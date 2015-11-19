# Electron app to view OSM Vector Tiles offline

## Usage

1. Clone repository and install dependencies

```bash
git clone https://github.com/osm2vectortiles/offline-maps.git
cd offline-maps
npm install
```

2. Download necessary fonts

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
3. Download the visual style and change vector tile source

```bash
git clone https://github.com/mapbox/mapbox-studio-osm-bright.tm2.git ./resources/tiles.tm2
cd ./resources/tiles.tm2
open project.yml and replace source: "mapbox:///mapbox.mapbox-streets-v6" with source: "mbtiles://./resources/tiles.mbtiles"
```

4. Add mbtiles to ./resources folder

Place your mbtiles file to the resources folder and rename it to tiles.mbtiles

5. Run Electron app

```bash
cd offline-maps
npm start
```
