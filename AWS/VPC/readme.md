

## **#️⃣ Step 1: Login to AWS Console**
- Go to **AWS Management Console**
- Search for **VPC**
- Open the **VPC Dashboard**

---

## **#️⃣ Step 2: Open the VPC Creation Wizard**
- Click **Create VPC**
- Select **VPC Only**

---

## **#️⃣ Step 3: Enter VPC Details**
Fill the form with:

- **Name tag:** (e.g., `MyVPC`, `Prod-VPC`)
- **IPv4 CIDR block:** `10.0.0.0/16`
- **Tenancy:** Default  
Click **Create VPC**

---

## **#️⃣ Step 4: Create Subnets**
Go to **Subnets → Create subnet**:

- Choose your VPC  
- Create at least:
  - **Public Subnet:** `10.0.1.0/24`
  - **Private Subnet:** `10.0.2.0/24`
- Select different **Availability Zones** for high availability

---

## **#️⃣ Step 5: Create an Internet Gateway (IGW)**
- Go to **Internet Gateways**
- Click **Create internet gateway**
- Name → `MyIGW`
- **Attach** it to your VPC

---

## **#️⃣ Step 6: Configure Route Tables**

### **Public Route Table**
- Go to **Route Tables → Create route table**
- Name → `Public-RT`
- Associate **public subnet**
- Add route:
  - **Destination:** `0.0.0.0/0`
  - **Target:** **Internet Gateway**

### **Private Route Table**
(Optional)
- Create separate table for private subnet  
- No internet route unless using NAT Gateway

---

## **#️⃣ Step 7: (Optional) Create a NAT Gateway**
For **private subnet internet access (outbound only)**:

- Allocate **Elastic IP**
- Create **NAT Gateway** in **public subnet**
- Update the private route table:
  - Route: `0.0.0.0/0 → NAT Gateway`

---

## **#️⃣ Step 8: Create Security Groups**
- Go to **Security Groups**
- Create groups for:
  - **EC2**
  - **RDS**
  - **Load Balancer**
- Add appropriate inbound/outbound rules

---

## **#️⃣ Step 9: Launch EC2 Instances**
Your VPC is ready. Now you can launch instances in:

- **Public Subnet:** Internet-facing resources  
- **Private Subnet:** Backend or secure services  


