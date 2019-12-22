# NESP - Polimorfisms and Database Architecture

This is a starter kit for [Stamina Cake's](https://www.staminacake.com) course: [Database Architecture with Polimorfisms, Building a Blog API with _Node.js, Express.js, Sequelize.js and PostgreSQL_](https://www.staminacake.com)

#### Table of Contents

1. [Objective](#1)
2. [Structure](#2)
3. [How to study](#3)
   1. Installation
   2. Following the Course Class
   3. Pull Requests [**for enrolled students only**]
4. [Links and Usefull Tips](#4)
5. [Important Notes](#5)

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

This project starts with a basic folder structure and files[^1] as follows:

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

[^1]: .gitkeep files can only be deleted once there is a file living inside its parent folder

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

3. Pull Requests

You can always check how well you are doing by comparing your code with...

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

This repository is shared as is and it is a part of a private course. Feel free to explore the starter kit and the rules mentioned described above to explore
