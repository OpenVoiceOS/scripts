# scripts
## ovos-logs
 Small helper tool to quickly navigate the logs, create slices and quickview errors  

---------------
- **ovos-logs slice [options]**

  **Slice logs of a given time period. Defaults on the last service start (`-s`) until now (`-u`)**

  _Different logs can be picked using the `-l` option. All logs will be included if not specified._  
  _Optionally, the directory where the logs are stored (`-d`) and the file where the slices should be dumped (`-f`) can be passed as arguments._  

  <sup>[ex: `ovos-logs slice`]</sup>  
  Slice all logs from service start up until now.

  <sup>[ex: `ovos-logs slice -s 17:05:20 -u 17:05:25`]</sup>  
  Slice all logs from 17:05:20 until 17:05:25.

  <sup>[ex: `ovos-logs slice -s 17:05:20 -u 17:05:25 -l bus -l skills`]</sup>  
  Slice the logs from 17:04:20 until 17:04:25 (bus.log/skills.log).

  <sup>[ex: `ovos-logs slice -s 17:05:20 -u 17:05:25 -f ~/testslice.log`]</sup>  
  Slice the logs from 17:04:20 until 17:04:25 on all log files and dump the slices in the file ~/testslice.log (default: ~/slice.log).
--------------

- **ovos-logs list [-e|-w|-d|-x] [options]**

  **List logs by level (a log level has to be specified, more than one can be listed)**  

  _A start and end date can be specified using the `-s` and `-u` options. Defaults to the last service start until now._  
  _Different logs can be picked using the `-l` option. All logs will be included if not specified._  
  _Optionally, the directory where the logs are stored (`-d`) and the file where the slices should be dumped (`-f`) can be passed as arguments._  

  <sup>[ex: `ovos-logs list -x`]</sup>  
  List the logs with level EXCEPTION (plus tracebacks) from the last service start until now.

  <sup>[ex: `ovos-logs list -w -e -s 20-12-2023 -l bus -l skills`]</sup>  
  List the logs with level WARNING and ERROR from the 20th of December 2023 until now from the logs bus.log and skills.log.

---------------------
- **ovos-logs show -l [servicelog]**

  **Show logs**

  <sup>[ex: `ovos-logs show -l bus`]</sup>  
  Show the logs from bus.log.

  <sup>[ex: wrong servicelog]</sup>  
