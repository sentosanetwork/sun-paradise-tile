# sun-paradise-tile


Vector and raster maps with GL styles. Server-side rendering by MapLibre GL Native. Map tile server for MapLibre GL JS, Android, iOS, Leaflet, OpenLayers, GIS via WMTS, etc.

Download vector tiles from [OpenMapTiles](https://data.maptiler.com/downloads/planet/).
## Getting Started with Node

Make sure you have Node.js version **18.17.0** or above installed. Node 20 is recommended. (running `node -v` it should output something like `v20.x.x`).

Install `tileserver-gl` with server-side raster rendering of vector tiles with npm. 

```bash
npm install -g tileserver-gl
```

Once installed, you can use it like the following examples.

using a mbtiles file
```bash
wget https://github.com/sentosanetwork/sun-paradise-tile/releases/download/tile/phuquoc.mbtiles
tileserver-gl --file phuquoc.mbtiles
[in your browser, visit http://[server ip]:8080]
```

using a config.json + style + mbtiles file
```bash
wget https://github.com/maptiler/tileserver-gl/releases/download/v1.3.0/test_data.zip
unzip test_data.zip
tileserver-gl
[in your browser, visit http://[server ip]:8080]
```

Alternatively, you can use the `tileserver-gl-light` npm package instead, which is pure javascript, does not have any native dependencies, and can run anywhere, but does not contain rasterization on the server side made with Maplibre GL Native.

## Getting Started with Docker

An alternative to npm to start the packed software easier is to install [Docker](https://www.docker.com/) on your computer and then run from the tileserver-gl directory

Example using a mbtiles file
```bash
wget https://github.com/maptiler/tileserver-gl/releases/download/v1.3.0/zurich_switzerland.mbtiles
docker run --rm -it -v $(pwd):/data -p 8080:8080 maptiler/tileserver-gl --file zurich_switzerland.mbtiles
[in your browser, visit http://[server ip]:8080]
```

Example using a config.json + style + mbtiles file
```bash
wget https://github.com/maptiler/tileserver-gl/releases/download/v1.3.0/test_data.zip
unzip test_data.zip
docker run --rm -it -v $(pwd):/data -p 8080:8080 maptiler/tileserver-gl
[in your browser, visit http://[server ip]:8080]
```

Example using a different path
```bash
docker run --rm -it -v /your/local/config/path:/data -p 8080:8080 maptiler/tileserver-gl
```
replace '/your/local/config/path' with the path to your config file


Alternatively, you can use the `maptiler/tileserver-gl-light` docker image instead, which is pure javascript, does not have any native dependencies, and can run anywhere, but does not contain rasterization on the server side made with Maplibre GL Native.

## Getting Started with Linux cli

Test from command line
```bash
wget https://github.com/maptiler/tileserver-gl/releases/download/v1.3.0/test_data.zip
unzip -q test_data.zip -d test_data
xvfb-run --server-args="-screen 0 1024x768x24" npm test
```

Run from command line
```bash
xvfb-run --server-args="-screen 0 1024x768x24" node .
```
