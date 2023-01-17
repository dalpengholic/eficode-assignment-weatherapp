# eficode-assignment-weatherapp
This is a repository for submitting an Eficode assignment about weatherapp

## How to use this repository for development
- Please refer to [README.md at dev branch](https://github.com/dalpengholic/eficode-assignment-weatherapp/blob/dev/README.md).

## How to use this repository for deployment
- This subject is handled by my different repo at [eficode-assignment-weatherapp-ansible](https://github.com/dalpengholic/eficode-assignment-weatherapp-ansible)

## How I understand this assignment
- General purpose
This assignment is designed to measure candidates' knowledge and implementation skills regarding the general Continuous Integration and Continuous Deployment(CI/CD) as well as Infrastructure as Code(IaC). 

- Target With Docker and Docker-Compose
The first target of docker assignment is to give the same development environment to developers by using docker and docker-compose. The second target is using proper branch strategy to accelerate development speed as well as keep the source codes in safe and clean.

- Virtual short 1 week sprint
I have followed the virtual 1 week sprint below.
  - Day1: Assignment analysis
  - Day2 to Day4: Plan and action and short review
  - Day5: Rest
  - Day6 and Day7: Polishing and main review


## How I approached this assignment
- Use two branches, `dev` and `master` from the perspective of a developer and a DevOps engineer. 
- ` dev` branch is a branch to be used for development. Developers start coding from this branch by launching the developing environment by docker compose and git push to `dev` branch. If developers follow this process `Plan - Branch - Code - Merge - Build`, The first three steps `Plan - Branch - Code` will be done at `dev` branch.
- `master` branch is the main branch having stable versions of source codes and ready to be packaged as docker images. Any changes from the `dev` branch have to be tested from the local and official test pipeline and merged to the master. Directly pushing to the master or merging without testing should be forbidden. If `master` has new commits, then new docker images including frontend and backend apps are built and published automatically by `GitHub Action` with the latest and short git commit hash.

## My assumptions regarding this assignment
- There is an official test pipeline that tests all `dev` branch changes.
- Only passed `dev` branch could be merged to `master`.
- My personal docker registry at [Official Docker Hub](https://hub.docker.com/) is the official place to store production images.

## What I have learned
- I spent a lot of time on the first day understanding the assignment. Especially, I needed to research how to handle NPM and nodejs director structure due to no experience with nodejs.
- I needed to spend some time setting up my environment on my new Ubuntu 22.04. For example, I had to configure of git, create ignore and .env files
- I only dealt with the GitLab pipeline and was new to GitHub Actions, but I got used to it quickly.

## What need to be improved
- The real test pipeline should exist for the dev branch. For example, using Robot Framework will be a candidate to build a test pipeline.


## To run production docker images in public cloud like AWS
- You need to provide .prod.env at working directory for production server
```Shell
$ cat .prod.env
# Example: http://{server ip/dns-hostname}/api
ENDPOINT=http://0.0.0.0:9000/api
```
