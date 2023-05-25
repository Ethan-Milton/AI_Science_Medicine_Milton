# High Low Guessing Game

This is a simple web-based High Low Guessing Game built using Python and the `microdot` library. The game generates a random number between 1 and 100, and the player needs to guess the correct number.

## Prerequisites

Before running the code, make sure you have the following requirements met:

- Python 3.x installed on your machine.
- The `microdot` library installed (`pip install microdot`).

## Usage

1. Clone or download the repository to your local machine.
2. Navigate to the directory containing the code.
3. Run the following command to start the web server:

   ```bash
   python filename.py
   ```

   Replace `filename.py` with the actual name of the Python file.

4. Open your web browser and enter the following URL: `http://localhost:8008`.
5. The game will display a message prompting you to guess a number between 1 and 100.
6. Enter your guess in the input field and click the "Submit" button.
7. Based on your guess, the game will provide feedback: "Too low!" if your guess is lower than the random number, "Too high!" if your guess is higher, or "Correct!" if your guess is correct.
8. The number of guesses you have made will be displayed.
9. A circle with a color representing the result (red for too low, yellow for too high, green for correct) will be shown.
10. To start a new game, click the "New Game" button.

## Code Explanation

The code consists of a few main components:

- Importing the necessary libraries:

  ```python
  from microdot import Microdot, Response
  import random

  app = Microdot()
  Response.default_content_type = 'text/html'
  ```

- Defining the HTML template for displaying the game:

  ```python
  def htmldoc(guesses, message, color):
      # ...
      return html
  ```

- Generating a random number and initializing the number of guesses:

  ```python
  random_number = random.randint(1, 100)
  guesses = 0
  ```

- Defining the route ("/") that handles both GET and POST requests for playing the game:

  ```python
  @app.route('/', methods=['GET', 'POST'])
  def home(request):
      # ...
      return htmldoc(guesses, message, color)
  ```

- Handling the player's guess and providing feedback based on the guess:

  ```python
  if request.method == 'POST':
      guess = int(request.form.get('guess'))

      if guess < random_number:
          message = 'Too low!'
          color = '853737'  # Red
      elif guess > random_number:
          message = 'Too high!'
          color = '907A4A'  # Yellow
      else:
          message = 'Correct!'
          color = '4E7039'  # Green

      guesses += 1
  else:
      message = 'Guess a number between 1 and 100.'
      color = '515262'  # Grey
  ```

- Defining a route ("/new_game") that starts a new game by generating a new random number and resetting the number of guesses:

  ```python
  @app.route('/new_game', methods=['POST'])
  def new_game(request):
      # ...
      return htmldoc(guesses, 'Guess a number between 1 and 100.', '515262')  # Grey
  ```

- Running the application on the local server with debug mode enabled on port 8008:

  ```python
  app
