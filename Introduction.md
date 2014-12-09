<img src="https://app.sycamoreeducation.com/images/SycamoreSchool_banner_small.png" style="display: block; margin: 0px auto;" title="Sycamore Logo" />

Sycamore School now offers an API that allows you to get access to data within our system without actually being in our system. If you are a programmer or developer, you can use our API to query our database to extract and manipulate certain pieces of data. This folder will walk you through exactly what an API is, how you can use ours and lay out all of the types of data that you can access.

## What Is An API?

API is an acronym that stands for 'application programming inferface'. It's a fancy-schmancy term that means 'a way that you can talk with our system'. You use APIs every time that you use a computer. There is an API for your mouse to "talk" with your computer. There is an API for you to log into your favorite website with your Facebook account. There is an API for Words With Friends. APIs are everywhere.


## What are the different kinds of APIs?

There are a few different types of APIs out there today. Some of them are easier to work with than others. Over the last 5 years, one type of API has risen highly in popularity: the REST API. REST stands for 'representational state transfer' and is a method proposed in Roy Thomas Fielding's doctoral dissertation. A REST API is simply an API that adheres to certain design standards and ideologies. Unfortunately, some of those ideologies are hard to comply with or simply don't make sense in certain instances. Sycamore' API tries to follow the REST principals that make sense for our use. For this reason, our API is considered 'REST-like'.

## What Does REST Mean?

REST APIs uses HTTP methods to perform actions on resources. Woah, that's a lot of acronyms. Let's walk through them

- API (application programming interface) A way for one program to communicate with another
- REST A method of structuring an API
- HTTP (Hyper Text Transfer Protocol) The language of the Internet

Every single time that you browse a web page on the Internet, you're using HTTP methods. When you loaded this page, your browser sent a GET HTTP request to our server that then sent a response to your browser that included a lot of "meta data" about the response and the actual HTML code for the web page you're currently viewing. Who would have thought so much stuff happened when you clicked a link on the internet!


## What is a resource?

Good question! A resource is an object (noun) that is exposed from an API. In the Sycamore Education API, a resouce may be a student, or a student's grades. It could be a list of news articles, or maybe a single calendar event. These resources are exposed via URIs (or sometimes called URLs). URI stands for universal resource indicator. You're already very familiar with URIs- you use them every time you use the internet. app.sycamoreeducation.com is the universal resource indicator for our servers where Sycamore Education resides. When you type in that URI, the browser go and looks for the resources located at that address. Sometimes those resources are HTML web pages, sometimes they are hypermedia like music of videos. Other times they are straight data- like our API. When a URI is mentioned in terms of an API, it can often be referred to as an 'end point'. An example of an end point for our API would be app.sycamoreeducation.com/api/v1/School/1002/Students/2342/Grades. We'll talk more about our URI structure in the next chapter.

## What HTTP methods can be used with an API?

Typically, there are 3 HTTP methods that can be used with our API: GET, POST, and DELETE. Each one performs a different action on a resource. GET will request some information from the API. POST will create a new resource or update an existing one. DELETE...well, you can probably guess what DELETE does. Sycamore's API doesn't include all of these method for every resource. For more detailed information about what methods are allowed per resource, please check out the endpoint that you are curious about.
