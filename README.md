# AWS-CLI

- First command: 
    #aws configure
    
    This command will ask you to configure the AWS CLI byasking you to enter the ACCESS KEY , PRIVATE KEY , REGION and the OUTPUT FORMAT for the results of the commands
    
- Second command: 
    #aws ec2 create-key-pair --key-name MyKeyPair
    This command will help you by creating a Key-Pair to keey the upcoming instance secure of anonymous and unwanted login to ouur instance.
    
    
 - Third command: 
    #aws ec2 create-security-group --group-name MySecurityGroup --description "My security group" 
    This command will ley you create a Security Group that will helpyou control the inbound and outbound traffic to your instance.
    
    
   We will just mention the inbound traffic rule as the AWS EC2 instance maintains Session(Statefulness) of the incoming requests.
   
  - Fourth command: 
     #aws ec2 run-instances --image-id ami-068d43a544160b7ef --count 1 --instance-type t2.micro --key-name MyKeyPair --security-group-ids sg-0ef69efcd4eede0ea --subnet-id subnet-72d8a43e
     
     This command will create an instance on the AWS account of the user specified on the first (#aws configure) command by providing keys.
     
  - Fifth command: 
     #aws ec2 create-volume --volume-type gp2 --size 1 --availability-zone ap-south-1b
     
     Creates a volume of the specified sizeat the specified AZ . One thin to be kept in mind is thatthe EBS volume being created should be creaetd atthe same AZ whereour instance      is created.
     
   - Sixth command: 
        #aws ec2 attach-volume --volume-id vol-09bb61f16caf50505 --instance-id i-0122b14214bee5d4a --device /dev/sdf 
        
     This command will help us by attaching the volume to the instance , if the instance and volume are in same AZ "NO ERROR" else an ERROR is displayed ststing that the two            resources are not in the same AZ.   
