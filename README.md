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
