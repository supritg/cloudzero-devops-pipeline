pipeline {
  agent any

  environment {
    AWS_ACCESS_KEY_ID = 'test'
    AWS_SECRET_ACCESS_KEY = 'test'
    AWS_SESSION_TOKEN = 'test'
    AWS_DEFAULT_REGION = 'us-east-1'
    BUCKET_NAME = 'cloudzerostaticsite'
    LOCALSTACK_HOST = 'localstack'
    AWS_ENDPOINT_URL = 'http://localstack:4566'
    S3_FORCE_PATH_STYLE = 'true'
    AWS_ENDPOINT_URL_S3 = 'http://localstack:4566'
  }

  stages {
    stage('Checkout') {
      steps {
        checkout scm
      }
    }

    stage('Build React App') {
      steps {
        dir('website') {
          sh 'npm install'
          sh 'npm run build'
        }
      }
    }

    stage('Terraform Init & Apply') {
      steps {
        dir('terraform') {
          sh 'terraform init -upgrade'
          sh 'terraform apply -auto-approve'
        }
      }
    }
  }
} 