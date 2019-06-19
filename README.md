Deploying spring boot application to AWS Lambda
=
Integrating Spring boot application into the AWS lambda runtime.

Prerequisites
===
* aws-serverless-java-container => https://github.com/awslabs/aws-serverless-java-container
** is a Java wrapper to run Spring, Jersey, Spark, and other apps inside AWS Lambda. https://aws.amazon.com/serverless/
* AWS CLI installed
* AWS SAM
+ a CLI tool to build, test, debug, and deploy Serverless applications using AWS SAM https://aws.amazon.com/serverless/sam/
* IAM user with required permissions to deploy in to AWS Lambda

Package & Deploy
===
```
mvn clean package

aws cloudformation package --template-file sam.yaml --output-template-file target/output-sam.yaml --s3-bucket artifacts-lambda --profile default

aws cloudformation deploy --template-file target/output-sam.yaml --stack-name demo-spring-boot --capabilities CAPABILITY_IAM
```

