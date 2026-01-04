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

### Energy Export Income Tracking

Track and visualize income from selling solar energy back to the grid:

**Configuration:**
1. Update `sensor.grid_export_energy` in `sensors/energy_income.yaml` and `utility_meters.yaml` to match your actual grid export sensor
2. Set your utility's buy-back rate via the `input_number.energy_export_rate` entity (default: $0.08/kWh)

**Sensors included:**
- `sensor.energy_export_income_total` - All-time income from energy export
- `sensor.energy_export_income_today` - Today's income
- `sensor.energy_export_income_monthly` - This month's income

**Dashboard cards:**
See `lovelace/energy_income_card.yaml` for multiple card options:
- Statistics Graph Card (built-in)
- History Graph Card (built-in)
- ApexCharts Card (requires HACS)
- Complete dashboard view with summary cards

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
