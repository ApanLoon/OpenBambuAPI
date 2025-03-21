# pushing.pushall

Reports the complete status of the printer. 

This is unnecessary for the X1 series since it already transmits the full object each time. However, the P1 series only sends the values that have been updated compared to the previous report.

> [!CAUTION]
> As a rule of thumb, refrain from executing this command at intervals less than 5 minutes on the P1P, as it may cause lag due to its hardware limitations.

**Request**

```json
{
    "pushing": {
        "sequence_id": "0",
        "command": "pushall",
        "version": 1,
        "push_target": 1
    }
}
```

**Report**

```json
{
    "print": {
        "ams": {
            "ams": [
              {
                "humidity": "4",
                "id": "0",
                "temp": "22.7",
                "tray": [
                    {
                        "id": "0" // an empty tray
                    },
                    {
                        "bed_temp": "0",
                        "bed_temp_type": "0",
                        "cols": [
                            "000000FF"
                        ],
                        "drying_temp": "0",
                        "drying_time": "0",
                        "id": "1",
                        "nozzle_temp_max": "240",
                        "nozzle_temp_min": "190",
                        "remain": 0,
                        "tag_uid": "0000000000000000",
                        "tray_color": "000000FF",
                        "tray_diameter": "0.00",
                        "tray_id_name": "",
                        "tray_info_idx": "GFA00",
                        "tray_sub_brands": "",
                        "tray_type": "PLA",
                        "tray_uuid": "00000000000000000000000000000000",
                        "tray_weight": "0",
                        "xcam_info": "000000000000000000000000"
                    },
                    {
                        "bed_temp": "0",
                        "bed_temp_type": "0",
                        "cols": [
                            "DFE2E3FF"
                        ],
                        "drying_temp": "0",
                        "drying_time": "0",
                        "id": "2",
                        "nozzle_temp_max": "240",
                        "nozzle_temp_min": "190",
                        "remain": 0,
                        "tag_uid": "0000000000000000",
                        "tray_color": "DFE2E3FF",
                        "tray_diameter": "0.00",
                        "tray_id_name": "",
                        "tray_info_idx": "GFA05",
                        "tray_sub_brands": "",
                        "tray_type": "PLA",
                        "tray_uuid": "00000000000000000000000000000000",
                        "tray_weight": "0",
                        "xcam_info": "000000000000000000000000"
                    },
                    {
                        "bed_temp": "0",
                        "bed_temp_type": "0",
                        "cols": [
                            "F95959FF"
                        ],
                        "drying_temp": "0",
                        "drying_time": "0",
                        "id": "3",
                        "nozzle_temp_max": "240",
                        "nozzle_temp_min": "190",
                        "remain": 0,
                        "tag_uid": "0000000000000000",
                        "tray_color": "F95959FF",
                        "tray_diameter": "0.00",
                        "tray_id_name": "",
                        "tray_info_idx": "GFL00",
                        "tray_sub_brands": "",
                        "tray_type": "PLA",
                        "tray_uuid": "00000000000000000000000000000000",
                        "tray_weight": "0",
                        "xcam_info": "000000000000000000000000"
                    }
                ]
            }
        ],
        "ams_exist_bits": "1",
        "insert_flag": true,
        "power_on_flag": false,
        "tray_exist_bits": "e",
        "tray_is_bbl_bits": "e",
        "tray_now": "255", // 254 if external spool / vt_tray, otherwise is ((ams_id * 4) + tray_id) for current tray (ams 2 tray 2 would be (1*4)+1 = 5)
        "tray_pre": "255",
        "tray_read_done_bits": "e",
        "tray_reading_bits": "0",
        "tray_tar": "255",
        "version": 4
        },
        "ams_rfid_status": 6,
        "ams_status": 0,
        "aux_part_fan": true, // is aux fan installed
        "bed_target_temper": 25.0,
        "bed_temper": 25.0,
        "big_fan1_speed": "0", // Auxilliary fan
        "big_fan2_speed": "0", // Chamber fan
        "chamber_temper": 24.0,
        "command": "push_status",
        "cooling_fan_speed": "0", // Part Cooling fan
        "fail_reason": "0",
        "fan_gear": 0,
        "filam_bak": [],
        "force_upgrade": false,
        "gcode_file": "",
        "gcode_file_prepare_percent": "0",
        "gcode_start_time": "0",
        "gcode_state": "IDLE",
        "heatbreak_fan_speed": "0",
        "hms": [],
        "home_flag": 0,
        "hw_switch_state": 1,
        "ipcam": {
            "ipcam_dev": "1",
            "ipcam_record": "disable",
            "resolution": "1080p",
            "timelapse": "disable"
        },
        "layer_num": 0,
        "lifecycle": "product",
        "lights_report": [
            {
                "mode": "on",
                "node": "chamber_light"
            },
            {
                "mode": "flashing",
                "node": "work_light"
            }
        ],
        "maintain": 3,
        "mc_percent": 0,
        "mc_print_error_code": "0",
        "mc_print_stage": "1",
        "mc_print_sub_stage": 0,
        "mc_remaining_time": 0,
        "mess_production_state": "active",
        "nozzle_diameter": "0.4",
        "nozzle_target_temper": 25.0,
        "nozzle_temper": 25.0,
        "online": {
            "ahb": false,
            "rfid": false,
            "version": 9
        },
        "print_error": 0,
        "print_gcode_action": 0,
        "print_real_action": 0,
        "print_type": "",
        "profile_id": "",
        "project_id": "",
        "queue_number": 0,
        "sdcard": true,
        "sequence_id": "2021",
        "spd_lvl": 2,
        "spd_mag": 100,
        "stg": [],
        "stg_cur": -1,
        "subtask_id": "",
        "subtask_name": "",
        "task_id": "",
        "total_layer_num": 0,
        "upgrade_state": {
            "ahb_new_version_number": "",
            "ams_new_version_number": "",
            "consistency_request": false,
            "dis_state": 0,
            "err_code": 0,
            "force_upgrade": false,
            "message": "",
            "module": "null",
            "new_version_state": 2,
            "ota_new_version_number": "",
            "progress": "0",
            "sequence_id": 0,
            "status": "IDLE"
        },
        "upload": {
            "file_size": 0,
            "finish_size": 0,
            "message": "Good",
            "oss_url": "",
            "progress": 0,
            "sequence_id": "0903",
            "speed": 0,
            "status": "idle",
            "task_id": "",
            "time_remaining": 0,
            "trouble_id": ""
        },
        "vt_tray": { // external spool
            "bed_temp": "0",
            "bed_temp_type": "0",
            "cols": [
                "00000000"
            ],
            "drying_temp": "0",
            "drying_time": "0",
            "id": "254",
            "nozzle_temp_max": "0",
            "nozzle_temp_min": "0",
            "remain": 0,
            "tag_uid": "0000000000000000",
            "tray_color": "00000000",
            "tray_diameter": "0.00",
            "tray_id_name": "",
            "tray_info_idx": "",
            "tray_sub_brands": "",
            "tray_type": "",
            "tray_uuid": "00000000000000000000000000000000",
            "tray_weight": "0",
            "xcam_info": "000000000000000000000000"
            },
        "wifi_signal": "-45dBm",
        "xcam": {
            "allow_skip_parts": false,
            "buildplate_marker_detector": false,
            "first_layer_inspector": true,
            "halt_print_sensitivity": "medium",
            "print_halt": true,
            "printing_monitor": true,
            "spaghetti_detector": true
        },
        "xcam_status": "0"
    }
}
```
<details open style="margin-left: 0rem;">
<summary style="font-size:1.5rem;">print</summary>
The print object is the container for the report, it contains a many top level properties as well as several objects with more information.

