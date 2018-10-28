# JAX-RS

<table width="80%">
  <tr>
    <th>JAXRS</th>
    <th></th>
    <th></th>
    <th>MICRONAUT</th>
  </tr>
  <tr><td colspan="4"><div align="center">URI DEFINITION</div></td></tr>
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
  <tr>
    <td>
      @Path<br/>
      For single method
    </td>
    <td>
      @Path("start")
    </td>
    <td>
    </td>
    <td>
     NOT EXIST  - you should use  Routing Annotations es. @Get(“/path”)
    </td>
  </tr>
  <tr>
    <td colspan="4">
        <div align="center">
          (JAXRS) HTTP Method Matching – (MICRONAUT) Routing Annotations
 [Micronaut is more COMPACT – they use one anntoation on method to indicate @Path + @(GET|POST|DELETE|HEAD|OPTIONS)]
      </div>
    </td>
  </tr>
  <tr>
    <td>
     @GET
    </td>
    <td>
    </td>
    <td>
    @Get("/path")
    </td>
    <td>
     @Get  
    </td>
  </tr>
  <tr>
    <td>
    @POST
    </td>
    <td>
    </td>
    <td>
    @Post(“/path”) <br/>
    @Post(value = "/p", consumes=MediaType.TEXT_PLAIN)
    </td>
    <td>
     @Post 
    </td>
  </tr>
    <tr>
    <td>
   @DELETE
    </td>
    <td>
    </td>
    <td>
   @Delete(“/path”)
    </td>
    <td>
    @Delete
    </td>
  </tr>
  <tr>
    <td>
   @PUT
    </td>
    <td>
    </td>
    <td>
 @Put(“/path”)
    </td>
    <td>
   @Put
    </td>
  </tr>
   <tr>
    <td>
   @HEAD
    </td>
    <td>
    </td>
    <td>
    </td>
    <td>
@Head 
    </td>
  </tr>
   <tr>
    <td>
   @OPTIONS
    </td>
    <td>
    </td>
    <td>
    </td>
    <td>
@Options
    </td>
  </tr>
   <tr>
    <td>
   NOT EXIST
    </td>
    <td>
    </td>
    <td>
    </td>
    <td>
@Trace 
    </td>
  </tr>
  <tr>
    <td>
   NOT EXIST
    </td>
    <td>
    </td>
    <td>
    </td>
    <td>
@Patch 
    </td>
  </tr>
    <tr>
    <td>
   @MatrixParam
    </td>
    <td>
      Matrix Param
public Customers getCustomersByName(@MatrixParam("firstname") String firstname,@MatrixParam("surname") String surname) { // URI : /customer/search;firstname=fiorenzo;surname=pizza
    </td>
    <td>
    </td>
    <td>
?? 
    </td>
  </tr>
   <tr>
    <td>
   (@DefaultValue
    </td>
    <td>
     public User byCodeId(@DefaultValue("50") @QueryParam("id") int id) {...}
    </td>
    <td>
    </td>
    <td>
?? 
    </td>
  </tr>
   <tr>
    <td colspan="4">
        <div align="center">
         Consuming and Producing Content Types (MEDIA TYPE)
      </div>
    </td>
  </tr>
   <tr>
    <td>
    </td>
    <td>
    APPLICATION_ATOM_XML “application/atom+xml” APPLICATION_FORM_URLENCODED “application/x-www-form-urlencoded” APPLICATION_JSON “application/json” APPLICATION_OCTET_STREAM “application/octet-stream” APPLICATION_SVG_XML “application/svg+xml” APPLICATION_XHTML_XML “application/xhtml+xml” APPLICATION_XML “application/xml” MULTIPART_FORM_DATA “multipart/form-data” TEXT_HTML “text/html” TEXT_PLAIN “text/plain” TEXT_XML “text/xml” WILDCARD “*/*”
    </td>
    <td>
      MediaType class => MULTIPART_FORM_DATA
    </td>
    <td>
    </td>
  </tr>
   <tr>
    <td colspan="4">
        <div align="center">
          Returned Types
      </div>
    </td>
  </tr>
   <tr>
    <td colspan="4">
        <div align="center">
         Consuming and Producing Content Types (MEDIA TYPE)
      </div>
    </td>
  </tr>
   <tr>
    <td>
    </td>
    <td>
    Object  => 
Response
Response.ok().build();
Response.noContent().build();
ResponseBuilder
    </td>
    <td>
???    </td>
    <td>
    </td>
  </tr>
  <tr>
    <td colspan="4">
        <div align="center">
          Consuming and Producing Content Types
      </div>
    </td>
  </tr>
   <tr>
    <td>
      @Produces
    </td>
    <td>
   @Produces(MediaType.APPLICATION_XML)
    </td>
    <td>
  @Produces(MediaType.TEXT_HTML)    
  </td>
    <td>
      @Produces
    </td>
  </tr>
   <tr>
    <td>
     @Consumes
    </td>
    <td>
   @Consumes(MediaType.APPLICATION_XML)
    </td>
    <td>
  @Consumes([MediaType.APPLICATION_FORM_URLENCODED, MediaType.APPLICATION_JSON])
  </td>
    <td>
     @Consumes
    </td>
  </tr>
    <tr>
    <td colspan="4">
        <div align="center">
          Contextual Information
      </div>
    </td>
  </tr>
     <tr>
    <td>
      @Context 
      HttpHeaders, UriInfo, Request, SecurityContext, and Providers
    </td>
    <td>
   @Context 
UriInfo uriInfo;

getDefaultMediaType(@Context HttpHeaders headers
    </td>
    <td>
  </td>
    <td>
    </td>
  </tr>
   <tr>
    <td colspan="4">
        <div align="center">
          Building URIs
      </div>
    </td>
  </tr>
   <tr>
    <td>
    </td>
    <td>
 UriBuilder
URI uri = UriBuilder.fromUri("http://www.myserver.com")
.path("book").
Path("1234")
.build(); assertEquals("http://www.myserver.com/book/1234", uri.toString());
    </td>
    <td>
  </td>
UriMatchTemplate 
UriTemplate.
    <td>
    </td>
  </tr>
</table>

