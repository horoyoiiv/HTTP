

# Cache-Control  
* HTTP 응답 결과를 어떻게 캐싱할 것인지에 대하여 결정하는 `디렉티브`  

```
HTTP/1.1 200 OK

Server: nginx/1.14.0 (Ubuntu)
...
[Cache-Control: no-store] 
...
Content-Encoding: gzip
```


## 1. no-store  
* `no-store` 가 value로 오게 되면 어디서도 이 응답이 캐시되어서는 안됨을 의미.  

```
Cache-Control: no-store
```
## 1.1. 결과  
* 매번 요청이 서버로부터 응답을 가져온다.  

![스크린샷, 2020-06-07 19-28-39](https://user-images.githubusercontent.com/62331555/83966423-2043f580-a8f5-11ea-87cb-abb3f3157609.png)  


## 2. max-age  
* `max-age`를 통하여 얼마나 캐싱된 곳에 저장할지를 결정한다.  
* **초 단위**  

```
Cache-Control: max-age=10
```
* 10초 동안은 메모리나 디스크에서 읽어오고, 10초 후 만료되면 다시 서버로 요청을 보낸다.  

## 2.1. 결과  
![스크린샷, 2020-06-07 19-38-58](https://user-images.githubusercontent.com/62331555/83966688-91d07380-a8f6-11ea-9f58-8ce12da14553.png)  
[+] 첫번째 img.png 파일은 memory에서 가져온다.  
[+] 두번째 img.png 파일은 만료되었기에 서버로 요청한다.  







