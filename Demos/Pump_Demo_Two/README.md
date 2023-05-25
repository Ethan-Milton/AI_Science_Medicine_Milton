# Pump Demo 2

This is a demonstration of an Aquaponics System Control using Python and the `microdot` library. The system allows controlling various components of an aquaponics system, such as water pump, air pump, and light. It also displays system parameters like water level, temperature, and pH level.

## Prerequisites

Before running the code, make sure you have the following requirements met:

- Python 3.x installed on your machine.
- The `microdot` library installed (`pip install microdot`).
- The `pandas` library installed (`pip install pandas`).

## Usage

1. Clone or download the repository to your local machine.
2. Navigate to the directory containing the code.
3. Make sure you have a CSV file named `state.csv` in the same directory. If not, create an empty `state.csv` file.
4. Run the following command to start the web server:

   ```bash
   python filename.py
   ```

   Replace `filename.py` with the actual name of the Python file.

5. Open your web browser and enter the following URL: `http://localhost:8008`.
6. The Aquaponics System Control interface will be displayed.
7. Click on the buttons to toggle the status of the water pump, air pump, and light.
8. The buttons will change color and display the current status of each component.
9. The system parameters (water level, temperature, pH level) will be displayed below the buttons.
10. To set a specific value for a parameter, use the URL `http://localhost:8008/set_parameter/<parameter>/<value>`, replacing `<parameter>` with the parameter name ('water_level', 'temperature', or 'pH_level') and `<value>` with the desired value. The interface will update accordingly.

## Code Explanation

The code consists of several components:

- Importing the necessary libraries:

  ```python
  from microdot import Microdot, Response
  import pandas as pd

  app = Microdot()
  Response.default_content_type = 'text/html'
  ```

- Initializing the system's state using a DataFrame and loading/saving the state to a CSV file:

  ```python
  CSV_FILE = 'state.csv'

  system_df = pd.DataFrame([{
      'water_pump': 'OFF',
      'air_pump': 'OFF',
      'light': 'OFF',
      'water_level': '0',
      'temperature': '0',
      'pH_level': '0',
  }])

  def load_state_from_csv():
      global system_df
      system_df = pd.read_csv(CSV_FILE)

  def save_state_to_csv():
      system_df.to_csv(CSV_FILE, index=False)
  ```

- Defining the HTML template for displaying the Aquaponics System Control interface:

  ```python
  def htmldoc(water_pump_status, air_pump_status, light_status, water_level, temperature, pH_level):
      # ...
      return html
  ```

- Generating the HTML document based on the system's state:

  ```python
  def generate_html_doc():
      load_state_from_csv()
      data = system_df.iloc[0]
      return htmldoc(
          data['water_pump'],
          data['air_pump'],
          data['light'],
          data['water_level'],
          data['temperature'],
          data['pH_level'],
      )
  ```

- Defining the routes ("/", "/toggle/<component>", and "/set_parameter/<parameter>/<value>") that handle GET requests for displaying the interface and POST requests for toggling component status and setting parameter values.

- Running the application on the local server with debug mode enabled on
