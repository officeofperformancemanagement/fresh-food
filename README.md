# fresh food
> places to get fresh food in Chattanooga

## overpass query
```
[out:csv('name',::type,::lat,::lon,'addr:full','addr:housenumber','addr:unit','addr:street','addr:city','addr:postcode',opening_hours,amenity,shop,'brand:wikidata','payment:ebt','payment:snap','payment:wic';true;',')];

// search for the relation named Chattanooga
area
  [place=city]
  ["wikidata"="Q186702"]
  ["name"="Chattanooga"]->.a;


// get all fresh food options in the area
(
  nwr["shop"="butcher"][name](area.a);
  nwr["shop"="supermarket"][name](area.a);
  nwr["shop"="greengrocer"][name](area.a);
  
  nwr["social_facility"="food_bank"][name](area.a);
  nwr["social_facility"="soup_kitchen"][name](area.a);

  nwr["amenity"="marketplace"][name](area.a);
  nwr["shop"="farm"][name](area.a);  
  
  nwr["garden:type"="community"][name](area.a);
);

out body center;
```
