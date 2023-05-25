# Coin Flip Web App

This is a simple web application that allows you to flip a virtual coin by clicking on it. The application is built using Python and utilizes the `microdot` library for creating a web server.

## Prerequisites

Before running the code, make sure you have the following requirements met:

- Python 3.x installed on your machine
- The `microdot` library installed (`pip install microdot`)
- The `numpy` library installed (`pip install numpy`)

## Usage

1. Clone or download the repository to your local machine.
2. Navigate to the directory containing the code.
3. Run the following command to start the web server:

```bash
python filename.py
```

Replace `filename.py` with the actual name of the Python file.

4. Open your web browser and enter the following URL: `http://localhost:8008`.
5. Click on the coin to flip it.
6. The coin will randomly show either "Heads" or "Tails" along with the corresponding color.

## Code Explanation

The code consists of a few main components:

- Importing the necessary libraries:

  ```python
  import numpy as np
  from microdot import Microdot, Response
  ```

- Setting up the `Microdot` application and configuring the default content type to be HTML:

  ```python
  app = Microdot()
  Response.default_content_type = "text/html"
  ```

- Defining the HTML template for the coin flip display:

  ```python
  def htmldoc():
      # ...
      return html
  ```

- Defining the home route ("/") that generates a random coin state and returns the HTML document:

  ```python
  @app.route("/")
  def home(request):
      # ...
      return htmldoc()
  ```

- Defining the toggle route ("/toggle") that generates a new random coin state and returns the HTML document:

  ```python
  @app.route("/toggle")
  def toggle_coin(request):
      # ...
      return htmldoc()
  ```

- Running the application on the local server with debug mode enabled on port 8008:

  ```python
  app.run(debug=True, port=8008)
  ```

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more details.

## Acknowledgments

- The `microdot` library for providing a simple web framework for Python.
- The `numpy` library for generating random numbers for the coin flip.
- Inspired by various online tutorials and examples.
