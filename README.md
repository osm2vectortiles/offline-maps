# Electron app to view OSM Vector Tiles offline

## Usage

### Clone repository and install dependencies

```bash
git clone https://github.com/osm2vectortiles/offline-maps.git
cd offline-maps
npm install
```

### Download necessary fonts to folder ./resources/fonts

```bash
mkdir -p ./tmp/mapbox-studio-default-fonts && \
mkdir -p ./resources/fonts && \
git clone https://github.com/mapbox/mapbox-studio-default-fonts.git ./tmp/mapbox-studio-default-fonts && \
cp ./tmp/mapbox-studio-default-fonts/**/*.otf ./resources/fonts && \
cp ./tmp/mapbox-studio-default-fonts/**/*.ttf ./resources/fonts && \
rm -rf ./tmp/

wget -P ./resources/fonts https://github.com/aaronlidman/Toner-for-Tilemill/raw/master/toner4tilemill/fonts/Arial-Bold.ttf && \
wget -P ./resources/fonts https://github.com/aaronlidman/Toner-for-Tilemill/raw/master/toner4tilemill/fonts/Arial-Regular.ttf && \
wget -P ./resources/fonts https://github.com/aaronlidman/Toner-for-Tilemill/raw/master/toner4tilemill/fonts/Arial-Unicode-Bold-Italic.ttf && \
wget -P ./resources/fonts https://github.com/aaronlidman/Toner-for-Tilemill/raw/master/toner4tilemill/fonts/Arial-Unicode-Bold.ttf && \
wget -P ./resources/fonts https://github.com/aaronlidman/Toner-for-Tilemill/raw/master/toner4tilemill/fonts/Arial-Unicode-Italic.ttf && \
wget -P ./resources/fonts https://github.com/aaronlidman/Toner-for-Tilemill/raw/master/toner4tilemill/fonts/Arial-Unicode-Regular.ttf
```
### Download the visual style

```bash
git clone https://github.com/mapbox/mapbox-studio-osm-bright.tm2.git ./resources/tiles.tm2
cd ./resources/tiles.tm2
open project.yml
```
### Download an mbtiles extract from [OSM2VectorTiles website](http://osm2vectortiles.org/downloads/)

```bash
wget https://osm2vectortiles-downloads.os.zhdk.cloud.switch.ch/v1.0/extracts/zurich.mbtiles
```

### Change the vector tile source to mbtiles
```diff
- source: "mapbox:///mapbox.mapbox-streets-v6"
+ source: "mbtiles://./resources/tiles.mbtiles"
```

### Add mbtiles file to ./resources folder

Place your mbtiles file to the resources folder and rename it to tiles.mbtiles

### Run Electron app

```bash
cd offline-maps
npm start
```

### Screenshot

![screenshot](./screenshot.png)
