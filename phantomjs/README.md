# PhantomJS - CasperJS

- [phantomjs](http://phantomjs.org/) ```2.0.0```
- [casperjs](http://casperjs.org/) ```master (latest)```

## Usage

```sh
sudo docker run fentas/phantomjs /usr/bin/phantomjs -v
sudo docker run fentas/phantomjs /usr/bin/casperjs --version
sudo docker run -v `pwd`:/mnt/test fentas/phantomjs /usr/bin/phantomjs /mnt/test/test.js
```
