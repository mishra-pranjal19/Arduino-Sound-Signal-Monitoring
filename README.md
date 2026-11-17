# Real-Time Sound Monitoring Using a Microphone Amplifier

## Project overview
This Arduino sketch measures sound-signal variation from an analog microphone amplifier. During each 50 ms sample window, it records the highest and lowest analog readings, calculates the peak-to-peak difference, converts that difference to an approximate voltage, and prints the result over Serial.

## Hardware 
- Arduino UNO or compatible board
- Analog microphone amplifier module (MAX4466 or the Adafruit microphone amplifier)
- Breadboard and jumper wires
- USB data cable
- Computer with Arduino IDE

## Typical signal connections
- Microphone module OUT -> Arduino analog input A0
- Microphone module GND -> Arduino GND
- Microphone module VCC -> a supply voltage supported by your exact module


## Upload and run
1. Open `src/real_time_sound_monitoring.ino` in Arduino IDE.
2. Select the correct Arduino board and port.
3. Upload the sketch.
4. Open Serial Monitor or Serial Plotter.
5. Set the baud rate to **9600** to match `Serial.begin(9600)`.
6. Make sound near the microphone and observe the changing peak-to-peak voltage readings.

## How the sketch works
- Reads analog input pin 0 (A0 on Arduino UNO).
- Collects readings for a 50 millisecond window.
- Finds the maximum and minimum readings in that window.
- Calculates `peakToPeak = signalMax - signalMin`.
- Converts the peak-to-peak count to an approximate voltage using a 5.0 V reference assumption.
- Prints one voltage value per sample window.

## Important notes
- The code's voltage conversion assumes a 5.0 V ADC reference. The actual value depends on the board's ADC reference voltage and configuration.
- The output is an approximate peak-to-peak signal voltage, not calibrated sound pressure level in dB.
- This sketch does not perform FFT or frequency-spectrum analysis.
- The code uses `analogRead(0)`, which corresponds to A0 on an Arduino UNO.
- Confirm that the microphone module's supply voltage and pinout are compatible with your board before connecting it.

## Repository folders
- `src/`: Arduino sketch.
- `docs/`: circuit diagram and documentation.
- `hardware_photos/`: add genuine photos of your assembled hardware here.
- `screenshots/`: add genuine Serial Plotter or Serial Monitor screenshots here.

## Evidence to add before submission
After assembling and testing your own circuit, add:
1. A clear photo of the complete hardware setup to `hardware_photos/`.
2. A close-up photo showing the module-to-Arduino wiring to `hardware_photos/`.
3. A screenshot of your actual Serial Plotter/Monitor output to `screenshots/`.



## Student details
Name: Pranjal Mishra  
Course: B.Tech CSE (Data Science and Artificial Intelligence)  
University: Shri Ramswaroop Memorial University, Lucknow  
Academic session: 2026–2027
