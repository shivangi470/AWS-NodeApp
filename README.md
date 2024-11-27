Here’s the corrected and formatted content for the README file:

---

# Deploying a Node.js Application on AWS EC2

## **Testing the Project Locally**

### **Clone this Project**

```bash
git clone https://github.com/verma-kunal/AWS-Session.git
```

### **Set Up Environment Variables**

Create a `.env` file with the following variables:

```env
DOMAIN=""
PORT=3000
STATIC_DIR="./client"

PUBLISHABLE_KEY=""
SECRET_KEY=""
```

### **Initialize and Start the Project**

```bash
npm install
npm run start
```

---

## **Set Up an AWS EC2 Instance**

### **Create an IAM User & Log in to Your AWS Console**

1. Create an IAM user with the following:
   - **Access Type**: Password
   - **Permissions**: Admin
2. Log in to your AWS Console.

### **Create an EC2 Instance**

1. **Select an OS Image**: Ubuntu  
2. **Create a New Key Pair**: Download the `.pem` file.  
3. **Instance Type**: t2.micro  

---

## **Connecting to the Instance Using SSH**

Use the following command to connect:

```bash
ssh -i instance.pem ubuntu@<IP_ADDRESS>
```

---

## **Configuring Ubuntu on the Remote VM**

1. **Update Outdated Packages and Dependencies**:
   ```bash
   sudo apt update
   ```

2. **Install Git**:
   Follow the [Git installation guide by DigitalOcean](https://www.digitalocean.com/community/tutorials/how-to-install-git-on-ubuntu).

3. **Configure Node.js and npm**:
   Follow the [Node.js and npm installation guide by DigitalOcean](https://www.digitalocean.com/community/tutorials/how-to-install-node-js-on-ubuntu-20-04).

---

## **Deploying the Project on AWS**

### **Clone the Project in the Remote VM**

```bash
git clone https://github.com/verma-kunal/AWS-Session.git
```

### **Set Up Environment Variables**

Create a `.env` file in the project directory with the following:

```env
DOMAIN=""
PORT=3000
STATIC_DIR="./client"

PUBLISHABLE_KEY=""
SECRET_KEY=""
```

> **Note**: Set up an **Elastic IP Address** for your EC2 instance. Use this IP address as your `DOMAIN`.

### **Initialize and Start the Project**

```bash
npm install
npm run start
```

### **Update Security Group Inbound Rules**

Edit the **inbound rules** of your EC2 instance's security group to allow traffic on your application’s port.

---

🎉 **Your project is deployed on AWS!**

--- 

This version is well-structured and uses Markdown for better readability. Let me know if you need further adjustments!
