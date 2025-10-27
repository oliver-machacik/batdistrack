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

Okt 27 10:24:26 t14-sh4 systemd[1]: Starting systemd-suspend.service - System Suspend...
Okt 27 10:24:26 t14-sh4 systemd-sleep[219445]: Saving time and charge.
Okt 27 10:24:26 t14-sh4 systemd-sleep[219443]: Performing sleep operation 'suspend'...
Okt 27 10:25:01 t14-sh4 systemd-sleep[219443]: System returned from sleep operation 'suspend'.
Okt 27 10:25:01 t14-sh4 systemd-sleep[219470]: Suspend duration: 00h:00m:35s
Okt 27 10:25:01 t14-sh4 systemd-sleep[219470]: Discharge rate: 2.05761 W/h.
Okt 27 10:25:01 t14-sh4 systemd-sleep[219470]: Charge went from 97 to 97 %
Okt 27 10:25:01 t14-sh4 systemd[1]: systemd-suspend.service: Deactivated successfully.
Okt 27 10:25:01 t14-sh4 systemd[1]: Finished systemd-suspend.service - System Suspend.
```
