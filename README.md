# OldFileRemover
**OldFileRemover** is an utility for removing old files from a directory. When executed the application will compare the size of directory to a specified quota. When the directory exceeds the quota, the application will start to remove files starting from the oldest till the quota is meet.

# Usage example
To automatically run the application every hour on Linux use cron (crontab).

Firstly, open up cronatb with the following command:
```
crontab -e`
```
Then add the one of the example lines to the end of crontab file:
NOTE: Be sure to change the `/path/to/directory` line to the directory that you want OldFileRemover to search in.

EX:1
```
0 * * * * `/usr/bin/mono /path/of/OldFileRemover.exe --exclude "^\." --max-size 1073741824 /path/to/directory`
```
This example makes the OldFileRemover application run every hour. When it runs it removes files from specified directory on path `/path/to/directory` when its size exceeds 1GiB. The files starting with a dot will be ignored.

EX:2
```
0 * * * * `/usr/bin/mono /path/OldFileRemover.exe --max-size 1073741824 /path/to/directory`
```
This example makes the OldFileRemover application run every hour. When it runs it removes files from specified directory on path `/path/to/directory` when its size exceeds 1GiB. No Files will be ignored.

EX:3
```
@daily `/usr/bin/mono /path/of/OldFileRemover.exe --exclude "^\." --max-size 1073741824 /path/to/directory`
```
This example makes the OldFileRemover application run every day. When it runs it removes files from specified directory on path `/path/to/directory` when its size exceeds 1GiB. The files starting with a dot will be ignored.

EX:4
```
@monthly `/usr/bin/mono /path/OldFileRemover.exe --max-size 1073741824 /path/to/directory`
```
This example makes the OldFileRemover application run every month. When it runs it removes files from specified directory on path `/path/to/directory` when its size exceeds 1GiB. No Files will be ignored.
