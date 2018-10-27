# JAX-RS

<table width="100%">
  <tr><th>JAXRS</th><th>MICRONAUT</th></tr>
  <tr><td colspan="4">URI DEFINITION</td></tr>
  <tr>
    <td>
      @ApplicationPath <br/>
      Global path
    </td>
    <td>
      @ApplicationPath("/api")
    </td>
    <td>
      NOT EXIST
    </td>
    <td>
      NOT EXIST
    </td>
  </tr>
  
  <tr>
    <td>
      @Path<br/>
      For single class<br/>
      Root resource classes<br/>
    </td>
    <td>
      @Path("/issues")
    </td>
    <td>
     @Controller("/issues")<br/>
      [URI Path Variables]
    </td>
    <td>
      @Controller
    </td>
  </tr>
</table>








@Path
For single method
@Path("start")
 


NOT EXIST  - you should use  Routing Annotations es. @Get(“/path”)
(JAXRS) HTTP Method Matching – (MICRONAUT) Routing Annotations
 [Micronaut is more COMPACT – they use one anntoation on method to indicate @Path + @(GET|POST|DELETE|HEAD|OPTIONS)]
@GET

@Get("/path")
@Get  
@POST

@Post(“/path”)
@Post(value = "/p", consumes=MediaType.TEXT_PLAIN)
@Post 
@DELETE

@Delete(“/path”)
@Delete
@PUT

@Put(“/path”)
@Put 
@HEAD


@Head 
@OPTIONS


@Options
NOT EXIST


@Trace 
NOT EXIST


@Patch
@MatrixParam
Matrix Param
public Customers getCustomersByName(@MatrixParam("firstname") String firstname,@MatrixParam("surname") String surname) { // URI : /customer/search;firstname=fiorenzo;surname=pizza


@DefaultValue("50")
public Customers getCustomersByAge(@DefaultValue("50") @QueryParam("age") int age) {






Consuming and Producing Content Types (MEDIA TYPE)


APPLICATION_ATOM_XML “application/atom+xml” APPLICATION_FORM_URLENCODED “application/x-www-form-urlencoded” APPLICATION_JSON “application/json” APPLICATION_OCTET_STREAM “application/octet-stream” APPLICATION_SVG_XML “application/svg+xml” APPLICATION_XHTML_XML “application/xhtml+xml” APPLICATION_XML “application/xml” MULTIPART_FORM_DATA “multipart/form-data” TEXT_HTML “text/html” TEXT_PLAIN “text/plain” TEXT_XML “text/xml” WILDCARD “*/*”
MediaType class => MULTIPART_FORM_DATA



Returned Types


Object  => 

Response
Response.ok().build();
Response.noContent().build();

ResponseBuilder






Consuming and Producing Content Types

@Produces
@Produces(MediaType.APPLICATION_XML)
@Produces(MediaType.TEXT_HTML)
@Produces
@Consumes
@Consumes(MediaType.APPLICATION_XML)
@Consumes([MediaType.APPLICATION_FORM_URLENCODED, MediaType.APPLICATION_JSON])
@Consumes
Contextual Information


@Context 
UriInfo uriInfo;

HttpHeaders, UriInfo, Request, SecurityContext, and Providers

getDefaultMediaType(@Context HttpHeaders headers


Building URIs


UriBuilder

URI uri = UriBuilder.fromUri("http://www.myserver.com")
.path("book").
Path("1234")
.build(); assertEquals("http://www.myserver.com/book/1234", uri.toString());
UriMatchTemplate 
UriTemplate.
