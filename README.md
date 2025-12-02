1. Create a Private Repository on GitHub
Go to github.com
Click New Repository
Enter repository name
Select Private
Click Create Repository

2. Initialize Git in Local Project
Open terminal in your project root:
cd /path/to/project
git init

3. Add Remote Repository
Copy the URL from GitHub and run:
git remote add origin https://github.com/username/private-repo.git

Add & Commit Files
git add .
git commit -m "Initial commit"

Push to GitHub
For main branch (default):
git push -u origin main

Task 2: Explore All Git Commands

1. Git Basic Commands
Check Git Version
git --version

Configure User Info
git config --global user.name "Your Name"
git config --global user.email "you@example.com"

List Git Configurations
git config --list

2. Repository Management
Initialize Repo
git init

Clone Repo
git clone https://github.com/username/repo.git

View Remotes
git remote -v

Add Remote
git remote add origin https://github.com/username/repo.git

Push to Remote
git push origin main

Pull from Remote
git pull origin main

Remove Remote
git remote remove origin

Rename Remote
git remote rename origin upstream

Fetch Updates
git fetch origin

Change Remote URL
git remote set-url origin https://github.com/username/new.git

Show Remote Info
git remote show origin

4. Branching & Merging
List/Create/Delete Branch
git branch
git branch new-branch
git branch -d branch-name
git branch -D branch-name   # force delete

List Remote Branches
git branch -r

Checkout Branch
git checkout branch-name
git checkout -b new-branch

Prune Deleted Remote Branches
git remote prune origin

Fetch Specific Branch
git fetch origin feature-branch

Set Upstream Branch
git push --set-upstream origin feature-branch

Merge Branch
git checkout main
git merge branch-name

Rebase on Remote
git fetch origin
git rebase origin/main

5. Undoing Changes
Unstage File
git reset file.txt

Revert Commit
git revert <commit>

6. View History
Commit Log
git log
git log --oneline

Show Differences
git diff

Show Commit Details
git show <commit>

7. Restore File Before Staging
git restore filename

8. Correct Last Commit Message
git commit --amend -m "Corrected message"

9. Recover Deleted Branch
git reflog
git checkout -b branch-name <commit-hash>

10. Download Latest Changes Without Merge
git fetch origin

11. Remove Sensitive File from History
git filter-branch --force --index-filter \
"git rm --cached --ignore-unmatch secrets.txt" \
--prune-empty --tag-name-filter cat -- --all

12. Merge Two Branches
git checkout previous-branch
git merge another-branch

13. Resolve Merge Conflicts

Open file → remove conflict markers

Then:

git add filename
git commit

14. .gitignore
Create File
touch .gitignore

