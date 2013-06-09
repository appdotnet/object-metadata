<!-- give your annotation a title -->
# Custom Checkin

<!-- specify the "type" for your annotation -->
> ### net.app.ohai.location

<!-- provide a description of what your annotation represents -->
Indicates that a user has "checked in" to a custom place as part of a resource. This is meant to be identical to a normal [checkin](https://github.com/appdotnet/object-metadata/blob/master/annotations/net.app.core.checkin.md), but used when a Place does not exist for a given location. Every field is identical to the checkin annotation, except `factual_id` is instead just `id`. All fields are optional, except for the `id` field, which must be some unique identifier (a UUID is recommended).

<!-- provide at least one example of what your annotation might look like in the wild -->
## Example

### Provided to App.net

~~~ js
{
    "type": "net.app.ohai.location", 
    "value": {
        "address": "20 Yerba Buena Lane", 
        "country_code": "US", 
        "id": "B572B5D8-5D5D-43F7-96D5-D9EB6D5D188E", 
        "latitude": 37.78612, 
        "locality": "San Francisco", 
        "longitude": -122.404631, 
        "name": "Press Club", 
        "postcode": "94103", 
        "region": "California"
    }
}
~~~

<!-- provide a complete description of the fields in the "value" object for your annotation -->
## Fields

| Field | Required? | Type | Description |
| ----- | --------- | ---- | ----------- |
| `id` | Required | string | Primary identifier for a place. If you check in to a place multiple times, each place should have the same `id`. Recommended to be a UUID. |
| `name` | Optional | string | Human-friendly name. |
| `address` | Optional | string | Street address. |
| `address_extended` | Optional | string | Apartment or Suite number in street address. |
| `locality` | Optional | string | City or town. |
| `region` | Optional | string | State, region, province etc. |
| `admin_region` | Optional | string | Additional sub-division (e.g. Wales). |
| `post_town` | Optional | string | Town used in postal addressing. |
| `po_box` | Optional | string | PO Box. |
| `postcode` | Optional | string | Postcode / zipcode. |
| `country_code` | Optional | string | A two-letter country code in ISO 3166-1 alpha-2 format. |
| `latitude` | Optional | decimal | Latitude in decimal degrees. |
| `longitude` | Optional | decimal | Longitude in decimal degrees. |
| `is_open` | Optional | boolean | Whether the establishment is still "in business" and/or open to the public and does not refer to business hours or whether it may be serving customers at any particular moment in time. |
| `telephone` | Optional | string | Telephone number in local formatting. |


<!-- provide a way to contact you -->
## Maintainers
* [Steve Streza](http://stevestreza.com) ([@SteveStreza](https://alpha.app.net/SteveStreza))

<!-- provide references to compatible apps / service -->
## Used by 
* [Ohai](http://ohaiapp.net)

<!-- provide references to related annotations -->
## Related annotations
* [+net.app.core.place](https://github.com/appdotnet/object-metadata/blob/master/annotation-replacement-values/+net.app.core.place.md)
* [net.app.core.checkin](https://github.com/appdotnet/object-metadata/blob/master/annotation/net.app.core.checkin.md)