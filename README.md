Deploying spring boot application to AWS Lambda
==
Integrating Spring boot application into the AWS lambda runtime

Deployment
===
mvn clean package

aws cloudformation package --template-file sam.yaml --output-template-file target/output-sam.yaml --s3-bucket artifacts-lambda --profile default

aws cloudformation deploy --template-file target/output-sam.yaml --stack-name demo-spring-boot --capabilities CAPABILITY_IAM


