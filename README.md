# ---------------------------------------------------
#          Arduino Fingerprint Enrollment
# ---------------------------------------------------

# Simple Arduino sketch to enroll and store new 
# fingerprints using the Adafruit Optical Fingerprint 
# Sensor.

# ---------------------------------------------------
#                 Description
# ---------------------------------------------------

# This program initializes an Adafruit Fingerprint
# sensor and waits for user input via the Serial
# Monitor. The user is prompted to enter a numeric
# ID (from 1 to 127) for the new fingerprint.

# The sketch then guides the user through the 
# enrollment process:
# 1. Take a first image of the finger.
# 2. Convert the image to a template.
# 3. Wait for the user to remove their finger.
# 4. Prompt the user to place the same finger again.
# 5. Take a second image.
# 6. Convert the second image to a template.
# 7. Create a model from the two templates.
# 8. Store the model in the sensor's flash memory
#    at the specified ID.

# All steps and errors are reported to the Serial
# Monitor.

# ---------------------------------------------------
#             Hardware Requirements
# ---------------------------------------------------

# > Arduino (UNO, Leonardo, Mega, etc.)
# > Adafruit Optical Fingerprint Sensor (or compatible)
# > Jumper wires

# --- Sensor Wiring (for UNO/Nano - SoftwareSerial) ---
# * Sensor GREEN wire -> Arduino Pin 2 (RX)
# * Sensor WHITE wire -> Arduino Pin 3 (TX)
# * Sensor RED wire   -> Arduino 5V
# * Sensor BLACK wire -> Arduino GND

# --- Sensor Wiring (for Leonardo/Mega - HardwareSerial) ---
# * Sensor GREEN wire -> Arduino Pin TX1 (Serial1)
# * Sensor WHITE wire -> Arduino Pin RX1 (Serial1)
# * Sensor RED wire   -> Arduino 5V
# * Sensor BLACK wire -> Arduino GND

# ---------------------------------------------------
#             Software Requirements
# ---------------------------------------------------

# > Arduino IDE (https://www.arduino.cc/en/software)
# > Adafruit Fingerprint Sensor Library
#   (Install via Arduino IDE Library Manager: 
#    Sketch > Include Library > Manage Libraries... > 
#    Search for "Adafruit Fingerprint Sensor Library")

# ---------------------------------------------------
#                  How to Use
# ---------------------------------------------------

# 1. Clone or download this repository.
# 2. Open the .ino file in your Arduino IDE.
# 3. Ensure you have the correct board and port 
#    selected.
# 4. Verify the wiring matches the setup in the code
#    (SoftwareSerial on pins 2/3 is the default
#    for UNO).
# 5. Upload the sketch to your Arduino.
# 6. Open the Serial Monitor (Tools > Serial Monitor).
# 7. Set the baud rate to 9600.
# 8. Follow the on-screen prompts to enroll a new
#    fingerprint.

# ---------------------------------------------------
#          Example Serial Monitor Output
# ---------------------------------------------------
#
# $ Adafruit Fingerprint sensor enrollment
#
# $ Found fingerprint sensor!
# $ Reading sensor parameters
# $ Status: 0x0
# $ Sys ID: 0x0
# $ Capacity: 127
# $ Security level: 3
# $ Device address: 0xFFFFFFFF
# $ Packet len: 128
# $ Baud rate: 57600
#
# $ Ready to enroll a fingerprint!
# $ Please type in the ID # (from 1 to 127) 
#   you want to save this finger as...
#
# > 5  (User types '5' and hits enter)
#
# $ Enrolling ID #5
# $ Waiting for valid finger to enroll as #5
# $ .................Image taken
# $ Image converted
# $ Remove finger
# $ ID 5
# $ Place same finger again
# $ .................Image taken
# $ Image converted
# $ Creating model for #5
# $ Prints matched!
# $ ID 5
# $ Stored!
#
# $ Ready to enroll a fingerprint!
# ...
#
