---
template: blog-post
title: Welcome To My Blog
slug: /welcome
date: 2022-01-30 19:10
description: First blog post
featuredImage: /assets/blog-image.jpg
---
# Hello World!
For many months I've wanted to start a blog, and now I'm finally doing it (It's not like this is a graded assignment for school or anything...). My reasons for starting a blog are mostly personal - I want to improve my writing skills, better understand topics I'm learning, and document my experiences! While I want to write a lot about learning web development, I also want to be able to write about anything else - like my current K-pop obsession, music I'm trying to make on Ableton, or video games I'm playing lately. 

For this first blog post, however, I want to talk a little bit about this website. More specifically, the fact that this is a JAMstack application.

## Jamstack Architecture
This website is a what now?? The JAMstack is a modern tech stack used to create websites. 

JAM is an acronym:

- **J** - Javascript

- **A** - APIs

- **M** - Markup (HTML/CSS)


### What's a tech stack?
In general, a tech stack is made up of technologies that a web developer will use to make a website. It includes the front-end (what the user sees) and the back-end (a server or database).

Common tech stacks:

- **LAMP** - Linux, Apache, MongoDB, Python

- **MEAN/MERN** - MongoDB, Express.js, Angular.js/React.js, Node.js

What's cool about a Jamstack app is that it isn't specific about what technologies to use (mostly because there are a lot of frameworks/languages out there now). So, unlike the other common tech stacks that include specific frameworks, JAM is an acronym for the elements needed to construct the website/application.

- **JavaScript**: programming language used to either talk to APIs or enhance the user experience

- **APIs**: Application Programming Interfaces used to request data from another application

- **Markup**: the HTML and CSS code that creates a static website the user sees

### How it works
In short, the front-end of a JAMstack site is HTML/CSS markup code. So, If we are building a website using a front-end framework, we need a static site generator to convert several kinds of files into one HTML file. This process is usually done during the "build" step. Then, at deploy time, the HTML files are quickly loaded and displayed to the user. 

For the backend of a JAMstack website, APIs let developers take a "microservices approach", where, using Javascript, developers can call APIs or use serverless functions to do back-end responsibilities as needed. This makes it very lightweight and easily scalable
[source](https://www.cloudflare.com/learning/performance/what-is-jamstack/).

### This site's technologies

This blog site is made from a template called Gatsby Starter Foundation, deployed from Netlify. Here is the link:

[https://templates.netlify.com/template/foundation-gatsby-netlifycms-starter/]()

[Gatsby](https://www.gatsbyjs.com/) is a static site generator, which uses [React](https://reactjs.org/) (front-end library). Gatsby is what builds our site into static HTML files easily interpreted by the browser. Then, [Netlify](https://www.netlify.com/) deploys the site to a CDN (Content Delivery Network), which is where the website is served from. Netlify also has a [CMS](https://www.netlifycms.org/) (Content Management System), which provides the developer a user interface to update the website (back-end functionality). Behind the scenes, it's Javascript (Netlify also uses React)! 

Netlify CMS connects directly to Github, so all of the source code for the website is in a Github repository and updates automatically whenever I make changes to the website. How convenient :)

### Conclusion
So far, my experience with this set up is positive! I've spent most of my time using the CMS and writing blog posts. The UI is easy to navigate and understand. One concern I'm having right now, however, is saving my work. For me, I can't just write out a blog post and submit it - I usually have to leave and come back to it. Unfortunately, I can't find a way to save half-finished blog posts! A solution I came up with is writing out the blog post on [Joplin](https://joplinapp.org/), which is a note-taking app that uses Markdown. Then, I just copy and paste it into the CMS and submit. It'll do for now until I find another solution.

Alright! Until the next blog post! :)



