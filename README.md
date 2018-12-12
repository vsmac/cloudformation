Creating a Daily Dashboard to Track Bounces and Complaints Via Manually
please check the below link and follow steps
https://docs.aws.amazon.com/ses/latest/DeveloperGuide/dashboardcreateSNStopic.html



We can automate these steps with CloudFormation 
please download the cloudformation template from this repository

LogIn into your AWS account

Step-1:
go to Services and Select CloudFormation

step-2:

choose create stack , it will ask for template select "Template is Ready" and upload template (you can also upload this template on s3 and can provide s3 link also)
click next

step-3: 
It will ask for "name of stack" and value of parameters

Parameters:
1. BucketName:-        This name will be global unique and make sure bucket is not present on your account.
2. BucketPrefix:-      This is optional field so you can leave it
3. DestinationEmail:   This email will receive the report of all bounce mails
4. Frequncy:           Cronjob you can modify according your requirement
5. Identity:           This is a SES identity which will be set SNS topic so you can provide(verified mail and domain also)
6. SourceEmail:        This mail will be used as a source

step-4:

Configure stack options

  Tags in Key-Value pair ( This is optional)
  Permissions:    you can create role for this cloudformation for create, delete and modify resources if you will not provide                     any permission it will take automatic user permission.
  
  
  Advance Options:     you can leave it as it is
  
  click next
  
  review your things and finished
  
  It will do all the things and upload logs on cloudwatch and it will cloudwatch events rule which will have trigger at a     specific time which will configure in Freqency(cronjob)
  
  Please also remember it will fail some regions like Mumbai(because mumbai region doesn't have SES,SNS services
  
  If any changes is required let me know.
  
  Thanks.




