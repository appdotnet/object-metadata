<!-- give your annotation a title -->
# Checkin

<!-- specify the "type" for your annotation -->
> ### net.app.core.checkin

<!-- provide a description of what your annotation represents -->
Indicates that a user has "checked in" to a Place as part of creating a resource.

<!-- provide at least one example of what your annotation might look like in the wild -->
## Example

### Provided to App.net
~~~ js
{
    "type": "net.app.core.checkin",
    "value": {
        "+net.app.core.place": [
            {
                "factual_id": "db3808e0-ea21-012e-ba1b-002590044566"
            }
        ]
    }
}
~~~

### Returned by API

~~~ js
{
    "type": "net.app.core.checkin",
    "value": {
        "website": "http://www.borderlands-books.com",
        "name": "Borderlands Books",
        "locality": "San Francisco",
        "region": "CA",
        "telephone": "(415) 824-8203",
        "longitude": -122.421336,
        "is_open": true,
        "postcode": "94110",
        "factual_id": "db3808e0-ea21-012e-ba1b-002590044566",
        "address": "866 Valencia St",
        "latitude": 37.759064,
        "country_code": "us",
        "categories": [
            {
                "labels": [
                    "Retail",
                    "Bookstores"
                ],
                "id":"130"
            }
        ]
    }
}
~~~

<!-- provide a complete description of the fields in the "value" object for your annotation -->
## Fields

| Field | Required? | Type | Description |
| ----- | --------- | ---- | ----------- |
| `+net.app.core.place` | Required | object | An object that matches the [+net.app.core.place](https://github.com/appdotnet/object-metadata/blob/master/annotation-replacement-values/+net.app.core.place.md) validations (contains a valid `factual_id`.|

<!-- provide a way to contact you -->
## Maintainers
* [Orian Marx](http://orianmarx.com) ([@orian](https://alpha.app.net/orian), [orian@app.net](mailto:orian@app.net))

<!-- provide references to compatible apps / service -->
## Used by
* Your app here!

<!-- provide references to related annotations -->
## Related annotations
* [+net.app.core.place](https://github.com/appdotnet/object-metadata/blob/master/annotation-replacement-values/+net.app.core.place.md)
