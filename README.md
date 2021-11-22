# PRE-CHECK AND MAIL 

## This will query linux/windows server with your command/s, compile the info and send it to your email.

## Prerequisite: None for linux, for windows, you need to identity your winrm, see link below.

https://docs.ansible.com/ansible/latest/user_guide/windows_setup.html

### For Linux instruction

### 1 Put your command/s in the variables,

command01: 'hostname -s'<br />
command02: 'dmidecode -s system-manufacturer'<br />
command03: 'vmware-toolbox-cmd -v'<br />
command04: 'systool -a -v -c scsi_host|grep firmware_revision'<br />

#### ***This up to command10 only but you can add more but you have to modify the pre_check.yml

### For Windows instruction

### 1 Put your command/s in the variables,

win_command1: 'hostname'<br />
win_command2: 'Get-WmiObject -class Win32_ComputerSystem'<br />
win_command3: 'systeminfo | Select-String "OS Version:"'<br />
win_command4: '(Get-WmiObject -class "cim_physicalmemory" | Measure-Object -Property Capacity -Sum).Sum/1024' #KB<br />

#### ***This up to win_command10 only but you can add more but you have to modify the pre_check_win.yml# pre-check
#   p r e - c h e c k  
 #   r v - a n s i b l e - p r e - c h e c k  
 #   p r e - c h e c k  
 