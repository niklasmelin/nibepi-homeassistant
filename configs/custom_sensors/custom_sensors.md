# Custom units for sensors

If a sensor is missing the correct unit of measurement this can be fixed in your configuration.yaml file by adding the required information. In the following section multiple examples are available for how this can be achieved for different type of sensors.



```yaml
homeassistant:
  customize:
    sensor.nibe_airflow_ref:
      unit_of_measurement: "m3/h"
    sensor.nibe_eb100_adjusted_bs1_air_flow:
      unit_of_measurement: "m3/h"
    sensor.nibe_eb100_bs1_air_flow:
      unit_of_measurement: "m3/h"
    sensor.nibe_eb100_bs1_air_flow_unfiltered:
      unit_of_measurement: "m3/h"
    sensor.nibe_hp_consumed_energy_due_to_heating:
      state_class: total_increasing
      device_class: energy
    sensor.nibe_hp_consumed_energy_due_to_hot_water:
      state_class: total_increasing
      device_class: energy
    sensor.nibe_hp_consumed_energy_due_to_ventilation:
      state_class: total_increasing
      device_class: energy
    sensor.nibe_degree_minutes_16_bit:
      unit_of_measurement: ""
    sensor.nibe_degree_minutes_32_bit:
      unit_of_measurement: ""
    sensor.nibe_eb100_be1_current:
        device_class: current
    sensor.nibe_eb100_be2_current:
        device_class: current
    sensor.nibe_eb100_be3_current:
        device_class: current
```

Credits to AndersHoglund