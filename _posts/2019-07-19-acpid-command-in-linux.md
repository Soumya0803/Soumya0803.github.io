---
layout:     post
title:      acpid command in linux with examples
date:       2019-07-19 11:05:20
author:     Soumya Chopra
---
 
The acpid daemon provides intelligent power management on a system and allows to query battery and configuration status by supporting the Advanced Configuration and Power Interface (ACPI). The ACPI events are notified to the user-space programs by acpid.

<b>Note:</b> The <b>ACPI (Advanced Configuration and Power Interface)</b> specification allows the operating system to control the amount of power it provides to each device or peripheral attached to the system. This makes the operating system to turn off specific devices when they are no longer in use such as the monitor, providing stable and efficient power management.

Acpid being a <b>daemon</b> runs as a background process by default and it should start during the <b>system boot</b>. Whenever an event occours it executes programs to handle the event. It does so as it opens an </b>events file (/proc/acpi/event by default)</b> and reads all the lines. When a line is received (an event), it examines a list of rules to execute the one that matches the event. If there is a lock file (/var/lock/acpid by default) it ignores all incoming ACPI events.

Simple <b>configuration files</b> are used to define the rules. It looks in a configuration directory (/etc/acpi/events by default) and all the files that do not begin with a period (‘.’) or end with a tilde (~) are parsed. Each file must define an event and a corresponding action. Blank lines or lines with the first character as hash (‘#’) are ignored.

There are <b>three tokens</b> in each line: the key, a literal equal sign and the value.

The key can take up to 63 characters, is case-insensitive but whitespaces matters.
The value can take up to 511 characters, it is case and whitespace sensitive. The event value consists of a regular expression and events are matched against it.

<b>Installation:</b>

```python
sudo apt-get install acpid 
```
<b>Synopsis:</b>

```python
acpid [options]
```
<b>Options:</b>

<b>c, –confdir directory</b>
Changes the directory that acpid looks for rule configuration files. The default directory is /etc/acpi/events.

<b>C, –clientmax number</b>
Changes the maximum number of non-root socket connections that can be made to the acpid socket. The default is 256.

<b>d, –debug </b>
Increases the acpid debug level by one. It runs in the foreground if the debug level is non-zero and logs to stderr and to the regular syslog.

<b>e, –eventfile filename</b>
Changes the event file. Acpid reads events from it. The default file is /proc/acpi/event.

<b>f, –foreground</b>
Keeps acpid in the foreground by not forking at startup.

<b>l, –logevents</b>
Tells acpid to log information related to all the events and actions.

<b>L, –lockfile filename</b>
Changes the lock file that is used to stop event processing. The default file is /var/lock/acpid.

<b>g, –socketgroup groupname</b>
Changes the group ownership of domain socket. Acpid publishes events to it.

<b>m, –socketmode mode</b>
Changes the permissions of the UNIX domain socket. Default is 0666.

<b>s, –socketfile filename</b>
Changes the name of the UNIX domain socket that is opened by acpid. The default is /var/run/acpid.socket.

<b>S, –nosocket filename</b>
Tells acpid to not open a UNIX domain socket. This overrides the -s option, it als negates all other socket options.

<b>p, –pidfile filename</b>
Tells acpid to use the specified file as its pidfile. If the file exists, it will be removed and over-written. The default is /var/run/acpid.pid.

<b>v, –version</b>
Prints the version information and exits.
Output:
![acpid](/favicons/acpidversion1.png)

<b>h, –help </b>
Shows help and exits.
Output:
![acpid](/favicons/acpidhelp.png)


<b>Service Control</b>

Use the service utility for controlling the acpid service:

```python
service  acpid
```
Output:
![acpid](/favicons/serviceacpid..png)

To Start the service:

```python
service acpid start
```
You will be prompted for authentication.

To Stop the service:

```python
service acpid stop
```
Output:
![acpid](/favicons/stopservice11.png)

You will be prompted for authentication.

Check if the serivce is started or stopped:

```python
service acpid status
```
Output:
![acpid](/favicons/stopservice.1.png)

