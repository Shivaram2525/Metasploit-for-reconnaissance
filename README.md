# NAME: SHIVARAM M.
# REG. NO.: 212223040195
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

![image](https://github.com/Shivaram2525/Metasploit-for-reconnaissance/assets/144226303/3038cf3c-802f-446c-b618-a7a3d35056fe)

Invoke msfconsole:

## OUTPUT:

![image](https://github.com/Shivaram2525/Metasploit-for-reconnaissance/assets/144226303/83ca802f-e9c5-46b6-b361-29ee4010d51a)

Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.
## OUTPUT:

![image](https://github.com/Shivaram2525/Metasploit-for-reconnaissance/assets/144226303/4eab3182-ca89-49d4-9cdf-a66a7ed0adbe)

Port Scanning: Following command is executed for scanning the systems on our local area network with a TCP scan (-sT) looking for open ports between 1 and 1000 (-p1-1000). msf > nmap -sT 192.168.1810/24 -p1-1000

## OUTPUT:

![image](https://github.com/Shivaram2525/Metasploit-for-reconnaissance/assets/144226303/7788a48c-d6c6-467d-a025-ddd3a5715fdf)

use the db-nmap command to scan and save the results into Metasploit's postgresql attached database. In that way, you can use those results in the exploitation stage later.

scan the targets with the command db_nmap as follows. msf > db_nmap 192.168.181.0/24

## OUTPUT:

![image](https://github.com/Shivaram2525/Metasploit-for-reconnaissance/assets/144226303/a33ce51c-ecaa-4f3c-9dce-599d65215ed2)

Metasploit has a multitude of scanning modules built in. If we open another terminal, we can navigate to Metasploit's auxiliary modules and list all the scanner modules. cd /usr/share /metasploit-framework/modules/auxiliary kali > ls -l

## OUTPUT:

![image](https://github.com/Shivaram2525/Metasploit-for-reconnaissance/assets/144226303/36171ee9-8236-4b47-8447-993d4f38701e)

Search is a powerful command in Metasploit that you can use to find what you want to locate. msf >search name:Microsoft type:exploit

## OUTPUT:

![image](https://github.com/Shivaram2525/Metasploit-for-reconnaissance/assets/144226303/6528d5d2-4d73-4edc-bad3-1a48c638be91)

The info command provides information regarding a module or platform,


## OUTPUT:

![image](https://github.com/Shivaram2525/Metasploit-for-reconnaissance/assets/144226303/81ccc05a-b015-4cf7-9007-99a89830262e)

Before beginning, set up the Metasploit database by starting the PostgreSQL server and initialize msfconsole database as follows: systemctl start postgresql msfdb init ##MYSQL ENUMERATION Find the IP address of the Metasploitable machine first. Then, use the db_nmap command in msfconsole with Nmap flags to scan the MySQL database at 3306 port. db_nmap -sV -sC -p 3306 <metasploitable_ip_address>

## OUTPUT:

![image](https://github.com/Shivaram2525/Metasploit-for-reconnaissance/assets/144226303/cc567a80-1899-400f-80f6-5e0dfed94d4f)

Use the search option to look for an auxiliary module to scan and enumerate the MySQL database. search type:auxiliary mysql

## OUTPUT:

![image](https://github.com/Shivaram2525/Metasploit-for-reconnaissance/assets/144226303/cc7d122a-2ea7-46a9-a0c3-0f721dc4bfb8)

use 11 Or: use auxiliary/scanner/mysql/mysql_version

## OUTPUT:

![image](https://github.com/Shivaram2525/Metasploit-for-reconnaissance/assets/144226303/fdf27656-e4f5-4796-97f8-34335cf17733)

Use the set rhosts command to set the parameter and run the module, as follows:

## OUTPUT:

![image](https://github.com/Shivaram2525/Metasploit-for-reconnaissance/assets/144226303/22d05579-6e37-498b-81ac-65c206296261)

After scanning, you can also brute force MySQL root account via Metasploit's auxiliary(scanner/mysql/mysql_login) module.

## OUTPUT:

![image](https://github.com/Shivaram2525/Metasploit-for-reconnaissance/assets/144226303/d1cc70b5-8d26-4b82-9c92-1ab811520499)

set the PASS_FILE parameter to the wordlist path available inside /usr/share/wordlists: set PASS_FILE /usr/share/wordlistss/rockyou.txt Then, specify the IP address of the target machine with the RHOSTS command. set RHOSTS Set BLANK_PASSWORDS to true in case there is no password set for the root account. set BLANK_PASSWORDS true

## OUTPUT:

![image](https://github.com/Shivaram2525/Metasploit-for-reconnaissance/assets/144226303/40964a4b-0709-45d0-801a-0389751291df)

## RESULT:
The Metasploit framework for reconnaissance is  examined successfully
