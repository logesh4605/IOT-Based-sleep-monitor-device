# IOT-Based-sleep-monitor-device
IoT-Based Wearable Sleep Monitoring System — An ESP32 device that tracks movement, sound, distance, temperature &amp; humidity to detect sleep disturbances in real time. Triggers buzzer/LED alerts, displays status on LCD, logs data to ThingSpeak, and hosts a live web dashboard
**IoT-Based Wearable Sleep Monitoring System**

An ESP32-based embedded system that monitors sleep quality in real time by tracking body movement, ambient sound, distance/posture, temperature, and humidity — with local display, buzzer/LED alerts, live cloud logging, and a built-in web dashboard.

**Overview**
The system continuously samples multiple sensors to detect abnormal sleep conditions (restlessness, disturbances, unsafe posture distance, excessive noise) and immediately alerts the user via an onboard buzzer and LED. All sensor readings are shown on a 16x2 I2C LCD, pushed to ThingSpeak for remote logging/visualization, and served over a lightweight built-in web server for live monitoring from any device on the network.

**Features**
Real-time monitoring of movement (piezo), sound level, distance (ultrasonic), temperature, and humidity (DHT11)
Automatic anomaly detection with configurable thresholds
Instant local alerts via buzzer and LED
Live status on a 16x2 I2C LCD
Cloud data logging via ThingSpeak (5 data fields)
Onboard Wi-Fi web server with an auto-refreshing live status page
Averaged ultrasonic readings for noise-resistant distance sensing

**Hardware Components**

ComponentPurposeESP32Main microcontroller with Wi-FiDHT11Temperature & humidity sensingHC-SR04 (Ultrasonic)Distance/posture sensingSound sensorAmbient noise detectionPiezo sensorBody movement detection16x2 I2C LCDLocal status displayBuzzer + LEDAlert indicators

**How It Works**

Sensors are sampled every cycle (ultrasonic distance is averaged over 5 readings for accuracy).
Readings are checked against threshold conditions to flag an abnormal state.
Buzzer and LED trigger immediately on any abnormal reading.
Data is displayed on the LCD and pushed to ThingSpeak.
A built-in web server serves a live HTML dashboard showing all readings and current status (NORMAL/ALERT).


Tech Stack

Platform: ESP32 (Arduino framework)
Libraries: WiFi.h, Wire.h, LiquidCrystal_I2C, DHT, ThingSpeak
Cloud: ThingSpeak IoT channel
Interface: Onboard HTTP server (auto-refreshing HTML page)

**Applications**

Designed with real-world, low-cost health monitoring in mind — suitable as a wearable/bedside sleep safety aid for individuals, elderly care, or hostel/dormitory environments where remote sleep-pattern visibility is useful.

Future Improvements

Mobile app integration for push notifications
Battery-powered wearable enclosure
Machine learning-based sleep stage classification
Historical trend analysis dashboard