Common Rules
*.log
temp/
secret.txt
folder/*
!folder/important.txt
*.bak

15. Find Who Changed Each Line
git blame script.py

16. Git Stash
git stash
git switch another-branch
git switch main
git stash apply

17. Check Merged Branches
git branch --merged

18. Delete Multiple Branches
git branch -d branch1 branch2 branch3



----------------------------------------------------------------------------------

1. Collaborative Coding – HOW TO DO
A. Collaboration Using an ORGANIZATION
Step 1: Create Organization

Login → GitHub

Click New Organization → Create a free organization

Step 2: Set Up Organization

Enter Organization name

Add email, verification details
Click Next

Step 3: Add Members

Add team members

Invitations go to others → They must accept

Then complete setup

Set Member Permissions

Go to:

Settings → Member privileges → Base permissions → Write
Projects → Base permissions → Write

Step 4: Create Repository Inside Organization

Create a repo inside the organization

Set it as Private (recommended)

Now all members can contribute based on permissions.

B. Collaboration Using Shared Repository
✔ Steps for Collaborator 1 (Owner)

Go to:

Settings → Collaborators → Add people


Add collaborator

They receive an invitation → They accept

✔ Steps for Collaborator 2
Step 1: Configure Git
git config --global user.name "Your Name"
git config --global user.email "you@example.com"

Step 2: Clone Shared Repo

Copy repo URL → then:

git clone https://github.com/username/repo.git
cd repo

Step 3: Create Your Branch
git checkout -b feature/my-task

Step 4: Make Changes

After editing:

git add .
git commit -m "Meaningful commit message"

Step 5: Push Branch
git push origin feature/my-task

Step 6: Keep Your Branch Updated
git checkout main
git pull origin main
git checkout feature/my-task
git merge main

🚀 Exercise on FORK – HOW TO DO
✔ If you want to contribute to someone's public repo
Step 1: Fork Repo

Open:
https://github.com/Person1/project-name
Click Fork → repo becomes:
https://github.com/Person2/project-name

Step 2: Clone Your Fork
git clone https://github.com/Person2/project-name
cd project-name

Step 3: Make Changes, Commit, Push
git add .
git commit -m "My update"
git push origin main

Step 4: Open Pull Request

GitHub → Pull Request → Create PR

✔ Steps for Original Owner (Person 1)

Go to Pull Requests

Review → Merge Pull Request

Confirm merge

✅ 2. Resolving Merge Conflicts – HOW TO DO

Conflicts happen when two people edit the same line.

Step 1: Check Which Files Have Conflicts
git status


You will see:

both modified: f1.txt

Step 2: Open the File

Git adds conflict markers:

<<<<<<< HEAD
print("Hello from collaborator 1")
=======
print("Hello from collaborator 2")
>>>>>>> feature/branch2

Step 3: Fix the Conflict

Either keep one version OR combine:

print("Hello from collaborator 1")
print("Hello from collaborator 2")


Remove all:

<<<<<<<
=======
>>>>>>>

Step 4: Mark Conflict as Resolved
git add f1.txt

Step 5: Complete Merge
git commit

⚠️ To abort merge:
git merge --abort

🚨 Example of Real Conflict Scenario

Collaborator 2 adds a line → pushes → no conflict

Collaborator 1 adds a line at SAME PLACE → pushes → conflict

Collaborator 2 runs:

git pull


Opens README → sees markers → resolves → pushes

✅ 3. Creating and Applying Patch – HOW TO DO

A patch is a file that contains the changes (diff) of your commit.

A. How to CREATE Patch
Step 1: Clone the Public Repo
git clone https://github.com/Person1/project.git
cd project

Step 2: Edit File & Commit
git add .
git commit -m "Updated feature"

Step 3: Get Commit Hash
git log


Copy hash: abc1234

Step 4: Create Patch File
git format-patch -1 abc1234


This generates:

0001-your-commit-message.patch

B. How to SEND Patch

Send .patch file via email/WhatsApp.

C. How to APPLY Patch (Owner)

Place patch in the repo folder.

✔ Option 1 — Apply only changes (NO commit)
git apply 0001-file.patch
git add .
git commit -m "Applied patch"

-----------------------------------------------------------------------------------------
4. Create Maven Java Project (Eclipse)

Open Eclipse → File → New → Project

Select Maven Project

Choose archetype:
maven-archetype-quickstart (1.4)

Enter:

Group ID → com.example

Artifact ID → my-maven-project

Finish → Project creates with pom.xml

Run Maven Tasks

Right-click project ➝ Run As →

✔ Maven Clean
✔ Maven Install
✔ Maven Test
✔ Maven Build → Goals → clean install test

Run program:
➡ Right-click App.java → Run As → Java Application
Output: Hello World

5. Create Maven Web Project (WAR)

File → New → Maven Project

Archetype → maven-archetype-webapp

Enter GroupId/ArtifactId

Add Servlet Dependency in pom.xml

<dependency>
    <groupId>javax.servlet</groupId>
    <artifactId>javax.servlet-api</artifactId>
    <version>4.0.1</version>
    <scope>provided</scope>
</dependency>

Configure Tomcat
Window → Show View → Servers → Add → Tomcat v9


Modify tomcat-users.xml → Add users & roles.

Build & Run Web Application

✔ mvn clean install
✔ Right-click index.jsp → Run on Server

Output → Webpage displayed in browser

💡 WAR creation:

<packaging>war</packaging>


Build command:

mvn package → target/*.war

6. Java Version Setup in POM
<plugin>
  <groupId>org.apache.maven.plugins</groupId>
  <artifactId>maven-compiler-plugin</artifactId>
  <version>3.11.0</version>
  <configuration>
    <source>17</source>
    <target>17</target>
  </configuration>
</plugin>


Verify:

mvn package
jar tf target/app.jar

7. JUnit Testing

📂 Place inside → src/test/java

public class AppTest {
    @Test
    public void testSum() {
        assertEquals(5, 2 + 3);
    }
}


Run:

mvn test


Reports generated:

target/surefire-reports/

8. Adding Resource Files

📂 Place inside:

src/main/resources/config.properties


Read in code:

InputStream input = getClass().getClassLoader().getResourceAsStream("config.properties");


After build → check:

target/classes/

9. Multi-Module Maven Project
parent/
 ├── pom.xml (packaging: pom)
 ├── core/
 │    └── pom.xml
 └── web/
      └── pom.xml


✔ Parent pom manages dependencies
✔ Modules build individually to their target/ folders

10. Creating Executable JAR

Add to pom.xml:

<build>
  <plugins>
    <plugin>
      <groupId>org.apache.maven.plugins</groupId>
      <artifactId>maven-jar-plugin</artifactId>
      <configuration>
        <archive>
          <manifest>
            <mainClass>com.example.Main</mainClass>
          </manifest>
        </archive>
      </configuration>
    </plugin>
  </plugins>
</build>


Build & Run:

mvn package
java -jar target/app.jar

----------------------------------------------------------------------------------
Maven java and web project and pushing into GITHUB

Creation of Maven Java Project Procedure Steps:
Step1: Open Eclipse IDE for Enterprise JAVA and WEB developers.
Step2: Click on File->New->Maven Project
Step3: Type quickstart in Filter and wait for artifacts to load.
Step4: Select org.apache.maven.archetypes   maven-archetype-quickstart 1.4 and click on next
Step5: Mention TeamID: as SE, ArtifactID: MavenJava and click on next
Step6: Now in Console we can see all the artifacts are grouped and console is waiting as Y: Now click Y and finally SE.MavenJava gets ready by combining all the artifacts.
Step7: We can see our MavenJava project ready with its own pom.xml file in the Project Explorer tool bar menu present at the left side.
Step8: Now click on src/main/java->SE.MavenJava->App.java where we can find a code sample for HELLO WORLD.
Step9: Now right click on App.java->Run as->Maven Clean
Step10: Now right click on App.java->Run as->Maven Install
Step11: Now right click on App.java->Run as->Maven Test
Step12: Now right click on App.java->Run as->Maven Build
Step13: In Goals, Type “clean install test”, click on apply next click on Run, for building the MavenJava project.
Step14: Every phase is checked and BUILD SUCCESS message can be seen in the console. 
Step15: Now right click on App.java->Run as->Java Application, click on OK.
Step16: Hello world is shown as output for MavenJava Project.
Creation of Maven Web Project Procedure Steps:
Step1: Open Eclipse IDE for Enterprise JAVA and WEB developers.
Step2: Click on File->New->Maven Project
Step3: Type webapp in Filter and wait for artifacts to load.
Step4: Select org.apache.maven.archetypes   maven-archetype-webapp 1.4 and click on next
Step5: Mention TeamID: as SE, ArtifactID: MavenWeb and click on next
Step6: Now in Console we can see all the artifacts are grouped and console is waiting as Y: Now click Y and finally SE.MavenWeb gets ready by combining all the artifacts.
Step7: We can see our MavenWeb project ready with its own pom.xml file in the Project Explorer tool bar menu present at the left side.
Step8: Now click on MavenWeb->src->main->Webapp->index.jsp where we can find a code sample for HELLO WORLD.
Step9: Now open browser and open mvnrepository.com
Step10: Search for JAVA servlet API and click on the latest version.
Step11: Copy the dependency code of the servlet. And paste it in MavenWeb’s pom.xml under target folder.
Step12: Now click on window in the menu bar, click on showview->servers.
Step13: Add servers by clicking on “No servers available”.
Step14: Select Tomcat v9.0 server/ Tomcat v11.0 server in the server type Click on next, select Apache Tomcat v9.0(optional), Click Apply and close.
Step15: Now we can find tomcat server attached to the project in server menu of the console. Duble click on it where the tomcat configuaration page appears.
Step16: select “Use Tomcat Installation”(which Is 2nd option) in Server locations, and modify the port numbers to “0” for admin port and “8085” for Https/1.1 and close the tab.
Step17: Double click “servers” folder present at the left side in project explorer, click on Tomcat v9.0 server at localhost-config->tomcat-users.xml, scroll to the end and paste the following exactly above </tomcat-users> tag and close the tab.

role rolename="admin-gui,manager-gui ,manager-script,manager-jmx,manager-status"/><user password="1234" roles="manager-gui, admin-gui ,manager-script" username="admin"/> 

Step18: Now right click on index.jsp ->Run as->Maven Clean
Step19: Now right click on index.jsp ->Run as->Maven Install
Step20: Now right click on index.jsp ->Run as->Maven Test
Step21: Now right click on index.jsp ->Run as->Maven Build
Step22: In Goals, Type “clean install test”, click on apply next click on Run, for building the MavenWeb project.
Step23: Every phase is checked and BUILD SUCCESS message can be seen in the console. 
Step24: Now right click on index.jsp ->Run as->Run on server, click on OK.
Step25: Select choose an existing server and click on finish.
Step26: Hello world Webpage is shown as output for MavenWeb Project.

Steps to Push the Maven Projects to GIT:
Java Project Push Procedure Steps:
Step1: Create two repositories for MavenJava and MavenWeb projects in your GitHUB account.
Step2: In eclipse right click on MavenJava folder present in project explorer and select show in local terminal option->GitBash.
Step3: execute: git init-> git branch –M main.
Step4: Now add your repository to the MavenJava using, git remote add origin <git java repository url> command.
Step5: execute: git add . -> git commit –m “Maven java push” -> git push –u origin main
Step6: Now refresh your GitHub account and we can see our MavenJava files are pushed to MavenJava repository in your GitHub account.
Web Project Push Procedure Steps:
Step1: In eclipse right click on MavenWeb folder present in project explorer and select show in local terminal option->GitBash.
Step2: execute: git init-> git branch –M main.
Step3: Now add your repository to the MavenWeb using, git remote add origin <git Web repository url> command.
Step4: Push your web project same as Java to GitHub. 
Step5: Now refresh your GitHub account and we can see our MavenWeb files are pushed to MaveWeb repository in your GitHub account.

Conclusion: we have learnt creation of Java and Web project through Maven and pushing them to GitHub.


-----------------------------------------------------------------------

Here is a **clean, well-structured Lab Action Plan for Week 5 – Docker with Redis & Dockerfile**, simplified for notes and easy execution during lab.

---

# 📘 **WEEK-5 LAB ACTION PLAN – Docker**

---

## **Part 1 – Working with Docker CLI using Redis**

### 🔹 Step-1 — Pull Redis Image

```bash
docker pull redis
```

Downloads Redis image from Docker Hub.

### 🔹 Step-2 — Run Redis Container

```bash
docker run --name my-redis -d redis
```

* Creates and starts a container named **my-redis**
* `-d` → runs container in background

### 🔹 Step-3 — Check Running Containers

```bash
docker ps
```

Shows only *active* containers.

### 🔹 Step-4 — Access Redis CLI inside Container

```bash
docker exec -it my-redis redis-cli
```

Now run commands like:

```
SET name "Alice"
GET name
```

### 🔹 Step-5 — Stop Container

```bash
docker stop my-redis
```

### 🔹 Step-6 — Start Container Again

```bash
docker start my-redis
```

### 🔹 Step-7 — Remove Container

```bash
docker rm my-redis
```

### 🔹 Step-8 — Remove Redis Image

```bash
docker rmi redis
```

---

---

## **Part 2 – Working with Dockerfile**

### 📁 Step-1 — Create Project Directory

Windows:

```bash
mkdir C:\DockerProjects\Redis
cd C:\DockerProjects\Redis
```

Mac/Linux:

```bash
mkdir ~/DockerProjects/Redis
cd ~/DockerProjects/Redis
```

### 📄 Step-2 — Create `Dockerfile`

```
FROM redis:latest
CMD ["redis-server"]
```

---

### 🏗 BUILD IMAGE

```bash
docker build -t redisnew .
```

Creates image named **redisnew**

### ▶ RUN CONTAINER

```bash
docker run --name myredisnew -d redisnew
```

### CHECK CONTAINERS

```bash
docker ps
docker ps -a   # includes stopped containers
```

### STOP CONTAINER

```bash
docker stop myredisnew
```

---

---

## **PART 3 – Docker Hub Operations**

### 🔐 Login

```bash
docker login
```

### 📌 Commit & Create Image From Container

```bash
docker commit <container_ID> budarajumadhurika/redis1
```

### 📥 View Images

```bash
docker images
```

### 📤 Push to Docker Hub

```bash
docker push budarajumadhurika/redis1
```

### ❌ Delete Container

```bash
docker rm <container_ID>
```

### ❌ Remove Image

```bash
docker rmi budarajumadhurika/redis1
```

---

---

## **Part-4 — Pull Again & Run from Docker Hub**

### 📥 Pull Image from Hub

```bash
docker pull budarajumadhurika/redis1
```

### ▶ Run Redis from Hub Image

```bash
docker run --name myredis -d budarajumadhurika/redis1
```

### 🔗 Enter Redis CLI

```bash
docker exec -it myredis redis-cli
```

Inside Redis:

```
SET name "Abcdef"
GET name
exit
```

### Stop & Remove Container & Image

```bash
docker stop myredis
docker rm <container_ID>
docker images
docker rmi budarajumadhurika/redis1
```

---

## **Optional: Logout**

```bash
docker logout
```

---

------------------------------------------------------------------------------------------------------
Here is a **clean, exam-ready, easy-to-remember** version of the steps you provided.
I rewrote everything in a **simple structured format**, removing confusion while keeping all important points.

---

# ✅ **Maven Java Automation — Jenkins Steps (Clean Notes for Exam)**

---

## **Step 1: Open Jenkins**

* Open browser → `localhost:8080`
* Click **New Item** → choose **Freestyle Project**
* Enter name: **MavenJava_Build**
* Click **OK**

---

## **Step 2: Configure MavenJava_Build**

### **Project Setup**

* **Description:** Java Build demo
* **Source Code Management (SCM):**

  * Git Repo URL → *Git Maven Java Project URL*
  * Branch → */main* or */master*

