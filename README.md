# LG F2WV5S8S0E Combo Card

## Installation (Need this: [SmartThinQ LGE Sensors](https://github.com/ollo69/ha-smartthinq-sensors))

### Manual
- Copy the content of the custom components folder into your HA config folder see below.<br>
<config directory>
  /config/www

### configuration(yaml)
Configure the time display sensor platform.<br>
```yaml
  - platform: template
    sensors:
      rozika_time_display:
        unique_id: "rozika_hh:mmtime_display"
        friendly_name: "Rozika HH:MM Time Display"
        value_template: "{% if is_state('sensor.rozika_run_state', '-') %}
                           - --
                         {% else %}
                         {{ states('sensor.rozika_remaining_time')[:-3]}}
                         {% endif %}"
  - platform: template
    sensors:
      rozika_pre_wash:
        unique_id: "rozika_pre_wash"
        friendly_name: "Rozika Pre wash"
        value_template: "{{ state_attr('sensor.rozika', 'pre_wash') }}"
  ```
