# kayak-trips


## install osmosis
https://wiki.openstreetmap.org/wiki/Osmosis/Installation#Linux


## start post gis database
```
cd postgress; docker-compose up
```

### Datenbank initialisieren
PGPASSWORD="blub" psql -h 192.168.168.161 -p 5432 -U postgres -v techuser="kayak" -v password="'kayak'"  -f postgres/create_user_and_db.sql
PGPASSWORD="blub" psql -h 192.168.168.161 -p 5432 -U postgres -f postgres/postgis_hstore_activation.sql

### PGSNAPSHOTSHEMA

cd downloads/osmosis/script/
PGPASSWORD="kayak" psql -d kayakdb -f pgsnapshot_schema_0.6.sql -h 192.168.168.161 -p 5432 -U kayak
PGPASSWORD="kayak" psql -d kayakdb -f pgsnapshot_schema_0.6_action.sql -h 192.168.168.161 -p 5432 -U kayak
PGPASSWORD="kayak" psql -d kayakdb -f pgsnapshot_schema_0.6_bbox.sql -h 192.168.168.161 -p 5432 -U kayak
PGPASSWORD="kayak" psql -d kayakdb -f pgsnapshot_schema_0.6_linestring.sql -h 192.168.168.161 -p 5432 -U kayak





## osm file
http://download.geofabrik.de/europe.html

## create xml data

# https://tagfinder.herokuapp.com/search?query=waterway&lang=en
downloads/osmosis/bin/osmosis --read-pbf file=downloads/unterfranken-latest.osm.pbf --tf accept-ways "waterway=*" --used-node --log-progress --write-xml unterfranken.osm

downloads/osmosis/bin/osmosis --read-pbf file=downloads/unterfranken-latest.osm.pbf --tf accept-ways "waterway=*" "railway=*" --used-node --log-progress --write-pgsql host=192.168.168.161  database=kayakdb user="kayak" password="kayak"

# 
```
jupyter notebook --allow-root
```
