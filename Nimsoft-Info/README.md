**DESCRIPTION**<br />
This Nmap script enumerates a CA Nimsoft Robot using the "nimbus" protocol. 
The status information gathered reveals detailed information about the Nimsoft
domain including the robot and hub information, IP addresses, local 
hostnames, the robot mode, the specific OS version including service pack, the 
server architecture, the SSL mode and specific version, among others. 

CA Unified Infrastructure Manager, formerly known as Nimsoft, is a scalable IT
monitoring solution. The solution is typically installed on managed servers, and
communicates using the closed source "nimbus" protocol. 

The commands executed by this script in order to enumerate the target Robot are:
 - _status
 - get_info
 - gethub
 - probe_checkin

The script was tested on versions 7.60 (latest) and 5.x.

**USAGE**<br />
The example output below demonstrates how the script can be used:

```
$ nmap —script nimbus-info -n -Pn -p 48000 10.20.0.101
Starting Nmap 6.46 ( http://nmap.org ) at 2015-01-11 13:24 GMT
Nmap scan report for 10.20.0.101
Host is up (0.00045s latency).
PORT      STATE SERVICE
48000/tcp open  unknown
| nimbus-info: 
|   status:
|     name: NMS Robot Controller
|     company: CA
|     version: 7.60 [Build 7.60.1097, Jun 12 2014]
|     started: 1420981880
|     restarted: 0
|     connections: 19
|     messages: 1
|     libversion: 6.01 (32bit)
|     libdate: Jun 12 2014
|     ssl_mode: 0
|     ssl_cipher: DEFAULT
|     ssl_version: OpenSSL 1.0.0c 2 Dec 2010
|   gethub:
|     name: win7
|     hubdomain: none
|     hubname: 
|     hubrobotname: 
|     hubip: 10.10.0.1
|     hubport: 48002
|     phub_domain: none
|     phub_name: 
|     phub_robotname: 
|     phub_ip: 10.10.0.1
|     phub_port: 48002
|   getinfo:
|     robotname: win7
|     robotip: 10.20.0.101
|     hubname: 
|     hubip: 10.10.0.1
|     domain: none
|     origin: 
|     source: Win7
|     robot_device_id: DF842C8209237C42AED75AB12
|     robot_mode: 1
|     hubrobotname: 
|     log_level: 0
|     log_file: controller.log
|     license: 0
|     requests: 59
|     uptime: 768
|     started: 1420981878
|     os_major: Windows
|     os_minor: Windows 7 Enterprise Edition, 32-bit
|     os_version: 6.1.7601
|     os_description: Service Pack 1 Build 7601
|     os_user1: 
|     os_user2: 
|     processor_type: Intel(R) Core(TM) i5-3230M CPU @ 2.60GHz
|     workdir: C:\Program Files\Nimsoft
|     current_time: 1420982646
|     access_0: 0
|     access_1: 0
|     access_2: 0
|     access_3: 0
|     access_4: 0
|     timezone_diff: 28800
|     timezone_name: Pacific Standard Time
|     spoolport: 48001
|     last_inst_change: 1411993600
|   probecheckin:
|     domain: none
|     robotname: win7
|     ssl_mode: 0
|     ssl_cipher: DEFAULT
|     robotip: 10.20.0.101
|     hubdomain: none
|     hubname: 
|     hubrobotname: 
|     hubip: 10.10.0.1
|     hubport: 48002
|     phub_domain: none
|     phub_name: 
|     phub_robotname: 
|     phub_ip: 10.10.0.1
|_    phub_port: 48002
MAC Address: 08:00:27:51:82:B0 (Cadmus Computer Systems)

Nmap done: 1 IP address (1 host up) scanned in 0.09 seconds
```

**BLOG REFERENCES**<br />
http://blog.gdssecurity.com/labs/2015/3/11/nimbus-protocol-enumeration-with-nmap.html

