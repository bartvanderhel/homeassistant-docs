# Automations

Your Home Assistant instance includes several automations that control lights, blinds, and create complex workflows. Below is a summary of key automations:

## Morning/Evening Routines

### Amber Raket - Morning Activation (06:55)

- **ID**: `1710526912749`
- **Trigger**: Time trigger at 06:55
- **Action**: Turns ON the Amber Raket switch
- **Purpose**: Morning wake-up routine for Amber's room

### Amber Raket - Morning Deactivation (08:15)

- **ID**: `1710526950121`
- **Trigger**: Time trigger at 08:15
- **Action**: Turns OFF the Amber Raket switch
- **Purpose**: End of morning routine

## Living Room Control

### Toggle Living Room Lights

- **ID**: `1710527522663`
- **Trigger**: Huiskamer Schakelaar (Living Room Switch) turned ON
- **Action**: Executes `script.lampen_normaal` (Normal Lights script)
- **Purpose**: Turns on living room lights to preset brightness levels

### Living Room Lights Off

- **ID**: `1710527672511`
- **Trigger**: Huiskamer Schakelaar (Living Room Switch) turned OFF
- **Action**: 
  1. Executes `script.huiskamer_lampen_uit` (Living Room Lights Off)
  2. Turns off two additional garden lights
- **Purpose**: All-off scene for living room and garden

## Device-Based Automations

### Shelly Button - Light Toggle

- **ID**: `1710531289437`
- **Trigger**: Shelly button single press
- **Action**: Toggles two lights (multiple devices)
- **Purpose**: Wireless remote control of specific lights

### Sun Shield / Awning Control

- **ID**: `1710580485958`
- **Trigger**: Manual (not automated, but available for triggering)
- **Action**: Opens zonnescherm (sun shield/awning)
- **Purpose**: Motorized outdoor shade control

## Laundry Automations

These automations are defined in `automations.yaml` and are currently active.

### AEG Wasmachine Gestart

- **ID**: `1711189485029`
- **Trigger**: Power sensor rises above `500W` for `5s`
- **Condition**: `input_boolean.aeg_washing_machine_running` is `off`
- **Action**: Turns `input_boolean.aeg_washing_machine_running` to `on`

### AEG Wasmachine Klaar

- **ID**: `1710876866929`
- **Trigger**: Power sensor falls below `1W` for `5m`
- **Condition**: `input_boolean.aeg_washing_machine_running` is `on`
- **Actions**:
  1. Sends `notify.notify` message: "AEG wasmachine klaar!"
  2. Announces on `media_player.nestmini7580` using `tts.google_translate_say`
  3. Turns `input_boolean.aeg_washing_machine_running` back `off`

### Samsung Wasmachine Gestart

- **ID**: `1711190196340`
- **Trigger**: Power sensor rises above `500W` for `5s`
- **Condition**: `input_boolean.samsung_washing_machine_running` is `off`
- **Action**: Turns `input_boolean.samsung_washing_machine_running` to `on`

### Samsung Wasmachine Klaar

- **ID**: `1710876901402`
- **Trigger**: Power sensor falls below `1W` for `5m`
- **Condition**: `input_boolean.samsung_washing_machine_running` is `on`
- **Actions**:
  1. Sends `notify.notify` message: "Samsung wasmachine klaar!"
  2. Announces on `media_player.nestmini7580` using `tts.google_translate_say`
  3. Turns `input_boolean.samsung_washing_machine_running` back `off`

## Automation Framework

### Trigger Types Used

- **Time** - Scheduled execution at specific times
- **Device** - Physical device interactions (buttons, switches)
- **State** - Entity state changes
- **MQTT** - Message-based triggers from MQTT broker
- **Event** - Custom Home Assistant events

### Automation Conditions

Some automations include conditional logic:
- Checking if lights are already on/off
- Device state validation
- Time-based conditions (e.g., only run during certain hours)

### Automation Actions

- Turn devices on/off
- Execute scripts
- Toggle device states
- Call services
- Send notifications (potential)

## Automation Best Practices

- **Device IDs**: Uses unique device identifiers for reliable control
- **Modes**: Single execution mode prevents overlapping runs
- **Entity IDs**: Direct entity references for specific control
- **Area-based Control**: Some automations target entire areas

## Additional Automation Patterns

Based on automations.yaml, the following patterns are available:

- **Motion-based lighting** - Using motion sensors to control lights
- **Binary sensors** - Door/window state automations
- **State monitoring** - Responding to sensor value changes
- **Multi-step sequences** - Complex workflows via scripts
- **Time patterns** - Recurring daily/weekly automations
- **Notification triggers** - Mobile app and other notifications
- **Area-based control** - Bulk device management by location

