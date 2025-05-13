ESP32_FreeRTOS with Azure_iot_middleware_freeRTOS - This project explains how to integrate azure_iot_middleware freertos project
into existing freeRTOS project. 

Detailed overview of middleware sdk is given in https://github.com/Azure/azure-iot-middleware-freertos
Device registration - How to register ESP32 WROOM 32 Devkit module with Azure? 
                      https://learn.microsoft.com/en-us/azure/iot-hub/create-connect-device?tabs=portal

This explains how the middleware is integrated as ESP-Component in my project:                      

🚀 ESP-IDF: Built-in vs Custom Components 🔧
Working with ESP32? Here’s a quick breakdown you should know:

🔷 Built-in Components (Provided by ESP-IDF):
 Core libraries maintained by Espressif, available out of the box {freertos, esp_wifi, nvs_flash, esp_event}

🟢 Custom Components (User/3rd-party):
 These include:
 • Logic you write (e.g., sensor drivers, app logic)
 • 3rd-party libraries (e.g., Azure IoT SDK, MQTT, OTA)
Organize them under the components/ directory to keep your project modular and scalable.

💡 Why Custom Components Matter:
 ✅ Keeps your main/ directory clean
 ✅ Enables code reuse across projects
 ✅ Supports easier testing and CI
 ✅ Simplifies integration and maintenance

🧩 How Azure Middleware Helps
 Here’s the architecture I followed 👇

Instead of manually integrating CoreMQTT, TLS, and TCP/IP, Azure provides a ready-to-use middleware layer that handles:
 • MQTT abstraction
 • Secure TLS communication
 • Azure SDK integration for IoT features like Device Twins, Telemetry, Plug and Play, and Provisioning
✅ This modular approach reduces porting effort—letting you focus only on your platform’s drivers while reusing a well-layered stack.