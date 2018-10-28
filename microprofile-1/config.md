# config

## Inject config properties 

Becoming a super hero is a fairly straight forward process:

[https://docs.micronaut.io/latest/guide/index.html\#valueAnnotation](https://docs.micronaut.io/latest/guide/index.html#valueAnnotation)

For example, from `application.yml` configuration file:

```
datasources:
    default:
        name: 'mydb'
jpa:
    default:
        properties:
            hibernate:
                hbm2ddl:
                    auto: update
                show_sql: true
```

To inject a property or properties:

```
@Property(name = "jpa.default.properties")
Map<String, String> jpaProperties;
```



