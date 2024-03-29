# supermarkets

## overpass query
```
[out:csv('name',::type,::lat,::lon,'addr:street','addr:unit','addr:city','addr:postcode';true;',')];
// search for the relation named Chattanooga
rel
  [place=city]
  ["wikidata"="Q186702"]
  ["name"="Chattanooga"];
// show the outline
out geom;
// turn the relation into an area
map_to_area;
// get all supermarkets in the area
nw[shop=supermarket][name](area);

out body center qt;
```
