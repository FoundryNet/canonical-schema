# Field Reference

All 694 canonical fields.

The per-field entries below cover the **366 corpus-attributed fields** — the
ones with real vendor tags behind them. The remaining **328 vocabulary fields**
are listed at the end: the kernel emits them, but no vendor tags map onto them
yet, so there is nothing to document per field beyond a name and a unit.

Each entry gives the field's type and unit with their provenance, a generated
description, how many corpus mappings resolve to it, which OEM families
contributed tags, and a sample of the real vendor tags observed.

Values for `type_source` and `unit_source`:

| Value | Meaning |
|---|---|
| `observed` | Type read from real sample values in the corpus |
| `inferred_from_unit` | Numeric because the field carries a physical unit |
| `inferred_from_name` | Type implied by a name suffix such as `_count` or `_state` |
| `unspecified` | No basis to state a type, so the field is left blank |
| `declared` | Unit stated explicitly in a vertical pack |
| `derived` | Unit taken from the field-name suffix |

---

## CNC machine tools (`cnc`)

82 fields.

### `spindle_speed_rpm`

Speed of the spindle, in rpm.

| | |
|---|---|
| Type | `integer` (observed) |
| Unit | `rpm` (declared) |
| Vertical | `cnc` |
| Example | `3400` |
| Mappings | 307 (263 confirmed) |
| OEM coverage | `brother`, `dmg_mori`, `fanuc`, `haas`, `heidenhain`, `hurco`, `mazak`, `mitsubishi`, `siemens`, `tornos` |

Mapped from: `Act Sp Speed (RPM)`, `SP_SPEED [RPM]`, `SPRPM (1/min)`, `Rotational_Speed_1/min`, `spindle_velocity[rpm]`, `S1_ActualVelocity`, `spindle_speed(1/min)`, `Speed_Spindle_rev/min`, `Spindle(1/min)`, `rotationalspeed(rev/min)` _(plus 297 more)_

### `spindle_load_pct`

Load on the spindle, in %.

| | |
|---|---|
| Type | `float` (observed) |
| Unit | `%` (declared) |
| Vertical | `cnc` |
| Example | `22.5` |
| Mappings | 255 (212 confirmed) |
| OEM coverage | `brother`, `dmg_mori`, `fanuc`, `haas`, `heidenhain`, `mazak`, `okuma`, `siemens`, `tornos` |

Mapped from: `SPINDLE_LOAD_PCT(%)`, `measured_spindle_torque`, `SP LOAD (%)`, `SpindleTorque (percent)`, `spindle load [%]`, `SP TORQUE PCT(percent)`, `Spindelueberlast`, `Spindle_Torque`, `Sp_Load`, `measured_sp_torque_pct` _(plus 245 more)_

### `axes.0.position_actual`

Position of a machine axis.

| | |
|---|---|
| Type | `float` (observed) |
| Unit | _none recorded_ (none) |
| Vertical | `cnc` |
| Example | `125.432` |
| Mappings | 232 (232 confirmed) |
| OEM coverage | `dmg_mori`, `fanuc`, `haas`, `heidenhain`, `mazak`, `okuma`, `siemens` |

Mapped from: `X_COORD(mm)`, `Pos_X_Act_mm`, `position x (mm)`, `xaxis_pos(m)`, `XActualPosition [in]`, `Xachse_Istposition (m)`, `X Mm (m)`, `XPosition [mm]`, `XPosition(inch)`, `x_m` _(plus 222 more)_

### `axes.0.temperature_c`

Temperature of a machine axis, in degC.

| | |
|---|---|
| Type | `float` (observed) |
| Unit | `degC` (derived) |
| Vertical | `cnc` |
| Example | `42.5` |
| Mappings | 222 (222 confirmed) |
| OEM coverage | `fanuc`, `haas`, `siemens` |

Mapped from: `driveTempX_celsius`, `temperaturexmotor_F`, `X Temp C`, `driveTempX_°C`, `X_TEMPERATURE_°F`, `XMotorTemperature_celsius`, `X Servo Temperature(F)`, `XMotorTemp_C`, `xtempc_F`, `Xmtr Temp [degC]` _(plus 212 more)_

### `axes.0.load_percent`

Load on a machine axis, in %.

| | |
|---|---|
| Type | `float` (observed) |
| Unit | `%` (derived) |
| Vertical | `cnc` |
| Example | `12.5` |
| Mappings | 215 (215 confirmed) |
| OEM coverage | `fanuc`, `haas`, `siemens` |

Mapped from: `driveLoadX`, `actual_x_current_pct`, `Load_X [%]`, `X_AXIS_LOAD_%`, `X TORQUE PCT (pct)`, `XSRVLOAD`, `servoloadx_pct`, `cur_x_load_pct`, `loadx`, `X_Current_Pct (pct)` _(plus 205 more)_

### `feed_rate`

Reported value for feed rate.

| | |
|---|---|
| Type | `float` (observed) |
| Unit | _none recorded_ (none) |
| Vertical | `cnc` |
| Example | `500.0` |
| Mappings | 215 (215 confirmed) |
| OEM coverage | `fanuc`, `haas`, `siemens` |

Mapped from: `FeedRate [ipr]`, `FEED_SPEED(mm/rev)`, `F_Speed (m/min)`, `ACT_FEED_mm/min`, `current_feed_rate`, `FEED RATE_ipr`, `F_Speed [mm/rev]`, `ACTFEED`, `FSPEED [ipm]`, `feedRateact [in/min]` _(plus 205 more)_

### `axes.1.position_actual`

Position of a machine axis.

| | |
|---|---|
| Type | `float` (observed) |
| Unit | _none recorded_ (none) |
| Vertical | `cnc` |
| Example | `80.221` |
| Mappings | 211 (211 confirmed) |
| OEM coverage | `fanuc`, `haas`, `siemens` |

Mapped from: `YIst [in]`, `Yachse_Istposition_mm`, `posy_in`, `Pos_Y (in)`, `Y1 Actualposition [mm]`, `y_ist [mm]`, `Y_ACT_POS(mm)`, `Y_Ist [mm]`, `measured_Y`, `Y_POS(in)` _(plus 201 more)_

### `sensor_readings.coolant_temp`

Temperature of the coolant circuit.

| | |
|---|---|
| Type | `float` (observed) |
| Unit | _none recorded_ (none) |
| Vertical | `cnc` |
| Example | `22.5` |
| Mappings | 209 (171 confirmed) |
| OEM coverage | `brother`, `dmg_mori`, `doosan`, `fanuc`, `haas`, `heidenhain`, `mazak`, `siemens`, `tornos` |

Mapped from: `value_coolant_temp`, `hydraulictemp (F)`, `coolantTemperature`, `fluid_temp [°F]`, `Kuehlmittel Temp(°C)`, `oil_temp(°C)`, `oiltemp(F)`, `Coolant Temperature_°F`, `cln_temp (°C)`, `COOLANT_TEMP_ACT` _(plus 199 more)_

### `axes.2.position_actual`

Position of a machine axis.

| | |
|---|---|
| Type | `float` (observed) |
| Unit | _none recorded_ (none) |
| Vertical | `cnc` |
| Example | `-200.1` |
| Mappings | 203 (203 confirmed) |
| OEM coverage | `fanuc`, `haas`, `siemens` |

Mapped from: `ZPOS`, `ZachseIstposition (in)`, `cur_z_position`, `actPosZ (in)`, `Z ACTUAL POSITION (mm)`, `zactual(mm)`, `actposz_in`, `z_ist [in]`, `z_act_pos [mm]`, `ZMACHPOS_mm` _(plus 193 more)_

### `tool_id`

Identifier of the active tool.

| | |
|---|---|
| Type | `string` (observed) |
| Unit | _none recorded_ (none) |
| Vertical | `cnc` |
| Example | `1` |
| Mappings | 164 (116 confirmed) |
| OEM coverage | `brother`, `dmg_mori`, `fanuc`, `haas`, `heidenhain`, `mitsubishi`, `siemens`, `tornos` |

Mapped from: `current_tool_act`, `t_num`, `cur_current_tool`, `CURRENT_TOOL_ACT`, `TOOL ID`, `toolIdActual`, `toolId`, `ACTIVE_TOOL_ACT`, `currentTool`, `Active_Tool` _(plus 154 more)_

### `sensor_readings.coolant_flow`

Flow rate through the coolant circuit.

