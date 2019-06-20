# AWS API Gateway Example

Greeting API using AWS Gateway and Lambda.

## Pre-requisites

- Docker
- Docker Compose
- AWS credentials in ~/.aws or environment variables
  > Environment variables can be defined inside your shell session using `export VAR=value` or setting them in .env file. See `.env.template` for more information.

## Installation

### With Serverless

    $ serverless install -u https://github.com/amaysim-au/docker-serverless/tree/master/example/apigw -n your-project

### With Docker

    $ docker run --rm -v ${PWD}:/opt/app amaysim/serverless:1.45.1 serverless install -u https://github.com/amaysim-au/docker-serverless/tree/master/example/apigw -n your-project

### With git

    $ git clone https://github.com/amaysim-au/docker-serverless.git
    $ cp -r docker-serverless/example/apigw/ your-project
    $ rm -fr docker-serverless/example/apigw/

## Usage

```bash
# create .env file based on .env.example
$ make dotenv DOTENV=.env.example
# test/build lambda package
$ make build
# deploy to aws
$ make deploy
# you should see something like:
#   endpoints:
#     GET - https://xyz.execute-api.ap-southeast-2.amazonaws.com/dev/greet
$ curl https://xyz.execute-api.ap-southeast-2.amazonaws.com/dev/greet
# <html>
#   <body>
#     <h1>"Welcome to Amaysim Serverless"</h1>
#   </body>
# </html>

# remove the api gateway
$ make remove
# clean your folder
$ make _clean
```
