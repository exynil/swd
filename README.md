# SWD - Simple Wallpaper Downloader

Shell script to download a random wallpaper from [wallhaven.cc](https://wallhaven.cc)

## Dependencies

- bash
- curl
- grep

## Options

You can configure it directly inside the script or per command line arguments (command line arguments will override settings made directly in the script).

`-l`, `--location` - location where the wallpapers will be stored

`-c`, `--categories` - categories to download from, eg. 111 for "General, Anime and People, 1 to include, 0 to exclude

`-p`, `--purity` - filter out content based on purity rating, eg. 111 for SFW, sketchy and NSFW content, 1 to include, 0 to exclude

`-r`, `--ratios` - only download wallpaper with given aspect ratios, separate multiple aspect ratios by ,

`-o`, `--order` - order ascending (asc) or descending (desc)

`-d`, `--dye`, `--color` - search for wallpapers containing the given color, color values are RGB without a leading #

`-s`, `--sorting` - sorting mode for wallpapers: latest, views, favorites, toplist, random

`-a`, `--atleast` - minimum resolution, show all images with a resolution greater than the specified value

| Aspect ratio | Resolution                                        |
|--------------|---------------------------------------------------|
| 5:4          | 1280x1024 1600x1280 1920x1536 2560x2048 3840x3072 |
| 4:3          | 1280x960 1600x1200 1920x1440 2560x1920 3840x2880  |
| 16:10        | 1280x800 1600x1000 1920x1200 2560x1600 3840x2400  |
| 16:9         | 1280x720 1600x900 1920x1080 2560x1440 2840x2160   |
| Ultrawide    | 2560x1080 3440x1440 3840x1600                     |
| All          | Do not include for all                            |


## Examples

```
$ ./swd -s latest -l "$HOME/Pictures" -a 2560x1080
```

```
$ ./swd -s favorites -l "$HOME/Pictures" -p 110
```
