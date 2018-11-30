---
layout: post
title:  "[Question][HttpDelete] spring-web lib 사용시 deleteMethod body 세팅 문제"
date:   2018-11-30 10:33:10 +0900
author: Hyunjoong Kim
categories: Question
tags: HttpDelete
---



[spring-web-3.1.1.RELEASE] <br>

CommonsClientHttpRequest.executeInternal()의 body 세팅 부에서 아래와 같이 EntityEnclosingMethod 클래스의 구현체에 대해서만 body를 세팅해주고 있다. 

```
if (this.httpMethod instanceof EntityEnclosingMethod) {
   EntityEnclosingMethod entityEnclosingMethod = (EntityEnclosingMethod) this.httpMethod;
   RequestEntity requestEntity = new ByteArrayRequestEntity(output);
   entityEnclosingMethod.setRequestEntity(requestEntity);
}
```

HttpDelete, HttpGet 은 HttpRequestBase를 상속받은 클래스이고, <br>

HttpPost, HttpPut은 HttpEntityEnclosingRequestBase를 상속받은 클래스이다. <br>HttpEntityEnclosingRequestBase는 EntityEnclosingMethod의 인터페이스 구현체이므로, 위에서 body를 세팅해준다. <br>

<br>

spring-web-5.1.2.RELEASE << 최신 라이브러리의 경우에, CommonsClientHttpRequest는 deprecated되었지만, <br>HttpComponentsClientHttpRequest , HttpComponentsAsyncClientHttpRequest 의 executeInternal()의 바디 세팅부에서 아래와 같이 동일하게 EntityEnclosingMethod 인터페이스의 구현체인지를 확인한다. <br>

```
if (this.httpRequest instanceof HttpEntityEnclosingRequest) {
    HttpEntityEnclosingRequest entityEnclosingRequest = (HttpEntityEnclosingRequest)this.httpRequest;
    HttpEntity requestEntity = new NByteArrayEntity(bufferedOutput);
    entityEnclosingRequest.setEntity(requestEntity);
}
```

<br>

[결론]

spring-web의 httpClient를 사용하는 경우에 Delete는 body를 담을수 없으니 삽질하지 마시길..ㅜㅜ