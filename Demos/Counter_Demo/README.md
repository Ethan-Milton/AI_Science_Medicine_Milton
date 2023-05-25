# Counter

This code demonstrates a simple counter using Python and the `microdot` library. The counter starts at 0 and can be incremented or decremented by clicking the corresponding buttons on a web interface.

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
5. The Counter Demo interface will be displayed.
6. The current value of the counter will be shown as the page title and in the heading.
7. Click the "Increment" button to increase the counter value by 1.
8. Click the "Decrement" button to decrease the counter value by 1.
9. The page will refresh and display the updated counter value.

## Code Explanation

The code consists of the following components:

- Importing the necessary libraries:

  ```python
  from microdot import Microdot, Response

  app = Microdot()
  Response.default_content_type = 'text/html'
  ```

- Defining the HTML template for displaying the Counter Demo interface:

  ```python
  def htmldoc(counter):
      # ...
      return html
  ```

- Defining the routes ("/" and "/change/<current_counter>/<step>") that handle GET requests for displaying the interface and incrementing/decrementing the counter value:

  ```python
  @app.route('/')
  def home(request):
      return htmldoc(0)

  @app.route('/change/<current_counter>/<step>')
  def change(request, current_counter, step):
      counter = int(current_counter) + int(step)
      return htmldoc(counter)
  ```

- Running the application on the local server with debug mode enabled on port 8008.

The interface allows users to increment or decrement the counter value by clicking the corresponding buttons. The counter value is updated and displayed on the web page accordingly.

---

# Data Points Scatter Plot

This code generates a scatter plot of random data points using Python, the `microdot` library, and the `matplotlib` library. The number of data points can be specified in the URL, and the scatter plot is displayed as an SVG image.

## Prerequisites

Before running the code, make sure you have the following requirements met:

- Python 3.x installed on your machine.
- The `microdot` library installed (`pip install microdot`).
- The `matplotlib` library installed (`pip install matplotlib`).

## Usage

1. Clone or download the repository to your local machine.
2. Navigate to the directory containing the code.
3. Run the following command to start the web server:

   ```bash
   python filename.py
   ```

   Replace `filename.py` with the actual name of the Python file.

4. Open your web browser and enter the following URL: `http://localhost:5000`.
5. The scatter plot with 10 data points will be displayed.
6. To change the number of data points, append the desired number to the URL, e.g., `http://localhost:5000/20` for 20 data points.
7. The scatter plot will refresh and display the updated number of data points.

## Code Explanation

The code consists of the following components:

- Importing the necessary libraries:

 
