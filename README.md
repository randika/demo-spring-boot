Deploying spring boot application to AWS Lambda
=
Integrating Spring boot application into the AWS lambda runtime.

Dependencies
===
- aws-serverless-java-container => https://github.com/awslabs/aws-serverless-java-container
-- is a Java wrapper to run Spring, Jersey, Spark, and other apps inside AWS Lambda. https://aws.amazon.com/serverless/
- AWS CLI installed
- IAM user with required permissions to deploy in to AWS Lambda

Deployment
===
```
mvn clean package

aws cloudformation package --template-file sam.yaml --output-template-file target/output-sam.yaml --s3-bucket artifacts-lambda --profile default

aws cloudformation deploy --template-file target/output-sam.yaml --stack-name demo-spring-boot --capabilities CAPABILITY_IAM
```

