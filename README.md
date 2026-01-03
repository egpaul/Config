# Home Assistant Configuration

This repository contains the Home Assistant configuration files.

## Structure

| File | Description |
|------|-------------|
| `configuration.yaml` | Main configuration file |
| `automations.yaml` | Automation rules |
| `scripts.yaml` | Script definitions |
| `scenes.yaml` | Scene configurations |
| `snmp-sensors.yaml` | SNMP sensor definitions |
| `themes/` | Custom frontend themes |

## Features

### Network Device Tracking

Uses SNMP to track devices on the network:
- Platform: SNMP v1/2c
- Monitors network interface statistics via OID `1.3.6.1.2.1.31.1.1.1.6.4`

### Frontend Themes

Custom themes are loaded from the `themes/` directory using `!include_dir_merge_named`.

### Packages

Modular configuration using Home Assistant packages for better organization.

## Setup

1. Clone this repository to your Home Assistant config directory
2. Customize the SNMP settings in `configuration.yaml` for your network
3. Add your automations, scripts, and scenes to the respective files
4. Restart Home Assistant to apply changes

## Requirements

- Home Assistant
- SNMP-enabled network device (router/switch) for device tracking
