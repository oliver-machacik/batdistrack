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

Jul 27 10:05:38 nb-oli systemd[1]: systemd-suspend.service: Consumed 1.282s CPU time.
Jul 27 10:06:39 nb-oli systemd[1]: Starting System Suspend...
Jul 27 10:06:39 nb-oli systemd-sleep[24567]: Saving time and charge.
Jul 27 10:06:40 nb-oli systemd-sleep[24565]: Entering sleep state 'suspend'...
Jul 27 10:09:56 nb-oli systemd-sleep[24565]: System returned from sleep state.
Jul 27 10:09:56 nb-oli systemd-sleep[24811]: Suspend duration: 00h 03m.
Jul 27 10:09:56 nb-oli systemd-sleep[24789]: Discharge rate: .91407 W/h.
Jul 27 10:09:56 nb-oli systemd[1]: systemd-suspend.service: Deactivated successfully.
Jul 27 10:09:56 nb-oli systemd[1]: Finished System Suspend.
Jul 27 10:09:56 nb-oli systemd[1]: systemd-suspend.service: Consumed 1.313s CPU time.
```