| | |
|---|---|
| Type | `float` (observed) |
| Unit | _none recorded_ (none) |
| Vertical | `cnc` |
| Example | `5.2` |
| Mappings | 153 (153 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `coolant_pressure [L/min]`, `coolantpressure_ml/min`, `flood_coolant [L/min]`, `flowrate (gpm)`, `flow rate [ml/min]`, `COOLANT FLOW RATE_L/min`, `coolant pressure (ml/min)`, `flood_coolant(gpm)`, `FLOW_RATE_L/min`, `Cutting Fluid Flow_lpm` _(plus 143 more)_

### `spindle_speed_commanded`

Speed of the spindle.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `cnc` |
| Example | _none observed_ |
| Mappings | 62 (9 confirmed) |
| OEM coverage | `brother`, `doosan`, `fanuc`, `haas`, `heidenhain`, `hurco`, `mitsubishi`, `siemens`, `tornos` |

Mapped from: `SpindleSpeedSetpoint`, `spindle_speed_commanded_actual`, `spindle_speed_cmd_actual`, `SpindleSpeedSetpointRPM`, `spindle_speed_commanded_act`, `SPINDLE_SPEED_CMD`, `spindle_speed_cmd[rpm]`, `SPINDLE_SPEED_SETPOINT_ACT`, `spindleSpeedCmd`, `Spindle_Speed_Cmd` _(plus 52 more)_

### `feed_rate_actual`

Reported value for feed rate actual.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `cnc` |
| Example | _none observed_ |
| Mappings | 61 (28 confirmed) |
| OEM coverage | `brother`, `dmg_mori`, `doosan`, `fanuc`, `heidenhain`, `hurco`, `mazak`, `mitsubishi`, `okuma`, `siemens`, `tornos` |

Mapped from: `FEEDRATE`, `feedActual`, `VorschubGeschw_Ist`, `Feedrate_Actual`, `Feed Rate`, `Feed (mm_min)`, `FEED`, `feed_actual`, `feed_mm_min`, `FEED_RATE_MM_MIN` _(plus 51 more)_

### `axes.y_load_pct`

Load on a machine axis, in %.

| | |
|---|---|
| Type | `float` (inferred_from_unit) |
| Unit | `%` (derived) |
| Vertical | `cnc` |
| Example | _none observed_ |
| Mappings | 60 (14 confirmed) |
| OEM coverage | `brother`, `doosan`, `fanuc`, `heidenhain`, `hurco`, `mazak`, `mitsubishi`, `okuma`, `siemens`, `tornos` |

Mapped from: `y_load_act`, `y_axis_load[pct]`, `AchseY_Last`, `AxisYLoadActual`, `y_axis_load_actual`, `YAxisLoadPCT`, `CargaEjeY`, `AxisYLoad`, `AxisY_Load`, `axisYLoad` _(plus 50 more)_

### `axes.z_load_pct`

Load on a machine axis, in %.

| | |
|---|---|
| Type | `float` (inferred_from_unit) |
| Unit | `%` (derived) |
| Vertical | `cnc` |
| Example | _none observed_ |
| Mappings | 60 (12 confirmed) |
| OEM coverage | `brother`, `doosan`, `fanuc`, `heidenhain`, `mazak`, `okuma`, `siemens`, `tornos` |

Mapped from: `axisZLoad`, `zAxisLoadActual`, `axisZLoadAct`, `z_axis_load`, `AXIS_Z_LOAD_ACT`, `zaxisload`, `Axis Z Load`, `AxisZ_Load`, `Z Axis Load`, `axis_z_load_act` _(plus 50 more)_

### `axes.x_load_pct`

Load on a machine axis, in %.

| | |
|---|---|
| Type | `float` (inferred_from_unit) |
| Unit | `%` (derived) |
| Vertical | `cnc` |
| Example | _none observed_ |
| Mappings | 58 (12 confirmed) |
| OEM coverage | `brother`, `dmg_mori`, `doosan`, `fanuc`, `heidenhain`, `mazak`, `mitsubishi`, `tornos` |

Mapped from: `x_axis_load_actual`, `xaxisload`, `X_AXIS_LOAD_ACT`, `x_load`, `AXIS_X_LD`, `axis_x_load`, `xAxisLoadAct`, `x_axis_load`, `x_axis_load_pct`, `ChargeAxeX` _(plus 48 more)_

### `axes.x_position_actual`

Position of a machine axis.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `cnc` |
| Example | _none observed_ |
| Mappings | 53 (12 confirmed) |
| OEM coverage | `brother`, `dmg_mori`, `doosan`, `haas`, `heidenhain`, `mitsubishi`, `okuma`, `siemens`, `tornos` |

Mapped from: `XPositionMM`, `X_Axis_Position`, `x_pos_actual`, `xPosActualAct`, `xPositionActual`, `xPositionAct`, `xActualPositionAct`, `X Position`, `X_Ichi`, `XPosActualActual` _(plus 43 more)_

### `axes.y_position_actual`

Position of a machine axis.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `cnc` |
| Example | _none observed_ |
| Mappings | 52 (12 confirmed) |
| OEM coverage | `brother`, `dmg_mori`, `doosan`, `heidenhain`, `mazak`, `mitsubishi`, `okuma`, `siemens`, `tornos` |

Mapped from: `y_pos_actual`, `yPositionMM`, `y_position_mm`, `yposactual`, `y_actual_position`, `Y Position (mm)`, `y_position_actual`, `Y Actual Position`, `YPosActualActual`, `AxisYPos` _(plus 42 more)_

### `axes.z_position_actual`

Position of a machine axis.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `cnc` |
| Example | _none observed_ |
| Mappings | 52 (12 confirmed) |
| OEM coverage | `brother`, `dmg_mori`, `doosan`, `heidenhain`, `mazak`, `mitsubishi`, `okuma`, `siemens`, `tornos` |

Mapped from: `Z Pos Actual`, `zActualPositionActual`, `ActPos_Z`, `ZPositionMM`, `Z_Ichi`, `Z_POSITION_MM`, `ZPositionActual`, `zposactual`, `zPosActual`, `Z_POSITION` _(plus 42 more)_

### `axes.x_position_commanded`

Position of a machine axis.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `cnc` |
| Example | _none observed_ |
| Mappings | 49 (7 confirmed) |
| OEM coverage | `fanuc`, `siemens` |

Mapped from: `XPositionCmdMM`, `xPositionCmdMM`, `x_position_cmd_actual`, `x_position_cmd`, `X_SETPOINT_ACT`, `x_setpoint_actual`, `X Position Cmd`, `SetPos_X`, `x_setpoint_act`, `X1_CommandPosition` _(plus 39 more)_

### `feed_rate_commanded`

Reported value for feed rate commanded.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `cnc` |
| Example | _none observed_ |
| Mappings | 49 (7 confirmed) |
| OEM coverage | `fanuc`, `haas`, `heidenhain`, `mitsubishi`, `okuma`, `siemens`, `tornos` |

Mapped from: `FEED_RATE_SETPOINT_ACT`, `feed_rate_commanded_actual`, `FEED_RATE_COMMANDED`, `FeedRateCmdMM_MIN`, `feedRateCmd`, `FeedRateCommanded`, `FeedRateSet`, `feedRateSetpointAct`, `Feed Rate Setpoint`, `FeedRateSetpointActual` _(plus 39 more)_

### `tool_life_remaining`

Reported value for tool life remaining.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `cnc` |
| Example | _none observed_ |
| Mappings | 48 (12 confirmed) |
| OEM coverage | `brother`, `fanuc`, `haas`, `heidenhain`, `hurco`, `mazak`, `mitsubishi`, `okuma` |

Mapped from: `T_LIFE`, `TOOL_LIFE_LEFT`, `TOOL_LIFE_REMAINING`, `ToolLifeRemainingActual`, `tool_life_remaining`, `ToolLifeRem`, `TOOL_LIFE_COUNT`, `remaining_tool_life_act`, `tool_life_left_actual`, `toolLifeLeft` _(plus 38 more)_

### `rapid_override_pct`

Operator override applied to the machine, in %.

| | |
|---|---|
| Type | `float` (inferred_from_unit) |
| Unit | `%` (derived) |
| Vertical | `cnc` |
| Example | _none observed_ |
| Mappings | 44 (10 confirmed) |
| OEM coverage | `dmg_mori`, `fanuc`, `heidenhain`, `mitsubishi`, `tornos` |

Mapped from: `RapidTraverseOverride`, `RapidOverridePCT`, `Rapid Override`, `rapidTraverseOverrideAct`, `rapidTraverseOverrideActual`, `rapid_pct`, `rapid_override_percent`, `rapidTraverseOverride`, `rapid_ovr`, `rapid_override[pct]` _(plus 34 more)_

### `spindle_override_pct`

Operator override applied to the spindle, in %.

| | |
|---|---|
| Type | `float` (inferred_from_unit) |
| Unit | `%` (declared) |
| Vertical | `cnc` |
| Example | _none observed_ |
| Mappings | 44 (11 confirmed) |
| OEM coverage | `doosan`, `fanuc`, `haas`, `mitsubishi`, `tornos` |

Mapped from: `Spindle Speed Override (pct)`, `Spindle Speed Override`, `spindleOverrideActual`, `Spindle Override (pct)`, `spindle_ovr`, `spindleSpeedOverrideActual`, `SPINDLE_OVERRIDE_ACT`, `SpindleOverrideActual`, `spindleoverride`, `SPINDLE_OVERRIDE_PCT` _(plus 34 more)_

### `feed_override_pct`

Operator override applied to the feed axis, in %.

| | |
|---|---|
| Type | `float` (inferred_from_unit) |
| Unit | `%` (declared) |
| Vertical | `cnc` |
| Example | _none observed_ |
| Mappings | 43 (9 confirmed) |
| OEM coverage | `dmg_mori`, `doosan`, `fanuc`, `haas`, `heidenhain`, `mazak`, `mitsubishi` |

Mapped from: `feedrateOverride`, `FEEDRATE_OVERRIDE_PCT`, `feedrate_override_pct`, `FEED_OVERRIDE_ACT`, `FeedOverridePCT`, `Feed Override`, `feed_override_actual`, `feedrateoverride`, `FEEDRATE_OVERRIDE_ACT`, `FeedrateOverride` _(plus 33 more)_

### `axes.y_position_commanded`

Position of a machine axis.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `cnc` |
| Example | _none observed_ |
| Mappings | 37 (7 confirmed) |
| OEM coverage | `fanuc`, `siemens` |

Mapped from: `pos_cmd_y`, `y_position_cmd_actual`, `yPositionCommanded`, `YPositionCmdActual`, `Y_POSITION_COMMANDED_ACT`, `Y_POSITION_CMD_ACT`, `Y_POSITION_COMMANDED`, `Y1_CommandPosition`, `yPositionCommandedAct`, `Y Position Commanded` _(plus 27 more)_

### `axes.z_position_commanded`

Position of a machine axis.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `cnc` |
| Example | _none observed_ |
| Mappings | 37 (7 confirmed) |
| OEM coverage | `fanuc`, `siemens` |

Mapped from: `commanded_position_z`, `ZPositionCmdActual`, `zPositionCommandedAct`, `z_position_commanded_actual`, `ZPositionCommandedActual`, `z_position_cmd`, `ZPositionCmdMM`, `Z_POSITION_CMD_ACT`, `Z_POSITION_COMMANDED_ACT`, `z_position_commanded` _(plus 27 more)_

### `sensor_readings.coolant_pressure`

Pressure in the coolant circuit.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `cnc` |
| Example | _none observed_ |
| Mappings | 37 (10 confirmed) |
| OEM coverage | `brother`, `dmg_mori`, `doosan`, `haas`, `heidenhain`, `mazak`, `mitsubishi` |

Mapped from: `Coolant Pressure (bar)`, `coolantPumpPressure`, `coolantpressure`, `Coolant Pressure`, `COOL_PRES`, `COOLANT_PRESSURE_BAR`, `CoolantPressureActual`, `coolant_pressure_act`, `coolant_pressure[bar]`, `CoolantPumpPressure` _(plus 27 more)_

### `tool_life_used`

Reported value for tool life used.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `cnc` |
| Example | _none observed_ |
| Mappings | 37 (2 confirmed) |
| OEM coverage | `fanuc`, `heidenhain` |

Mapped from: `TOOL_WEAR_PCT`, `WerkzeugVerschleiss`, `toolWearPct`, `tool_wear_pct`, `ToolWearActual`, `toolWearPctAct`, `toolWearPctActual`, `tool_wear_actual`, `toolWear`, `ToolWearPct` _(plus 27 more)_

### `sensor_readings.coolant_level`

Fill level of the coolant circuit.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `cnc` |
| Example | _none observed_ |
| Mappings | 34 (6 confirmed) |
| OEM coverage | `haas`, `siemens` |

Mapped from: `coolantLevelActual`, `CoolingFluidLevel`, `COOLING_FLUID_LEVEL`, `CoolingFluidLevelActual`, `CoolantLevelActual`, `Cooling Fluid Level`, `coolingFluidLevelActual`, `coolant_level_actual`, `coolingfluidlevel`, `coolant_level[pct]` _(plus 24 more)_

### `axes.x_temperature`

Temperature of a machine axis.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `cnc` |
| Example | _none observed_ |
| Mappings | 31 (1 confirmed) |
| OEM coverage | `fanuc` |

Mapped from: `xAxisTemperatureActual`, `x_servo_temp_act`, `x_servo_temp`, `x_servo_temp_actual`, `servo_temp_x`, `XAxisTemperatureActual`, `xAxisTemperature`, `XAxisTemperatureC`, `X Axis Temperature (c)`, `X_AXIS_TEMPERATURE` _(plus 21 more)_

### `axes.y_temperature`

Temperature of a machine axis.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `cnc` |
| Example | _none observed_ |
| Mappings | 31 (1 confirmed) |
| OEM coverage | `fanuc` |

Mapped from: `Y_AXIS_TEMPERATURE`, `Y_AXIS_TEMPERATURE_ACT`, `servo_temp_y`, `Y Axis Temperature (c)`, `y_axis_temperature_act`, `YAxisTemperature`, `yServoTempActual`, `YAxisTemperatureC`, `YAxisTemperatureActual`, `yservotemp` _(plus 21 more)_

### `axes.z_temperature`

Temperature of a machine axis.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `cnc` |
| Example | _none observed_ |
| Mappings | 31 (1 confirmed) |
| OEM coverage | `fanuc` |

Mapped from: `servo_temp_z`, `zAxisTemperatureAct`, `ZAxisTemperatureC`, `z_servo_temp_act`, `zAxisTemperature`, `z_servo_temp`, `z_axis_temperature_actual`, `z_axis_temperature[c]`, `Z_AXIS_TEMPERATURE_ACT`, `Z Servo Temp` _(plus 21 more)_

### `axes.x_position`

Position of a machine axis.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `cnc` |
| Example | _none observed_ |
| Mappings | 9 (9 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `actual_position_x`, `pos_x_act`, `X1_Pos`, `axis_x_pos`, `X_Position`, `XAxisPos`, `xpos_actual`, `X_ActualPos`, `X1_ActualPosition`

### `axes.y_position`

Position of a machine axis.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `cnc` |
| Example | _none observed_ |
| Mappings | 9 (9 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `actual_position_y`, `Y1_Pos`, `ypos_actual`, `YAxisPos`, `Y_ActualPos`, `axis_y_pos`, `Y_Position`, `pos_y_act`, `Y1_ActualPosition`

### `axes.z_position`

Position of a machine axis.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `cnc` |
| Example | _none observed_ |
| Mappings | 9 (9 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `ZAxisPos`, `actual_position_z`, `Z1_Pos`, `axis_z_pos`, `pos_z_act`, `Z1_ActualPosition`, `Z_ActualPos`, `zpos_actual`, `Z_Position`

### `cnc.path.feedrate`

Reported value for feedrate.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `cnc` |
| Example | _none observed_ |
| Mappings | 9 (9 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `path_feed_rate`, `PathFeedrate`, `feed_mm_s`, `path_feedrate`, `feedrate_mms`, `feedrate_actual`, `feed_mmps`, `programmed_feedrate`, `path_feed_mm_s`

### `machining_state`

Reported state of the machine.

| | |
|---|---|
| Type | `string` (inferred_from_name) |
| Unit | _none recorded_ (none) |
| Vertical | `cnc` |
| Example | _none observed_ |
| Mappings | 9 (9 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `machining_mode`, `cutting_state`, `process_state`, `machine_state`, `Machining_Process`, `operation_state`, `run_state`, `cycle_state`, `MachiningStatus`

### `spindle_position`

Position of the spindle.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `cnc` |
| Example | _none observed_ |
| Mappings | 8 (8 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `sp_position`, `spindle_pos`, `S1_CommandPosition`, `spindle_angle`, `C_axis_position`, `S_Position`, `S1_ActualPosition`, `SpindlePosition`

### `spindle_temperature`

Temperature of the spindle.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `cnc` |
| Example | _none observed_ |
| Mappings | 8 (8 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `SpindleMotorTemp`, `SP_TEMP`, `MTR_TEMP_SP`, `motor_temperature_spindle`, `sp_motor_temp`, `spindle_temp_c`, `S1_Temperature`, `spindle_motor_temp`

### `axes.x_current_amps`

Electrical current drawn by a machine axis.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `cnc` |
| Example | _none observed_ |
| Mappings | 7 (7 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `servo_current_x`, `X_Current`, `X1_OutputCurrent`, `motor_current_x`, `x_output_current`, `x_current`, `drive_current_x`

### `axes.x_power_kw`

Power draw of a machine axis, in kW.

| | |
|---|---|
| Type | `float` (inferred_from_unit) |
| Unit | `kW` (derived) |
| Vertical | `cnc` |
| Example | _none observed_ |
| Mappings | 7 (7 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `servo_power_x`, `motor_power_x`, `x_output_power`, `axis_power_x`, `x_motor_power`, `X1_OutputPower`, `X_Power`

### `axes.x_velocity`

Velocity of a machine axis.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `cnc` |
| Example | _none observed_ |
| Mappings | 7 (7 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `ActualVelocity_X`, `X_Velocity`, `x_vel_actual`, `axis_velocity_x`, `X1_ActualVelocity`, `vel_act_x`, `servo_vel_x`

### `axes.x_voltage`

Voltage at a machine axis.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `cnc` |
| Example | _none observed_ |
| Mappings | 7 (7 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `motor_voltage_x`, `X_Voltage`, `x_output_voltage`, `X1_OutputVoltage`, `X1_DCBusVoltage`, `drive_voltage_x`, `x_voltage`

### `axes.y_current_amps`

Electrical current drawn by a machine axis.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `cnc` |
| Example | _none observed_ |
| Mappings | 7 (7 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `Y1_OutputCurrent`, `Y_Current`, `motor_current_y`, `servo_current_y`, `drive_current_y`, `y_current`, `y_output_current`

### `axes.y_power_kw`

Power draw of a machine axis, in kW.

| | |
|---|---|
| Type | `float` (inferred_from_unit) |
| Unit | `kW` (derived) |
| Vertical | `cnc` |
| Example | _none observed_ |
| Mappings | 7 (7 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `servo_power_y`, `y_motor_power`, `motor_power_y`, `Y1_OutputPower`, `Y_Power`, `y_output_power`, `axis_power_y`

### `axes.y_velocity`

Velocity of a machine axis.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `cnc` |
| Example | _none observed_ |
| Mappings | 7 (7 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `servo_vel_y`, `vel_act_y`, `y_vel_actual`, `ActualVelocity_Y`, `Y1_ActualVelocity`, `Y_Velocity`, `axis_velocity_y`

### `axes.y_voltage`

Voltage at a machine axis.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `cnc` |
| Example | _none observed_ |
| Mappings | 7 (7 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `Y1_OutputVoltage`, `drive_voltage_y`, `Y1_DCBusVoltage`, `y_output_voltage`, `motor_voltage_y`, `Y_Voltage`, `y_voltage`

### `axes.z_current_amps`

Electrical current drawn by a machine axis.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `cnc` |
| Example | _none observed_ |
| Mappings | 7 (7 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `Z_Current`, `z_current`, `drive_current_z`, `motor_current_z`, `Z1_OutputCurrent`, `servo_current_z`, `z_output_current`

### `axes.z_power_kw`

Power draw of a machine axis, in kW.

| | |
|---|---|
| Type | `float` (inferred_from_unit) |
| Unit | `kW` (derived) |
| Vertical | `cnc` |
| Example | _none observed_ |
| Mappings | 7 (7 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `z_output_power`, `z_motor_power`, `Z1_OutputPower`, `motor_power_z`, `axis_power_z`, `servo_power_z`, `Z_Power`

### `axes.z_velocity`

Velocity of a machine axis.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `cnc` |
| Example | _none observed_ |
| Mappings | 7 (7 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `ActualVelocity_Z`, `Z_Velocity`, `vel_act_z`, `servo_vel_z`, `Z1_ActualVelocity`, `axis_velocity_z`, `z_vel_actual`

### `axes.z_voltage`

Voltage at a machine axis.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `cnc` |
| Example | _none observed_ |
| Mappings | 7 (7 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `motor_voltage_z`, `Z1_DCBusVoltage`, `z_voltage`, `z_output_voltage`, `Z_Voltage`, `Z1_OutputVoltage`, `drive_voltage_z`

### `spindle_voltage`

Voltage at the spindle.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `cnc` |
| Example | _none observed_ |
| Mappings | 7 (7 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `S1_DCBusVoltage`, `S_Voltage`, `sp_voltage`, `SpindleVoltage`, `spindle_motor_voltage`, `spindle_bus_voltage`, `S1_OutputVoltage`

### `tool_condition`

Reported value for tool condition.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `cnc` |
| Example | _none observed_ |
| Mappings | 7 (7 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `tool_status`, `tool_condition`, `tool_wear_state`, `tool_state`, `cutter_condition`, `tool_health`, `ToolCondition`

### `tool_number`

Reported value for tool number.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `cnc` |
| Example | _none observed_ |
| Mappings | 7 (7 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `tool_in_spindle`, `T_number`, `active_tool`, `TOOL_NO`, `ToolNumber`, `current_tool`, `tool_id`

### `workholding_pressure`

Pressure in the machine.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `cnc` |
| Example | _none observed_ |
| Mappings | 7 (7 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `clamp_force_psi`, `hydraulic_clamp_pressure`, `vise_pressure`, `WorkholdingPressure`, `fixture_pressure`, `clamping_force`, `clamp_pressure`

### `axes.x_velocity_commanded`

Velocity of a machine axis.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `cnc` |
| Example | _none observed_ |
| Mappings | 6 (6 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `X1_CommandVelocity`, `cmd_velocity_x`, `x_velocity_command`, `X_Velocity_Command`, `x_vel_cmd`, `X_CmdVelocity`

### `axes.y_velocity_commanded`

Velocity of a machine axis.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `cnc` |
| Example | _none observed_ |
| Mappings | 6 (6 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `cmd_velocity_y`, `Y_Velocity_Command`, `y_vel_cmd`, `Y1_CommandVelocity`, `Y_CmdVelocity`, `y_velocity_command`

### `axes.z_velocity_commanded`

Velocity of a machine axis.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `cnc` |
| Example | _none observed_ |
| Mappings | 6 (6 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `Z1_CommandVelocity`, `Z_Velocity_Command`, `z_velocity_command`, `Z_CmdVelocity`, `cmd_velocity_z`, `z_vel_cmd`

### `cnc.axis.load`

Load on the machine.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `cnc` |
| Example | _none observed_ |
| Mappings | 6 (6 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `AxisLoad`, `axis_load_pct`, `axis_servo_load`, `AxisLoad_X`, `servo_load`, `axis_load`

### `cnc.coolant.pressure`

Pressure in the coolant circuit.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `cnc` |
| Example | _none observed_ |
| Mappings | 6 (6 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `flood_coolant_pressure`, `coolant_press`, `CoolantPress`, `coolant_supply_pressure`, `coolant_pressure`, `CoolantPressure`

### `coolant_status`

Reported value for coolant status.

| | |
|---|---|
| Type | `string` (inferred_from_name) |
| Unit | _none recorded_ (none) |
| Vertical | `cnc` |
| Example | _none observed_ |
| Mappings | 6 (6 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `coolant_on_off`, `COOL_ON`, `coolant_mode`, `coolant_state`, `coolant_enabled`, `CoolantStatus`

### `spindle_current_amps`

Electrical current drawn by the spindle.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `cnc` |
| Example | _none observed_ |
| Mappings | 6 (6 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `sp_current`, `S_Current`, `S1_OutputCurrent`, `spindle_output_current`, `spindle_motor_current`, `SpindleCurrent`

### `spindle_inertia`

Reported value for spindle inertia.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `cnc` |
| Example | _none observed_ |
| Mappings | 6 (6 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `SpindleInertia`, `motor_inertia`, `spindle_inertia`, `system_inertia`, `inertia_ratio`, `S1_SystemInertia`

### `spindle_power_kw`

Power draw of the spindle, in kW.

| | |
|---|---|
| Type | `float` (inferred_from_unit) |
| Unit | `kW` (derived) |
| Vertical | `cnc` |
| Example | _none observed_ |
| Mappings | 6 (6 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `spindle_motor_power`, `spindle_output_power`, `S1_OutputPower`, `S_Power`, `sp_power`, `SpindleOutputPower`

### `axes.x_acceleration`

Ratio for a machine axis.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `cnc` |
| Example | _none observed_ |
| Mappings | 5 (5 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `X1_ActualAcceleration`, `X_Acceleration`, `x_axis_accel`, `x_accel`, `accel_act_x`

### `axes.x_acceleration_commanded`

Ratio for a machine axis.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `cnc` |
| Example | _none observed_ |
| Mappings | 5 (5 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `x_accel_cmd`, `cmd_acceleration_x`, `X1_CommandAcceleration`, `x_acceleration_command`, `X_CmdAcceleration`

### `axes.y_acceleration`

Ratio for a machine axis.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `cnc` |
| Example | _none observed_ |
| Mappings | 5 (5 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `Y_Acceleration`, `accel_act_y`, `Y1_ActualAcceleration`, `y_axis_accel`, `y_accel`

### `axes.y_acceleration_commanded`

Ratio for a machine axis.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `cnc` |
| Example | _none observed_ |
| Mappings | 5 (5 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `Y1_CommandAcceleration`, `y_accel_cmd`, `Y_CmdAcceleration`, `cmd_acceleration_y`, `y_acceleration_command`

### `axes.z_acceleration`

Ratio for a machine axis.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `cnc` |
| Example | _none observed_ |
| Mappings | 5 (5 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `z_axis_accel`, `accel_act_z`, `z_accel`, `Z_Acceleration`, `Z1_ActualAcceleration`

### `axes.z_acceleration_commanded`

Ratio for a machine axis.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `cnc` |
| Example | _none observed_ |
| Mappings | 5 (5 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `z_acceleration_command`, `z_accel_cmd`, `cmd_acceleration_z`, `Z_CmdAcceleration`, `Z1_CommandAcceleration`

### `cnc.spindle.rotary_velocity`

Velocity of the spindle.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `cnc` |
| Example | _none observed_ |
| Mappings | 4 (4 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `Rotational speed [rpm]`, `Rotational speed`, `rotational_speed_rpm`, `rotational_speed`

### `axes.a_load_pct`

Load on a machine axis, in %.

| | |
|---|---|
| Type | `float` (inferred_from_unit) |
| Unit | `%` (derived) |
| Vertical | `cnc` |
| Example | _none observed_ |
| Mappings | 3 (3 confirmed) |
| OEM coverage | `fanuc`, `haas`, `siemens` |

Mapped from: `AXIS_A_LOAD`, `AxisLoad_A`, `servo_load_a`

### `axes.b_load_pct`

Load on a machine axis, in %.

| | |
|---|---|
| Type | `float` (inferred_from_unit) |
| Unit | `%` (derived) |
| Vertical | `cnc` |
| Example | _none observed_ |
| Mappings | 3 (3 confirmed) |
| OEM coverage | `fanuc`, `haas`, `siemens` |

Mapped from: `servo_load_b`, `AXIS_B_LOAD`, `AxisLoad_B`

### `axes.x_current`

Electrical current drawn by a machine axis.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `cnc` |
| Example | _none observed_ |
| Mappings | 2 (2 confirmed) |
| OEM coverage | `heidenhain` |

Mapped from: `AchseX_Strom`, `MotorStrom`

### `axes.a_position_actual`

Position of a machine axis.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `cnc` |
| Example | _none observed_ |
| Mappings | 1 (1 confirmed) |
| OEM coverage | `fanuc` |

Mapped from: `actual_position_a`

### `axes.b_position_actual`

Position of a machine axis.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `cnc` |
| Example | _none observed_ |
| Mappings | 1 (1 confirmed) |
| OEM coverage | `fanuc` |

Mapped from: `actual_position_b`

### `axes.c_load_pct`

Load on a machine axis, in %.

| | |
|---|---|
| Type | `float` (inferred_from_unit) |
| Unit | `%` (derived) |
| Vertical | `cnc` |
| Example | _none observed_ |
| Mappings | 1 (1 confirmed) |
| OEM coverage | `fanuc` |

Mapped from: `servo_load_c`

### `axes.c_position_actual`

Position of a machine axis.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `cnc` |
| Example | _none observed_ |
| Mappings | 1 (1 confirmed) |
| OEM coverage | `fanuc` |

Mapped from: `actual_position_c`

### `axes.x_following_error`

Reported value for x following error.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `cnc` |
| Example | _none observed_ |
| Mappings | 1 (1 confirmed) |
| OEM coverage | `siemens` |

Mapped from: `FollowingError_X`

### `axes.y_following_error`

Reported value for y following error.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `cnc` |
| Example | _none observed_ |
| Mappings | 1 (1 confirmed) |
| OEM coverage | `siemens` |

Mapped from: `FollowingError_Y`

### `axes.z_following_error`

Reported value for z following error.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `cnc` |
| Example | _none observed_ |
| Mappings | 1 (1 confirmed) |
| OEM coverage | `siemens` |

Mapped from: `FollowingError_Z`

## Robotics (`robotics`)

53 fields.

### `sensor_readings.tcp_speed`

Speed of the robot tool centre point.

| | |
|---|---|
| Type | `float` (observed) |
| Unit | _none recorded_ (none) |
| Vertical | `robotics` |
| Example | `250.0` |
| Mappings | 152 (152 confirmed) |
| OEM coverage | `fanuc`, `kuka` |

Mapped from: `EE_SPEED [mm/s]`, `TCPSpeed (in/s)`, `path speed`, `$vel_act (mm/s)`, `Tool Speed`, `$VEL_ACT (m/s)`, `EE_SPEED (in/s)`, `TCP SPEED(m/s)`, `TCP_Speed (m/s)`, `$VELACT(m/s)` _(plus 142 more)_

### `robot.joint.position`

Position of a robot joint.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `robotics` |
| Example | _none observed_ |
| Mappings | 33 (33 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `q_actual`, `joint6_position`, `axis_act_pos`, `rax_3`, `rax_2`, `abb_jointtarget`, `j6_position`, `joint_position`, `joint_angles_rad`, `$AXIS_ACT` _(plus 23 more)_

### `robot.tcp.pose`

Reported value for pose.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `robotics` |
| Example | _none observed_ |
| Mappings | 24 (24 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `cartesian_pose`, `tcp_rx`, `tcp_trans_abb`, `actual_TCP_pose`, `tcp_pos_act`, `tcp_y`, `tcp_z`, `tcp_pose`, `TCP_Pose`, `abb_cartesian_pose` _(plus 14 more)_

### `robot.joint.effort`

Reported value for effort.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `robotics` |
| Example | _none observed_ |
| Mappings | 18 (18 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `actual_joint_torque`, `effort`, `abb_axis_torque`, `abb_motor_torque`, `kuka_axis_torque`, `joint_effort_nm`, `GetMotorTorque`, `axis_torque_act`, `actuator_effort`, `joint_effort_measured` _(plus 8 more)_

### `robot.joint.temperature`

Temperature of a robot joint.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `robotics` |
| Example | _none observed_ |
| Mappings | 18 (18 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `j2_temp`, `joint5_temperature`, `joint_temperature`, `JointTemp`, `j3_temp`, `joint_temp`, `j4_temp`, `j1_temp`, `joint3_temperature`, `j5_temp` _(plus 8 more)_

### `robot.tcp.speed`

Speed of the robot tool centre point.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `robotics` |
| Example | _none observed_ |
| Mappings | 15 (15 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `$VEL_ACT`, `tool_center_point_speed`, `tcp_velocity_abb`, `tcp_velocity`, `abb_cartesian_speed`, `kuka_tcp_velocity`, `cartesian_speed`, `target_TCP_speed`, `tool_speed`, `tcp_speed` _(plus 5 more)_

### `robot.safety.protective_stop`

Reported value for protective stop.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `robotics` |
| Example | _none observed_ |
| Mappings | 14 (14 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `kuka_safety_stop`, `$ALARM_STOP`, `alarm_stop_kuka`, `$STOPMESS`, `ctrl_state_abb`, `robot_protective_stop`, `CtrlState`, `is_protective_stopped`, `abb_emergencystop`, `protective_stop_active` _(plus 4 more)_

### `robot.joint.current`

Electrical current drawn by a robot joint.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `robotics` |
| Example | _none observed_ |
| Mappings | 12 (12 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `JointCurrent`, `abb_motor_current`, `axis_current_act`, `actuator_current`, `actual_current`, `curr_act_kuka`, `joint_current`, `motor_current_abb`, `$CURR_ACT`, `robot_motor_current` _(plus 2 more)_

### `robot.mode`

Reported value for mode.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `robotics` |
| Example | _none observed_ |
| Mappings | 12 (12 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `$MODE_OP`, `OpMode`, `mode_op_kuka`, `robot_mode`, `robot_run_state`, `opmode_abb`, `robot_state`, `RobotMode`, `robot_operating_mode`, `abb_operating_mode` _(plus 2 more)_

### `robot.joint.velocity`

Velocity of a robot joint.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `robotics` |
| Example | _none observed_ |
| Mappings | 11 (11 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `vel_axis_act`, `axis_velocity_act`, `joint_velocity`, `JointVelocity`, `joint_velocities`, `actual_qd`, `kuka_axis_velocity`, `target_qd`, `joint_angular_rate`, `$VEL_AXIS_ACT` _(plus 1 more)_

### `robot.program.state`

Reported state of the machine.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `robotics` |
| Example | _none observed_ |
| Mappings | 10 (10 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `program_state`, `robot_program_state`, `program_execution_state`, `RuntimeState`, `programState`, `program_run_state`, `ProgramState`, `prog_state`, `ur_program_state`, `runtime_state`

### `robot.speed_scaling`

Speed of the machine.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `robotics` |
| Example | _none observed_ |
| Mappings | 8 (8 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `controller_speed_scaling`, `speed_scaling`, `target_speed_fraction`, `speed_fraction`, `speedScaling`, `speed_scale_factor`, `ur_speed_scaling`, `motion_speed_scaling`

### `robot.payload`

Load on the machine.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `robotics` |
| Example | _none observed_ |
| Mappings | 7 (7 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `robot_payload_mass`, `tool_payload`, `carried_payload`, `PayloadMass`, `payload_mass`, `payload`, `payload_kg`

### `robot.safety.mode`

Reported value for mode.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `robotics` |
| Example | _none observed_ |
| Mappings | 7 (7 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `safety_operating_mode`, `robot_safety_mode`, `safetyMode`, `ur_safety_mode`, `safety_mode`, `safety_controller_mode`, `SafetyMode`

### `robot.tool.current`

Electrical current drawn by the machine.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `robotics` |
| Example | _none observed_ |
| Mappings | 7 (7 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `end_effector_current`, `ur_tool_current`, `tool_output_current`, `tool_io_current`, `tool_current`, `toolCurrent`, `tool_connector_current`

### `ros.battery_pct`

Reported value for battery pct, in %.

| | |
|---|---|
| Type | `float` (inferred_from_unit) |
| Unit | `%` (derived) |
| Vertical | `robotics` |
| Example | _none observed_ |
| Mappings | 7 (7 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `bat_lvl`, `battery_pct`, `battery_percentage`, `robot_battery`, `batt_pct`, `BatteryLevel`, `battery_level`

### `ros.motor_temp_c`

Temperature of the motor, in degC.

| | |
|---|---|
| Type | `float` (inferred_from_unit) |
| Unit | `degC` (derived) |
| Vertical | `robotics` |
| Example | _none observed_ |
| Mappings | 7 (7 confirmed) |
| OEM coverage | `haas` |

Mapped from: `motor_temperature`, `actuator_temp`, `weird_motor_temp_for_retrain_test`, `drive_temp`, `motor_temp_celsius`, `motor_temp`, `MotorTemp`

### `robot.tcp.force`

Force applied by the robot tool centre point.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `robotics` |
| Example | _none observed_ |
| Mappings | 6 (6 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `cartesian_force`, `tcp_force`, `tcp_wrench`, `tcp_contact_force`, `actual_TCP_force`, `TCP_Force`

### `ros.battery_current`

Electrical current drawn by the battery.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `robotics` |
| Example | _none observed_ |
| Mappings | 6 (6 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `current_draw`, `BatteryCurrent`, `bat_current`, `battery_amps`, `battery_current`, `ibat`

### `ros.battery_voltage`

Voltage at the battery.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `robotics` |
| Example | _none observed_ |
| Mappings | 6 (6 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `vbat`, `voltage_battery`, `battery_voltage`, `battery_volts`, `BatteryVoltage`, `bat_voltage`

### `ros.end_effector_torque`

Torque on the machine.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `robotics` |
| Example | _none observed_ |
| Mappings | 6 (6 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `tool_torque`, `ee_torque`, `tcp_torque`, `gripper_torque`, `EndEffectorTorque`, `end_effector_torque`

### `ros.joint_1_position`

Position of a robot joint.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `robotics` |
| Example | _none observed_ |
| Mappings | 6 (6 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `j1_rad`, `j1_pos`, `joint_1_position`, `joint1_angle`, `axis_1_position`, `Joint1Position`

### `ros.joint_1_torque`

Torque on a robot joint.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `robotics` |
| Example | _none observed_ |
| Mappings | 6 (6 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `joint1_load`, `j1_torque`, `axis_1_torque`, `Joint1Torque`, `joint_1_torque`, `j1_effort`

### `ros.joint_2_position`

Position of a robot joint.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `robotics` |
| Example | _none observed_ |
| Mappings | 6 (6 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `Joint2Position`, `j2_rad`, `j2_pos`, `joint2_angle`, `joint_2_position`, `axis_2_position`

### `ros.joint_2_torque`

Torque on a robot joint.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `robotics` |
| Example | _none observed_ |
| Mappings | 6 (6 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `axis_2_torque`, `Joint2Torque`, `joint_2_torque`, `j2_torque`, `j2_effort`, `joint2_load`

### `ros.joint_3_position`

Position of a robot joint.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `robotics` |
| Example | _none observed_ |
| Mappings | 6 (6 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `j3_rad`, `j3_pos`, `joint_3_position`, `joint3_angle`, `axis_3_position`, `Joint3Position`

### `ros.joint_3_torque`

Torque on a robot joint.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `robotics` |
| Example | _none observed_ |
| Mappings | 6 (6 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `j3_effort`, `Joint3Torque`, `j3_torque`, `joint3_load`, `axis_3_torque`, `joint_3_torque`

### `ros.joint_4_position`

Position of a robot joint.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `robotics` |
| Example | _none observed_ |
| Mappings | 6 (6 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `joint4_angle`, `j4_pos`, `j4_rad`, `Joint4Position`, `axis_4_position`, `joint_4_position`

### `ros.joint_4_torque`

Torque on a robot joint.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `robotics` |
| Example | _none observed_ |
| Mappings | 6 (6 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `Joint4Torque`, `joint4_load`, `axis_4_torque`, `j4_torque`, `j4_effort`, `joint_4_torque`

### `ros.joint_5_position`

Position of a robot joint.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `robotics` |
| Example | _none observed_ |
| Mappings | 6 (6 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `axis_5_position`, `j5_pos`, `joint_5_position`, `j5_rad`, `Joint5Position`, `joint5_angle`

### `ros.joint_5_torque`

Torque on a robot joint.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `robotics` |
| Example | _none observed_ |
| Mappings | 6 (6 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `j5_torque`, `j5_effort`, `joint5_load`, `Joint5Torque`, `axis_5_torque`, `joint_5_torque`

### `ros.joint_6_position`

Position of a robot joint.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `robotics` |
| Example | _none observed_ |
| Mappings | 6 (6 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `Joint6Position`, `axis_6_position`, `joint_6_position`, `j6_rad`, `joint6_angle`, `j6_pos`

### `ros.joint_6_torque`

Torque on a robot joint.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `robotics` |
| Example | _none observed_ |
| Mappings | 6 (6 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `axis_6_torque`, `j6_torque`, `Joint6Torque`, `j6_effort`, `joint6_load`, `joint_6_torque`

### `ros.localization_confidence`

Identifier of the machine.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `robotics` |
| Example | _none observed_ |
| Mappings | 6 (6 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `slam_confidence`, `LocalizationConfidence`, `localization_confidence`, `pose_confidence`, `amcl_confidence`, `loc_confidence`

### `ros.nav2_recovery_count`

Count of the machine.

| | |
|---|---|
| Type | `integer` (inferred_from_name) |
| Unit | _none recorded_ (none) |
| Vertical | `robotics` |
| Example | _none observed_ |
| Mappings | 6 (6 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `nav_recoveries`, `nav2_recovery_count`, `navigation_recoveries`, `replan_count`, `Nav2Recoveries`, `recovery_count`

### `ros.task_id`

Identifier of the machine.

| | |
|---|---|
| Type | `integer` (inferred_from_name) |
| Unit | _none recorded_ (none) |
| Vertical | `robotics` |
| Example | _none observed_ |
| Mappings | 6 (6 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `TaskID`, `current_task`, `task_handle`, `active_task_id`, `task_id`, `job_id`

### `ros.task_status`

Reported value for task status.

| | |
|---|---|
| Type | `string` (inferred_from_name) |
| Unit | _none recorded_ (none) |
| Vertical | `robotics` |
| Example | _none observed_ |
| Mappings | 6 (6 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `task_state`, `job_status`, `current_task_status`, `execution_status`, `task_status`, `TaskStatus`

### `ros.uptime_seconds`

Reported value for uptime seconds.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `robotics` |
| Example | _none observed_ |
| Mappings | 6 (6 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `Uptime`, `robot_uptime`, `uptime_s`, `running_time_s`, `uptime_seconds`, `uptime`

### `ros.wifi_signal_dbm`

Reported value for wifi signal dbm.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `robotics` |
| Example | _none observed_ |
| Mappings | 6 (6 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `wifi_signal_dbm`, `WifiSignal`, `rssi_dbm`, `wlan_signal`, `wifi_signal`, `signal_strength`

### `robot.safety.status_bits`

Reported value for status bits.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `robotics` |
| Example | _none observed_ |
| Mappings | 5 (5 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `safety_status_bits`, `SafetyStatus`, `safety_state_bits`, `robot_safety_bits`, `safety_status`

### `ros.camera_fps`

Reported value for camera fps.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `robotics` |
| Example | _none observed_ |
| Mappings | 5 (5 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `CameraFPS`, `cam_fps`, `camera_fps`, `video_fps`, `frame_rate`

### `ros.cycle_count`

Count of the machine.

| | |
|---|---|
| Type | `integer` (inferred_from_name) |
| Unit | _none recorded_ (none) |
| Vertical | `robotics` |
| Example | _none observed_ |
| Mappings | 5 (5 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `cycle_count`, `operation_count`, `cycles_completed`, `robot_cycles`, `CycleCount`

### `ros.end_effector_force`

Force applied by the machine.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `robotics` |
| Example | _none observed_ |
| Mappings | 5 (5 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `tool_force`, `EndEffectorForce`, `ee_force`, `gripper_force`, `end_effector_force`

### `ros.error_description`

Text description of the machine.

| | |
|---|---|
| Type | `string` (inferred_from_name) |
| Unit | _none recorded_ (none) |
| Vertical | `robotics` |
| Example | _none observed_ |
| Mappings | 5 (5 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `error_description`, `diagnostic_msg`, `alarm_description`, `ErrorDescription`, `error_message`

### `ros.imu_drift_rate`

Reported value for imu drift rate.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `robotics` |
| Example | _none observed_ |
| Mappings | 5 (5 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `imu_drift_rate`, `imu_bias_drift`, `imu_drift`, `IMUDrift`, `gyro_drift`

### `ros.lidar_point_density`

Identifier of the machine.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `robotics` |
| Example | _none observed_ |
| Mappings | 5 (5 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `scan_density`, `lidar_point_density`, `lidar_points_per_m2`, `lidar_density`, `LidarPointDensity`

### `ros.path_deviation_m`

Reported value for path deviation m, in m.

| | |
|---|---|
| Type | `float` (inferred_from_unit) |
| Unit | `m` (derived) |
| Vertical | `robotics` |
| Example | _none observed_ |
| Mappings | 5 (5 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `path_deviation`, `path_offset`, `PathDeviation`, `trajectory_error`, `path_deviation_m`

### `ros.payload_kg`

Load on the machine, in kg.

| | |
|---|---|
| Type | `float` (inferred_from_unit) |
| Unit | `kg` (derived) |
| Vertical | `robotics` |
| Example | _none observed_ |
| Mappings | 5 (5 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `PayloadKg`, `current_payload`, `load_kg`, `carried_mass_kg`, `payload_weight`

### `ros.payload_utilization_pct`

Load on the machine, in %.

| | |
|---|---|
| Type | `float` (inferred_from_unit) |
| Unit | `%` (derived) |
| Vertical | `robotics` |
| Example | _none observed_ |
| Mappings | 5 (5 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `PayloadUtilization`, `payload_pct`, `payload_utilization`, `load_factor_pct`, `payload_utilization_pct`

### `ros.sensor_quality_pct`

Reported value for sensor quality pct, in %.

| | |
|---|---|
| Type | `float` (inferred_from_unit) |
| Unit | `%` (derived) |
| Vertical | `robotics` |
| Example | _none observed_ |
| Mappings | 5 (5 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `sensor_health`, `sensor_quality_pct`, `SensorQuality`, `sensor_quality`, `perception_quality`

### `ros.task_completion_rate`

Reported value for task completion rate.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `robotics` |
| Example | _none observed_ |
| Mappings | 5 (5 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `task_success_rate`, `TaskCompletion`, `completion_rate`, `tasks_complete_pct`, `task_completion_rate`

### `ros.error_code`

Code reported by the machine.

| | |
|---|---|
| Type | `string` (inferred_from_name) |
| Unit | _none recorded_ (none) |
| Vertical | `robotics` |
| Example | _none observed_ |
| Mappings | 4 (4 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `diagnostic_code`, `error_code`, `ErrorCode`, `alarm_code`

### `ros.obstacle_distance_m`

Reported value for obstacle distance m, in m.

| | |
|---|---|
| Type | `float` (inferred_from_unit) |
| Unit | `m` (derived) |
| Vertical | `robotics` |
| Example | _none observed_ |
| Mappings | 4 (4 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `nearest_obstacle_m`, `clearance_m`, `min_obstacle_dist`, `obstacle_distance_m`

## Additive manufacturing (`additive`)

6 fields.

### `sensor_readings.hotend_temp`

Temperature of the hotend.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `additive` |
| Example | _none observed_ |
| Mappings | 43 (1 confirmed) |
| OEM coverage | `octoprint` |

Mapped from: `hotendTempActual`, `extruderTempAct`, `nozzle_temperature`, `hotend_temp_actual`, `NozzleTemperature`, `HotendTempC`, `hotend_temp_act`, `nozzletemperature`, `extruder_temp_act`, `ExtruderTemp` _(plus 33 more)_

### `filament_used_cm3`

Reported value for filament used cm3.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `additive` |
| Example | _none observed_ |
| Mappings | 1 (1 confirmed) |
| OEM coverage | `octoprint` |

Mapped from: `filamentVolume`

### `filament_used_mm`

Reported value for filament used mm.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `additive` |
| Example | _none observed_ |
| Mappings | 1 (1 confirmed) |
| OEM coverage | `octoprint` |

Mapped from: `filamentLength`

### `sensor_readings.hotend2_target`

Reported value for hotend2 target.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `additive` |
| Example | _none observed_ |
| Mappings | 1 (1 confirmed) |
| OEM coverage | `octoprint` |

Mapped from: `tool1_target`

### `sensor_readings.hotend2_temp`

Temperature of the hotend.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `additive` |
| Example | _none observed_ |
| Mappings | 1 (1 confirmed) |
| OEM coverage | `octoprint` |

Mapped from: `tool1_actual`

### `sensor_readings.hotend_target`

Reported value for hotend target.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `additive` |
| Example | _none observed_ |
| Mappings | 1 (1 confirmed) |
| OEM coverage | `octoprint` |

Mapped from: `tool0_target`

## Vehicles and off-highway (`vehicle`)

64 fields.

### `vehicle.ambient.air_temp`

Temperature of the vehicle.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `vehicle` |
| Example | _none observed_ |
| Mappings | 12 (12 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `outside_temp`, `outside_ambient_temp`, `ambAirTmp`, `outside_air_temp`, `ambient_air_tmp`, `amb_air_temp`, `AmbientAirTemp`, `ambient_air_temp`, `ambient_air_temperature`, `ambient_temp` _(plus 2 more)_

### `vehicle.brake.primary_air_pressure`

Pressure in the vehicle.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `vehicle` |
| Example | _none observed_ |
| Mappings | 7 (7 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `brake_air_primary`, `service_brake_primary`, `BrkPrimAir`, `brake_primary_pressure`, `BrakeAirPress`, `BrakePress_primary`, `primary_air_pressure`

### `vehicle.engine.demand_torque_pct`

Torque on the vehicle, in %.

| | |
|---|---|
| Type | `float` (inferred_from_unit) |
| Unit | `%` (derived) |
| Vertical | `vehicle` |
| Example | _none observed_ |
| Mappings | 7 (7 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `driver_demand_torque`, `EngineDemandTorquePct`, `dmd_pct_trq`, `demand_torque`, `DrvrDmd_Trq`, `driver_demand_pct_torque`, `demanded_torque_pct`

### `vehicle.engine.intake_manifold_pressure`

Pressure in the vehicle.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `vehicle` |
| Example | _none observed_ |
| Mappings | 7 (7 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `MAP`, `intake_manifold_pressure`, `intake_man_press`, `boost_pressure`, `charge_air_pressure`, `BoostPress`, `manifold_abs_pressure`

### `vehicle.engine.intake_manifold_temp`

Temperature of the vehicle.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `vehicle` |
| Example | _none observed_ |
| Mappings | 7 (7 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `charge_air_temp`, `manifold_air_temp`, `intake_manifold_temp`, `intakeAirTmp`, `boost_air_temp`, `IMT`, `intake_manifold_temperature`

### `vehicle.engine.oil_pressure`

Pressure in the lubrication system.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `vehicle` |
| Example | _none observed_ |
| Mappings | 7 (7 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `oil_press_kpa`, `lube_oil_pressure`, `engine_oil_pressure`, `EngineOilPressure`, `EngOilPress`, `eng_oil_press`, `oil_pressure`

### `vehicle.engine.oil_temp`

Temperature of the lubrication system.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `vehicle` |
| Example | _none observed_ |
| Mappings | 7 (7 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `EngineOilTemp`, `engine_oil_temperature`, `motor_oil_temp`, `eng_oil_temp`, `oil_temp_engine`, `EngOilTemp`, `engine_oil_temp`

### `vehicle.transmission.oil_temp`

Temperature of the lubrication system.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `vehicle` |
| Example | _none observed_ |
| Mappings | 7 (7 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `transmission_fluid_temp`, `transmission_oil_temp`, `atf_temp`, `gearbox_oil_temp`, `TransmissionOilTemp`, `TransOilTemp`, `trans_oil_temp`

### `vehicle.turbocharger.rpm`

Reported value for rpm.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `vehicle` |
| Example | _none observed_ |
| Mappings | 7 (7 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `TurboSpeed`, `turbo_shaft_speed`, `turbo_rpm`, `turbocharger_speed`, `turbocharger_rpm`, `turbo_speed`, `TurboRPM`

### `vehicle.acceleration_x`

Ratio for the vehicle.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `vehicle` |
| Example | _none observed_ |
| Mappings | 6 (6 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `accel_long`, `AccelX`, `longitudinal_accel`, `acceleration_x`, `accel_x`, `ax`

### `vehicle.acceleration_y`

Ratio for the vehicle.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `vehicle` |
| Example | _none observed_ |
| Mappings | 6 (6 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `acceleration_y`, `ay`, `accel_y`, `accel_lat`, `AccelY`, `lateral_accel`

### `vehicle.acceleration_z`

Ratio for the vehicle.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `vehicle` |
| Example | _none observed_ |
| Mappings | 6 (6 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `vertical_accel`, `accel_vert`, `acceleration_z`, `az`, `AccelZ`, `accel_z`

### `vehicle.ambient.barometric_pressure`

Pressure in the vehicle.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `vehicle` |
| Example | _none observed_ |
| Mappings | 6 (6 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `baro_press`, `barometric_pressure`, `BarometricPressure`, `baro_kpa`, `atmospheric_pressure`, `ambient_air_pressure`

### `vehicle.battery_soc_pct`

Reported value for battery soc pct, in %.

| | |
|---|---|
| Type | `float` (inferred_from_unit) |
| Unit | `%` (derived) |
| Vertical | `vehicle` |
| Example | _none observed_ |
| Mappings | 6 (6 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `ev_battery_pct`, `battery_soc_pct`, `state_of_charge`, `soc_pct`, `BatterySOC`, `battery_soc`

### `vehicle.dtc_code`

Code reported by the vehicle.

| | |
|---|---|
| Type | `string` (inferred_from_name) |
| Unit | _none recorded_ (none) |
| Vertical | `vehicle` |
| Example | _none observed_ |
| Mappings | 6 (6 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `dtc_code`, `obd2_code`, `fault_code`, `diagnostic_trouble_code`, `obd_dtc`, `DTCCode`

### `vehicle.engine.actual_torque_pct`

Torque on the vehicle, in %.

| | |
|---|---|
| Type | `float` (inferred_from_unit) |
| Unit | `%` (derived) |
| Vertical | `vehicle` |
| Example | _none observed_ |
| Mappings | 6 (6 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `actual_pct_torque`, `actual_torque`, `actual_engine_torque`, `eng_actual_torque_pct`, `delivered_torque_pct`, `ActEngTrq_pct`

### `vehicle.engine.exhaust_gas_temp`

Temperature of the vehicle.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `vehicle` |
| Example | _none observed_ |
| Mappings | 6 (6 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `egt_pre_turbine`, `EGT`, `exhaust_gas_temperature`, `EGT_bank1`, `ExhaustGasTemp`, `exhaust_gas_temp`

### `vehicle.engine.fuel_rail_pressure`

Pressure in the vehicle.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `vehicle` |
| Example | _none observed_ |
| Mappings | 6 (6 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `fuel_rail_press_mpa`, `FuelRailPress`, `fuel_rail_pressure`, `injection_rail_pressure`, `common_rail_pressure`, `rail_pressure`

### `vehicle.engine.fuel_rate`

Reported value for fuel rate.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `vehicle` |
| Example | _none observed_ |
| Mappings | 6 (6 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `instantaneous_fuel_rate`, `fuel_flow_rate`, `fuel_rate`, `fuel_consumption_rate`, `FuelRate`, `engine_fuel_rate`

### `vehicle.engine.load`

Load on the vehicle.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `vehicle` |
| Example | _none observed_ |
| Mappings | 6 (6 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `engine_load`, `calc_engine_load`, `EngineLoadPct`, `EngineLoad`, `engine_load_pct`, `engine_percent_load`

### `vehicle.engine.throttle_position`

Position of the vehicle.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `vehicle` |
| Example | _none observed_ |
| Mappings | 6 (6 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `ThrottlePos`, `throttle_pct`, `accelerator_pedal_position`, `throttle_position`, `ThrottlePosition`, `pedal_position`

### `vehicle.engine_rpm`

Reported value for engine rpm, in rpm.

| | |
|---|---|
| Type | `float` (inferred_from_unit) |
| Unit | `rpm` (derived) |
| Vertical | `vehicle` |
| Example | _none observed_ |
| Mappings | 6 (6 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `motor_rpm`, `engine_speed`, `engine_rpm`, `rpm`, `tachometer`, `EngineRPM`

### `vehicle.gps_altitude_m`

Reported value for gps altitude m, in m.

| | |
|---|---|
| Type | `float` (inferred_from_unit) |
| Unit | `m` (derived) |
| Vertical | `vehicle` |
| Example | _none observed_ |
| Mappings | 6 (6 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `alt_meters`, `gps_altitude_m`, `GPSAltitude`, `elevation`, `altitude_m`, `altitude`

### `vehicle.gps_longitude`

Reported value for gps longitude.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `vehicle` |
| Example | _none observed_ |
| Mappings | 6 (6 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `lng`, `longitude`, `lon`, `GPSLongitude`, `gps_longitude`, `gps_lon`

### `vehicle.heading_deg`

Reported value for heading deg, in deg.

| | |
|---|---|
| Type | `float` (inferred_from_unit) |
| Unit | `deg` (derived) |
| Vertical | `vehicle` |
| Example | _none observed_ |
| Mappings | 6 (6 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `heading`, `compass_heading`, `yaw_deg`, `HeadingDeg`, `bearing`, `heading_deg`

### `vehicle.speed_kmh`

Speed of the vehicle.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `vehicle` |
| Example | _none observed_ |
| Mappings | 6 (6 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `speed_kmh`, `vehicle_speed`, `km_per_hour`, `speed_kph`, `SpeedKmh`, `kph`

### `vehicle.transmission_gear`

Reported value for transmission gear.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `vehicle` |
| Example | _none observed_ |
| Mappings | 6 (6 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `selected_gear`, `GearPosition`, `current_gear`, `transmission_gear`, `gear`, `trans_gear`

### `vehicle.air_inlet_temp`

Temperature of the vehicle.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `vehicle` |
| Example | _none observed_ |
| Mappings | 5 (5 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `air_inlet_temperature`, `engine_air_inlet_temp`, `ambient_inlet_temp`, `inlet_air_temp`, `air_inlet_temp`

### `vehicle.autonomy_level`

Fill level of the vehicle.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `vehicle` |
| Example | _none observed_ |
| Mappings | 5 (5 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `automation_level`, `AutonomyLevel`, `ad_level`, `autonomy_level`, `sae_level`

### `vehicle.battery_temp_c`

Temperature of the vehicle, in degC.

| | |
|---|---|
| Type | `float` (inferred_from_unit) |
| Unit | `degC` (derived) |
| Vertical | `vehicle` |
| Example | _none observed_ |
| Mappings | 5 (5 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `battery_temperature`, `pack_temp`, `ev_battery_temp`, `battery_temp_c`, `BatteryTemp`

### `vehicle.brake.air_pressure`

Pressure in the vehicle.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `vehicle` |
| Example | _none observed_ |
| Mappings | 5 (5 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `brake_air_pressure`, `service_brake_pressure`, `brake_system_pressure`, `brake_reservoir_pressure`, `air_brake_circuit_pressure`

### `vehicle.brake.secondary_air_pressure`

Pressure in the vehicle.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `vehicle` |
| Example | _none observed_ |
| Mappings | 5 (5 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `secondary_air_pressure`, `BrkSecAir`, `brake_air_secondary`, `brake_secondary_pressure`, `service_brake_secondary`

### `vehicle.brake_pressure_pct`

Pressure in the vehicle, in %.

| | |
|---|---|
| Type | `float` (inferred_from_unit) |
| Unit | `%` (derived) |
| Vertical | `vehicle` |
| Example | _none observed_ |
| Mappings | 5 (5 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `brake_pressure_pct`, `brake_force_pct`, `brake_pressure`, `BrakePressure`, `brake_pct`

### `vehicle.camera_fps`

Reported value for camera fps.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `vehicle` |
| Example | _none observed_ |
| Mappings | 5 (5 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `front_cam_fps`, `DashCamFPS`, `vehicle_cam_fps`, `vehicle_camera_fps`, `image_rate`

### `vehicle.dtc_description`

Text description of the vehicle.

| | |
|---|---|
| Type | `string` (inferred_from_name) |
| Unit | _none recorded_ (none) |
| Vertical | `vehicle` |
| Example | _none observed_ |
| Mappings | 5 (5 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `DTCDescription`, `obd_description`, `dtc_message`, `fault_description`, `dtc_description`

### `vehicle.engine_temp_c`

Temperature of the vehicle, in degC.

| | |
|---|---|
| Type | `float` (inferred_from_unit) |
| Unit | `degC` (derived) |
| Vertical | `vehicle` |
| Example | _none observed_ |
| Mappings | 5 (5 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `EngineTemp`, `coolant_temp`, `ect`, `engine_temperature`, `engine_temp_c`

### `vehicle.fuel_level_pct`

Fill level of the vehicle, in %.

| | |
|---|---|
| Type | `float` (inferred_from_unit) |
| Unit | `%` (derived) |
| Vertical | `vehicle` |
| Example | _none observed_ |
| Mappings | 5 (5 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `fuel_level`, `fuel_level_pct`, `tank_level_pct`, `FuelLevel`, `fuel_pct`

### `vehicle.gps_latitude`

Reported value for gps latitude.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `vehicle` |
| Example | _none observed_ |
| Mappings | 5 (5 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `gps_lat`, `latitude`, `GPSLatitude`, `gps_latitude`, `lat`

### `vehicle.gyro_x`

Reported value for gyro x.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `vehicle` |
| Example | _none observed_ |
| Mappings | 5 (5 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `angular_velocity_x`, `wx`, `GyroX`, `gyro_x`, `roll_rate`

### `vehicle.gyro_y`

Reported value for gyro y.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `vehicle` |
| Example | _none observed_ |
| Mappings | 5 (5 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `wy`, `angular_velocity_y`, `pitch_rate`, `GyroY`, `gyro_y`

### `vehicle.gyro_z`

Reported value for gyro z.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `vehicle` |
| Example | _none observed_ |
| Mappings | 5 (5 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `angular_velocity_z`, `GyroZ`, `wz`, `yaw_rate`, `gyro_z`

### `vehicle.harsh_accel_event`

Reported value for harsh accel event.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `vehicle` |
| Example | _none observed_ |
| Mappings | 5 (5 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `harsh_accel_event`, `rapid_acceleration`, `harsh_acceleration`, `HarshAccel`, `hard_accel`

### `vehicle.harsh_brake_event`

Reported value for harsh brake event.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `vehicle` |
| Example | _none observed_ |
| Mappings | 5 (5 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `hard_brake_event`, `HarshBrake`, `panic_brake`, `harsh_brake_event`, `harsh_brake`

### `vehicle.harsh_cornering_event`

Reported value for harsh cornering event.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `vehicle` |
| Example | _none observed_ |
| Mappings | 5 (5 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `HarshCornering`, `harsh_cornering`, `hard_corner`, `aggressive_turn`, `harsh_cornering_event`

### `vehicle.idle_duration_seconds`

Ratio for the vehicle.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `vehicle` |
| Example | _none observed_ |
| Mappings | 5 (5 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `idle_seconds`, `IdleDuration`, `idle_time`, `idle_duration_seconds`, `stationary_time_s`

### `vehicle.intervention_event`

Reported value for intervention event.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `vehicle` |
| Example | _none observed_ |
| Mappings | 5 (5 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `disengagement`, `intervention_event`, `InterventionEvent`, `driver_intervention`, `manual_takeover`

### `vehicle.lane_deviation_m`

Reported value for lane deviation m, in m.

| | |
|---|---|
| Type | `float` (inferred_from_unit) |
| Unit | `m` (derived) |
| Vertical | `vehicle` |
| Example | _none observed_ |
| Mappings | 5 (5 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `lane_deviation_m`, `LaneDeviation`, `lane_deviation`, `lane_offset`, `cross_track_error`

### `vehicle.lidar_point_count`

Count of the vehicle.

| | |
|---|---|
| Type | `integer` (inferred_from_name) |
| Unit | _none recorded_ (none) |
| Vertical | `vehicle` |
| Example | _none observed_ |
| Mappings | 5 (5 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `lidar_points`, `lidar_point_count`, `LidarPoints`, `lidar_returns`, `scan_points`

### `vehicle.obstacle_distance_m`

Reported value for obstacle distance m, in m.

| | |
|---|---|
| Type | `float` (inferred_from_unit) |
| Unit | `m` (derived) |
| Vertical | `vehicle` |
| Example | _none observed_ |
| Mappings | 5 (5 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `ttc_distance`, `obstacle_distance`, `vehicle_obstacle_distance_m`, `fcw_distance`, `ObstacleDistance`

### `vehicle.odometer_km`

Reported value for odometer km.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `vehicle` |
| Example | _none observed_ |
| Mappings | 5 (5 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `odometer_km`, `odometer`, `mileage_km`, `Odometer`, `total_distance_km`

### `vehicle.radar_target_count`

Count of the vehicle.

| | |
|---|---|
| Type | `integer` (inferred_from_name) |
| Unit | _none recorded_ (none) |
| Vertical | `vehicle` |
| Example | _none observed_ |
| Mappings | 5 (5 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `RadarTargets`, `radar_object_count`, `radar_returns`, `radar_targets`, `radar_target_count`

### `vehicle.speed_mph`

Speed of the vehicle.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `vehicle` |
| Example | _none observed_ |
| Mappings | 5 (5 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `speed_miles`, `SpeedMph`, `speed_mph`, `mph`, `miles_per_hour`

### `vehicle.steering_angle_deg`

Reported value for steering angle deg, in deg.

| | |
|---|---|
| Type | `float` (inferred_from_unit) |
| Unit | `deg` (derived) |
| Vertical | `vehicle` |
| Example | _none observed_ |
| Mappings | 5 (5 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `steer_deg`, `SteeringAngle`, `steering_angle`, `steering_angle_deg`, `wheel_angle`

### `vehicle.throttle_pct`

Reported value for throttle pct, in %.

| | |
|---|---|
| Type | `float` (inferred_from_unit) |
| Unit | `%` (derived) |
| Vertical | `vehicle` |
| Example | _none observed_ |
| Mappings | 5 (5 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `throttle_percentage`, `throttle_pos`, `ThrottlePct`, `accelerator_pct`, `gas_pedal_pct`

### `vehicle.tire_pressure_fl`

Pressure in the vehicle.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `vehicle` |
| Example | _none observed_ |
| Mappings | 5 (5 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `TirePressureFL`, `fl_tire_psi`, `tpms_fl`, `tyre_pressure_fl`, `tire_pressure_fl`

### `vehicle.tire_pressure_fr`

Pressure in the vehicle.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `vehicle` |
| Example | _none observed_ |
| Mappings | 5 (5 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `fr_tire_psi`, `tpms_fr`, `TirePressureFR`, `tyre_pressure_fr`, `tire_pressure_fr`

### `vehicle.tire_pressure_rl`

Pressure in the vehicle.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `vehicle` |
| Example | _none observed_ |
| Mappings | 5 (5 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `tire_pressure_rl`, `TirePressureRL`, `tyre_pressure_rl`, `tpms_rl`, `rl_tire_psi`

### `vehicle.tire_pressure_rr`

Pressure in the vehicle.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `vehicle` |
| Example | _none observed_ |
| Mappings | 5 (5 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `tire_pressure_rr`, `TirePressureRR`, `tpms_rr`, `tyre_pressure_rr`, `rr_tire_psi`

### `vehicle.trip_distance_km`

Reported value for trip distance km.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `vehicle` |
| Example | _none observed_ |
| Mappings | 5 (5 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `trip_meter_km`, `trip_distance_km`, `TripDistance`, `trip_km`, `session_distance`

### `vehicle.v2x_message_count`

Count of the vehicle.

| | |
|---|---|
| Type | `integer` (inferred_from_name) |
| Unit | _none recorded_ (none) |
| Vertical | `vehicle` |
| Example | _none observed_ |
| Mappings | 5 (5 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `v2x_messages`, `v2x_message_count`, `c_v2x_msgs`, `dsrc_count`, `V2XMessages`

### `vehicle.wheel_speed_fl`

Speed of the vehicle.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `vehicle` |
| Example | _none observed_ |
| Mappings | 5 (5 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `wheel_speed_fl`, `wheelspeed_front_left`, `front_left_wheel_speed`, `WheelSpeedFL`, `fl_wheel_rpm`

### `vehicle.wheel_speed_fr`

Speed of the vehicle.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `vehicle` |
| Example | _none observed_ |
| Mappings | 5 (5 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `fr_wheel_rpm`, `front_right_wheel_speed`, `wheel_speed_fr`, `wheelspeed_front_right`, `WheelSpeedFR`

### `vehicle.wheel_speed_rl`

Speed of the vehicle.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `vehicle` |
| Example | _none observed_ |
| Mappings | 5 (5 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `wheel_speed_rl`, `WheelSpeedRL`, `wheelspeed_rear_left`, `rear_left_wheel_speed`, `rl_wheel_rpm`

### `vehicle.wheel_speed_rr`

Speed of the vehicle.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `vehicle` |
| Example | _none observed_ |
| Mappings | 5 (5 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `wheelspeed_rear_right`, `wheel_speed_rr`, `rr_wheel_rpm`, `rear_right_wheel_speed`, `WheelSpeedRR`

## Autonomous mobile robots (`amr`)

10 fields.

### `amr.battery.charge`

Reported value for charge.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `amr` |
| Example | _none observed_ |
| Mappings | 6 (6 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `BatteryCharge`, `battery_charge`, `agv_battery_charge`, `amr_battery_pct`, `battery_state_of_charge`, `batteryCharge`

### `amr.position.theta`

Reported value for theta.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `amr` |
| Example | _none observed_ |
| Mappings | 6 (6 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `amr_pose_theta`, `agv_orientation`, `amr_heading`, `agvPosition.theta`, `agv_yaw`, `agv_theta`

### `amr.battery.charging`

Reported value for charging.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `amr` |
| Example | _none observed_ |
| Mappings | 5 (5 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `is_charging`, `charging_flag`, `agv_charging`, `BatteryCharging`, `battery_charging`

### `amr.battery.voltage`

Voltage at the battery.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `amr` |
| Example | _none observed_ |
| Mappings | 5 (5 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `BatteryVoltageAmr`, `battery_pack_voltage`, `amr_battery_v`, `agv_battery_voltage`, `amr_battery_voltage`

### `amr.position.x`

Reported value for x.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `amr` |
| Example | _none observed_ |
| Mappings | 5 (5 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `amr_map_x`, `agvPosition.x`, `amr_x`, `agv_position_x`, `agv_x`

### `amr.position.y`

Reported value for y.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `amr` |
| Example | _none observed_ |
| Mappings | 5 (5 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `agv_y`, `agvPosition.y`, `amr_map_y`, `agv_position_y`, `amr_y`

### `amr.velocity.angular`

Reported value for angular.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `amr` |
| Example | _none observed_ |
| Mappings | 5 (5 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `agv_rotational_rate`, `agv_omega`, `velocity.omega`, `amr_yaw_rate`, `amr_angular_velocity`

### `amr.velocity.linear`

Reported value for linear.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `amr` |
| Example | _none observed_ |
| Mappings | 5 (5 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `agv_linear_speed`, `amr_linear_velocity`, `agv_vx`, `amr_translational_velocity`, `velocity.vx`

### `amr.operating_mode`

Reported value for operating mode.

| | |
|---|---|
| Type | `string` (inferred_from_name) |
| Unit | _none recorded_ (none) |
| Vertical | `amr` |
| Example | _none observed_ |
| Mappings | 4 (4 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `operatingMode`, `agv_operating_mode`, `AgvMode`, `amr_operating_mode`

### `amr.safety.estop`

Reported value for estop.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `amr` |
| Example | _none observed_ |
| Mappings | 4 (4 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `agv_e_stop`, `agv_estop`, `AgvEStop`, `amr_emergency_stop`

## Universal (cross-vertical) (`universal`)

151 fields.

### `sensor_readings.vibration_x`

Vibration measured on measured vibration.

| | |
|---|---|
| Type | `float` (observed) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | `0.012` |
| Mappings | 229 (229 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `ax (g)`, `xvib (m/s²)`, `x_g (mm/s²)`, `measured_vibration_x_axis`, `accel_x [m/s²]`, `xvib (g)`, `vibration_x`, `ACCELERATION_X (mm/s²)`, `x vib (mm/s²)`, `x accel [m/s²]` _(plus 219 more)_

### `operating_hours`

Cumulative runtime of the machine, in h.

| | |
|---|---|
| Type | `float` (observed) |
| Unit | `h` (derived) |
| Vertical | `universal` |
| Example | `12450.5` |
| Mappings | 227 (227 confirmed) |
| OEM coverage | `fanuc`, `haas`, `siemens` |

Mapped from: `TOTAL_HOURS (h)`, `Meter Hours`, `actual_uptime_hours`, `service_hours [minutes]`, `Total Hours [h]`, `RUNTIME_h`, `Service_Hours (hours)`, `TOTAL_HOURS [h]`, `power_on_time (hrs)`, `OperatingHours (minutes)` _(plus 217 more)_

### `energy_kwh`

Energy consumed by consumed energy, in kWh.

| | |
|---|---|
| Type | `float` (observed) |
| Unit | `kWh` (declared) |
| Vertical | `universal` |
| Example | `1.25` |
| Mappings | 226 (226 confirmed) |
| OEM coverage | `fanuc`, `siemens` |

Mapped from: `ENERGY_CONSUMPTION (J)`, `energy usage [Wh]`, `Consumption Kwh (W)`, `POWER USAGE_kW`, `watt hours_J`, `power_kwh_Wh`, `Energy Kwh(kW)`, `ENERGY CONSUMPTION (J)`, `power kwh(kWh)`, `watthours(Wh)` _(plus 216 more)_

### `alarm_code`

Code reported by the active alarm.

| | |
|---|---|
| Type | `string` (observed) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | `SRVO-062` |
| Mappings | 218 (183 confirmed) |
| OEM coverage | `brother`, `caterpillar`, `dmg_mori`, `fanuc`, `haas`, `heidenhain`, `kuka`, `okuma`, `siemens`, `tornos`, `universal_robots` |

Mapped from: `AlarmCodeActual`, `raw_alm`, `alm`, `Msg No`, `current_fault_id`, `fault_code_act`, `current_alm`, `alarm_code_act`, `act_alm_code`, `KeihouNo` _(plus 208 more)_

### `part_count`

Count of the machine.

| | |
|---|---|
| Type | `integer` (observed) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | `1234` |
| Mappings | 212 (212 confirmed) |
| OEM coverage | `fanuc`, `haas`, `siemens` |

Mapped from: `raw_piece_count`, `PRODUCTION_COUNT [cycles]`, `total_parts`, `PartsMade (parts)`, `units_produced_cycles`, `actual_part_count`, `M30 Count(cycles)`, `act_cycle_count`, `PIECE_COUNT [parts]`, `Units Produced (pcs)` _(plus 202 more)_

### `sensor_readings.total_temp_lpc_outlet`

Temperature of the machine.

| | |
|---|---|
| Type | `float` (observed) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | `642.15` |
| Mappings | 204 (204 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `lpcoutlettemp`, `fanoutlettemp [°C]`, `value_total_temp_lpc`, `lpc_outlet_temperature (°R)`, `Fan_Outlet_Temp [°C]`, `lpcoutlettemp [K]`, `T24 [°R]`, `Sensor_2 [K]`, `meas_T24`, `sensor2(K)` _(plus 194 more)_

### `sensor_readings.total_temp_lpt_outlet`

Temperature of the machine.

| | |
|---|---|
| Type | `float` (observed) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | `1400.6` |
| Mappings | 191 (191 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `Exhaust Temp (K)`, `exhausttemp [°C]`, `sensor 4`, `TURBINE_OUTLET_TEMP (K)`, `sensor 4(°R)`, `TURBINE_OUTLET_TEMP (°R)`, `sensor_4 (°C)`, `LPT_Outlet_Temperature [°R]`, `lpt_outlet_temp_°C`, `value_turbine_outlet_temp` _(plus 181 more)_

### `sensor_readings.total_temp_hpc_outlet`

Temperature of the machine.

| | |
|---|---|
| Type | `float` (observed) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | `1589.7` |
| Mappings | 190 (190 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `HPC_OUTLET_TEMPERATURE (°C)`, `Hpc_Outlet_Temp (°C)`, `SENSOR_3 (K)`, `total_temp_hpc (°C)`, `Compressor Outlet Temp(K)`, `act_total_temp_hpc`, `sensor3(K)`, `Total Temp Hpc (°C)`, `total temp hpc [K]`, `HPC Outlet Temperature (°C)` _(plus 180 more)_

### `sensor_readings.hydraulic_pressure`

Pressure in the hydraulic system.

| | |
|---|---|
| Type | `float` (observed) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | `2000.0` |
| Mappings | 187 (151 confirmed) |
| OEM coverage | `heidenhain`, `komatsu` |

Mapped from: `HYDRAULIC_PRESSURE`, `hyd_pressure[psi]`, `HYD_PRESSURE(kPa)`, `raw_hydraulic_bar`, `hydraulic(bar)`, `hyd pressure (psi)`, `HYDRAULIC_PRESSURE_BAR`, `Hydraulic_PSI_kPa`, `Hydraulic_Bar [MPa]`, `CHUCK_PRESSURE (MPa)` _(plus 177 more)_

### `sensor_readings.pressure_fan_inlet`

Pressure in the machine.

| | |
|---|---|
| Type | `float` (observed) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | `14.62` |
| Mappings | 184 (184 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `Sensor 5 (psia)`, `FanInletPressure(bar)`, `SENSOR_5 [bar]`, `p fan in`, `FanInletPressure [bar]`, `fan inlet pressure_bar`, `SENSOR_5(psia)`, `actual_P2`, `inlet pressure_bar`, `inletpressure(psia)` _(plus 174 more)_

### `alarm_description`

Text description of the active alarm.

| | |
|---|---|
| Type | `string` (observed) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | `BZAL alarm Group 1 Axis 1` |
| Mappings | 179 (137 confirmed) |
| OEM coverage | `abb`, `brother`, `doosan`, `fanuc`, `haas`, `heidenhain`, `komatsu`, `kuka`, `mazak`, `mitsubishi`, `okuma`, `siemens`, `tornos` |

Mapped from: `AlarmMeldung`, `actual_alarm_text`, `alarmTextActual`, `ALARM_DESCRIPTION_ACT`, `meas_fault_description`, `Message`, `cur_alarm_desc`, `errorMessageActual`, `measured_fault_description`, `raw_alarm_text` _(plus 169 more)_

### `sensor_readings.good_parts`

Reported value for good parts.

| | |
|---|---|
| Type | `integer` (observed) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | `1234` |
| Mappings | 176 (140 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `current_good_parts`, `cur_good`, `Good(pcs)`, `raw_pass_count`, `good_parts_act`, `act_good_count`, `cur_ok_parts`, `firstpassgood [pcs]`, `firstpassgood (parts)`, `PassCount [parts]` _(plus 166 more)_

### `sensor_readings.core_speed_rpm`

Speed of the machine, in rpm.

| | |
|---|---|
| Type | `float` (observed) |
| Unit | `rpm` (derived) |
| Vertical | `universal` |
| Example | `9046.19` |
| Mappings | 157 (157 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `SENSOR_9`, `NC`, `core rpm (rpm)`, `raw_sensor_9`, `val_core_rpm`, `n core(rpm)`, `sensor_9(rpm)`, `n core [rpm]`, `Sensor 9_rpm`, `sensor_9 [rpm]` _(plus 147 more)_

### `alarm_severity`

Severity of the active alarm.

| | |
|---|---|
| Type | `string` (observed) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | `CRITICAL` |
| Mappings | 155 (121 confirmed) |
| OEM coverage | `brother`, `fanuc`, `mitsubishi`, `siemens` |

Mapped from: `meas_level`, `current_level`, `alarmSeverityActual`, `actual_priority`, `current_severity`, `current_event_severity`, `ERROR_SEVERITY`, `ALARMKLASSE`, `raw_alarm_severity`, `val_priority` _(plus 145 more)_

### `sensor_readings.air_pressure`

Pressure in the machine.

| | |
|---|---|
| Type | `float` (observed) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | `90.0` |
| Mappings | 154 (154 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `air_pressure(MPa)`, `airbar_psi`, `current_supply_pressure`, `shop air [bar]`, `PNEUMATIC PRESSURE(psi)`, `measured_supply_pressure`, `compressedair [bar]`, `Air Pressure [MPa]`, `AirPressure [bar]`, `compressedair_MPa` _(plus 144 more)_

### `sensor_readings.cycle_time`

Reported value for cycle time.

| | |
|---|---|
| Type | `float` (observed) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | `45.2` |
| Mappings | 154 (154 confirmed) |
| OEM coverage | `fanuc`, `siemens` |

Mapped from: `Cyc Time(s)`, `Cycle_Time_Sec (ms)`, `cycletimesec_sec`, `Cycle_Duration_min`, `cycle_time (sec)`, `Cycle Time Min_sec`, `Cycle Time [s]`, `machining_time_sec`, `value_cycle_time`, `cuttime [ms]` _(plus 144 more)_

### `sensor_readings.fan_speed_rpm`

Speed of the machine, in rpm.

| | |
|---|---|
| Type | `float` (observed) |
| Unit | `rpm` (derived) |
| Vertical | `universal` |
| Example | `2388.06` |
| Mappings | 154 (154 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `val_fan_rpm`, `N Fan_rpm`, `fan speed_rpm`, `fan speed [rpm]`, `N Fan(rpm)`, `act_Nf`, `Physical_Fan_Speed (rpm)`, `measured_sensor_8`, `raw_Nf`, `fanrpm(rpm)` _(plus 144 more)_

### `sensor_readings.voltage`

Voltage at the machine.

| | |
|---|---|
| Type | `integer` (observed) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | `480` |
| Mappings | 154 (154 confirmed) |
| OEM coverage | `fanuc` |

Mapped from: `DCBUSVOLTAGE(VDC)`, `VDC_VDC`, `linevoltage(VDC)`, `Supply Voltage [V]`, `BusVoltage [VAC]`, `SupplyVoltage(V)`, `input_voltage [VDC]`, `BusVoltage_VDC`, `Bus Volt(kV)`, `Dc Voltage_kV` _(plus 144 more)_

### `metadata.controller_model`

Reported value for controller model.

| | |
|---|---|
| Type | `string` (observed) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | `R-30iB` |
| Mappings | 153 (112 confirmed) |
| OEM coverage | `abb`, `fanuc`, `kuka`, `siemens` |

Mapped from: `ControlModelActual`, `current_controller_name`, `CncModel`, `cncModelActual`, `actual_controller_type`, `controller model`, `controllerAct`, `controllerModelActual`, `CONTROL_MODEL_ACT`, `measured_control_unit` _(plus 143 more)_

### `payload_kg`

Load on the machine, in kg.

| | |
|---|---|
| Type | `float` (observed) |
| Unit | `kg` (derived) |
| Vertical | `universal` |
| Example | `5.0` |
| Mappings | 153 (153 confirmed) |
| OEM coverage | `abb`, `fanuc`, `kuka`, `universal_robots` |

Mapped from: `$load (lb)`, `PAYLOADKG_kg`, `PAYLOAD_MASS [g]`, `load_weight_lb`, `val_payload_kg`, `PAYLOAD WEIGHT`, `PAYLOADKG [g]`, `Payload Kg_g`, `PAYLOAD_KG_lbs`, `ToolMass_kg` _(plus 143 more)_

### `execution_state`

Reported state of the machine.

| | |
|---|---|
| Type | `string` (observed) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | `ACTIVE` |
| Mappings | 152 (128 confirmed) |
| OEM coverage | `brother`, `doosan`, `fanuc`, `haas`, `heidenhain`, `hurco`, `mitsubishi`, `siemens` |

Mapped from: `Running State`, `program_execution_actual`, `cur_exec_state`, `programExecutionAct`, `EstadoEjecucion`, `MACHINE STATUS`, `RUNNING_STATE`, `ExecState`, `measured_machine_state`, `running_state` _(plus 142 more)_

### `downtime_minutes`

Reported value for downtime minutes, in min.

| | |
|---|---|
| Type | `integer` (observed) |
| Unit | `min` (declared) |
| Vertical | `universal` |
| Example | `45` |
| Mappings | 151 (151 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `breakdown_time_minutes`, `downtimehrs_sec`, `timetorepair [minutes]`, `breakdowntime (sec)`, `repairtime [min]`, `downtimehrs(minutes)`, `meas_repair_time`, `repair time [min]`, `breakdowntime (minutes)`, `actual_downtime_hrs` _(plus 141 more)_

### `sensor_readings.unplanned_downtime`

Reported value for unplanned downtime.

| | |
|---|---|
| Type | `integer` (observed) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | `12` |
| Mappings | 150 (150 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `FAILURE_TIME_hours`, `UNPLANNED_DT [hours]`, `Failure Time [hrs]`, `Breakdown_Time [hours]`, `val_failure_time`, `UNPLANNED_DT [minutes]`, `act_unplanned_downtime`, `FAILURE_TIME (hrs)`, `unplanneddt(minutes)`, `Unexpected_Downtime [min]` _(plus 140 more)_

### `sensor_readings.planned_downtime`

Reported value for planned downtime.

| | |
|---|---|
| Type | `integer` (observed) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | `30` |
| Mappings | 149 (149 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `planned stop(hours)`, `plannedstop [minutes]`, `changeovertime_minutes`, `planned_dt [hours]`, `current_scheduled_downtime`, `measured_scheduled_downtime`, `actual_planned_dt`, `measured_planned_stop`, `scheduledmaintenance_hours`, `scheduled_downtime(hours)` _(plus 139 more)_

### `serial_number`

Reported value for serial number.

| | |
|---|---|
| Type | `string` (observed) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | `FANUC-M20-0312` |
| Mappings | 149 (108 confirmed) |
| OEM coverage | `fanuc`, `siemens` |

Mapped from: `device_id_actual`, `machineSerialActual`, `equipmentIdAct`, `Robot_Serial`, `equipmentIdActual`, `current_asset_serial`, `raw_robot_serial`, `act_machine_serial`, `measured_asset_serial`, `current_unit_serial` _(plus 139 more)_

### `sensor_readings.power_consumption`

Power draw of electrical power.

| | |
|---|---|
| Type | `float` (observed) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | `12.5` |
| Mappings | 148 (148 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `POWER [kW]`, `measured_power_usage`, `powerkw (kW)`, `Total Power`, `act_power_draw`, `PowerConsumption_HP`, `measured_watts`, `Power Kw(HP)`, `Watts [W]`, `powerusage_W` _(plus 138 more)_

### `sensor_readings.reject_parts`

Reported value for reject parts.

| | |
|---|---|
| Type | `integer` (observed) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | `12` |
| Mappings | 146 (146 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `nok [pcs]`, `meas_bad_parts`, `REJECTS_pcs`, `cur_scrap_count`, `rejected(parts)`, `Bad Parts [pcs]`, `val_fail_count`, `raw_bad_parts`, `Reject_Parts_pcs`, `nonconforming_parts` _(plus 136 more)_

### `sensor_readings.availability`

Reported value for availability.

| | |
|---|---|
| Type | `float` (observed) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | `95.0` |
| Mappings | 145 (145 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `current_availability_pct`, `MACHINE_AVAILABILITY (%)`, `AVAILABLE_TIME_PCT_%`, `availabilitypct [%]`, `Availability_Pct(percent)`, `EQUIPMENT_AVAILABILITY [%]`, `meas_avail`, `uptime pct [percent]`, `availability(%)`, `cur_availability` _(plus 135 more)_

### `sensor_readings.speed_override`

Speed of the machine.

| | |
|---|---|
| Type | `integer` (observed) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | `100` |
| Mappings | 145 (145 confirmed) |
| OEM coverage | `fanuc`, `haas`, `siemens` |

Mapped from: `Velocity Override [percent]`, `velocityoverride (%)`, `feed override [percent]`, `act_speed_ovrd`, `SPD_OVRD(%)`, `SPEED_OVERRIDE`, `act_rapid_override`, `cur_rapid_override`, `Spd_Ovrd [percent]`, `rapid_override_%` _(plus 135 more)_

### `sensor_readings.quality_rate`

Reported value for quality rate.

| | |
|---|---|
| Type | `float` (observed) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | `98.5` |
| Mappings | 144 (144 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `FirstPassYield(percent)`, `measured_fpy`, `yieldpct(%)`, `QUALITY SCORE (%)`, `act_pass_rate`, `QUALITY RATE_%`, `PASS_RATE (%)`, `Yield [percent]`, `measured_quality_rate`, `QualityRate_percent` _(plus 134 more)_

### `model`

Reported value for model.

| | |
|---|---|
| Type | `string` (observed) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | `M-20iA/20M` |
| Mappings | 142 (113 confirmed) |
| OEM coverage | `abb`, `fanuc`, `kuka`, `octoprint`, `siemens`, `universal_robots` |

Mapped from: `value_equipment_model`, `val_model_name`, `MODEL_NUMBER`, `val_device_model`, `act_model_name`, `value_machine_model`, `value_type`, `Robot Type`, `meas_model`, `cur_type` _(plus 132 more)_

### `sensor_readings.performance`

Reported value for performance.

| | |
|---|---|
| Type | `float` (observed) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | `82.0` |
| Mappings | 139 (139 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `PERFORMANCE_RATE_%`, `performance`, `run rate pct(percent)`, `performance_pct (%)`, `val_ideal_cycle_pct`, `Run Rate Pct(%)`, `Ideal Cycle Pct [%]`, `performancepct [%]`, `speed_rate (percent)`, `idealcyclepct_percent` _(plus 129 more)_

### `sensor_readings.oee`

Reported value for oee.

| | |
|---|---|
| Type | `float` (observed) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | `72.5` |
| Mappings | 136 (136 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `oee_pct (percent)`, `OverallEquipmentEffectiveness (%)`, `actual_equipment_effectiveness`, `equipmenteffectiveness_percent`, `oeescore [%]`, `Oee(percent)`, `meas_oee_pct`, `oeescore_%`, `Overall Equipment Effectiveness_%`, `actual_oee` _(plus 126 more)_

### `maintenance_desc`

Reported value for maintenance desc.

| | |
|---|---|
| Type | `string` (observed) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | `Replaced servo motor axis 3` |
| Mappings | 122 (122 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `maintenance_desc`, `cur_service_notes`, `meas_service_notes`, `repair_notes`, `measured_action_taken`, `meas_repair_description`, `maintenance_description`, `act_service_notes`, `Maintenance_Notes`, `measured_service_notes` _(plus 112 more)_

### `timestamp`

Reported value for timestamp.

| | |
|---|---|
| Type | `string` (observed) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | `2024-03-15T14:30:00Z` |
| Mappings | 122 (122 confirmed) |
| OEM coverage | `fanuc`, `siemens` |

Mapped from: `measured_ts`, `current_sample_time`, `value_datetime`, `Rec_Time`, `meas_time`, `value_collection_time`, `value_time`, `cur_dt`, `event time`, `DT` _(plus 112 more)_

### `program_name`

Identifier of the machine.

| | |
|---|---|
| Type | `string` (observed) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | `O0001` |
| Mappings | 118 (118 confirmed) |
| OEM coverage | `fanuc`, `haas`, `siemens` |

Mapped from: `partprogram`, `Gcode_File`, `Part_Program`, `gcodefile`, `cur_nc_program`, `raw_prog_name`, `cur_current_program`, `act_nc_program`, `value_program_name`, `gcode file` _(plus 108 more)_

### `machine_id`

Identifier of the machine.

| | |
|---|---|
| Type | `string` (observed) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | `M01` |
| Mappings | 117 (117 confirmed) |
| OEM coverage | `fanuc`, `haas`, `siemens` |

Mapped from: `Machine_No`, `cnc_id`, `meas_asset_id`, `CNCID`, `Asset ID`, `equipment id`, `Cnc Id`, `MASCHINE_ID`, `raw_machine_number`, `machine name` _(plus 107 more)_

### `metadata.cell_id`

Identifier of the machine.

| | |
|---|---|
| Type | `string` (observed) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | `CELL-01` |
| Mappings | 116 (116 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `cur_station_number`, `raw_work_cell`, `measured_bay`, `value_work_cell`, `value_cell_name`, `meas_bay`, `actual_zone_id`, `cur_zone`, `WorkCell`, `raw_cell_name` _(plus 106 more)_

### `metadata.batch_id`

Identifier of the machine.

| | |
|---|---|
| Type | `string` (observed) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | `BATCH-2024-001` |
| Mappings | 115 (115 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `val_lot_number`, `measured_batch_id`, `value_batch_number`, `cur_batch_number`, `measured_batch`, `act_job_number`, `current_job_number`, `val_lot_no`, `act_work_order`, `current_lot_id` _(plus 105 more)_

### `metadata.plant_id`

Identifier of the machine.

| | |
|---|---|
| Type | `string` (observed) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | `PLANT-OH-01` |
| Mappings | 115 (115 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `measured_facility`, `meas_facility_id`, `measured_site_id`, `raw_plant_code`, `current_facility_id`, `cur_plant_id`, `Plant_ID`, `val_factory_id`, `SITE`, `act_factory` _(plus 105 more)_

### `alarm_severity.alarm_group`

Reported value for alarm group.

| | |
|---|---|
| Type | `string` (observed) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | `SRVO` |
| Mappings | 114 (114 confirmed) |
| OEM coverage | `fanuc`, `siemens` |

Mapped from: `alarmcategory`, `actual_alarm_class_group`, `measured_alarm_group`, `act_alarm_type`, `value_error_group`, `ERRGROUP`, `value_group`, `cur_error_group`, `cur_fault_category`, `Fault Category` _(plus 104 more)_

### `alarm_severity.axis_number`

Reported value for axis number.

| | |
|---|---|
| Type | `string` (observed) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | `1` |
| Mappings | 111 (111 confirmed) |
| OEM coverage | `fanuc`, `siemens` |

Mapped from: `cur_joint_no`, `AFFECTED AXIS`, `Group Axis`, `val_joint_number`, `AXIS_NUMBER`, `group_axis`, `actual_joint_number`, `raw_axis_number`, `value_axis_id`, `act_axis_id` _(plus 101 more)_

### `metadata.technician_id`

Identifier of the machine.

| | |
|---|---|
| Type | `string` (observed) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | `TECH-001` |
| Mappings | 108 (108 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `val_tech_id`, `operator name`, `ASSIGNED_TO`, `Repair_By`, `raw_performed_by`, `cur_maintenance_tech`, `current_service_tech`, `Technician_ID`, `Performed By`, `performedby` _(plus 98 more)_

### `maintenance_type`

Reported value for maintenance type.

| | |
|---|---|
| Type | `string` (observed) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | `PREVENTIVE` |
| Mappings | 105 (105 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `service type`, `current_maintenance_category`, `current_maintenance_type`, `cur_service_category`, `actual_action_type`, `val_pm_type`, `Service Category`, `value_service_category`, `cur_service_type`, `cur_work_type` _(plus 95 more)_

### `sensor_readings.digital_input`

Reported value for digital input.

| | |
|---|---|
| Type | `boolean` (observed) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | `1` |
| Mappings | 103 (103 confirmed) |
| OEM coverage | `fanuc`, `siemens` |

Mapped from: `Io Input`, `cur_di`, `current_digital_input`, `DIGITALEINGANG`, `meas_di`, `DIGITAL_INPUT`, `current_io_input`, `Digital Input`, `value_digital_input`, `ioinput` _(plus 93 more)_

### `sensor_readings.register_value`

Reported value for register value.

| | |
|---|---|
| Type | `float` (observed) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | `125.0` |
| Mappings | 102 (102 confirmed) |
| OEM coverage | `fanuc`, `siemens` |

Mapped from: `R_Value`, `var_value`, `val_reg_val`, `current_reg`, `act_data_register`, `reg_val`, `current_variable`, `R`, `regval`, `meas_r_value` _(plus 92 more)_

### `sensor_readings.digital_output`

Reported value for digital output.

| | |
|---|---|
| Type | `boolean` (observed) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | `1` |
| Mappings | 97 (97 confirmed) |
| OEM coverage | `fanuc`, `siemens` |

Mapped from: `current_io_output`, `meas_binary_output`, `measured_discrete_output`, `DIGITAL_OUT`, `actual_digital_output`, `measured_do`, `current_output_signal`, `cur_discrete_output`, `measured_dout`, `value_do` _(plus 87 more)_

### `operational_settings.setting_2`

Reported value for setting 2.

| | |
|---|---|
| Type | `float` (observed) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | `-0.0004` |
| Mappings | 89 (89 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `OPERATIONAL_SETTING_2`, `Op Setting 2`, `cur_os2`, `operational setting 2`, `Param 2`, `OP_SETTING_2`, `current_param_2`, `param_2`, `cur_setting_2`, `os2` _(plus 79 more)_

### `operational_settings.setting_1`

Reported value for setting 1.

| | |
|---|---|
| Type | `float` (observed) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | `-0.0007` |
| Mappings | 88 (88 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `config 1`, `setting 1`, `Os1`, `cur_param_1`, `OPERATIONAL SETTING 1`, `current_op_setting_1`, `cur_op_setting_1`, `SETTING_1`, `value_os1`, `cur_os1` _(plus 78 more)_

### `metadata.line_id`

Identifier of the machine.

| | |
|---|---|
| Type | `string` (observed) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | `LINE-1` |
| Mappings | 87 (87 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `act_mfg_line`, `raw_line_name`, `actual_line_id`, `Line ID`, `Production Line`, `production_line`, `raw_line_number`, `line_name`, `mfg line`, `current_assembly_line` _(plus 77 more)_

### `metadata.accumulator_pressure`

Pressure in the machine.

| | |
|---|---|
| Type | `integer` (observed) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | `130` |
| Mappings | 80 (80 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `accum pressure (psi)`, `AccumulatorPressure(bar)`, `act_hydraulic_accumulator`, `Accumulator_Bar_psi`, `Acc_Bar_psi`, `accbar (psi)`, `meas_accumulator_pressure`, `AccumulatorPressure [bar]`, `accumpressure [bar]`, `accumulatorbar` _(plus 70 more)_

### `metadata.component`

Reported value for component.

| | |
|---|---|
| Type | `string` (observed) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | `comp1` |
| Mappings | 80 (80 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `current_replaced_component`, `act_replaced_component`, `part`, `measured_part`, `act_part`, `cur_component_name`, `actual_comp`, `cur_comp_id`, `value_replaced_component`, `FAILED_COMPONENT` _(plus 70 more)_

### `metadata.cooler_condition`

Reported value for cooler condition.

| | |
|---|---|
| Type | `integer` (observed) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | `3` |
| Mappings | 80 (80 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `cooler health_%`, `coolerstate_%`, `meas_cooler_condition`, `meas_cooler_pct`, `COOLER_PCT [%]`, `COOLER_PCT(%)`, `cooler pct (%)`, `COOLING_CONDITION`, `value_cooler_pct`, `Cooler_Health` _(plus 70 more)_

### `metadata.machine_age`

Reported value for machine age.

| | |
|---|---|
| Type | `integer` (observed) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | `18` |
| Mappings | 80 (80 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `meas_service_years`, `ageyears(years)`, `val_equipment_age`, `cur_machine_age`, `Machine_Age(years)`, `Age [years]`, `cur_age`, `ageyears`, `years_in_service (months)`, `machine age` _(plus 70 more)_

### `metadata.machine_failure`

Reported value for machine failure.

| | |
|---|---|
| Type | `boolean` (observed) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | `0` |
| Mappings | 80 (80 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `cur_fault_flag`, `machine_failure`, `current_failed`, `val_machine_failure`, `measured_failed`, `current_is_failed`, `measured_Machine failure`, `cur_breakdown`, `actual_breakdown`, `cur_Target` _(plus 70 more)_

### `metadata.product_quality`

Reported value for product quality.

| | |
|---|---|
| Type | `string` (observed) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | `L` |
| Mappings | 80 (80 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `Grade`, `current_material_grade`, `current_grade`, `raw_Type`, `act_Product ID`, `measured_material_grade`, `raw_material_grade`, `meas_grade`, `measured_Product ID`, `act_Type` _(plus 70 more)_

### `metadata.pump_leakage`

Reported value for pump leakage.

| | |
|---|---|
| Type | `integer` (observed) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | `0` |
| Mappings | 80 (80 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `raw_pump_leak`, `cur_pump_leak`, `PUMP_LEAK_ml/min`, `measured_pump_leakage`, `pumpcondition`, `PumpLeakage [ml/min]`, `Leakage`, `measured_pump_condition`, `PUMP_LEAK [ml/min]`, `meas_pump_condition` _(plus 70 more)_

### `metadata.valve_condition`

Reported value for valve condition.

| | |
|---|---|
| Type | `integer` (observed) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | `73` |
| Mappings | 80 (80 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `current_valve_health`, `Valve Health(%)`, `valve condition_%`, `Valve_Pct_%`, `Valve Pct`, `valvestatus`, `Valve State (%)`, `meas_valve_health`, `ValveHealth(%)`, `actual_valve_pct` _(plus 70 more)_

### `sensor_readings.air_temperature`

Temperature of the machine.

| | |
|---|---|
| Type | `float` (observed) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | `298.1` |
| Mappings | 80 (80 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `actual_room_temp`, `roomtemp(°F)`, `Airtemperature[K]_°F`, `Ambient Temp(C)`, `air_temperature_[c]_C`, `air_temperature_[c](K)`, `AirTemperature(°C)`, `Env_Temp (°F)`, `ambienttemp_°C`, `Ambient_°C` _(plus 70 more)_

### `sensor_readings.cooling_efficiency`

Efficiency of the machine.

| | |
|---|---|
| Type | `float` (observed) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | `72.5` |
| Mappings | 80 (80 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `COOLER EFFICIENCY(%)`, `coolereff_%`, `Cool Eff [percent]`, `Cooler_Eff (%)`, `measured_cooler_eff`, `Cooling_Efficiency(percent)`, `CoolingEfficiency [%]`, `val_CE`, `CoolerEfficiency_%`, `COOLER EFFICIENCY (percent)` _(plus 70 more)_

### `sensor_readings.cooling_power`

Power draw of electrical power.

| | |
|---|---|
| Type | `float` (observed) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | `1.41` |
| Mappings | 80 (80 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `meas_cooling_power`, `coolingkw_kW`, `coolpower_W`, `COOLING_KW(kW)`, `Cooling_Power (kW)`, `actual_cooler_power`, `measured_cool_power`, `value_cool_power`, `COOL_POWER(kW)`, `val_cooler_power` _(plus 70 more)_

### `sensor_readings.efficiency_factor`

Efficiency of the machine.

| | |
|---|---|
| Type | `float` (observed) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | `91.5` |
| Mappings | 80 (80 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `meas_SE`, `eff_factor`, `eff_factor(%)`, `EFFICIENCY FACTOR [percent]`, `efficiencypct(percent)`, `EFFICIENCY FACTOR`, `EFFICIENCY FACTOR(%)`, `value_system_efficiency`, `ETA_%`, `value_efficiency_pct` _(plus 70 more)_

### `sensor_readings.pressure`

Pressure in the machine.

| | |
|---|---|
| Type | `float` (observed) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | `113.08` |
| Mappings | 80 (80 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `Pressure Measure (atm)`, `Pressure_Reading [kPa]`, `PressureReading(kPa)`, `Pressure_Measure (bar)`, `system_pressure_atm`, `press_psi`, `Pressure Reading (kPa)`, `Pressure Sensor_atm`, `Pressure Reading_atm`, `Pressure Sensor (Pa)` _(plus 70 more)_

### `sensor_readings.pressure_1`

Pressure in the machine.

| | |
|---|---|
| Type | `float` (observed) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | `155.64` |
| Mappings | 80 (80 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `P1 [kPa]`, `actual_pump_pressure`, `ps1 [kPa]`, `press1_MPa`, `PRESS_1 (psi)`, `cur_system_pressure_1`, `Pressure Sensor 1(MPa)`, `Pressure Sensor 1 (bar)`, `pressure1 [bar]`, `PRESS_1 (bar)` _(plus 70 more)_

### `sensor_readings.pressure_3`

Pressure in the machine.

| | |
|---|---|
| Type | `float` (observed) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | `2.3` |
| Mappings | 80 (80 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `PRESSURE SENSOR 3 (bar)`, `meas_pressure_3`, `press3(psi)`, `PRESSURE SENSOR 3`, `act_P3`, `cur_P3`, `PressureSensor3_psi`, `Pressure_3(psi)`, `Pressure 3 (bar)`, `pressure3(bar)` _(plus 70 more)_

### `sensor_readings.pressure_4`

Pressure in the machine.

| | |
|---|---|
| Type | `float` (observed) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | `0.0` |
| Mappings | 80 (80 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `pressure sensor 4_bar`, `raw_P4`, `value_pressure_sensor_4`, `PressureSensor4(bar)`, `pressure4(psi)`, `PressureSensor4`, `act_pressure_sensor_4`, `pressure 4 [bar]`, `ps4 (psi)`, `act_P4` _(plus 70 more)_

### `sensor_readings.pressure_5`

Pressure in the machine.

| | |
|---|---|
| Type | `float` (observed) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | `8.37` |
| Mappings | 80 (80 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `pressure sensor 5(psi)`, `val_pressure_5`, `measured_PS5`, `pressure 5_psi`, `cur_pressure_sensor_5`, `PS5_bar`, `PS5 [psi]`, `act_PS5`, `PressureSensor5_bar`, `pressure5 (bar)` _(plus 70 more)_

### `sensor_readings.pressure_6`

Pressure in the machine.

| | |
|---|---|
| Type | `float` (observed) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | `1.31` |
| Mappings | 80 (80 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `pressure sensor 6 [bar]`, `pressure 6(bar)`, `Ps6_bar`, `raw_pressure_6`, `cur_PS6`, `measured_P6`, `act_pressure_6`, `raw_PS6`, `Ps6(bar)`, `Pressure_6(psi)` _(plus 70 more)_

### `sensor_readings.process_temperature`

Temperature of the machine.

| | |
|---|---|
| Type | `float` (observed) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | `308.6` |
| Mappings | 80 (80 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `machining temp [C]`, `machining temp(C)`, `proc temp (C)`, `Working Temperature_K`, `raw_Process temperature [C]`, `PROCESS_TEMPERATURE_[K] (F)`, `Tprocess_°C`, `processtemp [C]`, `meas_Process temperature [K]`, `Cutting Temp [F]` _(plus 70 more)_

### `sensor_readings.rotate`

Reported value for rotate.

| | |
|---|---|
| Type | `float` (observed) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | `418.55` |
| Mappings | 80 (80 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `Rotation_rpm`, `rotsensor_rad/s`, `val_rot_speed`, `rot speed (rpm)`, `current_rot_speed`, `Rotation(rpm)`, `RotationalMeasurement(rad/s)`, `actual_rot_sensor`, `Rotation_rad/s`, `rotate measure (rad/s)` _(plus 70 more)_

### `sensor_readings.temperature_1`

Temperature of the machine.

| | |
|---|---|
| Type | `float` (observed) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | `35.44` |
| Mappings | 80 (80 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `temperature_1_F`, `Temperature Sensor 1 (°C)`, `temp_1 (C)`, `OilTemperature_K`, `OIL_TEMP_1 (K)`, `temperature1 (F)`, `T1 (°C)`, `temperature 1`, `OIL_TEMPERATURE(°C)`, `Temp Sensor 1` _(plus 70 more)_

### `sensor_readings.temperature_2`

Temperature of the machine.

| | |
|---|---|
| Type | `float` (observed) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | `40.84` |
| Mappings | 80 (80 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `Temp Sensor 2 [F]`, `temperature2 [°C]`, `temperature 2 (F)`, `val_TS2`, `meas_TEMP2`, `Temp_Sensor_2 [C]`, `Temp Sensor 2_F`, `TemperatureSensor2(C)`, `Temp_Sensor_2`, `Ts2 [C]` _(plus 70 more)_

### `sensor_readings.temperature_3`

Temperature of the machine.

| | |
|---|---|
| Type | `float` (observed) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | `38.66` |
| Mappings | 80 (80 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `Temp 3`, `temperature3 [F]`, `actual_temp_3`, `TemperatureSensor3 (C)`, `temperature_3 (°C)`, `Temperature 3 (C)`, `temp3(C)`, `Temp 3 [F]`, `current_TS3`, `Temp 3 [°C]` _(plus 70 more)_

### `sensor_readings.temperature_4`

Temperature of the machine.

| | |
|---|---|
| Type | `float` (observed) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | `46.93` |
| Mappings | 80 (80 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `cur_temp_4`, `Temp 4 [°C]`, `temperature sensor 4`, `temp4(C)`, `temperature4 (F)`, `Temp Sensor 4 (°C)`, `meas_temperature_4`, `TEMPERATURE_4_F`, `temp4_°C`, `t4_C` _(plus 70 more)_

### `sensor_readings.torque`

Torque on the machine.

| | |
|---|---|
| Type | `float` (observed) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | `40.1` |
| Mappings | 80 (80 confirmed) |
| OEM coverage | `fanuc`, `siemens` |

Mapped from: `CuttingTorque`, `load_torque (Nm)`, `motor torque_kNm`, `torquevalue_ft-lb`, `shaft_torque_kNm`, `Torque[ft-lb]_N-m`, `loadtorque [Nm]`, `T_TORQUE [kNm]`, `TORQUE [FT-LB] (Nm)`, `actual_load_torque` _(plus 70 more)_

### `sensor_readings.vibration`

Vibration measured on measured vibration.

| | |
|---|---|
| Type | `float` (observed) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | `45.09` |
| Mappings | 80 (80 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `Vibration(g)`, `VibrationReading_m/s²`, `vib(mm/s)`, `Vibration Reading [g]`, `VibrationReading (m/s²)`, `vib (m/s²)`, `Accel_m/s²`, `Vibration`, `VibrationReading(m/s²)`, `Vibration_Reading(g)` _(plus 70 more)_

### `sensor_readings.vibration_1`

Vibration measured on measured vibration.

| | |
|---|---|
| Type | `float` (observed) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | `0.49` |
| Mappings | 80 (80 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `v1_m/s²`, `measured_vibration_1`, `Vibration Rms_g`, `VibrationSensor1 (mm/s)`, `value_VIB1`, `vibration_sensor_1`, `vib1 [mm/s]`, `vib_1_m/s²`, `value_vibration_1`, `vibration sensor 1_m/s²` _(plus 70 more)_

### `sensor_readings.volt`

Reported value for volt.

| | |
|---|---|
| Type | `float` (observed) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | `176.22` |
| Mappings | 80 (80 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `Voltage_Reading`, `raw_voltage_reading`, `act_volt`, `VoltageReading (mV)`, `measured_voltage_reading`, `VOLTAGE_MEASURE_mV`, `Voltage_Reading [mV]`, `raw_voltage_measure`, `V_READING [V]`, `act_volt_sensor` _(plus 70 more)_

### `sensor_readings.volume_flow_1`

Flow rate through the machine.

| | |
|---|---|
| Type | `float` (observed) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | `2.019` |
| Mappings | 80 (80 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `act_flow_1`, `flow sensor 1 (gpm)`, `val_flow_sensor_1`, `measured_FLOW1`, `VolumeFlow1_l/min`, `act_volume_flow_1`, `VolumeFlow1 (l/min)`, `val_FLOW1`, `FLOW_1(l/min)`, `Volume Flow 1(gpm)` _(plus 70 more)_

### `sensor_readings.volume_flow_2`

Flow rate through the machine.

| | |
|---|---|
| Type | `float` (observed) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | `8.4` |
| Mappings | 80 (80 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `value_F2`, `actual_F2`, `flow_rate_2(gpm)`, `val_volume_flow_2`, `FLOW_2 [l/min]`, `Volume Flow 2 [l/min]`, `FLOW_SENSOR_2(l/min)`, `actual_volume_flow_2`, `FlowRate2(gpm)`, `flow_rate_2_gpm` _(plus 70 more)_

### `sensor_readings.tool_wear`

Reported value for tool wear.

| | |
|---|---|
| Type | `integer` (observed) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | `108` |
| Mappings | 79 (79 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `Twear (minutes)`, `toolwearmin(minutes)`, `Twear_mm`, `value_Tool wear [min]`, `Cutting Time(minutes)`, `Wear Minutes(minutes)`, `ToolLifeUsed(min)`, `tool_use_time(μm)`, `toolwearmin (min)`, `Tool Life Used_mm` _(plus 69 more)_

### `sensor_readings.motor_power`

Power draw of the motor.

| | |
|---|---|
| Type | `float` (observed) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | `2503.56` |
| Mappings | 77 (77 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `motor watts_kW`, `motorwatts [W]`, `Power_Motor [HP]`, `motorpowerw(W)`, `power motor [HP]`, `drive power [kW]`, `power motor [W]`, `motorpowerw (W)`, `MotorPower_kW`, `measured_motor_power_w` _(plus 67 more)_

### `sensor_readings.pressure_2`

Pressure in the machine.

| | |
|---|---|
| Type | `float` (observed) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | `104.93` |
| Mappings | 76 (76 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `measured_PRESS2`, `pressure 2(kPa)`, `pressure 2(bar)`, `PRESSURE_2`, `ps2_kPa`, `SYSTEM PRESSURE 2 [bar]`, `pressure 2 (bar)`, `value_PRESS2`, `act_PS2`, `Press 2_bar` _(plus 66 more)_

### `metadata.error_id`

Identifier of the machine.

| | |
|---|---|
| Type | `string` (observed) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | `error1` |
| Mappings | 74 (74 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `meas_error_id`, `current_err_id`, `measured_error_number`, `act_error_identifier`, `act_errorCode`, `actual_error_identifier`, `meas_error_identifier`, `measured_error_identifier`, `value_err_id`, `error_id` _(plus 64 more)_

### `parts_count`

Count of the machine.

| | |
|---|---|
| Type | `integer` (inferred_from_name) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | _none observed_ |
| Mappings | 68 (24 confirmed) |
| OEM coverage | `dmg_mori`, `doosan`, `fanuc`, `heidenhain`, `hurco`, `mitsubishi`, `okuma`, `siemens` |

Mapped from: `Part Counter`, `partsCount`, `partcounter`, `PartsProducedActual`, `pieceCountActual`, `M30_CNT`, `PARTS_COUNT`, `PartCnt`, `Piece Count`, `PIECE_COUNT` _(plus 58 more)_

### `power_on_hours`

Cumulative runtime of electrical power, in h.

| | |
|---|---|
| Type | `float` (inferred_from_unit) |
| Unit | `h` (derived) |
| Vertical | `universal` |
| Example | _none observed_ |
| Mappings | 67 (20 confirmed) |
| OEM coverage | `brother`, `caterpillar`, `doosan`, `fanuc`, `haas`, `heidenhain`, `hurco`, `komatsu`, `mazak`, `mitsubishi`, `okuma`, `siemens`, `tornos` |

Mapped from: `OPERATING_HOURS_ACT`, `Machine_Hours`, `RuntimeHours`, `total_hours_act`, `OPER_TM`, `OPERATING_HOURS`, `uptimeHoursActual`, `operatingHours`, `uptime_hours`, `uptimeHours` _(plus 57 more)_

### `program_id`

Identifier of the machine.

| | |
|---|---|
| Type | `integer` (inferred_from_name) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | _none observed_ |
| Mappings | 62 (23 confirmed) |
| OEM coverage | `brother`, `doosan`, `fanuc`, `heidenhain`, `hurco`, `mazak`, `mitsubishi`, `octoprint`, `okuma`, `tornos` |

Mapped from: `ProgNo`, `PROGRAM_ID`, `programIdAct`, `Program Number`, `fileName`, `program_number_act`, `ACTIVE_PROGRAM_ACT`, `programnumber`, `NomProgramme`, `program_number` _(plus 52 more)_

### `cycle_time_seconds`

Reported value for cycle time seconds, in s.

| | |
|---|---|
| Type | `float` (inferred_from_unit) |
| Unit | `s` (declared) |
| Vertical | `universal` |
| Example | _none observed_ |
| Mappings | 60 (9 confirmed) |
| OEM coverage | `dmg_mori`, `doosan`, `heidenhain`, `hurco`, `mitsubishi`, `tornos` |

Mapped from: `CycleTimeSEC`, `cycle_duration_actual`, `part_cycle_time[sec]`, `Cycle Duration`, `CYCLE_TIME_ACT`, `partCycleTimeActual`, `partcycletime`, `cycle_duration_act`, `CycleTm`, `cycleTimeSEC` _(plus 50 more)_

### `metadata.failure_mode_hdf`

Reported value for failure mode hdf.

| | |
|---|---|
| Type | `integer` (observed) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | `0` |
| Mappings | 58 (58 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `value_heat_dissipation_failure`, `measured_HDF`, `val_overheat_failure`, `overheatfailure`, `actual_hdf_flag`, `act_heat_dissipation_failure`, `value_thermal_failure`, `raw_overheat_failure`, `meas_heat_dissipation_failure`, `cur_thermal_failure` _(plus 48 more)_

### `metadata.failure_mode_osf`

Reported value for failure mode osf.

| | |
|---|---|
| Type | `integer` (observed) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | `0` |
| Mappings | 58 (58 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `actual_strain_failure`, `meas_overload_failure`, `meas_overstrain_failure`, `value_strain_failure`, `measured_overload_failure`, `val_osf_flag`, `Overstrain_Failure`, `value_osf_flag`, `act_overload_failure`, `OverstrainFailure` _(plus 48 more)_

### `def_remaining_pct`

Reported value for def remaining pct, in %.

| | |
|---|---|
| Type | `float` (inferred_from_unit) |
| Unit | `%` (derived) |
| Vertical | `universal` |
| Example | _none observed_ |
| Mappings | 57 (3 confirmed) |
| OEM coverage | `caterpillar` |

Mapped from: `DEF_REMAINING_PCT`, `AdblueLevelActual`, `def_remaining`, `def_level_act`, `adblueLevel`, `adblue_level_pct`, `AdblueLevel`, `DEFLevel`, `def_remaining_actual`, `adblue_level_act` _(plus 47 more)_

### `machine_state`

Reported state of the machine.

| | |
|---|---|
| Type | `string` (inferred_from_name) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | _none observed_ |
| Mappings | 57 (16 confirmed) |
| OEM coverage | `brother`, `dmg_mori`, `doosan`, `heidenhain`, `hurco`, `komatsu`, `mazak`, `mitsubishi`, `octoprint`, `okuma` |

Mapped from: `machine_status_act`, `MachStat`, `executionStateAct`, `EXECUTION_STATE_ACT`, `MachState`, `state`, `MachineStatus`, `Execution State`, `executionState`, `OperatingStateActual` _(plus 47 more)_

### `fuel_consumed`

Reported value for fuel consumed.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | _none observed_ |
| Mappings | 56 (3 confirmed) |
| OEM coverage | `caterpillar`, `komatsu` |

Mapped from: `total_fuel[l]`, `fuel_consumed`, `Total Fuel`, `fuel_consumed_act`, `fuel_used[l]`, `TotalFuelL`, `fuelConsumedAct`, `Fuel Used (l)`, `fuelConsumedL`, `fuelConsumedActual` _(plus 46 more)_

### `payload_total`

Load on the machine.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | _none observed_ |
| Mappings | 55 (1 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `TotalPayload`, `Total Payload (tons)`, `payloadTotal`, `CUMULATIVE_LOAD_KG`, `PAYLOAD_TOTAL`, `Payload Total (kg)`, `Total Payload`, `totalPayloadActual`, `payloadTotalAct`, `totalPayloadAct` _(plus 45 more)_

### `ground_speed`

Speed of the machine.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | _none observed_ |
| Mappings | 54 (2 confirmed) |
| OEM coverage | `caterpillar`, `komatsu` |

Mapped from: `VEHICLE_SPEED`, `travel_speed_kph`, `Ground_Speed`, `TravelSpeedActual`, `ground_speed[kph]`, `travel_speed_actual`, `vehiclespeed`, `Travel Speed`, `TRAVEL_SPEED`, `vehicle_speed_kph` _(plus 44 more)_

### `engine_speed_rpm`

Speed of the machine, in rpm.

| | |
|---|---|
| Type | `float` (inferred_from_unit) |
| Unit | `rpm` (declared) |
| Vertical | `universal` |
| Example | _none observed_ |
| Mappings | 52 (6 confirmed) |
| OEM coverage | `caterpillar` |

Mapped from: `ENGINE_SPEED_ACT`, `engineSpeedActual`, `ENGINE_RPM`, `Engine Velocity`, `engine_velocity_act`, `engineRpm`, `ENGINE_RPM_ACT`, `engineVelocityAct`, `enginespeed`, `Engine Velocity (rpm)` _(plus 42 more)_

### `motion_time_hours`

Cumulative runtime of the machine, in h.

| | |
|---|---|
| Type | `float` (inferred_from_unit) |
| Unit | `h` (derived) |
| Vertical | `universal` |
| Example | _none observed_ |
| Mappings | 52 (11 confirmed) |
| OEM coverage | `brother`, `dmg_mori`, `doosan`, `fanuc`, `hurco`, `mazak`, `mitsubishi`, `okuma`, `siemens`, `tornos` |

Mapped from: `Maschinenlaufzeit`, `Axis Motion Time (hours)`, `AxisMotionTimeActual`, `motionHoursAct`, `axisMotionTime`, `MotionHrs`, `Active Hours`, `activeHoursAct`, `AXIS_MOTION_TIME_ACT`, `AXIS_MOTION_TIME` _(plus 42 more)_

### `door_status`

Reported value for door status.

| | |
|---|---|
| Type | `string` (inferred_from_name) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | _none observed_ |
| Mappings | 50 (16 confirmed) |
| OEM coverage | `dmg_mori`, `doosan`, `heidenhain`, `hurco`, `tornos` |

Mapped from: `DoorJoutai`, `doorInterlockAct`, `doorOpen`, `doorinterlock`, `DoorStatusActual`, `DoorOpenActual`, `door_open_act`, `doorInterlock`, `door_open`, `doorOpenActual` _(plus 40 more)_

### `sensor_readings.bad_parts`

Reported value for bad parts.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | _none observed_ |
| Mappings | 48 (0 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `REJECTED_PARTS_ACT`, `NG_COUNT_ACT`, `bad_parts_actual`, `ScrapCountActual`, `NG_COUNT`, `ngCountActual`, `NgCountActual`, `bad_parts`, `BAD_PARTS`, `SCRAP_COUNT` _(plus 38 more)_

### `battery_voltage`

Voltage at the battery.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | _none observed_ |
| Mappings | 46 (8 confirmed) |
| OEM coverage | `caterpillar`, `haas`, `mitsubishi`, `siemens` |

Mapped from: `Battery Level`, `battery_voltage_act`, `battery_level_act`, `battery_voltage_actual`, `Battery_Voltage`, `battery_voltage_v`, `Battery Voltage (v)`, `BackupBattery`, `BackupBatteryActual`, `backup_battery` _(plus 36 more)_

### `metadata.failure_mode_pwf`

Reported value for failure mode pwf.

| | |
|---|---|
| Type | `integer` (observed) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | `0` |
| Mappings | 46 (46 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `measured_power_failure`, `act_PWF`, `meas_PWF`, `val_electrical_failure`, `current_electrical_failure`, `actual_power_failure`, `meas_power_failure`, `cur_power_failure`, `actual_electrical_failure`, `raw_power_failure` _(plus 36 more)_

### `metadata.failure_mode_rnf`

Reported value for failure mode rnf.

| | |
|---|---|
| Type | `integer` (observed) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | `0` |
| Mappings | 46 (46 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `RANDOM FAILURE`, `act_rnf_flag`, `meas_random_failure`, `measured_rnf_flag`, `meas_rnf_flag`, `meas_RNF`, `value_rnf_flag`, `current_RNF`, `actual_random_failure`, `rnfflag` _(plus 36 more)_

### `metadata.failure_mode_twf`

Reported value for failure mode twf.

| | |
|---|---|
| Type | `integer` (observed) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | `0` |
| Mappings | 46 (46 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `meas_tool_wear_failure`, `raw_TWF`, `value_twf_flag`, `actual_twf_flag`, `measured_tool_failure`, `tool wear failure`, `current_twf_flag`, `act_twf_flag`, `meas_TWF`, `measured_twf_flag` _(plus 36 more)_

### `sensor_readings.oil_temp`

Temperature of the lubrication system.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | _none observed_ |
| Mappings | 46 (7 confirmed) |
| OEM coverage | `caterpillar`, `tornos` |

Mapped from: `oilTempAct`, `EngineOilTempActual`, `oilTempActual`, `OIL_TEMP_ACT`, `oil_temperature`, `engine_oil_temp_actual`, `engine_oil_temp_act`, `Oil_Temp`, `ENGINE_OIL_TEMP_ACT`, `engineOilTemp` _(plus 36 more)_

### `fuel_rate`

Reported value for fuel rate.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | _none observed_ |
| Mappings | 45 (1 confirmed) |
| OEM coverage | `caterpillar` |

Mapped from: `instantaneousFuelRateActual`, `InstantaneousFuelRate`, `fuelConsumptionRateActual`, `fuelRateL_HR`, `Fuel Rate (l_hr)`, `Fuel Consumption Rate`, `fuelConsumptionRateL_HR`, `FuelConsumptionRateL_HR`, `FuelConsumptionRate`, `FUEL_RATE` _(plus 35 more)_

### `fuel_remaining_pct`

Reported value for fuel remaining pct, in %.

| | |
|---|---|
| Type | `float` (inferred_from_unit) |
| Unit | `%` (derived) |
| Vertical | `universal` |
| Example | _none observed_ |
| Mappings | 45 (2 confirmed) |
| OEM coverage | `caterpillar` |

Mapped from: `fuel_remaining_actual`, `fuel_pct_actual`, `fuelRemainingPCT`, `fuel_remaining`, `FUEL_LEVEL`, `fuel_remaining_act`, `fuel_pct_act`, `FUEL_LEVEL_ACT`, `Fuel Remaining (pct)`, `fuellevel` _(plus 35 more)_

### `odometer`

Reported value for odometer.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | _none observed_ |
| Mappings | 44 (1 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `TOTAL_DISTANCE_KM`, `mileageAct`, `mileage_actual`, `odometerAct`, `MILEAGE_KM`, `ODOMETER_KM`, `TOTAL_DISTANCE`, `OdometerKM`, `mileage`, `Mileage (km)` _(plus 34 more)_

### `sensor_readings.ambient_temp`

Temperature of the machine.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | _none observed_ |
| Mappings | 44 (6 confirmed) |
| OEM coverage | `fanuc` |

Mapped from: `ambientTempAct`, `RoomTempActual`, `ShuuiOndo`, `ambient_temp_c`, `AMBIENT_AIR_TEMPERATURE_ACT`, `room_temp`, `room_temp_actual`, `roomTemp`, `ambientAirTemperature`, `RoomTemp` _(plus 34 more)_

### `idle_hours`

Cumulative runtime of the machine, in h.

| | |
|---|---|
| Type | `float` (inferred_from_unit) |
| Unit | `h` (derived) |
| Vertical | `universal` |
| Example | _none observed_ |
| Mappings | 43 (2 confirmed) |
| OEM coverage | `caterpillar` |

Mapped from: `idleTime`, `standby_hours`, `STANDBY_HOURS_ACT`, `idle_time_act`, `idlehours`, `IDLE_HOURS`, `IdleTimeHOURS`, `IDLE_TIME_ACT`, `idle_time_hours`, `Idle Time` _(plus 33 more)_

### `location_longitude`

Reported value for location longitude.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | _none observed_ |
| Mappings | 43 (2 confirmed) |
| OEM coverage | `caterpillar` |

Mapped from: `LongitudeActual`, `Longitude (deg)`, `gpsLongitude`, `lonActual`, `longitude_actual`, `lonAct`, `LongitudeDEG`, `LNG`, `longitude_deg`, `Lng` _(plus 33 more)_

### `sensor_readings.bed_temp`

Temperature of the print bed.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | _none observed_ |
| Mappings | 43 (1 confirmed) |
| OEM coverage | `octoprint` |

Mapped from: `build_plate_temp_act`, `bedTempAct`, `Build Plate Temp`, `bedTemp`, `heated_bed_temperature`, `build_plate_temp`, `buildPlateTempActual`, `heatedBedTemperatureAct`, `HeatedBedTemperatureActual`, `bedTempActual` _(plus 33 more)_

### `cutting_time_hours`

Cumulative runtime of the machine, in h.

| | |
|---|---|
| Type | `float` (inferred_from_unit) |
| Unit | `h` (derived) |
| Vertical | `universal` |
| Example | _none observed_ |
| Mappings | 42 (6 confirmed) |
| OEM coverage | `dmg_mori`, `doosan`, `fanuc`, `mazak`, `mitsubishi`, `okuma` |

Mapped from: `cuttingHoursActual`, `cutting_hours_act`, `spindleOnHours`, `machining_hours_act`, `cutting_hours_actual`, `CUTTING_HOURS_ACT`, `CuttingTime`, `machiningHours`, `SpindleOnHours`, `MachiningHours` _(plus 32 more)_

### `emergency_stop_active`

Reported value for emergency stop active.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | _none observed_ |
| Mappings | 41 (11 confirmed) |
| OEM coverage | `brother`, `doosan`, `heidenhain`, `hurco`, `mitsubishi`, `siemens` |

Mapped from: `estop`, `EmStopActive`, `estopAct`, `Emergency Stop`, `estop_actual`, `emergencyStop`, `Notaus_Aktiv`, `e_stop_active_act`, `E_STOP_ACTIVE`, `e_stop_active` _(plus 31 more)_

### `service_meter_hours`

Cumulative runtime of the machine, in h.

| | |
|---|---|
| Type | `float` (inferred_from_unit) |
| Unit | `h` (derived) |
| Vertical | `universal` |
| Example | _none observed_ |
| Mappings | 41 (1 confirmed) |
| OEM coverage | `komatsu` |

Mapped from: `SERVICE_METER_HOURS`, `serviceHoursActual`, `ServiceMeterActual`, `hoursSinceService`, `HoursSinceServiceActual`, `service_meter`, `serviceHours`, `serviceMeter`, `Hours Since Service`, `ServiceMeterHOURS` _(plus 31 more)_

### `location_altitude`

Reported value for location altitude.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | _none observed_ |
| Mappings | 40 (1 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `gpsAltitude`, `altitudeActual`, `elevationActual`, `elevation_m`, `gpsAltitudeAct`, `elevationM`, `ElevationActual`, `altitude_act`, `GPS_ALTITUDE_ACT`, `Elevation (m)` _(plus 30 more)_

### `program_line_number`

Reported value for program line number.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | _none observed_ |
| Mappings | 40 (6 confirmed) |
| OEM coverage | `haas`, `heidenhain`, `hurco`, `mitsubishi`, `siemens`, `tornos` |

Mapped from: `execution_line`, `execution_line_act`, `executionline`, `executionLine`, `current_line_actual`, `ExecutionLine`, `CurrentLine`, `programLineAct`, `currentline`, `CURRENT_LINE` _(plus 30 more)_

### `sensor_readings.motor_temp`

Temperature of the motor.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | _none observed_ |
| Mappings | 39 (0 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `motor_temp_act`, `MOTOR_TEMP_ACT`, `motor_temp_actual`, `MotorTempC`, `servo_motor_temp_act`, `motor_temp[c]`, `SERVO_MOTOR_TEMP`, `ServoMotorTempActual`, `motor_temperature_act`, `MotorTemperatureActual` _(plus 29 more)_

### `sensor_readings.oil_pressure`

Pressure in the lubrication system.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | _none observed_ |
| Mappings | 39 (7 confirmed) |
| OEM coverage | `caterpillar`, `komatsu` |

Mapped from: `EngineOilPressurePSI`, `oil_pressure_actual`, `Öldruck`, `AbraAtsuryoku`, `oil_pressure[bar]`, `Oil Pressure (bar)`, `oil_pressure_bar`, `OilPressureBAR`, `engineOilPressurePSI`, `PressionHuile` _(plus 29 more)_

### `machine_mode`

Reported value for machine mode.

| | |
|---|---|
| Type | `string` (inferred_from_name) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | _none observed_ |
| Mappings | 38 (2 confirmed) |
| OEM coverage | `fanuc`, `heidenhain` |

Mapped from: `operationMode`, `operation_mode_act`, `operationmode`, `operationModeAct`, `control_mode`, `operation_mode_actual`, `machine_mode_act`, `operation_mode`, `OperationModeActual`, `MACHINE_MODE_ACT` _(plus 28 more)_

### `cycle_count`

Count of the machine.

| | |
|---|---|
| Type | `integer` (inferred_from_name) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | _none observed_ |
| Mappings | 37 (4 confirmed) |
| OEM coverage | `haas`, `mitsubishi`, `siemens`, `tornos` |

Mapped from: `operationCount`, `cyclecount`, `cycleCounterAct`, `CycleCounterActual`, `OperationCount`, `CYCLE_COUNT_ACT`, `cycle_count_act`, `CycleCounter`, `cycleCounter`, `CycleCountActual` _(plus 27 more)_

### `load_count`

Load on the machine.

| | |
|---|---|
| Type | `integer` (inferred_from_name) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | _none observed_ |
| Mappings | 37 (1 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `payloadEventsActual`, `loadcount`, `PayloadEvents`, `payloadEvents`, `PayloadEventsActual`, `CumulativeLoadCount`, `Load Count`, `loadCountAct`, `loadCount`, `loads_completed` _(plus 27 more)_

### `location_latitude`

Reported value for location latitude.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | _none observed_ |
| Mappings | 35 (2 confirmed) |
| OEM coverage | `caterpillar` |

Mapped from: `latitudeDEG`, `GpsLatitude`, `gpsLatitude`, `latitude_deg`, `lat_actual`, `LAT_ACT`, `latitude_act`, `Location_Latitude`, `latitudeAct`, `gpslatitude` _(plus 25 more)_

### `sensor_readings.hydraulic_temp`

Temperature of the hydraulic system.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | _none observed_ |
| Mappings | 35 (6 confirmed) |
| OEM coverage | `caterpillar` |

Mapped from: `TemperaturaHidraulica`, `Hydraulic_Temp`, `hydraulic_temp`, `HydraulicTempActual`, `hydraulicTempActual`, `Hydrauliktemperatur`, `hydraulic_temp_act`, `HydraulicTempC`, `Hydraulic Temp (c)`, `hydraulictemp` _(plus 25 more)_

### `engine_load_pct`

Load on the machine, in %.

| | |
|---|---|
| Type | `float` (inferred_from_unit) |
| Unit | `%` (declared) |
| Vertical | `universal` |
| Example | _none observed_ |
| Mappings | 34 (1 confirmed) |
| OEM coverage | `caterpillar` |

Mapped from: `EngineTorqueLoadPCT`, `engineLoad`, `ENGINE_LOAD_PCT`, `engine_load[pct]`, `Engine Load (pct)`, `Engine_Load`, `engine_torque_load_actual`, `engineLoadPCT`, `EngineLoadActual`, `engine_load_actual` _(plus 24 more)_

### `sensor_readings.chamber_temp`

Temperature of the machine.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | _none observed_ |
| Mappings | 31 (1 confirmed) |
| OEM coverage | `octoprint` |

Mapped from: `enclosure_temperature_act`, `ENCLOSURE_TEMPERATURE_ACT`, `enclosureTemperatureActual`, `enclosureTemperature`, `ChamberTempActual`, `chamberTemp`, `chamber_temp`, `Enclosure Temperature`, `chamber_temp_c`, `EnclosureTemperature` _(plus 21 more)_

### `sensor_readings.vibration_score`

Vibration measured on measured vibration.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | _none observed_ |
| Mappings | 31 (1 confirmed) |
| OEM coverage | `octoprint` |

Mapped from: `vibration_score_actual`, `vibrationActual`, `vibrationScore`, `VibrationScore`, `VibrationLevelActual`, `VIBRATION_SCORE`, `vibrationscore`, `VIBRATION_LEVEL`, `vibration_score`, `vibration_level_actual` _(plus 21 more)_

### `sensor_readings.transmission_temp`

Temperature of the machine.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | _none observed_ |
| Mappings | 30 (2 confirmed) |
| OEM coverage | `caterpillar` |

Mapped from: `transmission_temp`, `Transmission_Temp`, `transmission_temp_c`, `transmissionTempC`, `TransmissionTemp`, `TRANS_OIL_TEMP`, `transmissionTemp`, `transmission_temp_actual`, `transOilTemp`, `transmissiontemp` _(plus 20 more)_

### `sensor_readings.drive_temp`

Temperature of the machine.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | _none observed_ |
| Mappings | 29 (1 confirmed) |
| OEM coverage | `siemens` |

Mapped from: `DriveTempC`, `DRIVE_TEMP`, `Servo Drive Temperature`, `DRIVE_TEMP_C`, `servoDriveTemperatureAct`, `driveTempC`, `drive_temp_c`, `Drive Temp`, `driveTempActual`, `driveTempAct` _(plus 19 more)_

### `sensor_readings.intake_temp`

Temperature of the machine.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | _none observed_ |
| Mappings | 29 (0 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `intakeTempActual`, `INTAKE_MANIFOLD_TEMPERATURE`, `INTAKE_TEMP`, `intakeManifoldTemperatureActual`, `IntakeTempC`, `intakeTempAct`, `intake_manifold_temperature_act`, `intakeTemp`, `intake_manifold_temperature_actual`, `intake_temp_act` _(plus 19 more)_

### `power.instantaneous_kw`

Reported value for instantaneous kw, in kW.

| | |
|---|---|
| Type | `float` (inferred_from_unit) |
| Unit | `kW` (derived) |
| Vertical | `universal` |
| Example | _none observed_ |
| Mappings | 12 (12 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `motor_power`, `power_kw`, `drive_motor_power`, `electric_motor_power`, `PowerConsumption_kW`, `EPS1`, `instantaneous_power_kw`, `active_power_kw`, `realtime_power_kw`, `kw_draw` _(plus 2 more)_

### `energy.cumulative_kwh`

Reported value for cumulative kwh, in kWh.

| | |
|---|---|
| Type | `float` (inferred_from_unit) |
| Unit | `kWh` (derived) |
| Vertical | `universal` |
| Example | _none observed_ |
| Mappings | 9 (9 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `cumulative_energy_kwh`, `energy_kwh`, `total_kwh_consumed`, `kwh_total`, `energy_consumed_kwh`, `cumulative_kwh`, `energy_kwh_total`, `total_energy_kwh`, `spindle_energy_kwh`

### `program_number`

Reported value for program number.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | _none observed_ |
| Mappings | 9 (9 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `M1_CURRENT_PROGRAM_NUMBER`, `program_no`, `program_id`, `prog_num`, `NC_program`, `current_program`, `ProgramNumber`, `active_program`, `O_number`

### `dc_bus_voltage`

Voltage at the machine.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | _none observed_ |
| Mappings | 7 (7 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `bus_voltage`, `dc_link_voltage`, `dc_bus_v`, `vdc_bus`, `dc_voltage_bus`, `DCBusVoltage`, `drive_voltage`

### `pallet_position`

Position of the machine.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | _none observed_ |
| Mappings | 7 (7 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `pallet_index`, `PalletNo`, `APC_POS`, `pallet_number`, `APC_Position`, `auto_pallet_changer`, `pallet_pos`

### `sequence_number`

Reported value for sequence number.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | _none observed_ |
| Mappings | 7 (7 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `N_number`, `seq_no`, `sequence_no`, `SequenceNumber`, `block_number`, `NC_block`, `M1_sequence_number`

### `cycle_time_ms`

Reported value for cycle time ms, in ms.

| | |
|---|---|
| Type | `float` (inferred_from_unit) |
| Unit | `ms` (derived) |
| Vertical | `universal` |
| Example | _none observed_ |
| Mappings | 6 (6 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `cycle_time`, `machining_time`, `CYCLE_TIME_MS`, `CycleTime`, `cutting_time_ms`, `run_time_ms`

### `identity.controller_model`

Reported value for controller model.

| | |
|---|---|
| Type | `string` (inferred_from_name) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | _none observed_ |
| Mappings | 6 (6 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `controller`, `controller_name`, `ControllerModel`, `controller_model`, `controller_type`, `cnc_controller_model`

### `program_runtime_seconds`

Reported value for program runtime seconds.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | _none observed_ |
| Mappings | 6 (6 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `program_time`, `running_time`, `program_elapsed_seconds`, `ProgramRuntime`, `elapsed_time`, `PROG_TIME`

### `vibration.rms`

Reported value for rms.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | _none observed_ |
| Mappings | 6 (6 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `vib_rms`, `vibration_rms_mms`, `vibration_rms`, `vibration_velocity_rms`, `rms_vibration`, `VibrationRMS`

### `sensor_readings.bucket_load`

Load on the machine.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | _none observed_ |
| Mappings | 2 (2 confirmed) |
| OEM coverage | `caterpillar` |

Mapped from: `BucketLoad`, `Bucket_Load`

### `axis_count`

Count of the machine.

| | |
|---|---|
| Type | `integer` (inferred_from_name) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | _none observed_ |
| Mappings | 1 (1 confirmed) |
| OEM coverage | `fanuc` |

Mapped from: `AxisCount`

### `last_cycle_time_seconds`

Reported value for last cycle time seconds.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | _none observed_ |
| Mappings | 1 (1 confirmed) |
| OEM coverage | `haas` |

Mapped from: `LAST_CYCLE_TIME`

### `max_axes`

Reported value for max axes.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | _none observed_ |
| Mappings | 1 (1 confirmed) |
| OEM coverage | `fanuc` |

Mapped from: `MaxAxes`

### `print_time_remaining`

Reported value for print time remaining.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | _none observed_ |
| Mappings | 1 (1 confirmed) |
| OEM coverage | `octoprint` |

Mapped from: `printTimeLeft`

### `print_time_seconds`

Reported value for print time seconds.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | _none observed_ |
| Mappings | 1 (1 confirmed) |
| OEM coverage | `octoprint` |

Mapped from: `printTime`

### `progress_pct`

Completion progress of the machine, in %.

| | |
|---|---|
| Type | `float` (inferred_from_unit) |
| Unit | `%` (derived) |
| Vertical | `universal` |
| Example | _none observed_ |
| Mappings | 1 (1 confirmed) |
| OEM coverage | `octoprint` |

Mapped from: `completion`

### `sensor_readings.bed_target`

Reported value for bed target.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | _none observed_ |
| Mappings | 1 (1 confirmed) |
| OEM coverage | `octoprint` |

Mapped from: `bed_target`

### `sensor_readings.boom_angle`

Reported value for boom angle.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | _none observed_ |
| Mappings | 1 (1 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `BoomAngle`

### `sensor_readings.chamber_target`

Reported value for chamber target.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | _none observed_ |
| Mappings | 1 (1 confirmed) |
| OEM coverage | `octoprint` |

Mapped from: `chamber_target`

### `sensor_readings.implement_pressure`

Pressure in the machine.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | _none observed_ |
| Mappings | 1 (1 confirmed) |
| OEM coverage | _generic tags only_ |

Mapped from: `ImplementPressure`

### `service_hours_remaining`

Cumulative runtime of the machine.

| | |
|---|---|
| Type | _unspecified_ (unspecified) |
| Unit | _none recorded_ (none) |
| Vertical | `universal` |
| Example | _none observed_ |
| Mappings | 1 (1 confirmed) |
| OEM coverage | `caterpillar` |

Mapped from: `Service_Hours_Remaining`

---

## Vocabulary tier: declared but unmapped

328 canonical names the reference implementation accepts and emits, with
no vendor tag mappings in the corpus yet. They are `provenance: vocabulary` in
`fields.json` and carry `mapping_count: 0`. Vendor tags for these are the most
useful contribution right now.

220 of them declare a unit; the rest declare none.
They come from two sources: 300 from the deterministic vertical packs and 28
from the 2026-08-22 energy sprint.

### Contracts withheld

These names are legitimate, but their generated unit contracts were wrong and
have been withheld rather than published. The generator read a three-phase
suffix as a unit — `_a` as Amps, `_c` as Celsius — when it means phase A and
phase C:

- `ac_current_phase_c` — typed dimension=temperature/unit=C accepting F/K/R, but this is a current. The builder read the '_c' phase suffix as Celsius.
- `ac_voltage_phase_a` — typed dimension=current/unit=A, but this is a voltage. The builder read the '_a' phase suffix as Amps.
- `ac_voltage_phase_c` — typed dimension=temperature/unit=C accepting F/K/R, but this is a voltage. The builder read the '_c' phase suffix as Celsius.

### By declared unit

**%** (33)

`battery_remaining_pct`, `battery_soc_pct`, `battery_soh_pct`, `bucket_fill_pct`, `co2_concentration_pct`, `coolant_level_pct`, `cooling_valve_pct`, `cpu_utilization_pct`, `damper_position_pct`, `dissolved_oxygen_pct`, `dpf_soot_load_pct`, `engine_torque_pct`, `fan_speed_pct`, `fuel_level_pct`, `gpu_utilization_pct`, `heating_valve_pct`, `memory_utilization_pct`, `mixed_air_damper_pct`, `output_load_pct`, `outside_air_damper_pct`, `oven_humidity_pct`, `pdu_load_pct`, `polytropic_efficiency_pct`, `pump_efficiency_pct`, `reactor_level_pct`, `relative_humidity_pct`, `servo_load_c_pct`, `servo_load_pct`, `servo_load_x_pct`, `servo_load_y_pct`, `servo_load_z_pct`, `tc_slip_pct`, `throttle_pct`

**A** (8)

`ac_current_phase_a`, `battery_current_a`, `dc_current_a`, `drive_current_x_a`, `drive_current_y_a`, `drive_current_z_a`, `line_current_a`, `pdu_outlet_current_a`

**C** (84)

`alarm_high_c`, `alarm_low_c`, `ambient_temperature_c`, `battery_cell_temp_max_c`, `battery_temperature_c`, `bearing_drive_end_temperature_c`, `bearing_non_drive_end_temperature_c`, `brake_temperature_c`, `chassis_temperature_c`, `chilled_water_return_temp_c`, `chilled_water_supply_temp_c`, `chilled_water_temperature_c`, `cip_temperature_c`, `cold_storage_temperature_c`, `column_bottom_temperature_c`, `column_top_temperature_c`, `condenser_temp_c`, `condenser_temperature_c`, `condenser_water_return_temp_c`, `condenser_water_supply_temp_c`, `coolant_temperature_c`, `cpu_temperature_c`, `cutout_high_c`, `cutout_low_c`, `discharge_air_temp_c`, `drive_temperature_x_c`, `drive_temperature_y_c`, `drive_temperature_z_c`, `evaporator_temp_c`, `evaporator_temperature_c`, `exhaust_temperature_c`, `holding_tube_temperature_c`, `hx_inlet_cold_c`, `hx_inlet_hot_c`, `hx_outlet_cold_c`, `hx_outlet_hot_c`, `hydraulic_temperature_c`, `inlet_temperature_c`, `intake_temperature_c`, `internal_temperature_c`, `inverter_cabinet_temp_c`, `jacket_temperature_c`, `mechanical_seal_temperature_c`, `mixed_air_temp_c`, `mixer_temperature_c`, `motor_temperature_c`, `motor_winding_temperature_c`, `oil_temperature_c`, `other_temperature_c`, `outside_air_temp_c`, `oven_temperature_c`, `panel_temperature_c`, `pasteurizer_temperature_c`, `product_temperature_c`, `reactor_temperature_c`, `retarder_temperature_c`, `return_air_temp_c`, `return_air_temperature_c`, `shelf_temperature_c`, `space_temp_c`, `space_temperature_c`, `spindle_temperature_c`, `sterilizer_temperature_c`, `supply_air_temp_c`, `supply_air_temperature_c`, `temperature_air_c`, `temperature_c`, `temperature_condenser_c`, `temperature_defrost_c`, `temperature_differential_c`, `temperature_evaporator_c`, `temperature_product_c`, `temperature_setpoint_c`, `temperature_suction_c`, `temperature_zone_1_c`, `temperature_zone_2_c`, `temperature_zone_3_c`, `temperature_zone_4_c`, `temperature_zone_5_c`, `temperature_zone_6_c`, `transformer_temperature_c`, `transmission_temperature_c`, `vessel_temperature_c`, `zone_temp_c`

**Hz** (1)

`grid_frequency_hz`

**K** (2)

`subcooling_k`, `superheat_k`

**Nm** (5)

`agitator_torque_nm`, `cap_torque_nm`, `joint_effort_0_nm`, `mixer_torque_nm`, `swing_torque_nm`

**V** (4)

`battery_voltage_v`, `dc_bus_voltage_v`, `dc_voltage_v`, `line_voltage_v`

**W/m2** (1)

`solar_irradiance_w_m2`

**Wh** (1)

`dc_energy_total_wh`

**bar** (22)

`air_pressure_bar`, `cip_pressure_bar`, `column_pressure_bar`, `compressor_discharge_pressure_bar`, `compressor_suction_pressure_bar`, `condenser_pressure_bar`, `discharge_pressure_bar`, `hydraulic_pressure_bar`, `interstage_pressure_bar`, `mechanical_seal_chamber_pressure_bar`, `oil_pressure_bar`, `pump_differential_pressure_bar`, `pump_discharge_pressure_bar`, `pump_head_pressure_bar`, `pump_suction_pressure_bar`, `reactor_pressure_bar`, `seal_pressure_bar`, `sterilizer_pressure_bar`, `suction_pressure_bar`, `swing_pressure_bar`, `tire_pressure_bar`, `vessel_pressure_bar`

**h** (3)

`compressor_runtime_hours`, `fuel_rate_l_h`, `runtime_hours`

**kVA** (1)

`apparent_power_kva`

**kVAR** (1)

`reactive_power_kvar`

**kW** (10)

`active_power_kw`, `charge_rate_kw`, `condenser_duty_kw`, `dc_power_kw`, `discharge_rate_kw`, `inverter_output_kw`, `peak_demand_kw`, `power_consumption_kw`, `reboiler_duty_kw`, `stirrer_power_kw`

**kWh** (3)

`battery_capacity_kwh`, `energy_delivered_kwh`, `energy_received_kwh`

**kph** (2)

`ground_speed_kph`, `vehicle_speed_kph`

**m** (1)

`altitude_m`

**m/s** (6)

`airspeed_m_s`, `climb_rate_m_s`, `commanded_linear_velocity_m_s`, `groundspeed_m_s`, `linear_velocity_m_s`, `wind_speed_m_s`

**m/s2** (1)

`accel_z_m_s2`

**mbar** (1)

`chamber_pressure_mbar`

**min** (2)

`runtime_remaining_min`, `sterilization_cycle_time_min`

**mm** (3)

`position_x_mm`, `position_y_mm`, `position_z_mm`

**mm/min** (1)

`feed_rate_mm_min`

**mm/s** (5)

`vibration_drive_end_axial_mm_s`, `vibration_drive_end_radial_mm_s`, `vibration_non_drive_end_axial_mm_s`, `vibration_non_drive_end_radial_mm_s`, `vibration_rms_mm_s`

**ms** (1)

`cip_conductivity_ms`

**psi** (8)

`brake_pressure_psi`, `hydraulic_pressure_psi`, `oil_pressure_psi`, `tire_pressure_lf_psi`, `tire_pressure_lr_psi`, `tire_pressure_rf_psi`, `tire_pressure_rr_psi`, `transmission_pressure_psi`

**ratio** (1)

`power_factor`

**rpm** (8)

`agitator_speed_rpm`, `fan_speed_rpm`, `impeller_rotational_speed_rpm`, `joint_speed_rpm`, `mixer_speed_rpm`, `pump_speed_rpm`, `stirrer_speed_rpm`, `turret_speed_rpm`

**s** (1)

`joint_velocity_0_rad_s`

**(no unit declared)** (108)

`ac_current_phase_b`, `ac_current_phase_c`, `ac_voltage_ll_ab`, `ac_voltage_ll_bc`, `ac_voltage_ll_ca`, `ac_voltage_phase_a`, `ac_voltage_phase_b`, `ac_voltage_phase_c`, `active_program`, `active_tool_id`, `alarm_count`, `alarm_label`, `auto_mode_active`, `availability_state`, `batch_volume_liters`, `battery_current_ca`, `battery_voltage_mv`, `belt_speed_mpm`, `charge_cycles`, `chiller_efficiency_kw_ton`, `chiller_status`, `cip_flow_lpm`, `co2_ppm`, `compression_force_kn`, `compression_ratio`, `compressor_current_amps_1`, `compressor_current_amps_2`, `compressor_relay_state`, `compute_throughput`, `condenser_pressure`, `controller_mode`, `cooling_capacity_tons`, `cooling_command`, `defrost_relay_state`, `defrost_state`, `dig_force_kn`, `discharge_pressure`, `disk_read_iops`, `disk_write_iops`, `divert_valve_status`, `door_interlock_open`, `door_state`, `downtime_category`, `downtime_planned`, `ejection_force_kn`, `error_count`, `estop_active`, `evaporator_pressure`, `event_flags_2`, `fan_relay_state`, `fill_level_ml`, `fill_speed_bpm`, `filter_status`, `fouling_factor`, `fuel_consumption_lph`, `gear_position`, `gps_fix_type`, `gps_satellites`, `gpu_clock_mhz`, `heading_deg`, `heating_command`, `inverter_event_flags`, `inverter_state`, `jacket_flow_lpm`, `joint_position_0_rad`, `label_speed_bpm`, `machine_name`, `memory_bandwidth`, `memory_used_gb`, `motor_current_amps`, `network_rx_bytes`, `network_tx_bytes`, `npsh_available_m`, `npsh_required_m`, `occupancy_state`, `odometer_km`, `oil_pressure`, `output_apparent_power_va`, `pasteurizer_flow_lpm`, `payload_tonnes`, `percent_rated_load_amps`, `ph`, `pitch_rad`, `power_draw_watts`, `power_usage_effectiveness`, `psu_input_voltage`, `pump_cavitation_index`, `pump_flow_lpm`, `pump_flow_rate_m3h`, `pump_head_m`, `reflux_ratio`, `reject_count`, `relay_state`, `return_air_flow_cfm`, `return_fan_status`, `roll_rad`, `suction_pressure`, `supply_air_flow_cfm`, `supply_fan_status`, `supply_static_pressure`, `tablet_hardness_kp`, `tablet_weight_mg`, `transfer_cause`, `ups_status_bitmask`, `vibration_rms`, `viscosity_cp`, `yaw_rad`, `zone_co2_ppm`