### **Build Steps**

1. **Invoke top-level Maven targets**

   * Maven Version: **MAVEN_HOME**
   * Goals: **clean**

2. **Invoke top-level Maven targets**

   * Maven Version: **MAVEN_HOME**
   * Goals: **install**

### **Post-build Actions**

* **Archive artifacts**

  * Files: `**/*`
* **Build other projects**

  * Next Project: **MavenJava_Test**
  * Trigger: **Only if build is stable**
* Click **Apply** → **Save**

---

## **Step 3: Create MavenJava_Test Project**

* New Item → **MavenJava_Test**
* Click **OK**

### **Configure MavenJava_Test**

* **Description:** Test demo
* **Build Environment:**

  * Tick → *Delete workspace before build starts*

### **Build Steps**

1. **Copy artifacts from another project**

   * From project: **MavenJava_Build**
   * Build: *Stable build only*
   * Artifacts: `**/*`

2. **Invoke top-level Maven targets**

   * Maven Version: **MAVEN_HOME**
   * Goals: **test**

### **Post-build Actions**

* Archive artifacts → `**/*`
* Save

---

## **Step 4: Create Pipeline View**

* Dashboard → click **+** beside "All"
* View name: **MavenJava_Pipeline**
* Select **Build Pipeline View**
* **Initial job:** MavenJava_Build
* Save

