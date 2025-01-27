
# Gemini API Query Bot: Wi-Fi Enabled Question Answering System

This project is a simple Arduino-based Wi-Fi-enabled bot that interacts with the [Gemini API](https://generativelanguage.googleapis.com/) to ask questions and receive responses in real time. The bot connects to a Wi-Fi network, accepts user input via the Serial Monitor, sends the query to the Gemini API, and displays the response after filtering unnecessary characters.

## Features

- **Wi-Fi Connectivity**: Connects to your Wi-Fi network using credentials provided in the code.
- **Question Input**: Accepts user questions via the Serial Monitor.
- **Gemini API Integration**: Sends the query to the Gemini API and receives a response.
- **Filtered Output**: Filters special characters and whitespace from the response for better readability.
- **Easy to Use**: Simply enter a question and get an answer printed in the Serial Monitor.

## Requirements

Before running this project, ensure you have the following libraries installed:

- [WiFi](https://github.com/espressif/arduino-esp32/tree/master/libraries/WiFi) (for ESP32 boards)
- [HTTPClient](https://github.com/espressif/arduino-esp32/tree/master/libraries/HTTPClient)
- [ArduinoJson](https://github.com/bblanchon/ArduinoJson)

You can install these libraries using the Arduino Library Manager or by downloading them from the respective GitHub repositories.

## Hardware Required

- **ESP32 or compatible board** with Wi-Fi capabilities
- **USB cable** for connecting the board to your computer

## How to Use

1. **Clone this repository** to your local machine:

   ```bash
   git clone https://github.com/yourusername/gemini-query-bot.git
   ```

2. **Open the code in Arduino IDE**:
   - Open the `gemini-query-bot.ino` file in the Arduino IDE.
   
3. **Configure the Wi-Fi Credentials**:
   - Replace the placeholder values for `ssid` and `password` with your Wi-Fi credentials in the code:

   ```cpp
   const char* ssid = "YOUR_SSID";  // Replace with your Wi-Fi SSID
   const char* password = "YOUR_PASSWORD";  // Replace with your Wi-Fi password
   ```

4. **Set up Gemini API Token**:
   - Replace `"YOUR_API_KEY"` with your actual Gemini API token. You can get it from the [Gemini API platform](https://generativelanguage.googleapis.com/).

   ```cpp
   const char* Gemini_Token = "YOUR_API_KEY";  // Replace with your Gemini API token
   ```

5. **Upload the code** to your ESP32 board:
   - Make sure the correct board and port are selected in the Arduino IDE.
   - Click **Upload** to flash the code to your board.

6. **Open the Serial Monitor**:
   - Set the baud rate to `115200` in the Serial Monitor.
   - Once the device connects to Wi-Fi, type a question and press Enter. The bot will send the question to the Gemini API and display the response.

## Code Explanation

- **Wi-Fi Setup**: The `setup()` function connects the ESP32 to the specified Wi-Fi network and prints the local IP address.
- **User Input**: In the `loop()`, the code waits for user input (a question). The input is processed and sent to the Gemini API in the required format.
- **API Request**: The HTTP request is sent using the `HTTPClient` library. The response is parsed with the `ArduinoJson` library.
- **Filtering**: Special characters and whitespaces are removed from the response before displaying it.
- **Displaying the Answer**: The final cleaned-up answer is printed to the Serial Monitor.

## Example Usage

### Input:
```
Ask your Question:
What is the capital of France?
```

### Output:
```
Here is your Answer:
The capital of France is Paris.
```

## Troubleshooting

- **Wi-Fi Connection Issues**: Double-check your Wi-Fi credentials. Ensure the ESP32 is within range of the Wi-Fi router.
- **API Token Issues**: If you're getting an error response from the API, ensure the API token is valid and correctly entered.

## License

This project is licensed under the MIT License.

## Acknowledgements

- [Gemini API](https://generativelanguage.googleapis.com/) for providing the AI-powered responses.
- [ESP32](https://www.espressif.com/en/products/socs/esp32) for the Wi-Fi-enabled hardware platform.
- [Arduino IDE](https://www.arduino.cc/en/software) for easy development and uploading of code to microcontrollers.

