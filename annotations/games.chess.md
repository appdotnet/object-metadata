<!-- give your annotation a title -->
# Chess

<!-- specify the "type" for your annotation -->
> ### games.chess

<!-- provide a description of what your annotation represents -->
This is based on discussion at [Issue 164](https://github.com/appdotnet/api-spec/issues/164), which has more information including validation and explanation.

The type in all cases is "games.chess".  Clients can optionally support the old namespace "net.app.mattflaschen.chess".

The current version is "1.0", which should be included in the root of all posts. This may change as needed if discussed at the issue.

<!-- provide at least one example of what your annotation might look like in the wild -->
## Examples

Not an app.net correspondence game (for example it might be a historic tournament game) where white won (... would not be in real PGN) with optional selected_ply (which indicates which move should be displayed initially):

```javascript
"value": {
    "version": "1.0",
    "result": "1-0",
    "pgn": "[Date \\"2011.07.22\\"] ... 1. e4 e5 ... 33.Qxe7# 1-0",
    "selected_ply": "5"
}
```

Challenge as white:

```javascript
"value": {
    "version": "1.0",
    "correspondence": {
        "white": "mattflaschen",
        "black": "davidkrauser"
    },
    "pgn": "1. e4"
}
```

Challenge as black:

```javascript
"value": {
    "version": "1.0",
    "correspondence": {
        "white": "davidkrauser",
        "black": "mattflaschen"
    }
}
```

Black accepts:

```javascript
"value": {
    "version": "1.0",
    "result": "*",
    "correspondence": {
        "white": "mattflaschen",
        "black": "davidkrauser",
        "challenge_post_id": "123"
    },
    "pgn": "1. e4 e5"
}
```

Black rejects:

```javascript
"value": {
    "version": "1.0",
    "result": "rejected",
    "correspondence": {
        "white": "mattflaschen",
        "black": "davidkrauser",
        "challenge_post_id": "123"
    },
    "pgn": "1. e4"
}
```

White accepts:

```javascript
"value": {
    "version": "1.0",
    "result": "*",
    "correspondence": {
        "white": "davidkrauser",
        "black": "mattflaschen",
        "challenge_post_id": "123"
    },
    "pgn": "1. d4"
}
```

White rejects:

```javascript
"value": {
    "version": "1.0",
    "result": "rejected",
    "correspondence": {
        "white": "davidkrauser",
        "black": "mattflaschen",
        "challenge_post_id": "123"
    }
}
```

Follow-up black move after white acceptance:

```javascript
"value": {
    "version": "1.0",
    "result": "*",
    "correspondence": {
        "white": "davidkrauser",
        "black": "mattflaschen",
        "challenge_post_id": "123"
    },
    "pgn": "1. d4 d5"
}
```

Follow-up white move after black acceptance:
```javascript
"value": {
    "version": "1.0",
    "result": "*",
    "correspondence": {
        "white": "mattflaschen",
        "black": "davidkrauser",
        "challenge_post_id": "123"
    },
    "pgn": "1. e4 e5 2. d4"
}
```

Hypothetical black move:

```javascript
"value": {
    "version": "1.0",
    "result": "*",
    "correspondence": {
        "white": "mattflaschen",
        "black": "davidkrauser",
        "challenge_post_id": "123",
        "is_final": false
    },
    "pgn": "1. e4 e5 2. d4 d5"
}
```

White wins by checkmate:
```javascript
"value": {
    "version": "1.0",
    "result": "1-0",
    "correspondence": {
        "white": "mattflaschen",
        "black": "davidkrauser",
        "challenge_post_id": "123"
    },
    "pgn": "[Result \\"1-0\\"] 1. e4 e5 2. d4 ... 23. Be7# 1-0"
}
```

White resigns/black wins:
```javascript
"value": {
    "version": "1.0",
    "result": "0-1",
    "correspondence": {
        "white": "mattflaschen",
        "black": "davidkrauser",
        "challenge_post_id": "123"
    },
    "pgn": "[Result \\"0-1\\"] [Termination \\"davidkrauser won by resignation\\"] 1. e4 e5 2. d4 ... 23. 0-1"
}
```
Draw (by agreement):
```javascript
"value": {
    "version": "1.0",
    "result": "1/2-1/2",
    "correspondence": {
        "white": "mattflaschen",
        "black": "davidkrauser",
        "challenge_post_id": "123"
    },
    "pgn": "[Result \\"1/2-1/2\\"] [Termination \\"Draw by agreement\\"] 1. e4 e5 2. d4 ... 23. 1/2-1/2"
}
```

<!-- provide a way to contact you -->
## Maintainers
* Matthew Flaschen ([@mattflaschen](https://alpha.app.net/mattflaschen)

<!-- provide references to compatible apps / service -->
## Used by

[Apppassant](http://dev.apppassant.com/)

<!-- provide references to related annotations -->
## Related annotations
 

