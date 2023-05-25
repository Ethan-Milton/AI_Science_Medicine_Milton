# Traffic Light Web App

This is a simple web application that simulates a traffic light. The application is built using Python and utilizes the `microdot` library for creating a web server.

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
5. The traffic light will be displayed with the initial light configuration.
6. Click on each light to toggle it on or off.

## Code Explanation

The code consists of a few main components:

- Importing the necessary libraries:

  ```python
  from microdot import Microdot, Response
  app = Microdot()
  Response.default_content_type = 'text/html'
  ```

- Defining the HTML template for displaying the traffic light:

  ```python
  def htmldoc():
      # ...
      return html
  ```

- Defining the colors for the red, yellow, and green lights:

  ```python
  reds = ["853737","ff6465"]
  yellows = ["907A4A","ffd782"]
  greens = ["4E7039","a5eb78"]
  ```

- Defining the route ("/") that displays the traffic light with the initial light configuration:

  ```python
  @app.route('/')
  def hello(request):
      # ...
      return htmldoc()
  ```

- Defining a dynamic route ("/toggle/<light_index>") that toggles the specified light and returns the updated HTML document:

  ```python
  @app.route('/toggle/<light_index>')
  def toggle_light(request, light_index):
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
- Inspired by various online tutorials and examples.
