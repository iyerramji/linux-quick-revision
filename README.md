### linux-quick-revision
Just a summary of all the Linux commands that you typically will need for your survival :)


### Check which OS you are on ?
  cat /etc/*release

### Check free memory
  free -kh

### Check disk usage
  df -kh

### Check space consumed by any directory/file.
  du -kh


### Check num of cpus.
  lscpu
  cat /proc/cpuinfo
  nproc

### Check general system health
  top -> very easy to spot high cpu and memory usage.
  You can sort by cpu/mem usage . hit h for more help

  *TIP* You can also identify I/O issue here->
  On the top, you will see %Cpu(s) - If the number for "wa" is higher => that means you have an I/O issue.
  wa -> The amount of time cpu does nothing waiting for an I/O operation

  *TIP* top/uptime shows "load average". check youtube for what it is and how its calculated :)  

### Check what are all the various disks/mounts you have
   lsblk

### Check for I/O issue ?
  iostat 1-> runs iostat every 1 second
  You will figure out if any high activity happens with I/O with this.

  iotop -> like top but for I/O ( you will need to install sysstat package for this)

### What set of files does a process/user have open ?
  lsof -p

### Check what are the various process running
  ps -ef ( for your permitted level)
  ps -aux ( for all the users in the systems)

### Give me a process hierarchy given a parent process id
  pstree -p <pid>

### Check the num of threads of a given process
  check in /proc/<pid>/status

### My service has issues.
  journalctl -u <service_name>

### Check kernel for any issues.
  dmesg

### Bios and other h/w info
  dmidecode

### There are other popular tools that I haven't talked about as I havent used them myself :) -
  pidstat
  nicstat
  dtrace
  pmstat
  ethtool

### Can my user create dumps ?
  ulimit

### Check inode information for my block device
  df -i


### Networking troubleshooting
  ping
  dig
  traceroute
  arping
  ip a
  ip route show

### Which process is listening on what ports ?
  ss -tuna
  netstat -an

### Check if selinux is enabled ?
  getenforce

### Check what the hung process is upto
  strace -p <pid>
