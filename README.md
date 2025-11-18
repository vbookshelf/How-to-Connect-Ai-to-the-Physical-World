# How to Add Arduino Tool Calls to Ai Chat

The attached notebook and Arduino code is simple example that shows how to use Pyserial to connect Python code running in a local Jupyter Notebook to an Arduino. This setup gives a user the ability to tell AI chat agents to take actions in the real world e.g. switch on a light. It's also an easy and low-cost way to add GPIO pins to a Mac or PC.

<br>

## How It Works

*   **The Connection:** The Python code in the Jupyter Notebook uses the `pyserial` library to connect to the Arduino through the computer's USB port. This communication happens over a standard protocol called **Serial**.

*   **The Configuration:** For the connection to succeed, two parameters must be configured correctly in the Python script:
    *   **The Port:** The name of the port your Arduino is connected to (e.g., `COM3` on Windows or `/dev/ttyUSB0` on Linux/Mac).
    *   **The Baud Rate:** The speed of communication. This rate **must be identical** in both the Python script and the Arduino sketch (e.g., `9600`).

*   **The Arduino's Role:** The code on the Arduino runs continuously in its `loop()` function. It can be programmed to do one of two things:
    *   **Send Data:** Constantly send information (like sensor readings) over the serial port for Python to read.
    *   **Listen for Data:** Wait for a command to be sent from the Jupyter Notebook, and then take action based on that command (like turning an LED on or off, or sending back a sensor reading).
 
<br>

## Example Use Cases

The included Jupyter Notebook (`example.ipynb`) provides two examples:

*   **1. Simple Digital Control: Turn an LED On and Off**
    *   Send a simple command from the Jupyter Notebook to make the Arduino perform a physical action. This example uses the builtin LED on the Arduino therefore, you don't need to do any wiring.

*   **2. Control Arduino with the Gemini LLM**
    *   Use a Large Language Model (LLM) to interact with the Arduino using natural language. By chatting with Gemini and using function calling, you can type commands like "turn the light on." The model will translate your request into code that controls the Arduino. 

This setup will help you to quickly grasp the fundamentals of connecting AI to the physical world.
