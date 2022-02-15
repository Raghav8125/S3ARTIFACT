# S3ARTIFACT
#publish s3 as a artifact for jenkins
Prerequisites
---------------
    Create Jenkins Server Jenkins server
   
   Steps to set up
   ---------------
  1. Create a S3 bucket to store artifacts
         S3 --> Create bucket
         Bucket name: s3-artifact 
         Region: ap-southeast1
  2.  Create new IAM role with "S3 full access" and assign it to jenkins server
           IAM --> Create role --> EC2

                Permission: AmazonS3FullAccess 
                Tags: key - Name, Value - S3FullAccess Role 
                name: S3_Full_Access
3)  Install "S3 Publisher" plugin on Jenkins   (assign iam role to jenkins in ec2 instance)
    Manage Jenkins --> Manage Plugins --> Availabe --> S3 publisher

4)  Configure S3 profile on Jenkins
    Manage Jenkins --> Configure Systems --> Amazon S3 profiles

          Profile name : s3-artifact-repository 
          Use IAM Role : choose(which is aasigned is jenkins)

Create a job to store artifacts under S3.
       
