# Temperaturereporting-rpi

# Raspberry Pi Temperature Reporting System

This is a Raspberry Pi-based temperature reporting system that reads temperature values from a DHT11 sensor and reports them to Adafruit IO. It also includes a feature to send email notifications via IFTTT when the temperature exceeds a threshold.

## Prerequisites

To run this project, you will need:

- Raspberry Pi
- DHT11 temperature and humidity sensor
- Python 3 installed on Raspberry Pi
- Adafruit_DHT library
- Adafruit_IO library
- Adafruit IO account
- IFTTT account

## Hardware Setup

1. Connect the DHT11 sensor to the Raspberry Pi's GPIO pin. Make sure to note down the pin number you used.

## Software Setup

1. Install the required libraries:

   ```bash
   pip install Adafruit_DHT Adafruit_IO
   ```

2. Create an account on Adafruit IO (https://io.adafruit.com/).

3. Create a feed on Adafruit IO for storing temperature values.

4. Set up an IFTTT account and install the IFTTT app on your mobile device.

## Configuration

1. Open the `temperature_reporting.py` file.

2. Set the following variables:
   - `ADAFRUIT_IO_USERNAME`: Your Adafruit IO username.
   - `ADAFRUIT_IO_KEY`: Your Adafruit IO API key.
   - `dht_pin`: GPIO pin number connected to the DHT11 sensor.
   - `threshold`: Temperature threshold value for triggering notifications (if desired).

3. Configure the IFTTT applet:
   - Create an applet with Webhooks as the trigger and the email service as the action.
   - Set the trigger event name to something like `temperature_exceeded`.
   - Set the action to send an email to the desired email address with a suitable message indicating the temperature exceeded the threshold.

## Running the Project

1. Ensure the DHT11 sensor is properly connected to the Raspberry Pi.

2. Open a terminal on the Raspberry Pi.

3. Navigate to the project directory.

4. Run the Python script:

   ```bash
   python temperature_reporting.py
   ```

   The script will start reading temperature values from the DHT11 sensor and sending them to Adafruit IO. If the temperature exceeds the threshold, it will print a message, trigger the configured IFTTT applet, and send an email notification to the provided email address.
 
## Customization

- You can modify the threshold value (`threshold`) in the `temperature_reporting.py` file according to your needs.
- You can customize the IFTTT applet to trigger different actions, such as sending notifications to other services or devices.

## Contributing

Contributions are welcome! Please open an issue or submit a pull request for any enhancements or bug fixes.

## License

This project is licensed under the [MIT License](LICENSE).
```

Make sure to provide the necessary details and instructions for setting up and configuring the IFTTT applet to send email notifications.
