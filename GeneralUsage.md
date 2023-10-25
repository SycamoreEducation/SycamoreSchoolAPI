# Endpoint Usage

As discussed in the introductory chapter, our API is consumed via HTTP requests. Each resource (noun) can be accessed by visiting (or querying) a specially formatted URI. Let's take a look at what the URI would look like when we want to view a specific news article.

https://app.sycamoreschool.com/api/v1/School/1002/News/22323

Let's eat this elephant one bite at a time.

1. Protocol: https://
  - All requests should be pointed to our domain over SSL.
2. Domain: app.sycamoreschool.com
  - The same great website you know and love
3. Directory: /api
  - Sycamore offers multiple sub-directory sites like /admissions and /kiosk. /api will point your browser to the API.
4. Version: /v1
  - Our API will evolve over time. To keep backwards compatibility, we will attempt to version each release. This will allow new features and options to be added to the API without breaking existing apps that consume it.
5. Resouce: /School/1002/News/12345
  - Everything after the version number will be a direct line to the resource that you're attempting to access. The general pattern will be a resource (a noun) with a slash followed by an ID if you're looking for a specific resource.

This covers the basic usage of the API. However, to make a successful API call you will need to provide additional pieces of information depending on which resource you are attempting to access. In the next chapter, we will review our security proceedures and access control.
