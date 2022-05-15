# Shell-Scripting


A shell is a program that interprets and executes the commands that a user inputs.
Shells are programs used to interact with a computer using a command line. 
They are used to make many administration procedures automatic: backup, program installation, Web services.
There are various types of shells and many of them support scripting languages. In this lab we will be using bash scripting.

Password Checker:
The first half of this project is a script that will test password strength. 
The input to the script will be the path to a file which contains only the password which will be tested.
Strength of the password is based on these rules...

Password has less than 6, or more than 32 characters
Print "Error: Password length invalid."
For any valid password: +1 point for each character in the string
If the password contains one of the following special characters (#$+%@) +5 points
If the password contains at least one number (0-9) +5 points
If the password contains at least one alpha character (A-Za-z) +5 points
If the password contains a repeated alphanumeric character (i.e. aa, bbb, 55555) -10 points
If the password contains 3 or more consecutive lowercase characters (i.e. bbb, abe, this) -3 points
If the password contains 3 or more consecutive uppercase characters (i.e. BBB, XQR, APPLE) -3 points
If the password contains 3 or more consecutive numbers (i.e. 55555, 1747, 123, 321) -3 points

CPU and Memory Monitor:
a script that: 
(1) generates CPU and memory usage reports and stores them in a directory; 
(2) notifies you by email whenever CPU or memory usage exceeds certain thresholds that you set.
  
  CPU:
  ./monitor.sh {process id} -cpu {cpu usage percentage} {maximum reports} {time interval}
  Note that {X} indicates that X is a mandatory argument. In the above shell command, a number of inputs are required:
  process id: the process id of the process to be monitored.
  cpu usage percentage: the percentage of CPU usage that the process should not exceed. If this is exceeded, a report will be generated.
  maximum reports: the maximum number of usage reports stored in the “./reports_dir” directory.
  time interval: a time in seconds. This represents the amount of time which should pass between checks of CPU usage. 
  
  Memory Monitor:
  Script will now take extra arguments to indicate the maximum physical memory that the process should not exceed.
  Monitor {process id} -cpu {cpu usage percentage} -mem {maximum memory in kB} {maximum reports} {time interval}
  The physical memory used by the process is found in the file /proc/{pid}/status. You should extract the value of “VmRSS”. 
  As opposed to CPU usage, we are now interested in measuring the used memory from the time the process started.
  
Whenever the memory usage exceeds the provided maximum memory, an email is sent to $USER containing the last usage report. 
At this point, the script should be generating reports if a user exceeds either the memory or CPU threshold.






