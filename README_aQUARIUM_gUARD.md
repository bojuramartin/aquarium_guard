
# aQUARIUM gUARD
## Smart Water Monitoring & Resource Management

**Project status:** Initial design / planning  
**Target platform:** Nordic nRF54LM20 DK  
**Contest:** Hackster.io — Sustain the System

aQUARIUM gUARD is a planned modular water-monitoring and automation system. It aims to combine water-quality measurements, pump monitoring, and controlled dosing to help reduce water, fertilizer, and water-treatment waste.

The project is currently at the planning stage. Features described here are goals for the prototype, not claims that a working system has already been completed.

## Problem

Small water systems often rely on manual measurements, fixed timers, and simple threshold alarms. This can lead to unnecessary water changes, overdosing, and pump problems that go unnoticed.

aQUARIUM gUARD will explore how sensor data and local processing can support more responsive water management and earlier fault detection.

## Planned Features

- Monitor water temperature and electrical conductivity (EC).
- Add pH, water level, and flow-rate sensing for the first prototype.
- Investigate optical color/light measurements and other application-specific sensors.
- Monitor pump operation using water level, flow, and—where practical—current or vibration measurements.
- Control external circulation/drainage pumps and dosing pumps through suitable driver circuits.
- Provide Bluetooth Low Energy (BLE) telemetry, status, and alerts.
- Start with configurable rules and thresholds, then evaluate lightweight edge-AI/anomaly detection as data becomes available.
- Keep the design modular so sensors and actuators can be adapted to different applications.

## Intended Applications

The platform is intended to be adaptable to aquariums, hydroponics, aquaponics, greenhouse irrigation, water storage, and small-scale water treatment. The exact sensor set will depend on the application.

## How It Is Intended to Work

1. Sensors collect measurements about the water and equipment.
2. The controller validates and processes readings locally.
3. Rules identify conditions requiring attention—for example, low water level, insufficient flow, or unexpected EC changes.
4. Status and alerts are made available over Bluetooth LE.
5. If enabled, external driver hardware operates pumps or dosing equipment within configured limits and safety interlocks.
6. Data from normal and abnormal operation can be used to evaluate anomaly-detection methods for local processing.

**Safety note:** The development board will not directly drive pumps or other high-power loads. External loads require appropriately rated driver hardware, suitable power supplies, and safeguards. Chemical dosing must use application-specific limits and fail-safe controls.

## Planned Hardware / Initial Bill of Materials

| Component | Purpose | Status |
|---|---|---|
| Nordic nRF54LM20 DK | Main controller, BLE, local processing and edge-AI experimentation | Requested development board |
| Waterproof temperature sensor | Water temperature | Planned |
| EC sensor and interface | Electrical conductivity trends | Planned |
| pH sensor and interface | Water acidity | Planned |
| Water-level sensor | Level monitoring and dry-run protection | Planned |
| Flow sensor | Circulation and pump-performance monitoring | Planned |
| Optical color/light sensor | Optical measurements, subject to validation | Planned |
| Pump driver or relay module | Switching external pumps/actuators | Planned |
| Peristaltic dosing pump(s) | Controlled additive dosing | Planned |
| Low-voltage power supply | Power for controller and electronics | Planned |
| Tubing, connectors and enclosure | Prototype assembly | Planned |

The final sensor interfaces, voltage levels, and components will be selected after the application and prototype requirements are confirmed. Sensors for dissolved CO2 or nitrogen compounds may be investigated later; they are not part of the minimum viable prototype.

## Development Roadmap

### Phase 1 — Core Monitoring

- Bring up the nRF54LM20 DK development environment.
- Read temperature, water level, and EC sensors.
- Validate measurements and configurable thresholds.

### Phase 2 — Bluetooth LE

- Send measurements and device status over BLE.
- Add basic configuration and fault notifications.

### Phase 3 — Pump Monitoring and Safe Control

- Integrate a flow sensor and external pump-driver hardware.
- Demonstrate detection of low-level or low-flow conditions.
- Add interlocks and safe failure behavior before enabling automated actuation.

### Phase 4 — Anomaly Detection

- Record representative sensor and pump data.
- Establish a rule-based baseline.
- Evaluate whether a lightweight local anomaly-detection model adds value on the target platform.

### Phase 5 — Documentation and Validation

- Document wiring, firmware setup, calibration, test procedures, limitations, and results.
- Report measured results and sustainability benefits without overstating untested capabilities.

## Sustainability Goals

The project aims to:

- Reduce unnecessary water exchange and water loss.
- Improve dosing accuracy and avoid avoidable use of fertilizers or treatment products.
- Detect pump and flow problems earlier.
- Support maintenance before a small fault becomes equipment damage.
- Use a modular, repairable design that can be adapted instead of replaced.

These are intended outcomes; savings will need to be measured during testing.

## Current Status

This repository documents the initial concept, planned architecture, preliminary bill of materials, and development roadmap. A working prototype and validated performance results are not yet claimed.

## Next Steps

1. Confirm the first target application and sensor requirements.
2. Select compatible sensor interfaces and driver hardware.
3. Implement and test the first monitoring and BLE features.
4. Publish wiring diagrams, firmware, test results, and updates as the project progresses.
