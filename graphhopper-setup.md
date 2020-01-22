## Map-matching
##### refer to :https://github.com/graphhopper/map-matching/blob/master/README.md
#### navigate to the folder
cd Uber/map-matching-master/
#### creates a jar file
mvn package -DskipTests
#### import the osm network
java -jar matching-web/target/graphhopper-map-matching-web-1.0-SNAPSHOT.jar import map-data/latestarizna.osm.pbf 
#### Matching using the desired gpx files
java -jar matching-web/target/graphhopper-map-matching-web-1.0-SNAPSHOT.jar match /mnt/c/Users/bitas/folders/Uber/trip_id.gpx  > res.log
