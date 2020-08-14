# Video-on-demand Prototype (Work in progress)

## Overview

<img src="https://raw.githubusercontent.com/normanwongcl/video-transcoding-serverless/master/images/overview.png" alt="AWS Overview">

## Tools used

```yaml
Node.js: 12.18.0
npm: 6.14.4
Serverless Framework:
  Core: 1.78.1
  Plugin: 3.7.0
  SDK: 2.3.1
  Components: 2.34.1
```

## Install

```bash
# If you don't already have the serverless cli installed, do that
npm install -g serverless

# Install aws cli v2
curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
sudo unzip awscliv2.zip
sudo ./aws/install
rm -rf aws awscliv2.zip

# Set up your aws cli
aws configure

# Clone this repo
git clone git@github.com:normanwongcl/whatsapp-notification.git

# cd into project and set it up
cd whatsapp-notification

```

## Development

Creating and deploying a new function takes two steps, which you can see in action with this repo's default Hello World function (if you're already familiar with Serverless, you're probably familiar with these steps).

#### Add your function to `serverless.yml`

In the functions section of [`./serverless.yml`](./serverless.yml), you have to add your new function like so:

```yaml
functions:
  hello:
    handler: hello/index.handler
```

You can see here that we're setting up a function named `hello` with a handler at `hello/index.js.

## Deployment

Assuming you've already set up your default AWS credentials (or have set a different AWS profile via [the profile field](serverless.yml#L26):

Then run the command below:

```bash
serverless deploy
```

Test function is working

```bash
serverless invoke --function hello
```

Expected output:

```json
{
  "statusCode": 200,
  "body": "{\"message\":\"Go Serverless v1.0! Your function executed successfully!\",\"input\":{}}"
}
```
