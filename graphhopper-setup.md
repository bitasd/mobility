## Map-matching
##### refer to :https://github.com/graphhopper/map-matching/blob/master/README.md
#### navigate to the folder
cd Uber/map-matching-master/
#### creates a jar file
mvn package -DskipTests
#### import the osm network
java -jar matching-web/target/graphhopper-map-matching-web-1.0-SNAPSHOT.jar import map-data/latestarizna.osm.pbf 
#### Matching using the desired gpx files
ls -f gpx_files > gpxlist.txt

cat ../gpxlist.txt | while read line; do java -jar matching-web/target/graphhopper-map-matching-web-1.0-SNAPSHOT.jar match '/mnt/c/Users/bitas/folders/Uber/gpx_files/'$line | grep 'gpx length:.*'| grep -o '[0-9]*\.[0-9]* vs [0-9]*\.[0-9]*' | sed -e 's/\svs\s/\, /g' > '/mnt/c/Users/bitas/folders/Uber/gpx_matched/'$line'_log.txt'; done


diff file1 file 2 > diff_file
cat diff_file | sed -e 's/\>\s//g' > diff_file2

cat ../gpxunmatchedlist2.txt | while read line; do java -jar matching-web/target/graphhopper-map-matching-web-1.0-SNAPSHOT.jar match '/mnt/c/Users/bitas/folders/Uber/gpx_files/'$line > '/mnt/c/Users/bitas/folders/Uber/gpx_matched/'$line'_log.txt'; done
Problem with file /mnt/c/Users/bitas/folders/Uber/gpx_files/10860.gpx
