---
description: '@PostConstruct and @PreDestroy (like in java ee Enterprise Java Beans)'
---

# Life-Cycle Methods

## Annotations for methods, using PostConstruct and PreDestroy 

In micronaut you can define init method:

```
    @PostConstruct
    private void start() {
        System.out.println(" init method");
    }

```

and pre destroy:

```text

    @PreDestroy
    private void end() {
        System.out.println(" end method");
    }


```



