# Dice Roll Web App

This is a simple web application that simulates rolling dice using SVG (Scalable Vector Graphics). The application is built using Python and utilizes the `microdot` library for creating a web server.

## Prerequisites

Before running the code, make sure you have the following requirements met:

- Python 3.x installed on your machine
- The `microdot` library installed (`pip install microdot`)

## Usage

1. Clone or download the repository to your local machine.
2. Navigate to the directory containing the code.
3. Run the following command to start the web server:

```bash
python filename.py
```

Replace `filename.py` with the actual name of the Python file.

4. Open your web browser and enter the following URL: `http://localhost:8008`.
5. Click on the buttons to roll the dice.
6. The dice will be displayed as SVG graphics with random numbers and background colors.

## Code Explanation

The code consists of a few main components:

- Importing the necessary libraries:

  ```python
  from microdot import Microdot, Response
  import random
  app = Microdot()
  Response.default_content_type = 'text/html'
  ```

- Defining a function to generate random hexadecimal color codes:

  ```python
  def random_color():
      # ...
      return color_code
  ```

- Defining the HTML template for displaying the dice rolls:

  ```python
  def htmldoc(dice_faces, background_colors):
      # ...
      return html
  ```

- Defining the home route ("/") that displays a single dice with a specific background color:

  ```python
  @app.route('/')
  def home(request):
      # ...
      return htmldoc([1], ['F0E68C'])
  ```

- Defining a dynamic route ("/roll/<num_dice>") that rolls a specific number of dice and returns the resulting HTML document:

  ```python
  @app.route('/roll/<num_dice>')
  def roll_dice(request, num_dice):
      # ...
      return htmldoc(dice_faces, background_colors)
  ```

- Running the application on the local server with debug mode enabled on port 8008:

  ```python
  app.run(debug=True, port=8008)
  ```

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more details.

## Acknowledgments

- The `microdot` library for providing a simple web framework for Python.
- Inspired by various online tutorials and examples.
