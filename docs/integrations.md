# Integrations

## Enabled Integrations

Your Home Assistant instance has the following integrations configured:

### Core Integrations (via `default_config`)

The `default_config` component provides access to standard Home Assistant integrations including:

- **Homeassistant** - Core Home Assistant configuration and control
- **Frontend** - Web UI with custom themes
- **History** - Historical state storage and graphs
- **Logbook** - Event log visualization
- **System Monitor** - System health and diagnostics
- **System Log** - System event logging
- **Auth** - User authentication and authorization
- **Config** - Configuration management UI
- **Mobile App** - Mobile device integration support

### Text-to-Speech (TTS)

- **Google Translate** - Text-to-speech using Google Translate API

### HTTP Configuration

- **HTTP** - Web server with reverse proxy support
  - Trusted proxies: `172.30.33.0/24` (internal HAOS range), `192.168.1.136/32` (Talos NodeIP)
  - X-Forwarded-For header support enabled

### Connected Devices & Protocols

- **Bluetooth** - Bluetooth device discovery and connectivity
- **Prometheus** - Metrics collection for monitoring
- **Media Source** - Media library aggregation
- **ZHA** - Zigbee Home Automation (via automations with ZHA device triggers)
- **Shelly** - Shelly smart switches and relays (via automations)
- **MQTT** - MQTT message broker integration (referenced in automations)

### Assistant & Voice

- **Google Assistant** - Google Home integration with state reporting
  - Exposed domains: `switch`, `light`, `climate`, `scene`, `script`, `cover`
  - Service account authentication enabled
  - Project ID: `home-assistant-389312`

### Plant Monitoring

- **Plant** - Soil moisture, temperature, and battery monitoring for plants

### Local/Custom Integrations

- **LocalTuya** - Local control of Tuya smart devices
- **ESPHome** - Integration with ESPHome-based custom devices
- **Sonos** - Sonos speaker integration
- **UniFi** - Ubiquiti UniFi network device control
- **Broadlink** - Broadlink IR blaster control
- **Midea AC** - Midea air conditioner control
- **Nest** - Google Nest devices (thermostats, cameras)
- **Android TV Remote** - Android TV remote control
- **Git HA-ppens** - Git integration for Home Assistant (config sync)
- **Afvalbeheer** - Dutch waste collection schedule
- **Buienradar** - Dutch weather integration

### Specialized Features

- **Device Tracker** - Device location tracking
- **Image Upload** - Image handling
- **Templates** - Template sensors and helpers
- **Utility Meter** - Energy consumption metering
- **Tag** - NFC/RFID tag support
- **Event** - Custom events and triggers
- **IPP** - Internet Printing Protocol
- **WebRTC** - WebRTC camera support
- **Go2RTC** - RTSP stream support (noted in project)

### Automations & Scenes

- **Scenes** - Custom scene definitions
- **Automations** - Automation rules (based on automations.yaml)
- **Scripts** - Custom scripts for complex workflows

## Configuration Structure

Configuration is split across multiple files for maintainability:

- `configuration.yaml` - Main config file with integrations and includes
- `configuration/homeassistant.yaml` - Core HA settings, auth, external URL
- `configuration/plant.yaml` - Plant monitoring configuration
- `configuration/sensor.yaml` - REST sensors (Foscam camera)
- `configuration/google_assistant.yaml` - Google Assistant settings
- `automations.yaml` - Automation rules
- `scripts.yaml` - Custom scripts
- `scenes.yaml` - Scene definitions (currently empty)

## Authentication

- **External URL**: `https://ha.bartvanderhel.nl`
- **Auth Providers**: 
  - Trusted Networks (local network IPs)
  - Home Assistant Local (standard login)
- **Service Account**: Google Cloud service account for Google Assistant

