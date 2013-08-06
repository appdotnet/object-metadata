# Place

<!-- specify the "key" for the replacement value -->
> ### +net.app.core.place

<!-- provide a description of the replacement value -->
This dynamically inserts information about a Place object into an annotation. The Place information is merged with any other values to form a single object.

### Deduplication effects

Because it is possible for duplicate entries to exist for the same Place, Factual provides a method to deduplicate one Place object by "replacing" it with another. As a result, you may notice sometimes that when you have stored a Place with one `factual_id` that you will later see an entry with a different `factual_id`. When we replace a `+net.app.core.place` in this way, we claim that it is equivalent to the one requested.

<!-- provide at least one example of what your annotation might look like in the wild -->
## Example

#### Provided to App.net
~~~ js
{
    "type": "com.example.test",
    "value": {
        "+net.app.core.place": {
            "factual_id": "0caa0bb0-cd40-012e-5616-003048cad9da"
        },
        "other_values": "are preserved"
    }
}
~~~

#### Returned by API
~~~ js
{
    "type": "com.example.test",
    "value": {
        "website": "http://www.bluebottlecoffee.net/locations/sfmoma/",
        "name": "Rooftop Garden Blue Bottle Coffee Bar",
        "locality": "San Francisco",
        "region": "CA",
        "telephone": "(415) 243-0455",
        "longitude": -122.400751,
        "is_open": true,
        "postcode": "94103",
        "factual_id": "0caa0bb0-cd40-012e-5616-003048cad9da",
        "address": "151 3rd St",
        "latitude": 37.78592,
        "country_code": "us",
        "categories": [
            {
                "labels": [
                    "Social",
                    "Food and Dining",
                    "Restaurants"
                ],
                "id":"347"
            }
        ]
        "other_values": "are preserved"
    }
}
~~~

<!-- provide a complete description of the fields in the "value" object for your annotation -->
## Fields

| Field | Required? | Type | Description |
| ----- | --------- | ---- | ----------- |
| `factual_id` | Required | string | A valid factual.com UUID corresponding to a Place object on App.net.|

<!-- provide a way to contact you -->
## Maintainers
* App.net core team

<!-- provide references to compatible apps / service -->
## Used by

<!-- provide references to related annotations -->
## Related annotations

* [net.app.core.checkin](https://github.com/appdotnet/object-metadata/blob/master/annotations/net.app.core.checkin.md)
