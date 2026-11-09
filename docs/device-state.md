# Device State and additional PDOs

## Device State (PDO 16)

PDO 16 is the state of the whole unit. The `Device State` text sensor names every value;
unknown values are shown as their number.

| value | Device State |
|-------|--------------|
| 0 | Init |
| 1 | Normal |
| 2 | Filter Wizard |
| 3 | Commissioning |
| 4 | Supplier Factory |
| 5 | Zehnder Factory |
| 6 | Standby |
| 7 | Away |
| 8 | DFC |

`Away Indicator` stays: it is still derived from the same PDO (`7`) and drives the feedback
of the `Away` switch, so existing Home Assistant automations keep working.

## Additional PDOs

These non-schedule PDOs from the
[PDO protocol](https://github.com/michaelarnauts/aiocomfoconnect/blob/master/docs/PROTOCOL-PDO.md)
are polled and exposed by the base package:

| PDO | entity |
|-----|--------|
| 17 | Alarm |
| 18 | Application Mode |
| 115, 116 | Exhaust Fan Enabled, Supply Fan Enabled |
| 144-146 | Pre-heater Energy YTD / Since Start, Pre-heater Power |
| 176 | RF Pairing Mode |
| 208, 224 | Temperature Unit, Airflow Unit |
| 228 | Frost Protection Unbalance |
| 305, 306 | Exhaust Pressure, Supply Pressure (P12/P22, assumed Pa) |
| 369-372 | Analog Input 1-4 (V) |
| 400-402 | Post-heater Temperature, State, Present |
| 416-419 | ComfoFond Outdoor Air / Ground Temperature, GHE State, GHE Present |
| 784, 802 | ComfoCool State, Condenser Temperature |

Entities of accessories that are not installed stay unknown.

Not exposed: the schedule PDOs other than the ones already used (33-90, 321-346), PDOs
above 1023 (CO2 sensors, ComfoClime; the CAN filter only accepts PDO ids up to 1023), and
PDOs whose meaning or scaling is not confirmed on a unit (96-98, 160-162, 219, 222, 229,
256-257, 273, 289, 384-386, 513-524, 785, 801, 803).
