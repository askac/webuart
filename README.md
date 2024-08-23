# WebUART

**WebUART** is a web-based interface designed to communicate with microcontrollers (MCUs) via UART using the Web Serial API. This project allows users to connect to a serial port, send commands, and receive data directly from their web browser.

## Features

- **Connect/Disconnect:** Select a COM port and baud rate to establish or close a connection with an MCU.
- **Command Buttons:** Predefined command buttons for sending frequently used commands.
- **Manual Command Input:** Manually input and send text or hexadecimal commands with an option to append a newline.
- **Debug Log:** A log that displays the sent commands for debugging purposes.

## Installation

1. **Clone the repository:**

   ```bash
   git clone https://github.com/askac/webuart.git
   ```

2. **Navigate to the project directory:**

   ```bash
   cd webuart
   ```

3. **Open the `webuart.html` file in your web browser:**

   Simply double-click the `webuart.html` file to launch the interface in your default web browser.

## Usage

- **Connect to MCU:**
  - Select a baud rate from the dropdown menu.
  - Click the "Connect" button and choose the appropriate COM port.
  - Once connected, you can send predefined or manual commands to the MCU.

- **Send Commands:**
  - Use the provided buttons to send frequently used commands.
  - Input text or hexadecimal values in the manual input field to send custom commands.
  - Optionally, append a newline to your manual commands using the "Newline" checkbox.

- **View Received Data:**
  - The received data from the MCU will be displayed in the terminal area.

- **Debugging:**
  - The debug log will show all sent commands for review and troubleshooting.

## Modifying Buttons

To modify the predefined command buttons, follow these steps:

1. **Locate the Button Configuration Section:**

   In the `webuart.html` file, find the section where the command buttons are configured. It should look like this:

   ```javascript
   const commands = [
       { label: "Text Command 1", type: "text", command: "*FOOR*BAR", newline: true },
       { label: "Hex Command 2", type: "hex", command: "DEADBEAF", newline: false }
   ];
   ```

2. **Add a New Button:**

   To add a new button, simply append a new object to the `commands` array with the desired label, type (`"text"` or `"hex"`), and the command to be sent:

   ```javascript
   const commands = [
       { label: "Text Command 1", type: "text", command: "*FOOR*BAR", newline: true },
       { label: "Hex Command 2", type: "hex", command: "DEADBEAF", newline: false },
       { label: "Hex Command 3", type: "hex", command: "DEADBEAF03", newline: true },
   ];
   ```

3. **Modify an Existing Button:**

   To modify an existing button, change the `label`, `type`, or `command` within the corresponding object:

   ```javascript
   const commands = [
       { label: "New Label", type: "hex", command: "NewHexCommand", newline: true }
   ];
   ```

4. **Save and Refresh:**

   After making changes, save the `webuart.html` file and refresh the web page in your browser to see the updated buttons.

## Contributing

Feel free to fork this project, submit issues, or open pull requests to contribute. Any feedback or suggestions are welcome!

## License

This project is licensed under the MIT License. See the `LICENSE` file for more details.