<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">ams (object)</summary>
An object describing the AMS attached to this printer.

<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">ams (array)</summary>
An array of objects describing a single AMS module.
<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">humidity</summary>
A string containing a number indicating the humidity level inside the AMS module. The number ranges from 0 to 5 where 5 is the lowest and 0 is the highest. 
</details>
<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">id</summary>
A string containing a number that is the index of this AMS module.
</details>
<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">temp</summary>
A string containing a number indicating the current temperature inside this AMS module in degrees celcius. (Unclear if the unit changes to farenheit based on a printer setting)
</details>
<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">tray</summary>
An array of objects describing a tray of an AMS module. This object is also used to describe the external spool tray in the "vt_tray" property of the "print" object.

<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">bed_temp</summary>
A string containing a number indicating the recommended bed temperature for the filament in this tray in degrees celcius. (Unclear if the unit changes to farenheit based on a printer setting)
</details>
<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">bed_temp_type</summary>
A string containing a number of unknown meaning. Seen values are: "1" and "2".
</details>
<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">cali_idx</summary>
A number of unknown meaning.
</details>
<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">cols</summary>
An array of strings indicating the RGBA colour of the filament in this tray. For example: "8E9089FF".
</details>
<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">c_type</summary>
A number of unknown meaning. Seen values are: 0.
</details>
<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">drying_temp</summary>
A string containing a number indicating the recommended drying temperature in degrees celsius for the filament in this tray. (Unclear if the unit changes to farenheit based on a printer setting)
</details>
<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">drying_time</summary>
A string containing a number representing the number of hours to fully dry the filament in this tray.
</details>
<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">id</summary>
A string containing a number that is the index of this tray within this AMS module.
</details>
<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">nozzle_temp_max</summary>
A string containing a number indicating the recommended maximum nozzle temperature in degrees celsius for the filament in this tray. (Unclear if the unit changes to farenheit based on a printer setting)
</details>
<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">nozzle_temp_min</summary>
A string containing a number indicating the recommended minimum nozzle temperature in degrees celsius for the filament in this tray. (Unclear if the unit changes to farenheit based on a printer setting)
</details>
<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">remain</summary>
A string containing a number indicating the remaining amount, in percent, of filament in this tray.
</details>
<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">tag_uid</summary>
A string that indicates the RFID tag of the filament in this tray.
</details>
<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">tray_color</summary>
A string indicating the RGBA colour of the filament in this tray. For example "8E9089FF".
</details>
<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">tray_diameter</summary>
A string containing a number indicating the diameter, in millimeters, of the filament in this tray.
</details>
<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">tray_id_name</summary>
A string indicating the id code of the detected filament in this tray. Seen values are: "A00-D0" (Bambu PLA Basic GRAY), "G00-K0" (Bambu PETG Basic BLACK), "A00-K0" (Bambu PLA Basic BLACK), "A00-W1" (Bambu PLA Basic JADE WHITE).
</details>
<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">tray_info_idx</summary>
A string indicating the id code of the family of the detected filament in this tray. Seen values are: "GFA00" (Bambu PLA Basic) and "GFG00" (Bambu PETG Basic) 
</details>
<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">tray_sub_brands</summary>
A string indicating the name of the family of the detected filament in this tray. Seen values are "PLA Basic" and "PETG Basic".
</details>
<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">tray_type</summary>
A string indicating the type of plastic of the detected filament in this tray. Seen values are "PLA" and "PETG".
</details>
<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">tray_uuid</summary>
A string of unknown meaning.
</details>
<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">tray_weight</summary>
A string containing a number indicating the weight, in grammes, of a full spool of the detected filament in this tray.
</details>
<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">xcam_info</summary>
A string of unknown meaning.
</details>

