# eks-cluster-with-terraform
EKS Cluster creation with Terraform modules using remote state backend

## Deploy with terraform
    
    terraform fmt --recursive
    cd backend/
    terraform init

  Import the state file into the root module

    cd ..
    terraform import import aws_s3_bucket.terraform_state savvy-app01-terraform-state-bucket

    terraform validate
    terraform plan
    tf apply -auto-approve

  ## Clean Up
  Remove the imported remote state backend

     terraform state rm aws_s3_bucket.terraform_state
     tf destroy -auto-approve