---

## **Step 5: Run Pipeline**

* Click **Run** icon
* Open console (black box) → check logs
* If both builds → green color → pipeline successful

---

# ✅ **Maven Web Automation — Jenkins Steps (Clean Notes)**

---

## **Step 1: Create MavenWeb_Build**

* New Item → **MavenWeb_Build**
* Description: Web Build demo
* SCM:

  * Git URL: *Git Maven Web repo URL*
  * Branch: */main* or */master*

### **Build Steps**

* Maven → clean
* Maven → install

### **Post-build Actions**

* Archive artifacts → `**/*`
* Build other projects → **MavenWeb_Test**

  * Trigger: Only if stable
* Save

---

## **Step 2: Create MavenWeb_Test**

* Description: Test demo
* Build Environment: Delete workspace before build

### **Build Steps**

1. Copy Artifacts

   * From project: **MavenWeb_Build**
   * Stable build only
   * Artifacts: `**/*`

2. Maven Goals → **test**

### **Post-Build**

* Archive artifacts → `**/*`
* Build other projects → **MavenWeb_Deploy**
* Save

---

## **Step 3: Create MavenWeb_Deploy**

* Description: Web Code Deployment
* Build Environment → Delete workspace before build

### **Build Steps**

* Copy artifacts

  * From: MavenWeb_Test
  * Stable build only
  * Artifacts: `**/*`

