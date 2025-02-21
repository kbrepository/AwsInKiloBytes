Got it! Here's your **`README.md`** file, which includes **instructions, code samples, and a screenshot link** of `index.html`.  

---

### **`README.md`**
```md
# 🚀 AWS S3 Static Website Deployment using CloudFormation  

This project demonstrates how to deploy a **static website** on AWS **S3** using **CloudFormation**.  

## 📌 Features  
✅ Host a static website on S3  
✅ CloudFormation template to automate setup  
✅ Custom 404 Error Page (`error.html`)  
✅ Public Access using Bucket Policy  
✅ Fancy UI with CSS Animations & Marquee Tags  

---

## 📜 Prerequisites  
Before deploying, ensure you have:  
- An **AWS Account**  
- **AWS CLI** installed & configured (`aws configure`)  
- **CloudFormation permissions** (`s3:CreateBucket`, `s3:PutBucketPolicy`, etc.)  

---

## 📂 Project Structure  
```
📁 s3-static-website
│── 📜 s3-static-website.yaml   # CloudFormation Template
│── 📜 index.html               # Home Page
│── 📜 error.html               # Custom 404 Page
│── 📜 README.md                # Project Documentation
│── 🖼️ index-preview.png        # Screenshot of the index.html page
```

---

## ⚙️ **CloudFormation Deployment**  

### 1️⃣ **Deploy the CloudFormation Stack**  
Run the following command to create the S3 bucket & configure website hosting:  
```bash
aws cloudformation create-stack --stack-name S3StaticWebsite --template-body file://s3-static-website.yaml --capabilities CAPABILITY_NAMED_IAM
```

### 2️⃣ **Upload Website Files to S3**  
Once the stack is created, upload `index.html` and `error.html` to the S3 bucket:  
```bash
aws s3 cp index.html s3://your-s3-bucket-name/
aws s3 cp error.html s3://your-s3-bucket-name/
```

### 3️⃣ **Get Website URL**  
Retrieve the static website URL from the CloudFormation output:  
```bash
aws cloudformation describe-stacks --stack-name S3StaticWebsite --query "Stacks[0].Outputs[?OutputKey=='WebsiteURL'].OutputValue" --output text
```
Alternatively, you can also get it from the **AWS S3 Console** under "Static Website Hosting."

---

## 🖼️ **Homepage Preview**
Below is a preview of the homepage:

![Homepage Preview](index-preview.png)

> *(Ensure `index-preview.png` is uploaded to your S3 bucket or GitHub repository for proper rendering.)*

---

## 🛠️ **Cleanup**
If you want to **delete the static website**, run:
```bash
aws cloudformation delete-stack --stack-name S3StaticWebsite
```
This will remove the S3 bucket and website hosting.

---

## 📢 **Conclusion**
You have successfully deployed a **fancy static website** on **AWS S3** using **CloudFormation**! 🎉  

---

💡 **Need Help?**  
Feel free to open an issue or reach out. 🚀  
```

---

### **Instructions for Adding `index-preview.png`**
1. Take a **screenshot** of `index.html` rendered in a browser.  
2. Save it as `index-preview.png`.  
3. Upload it to your **GitHub repository** or **S3 bucket**.  
4. If hosting on GitHub, ensure it's in the root directory for proper linking.  
5. If hosting on S3, use a public URL like:
   ```
   ![Homepage Preview](https://your-bucket-name.s3.amazonaws.com/index-preview.png)
   ```
6. **Commit & push** the `README.md` and `index-preview.png` to your repo.  

Now your `README.md` contains **proper documentation with a screenshot preview**. 🚀  
Let me know if you need any changes! 😃