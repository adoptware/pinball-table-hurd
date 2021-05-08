project?= pinball-table-hurd

-include ~/bin/mk-private.mk
authority_id ?= TODO
brand_id ?= ${authority_id}

gadget?=pc
base?=core
base_version?=20
architecture?=amd64
name?=${project}-${base}${base_version}-${architecture}-${gadget}
channel?=edge

snap_id?=$(shell snap info ${project} | grep '^snap-id:' | cut -d: -f2 | awk '{ print $1 }' || echo "TODO")

all ?= pc
all += pi

.PRECIOUS: %.model

default: ${name}.img.gz
	du -hs $<

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

%.img: %.model
	ubuntu-image snap -o $@ $<
	mv seed.manifest $@.manifest
	du -hsc $@

%.model: %.json Makefile
	cat $< | snap sign -k default > $@.tmp
	mv $@.tmp $@

timestamp: ${name}.json
	sed -e "s|\"timestamp\": .*|\"timestamp\": \"$$(date -Iseconds --utc)\",|g" -i "$<"

clean:
	rm -fv *~ *.img *.img.gz *.model

%.img.gz: %.img
	du -hsc $<
	gzip -9 $<
	du -hsc $@

pc:
	${MAKE} gadget=$@ architecture=amd64

pi:
	${MAKE} gadget=$@ architecture=arm64
