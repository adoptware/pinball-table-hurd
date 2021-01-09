# PINBALL-TABLE-HURD #

[![GitHub forks](
https://img.shields.io/github/forks/rzr/pinball-table-hurd.svg?style=social&label=Fork&maxAge=2592000
)](
https://github.com/rzr/pinball-table-hurd
)
[![Packaging status](
https://repology.org/badge/tiny-repos/pinball-table-hurd.svg
)](
https://repology.org/project/pinball-table-hurd/versions
)
[![Fediverse](
https://img.shields.io/mastodon/follow/279303?domain=https%3A%2F%2Fmastodon.social&style=social#
)](
https://mastodon.social/@rzr/104267382681571109#pinball-table-hurd#
)

## INFOS ##

HURD Pinball table for emilia pinball

Another pinball table to have fun, behaviour plugin.
The table is dedicated to GNU/Hurd project.
It features shoot cave, multiballs, ramps and bumpers.

For more details check file:

- [data/hurd/README.txt](data/hurd/README.txt)

## DEMO ##

[![Video](
https://files.mastodon.social/media_attachments/files/105/527/493/453/847/897/small/79821cafe85c6ad9.png
)](
https://rzr.github.io/rzr-presentations/docs/pinball/#/17/:PinballTableHurd:
)

Watch video on PeerTube:

- <https://mastodon.social/@rzr/104267382681571109#:pinball-table-hurd:>

## USAGE ##

It's easy build table assuming that Emilia pinball headers installed in system.

```sh
./bootstrap && ./configure && make && make install
```

For Debian users building a package can be automated using:

```sh
./debian/rules rule/setup && ./debian/rules && sudo debi
```

Then new table should be listed when you run pinball game.

Also a Dockerfile can be used as reference env.

```sh
docker-compose up --build
```

## RESOURCES ##

- <https://repology.org/project/pinball-table-hurd>
- <https://tracker.debian.org/pkg/pinball-table-hurd>
- <https://pinball.sf.net>
- <https://purl.org/rzr/pinball>
- <https://github.com/rzr/pinball/issues/4>
- <https://github.com/paolo-caroni/pinball/commit/377734778363b9d1397bc645bc4c755a5de66a68>
- <https://mastodon.social/@rzr/103809517516701240#pinball-table-hurd>
- <https://rzr.github.io/rzr-presentations/docs/pinball/>
- <https://purl.org/rzr>
- <https://purl.org/rzr/presentations>
- <https://mdco2.mini.debconf.org/talks/23-my-diy-pinball-on-debian/>
- <https://peertube.debian.social/videos/watch/c23f0709-4099-4302-b877-f7d2562b2880#my-diy-pinball-on-debian>
- <https://github.com/rzr/pinball-table-gnu/>
