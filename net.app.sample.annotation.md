<!-- give your annotation a title -->
### Sample

<!-- specify the "type" for your annotation -->
> ### net.app.sample.annotation

<!-- provide a description of what your annotation represents -->
This is a sample annotation

<!-- provide at least one example of what your annotation might look like in the wild -->
## Example

~~~ js
{
    "type": "net.app.sample.annotation",
    "value": {
        "is_sample": "true",
        "num_properties": "2" 
    }
}
~~~

<!-- provide a complete description of the fields in the "value" object for your annotation -->
## Fields

| Field | Required? | Type | Description |
| ----- | --------- | ---- | ----------- |
| `is_sample` | Required | boolean | Whether or not the annotation is a sample. |
| `num_properties` | Optional | integer | The number of properties in the `value` object |

<!-- provide a way to contact you -->
## Maintainers
* [Orian Marx](http://orianmarx.com) ([@orian](https://alpha.app.net/orian), [orian@app.net](mailto:orian@app.net))

<!-- provide references to compatible apps / service -->
## Used by 
* This annotation is used by the [annotations repository](annotations/)

<!-- provide references to related annotations -->
## Related annotations ##
* None