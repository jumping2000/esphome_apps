![GitHub release (latest by date)](https://img.shields.io/github/v/release/jumping2000/esphome_apps?style=for-the-badge) ![GitHub Release Date](https://img.shields.io/github/release-date/jumping2000/esphome_apps?style=for-the-badge) ![GitHub Releases](https://img.shields.io/github/downloads/jumping2000/esphome_apps/latest/total?color=purple&label=%20release%20Downloads&style=for-the-badge) ![GitHub All Releases](https://img.shields.io/github/downloads/jumping2000/esphome_apps/total?color=orange&label=Total%20downloads&style=for-the-badge)

# ESPhome Apps for Home Assistant
[![Buy me a coffee](https://cdn.buymeacoffee.com/buttons/bmc-new-btn-logo.svg)](https://www.buymeacoffee.com/jumping)<span style="margin-left:15px;font-size:28px !important;">Buy me a coffee</span></a>

### Please [support our work with a donation](https://paypal.me/hassiohelp) and star this repository! Thanks

ESPhome apps for Home Assistant [jumping2000](https://github.com/jumping2000/esphome_apps/commits?author=jumping2000)<br>
[![GitHub release (latest by date)](https://img.shields.io/github/v/release/jumping2000/esphome_apps)](https://github.com/jumping2000/esphome_apps/releases)
[![GitHub Release Date](https://img.shields.io/github/release-date/jumping2000/esphome_apps)](https://github.com/jumping2000/esphome_apps/releases)
[![ESPhome][img-esphome]][link-esphome]
[![Maintenance](https://img.shields.io/badge/Maintained%3F-Yes-brightgreen.svg)](https://https://github.com/jumping2000/esphome_apps/graphs/commit-activity)
[![GitHub issues](https://img.shields.io/github/issues/jumping2000/esphome_apps)](https://github.com/jumping2000/esphome_apps/issues)

# Esphome apps works with ESPhome addon or ESPhome environment (Docker container or Python environment)

## Installation
- Install ESPhome: follow the istructions here [ESPhome](https://esphome.io), you can use [HA addon](https://github.com/esphome/home-assistant-addon) or [Docker Container](https://hub.docker.com/r/esphome/esphome) or [Python](https://esphome.io/guides/installing_esphome.html)!
- Configure secrets: [ESPhome FAQ](https://esphome.io/guides/faq.html)
- Copy **common** folder in your **ESPhome folder**
- Copy apps yaml file in your **ESPhome folder**
- Personalize the **subsitutions** section in yaml file

## Apps
-  IKEA Vindriktning
-  Plug BLITZWOLF SHP2 with FSM (Finite State Machine) to model washing machine states 
```mermaid
stateDiagram-v2
  direction LR
  [*] --> Idle
  Idle --> Riempimento: POWER_LOW
  Lavaggio --> Risciacquo: POWER_LOW
  Riempimento --> Lavaggio: POWER_HIGH
  Risciacquo --> Lavaggio: POWER_HIGH
  Riempimento --> Lavaggio: POWER_MEDIUM
  Risciacquo --> Centrifuga: POWER_MEDIUM
  Centrifuga --> Svuotare: CLEANING
  Risciacquo --> Svuotare: CLEANING
  Svuotare --> Idle: OPENING
```


```mermaid
stateDiagram-v2
  direction LR
  [*] --> Idle
  Riscaldamento --> Mantenimento: POWER_LOW
  Idle --> Riscaldamento: POWER_HIGH
  Mantenimento --> Riscaldamento: POWER_HIGH
  Riscaldamento --> Raffreddamento: COOLING
  Mantenimento --> Raffreddamento: COOLING
  Raffreddamento --> Idle: COOLING_PLUS
  Mantenimento --> Idle: COOLING_PLUS
```

[img-hassio]:https://img.shields.io/badge/config_for-Hass.io-53c1f1.svg
[img-esphome]:https://img.shields.io/badge/config_for-esphome.io-53c1f1.svg

[link-hassio]:https://home-assistant.io/hassio/
[link-esphome]:https://esphome.io/
