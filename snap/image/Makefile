project?= pinball-table-hurd

-include ~/bin/mk-private.mk

gadget?=pc
base?=core
base_version?=20
architecture?=amd64
name?=${project}-${base}${base_version}-${architecture}-${gadget}
channel?=edge
developer_id?=$(shell snapcraft whoami \
	| grep 'developer-id:' | cut -d' ' -f2 \
	|| echo "TODO: https://ubuntu.com/core/docs/custom-images")
authority_id?=${developer_id}
brand_id?=${authority_id}
ubuntu_image_snap_options?=
# image_size?=3G
# ubuntu_image_snap_options+=--image-size ${image_size}
key?=${project}
all?=version
all+=pc
all+=pi

.PRECIOUS: \
	%.img \
	%.model \
#EOL

default: ${name}.img.gz
	du -hs $<

help:
	snap keys


all: ${all}
	-sync

${name}.json: ubuntu-image-${gadget}.json Makefile
	jq -M . $<
	sed -e "s|{architecture}|${architecture}|g" < $< \
	| jq -r '.["authority-id"] = "${authority_id}"' \
	| jq -r '.architecture = "${architecture}"' \
	| jq -r '.["brand-id"] = "${brand_id}"' \
	| sponge $@
	jq -M . $@

image: ${name}.img.gz
	du -hs $<

%.img: %.model
	ubuntu-image snap ${ubuntu_image_snap_options} -o $@ $<
	mv seed.manifest $@.manifest
	du -hsc $@

%.model: %.json timestamp Makefile
	cat $< | snap sign -k ${key} > $@.tmp
	mv $@.tmp $@

timestamp: ${name}.json
	sed -e "s|\"timestamp\": .*|\"timestamp\": \"$$(date -Iseconds --utc)\",|g" -i "$<"

clean:
	rm -fv *~ *.img *.img.gz *.model

%.img.gz: %.img
	rm -f "$@"
	du -hsc $<
	gzip -9 $<
	du -hsc $@

pc:
	${MAKE} gadget=$@ architecture=amd64

pi:
	${MAKE} gadget=$@ architecture=arm64

version:
	${MAKE} --version
	ubuntu-image --version
	snap --version
	jq --version

%.key.tmp:
	snap keys | grep "^${key}" \
	|| snap create-key ${key}
	snap keys | grep "^${key}" | awk '{ print $$2 }' | tee $@


register:
	snapcraft list | grep '^${project} ' && exit 1
	snapcraft whoami || snapcraft login
	snapcraft whoami | grep '^developer-id: ${developer_id}'
	snapcraft list | grep '^${project} ' || snapcraft register "${project}"
	snapcraft list | grep '^${project} '

${project}.reg.tmp:
	snapcraft list | grep '^${project} ' || ${MAKE} register
	snapcraft list | grep '^${project} ' | tee "$@"

key: ${project}.key.tmp
	ls $<

run/%: %.img
	sudo qemu-system-x86_64 \
	-enable-kvm -smp 2 -m 1500 -cpu host \
	-device virtio-vga,virgl=on \
	-drive file=/usr/share/OVMF/OVMF_CODE.fd,if=pflash,format=raw,unit=0,readonly=on \
	-device virtio-net-pci,netdev=net0 \
	-netdev user,id=net0,hostfwd=tcp::50022-:22,hostfwd=tcp::50080-:80 \
	-drive file=$<,format=raw

run: run/${name}