</details> <!-- tray-->

</details> <!-- ams (array) -->

<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">ams_exist_bits</summary>
A string containing a number that is a bit mask indicating which AMS instances are available.
</details>
<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">ams_exist_bits_raw</summary>
The difference between this property and "ams_exist_bits" is unknown.
</details>
<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">insert_flag</summary>
A boolean of unknown meaning.
</details>
<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">power_on_flag</summary>
A boolean indicating if the AMS system is powered?
</details>
<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">tray_exist_bits</summary>
A number containing a bit mask identifying each tray of each AMS module. The bit to check can be calculated by (Ams.id * 4 + Tray.id) When a bit is set, there is filament detected in the tray.
</details>
<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">tray_is_bbl_bits</summary>
A number containing a bit mask identifying each tray of each AMS module. The bit to check can be calculated by (Ams.id * 4 + Tray.id) When a bit is set, the detected filament in the tray is official Bambu Labs filament.
</details>
<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">tray_now</summary>
A string containing a number indicating what tray is currently loaded into the extruder. 254=External spool, 255=No filament is loaded.
</details>
<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">tray_pre</summary>
A string containing a number indicating the tray that was previously loaded into the extruder. 254=External spool, 255=No filament.
</details>
<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">tray_read_done_bits</summary>
A number containing a bit mask identifying each tray of each AMS module. The bit to check can be calculated by (Ams.id * 4 + Tray.id) When a bit is set, the RFID has been read in the tray.
</details>
<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">tray_reading_bits</summary>
A number containing a bit mask identifying each tray of each AMS module. The bit to check can be calculated by (Ams.id * 4 + Tray.id) When a bit is set, the RFID is currently being read in the tray.
</details>
<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">tray_tar</summary>
A string containing a number indicating the tray that is currently being loaded into the extruder. 254=External spool, 255=No filament.
</details>
<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">version</summary>
A number of unknown meaning.
</details>

