# HTTP  
[MDN](https://developer.mozilla.org/ko/docs/Web/HTTP/Messages)  

* ASCII로 인코딩된다.  
* Case insensitive 하다.  


# HTTP Message  

* Http Message는 서버 - 클라이언트 간 데이터를 교환하는 방식.  
* **HTTP 메세지 타입**은 두 가지가 있다.  
1. 요청  
2. 응답  

* HTTP 메세지는 **ASCII로 인코딩된 텍스트 정보**  
[+] ASCII : 7bit로 구성 / 영어문자, 숫자, 특수문자 128자 표현  

# 구조  
![스크린샷, 2020-06-03 23-30-04](https://user-images.githubusercontent.com/62331555/83649465-2fbff780-a5f2-11ea-8a1e-d89f4b3e8701.png)  

1. **Start-Line** : 항상 한줄  
2. **HEADER** : '옵션`  
3. **Blank Line** : 요청에 대한 모든 `메타정보`가 전송되었음을 알림.  
4. **BODY** : `옵션` 요청과 관련된 내용(Form) / 응답의 결과(document)  



# HTTP 요청  

## 1. Start Line  
* 세 가지로 이뤄진다.  
```
GET /hello/world HTTP/1.1
```

1. **HTTP METHOD** : 서버가 수행해야 할 동작을 의미  
* [HTTP method](https://github.com/horoyoiiv/HTTP/blob/master/docs/http_method.md)  
예를 들어) GET - `리소스`를 클라이언트로 가져달라는 요청 / POST - `리소스`를 서버에 저장함을 알리는 요청  

  
2. **요청 타겟**  
* 주로 URL 혹은 `프로토콜:도메인:포트:패쓰`의 절대경로 삽입  
```
POST /user HTTP/1.1
HEAD /test.html?query=string HTTP/1.1
```

* 절대 경로 : 주로 프록시에 연결하는 경우 GET과 함께 사용.  
```
GET http://developer.mozilla.org/en-US/docs/Web/HTTP/Messages HTTP/1.1
```


3. **HTTP 버전**  
**http의 구조를 식별**하기 위함이다.  

## 2. 요청 헤더  
* 대소문자의 구분이 없다.  
* `:` 을 기준으로 key - value 형태로 사용.  
* 헤더는 값까지 포함하여 한 줄로 표현된다.  
* 값 앞의 빈 문자열을 무시된다.  

## 3. 본문  
* 요청의 마지막에 들어간다.  
* 두 가지 종류  

1. **단일-리소스 본문**  
헤더 두 개(Content-Type & Content-Length)로 정의된 단일 파일로 구성.  

2. **다중-리소스 본문**  
멀티파트 본문은 **본문이 파트마다 다른 정보**를 가질 수 있다.  











