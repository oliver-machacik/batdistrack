## Batdistrack

A simple script to track the battery discharge rate during suspend.

## Usage

Copy the script to `/usr/lib/systemd/system-sleep/`.

```
sudo cp batdistrack /usr/lib/systemd/system-sleep/
```

The discharge rate will be logged after each suspend/resume. Nothing will be logged if suspend is entered while charging.

```
% journalctl -u systemd-suspend.service | tail

Sep 01 18:59:40 nb-oli systemd[1]: systemd-suspend.service: Consumed 1.320s CPU time.
Sep 01 19:07:41 nb-oli systemd[1]: Starting System Suspend...
Sep 01 19:07:41 nb-oli systemd-sleep[35407]: Saving time and charge.
Sep 01 19:07:42 nb-oli systemd-sleep[35405]: Entering sleep state 'suspend'...
Sep 02 09:04:38 nb-oli systemd-sleep[35405]: System returned from sleep state.
Sep 02 09:04:38 nb-oli systemd-sleep[35686]: Suspend duration: 13h:56m:57s
Sep 02 09:04:38 nb-oli systemd-sleep[35686]: Discharge rate: .69968 W/h.
Sep 02 09:04:38 nb-oli systemd[1]: systemd-suspend.service: Deactivated successfully.
Sep 02 09:04:38 nb-oli systemd[1]: Finished System Suspend.
Sep 02 09:04:38 nb-oli systemd[1]: systemd-suspend.service: Consumed 1.405s CPU time.
```
