# 307 Temporary Redirect  
* 요청 시 307응답이 오면 **Location** 헤더에 재요청할 URL이 딸려온다.  
* 브라우져는 이 URL에 다시 요청을 수행한다.  

```
HTTP/1.1 307 Temporary Redirect
Server: nginx/1.14.0 (Ubuntu)
Date: Fri, 19 Jun 2020 11:49:54 GMT
Content-Type: text/html
Content-Length: 196

>> Location: http://127.0.0.1:8888/thumb.png <<

Connection: keep-alive
```

```
GET ------------------------------->
    
    <------------------------------- 307 
          Location : hello

GET ------------------------------>
        URL : hello
```


# 302와 차이점  
* 307은 첫 요청 시의 **메서드**와 **body**를 그대로 사용할 것이 보장된다.  

