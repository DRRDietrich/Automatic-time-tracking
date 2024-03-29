# Automatic Time Tracking

Time tracking for Gnome.

### Dependencies

yum -y install xdotool

### Useful adjustments

- „GNOME Tweak Tool“ => Workspaces => Static Workspaces

- GNOME Shell Extension „Workspace Indicator“

.local/share/gnome-shell/extensions/workspace-indicator@gnome-shell-extensions.gcampax.github.com/extension.js
```
_labelText(workspaceIndex) {
        if (workspaceIndex == undefined) {
            workspaceIndex = this._currentWorkspace;
+++         return Meta.prefs_get_workspace_name(workspaceIndex);
            return (workspaceIndex + 1).toString();
        }
        return Meta.prefs_get_workspace_name(workspaceIndex);
    }
```

### Start Time Tracking
```bash
#!/bin/bash
nohup python3 usage.py >/dev/null 2>&1 &
```

### Show Statistics
```bash
#!/bin/bash
cat .usagelogs/YYYY_MM_DD_HH_MM_SS.txt
```

#### Output
Statistics about the 6 workspaces (Project 1 to 6) and active programs. Values in HH:MM:SS and percent.
```bash
Project_1: 0:08:08
Project_2: 0:00:06
Project_3: 0:00:00
Project_4: 0:00:00
Project_5: 0:07:59
Project_6: 0:02:05

------------------------------------------------------------
firefox
0:14:25 (79%)
------------------------------------------------------------
   0:00:30 (3%)     Google - Mozilla Firefox
   ...
------------------------------------------------------------
vlc
0:01:23 (8%)
------------------------------------------------------------
   0:01:15 (7%)     【IT_GE_EN_RU_ES SUBS】 Dimash - Olimpiko _ Ogni Pietra (Minsk, 21.06.2019)-eiLhcmO_RFk.mp4 - VLC media player
   ...
------------------------------------------------------------
gnome-terminal
0:00:52 (5%)
------------------------------------------------------------
   0:00:52 (5%)     ich@me:~
------------------------------------------------------------
nautilus
0:00:40 (4%)
------------------------------------------------------------
   0:00:11 (1%)     Dimash
   0:00:10 (1%)     Videos
   0:00:09 (1%)     Persönlicher Ordner
   ...
------------------------------------------------------------
IDLE
0:00:26 (2%)
------------------------------------------------------------
   0:00:26 (2%)     
------------------------------------------------------------
thunderbird
0:00:17 (2%)
------------------------------------------------------------
   0:00:17 (2%)     Posteingang - ich@me - Mozilla Thunderbird
------------------------------------------------------------
keepassx2
0:00:11 (1%)
------------------------------------------------------------
   0:00:06 (1%)     KEY - KeePassX
   0:00:05 (0%)     KEY.kdbx - KeePassX
------------------------------------------------------------
kthreadd
0:00:04 (0%)
------------------------------------------------------------
   0:00:04 (0%)     Signal

============================================================
started: 2019-06-26 14:35:00	updated: 2019-06-26 14:53:42
============================================================
```
