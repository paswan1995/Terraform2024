# N-Tier Application

* Consider the following architecture of a typical web application (ticket booking)
![preview](images/10.png)

* To realize this application on AWS, the high level overview is as shown below
![preview](images/11.png) 

* To realize this application on Azure, the high level overview is as shown below
 ![preview](images/12.png)

# WOW (Ways of Working)

  * Lets realize the architecture manually, make a note of 
     * resource
     * inputs
     * outputs

  * Find resources in Terraform to achieve the above manual steps  

# Configuring a Provider in Terraform

  * Install Terraform on a linux machine 
     * Create a linux vm and ssh into it and execute the steps based on your distribution from here
     * refer: https://developer.hashicorp.com/terraform/install 
     ![preview](images/.png)

# AWS Provider
     
  * Terraform aws provider uses the AWS APIs to get the infra created.
  * To Create infrastructure in your AWS Account, it needs AWS programmatic credentials (Secret key and access key)
  * To configure these keys Refer Here: https://registry.terraform.io/providers/hashicorp/aws/latest/docs#authentication-and-configuration
  * Create IAM Secret key and access key Refer Here: https://guide.sst.dev/chapters/create-an-iam-user.html for manual steps
  * Lets write provider configuration
  
  ``` 
  provider "aws" {
    region = "us-west-2"
    access_key = "AKIAZ4ECZC3PP5DPPHG6"
    secret_key = "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"
}


  * This is not a great way as we are having sensitive information in the text format.
  * Best way is to install aws cli on the machine with terraform and terraform will automatically pickup credentials from there use the command `aws configure` on your machine terminal  .
  * Installing aws cli Refer Here:https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html
  * Now your provider can be as simple as 
  
provider "aws" {
    region = "us-west-2"
}
  ```   