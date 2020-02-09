# NESP - Polimorfisms and Database Architecture

This is a starter kit for [Stamina Cake's](https://www.staminacake.com) course: [Database Architecture with Polimorfisms, Building a Blog API with _Node.js, Express.js, Sequelize.js and PostgreSQL_](https://www.staminacake.com).

Everything you need to succeed in this project is already in you! And we encourage people to go after the resources which are public and, we think, will ever be. However if you need a little pull, we can help you.

#### Table of Contents

1. [Objective](#1.-objective)
2. [Structure](#2.-structure)
3. [How to study](#3.-how-to-study)
   1. Installation
   2. Following the Course Class
   3. Pull Requests [**for enrolled students only**]
4. [Links and Usefull Tips](#4.-links-and-usefull-tips)
5. [Important Notes](#5.-importante-notes)

---

### 1. Objective

Along the course you will be able to:

- Use the Docker Command Line Interface to:
  - Build a container to run your application and Postgres database
  - Log in a service to use the container console
- Use the Sequelize Command Line Interface to:
  - Initiate a project
  - Create a database
  - Generate migrations
  - Run migrations
  - Undo migrations
- Understang ORM - _Object Relationship Mapping_ and its patterns
- Understand the process of creating and running Migrations
- Understand OOP to build Models and Controllers
- Understand generally one-to-many, and many-to-many table relationships
- Understand Polimorfisms within SQL Databases
- Use and understand Sequelize's ORM intrincated model-methods builds
  - get*Model*
  - create*Model*

By the end of this course you will have created a fully working simple blog api with "liking" both users and posts capability with the same entity.

### 2. Structure

This project starts with a basic folder structure and files<sup id="a1">[1](#f1)</sup> as follows:

```
.
│   README.md
│   LICENSE.txt
│   .editorconfig
│   .gitignore
│   .sequelizerc
│   docker-compose.yml
│   Dockerfile
│   nodemon.json
│   package.json
│   server.js
└───app
    │   index.js
    │   router.js
    └───controllers
    │       example.js
    └───database
    │   └───migrations
    │   └───seeders
    │       index.js
    └───models
    │       index.js
    └───utils
            generic-controller.js
```

<b id="f1">1</b>: .gitkeep files can only be deleted once there is a file living inside its parent folder

And, by the end of your couse it will look like the following:

```
.
│   README.md
│   LICENSE.txt
│   .editorconfig
│   .gitignore
│   .sequelizerc
│   docker-compose.yml
│   Dockerfile
│   nodemon.json
│   package.json
│   server.js
└───app
    │   index.js
    │   router.js
    └───controllers
    │       user.js
    │       post.js
    │       like.js
    └───database
    │   └───migrations
    │   │       201973737-user-create.js
    │   │       201973737-post-create.js
    │   │       201973737-like-create.js
    │   └───seeders
    │       index.js
    └───models
    │       index.js
    │       users.js
    │       posts.js
    │       likes.js
    └───utils
            generic-controller.js
```

#### Blog API

The [API](https://en.wikipedia.org/wiki/Application_programming_interface) will consist of general [CRUD](https://en.wikipedia.org/wiki/Create,_read,_update_and_delete) for _Users_, _Posts_ and _Likes_, as [RESTful](https://en.wikipedia.org/wiki/Representational_state_transfer). We will not provide **Authentication**, although it can be fully implemented in this project.

Generaling speaking in a Blog API Users can create Posts and share their recognition of both posts and, or, themselves by attributing likes to either one of those entities.

#### Must have dependencies for the course:

Use [NPM](https://www.npmjs.com/) or [Yarn](https://yarnpkg.com/lang/en/) or your preferable package manager.

- [Sequelize](https://sequelize.org/)
- [Sequelize-CLI](https://github.com/sequelize/cli)
- [PG](https://node-postgres.com/)
- [Express.js](https://expressjs.com/pt-br/)

#### Other must haves:

- [Node.js](https://nodejs.org/en/)
- [Docker](https://www.docker.com/)

### 3. How to Study

1. Installation

This starter kit already comes preconfigured with the basic folder structure and files, it also come with dev and production dependencies already set on the package.json file. Just run one of the following commands bellow with your preferred package manager.

```
npm install
```

or

```
yarn install
```

Once the packages are installed, you will need to run:

```
npx sequelize init
```

or

```
yarn sequelize init
```

And do some tweaking to the generated files as presented on the course.

To help you with that we've already prepared the files where they belong with some helpful comments regarding their purpose and general coding.

2. Following the Course Class

It is important that you code along at the class. Even though we want, hard, that you succeed we will not provide any sort of step-by-step content which is not that presented during the course. That is what separates jr. from seasoned developers: your ability to focus on a concept and then go after the plentfull resources.

So code along, understand the concepts and then practice again with this "not so empty" repository!

3. Issues

[Issues](https://help.github.com/en/github/managing-your-work-on-github/about-issues) are a great way to ask and get answers if you need help of any sort (regarding code!). **You will most likely get an answer from us** or from our community, since answering others questions is the best way to learn feel free to navigate on this repo issues list to see what are the most tricky questions and their best solutions.

Remember, as an engineer you are a problem solver. You gain experience by doing that, even though you do in a small scale.

4. Pull Requests

If you enrolled in this course you will be able to add [Pull Requests](https://help.github.com/pt/github/collaborating-with-issues-and-pull-requests/about-pull-requests) to the main code. Although we will not merge the content it is a good way for us to tell if you got the idea we were trying to pass along.

In order for us to evaluate your Pull Requests please notice that:

- Your code is complete, regarding the topics covered in class
- You have all the Controllers, Models and Migrations

What we will evaluate:

- Clean Code
- Completeness
- ...

You can always check how well you are doing by comparing your code with the other peers who have studied with us!

### 4. Links and Usefull Tips

**Docker Commands**

Within the docker-compose.yml file folder type:

```
docker-compose up #builds the container
```

```
docker-compose down #takes the container down
```

```
docker-compose exec <service_name> sh #logs into container service shell
```

To run your migrations with docker exposed application container you will need to, first, log into the app service shell with the above command and, then, run:

```
npx sequelize db:migrate
```

or

```
npx sequelize db:migrate:undo
```

To undo a previously ran migration.

### 5. Important Notes

This repository is shared as is and it is a part of a private course. Feel free to explore the starter kit and the rules described above to explore and code by yourself.

However if you feel you need any mentorship feel free to contact us at [contato@staminacake.com](mailto:contato@staminacake.com?subject=[NESP]%20Quero%20aprender!).

Presently we teach in [São Paulo, Brazil](https://www.staminacake.com)!
