wiki page
https://wiki.openstreetmap.org/wiki/Import/Catalogue/Bergamo_addresses_import

audit map
http://audit.osmz.ru/project/BG-addrs/


workflow example:

query overpass http://overpass-turbo.eu/s/U9z

wget -O addresses.osm "http://overpass-api.de/api/interpreter?data=%5Bout%3Axml%5D%5Btimeout%3A25%5D%3Barea%5B%22name%22%3D%22Bergamo%22%5D%5B%22admin%5Flevel%22%3D%228%22%5D%2D%3E%2EsearchArea%3B%28nwr%5B%22addr%3Ahousenumber%22%5D%28area%2EsearchArea%29%3B%29%3Bout%20meta%20qt%20center%3B%0A"

conflate -i Comune_Bergamo_Numerazione_civica.json --osm addresses.osm -v  -c preview-BG.json profile.py
