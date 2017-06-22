# What to do when Windows simply hangs or freezes

## What processes and services are running

Press [Win-R] and type `services.msc`. This will start the local services monitor. Then select `Actions -> Export List...` and save the list as type `Text (Comma Delimited) (*.csv)`. Mail this list of services to us.

## What processes were running

The following terminal commands will enable certain key indicators to be logged by PerfMon (Windows Performance Monitor).

You can use Windows Performance Monitor to examine how programs that you run affect your computer's performance, both in real time and by collecting log data for later analysis. To create performance counter and event trace log collections on local and remote systems, at a command prompt that's running as administrator, run the following commands:

```bat
Logman create counter MONITOR_Long -u DOMAIN\USERNAME * -f bincirc -v mmddhhmm -max 500 -c "\\COMPUTERNAME\LogicalDisk(*)\*" "\\COMPUTERNAME\Memory\*" "\\COMPUTERNAME\Network Interface(*)\*" "\\COMPUTERNAME\Paging File(*)\*" "\\COMPUTERNAME\PhysicalDisk(*)\*" "\\COMPUTERNAME\Process(*)\*" "\\COMPUTERNAME\Redirector\*" "\\COMPUTERNAME\Server\*" "\\COMPUTERNAME\System\*" "\\COMPUTERNAME\Terminal Services\*" "\\COMPUTERNAME\Processor(*)\*" "\\COMPUTERNAME\Cache\*" -si 00:05:00

Logman create counter MONITOR_Short -u DOMAIN\USERNAME * -f bincirc -v mmddhhmm -max 500 -c "\\COMPUTERNAME\LogicalDisk(*)\*" "\\COMPUTERNAME\Memory\*" "\\COMPUTERNAME\Network Interface(*)\*" "\\COMPUTERNAME\Paging File(*)\*" "\\COMPUTERNAME\PhysicalDisk(*)\*" "\\COMPUTERNAME\Process(*)\*" "\\COMPUTERNAME\Redirector\*" "\\COMPUTERNAME\Server\*" "\\COMPUTERNAME\System\*" "\\COMPUTERNAME\Terminal Services\*" "\\COMPUTERNAME\Processor(*)\*" "\\COMPUTERNAME\Cache\*" -si 00:00:10
```

This creates two counters, `MONITOR_Long` & `MONITOR_Short` one running every 10 seconds, the other every 5 minutes.

Then, you can start or stop the log(s) by running the following commands:

```bat
logman start MONITOR_Long / MONITOR_Short
logman stop MONITOR_Long / MONITOR_Short
```

The Performance Monitor log is located in the following path: `C:\PERFLOGS`