# icao-aircraft-codes
[ICAO aircraft type designators](https://en.wikipedia.org/wiki/List_of_ICAO_aircraft_type_designators) in XML format. You can use this XML file containing most ICAO aircraft codes. This can be useful when you want to resolve an ICAO aircraft code to the aircraft's name without using an API. 
  
Last update: January 3rd 2018

# PHP example

```php
// Function to get the aircraft name from ICAO aircraft code
function ICAOToAircraft($ICAO) {
  $ICAOData = simplexml_load_string(file_get_contents('ICAO_AIRCRAFTS.xml'));

  foreach($ICAOData->icao_aircraft as $code) {
    if($code->code == $ICAO) return $code->aircraft;
  }
}
```
