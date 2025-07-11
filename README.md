# Terraform-for-AWS-EC2-Infrastructure

This project demonstrates basic Infrastructure as Code (IaC) using **Terraform** to provision and manage an AWS EC2 instance along with its networking resources.

---

## 📦 Features
- Deploys a custom **VPC**, **Subnet**, **Internet Gateway**, and **Route Table**
- Creates a **Security Group** allowing SSH (22) and HTTP (80)
- Provisions an **EC2 Instance** using a key pair
- Uses **Terraform variables** for flexibility
- Outputs the instance **Public IP**

---

## 📁 Project Structure
```
terraform-aws-ec2/
├── main.tf         # Main infrastructure definitions
├── variables.tf    # Input variables
├── outputs.tf      # Output values
```

---

## ⚙️ Requirements
- Terraform >= 1.0
- AWS CLI configured with credentials
- An existing AWS EC2 Key Pair (name passed via variable)

---

## 🚀 How to Use

### 1. Clone this Repository
```bash
cd terraform-aws-ec2
```

### 2. Initialize Terraform
```bash
terraform init
```

### 3. Set Key Pair Name
Provide AWS EC2 key pair name either in a `.tfvars` file or directly when applying:
```bash
echo 'key_pair = "key-pair-name"' > terraform.tfvars
```

### 4. Review the Execution Plan
```bash
terraform plan -var-file="terraform.tfvars"
```

### 5. Apply the Configuration
```bash
terraform apply -var-file="terraform.tfvars"
```

### 6. Output
After provisioning, the EC2 public IP will be shown in the output.

---

## 🧹 Cleanup
To destroy all resources created:
```bash
terraform destroy -var-file="terraform.tfvars"
```

---

## 📌 Notes
- Make sure AWS credentials are configured before running.
- Replace AMI ID in `main.tf` if it is a different region.

---

## 📄 License
This project is open-source and free to use.

