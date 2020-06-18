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

diff gpxlist matchedlist > unmatchedlist
cat unmatchedlist | sed -e 's/\>\s//g' > gpxunmatchedlist2

cat ../gpxunmatchedlist2.txt | while read line; do java -jar matching-web/target/graphhopper-map-matching-web-1.0-SNAPSHOT.jar match '/mnt/c/Users/bitas/folders/Uber/gpx_files/'$line > '/mnt/c/Users/bitas/folders/Uber/gpx_matched/'$line'_log.txt'; done




#### changes in intellij we made to be able to use profile "bfoot":


