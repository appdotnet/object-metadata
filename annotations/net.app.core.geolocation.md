<!-- give your annotation a title -->
# Geolocation 

<!-- specify the "type" for your annotation -->
> ### net.app.core.geolocation

<!-- provide a description of what your annotation represents -->
The geolocation annotation is meant to specify a geographic point on the Earth. It is not meant to specify:

* a human place (city, building, park, "San Francisco", "The Mission", "The Moscone Center"). We're investigating how to efficiently provide this data in the core api.
* paths, regions, or complex geographic shapes. We recommend using a common schema (like [GeoJSON](http://www.geojson.org/)) in your own annotation if you need this kind of solution.

<!-- provide at least one example of what your annotation might look like in the wild -->
## Examples

Just the required parameters:

~~~ js
{
    "type": "net.app.core.geolocation",
    "value": {
        "latitude": 74.0064,
        "longitude": 40.7142
    }
}
~~~

With all optional parameters:

~~~ js
{
    "type": "net.app.core.geolocation",
    "value": {
        "latitude": 74.0064,
        "longitude": 40.7142,
        "altitude": 4400,
        "horizontal_accuracy": 100,
        "vertical_accuracy": 100
    }
}
~~~

<!-- provide a complete description of the fields in the "value" object for your annotation -->
## Fields

| Field                 | Required? | Type    | Description                                                                                                              |
| -----                 | --------- | ----    | -----------                                                                                                              |
| `latitude`            | Required  | decimal | The latitude of the geographic location in decimal degrees. Must range from -90 (the South Pole) to 90 (the North Pole). |
| `longitude`           | Required  | decimal | The longitude of the geographic location in decimal degrees. Must range from -180 to 180.                                |
| `altitude`            | Optional  | decimal | The altitude (in meters) of the geographic location. Can be negative.                                                    |
| `horizontal_accuracy` | Optional  | decimal | The horizontal accuracy (in meters) of the instrument providing this geolocation point. Must be >= 0.                    |
| `vertical_accuracy`   | Optional  | decimal | The vertical accuracy (in meters) of the instrument providing this geolocation point. Must be >= 0.                      |

<!-- provide a way to contact you -->
## Maintainers
* App.net core team

<!-- provide references to compatible apps / service -->
## Used by

<!-- provide references to related annotations -->
## Related annotations