### **Post-build Actions**

* Deploy WAR/EAR to Container

  * WAR File: `**/*.war`
  * Context path: **webpath**
  * Add container: **Tomcat 9.x Remote**

    * Username: admin
    * Password: 1234
    * Tomcat URL: `http://localhost:8085/`

* Save

---

## **Step 4: Create Pipeline View**

* Dashboard → "+"
* View name: **MavenWeb_Pipeline**
* Select: **Build Pipeline View**
* Initial Job → MavenWeb_Build
* Save

---

## **Step 5: Run & Verify**

* Click **Run**
* Check green status
* Open Tomcat → `http://localhost:8085/`
* Open `/webpath`
* Enter Tomcat credentials
* Application should load

---


_________________________________________________
JENKINS PIPELINE (GENERAL CONFIGURATION)

(Simple & Clean for Exams)

1. Description

In this section, we enter a brief explanation about the project.
Example:
“This project demonstrates automated build, test, and package using Jenkins Pipeline.”

2. Build Triggers

In this section, we can select triggers such as:

Build periodically
* * * * *

(Choose based on requirement.)

3. Advanced Project Options

Under this section:

Go to Definition

Select Pipeline Script

This enables us to write a full scripted pipeline directly inside Jenkins.

4. Pipeline Script Section

pipeline {
    agent any
    tools{
        jdk 'JAVA_HOME'
        maven 'MAVEN_HOME'
    }
    stages {
        stage('git repo & clean') {
            steps {
                bat "rmdir /s /q Harshitha_Jenkins_Maven || exit 0"
                bat "git clone https://github.com/Harshitha-Macha/Harshitha_Jenkins_Maven.git"
                bat "mvn clean -f Harshitha_Jenkins_Maven/pom.xml"
            }
        }
        stage('install') {
            steps {
                bat "mvn install -f Harshitha_Jenkins_Maven/pom.xml" 
            }
        }
        stage('test') {
            steps {
                bat "mvn test -f Harshitha_Jenkins_Maven/pom.xml"
            }
        }
        stage('package') {
            steps {
                bat "mvn package -f Harshitha_Jenkins_Maven/pom.xml"
            }
        }
    }
}
5. Save Configuration

