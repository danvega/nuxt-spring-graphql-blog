# Nuxt Blog + Spring GraphQL

This is a sample project that shows how to use Nuxt with Spring GraphQL. In this project the Nuxt application is using 
the Nuxt GraphQL Client Module to query the Spring GraphQL API.

## Getting Started 

To run the application you will need to to run the Spring Boot application first: 

```bash
mvn spring-boot:run
```

And then from the `/src/main/frontend' directory you can run the Nuxt application:

```bash
npm run dev
````

## Loading Data

In this first part of this tutorial I am going to query my existing blog to get some data that we can load into our
application and make that available in the GraphQL API. If you want to run my site locally you can do so by cloning
[this repository](https://github.com/danvega/danvega-dev). If you run the application you can visit the following URL
to see the GraphQL Playground. From there I run the following query to get the last 100 posts. 

Run http://localhost:8080/___explore

```graphql
query {
  allPost(limit:100){
  	edges {
    	node {
        id
        title
        slug
        date(format:"MM/DD/YYYY")
        timeToRead
        tags {
          title
        }
      }
  	} 
  }
}
```

You can copy the results to `/src/main/resources/data/blog-posts.json` and then we can use that data to load into our
in-memory database.

## Building out the UI 


Nuxt UI
https://ui.nuxtlabs.com/data/table 


Nuxt GraphQL Client 

https://nuxt-graphql-client.web.app/