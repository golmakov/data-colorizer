# Data Colorizer

A plugin for Bohemiancoding Sketch for re-coloring graphics based on JSON data files. It takes JSON file as a data source and changes stroke/fill of shapes.

This plugin was ispired by Gregor Aisch's [Illustrator script](https://www.vis4.net/blog/2017/03/re-coloring-illustrator-graphics-based-on-data-files/)


## Usage

Create the JSON file with simmilar structure:
```JSON
[{
    "data": {
        "AL": { "fill": "#cc3d3d", "stroke": false },
        "AK": { "fill": "#cc3d3d", "stroke": false },
        "AZ": { "fill": "#cc3d3d", "stroke": false },
        "AR": { "fill": "#cc3d3d", "stroke": false },
        "CA": { "fill": "#1a80c4", "stroke": false },
        "CO": { "fill": "#1a80c4", "stroke": false },
        //...
    }
}]
```

The keys under the `data` section need to match the shape names in the Sketch document, in our case the two-letter state codes. The `fill` and `stroke` keys define colors in which shapes will be colored. If you set stroke or fill to false, Sketch will remove the stroke/fill. If you want either stroke or fill to be left unchanged, simply leave them out in the data file.

You can use whatever script or data source you want to create this file.

Run the plugin from `Plugins → Re-color with data...`. The file open dialog will pop up asking you for the location of the JSON data file.



## Install Instructions

Download [archive]() and extract contents, then double-click on the `DataColorizer.sketchplugin` file.

Or if you using [Runner](http://sketchrunner.com), just go to the `install` command and search for `Data Colorizer`


## Building from Source

```bash
# Install the dependencies
npm install

# Build an watch for changes
npm run watch

# Watch for sketch plugins logs
skpm log -f

# Always reload scripts before running
defaults write ~/Library/Preferences/com.bohemiancoding.sketch3.plist AlwaysReloadScript -bool YES
```