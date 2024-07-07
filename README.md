# ENDPOINT-log-Analysis
<h2>Description</h2>
Project consists of a simple of endpoint log analysis of a wordpress log file and answers some questions <br/>
<br />
<h2>Platforms and Technology Used</h2>

- <b>Virtual Box </b>
- <b>Ubuntu 22.4</b>
- <b>Worpress log zip file</b>
- <b>Pass: btloe</b>

<h2>Lab walk-through:</h2>

<h2>Here is the scenario we are going to work in this lab</h2>

![scenario](https://github.com/princemilkan/ENDPOINT-log-Analysis/assets/25425389/4d098d7e-af53-4b96-9cb5-395913d81c93)

<h2>Unzip the Wordpress.zip 📂 </h2>

![1 Unzip file](https://github.com/princemilkan/ENDPOINT-log-Analysis/assets/25425389/ec5d2bbf-9846-47a5-a280-00860fc6dbb3)

<h2>First 10 lines of the log</h2>

![2  first 10 lines of the log](https://github.com/princemilkan/ENDPOINT-log-Analysis/assets/25425389/d45e7221-c08b-4266-8d5f-b061827802fa)


<h2>Last 10 lines of the log</h2>

![3 last 10 lines of the log](https://github.com/princemilkan/ENDPOINT-log-Analysis/assets/25425389/8e5fbfb1-b920-4289-a204-1270f545560b)


<h2>Putting sorted ips into a file name IPs.txt</h2>

![5 putting sorted ips into a file](https://github.com/princemilkan/ENDPOINT-log-Analysis/assets/25425389/62d3ffe6-5c86-4482-b565-45119bbda79c)

<h2>Sorting user agents and ptting into file names useragents.txt</h2>

![6 sorting user agents and ptting into file](https://github.com/princemilkan/ENDPOINT-log-Analysis/assets/25425389/94d20da0-3112-444f-8ee6-2097d489388a)

<h2>sorting POSt commands excluding 403 error</h2>

![7 sorting POSt commands excluding 403 error](https://github.com/princemilkan/ENDPOINT-log-Analysis/assets/25425389/ac0f87ba-5682-4698-b400-594ecd8e5392)

<h2>sorting post commands along with ips and top hits</h2>

![8 sorting post commands along with ips and top hits](https://github.com/princemilkan/ENDPOINT-log-Analysis/assets/25425389/f870b2a6-c7df-4b7c-ab56-71a2b63b28fc)

<h2>suspicious file post request from this IP 103.69.55.212</h2>

![11 suspicious file post request from this IP](https://github.com/princemilkan/ENDPOINT-log-Analysis/assets/25425389/f99a47aa-26fe-48d9-b8f6-21c07a21d1e8)

<h2>suspicious activities from 119.241.22.121</h2>

![16 suspicious activities from 119 241 22 121](https://github.com/princemilkan/ENDPOINT-log-Analysis/assets/25425389/9db90cc7-5c50-4dcf-bb2e-25099f95cfcc)
![17 more   suspicious activities from 119 241 22 121](https://github.com/princemilkan/ENDPOINT-log-Analysis/assets/25425389/2ddaa141-cd5a-406e-8b72-7a4c7d2704fe)
![17 more suspicious activities from 119 241 22 121](https://github.com/princemilkan/ENDPOINT-log-Analysis/assets/25425389/9edc6c8b-fea5-467a-9631-62ab0b0762cb)


<h2>OSINT on both IP 119.241.22.121 and 103.69.55.21</h2>

![9 checking te 2nd ip in abuseipdb](https://github.com/princemilkan/ENDPOINT-log-Analysis/assets/25425389/4e7f5749-35b0-49e6-ad41-e02c5dc9aa48)
![10  checking te 2nd ip in virus total](https://github.com/princemilkan/ENDPOINT-log-Analysis/assets/25425389/7c32f4d6-4138-4684-8e44-7b669d823394)
![16 OSINT on IP 119 241 22 121](https://github.com/princemilkan/ENDPOINT-log-Analysis/assets/25425389/2b41a70e-30e8-480f-82cf-e6507a716284)
![17 OSINT on IP 119 241 22 121](https://github.com/princemilkan/ENDPOINT-log-Analysis/assets/25425389/c1771d26-0152-40ba-a44b-301538f7c7ea)


<h2>CVE found for contact form plugin and 
Found arbitrarycode for file simple file listand it's Remote Code Execution is pre authorised</h2>


![13 CVE found for contact form plugin](https://github.com/princemilkan/ENDPOINT-log-Analysis/assets/25425389/71ddabda-79d2-446e-83c1-584d9605fb3a)
![14 found arbitrarycode for file simple file listand it's Remote Code Execution is pre authorised ](https://github.com/princemilkan/ENDPOINT-log-Analysis/assets/25425389/12a41f51-41bf-4d11-b06b-ab3e68d3fd4b)

<h2>contact form7 plugin was first activated</h2>

![18 contact form7 plugin was first activated](https://github.com/princemilkan/ENDPOINT-log-Analysis/assets/25425389/83608869-050a-49c0-956f-2e31cb522429)

<h2>simple file list plugin was first activated</h2>

![19 simple file list plugin was first activated](https://github.com/princemilkan/ENDPOINT-log-Analysis/assets/25425389/64018db4-da7e-4326-96eb-49970807074d)

<h1>Observations</h1>
<h2> 🔎 January 12 @ 15:56:41 UTC

Plugin: contact-form-7 was activated

January 12 @ 15:57:07 UTC

Plugin: simple-file-list was activated

Both plugins have vulnerabilities to RCE

contact-form-7 - Vulnerable versions <= 5.3.1 </br>
simple-file-list - Vulnerable versions <= 4.2.2</h2>

<h2> 🔎 First external IP activity

January 14th @ 05:42:34 UTC
IP: 119.241.22.121 - Japan
Interacting with both plugins
Crawling file paths on 172.21.0.3

January 14th @ 05:54:14 UTC
Identified Token: adminlogin
Full URI: wp-login.php?itsec-hb-token=adminlogin</h2>

<h2> 🔎 January 14 @ 06:01:41 UTC
IP: 119.241.22.121 - Japan
Used tool: WPScan (WordPress Scanner)
  
January 14th @ 06:08:31 UTC
IP: 103.69.55.212 - Taiwan
Crawling plugins on 172.21.0.3

January 14th @ 06:26:53 UTC
IP: 119.241.22.121 - Japan
Exploited plugin: simple-file-list
Uploaded file named: fr34k.png</h2>

<h2> 🔎 GET Request towards fr34k.php
IP: 103.69.55.212 - Taiwan

LAST OBSERVED ACTIVITY
IP: 119.241.22.121 - Japan
January 14 @ 06:26:53 UTC
IP: 103.69.55.212 - Taiwan
January 14 @ 06:30:11 UTC

Total Duration: 47 Minutes & 37 Seconds</h2>


<h2>Some Questions and answers based on the log findings</h2>

![questions](https://github.com/princemilkan/ENDPOINT-log-Analysis/assets/25425389/f70a75d6-c2e1-40ec-9b6e-324c7e77f4cd)