</details> <!-- ams (object) -->

<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">ams_rfid_status</summary>
A number indicating the status of the RFID scanner. Known values are:

| Value | Name |
| ----: | ---- |
|     0 | IDLE           |
|     1 | READING        |
|     2 | GCODE_TRANS    |
|     3 | GCODE_RUNNING  |
|     4 | ASSITANT       |
|     5 | SWITCH_FILAMENT|
|     6 | HAS_FILAMENT   |
</details>

<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">ams_status</summary>
A number indicating the status of the AMS. The value is a bit field containing two eight bit values:

## Bit field values
| Bits | Name        |
| ---: | ----------- |
|  0-7 | Sub status  |
| 8-15 | Main status |

## Main status values
| Value | Name             |
| ----: | ---------------- |
|  0x00 | IDLE             |
|  0x01 | FILAMENT_CHANGE  |
|  0x02 | RFID_IDENTIFYING |
|  0x03 | ASSIST           |
|  0x04 | CALIBRATION      |
|  0x10 | SELF_CHECK       |
|  0x20 | DEBUG            |
|  0xFF | UNKNOWN          |

## FILAMENT_CHANGE sub status
| Value | Name               |
| ----: | ------------------ |
|     0 | IDLE               |
|     1 | HEAT_NOZZLE        |
|     2 | CUT_FILAMENT       |
|     3 | PULL_CURR_FILAMENT |
|     4 | PUSH_NEW_FILAMENT  |
|     5 | PURGE_OLD_FILAMENT |
|     6 | FEED_FILAMENT      |
|     7 | CONFIRM_EXTRUDED   |
|     8 | CHECK_POSITION     |

## RFID_IDENTIFYING sub status
See "ams_rfid_status"
</details>

<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">aux_part_fan</summary>
A boolean possibly indicating if the printer has a part cooling fan or not.
</details>

<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">bed_target_temper</summary>
A number indicating the current target temperature of the print bed in degrees celcius. (Unclear if the unit changes to farenheit based on a printer setting)
</details>

<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">bed_temper</summary>
A number indicating the current temperature of the print bed in degrees celcius. (Unclear if the unit changes to farenheit based on a printer setting)
</details>

<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">big_fan1_speed (Aux fan speed)</summary>
A string containing a four bit decimal number representing the fan speed in percent where 0 is off and 15 is 100%.
</details>

