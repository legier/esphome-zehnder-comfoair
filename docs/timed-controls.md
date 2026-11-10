# Timed controls

`packages/timed_controls.yml` is included by both the base and dashboard packages.
It adds a mode select, a duration number and an "Apply" button for each timer-based
action, so the duration can be chosen instead of using the fixed presets:

| Action              | Mode select                 | Duration number             | Button                    |
| ------------------- | --------------------------- | --------------------------- | ------------------------- |
| Bypass              | Bypass Mode                 | Bypass Hours                | Bypass Apply              |
| Boost               | -                           | Boost Minutes               | Boost Apply               |
| Fan level           | Timed Fan Level             | Fan Level Hours             | Fan Level Apply           |
| Temperature profile | Timed Temperature Profile   | Temperature Profile Hours   | Temperature Profile Apply |
| Balance mode        | Timed Balance Mode          | Balance Mode Hours          | Balance Mode Apply        |
| Away                | -                           | Away Days                   | Away Apply                |

Nothing is sent until an "Apply" button is pressed. Bypass "Auto" and balance mode
"Balanced" cancel the respective timer, so their duration is ignored. Use the
existing "Boost off" button and "Away Mode" switch to end boost or away early.
