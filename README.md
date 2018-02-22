Create a standalone build project in AWS CodeBuild and trigger builds, for example, using a webhook

- Use the [CloudFormation template](template.yaml) to provision a build project in AWS CodeBuild

```
$ aws cloudformation create-stack \
    --stack-name standalone-build-servers-api-ruby \
    --template-body file://template.yaml \
    --capabilities CAPABILITY_IAM

```

- You can create and configure a webhook to trigger builds from the repository in Github

```
$ aws codebuild create-webhook --project-name standalone-build-servers-api-ruby
 
```

Use the ```payloadUrl``` in the response to [create a webhook](https://developer.github.com/webhooks/creating/) on the repository in Github 
 
- You can also trigger the build using an API call, or from Jenkins via the [AWS CodeBuild plugin for Jenkins](https://plugins.jenkins.io/aws-codebuild)