# MarcusRS-Python

Hangman Game API Challenge

POST /games/
Starts a new game of Hangman. This endpoint should initialize a new game with a word and return a game ID.

GET /games/{game_id}
Retrieves the current state of the game identified by the provided game_id. The response should include the word with masked letters, the incorrect guesses made so far, the number of remaining attempts, and the game status (e.g. in progress, won or lost).

POST /games/{game_id}/guesses
Allows the player to make a letter guess for the game identified by game_id. The guess should be submitted as the request body in JSON format, containing the guessed letter. The response should include the updated game state after the guess.


Starting/Creating a new game
NOTE: the response below is just for demonstrative purposes, calling this API will return a different identifier each time.

Request: POST /games
Response: 201

"8dfff98b-976a-4141-9a96-38fb86522daf"
Retrieving current game state
NOTE: the ID in the path we use is from the game we have created, it will be different for each game created.

Request: GET /games/8dfff98b-976a-4141-9a96-38fb86522daf
Response: 200

{
  "word": "_ _ _ _ _",
  "incorrect_guesses": [],
  "remaining_attempts": 6,
  "status": "in progress"
}
Make a guess for a game
NOTE: the ID in the path we use is from the game we have created, it will be different for each game created.

Request: POST /games/8dfff98b-976a-4141-9a96-38fb86522daf/guesses
Request body:

{ "letter": "A" }  
Response: 201

{
  "word": "_ A _ _ _",
  "incorrect_guesses": [],
  "remaining_attempts": 6,
  "status": "in progress"
}
