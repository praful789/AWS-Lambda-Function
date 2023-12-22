# My AWS Lambda Function

This AWS Lambda function is a simple example written in Python. It prints "Hello World!" and the content of the event it receives. Additionally, it demonstrates handling imports and includes the `requests` module for making HTTP requests.

## Getting Started

Follow these steps to deploy the Lambda function using Docker:

### Prerequisites

- Docker installed on your local machine
- AWS CLI configured with the necessary credentials

### Building and Deploying

1. Clone the repository:

    ```bash
    git clone <repository_url>
    cd <repository_directory>
    ```

2. Create a file named `requirements.txt` with the following content:

    ```text
    requests==2.25.1
    ```

3. Build the Docker image:

    ```bash
    docker build -t my-lambda-function .
    ```

4. Deploy the Docker image to AWS Lambda (replace `<function_name>` with your desired function name):

    ```bash
    docker tag my-lambda-function:latest <account_id>.dkr.ecr.<region>.amazonaws.com/<repository_name>:<tag>
    docker push <account_id>.dkr.ecr.<region>.amazonaws.com/<repository_name>:<tag>
    ```

### Testing

After deploying the Lambda function, you can test it using the AWS Lambda console or the AWS CLI. Example AWS CLI command:

```bash
aws lambda invoke --function-name <function_name> --payload '{"key1":"value1", "key2":"value2", "key3":"value3"}' output.txt
