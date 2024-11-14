# Rasp-Car
A Raspberry pi 4b car, this is a project implementing the use of python to code and build a functioning car

## Code Requirements 
To execute any of the code in the subfolders, ensure you are running on a python virtual environment (venv). If no, create one and use it from the termimal: 
```bash
python3 -m venv rasp-car
source rasp-car/bin/activate
```

If you need to get out of the venv, just use __deactivate__
```bash
deactivate
```

Ensuring you are in a venv, install the requirements using: 
```bash
pip3 install -r requirements.txt
```

Now you can run any part of the code, ensure you read the documentation provided in every part and in the code.

## Run 

To test the controllers and everything, use the test.py file, it is part of the module car_logic if you are running it from outside you can use:

```bash
python -m car_logic.test
```
If you are running it from car_logic folder user: 
```bash
python -m test
```

## File Descriptions

### Connections

This folder contains the files used to communicate between the different sensors via HTTP requests. Each sensor is mapped to an endpoint with API urls.

### Motors

The motors folder provides functionality to control motor movements using a Raspberry Pi and a motor driver. It includes code to initialize and manage motor directions (forward, backward, left, right, and spins) through GPIO pins, along with a test script to verify motor operations.

### Sensors
  
This folder provides setup instructions and code for controlling motor movements and connecting sensors to a Raspberry Pi. It includes necessary library installations, wiring guidance, and a class to manage motor actions. Testing scripts are also provided to verify the setup and functionality.

### setGPIO.py

This script provides utility functions for configuring and controlling GPIO pins on a Raspberry Pi. It includes functions to configure specific pins as outputs, and set output states for those pins. These functions are designed to handle errors and offer optional print feedback to indicate the status of operations.

### setupControllers.py

This script provides a function to initialize and configure multiple controllers, including motor, sensor, API, MQTT, and database controllers. It retrieves configuration data from an API endpoint and uses optional parameters to override defaults for MQTT and database settings. If the API lacks necessary configurations, it raises an error. This setup ensures all controllers are ready for coordinated operation in a connected environment.


## Test.py
# Sensor and Motor Controller with API and MQTT Integration

This Python script is designed to control various types of hardware (motors and sensors) and facilitate data communication with external systems using API, MQTT, and direct SQL database connections. It provides a menu-driven interface to interact with hardware and to send sensor data to various platforms.

## Features

The application includes the following functionalities:

1. **Main Menu**: 
   - Allows selection between motor control, sensor data reading, and data transmission using different protocols (API, MQTT, SQL).

2. **Motor Control**:
   - Provides options to control motor movements, including moving forward, backward, turning, and spinning in place.

3. **Sensor Control**:
   - Allows reading data from various sensors such as Light, Accelerometer, Environmental, and Distance sensors. 
   - Displays individual sensor data or reads all sensor data at once.

4. **Data Transmission via API**:
   - Sends sensor data to a specified API endpoint. Each sensor type (Light, Accelerometer, Environmental, Distance) has dedicated options to transmit data.
   - Supports bulk transmission of all sensor data to the API.

5. **Data Transmission via MQTT**:
   - Sends sensor data to an MQTT broker.
   - Allows sending data for individual sensors or all sensors at once to predefined MQTT topics.

6. **Direct Database Transmission**:
   - Sends sensor data directly to a database using SQL.
   - Provides individual transmission options for Light, Accelerometer, Environmental, and Distance data.

## Usage

### Running the Script

The script accepts the following command-line arguments:

- `baseUrl` (required): The base URL for the API server.
- `mqttBroker` (optional): The address of the MQTT broker.
- `mqttPort` (optional): The port of the MQTT broker.
- `mqttTopic` (optional): The base topic for MQTT.
- `dbURL` (optional): URL of the database for a direct SQL connection.

```bash
python main.py <baseUrl> <mqttBroker> <mqttPort> <mqttTopic> <dbURL>



