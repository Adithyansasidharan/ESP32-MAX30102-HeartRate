# ESP32 Heart Rate Monitor with MAX30102

A simple and efficient IoT project to measure Heart Rate (BPM) using the ESP32 microcontroller and the MAX30102 Pulse Oximeter sensor. The system detects the pulse via infrared light reflection and outputs the real-time Beats Per Minute (BPM) to the Serial Monitor.

## 🚀 Features
* **Real-time Monitoring:** Instant BPM calculation.
* **Smart Detection:** Automatically detects if a finger is present on the sensor.
* **Data Averaging:** Uses a running average algorithm to smooth out sensor noise for stable readings.
* **Low Power:** Configured for optimal LED brightness (`0x1F`) to prevent sensor heating and save power.

## 🛠️ Hardware Requirements
* **Microcontroller:** ESP32 Development Board (e.g., DOIT DevKit V1)
* **Sensor:** MAX30102 Pulse Oximeter & Heart Rate Module
* **Connections:** Jumper wires (Female-to-Male)
* **Cable:** Micro USB cable for programming

## 🔌 Pinout / Wiring
Connect the MAX30102 to the ESP32 as follows (I2C protocol):

| MAX30102 Pin | ESP32 Pin | Note |
| :--- | :--- | :--- |
| **VIN** | **3V3** | ⚠️ Do not connect to 5V |
| **GND** | **GND** | Common Ground |
| **SDA** | **GPIO 21** | I2C Data |
| **SCL** | **GPIO 22** | I2C Clock |

## 💻 Software & Libraries
This project requires the **Arduino IDE** and the following library:

1.  Open Arduino IDE.
2.  Go to **Sketch** -> **Include Library** -> **Manage Libraries**.
3.  Search for **SparkFun MAX3010x**.
4.  Install **"SparkFun MAX3010x Pulse and Proximity Sensor Library"**.

## ⚙️ How to Run
1.  Clone this repository or download the `.ino` file.
2.  Open the file in Arduino IDE.
3.  Select your board: **Tools** > **Board** > **DOIT ESP32 DEVKIT V1**.
4.  Select the correct Port.
5.  Click **Upload**.
6.  Open the **Serial Monitor** and set the baud rate to **115200**.

## 📊 How to Use
1.  Once the system is running, the Serial Monitor will display `Place your index finger on the sensor...`.
2.  Place your index finger **gently** on the sensor window.
3.  **Wait 5-10 seconds** for the algorithm to stabilize.
4.  View the `Avg BPM` value for the most accurate heart rate reading.

### Troubleshooting
* **"MAX30102 was not found"**: Check your wiring. Ensure SDA connects to pin 21 and SCL to pin 22.
* **Erratic Readings**: Ensure you are applying **steady, light pressure**. Pressing too hard cuts off blood flow; pressing too lightly allows ambient light interference.

## 📄 License
This project is open-source. The code relies on the SparkFun MAX3010x library.
