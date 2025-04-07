---
title: Detailed Contributing Guide
parent: Contributing
layout: default
---

{: .help}
> We could use contributions to add content/clarity to all h1's defined in this article.

# Running the Website Locally

## (1) Running the website on your machine

This is an essential step of contributing to the WCA website, as you'll want to see the effect of the changes you make to the code.

### 1. Clone this repo! (And navigate into it)
1. `git clone https://github.com/thewca/worldcubeassociation.org`
2. `cd worldcubeassociation.org`

### 2. Run using Docker

1. Install [Docker](https://docs.docker.com/get-docker/) (remember to complete the [Linux post-install steps](https://docs.docker.com/engine/install/linux-postinstall/) if you're on Linux)
2. Install docker-compose. The best way to get an up-to-date version is to get it from their [releases page](https://github.com/docker/compose/releases)
3. Navigate into the repository's main directory (`worldcubeassociation.org`)
4. To start the server at `http://localhost:3000`, run `docker-compose up` (or `docker compose up`, depending on your install). To bring it down, `docker-compose down` (or just press ctrl + c in the same terminal)
5. To run tests, run `docker-compose exec wca_on_rails bash -c "RAILS_ENV=test bin/rake db:reset && RAILS_ENV=test bin/rake assets:precompile && bin/rspec"`
6. If you're using Visual Studio Code to develop, you can [attach it to the Docker container](https://code.visualstudio.com/docs/remote/containers) so that your extensions can take advantage of the Ruby environment and so the terminal runs from inside the container

### 3. Set up the database

#### Import the developer database
1. Make sure that you have allocated at least 4GB RAM to your Docker containers under the Resources menu.
2. In a bin/rails console prompt, run `bin/rake db:load:development`
3. This job will take 10-200 minutes - yes, more than two hours in bad cases! This will load the latest database export onto your local machine.

#### Run CAD 
In a bin/rails console prompt, run `ComputeAuxiliaryData.perform_now`.

### 4. Run migrations (if necesary)

## (2) Find an issue you'd like to contribute to

You can look at our [good first issues](https://github.com/thewca/worldcubeassociation.org/labels/META%3A%20good%20first%20issue), find one that interests you, and add a comment saying that you'd like to work on the issue.


## (3) Create a new branch, and start writing your changes.

### Create a new branch

### Start the Docker container

### Start writing your code

With the Docker container running, the website will automatically update with any changes you make to the code.

## (4) Commit and push your changes

# Opening A Pull Request

# Reviewing Someone's Pull Request

# Pulling from / Pushing to Someone's Pull Request

- Pulling: `gh pr checkout {pr-number}`
- Pushing: `git push git@github.com:{author-username}@worldcubeassociation.org.git HEAD:{branch-name}`

The "pushing" command allows you to push changes to someone's repo without adding them as REMOTE on your local git. 

{: .help}
> Add instructions for pushing to a repo by adding it as remote and then pushing to it