<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">big_fan2_speed (Chamber fan speed)</summary>
A string containing a four bit decimal number representing the fan speed in percent where 0 is off and 15 is 100%.
</details>

<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">cali_version</summary>
A number of unknown meaning.
</details>

<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">chamber_temper</summary>
A number indicating the current temperature of the chamber in degrees celcius. (Unclear if the unit changes to farenheit based on a printer setting)
</details>

<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">cooling_fan_speed (Part cooling fan speed)</summary>
A string containing a four bit decimal number representing the fan speed in percent where 0 is off and 15 is 100%.
</details>

<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">ctt</summary>
A number of unknown meaning.
</details>

<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">device</summary>
An object describing print heads in the device. This was possibly added in preparation for creating a multi-toolhead printer.

<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">fan</summary>
A number of unknown meaning.
</details>

<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">nozzle</summary>
An associative array with keys that seem to indicate a possibility of multiple nozzles in a single device.
<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">"0"</summary>
Each number key has a value that is an object.
<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">info</summary>
A number of unknown meaning.
</details>
<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">temp</summary>
A number indicating the current temperature of the nozzle in degrees celcius. (Unclear if the unit changes to farenheit based on a printer setting)
</details>
</details><!--  NozzleInfo -->
<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">info</summary>
A key named "info" with a number value of unknown meaning.
</details>
</details><!-- nozzle -->
</details><!-- device -->

<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">fail_reason</summary>
A string.
</details>

<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">fan_gear</summary>
A number that appears to be a bit field containing information about multiple fans.
</details>

<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">filam_bak</summary>
An array of unknown items.
</details>

<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">force_upgrade</summary>
A boolean.
</details>

<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">gcode_file</summary>
A string identifying the gcode that is currently printed. The path is relative to the mount point "data" where the 3mf project file is mounted to. After the print is completed, the name remains set until the next print starts or the printer is reset.
</details>

<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">gcode_file_prepare_percent</summary>
A string containing a number that possibly represents the progress of downloading and mounting(unzipping) the 3mf project file.
</details>

<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">gcode_start_time (Removed in fw 01.08.00.00)</summary>
A string containing a number represending the number of seconds sunce UNIX epoch the print job was started.
</details>

<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">gcode_state</summary>
A string representing the state of the current job. Known values are 
"IDLE", "PAUSE", "RUNNING", "SLICING", "PREPARE", "FINISH" and "FAILED".
</details>

<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">heatbreak_fan_speed</summary>
A string containing a four bit decimal number representing the fan speed in percent where 0 is off and 15 is 100%. (Uncertain)
</details>

<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">hms</summary>
An array of unknown items.
</details>

<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">home_flag</summary>
A number that is a bit field representing several flags. Known flags are:

| Bit(s) | Name                              | Comment                                       |
| -----: | --------------------------------- | --------------------------------------------- |
|      0 | is_x_axis_home                    |                                               |
|      1 | is_y_axis_home                    |                                               |
|      2 | is_z_axis_home                    |                                               |
|      3 | is_220V_voltage                   | If false, assume 110V                         |
|      4 | xcam_auto_recovery_step_loss      |                                               |
|      5 | camera_recording                  |                                               |
|      7 | ams_calibrate_remain_flag         |                                               |
|    8-9 | sdcard_state                      | NO_SDCARD = 0 <br />HAS_SDCARD_NORMAL = 1<br />HAS_SDCARD_ABNORMAL = 2<br/>SDCARD_STATE_NUM = 3                                        |
|     10 | ams_auto_switch_filament_flag     | Only read this after n received messages      | 
|     17 | xcam_allow_prompt_sound           | Only read this after n received messages      | 
|     18 | is_support_prompt_sound           |                                               |
|     19 | is_support_filament_tangle_detect |                                               |
|     20 | xcam_filament_tangle_detect       | Only read this after n received messages      | 
|     21 | is_support_motor_noise_cali       | Only set this if it was previously false?     |
|     22 | is_support_user_preset            |                                               |
|     24 | nozzle_blob_detection_enabled     |                                               |
|     25 | is_support_nozzle_blob_detection  |                                               |
|     26 | installed_plus                    | These toghether indicate P1S Plus             | 
|     27 | supported_plus                    | These toghether indicate P1S Plus             |
|     28 | ams_air_print_status              |                                               |
|     29 | is_support_air_print_detection    |                                               |

