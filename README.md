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

