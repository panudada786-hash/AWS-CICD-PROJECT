<img width="1485" height="361" alt="Screenshot 2026-09-08 113210" src="https://github.com/user-attachments/assets/ffbdc8a7-c929-4fa1-8428-9c7ffaf640f9" />


# AWS CI/CD Pipeline for Static Website

## 📌 Project Overview

This project demonstrates an automated CI/CD pipeline for deploying a static website using AWS services.

The source code is maintained in **GitHub**. Whenever changes are pushed to the repository, **AWS CodePipeline** automatically triggers the pipeline, **AWS CodeBuild** processes the project, and the generated files are deployed to an **Amazon S3 bucket** configured for static website hosting.

The main goal of this project is to reduce manual deployment effort and understand how cloud-based CI/CD automation works.

---

## 🏗️ Architecture

```text
Developer
    |
    | Git Push
    v
GitHub Repository
    |
    | Source Change
    v
AWS CodePipeline
    |
    v
AWS CodeBuild
    |
    | Build Artifacts
    v
Amazon S3
    |
    v
Static Website
    |
    v
Users
```

### Pipeline Flow

**GitHub → CodePipeline → CodeBuild → S3 → Users**

---

## 🔄 CI/CD Workflow

### 1. Source – GitHub

The website source code is stored in a GitHub repository.

When a developer pushes a new change, the pipeline is triggered automatically.

### 2. Pipeline – AWS CodePipeline

AWS CodePipeline coordinates the CI/CD workflow.

It retrieves the latest source code and passes it to the build stage.

### 3. Build – AWS CodeBuild

AWS CodeBuild executes the commands defined in `buildspec.yml`.

For this static website, the build process prepares and validates the website files and generates the required artifacts.

### 4. Deployment – Amazon S3

The generated website files are deployed to an Amazon S3 bucket.

The S3 bucket is configured to host the static website.

### 5. Website Access

After successful deployment, users can access the updated static website.

---

## ☁️ AWS Services Used

| Service              | Purpose                                       |
| -------------------- | --------------------------------------------- |
| **Amazon S3**        | Static website hosting and deployment         |
| **AWS CodePipeline** | Automates and orchestrates the CI/CD workflow |
| **AWS CodeBuild**    | Builds and prepares website artifacts         |
| **AWS IAM**          | Controls permissions and service access       |
| **GitHub**           | Source code repository                        |

---

## 🛠️ Technologies Used

* HTML
* CSS
* JavaScript
* Git
* GitHub
* AWS CodePipeline
* AWS CodeBuild
* Amazon S3
* AWS IAM

---

## 📂 Project Structure

```text
aws-cicd-static-website/
│
├── index.html
├── about.html
├── contact.html
│
├── css/
│   └── style.css
│
├── js/
│   └── script.js
│
├── images/
│   └── ...
│
├── buildspec.yml
├── .gitignore
└── README.md
```

---

## ⚙️ Build Configuration

The CI/CD pipeline uses `buildspec.yml` to define the CodeBuild process.

Example:

```yaml
version: 0.2

phases:
  install:
    commands:
      - echo "Installing dependencies..."

  pre_build:
    commands:
      - echo "Starting pre-build phase..."

  build:
    commands:
      - echo "Building static website..."
      - echo "Validating website files..."

  post_build:
    commands:
      - echo "Build completed successfully."

artifacts:
  files:
    - '**/*'
```

> Keep this file consistent with the actual `buildspec.yml` used in the project.

---

## 🔐 Security

The project uses AWS IAM to control access between CI/CD services.

Security considerations include:

* IAM service roles for AWS services
* Least-privilege permissions
* No AWS access keys stored in the repository
* No passwords or secrets committed to GitHub
* Controlled access to the S3 deployment bucket

---

## ✨ Key Features

* Automated CI/CD pipeline
* GitHub-based source control
* Automated build process
* Automated deployment to Amazon S3
* Static website hosting
* IAM-based access control
* Reduced manual deployment effort
* Consistent deployment process

---

## 📸 Screenshots

### 1. Website

![Website](docs/website.png)

### 2. AWS CodePipeline

![CodePipeline](docs/codepipeline-success.png)

### 3. AWS CodeBuild

![CodeBuild](docs/codebuild-success.png)

### 4. S3 Deployment

![S3 Deployment](docs/s3-deployment.png)

### 5. Architecture

![Architecture](docs/architecture.png)

---

## 🧪 Testing

The deployment was verified by:

1. Making a change to the website source code.
2. Pushing the change to GitHub.
3. Checking that CodePipeline was triggered.
4. Verifying the CodeBuild stage.
5. Checking successful deployment to S3.
6. Opening the website and confirming the updated content.

---

## 📈 Benefits of CI/CD

This project demonstrates how CI/CD can:

* Reduce manual deployment steps
* Automate repetitive tasks
* Provide consistent deployments
* Detect build failures
* Improve deployment speed
* Maintain deployment history

---

## 🎯 What I Learned

Through this project, I learned:

* How CI/CD pipelines work
* How GitHub integrates with AWS CodePipeline
* How CodeBuild executes build commands
* How static websites can be hosted on Amazon S3
* How IAM service roles control AWS resource access
* How to troubleshoot pipeline and deployment failures
* How source-code changes can be automatically deployed to the cloud

---

## 🚀 Future Improvements

Possible improvements include:

* Add Amazon CloudFront for CDN and better performance
* Add HTTPS using AWS Certificate Manager
* Add automated testing
* Add CloudWatch monitoring and notifications
* Create separate development and production environments
* Improve S3 security using CloudFront Origin Access Control

---

## 👨‍💻 Author

**Pranav Kumbhar**

Computer Engineering Student

---

## ⭐ Project Highlights

**Source Control:** GitHub
**CI/CD:** AWS CodePipeline + CodeBuild
**Hosting:** Amazon S3
**Security:** AWS IAM
**Deployment:** Automated
