# Configuration

Overview of the repository configuration for Home Assistant.

Structure:

- `configuration.yaml` — the primary configuration file. Large blocks have been split into `configuration/` includes for readability.
- `configuration/` — contains extracted files such as `homeassistant.yaml`, `plant.yaml`, `sensor.yaml`, and `google_assistant.yaml`.

Notes:

- When editing configuration files, validate YAML syntax and, where possible, test changes in a safe branch before applying to the running instance.
- Sensitive files (service account JSON, credentials) are referenced using `!include` and should not be committed in plaintext.
