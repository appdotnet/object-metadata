<!-- give your annotation a title -->
# Poll

<!-- specify the "type" for your annotation -->
> ### net.questionapp.poll

<!-- provide a description of what your annotation represents -->
The poll annotation is meant to facilitate voting in a Channel Environment. It's currently set up to use the Channel as the question and messages as the answers. Though a clever use of reply_to could make any Message a poll question.

It is currently recommended that polls be limited to 150 characters with up to 10 options. Each option is no longer than 100 characters. This is to stay within the annotation size limit, and have space for other annotations.

<!-- provide at least one example of what your annotation might look like in the wild -->
## Question Example (Placed on Channels)

~~~ js
{
    "type": "net.questionapp.poll",
    "value": {
        "question": "Does App.Net rock your socks?",
        "options": [
            'Yeah',
            'Of Course!',
            'Definitely!!'
        ]
    }
}
~~~

## Answer Example (Placed on Messages)

~~~ js
{
    "type": "net.questionapp.poll",
    "value": {
        "answer": "Definitely!!"
    }
}
~~~

<!-- provide a complete description of the fields in the "value" object for your annotation -->
## Question Fields

| Field         | Required? | Type   | Description                                                 |
| -----         | --------- | ----   | -----------                                                 |
| question      | Required  | string | A question to users.                                        |
| options       | Required  | list   | A list of strings to present as answer options.             |

## Anser Fields

| Field         | Required? | Type   | Description                                                 |
| -----         | --------- | ----   | -----------                                                 |
| answer        | Required  | string | A answer that matches one of the above options.             |

<!-- provide a way to contact you -->
## Maintainers
* Bryan Redeagle ([@misterpoppet](https://alpha.app.net/misterpoppet), [misterpoppet@gmail.com](mailto:misterpoppet@gmail.com))

<!-- provide references to compatible apps / service -->
## Used by
* [Question App.Net](https://questionapp.net)