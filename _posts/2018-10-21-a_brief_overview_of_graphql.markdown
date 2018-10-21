---
layout: post
title:      "A Brief overview of GraphQL"
date:       2018-10-21 15:22:39 +0000
permalink:  a_brief_overview_of_graphql
---


RESTful APIs have been around for a long time now... around 18 years by the time of this posting. It's helped immensly as far as standarizing how API's work, particularly as far as CRUD actions go. However, as time goes by webapps evolve, demands on APIs evolve as well. While REST is perfectly functional and obiously still useful, some things aren't as performant as they could be. Enter GraphQL.
GraphQL is a specification that was developed and used by Facebook, which they then open sourced it in 2015. It is a different approach to building out an API and aims to be more efficient for modern development, specifically when lower bandwidth is involved.
Say we're building a social media app for sharing pictures. If I wanted to pull from their public API to display an index of a user's pictures. Depending on how the endpoints are put together, it might require several requests. We need to ask for the user's overall data, and get back something like this:
```
{
    user: {
        id: 1,
        name: 'ted',
        email: 'ted@example.com',
        images: [...] //array of image ID's,
        liked: [...] //array of like'd images
    }
}
```
We got what we need, but maybe too much. We don't necessarily need Ted's email address, and we'd still need to use the image IDs to pull in the actual images, requiring another request. We also don't need the array of liked images. Obviously not all API's would feature this structure, but it works for the sake of an example. In order to fix it and make it more efficient on the frontend, we'd need to communicate to the backend people to change it around. If it's a one person operation that might not be an issue, but either way, it adds a layer. REST API endpoints are sort of set in stone in this way. The URL will send back all the data it's programmed to, weather you need it or not, and if there's more data you need on top of it, another request is necessary.
If GraphQL is set up, it goes around several of these issues. In place of the API determining exactly what you're sent, there's more elbow room. While obviously we can only get data that is accessible and open on the server, but other than that, the request itsself determines what data is returned. A request is almost structured like the inverse of a JSON object. We send what keys we need to the server, and they're sent back in turn. We could send this query:
```
{
    user {
        id
        name
        images {
            imageID
            thumbnail
        }
    }
}
```
And recieve something like this:
```
{
    user {
        id: "1",
        name: "ted",
        images [
            {
            imageID: 1,
            thumbnail: ...
            },
            {
            imageID: 2,
            thumbnail: ...
            },
            {
            etc...
            }
        ]
    }
}
```
We request exactly what data is necessary, and we get back only what we need. One request is used, and there's no waste. When bandwidth and processing power are a concern, like mobile networks with 3g or slower, it can make a big difference. 
