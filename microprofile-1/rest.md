---
description: Rest api -  a little comparation
---

# jax-rs

| JAXRS |  |  | MICRONAUT |
| :--- | :--- | :--- | :--- |
| URI DEFINITION |  |  |  |
|  @ApplicationPath  Global path |  @ApplicationPath\("/api"\) |  NOT EXIST |  NOT EXIST |
|  @Path  For single class  Root resource classes  |  @Path\("/issues"\) |  @Controller\("/issues"\)  \[URI Path Variables\] |  @Controller |
|  @Path  For single method |  @Path\("start"\) |  |  NOT EXIST  use Routing Annotations es. @Get\(“/path”\) |
|  \(JAXRS\) HTTP Method Matching – \(MICRONAUT\) Routing Annotations  Micronaut use one annotation instead of two annotations: @Path + @\(GET\|POST\|DELETE\|HEAD\|OPTIONS\) |  |  |  |
|  @GET |  |  @Get\("/path"\) |  @Get |
|  @POST |  |  @Post\(“/path”\)  @Post\(value = "/p", consumes=MediaType.TEXT\_PLAIN\) |  @Post |
|  @DELETE |  |  @Delete\(“/path”\) |  @Delete |
|  @PUT |  |  @Put\(“/path”\) |  @Put |
|  @HEAD |  |  |  @Head |
|  @OPTIONS |  |  |  @Options |
|  NOT EXIST |  |  |  @Trace |
|  NOT EXIST |  |  |  @Patch |
|  @MatrixParam |  Matrix Param public Customers getCustomersByName\(@MatrixParam\("firstname"\) String firstname,@MatrixParam\("surname"\) String surname\) {}  // URI : /customer/search;firstname=fiorenzo;surname=pizza |  |  ?? |
|  \(@DefaultValue |  public User byCodeId\(@DefaultValue\("50"\) @QueryParam\("id"\) int id\) {...} |  |  ?? |
|  Consuming and Producing Content Types \(MEDIA TYPE\) |  |  |  |
|  |  APPLICATION\_ATOM\_XML “application/atom+xml”  APPLICATION\_FORM\_URLENCODED “application/x-www-form-urlencoded”  APPLICATION\_JSON “application/json”  APPLICATION\_OCTET\_STREAM “application/octet-stream”  APPLICATION\_SVG\_XML “application/svg+xml”  APPLICATION\_XHTML\_XML “application/xhtml+xml”  APPLICATION\_XML “application/xml”  MULTIPART\_FORM\_DATA “multipart/form-data”  TEXT\_HTML “text/html” TEXT\_PLAIN “text/plain”  TEXT\_XML “text/xml” WILDCARD “\*/\*” |  MediaType class =&gt; MULTIPART\_FORM\_DATA |  |
|  Returned Types |  |  |  |
|  Consuming and Producing Content Types \(MEDIA TYPE\) |  |  |  |
|  |  Object =&gt;  Response  Response.ok\(\).build\(\);  Response.noContent\(\).build\(\);  ResponseBuilder  |  ??? |  |
|  Consuming and Producing Content Types |  |  |  |
|  @Produces |  @Produces\(MediaType.APPLICATION\_XML\) |  @Produces\(MediaType.TEXT\_HTML\) |  @Produces |
|  @Consumes |  @Consumes\(MediaType.APPLICATION\_XML\) |  @Consumes\(MediaType.APPLICATION\_XML\) |  @Consumes |
|  Contextual Information |  |  |  |
|  @Context HttpHeaders, UriInfo, Request, SecurityContext, and Providers |  @Context  UriInfo uriInfo;  public void getDefaultMediaType\(@Context HttpHeaders headers\){} |  |  |
|  Building URIs |  |  |  |
|  |  UriBuilder URI uri = UriBuilder.fromUri\("http://www.myserver.com"\) .path\("book"\). Path\("1234"\) .build\(\);  // http://www.myserver.com/book/1234 |  |  UriMatchTemplate  UriTemplate.  |

