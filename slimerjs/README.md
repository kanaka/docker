# SlimerJS - CasperJs

- [slimerjs](https://slimerjs.org/) ```0.9.5```
- [casperjs](http://casperjs.org/) ```1.1.0-beta3```

## Usage

```sh
docker run fentas/slimerjs /usr/bin/slimerjs -v
docker run fentas/slimerjs /usr/bin/casperjs | head -n 1
docker run -v `pwd`:/mnt/test fentas/slimerjs /usr/bin/slimerjs /mnt/test/test.js
```
