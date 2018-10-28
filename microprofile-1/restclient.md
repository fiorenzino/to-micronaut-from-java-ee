---
description: Micronaut client annotation to handle http requests.
---

# restclient

## HTTP Client with @Client

Declarative HTTP Clients with @Client 

```
https://docs.micronaut.io/latest/api/index.html
```

{% hint style="info" %}
 The [@Client](https://docs.micronaut.io/latest/api/io/micronaut/http/client/Client.html) annotation can also handle streaming HTTP responses  
[https://docs.micronaut.io/latest/guide/index.html\#clientAnnotation](https://docs.micronaut.io/latest/guide/index.html#clientAnnotation)
{% endhint %}

```
@Client(path="http://locahost:8080/users")
public interface UsersClient {

    @Get(value = "/{uuid}") 
    User get(String uuid); 
}
```

At end, you can inject in other controller/service:

```text
@Controller("/tickets")
public class TicketsController {

    @Inject 
    TicketRepository ticketRepository;
    
    @Inject
    UsersClient usersClient;
    
    @Get("/{uuid}")
    public Ticket get(String uuid) {
        Ticket ticket = ticketRepository.find(uuid);
        return ticket;
    }

    @Get("/{uuid}/user")
    public User user(String uuid) throws Exception {
        Ticket ticket = ticketRepository.find(uuid);
        if(ticket == null) 
            throw New 
        User user = usersClient.get(ticket.getUserUuid();
        return user;
    }
    
}
```

In Microprofile \([https://openliberty.io/guides/microprofile-rest-client.html](https://openliberty.io/guides/microprofile-rest-client.html)\)

```text
@RegisterRestClient
@Path("/properties")
public interface SystemClient {

  @GET
  @Produces(MediaType.APPLICATION_JSON)
  public Properties getProperties() throws UnknownUrlException, ProcessingException;
}
```

And you can inject in a service:

```text
@ApplicationScoped
public class InventoryManager {


  @Inject
  @RestClient
  private SystemClient defaultRestClient;
  
  
   private Properties getPropertiesWithDefaultHostName() {
      return defaultRestClient.getProperties();
  }
  
  }
```



