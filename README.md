# PINBALL-TABLE-HURD #


## INFOS ##

For more details check file:

  * data/hurd/README.txt


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
docker build .
docker-compose up
```


## RESOURCES ##

  * <https://pinball.sf.net>
  * <https://github.com/rzr/pinball/issues/4>
  * <https://github.com/paolo-caroni/pinball/commit/377734778363b9d1397bc645bc4c755a5de66a68>