_______
DEPLOYMENT OF index.html USING EC2 INSTANCE IN AWS
Step 1: Login to AWS / Canvas Account

Open the Course Invitation Mail → click Start.

AWS Academy opens → Select Student Login → enter email & password.

Click Modules.

Scroll down → select Launch AWS Academy Lab.

Click Start Lab and wait until the AWS icon turns Red → Green.

Click AWS to enter the console.

Step 2: Create an EC2 Instance

In the AWS Console → search for EC2 → click it.

Click Launch Instance.

Stage 1: Name

Give instance name: ubuntu.

Stage 2: Select AMI

Select Ubuntu Server (Free Tier Eligible).

Stage 3: Architecture

Ensure 64-bit (x86) is selected.

Stage 4: Instance Type

Choose t2.micro (1 CPU, 1 GB RAM, free tier).

Stage 5: Create Key Pair

Click Create New Key Pair.

Enter keypair name.

Download the .pem file.

Save it safely (example: Desktop → AWS folder).

Stage 6: Network Settings – Security Group

Enable:

HTTP (80)

HTTPS (443)

SSH (22)

(These are required to access the webpage.)

Stage 7: Storage

Default storage: 8 GB (root volume).

Stage 8: Launch

Click Launch Instance.

Go to Instances page.

Wait until instance shows:

