# scripts
## ovos-logs
 Small helper tool to quickly navigate the logs, create slices and quickview errors  

---------------
- **ovos-logs slice [options]**

  **Slice logs of a given time period. Defaults on the last service start (`-s`) until now (`-u`)**

  _Different logs can be picked using the `-l` option. All logs will be included if not specified._  
  _Optionally, the directory where the logs are stored (`-d`) and the file where the slices should be dumped (`-f`) can be passed as arguments._  

  _[ex: `ovos-logs slice`]_  
  <sup>_Slice all logs from service start up until now. (not shown)_</sup>
  
  _[ex: `ovos-logs slice -s 17:05:20 -u 17:05:25`]_  
  <sup>_Slice all logs from 17:05:20 until 17:05:25._</sup>    
  <sup>_**no logs in that timeframe in other present logs_</sup>
  <img width="1898" alt="Screenshot 2023-12-25 185004" src="https://github.com/emphasize/scripts/assets/25036977/63ae2123-05d5-4044-be7c-4fe9af10e076">
   
  _[ex: `ovos-logs slice -s 17:05:20 -u 17:05:25 -l skills`]_  
  <sup>_Slice skills.log from 17:04:20 until 17:04:25._</sup>
  <img width="1239" alt="Screenshot 2023-12-25 200705" src="https://github.com/emphasize/scripts/assets/25036977/39893908-5b85-4261-8f08-81938690edc8"> 
  
  _[ex: `ovos-logs slice -s 17:05:20 -u 17:05:25 -f ~/testslice.log`]_  
  <sup>_Slice the logs from 17:04:20 until 17:04:25 on all log files and dump the slices in the file ~/testslice.log (default: ~/slice.log)._</sup>
  <img width="1433" alt="Screenshot 2023-12-25 190521" src="https://github.com/emphasize/scripts/assets/25036977/db0dfd16-87e0-4eaf-abc3-bccf95cb23b5">
  <img width="1246" alt="Screenshot 2023-12-25 190732" src="https://github.com/emphasize/scripts/assets/25036977/23deb4d1-714d-4ba5-a2cb-4173352568c0">
--------------

- **ovos-logs list [-e|-w|-d|-x] [options]**

  **List logs by severity (error/warning/debug/exception). A log level has to be specified - more than one can be listed**  

  _A start and end date can be specified using the `-s` and `-u` options. Defaults to the last service start until now._  
  _Different logs can be picked using the `-l` option. All logs will be included if not specified._  
  _Optionally, the directory where the logs are stored (`-d`) and the file where the slices should be dumped (`-f`) can be passed as arguments._  

  _[ex: `ovos-logs list -x`]_  
  <sup>_List the logs with level EXCEPTION (plus tracebacks) from the last service start until now._</sup>
  <img width="992" alt="Screenshot 2023-12-25 184321" src="https://github.com/emphasize/scripts/assets/25036977/7e67ee30-7b34-4645-8e8c-e11622c5226d">

  _[ex: `ovos-logs list -w -e -s 20-12-2023 -l bus -l skills`]_  
  <sup>_List the logs with level WARNING and ERROR from the 20th of December 2023 until now from the logs bus.log and skills.log._</sup>
  <img width="1898" alt="Screenshot 2023-12-25 173739" src="https://github.com/emphasize/scripts/assets/25036977/4c3d8d59-8886-444d-aaa8-3bfc57dd31b7">
---------------------

- **ovos-logs show -l [servicelog]**

  **Show logs**

  _[ex: `ovos-logs show -l bus`]_  
  <sup>_Show the logs from bus.log. (not shown)_</sup>  

  _[ex: wrong servicelog]_  
  <sup>_**logs shown depending on the logs present in the folder_</sup>
  <img width="1900" alt="Screenshot 2023-12-25 190910" src="https://github.com/emphasize/scripts/assets/25036977/085fac17-c58a-4a9b-8acb-b5a948903b6e">
  
