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


### Card

```yaml
type: vertical-stack
cards:
  - type: picture-elements
    image: /local/lg_combo.png
    elements:
      - type: image
        entity: sensor.rozika_current_course
        image: /local/lg-icons/ai_grey.png
        state_image:
          Cotton: /local/lg-icons/ai_white.png
          Mixed Fabric: /local/lg-icons/ai_white.png
          Easy Care: /local/lg-icons/ai_white.png
        style:
          top: 12%
          left: 7%
          width: 6%
          image-rendering: auto
      - type: image
        entity: sensor.rozika_run_state
        image: /local/lg-icons/ai_blank.png
        state_image:
          Detecting: /local/lg-icons/ai.detecting.gif
        style:
          top: 12%
          left: 7%
          width: 6%
          image-rendering: auto
        tap_action:
          action: none
      - type: image
        entity: sensor.rozika_run_state
        image: /local/lg-icons/washing.png
        state_image:
          Washing: /local/lg-icons/washing.on.gif
          Rinsing: /local/lg-icons/washing.on.gif
          Detecting: /local/lg-icons/washing.on.gif
        style:
          top: 15.9%
          left: 17%
          width: 11.4%
          image-rendering: auto
        tap_action:
          action: none
      - type: image
        entity: sensor.rozika_run_state
        image: /local/lg-icons/spining.png
        state_image:
          Washing: /local/lg-icons/spining-on.png
          Rinsing: /local/lg-icons/spining-on.png
          Spinning: /local/lg-icons/spining.on.gif
        style:
          top: 15.9%
          left: 28%
          width: 11.4%
          image-rendering: auto
        tap_action:
          action: none
      - type: image
        entity: sensor.rozika_run_state
        image: /local/lg-icons/drying.png
        state_image:
          Drying: /local/lg-icons/drying-on.png
        style:
          top: 15.9%
          left: 38.5%
          width: 11.4%
          image-rendering: auto
        tap_action:
          action: none
      - type: image
        entity: sensor.rozika_run_state
        image: /local/lg-icons/sound.png
        state_image:
          Drying: /local/lg-icons/sound-on.png
        style:
          top: 54%
          left: 7%
          width: 15%
          image-rendering: auto
        tap_action:
          action: none
      - type: image
        entity: binary_sensor.rozika_child_lock
        image: /local/lg-icons/child-lock.png
        state_image:
          'on': /local/lg-icons/child-lock-on.png
        style:
          top: 55%
          left: 14%
          width: 6%
          image-rendering: auto
        tap_action:
          action: none
      - type: image
        entity: sensor.rozika
        image: /local/lg-icons/wifi.png
        state_image:
          'on': /local/lg-icons/wifi-on.png
        style:
          top: 55%
          left: 21.5%
          width: 6%
          image-rendering: auto
        tap_action:
          action: none
      - type: image
        entity: binary_sensor.rozika_remote_start
        image: /local/lg-icons/remote-start.png
        state_image:
          'on': /local/lg-icons/remote-start-on.png
        style:
          top: 55%
          left: 30%
          width: 7%
          image-rendering: auto
        tap_action:
          action: none
      - type: image
        entity: binary_sensor.rozika_door_lock
        image: /local/lg-icons/lock.png
        state_image:
          'on': /local/lg-icons/lock-on.png
        style:
          top: 55%
          left: 38.5%
          width: 5%
          image-rendering: auto
        tap_action:
          action: none
      - type: image
        entity: sensor.rozika_pre_wash
        image: /local/lg-icons/prewash.png
        state_image:
          'on': /local/lg-icons/prewash-on.png
        style:
          top: 67.5%
          left: 7%
          width: 6%
          image-rendering: auto
        tap_action:
          action: none
      - type: image
        entity: sensor.rozika_dry_level
        image: /local/lg-icons/drying.png
        state_image:
          Time Dry: /local/lg-icons/drying-on.png
        style:
          top: 71.5%
          left: 14%
          width: 10%
          image-rendering: auto
        tap_action:
          action: none
      - type: image
        entity: sensor.rozika_dry_level
        image: /local/lg-icons/iron_dry.png
        state_image:
          Iron Dry: /local/lg-icons/iron-on.png
        style:
          top: 67.5%
          left: 21.5%
          width: 7%
          image-rendering: auto
        tap_action:
          action: none
      - type: image
        entity: sensor.rozika_dry_level
        image: /local/lg-icons/dry_low.png
        state_image:
          Low: /local/lg-icons/dry_low-on.png
        style:
          top: 71%
          left: 29.4%
          width: 10%
          image-rendering: auto
        tap_action:
          action: none
      - type: image
        entity: sensor.rozika_dry_level
        image: /local/lg-icons/dry_e.png
        state_image:
          Energy: /local/lg-icons/dry_e-on.png
        style:
          top: 71%
          left: 38.2%
          width: 10%
          image-rendering: auto
        tap_action:
          action: none
      - type: image
        entity: sensor.rozika_pre_wash
        image: /local/lg-icons/butt_off.png
        state_image:
          'on': /local/lg-icons/button_on.png
        style:
          top: 85.7%
          left: 3.2%
          width: 0.7%
          image-rendering: auto
        tap_action:
          action: none
      - type: image
        entity: sensor.rozika_rinse_mode
        image: /local/lg-icons/butt_off.png
        state_image:
          Rinse+: /local/lg-icons/button_on.png
        style:
          top: 85.7%
          left: 22.6%
          width: 0.7%
          image-rendering: auto
        tap_action:
          action: none
      - type: image
        entity: sensor.rozika_dry_level
        image: /local/lg-icons/butt_off.png
        state_image:
          Time Dry: /local/lg-icons/button_on.png
          Low: /local/lg-icons/button_on.png
          Iron Dry: /local/lg-icons/button_on.png
        style:
          top: 85.7%
          left: 42.6%
          width: 0.7%
          image-rendering: auto
        tap_action:
          action: none
      - type: image
        entity: sensor.rozika_countdown_time
        image: /local/lg-icons/butt_off.png
        state_image:
          '0:03:00': /local/lg-icons/button_on.png
          '0:04:00': /local/lg-icons/button_on.png
          '0:05:00': /local/lg-icons/button_on.png
          '0:06:00': /local/lg-icons/button_on.png
          '0:07:00': /local/lg-icons/button_on.png
          '0:08:00': /local/lg-icons/button_on.png
          '0:09:00': /local/lg-icons/button_on.png
          '0:10:00': /local/lg-icons/button_on.png
          '0:11:00': /local/lg-icons/button_on.png
          '0:12:00': /local/lg-icons/button_on.png
          '0:13:00': /local/lg-icons/button_on.png
          '0:14:00': /local/lg-icons/button_on.png
          '0:15:00': /local/lg-icons/button_on.png
          '0:16:00': /local/lg-icons/button_on.png
          '0:17:00': /local/lg-icons/button_on.png
          '0:18:00': /local/lg-icons/button_on.png
          '0:19:00': /local/lg-icons/button_on.png
        style:
          top: 85.7%
          left: 61.8%
          width: 0.7%
          image-rendering: auto
        tap_action:
          action: none
      - type: image
        entity: binary_sensor.rozika_remote_start
        image: /local/lg-icons/butt_off.png
        state_image:
          'on': /local/lg-icons/button_on.png
        style:
          top: 85.7%
          left: 81.2%
          width: 0.7%
          image-rendering: auto
        tap_action:
          action: none
      - type: image
        entity: sensor.rozika_water_temp
        image: /local/lg-icons/temp_cold.png
        state_image:
          Cold: /local/lg-icons/temp_cold-on.png
        style:
          top: 16%
          left: 55%
          width: 13%
          image-rendering: auto
        tap_action:
          action: none
      - type: image
        entity: sensor.rozika_water_temp
        image: /local/lg-icons/temp_20.png
        state_image:
          20℃: /local/lg-icons/temp_20-on.png
        style:
          top: 16%
          left: 66%
          width: 13%
          image-rendering: auto
        tap_action:
          action: none
      - type: image
        entity: sensor.rozika_water_temp
        image: /local/lg-icons/temp_30.png
        state_image:
          30℃: /local/lg-icons/temp_30-on.png
        style:
          top: 16%
          left: 77%
          width: 13%
          image-rendering: auto
        tap_action:
          action: none
      - type: image
        entity: sensor.rozika_water_temp
        image: /local/lg-icons/temp_40.png
        state_image:
          40℃: /local/lg-icons/temp_40-on.png
        style:
          top: 32%
          left: 55%
          width: 13%
        image-rendering: auto
        tap_action:
          action: none
      - type: image
        entity: sensor.rozika_water_temp
        image: /local/lg-icons/temp_60.png
        state_image:
          60℃: /local/lg-icons/temp_60-on.png
        style:
          top: 32%
          left: 66%
          width: 13%
          image-rendering: auto
        tap_action:
          action: none
      - type: image
        entity: sensor.rozika_water_temp
        image: /local/lg-icons/temp_95.png
        state_image:
          95℃: /local/lg-icons/temp_95-on.png
        style:
          top: 32%
          left: 77%
          width: 13%
          image-rendering: auto
        tap_action:
          action: none
      - type: image
        entity: sensor.rozika_spin_speed
        image: /local/lg-icons/spin_no.png
        state_image:
          'No': /local/lg-icons/spin_no-on.png
        style:
          top: 51%
          left: 55%
          width: 13%
          image-rendering: auto
        tap_action:
          action: none
      - type: image
        entity: sensor.rozika_spin_speed
        image: /local/lg-icons/spin_400.png
        state_image:
          '400': /local/lg-icons/spin_400-on.png
        style:
          top: 51%
          left: 66%
          width: 13%
          image-rendering: auto
        tap_action:
          action: none
      - type: image
        entity: sensor.rozika_spin_speed
        image: /local/lg-icons/spin_600.png
        state_image:
          '600': /local/lg-icons/spin_600-on.png
        style:
          top: 51%
          left: 77%
          width: 13%
          image-rendering: auto
        tap_action:
          action: none
      - type: image
        entity: sensor.rozika_spin_speed
        image: /local/lg-icons/spin_800.png
        state_image:
          '800': /local/lg-icons/spin_800-on.png
        style:
          top: 63%
          left: 55%
          width: 13%
          image-rendering: auto
        tap_action:
          action: none
      - type: image
        entity: sensor.rozika_spin_speed
        image: /local/lg-icons/spin_1000.png
        state_image:
          '1000': /local/lg-icons/spin_1000-on.png
        style:
          top: 63%
          left: 66%
          width: 13%
          image-rendering: auto
        tap_action:
          action: none
      - type: image
        entity: sensor.rozika_spin_speed
        image: /local/lg-icons/spin1200.png
        state_image:
          '1200': /local/lg-icons/spin1200-on.png
        style:
          top: 63%
          left: 77%
          width: 13%
          image-rendering: auto
        tap_action:
          action: none
      - type: state-label
        entity: sensor.rozika_time_display
        style:
          color: '#f0f0f0'
          font-size: 57.5px
          font-family: segment7
          left: 31.5%
          top: 33.5%
          transform: translate(-100%,-50%)
        tap_action:
          action: none
  ```
