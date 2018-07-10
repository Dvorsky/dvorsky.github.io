---
title: "On Documenting Your Projects"
layout: post
date: 2018-07-9 15:44
image: /assets/images/markdown.jpg
headerImage: false
tag:
- documentation
- improvement
star: false
category: blog
author: andrija
description: Lets talk about writing documentation for your projects
---

Documentation is used to make managing a project easier. It helps those who use, maintain and extend project in the future. While it takes time, it doesn’t need to look pretty, but functional and updatable, so in the long run it saves you a lot more time than you spend on it.


So, to get started, what you need to document? These are not rules, just guidelines, pick which of these to include depending on what your project needs.

1. [Summary what the project is about and what it accomplishes](#summary-what-the-project-is-about-and-what-it-accomplishes)
2. [Stack the project uses](#stack-the-project-uses)
3. [Project diagram](#project-diagram)
4. [Features](#features)
5. [Installation and running](#installation-and-running)
6. [Configuration](#configuration)
7. [Contribute](#contribute)
8. [Support](#support)


## Summary what the project is about and what it accomplishes

Just summarise your project. Think of it as this, if someone approached you just now and asked you “hey, what was that thing you were working on?”, write down what you would say to them and that’s your project summary.

**Example:**

```
## MyCoolApp

MyCoolApp is used as user identity managment wrapper. It
Is combines a lot of third party tools in the one place.
```

## Stack

What technologies you used to build the project? You don’t need to mention every single package you pulled with it, but bigger things that whole project is dependent on. It’s also good if you have layers of abstraction to point them out here. 

You can also elaborate on these technology choices here.

``` md
## Stack

#### StorageService

MyCoolApp uses StorageService interface as a level of 
abstraction over storage implementations. Currently, 
DatabaseStorageService is implemented.


#### Keycloak

MyCoolApp uses keycloak for user authentication and authorization. 
It is a open source solution for user management with realms 
and roles out of the box. Library used to interface with keycloak 
is keycloak-admin-client


#### Express

MyCoolApp uses express for API routing
```

## Project Diagram

Make a diagram using some tool like [draw.io](https://draw.io) to better represent how your application works internally. If I want to make change to __XXX__ part of it, what other stuff can potentially be affected. I suggest making UML diagrams, but depending on your project your requirements may differ.

![app-diagram](/assets/app-diagram.png)
<figcaption class="caption">Courtesy of <a href="https://christiantietze.de/posts/2015/08/drawio-uml-diagrams/">Christian Tietze</a></figcaption>

## Features

What your app accomplishes in current iteration, what it supports for you to do with it? Write it down here in bullet points.

```
## Features

 * REST API
 * User Authentication and Authorization
 * User manipulation
```

## Installation and Running

What steps do you have to take to install the app and run it locally (this does not include what configuration you have to setup). Write down those steps here and make note of any problems someone could encounter while installing/running.

```
To install MyCoolApp locally, first run `npm install`.

After that, you first duplicate `pm2-compose.example.yml` and save it 
as `pm2-compose.yml`. For local purposes there is no need to change 
any environment variables.

After that, you run `docker-compose up` and `npm run migrations`. 
This needs to be done only the first time to create containers and run 
migrations to fill databases. In the future, you can just run npm run dev.

You can send requests to localhost:3010 and access database on localhost:5433
```

## Configuration

What kind of configuration your app uses, does it use environment variables, what values you need to setup? Config files? Note it here and explain it.

```
## Configuration

While for local environment it will work with default values set up in 
for deployment you want to configure these settings.

PORT - on which port should Kika be accessable)
APP_ENV - local|test|prod

KEYCLOAK_URL - URL to keycloak authentication
KEYCLOAK_ADMIN_USERNAME
KEYCLOAK_ADMIN_PASSWORD
ADMIN_KEYCLOAK_CLIENT
KEYCLOAK_REALM

STORAGE_HOST
STORAGE_DATABASE
STORAGE_USER
STORAGE_PASSWORD
STORAGE_PORT
```

## Contribute

Here are links to project related tools which help along with this documentation, for example link to the graph used for app overview so someone else can update it, API documentation which is documented separately, etc. Link such sites/services here.

```
## Contribute

Issue tracker: [Issues](https://https://github.com/Dvorsky/MyCoolApp/issues)

Graphs: [draw.io](https://www.draw.io/#LinkToMyGraph)

API: [Documentation](docs/API.md)

```

## Support

If all else fails, put here who to contact if there are any problems :)


## Parting words

And that’s it, all documentation your project needs. Of course you can expand on this, but I found this a good reference point when starting. This takes around a half an hour to write up if you don't do the graphs, which I found a really good time investment for how much it could save time for other people when discovering my project.



