## Powerdrain

A simple script to track the battery discharge rate during suspend.

## Usage

Copy the script to `/usr/lib/systemd/system-sleep/`:

```
sudo cp powerdrain /usr/lib/systemd/system-sleep/
```

The discharge rate will be logged after each suspend/resume.
Nothing will be logged if system is suspended with connected PSU.

```
% journalctl -u systemd-suspend.service | tail

Sep 11 12:54:33 laptop systemd-sleep[19801]: Suspending system...
Sep 11 12:55:37 laptop systemd-sleep[19801]: System resumed.
Sep 11 12:55:37 laptop systemd-sleep[19841]: [INFO] Duration: 00:01:04
Sep 11 12:55:37 laptop systemd-sleep[19841]: [INFO] Discharge rate: 1.12549 W/h.
```
