# Geotagging images from gpx file

Use correct geosync value to assign locations

    exiftool -overwrite_original -geosync=0:0 -geotag 2930949.gpx ./

# GPX memos using exiftool and gpsbabel

## Create gpx file from geotagged series of pictures

Extract location EXIF information from pictures and build a gpx file from them

    exiftool -fileOrder gpsdatetime -p gpx/gpx_original.fmt ~/Pictures/ > my_track.gpx

Extract location EXIF information from pictures and build a gpx file from them (using GITUP G3 action camera)

    exiftool -fileOrder gpsdatetime -p gpx/gpx.fmt ~/Pictures/ > my_track.gpx

## Create gpx file from geotagged video

Extract location EXIF information from geotagged video and build a gpx file from them

    exiftool -ee -fileOrder gpsdatetime -p fmt/gpx_video.fmt ~/Videos/ > my_track_video.gpx

## Convert kml files to gpx format

Using GPSBabel website: http://www.gpsbabel.org

    gpsbabel -i kml -f ./myfile.kml -o gpx -F ./myfile.gpx
