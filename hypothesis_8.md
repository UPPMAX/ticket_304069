# H8: seeing the Whisper icon is relevant to the problem

![The user has a Whisper icon](20241119.png)

> The user has a Whisper icon

## Experiment

When starting up, there is no Whisper icon on the desktop.

```bash
interactive -A sens2023036 -n 2 -t 1:00:00
```

Took 408 seconds.

```bash
[richel@sens2023036-b10 richel]$ module load R_packages/4.3.1
R_packages/4.3.1: Note that loading some spatial analysis packages, especially geo-related packages, might
R_packages/4.3.1: require you to load additional modules prior to use. monocle3 is such a package. See
R_packages/4.3.1: 'module help R_packages/4.3.1'

R_packages/4.3.1: The RStudio packages pane is disabled when loading this module, due to RStudio slowdowns
R_packages/4.3.1: because there are >20000 available packages. *All packages are still available.*  For
R_packages/4.3.1: more information and instructions to re-enable the packages pane (not recommended) see
R_packages/4.3.1: 'module help R_packages/4.3.1'
```


Took some seconds. No Whisper icon appeared on the desktop.

```bash
[richel@sens2023036-b10 richel]$ module load RStudio/2023.12.1-402
RStudio/2023.12.1-402: Sandboxing is not enabled for RStudio at UPPMAX. See 'module help RStudio/2023.12.1-402' for more information
```

Took some seconds. No Whisper icon appeared on the desktop.

```bash
RStudio/2023.12.1-402: Sandboxing is not enabled for RStudio at UPPMAX. See 'module help RStudio/2023.12.1-402' for more information
[richel@sens2023036-b10 richel]$ rstudio
[15610:1218/121941.098426:ERROR:bus.cc(399)] Failed to connect to the bus: Failed to connect to socket /tmp/dbus-daKRBzOsXe: Connection refused
[15610:1218/121941.098696:ERROR:bus.cc(399)] Failed to connect to the bus: Failed to connect to socket /tmp/dbus-daKRBzOsXe: Connection refused
[15610:1218/121941.098769:ERROR:bus.cc(399)] Failed to connect to the bus: Failed to connect to socket /tmp/dbus-daKRBzOsXe: Connection refused
[15610:1218/121941.098825:ERROR:bus.cc(399)] Failed to connect to the bus: Failed to connect to socket /tmp/dbus-daKRBzOsXe: Connection refused
[15610:1218/121944.233648:ERROR:bus.cc(399)] Failed to connect to the bus: Failed to connect to socket /tmp/dbus-daKRBzOsXe: Connection refused
[15610:1218/121944.539871:ERROR:bus.cc(399)] Failed to connect to the bus: Failed to connect to socket /tmp/dbus-daKRBzOsXe: Connection refused
[15610:1218/121944.564217:ERROR:object_proxy.cc(590)] Failed to call method: org.freedesktop.portal.Settings.Read: object_path= /org/freedesktop/portal/desktop: unknown error type: 
[15610:1218/121944.572749:ERROR:bus.cc(399)] Failed to connect to the bus: Failed to connect to socket /tmp/dbus-daKRBzOsXe: Connection refused
```

RStudio took around a minute to start up and seems to work fine. No Whisper icon appeared on the desktop.
