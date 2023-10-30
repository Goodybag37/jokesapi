# jokesapi

1 GET Random Joke at /random
Response:
{
    "id": 43,
    "jokeText": "What did one ocean say to the other ocean? Nothing, they just waved.",
    "jokeType": "Wordplay"
}

2 GET Specific Joke
Responds with a single joke with the requested joke id.
Provide the joke id as a path parameter. at /jokes/2
Response:
{
    "id": 2,
    "jokeText": "Why did the scarecrow win an award? Because he was outstanding in his field.",
    "jokeType": "Puns"
}

3 GET Filtered Joke By Type
Filters all the jokes by their joke type.
Provide a query parameter for type and if the type exists, then you should get back all the jokes that match that type. at /filter?type=Puns
Response:
[
    {
        "id": 2,
        "jokeText": "Why did the scarecrow win an award? Because he was outstanding in his field.",
        "jokeType": "Puns"
    },
    {
        "id": 3,
        "jokeText": "I told my wife she was drawing her eyebrows too high. She looked surprised.",
        "jokeType": "Puns"
    },
    {
        "id": 7,
        "jokeText": "Why don't some couples go to the gym? Because some relationships don't work out.",
        "jokeType": "Puns"
    }
  ]


4 POST New Joke
curl --location '/jokes' 
--data-urlencoded 'text=Iamonthemoonandthereisnowheretogetabeer. Thereisnospacebar.' 
--data-urlencoded 'type=Science'
Response:
{
    "id": 101,
    "jokeText": "Iamonthemoonandthereisnowheretogetabeer. Thereisnospacebar.",
    "jokeType": "Science"
}

5 PATCH Edit Joke
Edit a joke for the id that is specified in the path parameter. /jokes/:id
Provide optional values for either the text or the type. 
Response:
{
    "id": 2,
    "jokeText": "Why did the scarecrow win a prize? Because he was outstanding in his field.",
    "jokeType": "Agriculture"
}

6 DELETE A Joke
Delete a joke from the bank of jokes based on the path parameter provided for the joke id. at /jokes:id
Will return an error if no jokes match the provided id.
Response OK

7 DELETE All Jokescurl --location --request DELETE at  /all
Delete all jokes in the bank.
DANGER.
Authentication:
Requires an API Key to perform this action.
Response OK










