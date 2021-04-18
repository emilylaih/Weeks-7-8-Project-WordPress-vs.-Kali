# Weeks-7-8-Project-WordPress-vs.-Kali

Time spent: **X** hours spent in total

> Objective: Find, analyze, recreate, and document **five vulnerabilities** affecting an old version of WordPress

## Pentesting Report

### 1.  WordPress <= 5.2.3 Stored XSS in Style Tags, ID CVE-2019-17672
  - [x] Summary:
    - Vulnerability types: Cross-site Scripting
    - Tested in version: WordPress 4.2
    - Fixed in version: 4.2.25
  - [x] GIF Walkthrough:
 <img src='https://user-images.githubusercontent.com/57808274/114906218-ad39c400-9dce-11eb-9e0c-2c3fbd1e2eb6.gif' title='Video Walkthrough' width='800' alt='Video Walkthrough' />


  - [x] Steps to recreate: 
  1. First add a new post
  2. click add media in the add new post page and choose a picture to upload to the webpage
  3. insert <IFRAME SRC="javascript:alert('XSS attack!!!');"></IFRAME> code between the <a> tags in the text section to perform cross-site scripting attack.
  4. Click publish
  
 <img src='https://user-images.githubusercontent.com/57808274/114908884-639ea880-9dd1-11eb-91da-59f59bcd97e2.gif' title='Video Walkthrough' width='800' alt='Video Walkthrough' />

  - [x] Affected source code: https://blog.wpscan.com/wordpress/security/release/2019/10/15/wordpress-524-security-release-breakdown.html
    - [Link 1](https://wordpress.org/news/2019/10/wordpress-5-2-4-security-release/)
    - [Link 2](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2019-17672)  
### 2. WordPress < 5.4.2 - Disclosure of Password-Protected Page/Post Comments
  - [x] Summary: 
    - Vulnerability types:SENSITIVE DATA DISCLOSURE 
    - Tested in version:4.2
    - Fixed in version: 5.4.2
  - [x] GIF Walkthrough:  <img src='https://user-images.githubusercontent.com/57808274/115097439-1dd00600-9edf-11eb-8a66-4be18b49161e.gif' title='Video Walkthrough' width='800' alt='Video Walkthrough' />()
  - [x] Steps to recreate: 

1. Create a new post and set it to password-protect and then publish.
2. got to the password-protected page and comment 
3. after the admin approve the comment, navigate to the home page
4. click on recent comments that is password-protected comment
5. could see the comment and new post without entering password
  - [x] Affected source code:https://core.trac.wordpress.org/changeset/47984 
    - [Link 1](https://wpscan.com/vulnerability/eea6dbf5-e298-44a7-9b0d-f078ad4741f9)
    - [Link 2](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2020-25286)
### 3. WordPress 4.0-4.7.2 - Authenticated Stored Cross-Site Scripting (XSS) in YouTube URL Embeds
  - [x] Summary: 
    - Vulnerability types:Cross-site Scripting
    - Tested in version:4.2
    - Fixed in version:4.7.3
  - [x] GIF Walkthrough: <img src='https://user-images.githubusercontent.com/57808274/115135886-c4e09a80-9fd0-11eb-9d7a-8ace58460427.gif' title='Video Walkthrough' width='800' alt='Video Walkthrough' />()
  - [x] Steps to recreate:
1. Create a new post
2. type [embed src='https://youtube.com/embed/12345\x3csvg onload=alert(x)\x3e'][/embed] in the text area of the post
3. Click publish and it's done, users visitng the post will be affected by a XSS attack.
  - [x] Affected source code:https://github.com/WordPress/WordPress/commit/419c8d97ce8df7d5004ee0b566bc5e095f0a6ca8 
    - [Link 1]https://wpscan.com/vulnerability/3ee54fc3-f4b4-4c35-8285-9d6719acecf0?__cf_chl_jschl_tk__=1bbd38b1b3d23f8e1e6d9857ecb89ea5a1083ac3-1618724119-0-AdtoNWKKol433q1aWoJ9Q0vY9sNVR3v5wJVEcnDQ0gb3OG2Qtd0t30Jzc5nKg2kdv7k6B_snDb9i7uBoVjUscH-pphLrqKrj198Vr0p0FY8WS7doNhf8lyrLWcf7XiN6anIEUUGfXDb0DsbTHWp1gdt6_EogBo61RcSYNI5Pv951cXWsIZPCcxLhC4lnuSIgWEJAR1Lma80PcLlYL9B-HSPQHyxiUJfSHzbfp-RL3Ekenrd6VxHWW7-HJt3A-5Ya-xXJRP0nZjSLq0bEUfMaJbw4tK-qrPFUH7VFsBUT7H4aHU_M5nl0ORpAPc2I9lHtBF5QGfbY7q1f3aHQtF5DpO8nB3-2d43lEFPWbtdUKNJaMOs6ybAw2cOzq55bmQsIXlA9rWEheq5c_X14ekmIUUSCAQfO31epp5C-88vM9ZluCFYrkaIhWlT59ITYqqwrflLWy3zYG6v9NBnlGmibtJ1P29QLiMg06f_VTMrFof6Y7Agmth5amYugwJBWQ1YL8A
    - [Link 2] https://blog.sucuri.net/2017/03/stored-xss-in-wordpress-core.html
### 4. WordPress <= 4.2.2 - Authenticated Stored Cross-Site Scripting (XSS)
  - [x] Summary: 
    - Vulnerability types:Cross-Site Scripting
    - Tested in version:4.2
    - Fixed in version: 4.2.3
  - [x] GIF Walkthrough:  <img src='https://user-images.githubusercontent.com/57808274/115136268-839dba00-9fd3-11eb-9359-8dabd7220ab5.gif' title='Video Walkthrough' width='800' alt='Video Walkthrough' />
  - [x] Steps to recreate: 

<a href="[caption code=">]</a><a title=" onmouseover=alert('test')  ">link</a> 

  - [ ] Affected source code:
    - [Link 1]https://wpscan.com/vulnerability/0f027d7d-674b-4a63-9603-25ea68069c1d?__cf_chl_jschl_tk__=95a6de67264fd1e350aef454ed95b445c1af29fc-1618726071-0-AVs4MZPJ5McWrALJzYP6KPufKnjaeAvNe846Azhl5O5LGTaZV2kN_Voj_zEKOPhUN2vxIGqMOjGovmyGxDLu1p2p6JG3M5s7v0ef7z02gUUSuzQkLuteHPAHjnOD6NZvG18azSbPIkHl4e_3tcq_uAvhQXJe_k8CKl-CL1f5MMnvNcp8cZjVR_MdgzDbBl7GQW8rekitRsRCLURxQ1nBkguCJiRJdK9H9gV3bM9xh63FlWZl6OiDPwm8ZG4W0tBLrMO5rmIrLnlvhOHghlkWHoh0Gt3SqApWli7gCPXsPQYQmmndLNaiS1TsAHySGUv86v13TNfOfgUtF_7M1rk7ssUS3mGwzp4BdFjklCKHn3jyfDEWWTSOafkZV9U-v1he5qDZWx126B6l_wgvfUgqdk_E0jXdZPKZFzjyxLhVkUqwC2iDltk87DqIglMhIQ0ZwHLn0oXrg4k2c2E60eJgjFOjG7tDdkhgT9rwKAirzQYyTIotb0tD5pEtqMsNk-uhZQ
   -[Link 2]https://klikki.fi/adv/wordpress3.html
   -[Link 3]https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2015-5622
### 5. (Optional) Vulnerability Name or ID
  - [ ] Summary: 
    - Vulnerability types:
    - Tested in version:
  - [ ] GIF Walkthrough: 
  - [ ] Steps to recreate: 
  - [ ] Affected source code:
    - [Link 1](https://core.trac.wordpress.org/browser/tags/version/src/source_file.php) 

## Assets

List any additional assets, such as scripts or files

## Resources

- [WordPress Source Browser](https://core.trac.wordpress.org/browser/)
- [WordPress Developer Reference](https://developer.wordpress.org/reference/)

GIFs created with [LiceCap](http://www.cockos.com/licecap/).

## Notes

I couldn't run the webpage on my host machine probably due to my anti-virus software so I use my kali linux to browse the webpage and complete this assignment.
## License

    Copyright [yyyy] [name of copyright owner]

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
