Here's the completed version with better clarity and structure:

---

### Current issue
- The WiFi router provided by ISP ACT is locked, and it's not possible to change the firmware through the GUI management page.
- To install OpenWRT, physical access to the router is required.
- Open up the router casing carefully and locate a group of 4 unlabelled circular pads or pin headers — these are likely UART.
- Use a multimeter to identify the UART pins (GND, TX, RX, VCC).

### Steps to Identify Pins Using a Multimeter
1. **Set multimeter to continuity mode** (marked with a diode/beep symbol).
2. **Identify GND:**
   - Power on the router.
   - Place the black probe on a known ground point (e.g., metal shielding or an Ethernet port casing).
   - Tap the red probe on each of the 4 pins.
   - The pin that causes the multimeter to **beep** is **GND**.
3. **Identify TX:**
   - Set the multimeter to voltage mode.
   - With the router still powered, place the black probe on the GND pin.
   - Tap the red probe on the remaining pins.
   - The one that shows **fluctuating voltage** (e.g., bouncing between 0V–3.3V when the device is booting) is likely **TX** (transmitting data from the router).
4. **Identify RX:**
   - Still with the black probe on GND, check the remaining pins.
   - The **RX** pin usually stays at a steady **low voltage (~0V)**.
   - (Note: You won't see much fluctuation here unless you're sending data to the router.)

---

You can solder header pins onto the board or use jumper cables and attach them using a clip.

Use a UART to USB adapter to connect to your laptop.
(Insert picture here)