Note: Bambu Studio does something weird when decoding the sdcard state. I have not verified that the sdcard_state above is correct but if it is, Bambu Studio is wrong. The source code would make sense if the mask was binary, but it is hexadecimal:
```c++
sdcard_state = MachineObject::SdcardState((flag >> 8) & 0x11);
```
</details>

<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">hw_switch_state</summary>
A number of unknown meaning.
</details>

<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">ipcam</summary>
An object describing the web camera of the printer.
<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">agora_service</summary>
A string. Seen values are: "disable".
</details>
<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">ipcam_dev</summary>
A string containing a number.
</details>
<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">ipcam_record</summary>
A string. Seen values are "enable".
</details>
<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">mode_bits</summary>
A number.
</details>
<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">resolution</summary>
A string indicating the vertical resolution of the camera. Seen values are: "1080p".
</details>
<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">rtsp_url</summary>
A string containing the RTSPS url that can be used for accessing the web camera. If the "LAN Mode Liveview" configuration option is diabled in the printer this string has the value "disable".
</details>
<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">timelapse</summary>
A string indicating if a timelapse is being recorded. Seen values are "disable" and "enable".
</details>
<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">tutk_server</summary>
A string. Seen values are "disable" and "enable". 
</details>

</details><!--  -->

<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">job_id</summary>
A string.
</details>

<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">layer_num</summary>
A number indicating the layer the print is currently on.
</details>

<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">lifecycle (Removed in fw ?)</summary>
A string of unknown meaning. Seen values are "product".
</details>

<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">lights_report</summary>
An array of LightReport objects.
<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">LightReport</summary>
An object containing information about device lighting.
<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">mode</summary>
A string indicating the current mode of this light. Seen values are "on", "off" and "flashing".
</details>
<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">node</summary>
A string identifying the name of the light. Seen values are "chamber_light" and "work_light".
</details>

</details><!-- LightReport -->
</details><!-- lights_report -->

<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">maintain</summary>
A number representing a maintenance code. Seen values are:

| Value  | Guessed meaning               |
| -----: | ----------------------------- |
|      3 | Firmware update is available? |
| 131075 | Lead screws need lubrication? |
</details>

<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">mc_percent</summary>
A number between 0 and 100 indicating the current print job progress.
</details>

<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">mc_print_error_code</summary>
A string containing a number.
</details>

<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">mc_print_stage</summary>
A string containing a number.
</details>

<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">mc_print_sub_stage</summary>
A number.

| Value  | Guessed meaning               |
| -----: | ----------------------------- |
|      0 | Printing?                     |
|      1 | Homing?                       |
|      2 | Purging filament?             |
|      4 | Retracting filament?          |
|      5 | Inspecting print bed? <br/> (Both after bed-leveling and first layer) |
</details>

<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">mc_remaining_time</summary>
A number indicating the remaining time of the current print job in minutes.
</details>

<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">mess_production_state (Removed in fw 01.08.00.00)</summary>
A string of unknown meaning. Seen values are: "active"
</details>

<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">net</summary>
An object describing the network configuration of the printer.
<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">conf</summary>
A number.
</details>
<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">info</summary>
An array of NetInfo objects.
</details>
<details style="margin-left: 2rem;">
<summary style="font-size:1.5rem;">NetInfo</summary>
<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">ip</summary>
A number containing a 32 bit unsigned integer representation of an IPv4 address.
</details>
<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">mask</summary>
A number containing a 32 bit unsigned integer representation of an IPv4 network mask.
</details>
</details><!-- NetInfo -->
</details><!-- net -->

