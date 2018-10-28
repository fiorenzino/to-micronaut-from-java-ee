---
description: Event system through the context (similar to CDI events)
---

# Context Events

## Publishing & Listening Events

A simple custom event

```text

public class SimpleEvent {

    public String txt;

    public SimpleEvent(String txt) {
        this.txt = txt;
    }

    @Override
    public String toString() {
        return "SimpleEvent{" +
                "txt='" + txt + '\'' +
                '}';
    }
}

```

Simple Publisher

```
@Controller("/hello")
public class HelloController {


    @Inject
    ApplicationEventPublisher eventPublisher;


    @Get("/name/{name}")
    public String name(String name) {
        eventPublisher.publishEvent(new SimpleEvent("Hello " + name));
        return "Hello " + name;
    }
}
```

Simple Receiver

```text

@Singleton
public class SimpleEventReceiver {

    @EventListener
    void onStartup(SimpleEvent event) {
        System.out.println(event.toString());
    }
}

```

In CDI \([https://dzone.com/articles/an-overview-of-cdi-events](https://dzone.com/articles/an-overview-of-cdi-events)\)

Simple event publisher in CDI:

```text
@Named
public class CdiSimpleEventPublisher {
    @Inject
    private Event<SimpleEvent> simpleEvent;
    
    public void fireEvent(){
          simpleEvent.fire(new SimpleEvent("Hello " + name));
    }
}
```

Simple event receiver in CDI:

```text
@Named
public class CdiSimpleEventReceiver {
    public void observeEvent(@Observes SimpleEvent simpleEvent){
          System.out.println(event.toString());
    }
}
```