Running

Status Checks = 2/2 passed

Connect

Tick the instance → click Connect → open SSH Client tab.

Copy the ssh -i command for later use.

Step 3: Connect Local System to EC2 (SSH)
Step a:

Copy the path where the .pem file is saved.
Example: D:\SUNNY\SELABWEB\AWS

Step b:

Open PowerShell (Run as Administrator).
Navigate to the key file path:

cd <path>

Step c:

From AWS, copy the SSH command under “SSH Client”.

Step d:

Paste and run the SSH command in PowerShell:

ssh -i "<keypair>.pem" ubuntu@<public-ip>

Step 4: Install Required Software in Ubuntu

Run the following commands:

Update packages
sudo apt update

Install Docker
sudo apt-get install docker.io

Install Git
sudo apt install git

Install Nano (Text Editor)
sudo apt install nano

Step 5: Create Web Application and Push to GitHub
Step a:

Create an index.html file (Example folder).

Step b:

Open Git Bash in that folder.

Step c:

Initialize Git:

git init
git add .
git commit -m "first commit"

Step d:

Create a new GitHub repository (example: AWS).

Step e:

Run commands (copied from GitHub):

git branch -M main
git remote add origin <https-url>
git push -u origin main

Step f:

Refresh GitHub → confirm index.html uploaded.

Step 6: Clone Repository in EC2 Server
Step g:

Copy the repository HTTPS link.

Step h:

Clone it inside EC2:

git clone <repository-url>

Step i:

Navigate into folder:

cd AWS
ls

Step 7: Create Dockerfile and Build Image
Step j:

Create Dockerfile:

nano Dockerfile

Step k:

Add the following content:

FROM nginx:latest
COPY . /usr/share/nginx/html


Save:

Ctrl + O → Enter

Ctrl + X (exit)

Step L: Build Docker Image
sudo docker build -t mywebapp .

Step m: Run Docker Container
sudo docker run -d -p 80:80 mywebapp

Step 8: Test the Deployment
Step n:

Open EC2 → Instances.

Step o:

Copy Public IPv4 Address.

Step p:

Open a browser → paste the IP:

http://<public-ip>


If HTTPS doesn’t work, use HTTP.
The index.html page should load.

Step 9: Stop and Terminate Resources
Step Q: Stop Container
sudo docker ps
sudo docker stop <container-id>

Terminate EC2 Instance

Go to Instances

Click Instance State → Terminate

End Lab

Click End Lab in AWS Academy.