<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">nozzle_diameter</summary>
A string containing a number representing the dimension of the nozzle in millimeters. For example "0.4".
</details>

<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">nozzle_target_temper</summary>
A number indicating the current target temperature of the nozzle in degrees celcius. (Unclear if the unit changes to farenheit based on a printer setting)
</details>

<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">nozzle_temper</summary>
A number indicating the current temperature of the nozzle in degrees celcius. (Unclear if the unit changes to farenheit based on a printer setting)
</details>

<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">nozzle_type</summary>
A string indicating the type of the nozzle. For example "hardened_steel".
</details>

<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">online</summary>
An object.
<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">ahb</summary>
A boolean.
</details>
<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">ext</summary>
A boolean.
</details>
<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">version</summary>
A number.
</details>
</details><!-- online -->

<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">param (Removed in fw 01.08.00.00)</summary>
A string of unknown meaning.
</details>

<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">print_error</summary>
A number of unknown meaning,
</details>

<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">print_gcode_action</summary>
A number of unknown meaning.
</details>

<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">print_real_action</summary>
A number of unknown meaning.
</details>

<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">print_type</summary>
A string indication if the print was initiated over the cloud or locally. Seen values are "", "cloud" and "local".
</details>

<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">profile_id</summary>
A string containing a number. Possibly an ID of the print profile used for slicing the current print job?
</details>

<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">project_id</summary>
A string containing a number. Possibly an ID of the project 3mf-file that is currently being printed?
</details>

<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">queue_est</summary>
A number of unknown meaning.
</details>

<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">queue_number</summary>
A number of unknown meaning.
</details>

<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">queue_sts</summary>
A number of unknown meaning.
</details>

<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">queue_total</summary>
A number of unknown meaning.
</details>

<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">s_obj</summary>
An array of unknown items.
</details>

<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">sdcard</summary>
A booloean indicating the presence of an SD card.
</details>

<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">spd_lvl</summary>
A number of unknown meaning.
</details>

<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">spd_mag</summary>
A number of unknown meaning.
</details>

<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">stg</summary>
An array of numbers representing a queue of stage ids. See "stg_cur".
</details>

<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">stg_cur</summary>
A number indicating the current printing stage. Known stages are:

| Stage | Name                                               |
| ----: | -------------------------------------------------- |
|     0 |  ""                                                |
|     1 |  "Auto bed leveling"                               |
|     2 |  "Heatbed preheating"                              |
|     3 |  "Sweeping XY mech mode"                           |
|     4 |  "Changing filament"                               |
|     5 |  "M400 pause"                                      |
|     6 |  "Paused due to filament runout"                   |
|     7 |  "Heating hotend"                                  |
|     8 |  "Calibrating extrusion"                           |
|     9 |  "Scanning bed surface"                            |
|    10 |  "Inspecting first layer"                          |
|    11 |  "Identifying build plate type"                    |
|    12 |  "Calibrating Micro Lidar"                         |
|    13 |  "Homing toolhead"                                 |
|    14 |  "Cleaning nozzle tip"                             |
|    15 |  "Checking extruder temperature"                   |
|    16 |  "Printing was paused by the user"                 |
|    17 |  "Pause of front cover falling"                    |
|    18 |  "Calibrating the micro lida"                      |
|    19 |  "Calibrating extrusion flow"                      |
|    20 |  "Paused due to nozzle temperature malfunction"    |
|    21 |  "Paused due to heat bed temperature malfunction"  |
|    22 |  "Filament unloading"                              |
|    23 |  "Skip step pause"                                 |
|    24 |  "Filament loading"                                |
|    25 |  "Motor noise calibration"                         |
|    26 |  "Paused due to AMS lost"                          |
|    27 |  "Paused due to low speed of the heat break fan"   |
|    28 |  "Paused due to chamber temperature control error" |
|    29 |  "Cooling chamber"                                 |
|    30 |  "Paused by the Gcode inserted by user"            |
|    31 |  "Motor noise showoff"                             |
|    32 |  "Nozzle filament covered detected pause"          |
|    33 |  "Cutter error pause"                              |
|    34 |  "First layer error pause"                         |
|    35 |  "Nozzle clog pause"                               |
</details>

