# 📦 Step 08 — Infrastructure as Code (IaC) with Terraform  

## 📌 What is IaC?  
Infrastructure as Code means managing infrastructure using code instead of manual setup.  
Terraform is the most popular IaC tool.  

---

## ⚙️ Install Terraform  

### Ubuntu/Debian  
```bash
sudo apt update && sudo apt install -y wget unzip
wget https://releases.hashicorp.com/terraform/1.5.0/terraform_1.5.0_linux_amd64.zip
unzip terraform_1.5.0_linux_amd64.zip
sudo mv terraform /usr/local/bin/
terraform -v
```

### macOS  
```bash
brew tap hashicorp/tap
brew install hashicorp/tap/terraform
```

### Windows  
```powershell
choco install terraform
```

---

## 📝 Example: Provision Infrastructure  
`main.tf`  
```hcl
provider "aws" {
  region = "us-east-1"
}

resource "aws_s3_bucket" "mybucket" {
  bucket = "my-terraform-bucket-example"
  acl    = "private"
}
```

Run:  
```bash
terraform init
terraform apply
```

✅ You just deployed infra with Terraform!  
