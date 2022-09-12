# python_test
The circle ci has the below steps 
  Step: Setting up a CircleCI pipeline using the aws-ecr orb - circleci/aws-ecr@7.0.0
  
        The aws-ecr orb comes prepackaged with commands to:
        
        1.Build an image
        
        2.Tag the image (using the Git commit hash of the HEAD == CIRCLE_SHA1 )
        
        3.Login to Amazon EC
        
        4.Push an image to Amazon ECR

        we need pass the below details 
        
        Amazon ECR account URL that maps to an AWS account, e.g. {awsAccountNum}.dkr.ecr.us-west-2.amazonaws.com
        
        AWS access key id of cicd iam user
        
        AWS secret key of cicd iam user
        
        AWS region where your ECR resources will be located
        
        dockerfile which required to create image

Once this step executed it builds image using docker file and it pushes the image to docker repository which we provided in the aws-ecr orb configuration. 


We have set up a cloudwatch event rule which will trigger the AWS batch job on the event of successful push of Image to ECR repo

 