<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">subtask_id</summary>
A string containing a number of unknown meaning.
</details>

<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">subtask_name</summary>
A string indicating the name of the currently printing job.
</details>

<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">task_id</summary>
A string containing a number of unknown meaning.
</details>

<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">total_layer_num</summary>
A number indicating the total number of layers in the current print job.
</details>

<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">upgrade_state</summary>
<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">ahb_new_version_number</summary>
A string.
</details>
<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">ams_new_version_number</summary>
A string.
</details>
<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">consistency_request</summary>
A boolean.
</details>
<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">dis_state</summary>
A number.
</details>
<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">err_code</summary>
A number.
</details>
<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">ext_new_version_number</summary>
A string.
</details>
<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">force_upgrade</summary>
A boolean.
</details>
<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">idx</summary>
A number.
</details>
<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">idx1</summary>
A number.
</details>
<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">lower_limit</summary>
A string. Seen values are: "00.00.00.00".
</details>
<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">message</summary>
A string. Seen values are: "", "start downloading ota...", "downloading: mc", "downloading: rk1126", "verifying: rk1126", "unziping: rk1126", "rk1126 start flashing...", "mc start flashing...", "RK1126 start write flash success" and "verifying: hms"
</details>
<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">module</summary>
A string. Seen values are: "", "null", "ota", "mc", "rk1126" and "ap".
</details>
<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">new_version_state</summary>
A number.
</details>
<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">ota_new_version_number</summary>
A string. Seen values are: "01.08.00.00".
</details>
<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">progress</summary>
A string containing a number between "0" and "100" indicating the upgrade progress in percent.
</details>
<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">sequence_id</summary>
A string containing a number. Seen values are: "0", "0903" and "2006".
</details>
<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">sn</summary>
A string.
</details>
<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">status</summary>
A string. Seen values are: "IDLE", "DOWNLOADING", "PRE_FLASH_START", "FLASH_START", "FLASH_SUCCESS" and "UPGRADE_SUCCESS".
</details>


</details><!-- upgrade_state -->

<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">upload</summary>
<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">file_size</summary>
A number.
</details>
<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">finish_size</summary>
A number.
</details>
<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">message</summary>
A string. Seen values are: "Good".
</details>
<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">oss_url</summary>
A string.
</details>
<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">progress</summary>
A number.
</details>
<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">sequence_id</summary>
A string containing a number.
</details>
<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">speed</summary>
A number.
</details>
<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">status</summary>
A string. Seen values are: "idle"
</details>
<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">task_id</summary>
A string.
</details>
<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">time_remaining</summary>
A number.
</details>
<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">trouble_id</summary>
A string.
</details>
</details><!-- upload -->

<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">vt_tray</summary>
An object describing the filament in the external spool. See "tray".
</details>

<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">wifi_signal</summary>
A string indicating the current WIFI signal strength. For example: "-37dBm".
</details>

<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">xcam</summary>
An object containing information about the lidar scanner in the printer.
<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">allow_skip_parts</summary>
A boolean of unknown meaning.
</details>
<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">buildplate_marker_detector</summary>
A boolean of unknown meaning.
</details>
<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">first_layer_inspector</summary>
A boolean of unknown meaning.
</details>
<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">halt_print_sensitivity</summary>
A string. Seen values are: "medium".
</details>
<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">print_halt</summary>
A boolean of unknown meaning.
</details>
<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">printing_monitor</summary>
A boolean of unknown meaning.
</details>
<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">spaghetti_detector</summary>
A boolean of unknown meaning.
</details>
</details><!-- xcam -->

<details style="margin-left: 1rem;">
<summary style="font-size:1.5rem;">xcam_status</summary>
A string containing a number of unknown meaning.
</details>

</details><!-- print -->

