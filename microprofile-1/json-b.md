---
description: Micronaut use Jackson for JSON Binding
---

# json-b

## Difference between JsonB and Jackson

From: [https://www.ibm.com/developerworks/library/j-javaee8-json-binding-4/index.html](https://www.ibm.com/developerworks/library/j-javaee8-json-binding-4/index.html)

#### JSON-B <a id="N100A8"></a>

JSON ****Binding ****API. Developers access JSON Binding’s runtime configuration via the `JsonConfig` class:

```
JsonbConfig jsonbConfig = new JsonbConfig()
    .with...(...);
 
String json = JsonbBuilder
    .create(jsonbConfig)
    .toJson(...);
 
AnObject anObj = JsonbBuilder
    .create(jsonbConfig)
    .fromJson("{JSON}", AnObject.class);
```

#### Jackson <a id="N100CB"></a>

 This engine is then used to perform serialization and deserialization on the target object.

```text
ObjectMapper objectMapper = new ObjectMapper()
    .set...(...)
    .configure(...)
    .addHandler(...)
    .disable(...)
    .enable(...)
    .registerModule(...)
    ...;
 
String json = objectMapper
    .writeValueAsString(...);
 
AnObject anObj = objectMapper
    .readValue("{JSON}", AnObject.class);
```

{% hint style="info" %}
 More info:

[https://docs.micronaut.io/latest/guide/index.html\#jsonBinding](https://docs.micronaut.io/latest/guide/index.html#jsonBinding)
{% endhint %}

