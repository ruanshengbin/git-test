# git-test
git-test

```java
    private void frontCustomNewSpan() {
        Span newSpan = tracer.createSpan("frontCustomNewSpan");
        try {
            newSpan.logEvent("frontCustomNewSpan-start");
            newSpan.tag("frontCustomNewSpan-test", "test");
            zipkinTestUtil.randomSleep(3);
            zipkinTestUtil.randomThrowException(0.4F);
        } finally {
            newSpan.logEvent("frontCustomNewSpan-finish");
            tracer.close(newSpan);
        }
    }
```

```shell
java -jar spring-zipkin-example-1.5.9.RELEASE.jar --server.port=8888 --spring.application.name=zipkin-test-front --spring.zipkin.baseUrl=http://127.0.0.1:9411/ --backend.url=http://127.0.0.1:8889
```
