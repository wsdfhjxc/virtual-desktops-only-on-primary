# KWin scripts

This is a repository with some KWin scripts.

The scripts are intended to be used under KDE Plasma.

## Installation

Enter the directory of a choosen script, e.g.:

```
cd virtual-desktops-only-on-primary
```

To install the script, run: `../helper.sh install`

To upgrade the script to a newer version, run: `../helper.sh upgrade`

To uninstall the script, regardless of the installation method, run: `../helper.sh uninstall`

After installing the script, it must be also enabled in the System Settings.

## Available scripts

- [Simple Window Groups](#simple-window-groups)
- [Temporary Virtual Desktops](#temporary-virtual-desktops)
- [Virtual Desktops Only On Primary](#virtual-desktops-only-on-primary)

## Simple Window Groups

This is a script that provides a window grouping system, similar as in some window managers.

Groups, as implemented in this script, are kind of a replacement for virtual desktops. A window can be added to multiple groups at the same time, and windows from different groups can be shown together or hidden on demand. Also, actual virtual desktops are completely ignored while using window groups, because it'd be too confusing to mix these concepts together. However, the regular virtual desktops workflow can be recreated with this script.

The script isn't very convenient in regard to user experience in its current state - no visual cues, indicators etc.

### Configuration and usage

After enabling the script, and while still being in the System Settings, you should head up to the Shortcuts section and select the KWin component, as the script is controllable through keyboard shortcuts.

There are 10 available window groups which can be used, and there are 3 actions that can be invoked for each of the groups. In total there are 30 keyboard shortcuts, but you don't need to set up all of them.

The keyboard shortcuts allow you to toggle a group on the active window (add it to the group, or remove it), show or hide windows from a specific group (e.g. show windows from group 1 and group 3), and show exclusively windows from a specific group (in such case, all windows not present in that group will be hidden).

By default, all new windows are added to groups which are visible at the moment of their opening. It means that when group 1 and group 3 are set to be shown, a new window will be added to both these groups.

### Available keyboard shortcuts

* Add/remove window to/from group 1..10
* Show/hide windows from group 1..10
* Show exclusively windows from group 1..10

Note: All keyboard shortucts have `Simple Window Groups` prefix for easier recognition.

### In case of some terrible things that could happen

If your windows somehow become unaccessible, the following command will bring them back:

```
kwin_x11 --replace & disown
```

## Temporary Virtual Desktops

This is a script that automatically adds and removes virtual desktops.

When the script is enabled, virtual desktops will be added and removed in a way, so that there is always exactly one empty virtual desktop available (until hitting the limit of 20). Once a virtual desktop becomes empty (due to closing windows), it'll be removed, unless it's the only virtual desktop left. That's a feature known from the GNOME Shell, and while it works best with its unmatched overview mode, that feature can be also useful when using KDE Plasma.

Besides enabling the script in the System Settings, no additional steps are required.

## Virtual Desktops Only On Primary

This is a script that brings a feature similar to GNOME Mutter's `workspaces-only-on-primary` option, that is switchable virtual desktops on the primary monitor, and non-switchable virtual desktops on other monitors.

When the script is enabled, all windows placed on monitors other than the primary, are automatically set to be shown on all virtual desktops. This can be considered a hack, but from the user's perspective, this effectively results in having multiple switchable virtual desktops on the primary monitor, and fixed non-switchable virtual desktops on other monitors. That's how GNOME Shell handles workspaces by default, and the script mimics that.

Besides enabling the script in the System Settings, no additional steps are required.
