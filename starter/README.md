# CD12352 - Infrastructure as Code Project Solution
# BaoTHD

## Prerequisites
- AWS CLI is already set up.

## Spin up instructions
Go to 'starter' directory:
1. Create S3 bucket
    ```
    ./create.sh uda-s3 s3.yml s3-parameters.json
    ```
2. Create cloud network
    ```
    ./create.sh uda-vpc network.yml network-parameters.json
    ```
3. Provision server
    ```
    ./create.sh uda-server udagram.yml udagram-parameters.json
    ```
4. Create cloudfront distribution
    ```
    ./create.sh uda-cf cloudfront.yml cloudfront-parameters.json
    ```
5. Upload index.html to s3 bucket for testing purpose

## Tear down instructions
Go to 'starter' directory:
1. Remove cloudfront stack
    ```
    ./delete.sh uda-cf
    ```
2. Remove server stack
    ```
    ./delete.sh uda-server
    ```
3. Remove network stack
    ```
    ./delete.sh uda-vpc
    ```
4. Go to S3 console and empty bucket (Cannot empty from CLI because of enabling versioning)
5. Remove s3 stack
    ```
    ./delete.sh uda-s3
    ```
