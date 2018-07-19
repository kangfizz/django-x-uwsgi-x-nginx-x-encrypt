
## 步驟1. 在linode建立server
(記得使用coupon購買,優惠很多)  
 Ubuntu 16.04 LTS Disk
 
 ## 步驟2. 建立django 
1.<code> python3 -m venv django_venv </code>  
2.<code> source django_venv/bin/activate </code>  
3.<code> pip install "django<1.12" </code>  
4. (其它參照 django girls,做到hello world即可)  
5. 設置staticfile(https://docs.djangoproject.com/en/1.11/howto/static-files/ 與 https://stackoverflow.com/questions/15491727/include-css-and-javascript-in-my-django-template)  

## 步驟3. Godaddy網域(Domain Name)購買
(記得使用coupon購買,優惠很多)  
![123](https://i.imgur.com/xrpJ727.png)

## 步驟4. 建立uwsgi 與 nginx
參照 hack 的 wiki 
* (你的根目錄為你django的project)

## 步驟5. 用letencrypt 建立SSL連線(HTTPS)

參照 小知識的 SSL PDF  
與  
https://imliyan.com/blogs/article/%E4%BD%BF%E7%94%A8Let%27s%20Encrypt%E9%83%A8%E7%BD%B2TLS%E8%AF%81%E4%B9%A6/  

(最後重啟 <code> sudo systemctl restart nginx </code>)

## 額外1. 將http 轉址為 https

https://bjornjohansen.no/redirect-to-https-with-nginx  

````
server {
    listen 80;
    listen [::]:80;
    server_name MYDOMAIN www.MYDOMAIN.com;

    return 301 https://www.MYDOMAIN.com;
}
````
