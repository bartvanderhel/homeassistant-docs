# Devices & Areas

## Home Areas

Based on your scripts and automations, the following areas are defined:

- **Huiskamer** (Living Room)
- **Tuin** (Garden/Outdoor)
- **Amber** (Amber's room)
- **Slaapkamer** (Bedroom)
- **Milou** (Milou's room)
- **Badkamer** (Bathroom)
- **Gang Boven** (Upstairs Hallway)

## Device Categories

### Lighting Devices

Your setup includes multiple smart lights controlled via scripts and automations:

- **Living Room Lights** - Controlled by `lampen_normaal` script with adjustable brightness (45%)
- **Bedroom Lights** - Controlled by `lampen_boven_uit` script
- **Garden/Outdoor Lights** - Controlled by `tuin_lampen_uit` script with conditional logic
- **Amber's Lights** - Part of the upper floor lighting group
- **Milou's Lights** - Part of the upper floor lighting group
- **Various Brightness Scenes** - Preset brightness levels (20%, 40%, 45%, 50%, 90%)

### Switches

- **Amber Raket Switch** - Smart switch with scheduled on/off
  - Turns ON at 06:55 (Amber raket aan)
  - Turns OFF at 08:15 (Amber raket uit)
- **Huiskamer Schakelaar** (Living Room Switch) - Wall-mounted control
  - Triggers lighting scenes when toggled on/off
- **Shelly Button** - Wireless button device
  - Toggles lights in living room and bedroom areas

### Covers (Blinds/Shutters)

- **Zonnescherm** (Sun Shield/Awning) - Motorized shade
  - Open/close automation available
  - Integrated with cover domain controls

### Sensors

#### Foscam IP Camera

**REST-based sensors from IP camera at `192.168.1.34:88`**:

- **Foscam Motion Sensor** - Motion detection alarm
  - States: Disabled, None, Detected, Not Determined
  - Scan interval: 3 seconds

- **Foscam Sound Sensor** - Audio detection alarm
  - States: Disabled, None, Detected, Not Determined
  - Scan interval: 3 seconds

### Appliances (Wasmachines)

Your laundry setup has two monitored washing machines with power-based start/finish detection:

- **AEG Wasmachine**
  - Start detection: power above `500W` for `5s`
  - Finish detection: power below `1W` for `5m`
  - Running state helper: `input_boolean.aeg_washing_machine_running`
  - Notification + TTS when cycle is complete

- **Samsung Wasmachine**
  - Start detection: power above `500W` for `5s`
  - Finish detection: power below `1W` for `5m`
  - Running state helper: `input_boolean.samsung_washing_machine_running`
  - Notification + TTS when cycle is complete

### Plant Monitoring Sensors

#### Croton

- Moisture sensor (humidity)
- Battery indicator
- Temperature sensor
- Thresholds:
  - Moisture: 15-60%
  - Battery: Minimum 5%
  - Temperature: 5-32°C

#### Dieffenbachia

- Moisture sensor (soil moisture)
- Battery indicator
- Temperature sensor
- Thresholds:
  - Moisture: 15-60%
  - Battery: Minimum 5%
  - Temperature: 12-32°C

## Device Control Methods

### Automation Triggers

- **Time-based** - Scheduled on/off (e.g., Amber raket at 06:55)
- **Device triggers** - Physical button presses (Shelly button, wall switches)
- **State-based** - Conditional logic based on light/switch status
- **Manual** - Direct control via Home Assistant UI

### Control Protocols

- **ZHA** - Zigbee Home Automation (for compatible devices)
- **Shelly** - Direct WiFi control for Shelly devices
- **MQTT** - MQTT-based devices and messaging
- **REST API** - Foscam camera and custom devices
- **Cloud APIs** - Google Assistant, Nest devices, Tuya

## Device Management

### Entity Registry

Devices are assigned unique entity IDs for automation and scripting. Device references include:
- Device UUID for reliable identification
- Entity IDs for state tracking
- Domain classification (light, switch, cover, etc.)

### Areas

Areas help organize devices by physical location:
- Each light/switch/cover is assigned to one or more areas
- Area-based automation possible (e.g., turn off all lights in Huiskamer)
- Used in scripts for bulk control (e.g., `huiskamer_lampen_uit`)

