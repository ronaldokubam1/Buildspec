# 🚀 CI/CD Pipeline: Python App on AWS CodePipeline

This project demonstrates a **2-stage CI/CD pipeline** using **GitHub**, **AWS CodePipeline**, and **AWS CodeBuild**.  
The pipeline automatically builds and deploys a simple Python application that prints:

>  **"Hello world from Ronaldo"**

---

## 🧾 Homework Overview

| Component | Description |
|------------|--------------|
| **Source Control** | [GitHub](https://github.com/) |
| **CI/CD Orchestration** | [AWS CodePipeline](https://aws.amazon.com/codepipeline/) |
| **Build Tool** | [AWS CodeBuild](https://aws.amazon.com/codebuild/) |
| **Runtime** | Python 3.9 |
| **Application** | A simple Python script — `my_app.py` |

---

## ⚙️ How It Works

1. **GitHub Commit** → Triggers the pipeline when new code is pushed.  
2. **AWS CodePipeline** → Orchestrates the workflow.  
3. **AWS CodeBuild** → Builds and runs the Python app using the `buildspec.yml` file.  
4. **Output** → Displays `"Hello world from Ronaldo"` in the build logs.

---

## 🧰 Buildspec Overview

Below is the simplified **`buildspec.yml`** used in the project:

```yaml
ersion: 0.2

phases:
  install:
    runtime-versions:
      python: 3.9 # instal python
    commands:
      - echo === INSTALL YOUR PACKAGES HERE ===
    
  pre_build:
    commands:
      - echo === CHECKING FOR PYTHON INSTALLED ===
      - python --version
      - echo === INSTALLING PYTHON INSTALL ===
      - aws --version
    
  build:
    commands:
      - echo === RUN OUR CODE/APP ===
      - python3 my_app.py #run the python file
    
  post_build:
    commands:
      - echo === POST BUILD ACTIONS HERE ===
      - echo "Build completed on `date`"

artifacts:
  files:
    - '**/*'
## 🧩 Steps Followed

### 🪄 Step 1: Create GitHub Repository

1. **Created a new repository** named: `Buildspec`.
2. **Cloned** the repository locally.
3. Added two files:
   - **`my_app.py`** → Simple Python script that prints your name:
     ```python
     print("Hello world from Ronaldo")
     ```
   - **`buildspec.yml`** → Instructions for AWS CodeBuild to install dependencies and run the Python script.
4. **Pushed** both files to GitHub.

---<img width="1366" height="768" alt="Screenshot (303)" src="https://github.com/user-attachments/assets/969d5281-3e8c-4258-b0d7-2b2b7659c087" />


### ⚙️ Step 2: Create the AWS CodePipeline

1. **Source Stage:**  
   - Selected **GitHub** as the source provider.  
   - Connected the repository to AWS CodePipeline.

2. **Build Stage:**  
   - Added a **CodeBuild Project**.  
   - Configuration details:
     - **Environment:** Managed Image  
     - **Operating System:** Amazon Linux  
     - **Runtime:** Standard  
     - **Buildspec:** Default (`buildspec.yml`)  

💡 *This setup ensures that any commit pushed to GitHub automatically triggers the pipeline to build and run your Python app.*

---<img width="1366" height="768" alt="Screenshot (303)" src="https://github.com/user-attachments/assets/0120f66b-2dd2-40c0-bbec-a48ee25f947a" />



### 🧱 Step 3: CodeBuild Execution Log

Once the pipeline runs, the **CodeBuild logs** show:

---<img width="1366" height="768" alt="Screenshot (304)" src="https://github.com/user-attachments/assets/507e1307-41fe-4a34-8bae-9f267fcb10ae" />


✅ The build completes successfully, proving that the pipeline is configured correctly.

---<img width="1366" height="768" alt="Screenshot (302)" src="https://github.com/user-attachments/assets/d2542b9c-bc56-4281-9483-71bc84d89c50" />


### 🏁 Conclusion

This homework demonstrates how to:

- 🔗 **Integrate GitHub with AWS CodePipeline** for continuous delivery.  
- ⚙️ **Configure AWS CodeBuild** to use the **Python 3.9 runtime**.  
- 🐍 **Run a simple Python script (`my_app.py`) automatically** whenever new code is pushed.  
- 📋 **Validate build logs** to confirm successful execution (`Hello world from Ronaldo`).  

---

### 🌟 Key Takeaways

- AWS CodePipeline seamlessly automates CI/CD from GitHub to AWS.
- CodeBuild provides an isolated environment for building and testing Python apps.
- The process ensures faster feedback, consistency, and reliability in deployments.

---

### ✨ Author

**Kubam Ronaldo**  
🚀 Cloud & DevOps Enthusiast  
📧 [kubamnronaldoy@gmail.com]  

---


 


