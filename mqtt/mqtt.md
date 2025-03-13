# Basics

All messages on the MQTT broker are JSON encoded

There is two ways to connect to the MQTT broker

## Cloud MQTT server

URL: `mqtt://us.mqtt.bambulab.com:8883`

TLS: **yes**

Authentication: **required**

**Username:** `u_{USER_ID}`, where the user id can be grabbed via [the GET /v1/design-user-service/my/preference
 API](cloud-http.md#get-v1design-user-servicemypreference)

**Password:** `{ACCESS_TOKEN}` (the entire access token, no prefix or suffix)

## Local MQTT server

URL: `mqtt://{PRINTER_IP}:8883`

TLS: **yes**

Authentication: **required**

**Username:** `bblp`

**Password:** `dev_access_code` from a `Device` object (aka the LAN access code).

Wildcard subscriptions with `#` possible

> [!IMPORTANT]  
> Check out the [TLS Certificates](tls.md) page for more information on how to securely connect.

# Topics

## device/{DEVICE_ID}/report

For information from the device to the slicer, including responses to commands

## device/{DEVICE_ID}/request

For commands to the device from the slicer

# Requests and reports

## Overview

**Request structure**

```json
{
    "{TYPE}": {
        "sequence_id": "0", // Incremented by 1 on each command
        "command": "{COMMAND}",
        ...
    }
}
```

**Report structure**

```json
{
    "{TYPE}": {
        "sequence_id": "0", // Same as the one sent in the request
        "command": "{COMMAND}",

        "result": "success", // Case insensitive!
        "reason": "", // Might not be present for some commands

        ... // All parameters from the original command
    }
}
```

## info.get_version

Get current version of printer

**Request**

```json
{
    "info": {
        "sequence_id": "0",
        "command": "get_version"
    }
}
```

**Report**

```json
{
    "info": {
        "command": "get_version",
        "module": [
            {
                "hw_ver": "",
                "name": "ota",
                "sn": "",
                "sw_ver": "01.01.01.00"
            },
            {
                "hw_ver": "AP05",
                "name": "rv1126",
                "sn": "[REDACTED]",
                "sw_ver": "00.00.14.74"
            },
            {
                "hw_ver": "TH07",
                "name": "th",
                "sn": "[REDACTED]",
                "sw_ver": "00.00.03.79"
            },
            {
                "hw_ver": "MC07",
                "name": "mc",
                "sn": "[REDACTED]",
                "sw_ver": "00.00.10.48/00.00.10.48"
            },
            {
                "hw_ver": "",
                "name": "xm",
                "sn": "",
                "sw_ver": "00.00.00.00"
            }
        ],
        "sequence_id": "0"
    }
}
```

## [pushging.pushall](pushing.pushall.md)

## upgrade.upgrade_confirm

Part of firmware upgrade process

**Request**

```json
{
    "upgrade": {
        "sequence_id": "0",
        "command": "upgrade_confirm",
        "src_id": 1 // src_id is always 1 for the slicer
    }
}
```

**Report**

TODO


## upgrade.consistency_confirm

Part of firmware upgrade process

**Request**

```json
{
    "upgrade": {
        "sequence_id": "0",
        "command": "consistency_confirm",
        "src_id": 1 // src_id is always 1 for the slicer
    }
}
```

**Report**

TODO

## upgrade.start

Part of firmware upgrade process

**Request**

```json
{
    "upgrade": {
        "sequence_id": "0",
        "command": "start",
        "src_id": 1, // src_id is always 1 for the slicer
        "url": "...",
        "module": "ota", // ota or ams
        "version": "",
    }
}
```

**Report**

TODO

## upgrade.get_history

Return the firmware history of the printer

**Request**

```json
{
    "upgrade": {
        "sequence_id": "0",
        "command": "get_history"
    }
}
```

**Report**

```json
{
  "upgrade": {
    "command": "get_history",
    "firmware_optional": [
      {
        "ams": [
          {
            "address": 0,
            "dev_model_name": "BL-A001",
            "device_id": "{DEVICE_ID}",
            "firmware": [
              {
                "description": "",
                "force_update": false,
                "url": "http://public-cdn.bambulab.com/upgrade/device/BL-A001/00.00.05.96/product/ams-ota_v00.00.05.96-20230106163615.json.sig",
                "version": "00.00.05.96"
              }
            ],
            "firmware_current": null
          }
        ],
        "firmware": {
          "description": "",
          "force_update": false,
          "url": "https://public-cdn.bambulab.com/upgrade/device/BL-P001/01.04.01.00/product/ota-v01.04.01.00-20230227162230.json.sig",
          "version": "01.04.01.00"
        }
      }
    ],
    "reason": "",
    "result": "success",
    "sequence_id": "0"
  }
}
```

## Trigger downgrade
TODO

## print.stop

Stops a print. Sent with QoS of **1** for higher priority.

**Request**

```json
{
    "print": {
        "sequence_id": "0",
        "command": "stop",
        "param": "", // Always empty
    }
}
```

**Report**

See basic structure

## print.pause

Pauses a print. Sent with QoS of **1** for higher priority.

**Request**

```json
{
    "print": {
        "sequence_id": "0",
        "command": "pause",
        "param": "", // Always empty
    }
}
```

**Report**

See basic structure

## print.resume

Resumes a print. Sent with QoS of **1** for higher priority.

**Request**

```json
{
    "print": {
        "sequence_id": "0",
        "command": "resume",
        "param": "", // Always empty
    }
}
```

**Report**

See basic structure

## print.ams_change_filament

Tells printer to perform a filament change using AMS.

**Request**

```json
{
    "print": {
        "sequence_id": "0",
        "command": "ams_change_filament",
        "target": 0, // ID of filament tray
        "curr_temp": 0, // Old print temperature
        "tar_temp": 0 // New print temperature
    }
}
```

**Report**

TODO

## print.ams_user_setting

Changes the AMS settings of the given unit.

**Request**

```json
{
    "print": {
        "sequence_id": "0",
        "command": "ams_user_setting",
        "ams_id": 0, // Index of the AMS
        "startup_read_option": true, // Read RFID on startup
        "tray_read_option": true // Read RFID on insertion
    }
}
```

**Report**

TODO

## print.ams_filament_setting

Changes the setting of the given filament in the given AMS.

**Request**

```json
{
    "print": {
        "sequence_id": "0",
        "command": "ams_filament_setting",
        "ams_id": 0, // Index of the AMS
        "tray_id": 0, // Index of the tray
        "tray_info_idx": "", // Probably the setting ID of the filament profile
        "tray_color": "00112233", // Formatted as hex RRGGBBAA (alpha is always FF)
        "nozzle_temp_min": 0, // Minimum nozzle temp for filament (in C)
        "nozzle_temp_max": 0, // Maximum nozzle temp for filament (in C)
        "tray_type": "PLA" // Type of filament, such as "PLA" or "ABS"
    }
}
```

**Report**

TODO

## print.ams_control

Gives basic control commands for the AMS.

**Request**

```json
{
    "print": {
        "sequence_id": "0",
        "command": "ams_control",
        "param": "resume" // "resume", "reset" or "pause"
    }
}
```

**Report**

TODO

## print.print_speed

Set print speed to one of the 4 presets.

**Request**

```json
{
    "print": {
        "sequence_id": "0",
        "command": "print_speed",
        "param": "2" // Print speed level as a string
                     // 1 = silent
                     // 2 = standard
                     // 3 = sport
                     // 4 = ludicrous
    }
}
```

**Report**

See basic structure

## print.gcode_file

Print a gcode file. This takes absolute paths.

**Request**

```json
{
    "print": {
        "sequence_id": "0",
        "command": "gcode_file",
        "param": "filename.gcode" // Filename (on the printer's filesystem) to print
    }
}
```

**Report**

See basic structure

## print.gcode_line

Send raw GCode to the printer.

**Request**

```json
{
    "print": {
        "sequence_id": "0",
        "command": "gcode_line",
        "param": "M420", // Gcode to execute, can use \n for multiple lines
        "user_id": "1234" // Optional
    }
}
```

**Report**

See basic structure

## print.calibration

Starts calibration process.

**Note:** Some printers might need `gcode_file` with `/usr/etc/print/auto_cali_for_user.gcode` instead!

**Request**

```json
{
    "print": {
        "sequence_id": "0",
        "command": "calibration"
    }
}
```

**Report**

TODO

## print.unload_filament

Unloads the filament.

**Note:** Some printers might need `gcode_file` with `/usr/etc/print/filament_unload.gcode` instead!

**Request**

```json
{
    "print": {
        "sequence_id": "0",
        "command": "unload_filament"
    }
}
```

**Report**

```json
{
    // TODO
}
```

## print.project_file

Prints a "project"

**Request**
```json
{
    "print": {
        "sequence_id": "0",
        "command": "project_file",
        "param": "Metadata/plate_X.gcode",
        "project_id": "0", // Always 0 for local prints
        "profile_id": "0", // Always 0 for local prints
        "task_id": "0", // Always 0 for local prints
        "subtask_id": "0", // Always 0 for local prints
        "subtask_name": "",

        "file": "", // Filename to print, not needed when "url" is specified with filepath
        "url": "file:///mnt/sdcard", // URL to print. Root path, protocol can vary. E.g., if sd card, "ftp:///myfile.3mf", "ftp:///cache/myotherfile.3mf"
        "md5": "",

        "timelapse": true,
        "bed_type": "auto", // Always "auto" for local prints
        "bed_levelling": true,
        "flow_cali": true,
        "vibration_cali": true,
        "layer_inspect": true,
        "ams_mapping": "",
        "use_ams": false
    }
}
```

**Report**

See basic structure

## print.skip_objects

Skips object ids defined in slice_info.config

**Request**
```json
{
  "print": {
    "sequence_id": "0",
    "command": "skip_objects",
    "timestamp": {unix_timestamp} // Current Unix timestamp, seems to be optional. 
    "obj_list": [ 
      206 // List of canceled object IDs. 
    ]
  }
}
```

**Report**

Updates [`pushing.pushall`](#pushingpushall) with 
```json
"s_obj": [
      {obj ids}
    ],
```

## system.ledctrl

Controls the LEDs of the printer.

**Request**

```json
{
    "system": {
        "sequence_id": "0",
        "command": "ledctrl",
        "led_node": "chamber_light", // Either "chamber_light" or "work_light"
        "led_mode": "on", // "on", "off" or "flashing"

        // The below effects are only used for "flashing" mode
        // but required to be present always
        "led_on_time": 500, // LED on time in ms
        "led_off_time": 500, // LED off time in ms
        "loop_times":  1, // How many times to loop
        "interval_time": 1000 // Looping interval
    }
}
```

**Report**

See basic structure

## system.get_access_code

Gets the LAN access code of the printer

**Request**
```json
{
    "system": {
        "sequence_id": "0",
        "command": "get_access_code"
    }
}
```

**Report**

```json
{
    "system": {
        "sequence_id": "0",
        "command": "get_access_code",
        "access_code": "{ACCESS_CODE}",
        "result": "success"
    }
}
```

## camera.ipcam_record_set

Turns on or off creating a recording of prints.

**Request**

```json
{
    "camera": {
        "sequence_id": "0",
        "command": "ipcam_record_set",
        "control": "enable" // "enable" or "disable"
    }
}
```

**Report**

See basic structure

## camera.ipcam_timelapse

Turns on or off creating a timelapse of prints.

**Request**

```json
{
    "camera": {
        "sequence_id": "0",
        "command": "ipcam_timelapse",
        "control": "enable" // "enable" or "disable"
    }
}
```

**Report**

See basic structure


## xcam.xcam_control_set

Configures the XCam (camera AI features, including Micro LIDAR features).

**Request**

```json
{
    "xcam": {
        "sequence_id": "0",
        "command": "xcam_control_set",
        "module_name": "first_layer_inspector", // "first_layer_inspector" or "spaghetti_detector"
        "control": true, // Enable the module
        "print_halt": false // Cause the module to halt the print on error
    }
}
```

**Report**

See basic structure

# Unsolicited (or semi-solicited) reports

## print.push_status

Reports printer status

### X1 Series
The X1 series always responds with the full object. See [`pushing.pushall`](#pushingpushall) for said object.

### P1 Series
Due to performance limitations the P1P uses the same object, but only actually responds with values that have been changed since the previous report. The full data can be requested using the [`pushing.pushall`](#pushingpushall) request.

## mc_print.push_info

Reports log lines of the printer. Can be requested with the [`pushing.pushall`](#pushingpushall) request.

```json
{
    "mc_print": {
        "command": "push_info",
        "param": "[LINK] GcodeLine (8) l=15 from 0600 ok: M106 P2 S255 \n\n",
        "sequence_id": "107"
    }
}
```

## mc_print.command = "push_info", mc_print.param = "[BMC] M900 KX.XXXX, LX.XXXXX, MX.XXXXX"

Report after Lidar calibration of the pressure advance (the reported K value)

```json
{
    "mc_print": {
        "command": "push_info",
        "param": "[BMC] M900 KX.XXXX, LX.XXXXX, MX.XXXXX",
        "sequence_id": "2004"
    }
}
```

## mc_print.command = "push_info", mc_print.param = "[AMS][TASK]amsX temp:XX.X;humidity:XX%;humidity_idx:X"

Report for the raw value for AMS humidity % per AMS id

```json
{
    "mc_print": {
        "command":"push_info",
        "param":"[AMS][TASK]ams0 temp:18.4;humidity:30%;humidity_idx:4",
        "sequence_id":"83"
    }
}
```
