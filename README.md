# 1. Modbus Experimental SERVER:

This project is an experimental implementation of a Modbus TCP server designed for industrial control cybersecurity testing. The server is configured to simulate a Modbus device with specific identity details and includes functionality for automatic termination of any existing Modbus server instances running on the designated port.

## 1.1. Features

- **Modbus TCP Server**: Implements a Modbus TCP server using `pymodbus`.
- **Automatic Server Termination**: Checks for and terminates any existing server instances running on the specified port.
- **Device Identity Setup**: Configures the Modbus server with customizable identity details.
- **Signal Handling**: Gracefully shuts down the server upon receiving termination signals (SIGINT, SIGTERM).

## 1.2. Configuration

The server can be configured using the following parameters:
- `SERVER_IP`: IP address of the Modbus server (default: `"192.168.56.112"`).
- `SERVER_PORT`: Port number for the Modbus server (default: `502`). Use a higher port number if running without root privileges (e.g., `1502`).

## 1.3. Installation

To run the Modbus server, ensure that you have the following dependencies installed:
- Python 3.6 or higher
- `asyncio`
- `signal`
- `os`
- `subprocess`
- `pymodbus`

## 1.4. Usage
Kill Existing Server: The script automatically checks for any existing Modbus server instances running on the specified port and terminates them.

Start the Server: Run the script to initialize and start the Modbus TCP server with the configured identity details.

## 1.5. Example

The server's identity details are configured as follows:
- Vendor Name: https://www.cyberseclab.eu
- Product Code: EXP2025
- Vendor URL: https://github.com/Dobrady/Modbus-Threat-Analysis-with-AI.git
- Product Name: Modbus Experimental Server
- Model Name: ICS Modbus Security Testbed
- Version: v1.0.7
- Application Name: Industrial Control Cybersecurity Test

## 1.6. Signal Handling
The server is equipped to handle termination signals (SIGINT, SIGTERM) to ensure graceful shutdown. Upon receiving a termination signal, the server stops running and cleans up resources.

# 2. Modbus Experimental CLIENT_1:
## 2.1. Client_1 Description

The Modbus Experimental Client is designed to connect to the Modbus server and read temperature values
from specific input registers. It continuously polls the server to monitor real-time temperature data.

## 2.2.Features

- Establishes a Modbus TCP connection to the server.
- Reads temperature values from predefined input registers.
- Implements error handling to detect failed read attempts.
- Displays read statistics including successful and failed attempts.
- Supports graceful termination via keyboard interrupt.

## 2.3. Client Code Implementation

The client is implemented using the `pyModbusTCP` library and follows the below workflow:
- Initializes a connection to the Modbus server using the configured IP and port.
- Defines input registers for temperature readings.
- Continuously reads temperature data and prints the values.
- Tracks successful and failed read attempts.
- Implements signal handling to safely terminate the process.

# 3. License
This project is licensed under the MIT License. See the LICENSE file for details.

# 4. Acknowledgments
This project is developed and maintained by www.CyberSecLab.eu

# 6. Contact
For inquiries, please contact us at zoltan.dobrady@cyberseclab.eu.
