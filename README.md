# Metasploit-for-reconnaissance
# Metasploit
Metasploit for reconnaissance in pentesting

# AIM:

To get introduced to Metasploit Framework and to  perform reconnaissance  in pentesting .

## DESIGN STEPS:

### Step 1:

Install kali linux either in partition or virtual box or in live mode

### Step 2:

Investigate on the various categories of tools as follows:

### Step 3:

Open terminal and try execute some kali linux commands

## EXECUTION STEPS AND ITS OUTPUT:

Find out the ip address of the attackers system

## OUTPUT:
<img width="691" height="367" alt="image" src="https://github.com/user-attachments/assets/304d344e-9c5f-4e91-9c46-0153d61b5096" />

Invoke msfconsole:

## OUTPUT:
<img width="624" height="600" alt="image" src="https://github.com/user-attachments/assets/068f04cf-963f-4a66-9bfe-c048ebd353c3" />

Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.

## OUTPUT:
<img width="806" height="669" alt="image" src="https://github.com/user-attachments/assets/a50fec69-cab4-4f74-bb21-1fa5aaaaea79" />

Port Scanning:
Following command is executed for scanning the systems on our local area network with a TCP scan (-sT) looking for open ports between 1 and 1000 (-p1-1000).
msf >  nmap -sT 192.168.1810/24 -p1-1000

## OUTPUT:
<img width="541" height="431" alt="image" src="https://github.com/user-attachments/assets/eb358d7b-6d45-415f-ad24-9f23301bb054" />


use the db-nmap command to scan and save the results into Metasploit's postgresql attached database. In that way, you can use those results in the exploitation stage later.

scan the targets with the command db_nmap as follows.
msf > db_nmap 192.168.181.0/24
## OUTPUT:
<img width="639" height="355" alt="image" src="https://github.com/user-attachments/assets/f62b17a7-86b0-4e59-844d-6a03e0d70fa6" />

Metasploit has a multitude of scanning modules built in. If we open another terminal, we can navigate to Metasploit's auxiliary modules and list all the scanner modules.
cd /usr/share /metasploit-framework/modules/auxiliary
kali > ls -l
## OUTPUT:


Search is a powerful command in Metasploit that you can use to find what you want to locate. 
msf >search name:Microsoft type:exploit
## OUTPUT:
<img width="797" height="740" alt="image" src="https://github.com/user-attachments/assets/1b903363-d6b2-43aa-8bfe-a97279a65dd5" />

The info command provides information regarding a module or platform
## OUTPUT:
<img width="747" height="657" alt="image" src="https://github.com/user-attachments/assets/de27e94d-a83a-453e-8461-9e64cc41e7da" />
<img width="665" height="506" alt="image" src="https://github.com/user-attachments/assets/d12ec2d1-1aa2-44d5-ac16-590a77c60626" />

## MYSQL ENUMERATION
Find the IP address of the Metasploitable machine first. Then, use the db_nmap command in msfconsole with Nmap flags to scan the MySQL database at 3306 port.
db_nmap -sV -sC -p 3306 <metasploitable_ip_address>
## OUTPUT:
<img width="869" height="137" alt="image" src="https://github.com/user-attachments/assets/5d862e3f-35d5-4580-8308-996c9c970a81" />

Use the search option to look for an auxiliary module to scan and enumerate the MySQL database.
search type:auxiliary mysql
## OUTPUT:
<img width="940" height="514" alt="image" src="https://github.com/user-attachments/assets/d873ab54-509c-4664-9df8-a4688022e9fe" />

use the auxiliary/scanner/mysql/mysql_version module by typing the module name or associated number to scan MySQL version details.
use 11
## OUTPUT:
<img width="938" height="393" alt="image" src="https://github.com/user-attachments/assets/74a7f5ee-e6b8-4aee-971e-5541cefd213b" />

Use the set rhosts command to set the parameter and run the module, as follows:

## OUTPUT:
<img width="740" height="85" alt="image" src="https://github.com/user-attachments/assets/d2266fdf-0330-4522-b79e-d467796a1262" />

After scanning, you can also brute force MySQL root account via Metasploit's auxiliary(scanner/mysql/mysql_login) module.

## OUTPUT:
<img width="942" height="436" alt="image" src="https://github.com/user-attachments/assets/4b9851b8-4897-49a5-8e57-4699ae36f2be" />









## RESULT:
The Metasploit framework for reconnaissance is  examined successfully
