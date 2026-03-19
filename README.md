### 📱 ESP32 SPI Interface with 16-Pin Phone TFT Display

Drive a salvaged 16-pin mobile TFT display (ST7789) using an ESP32 over SPI with minimal configuration.

### 🚀 Overview

This project shows how to interface a 160×128 phone TFT display (commonly found in older/mobile modules) with an ESP32 using the SPI-based ST7789 driver.

Unlike typical smartphone panels that rely on complex interfaces (e.g., MIPI), this display exposes an SPI-compatible controller—making it possible to directly drive it using the TFT_eSPI library.

### ✨ Features

✅ Works with ESP32 + TFT_eSPI

✅ Simple SPI wiring (no external controller needed)

✅ Minimal configuration

✅ Compatible with standard ST7789 graphics pipelines

✅ Lightweight and fast rendering

### 🧠 Key Insight

Not all “phone displays” are MIPI.

Some 16-pin TFT panels internally use controllers like ST7789, which can be driven over SPI—this project demonstrates exactly how to identify and use them.

### 📐 Display Specs

Resolution: 160 × 128 (H × W)

Driver: ST7789

Color Order: RGB

Interface: SPI

### 🔧 Hardware Setup

🧩 Components

ESP32 (tested with standard dev boards)

16-pin TFT phone display (ST7789-based)

Jumper wires

(Optional) Reset connection

🔌 Pin Configuration
c++'''
#define TFT_MISO 19
#define TFT_MOSI 23
#define TFT_SCLK 18

#define TFT_CS   5   // Chip select
#define TFT_DC   17  // Data/Command
#define TFT_RST  4   // Optional (can be left unconnected)
'''
### ⚙️ Software Setup

1. Install Library

Use the TFT_eSPI library.

2. Configure User_Setup.h

Set the following:
c++'''
#define ST7789_DRIVER
#define TFT_WIDTH  128
#define TFT_HEIGHT 160
#define TFT_RGB_ORDER TFT_RGB
'''
Then apply the pin configuration above.

### ▶️ Usage

After configuration, you can use any standard TFT_eSPI example:

Graphics test

Text rendering

UI frameworks like LVGL (optional)

Upload and your display should initialize and render immediately.

### ⚠️ Notes

TFT_RST is optional — connect only if your display requires manual reset.

Ensure correct driver (ST7789) — this may vary depending on your panel.

Double-check pin alignment on the 16-pin connector (varies by manufacturer).

🔥 Why This Project Matters

♻️ Reuse old phone displays instead of discarding them

💸 Build low-cost embedded UIs

🧪 Explore unconventional hardware hacks with ESP32

📌 Future Improvements

Touch support (if available)

LVGL UI examples

Auto-detection of display configs

Power optimization

### 📄 License

MIT License

### ⭐ Support

If this helped you, consider giving the repo a star.