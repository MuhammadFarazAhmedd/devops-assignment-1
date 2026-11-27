# Answers - DevOps Assignment 1


## Part 3, Task 1

Commands:
```
cd ~
mkdir devops-assignment-1
cd devops-assignment-1
git config --global init.defaultBranch main
git init
git config --global user.name "MuhammadFarazAhmedd"
git config --global user.email "fu96555@gmail.com"
git config user.name
git config user.email
```

Output:
```
Initialized empty Git repository in /home/faraz/devops-assignment-1/.git/
MuhammadFarazAhmedd
fu96555@gmail.com
```

Explanation:
Git init is used to start git in our folder. It create a hidden .git folder where project history is saved. Username and email is set so git can identify who made the changes.




## Part 3, Task 2

Commands:
```
mkdir scripts screenshots tips
echo "# DevOps Assignment 1" > README.md
echo "# Answers - DevOps Assignment 1" > answers.md
printf '*.log\ntmp/\n.env\n' > .gitignore
cat .gitignore
echo "test log" > server.log
mkdir tmp
echo "temp" > tmp/temp.txt
echo "API_KEY=abc123" > .env
git status
git add .
git commit -m "Part 3: add README, answers and .gitignore"
```

Output:
```
On branch main

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
	.gitignore
	README.md
	answers.md

nothing added to commit but untracked files present (use "git add" to track)

[main (root-commit) 5dbd696] Part 3: add README, answers and .gitignore
 3 files changed, 5 insertions(+)
 create mode 100644 .gitignore
 create mode 100644 README.md
 create mode 100644 answers.md
```

Explanation:
I have set up directories and files. In addition, I have produced a .gitignore document so that Git ignores log files, a tmp directory and .env. Git status then displays just the non-ignored files. I can then add and commit files to Git.


## Part-1

##Question 01
Problem 01 – Infrequent but large updates
The company release updates after every 3 months. Many changes come together which can cause problems. If any error occur, it is difficult to find and fix.

DevOps Solution: DevOps helps to release small updates frequently. CI/CD is used to test and deploy updates automatically. It makes testing easy and problems can be fixed quickly.

Problem 02 – Blame game
Developers and Operations work in separate teams. When a problem happen, both teams blame each other and nobody take responsibility.

DevOps Solution: DevOps helps both teams to work together and share responsibility. Testing and monitoring help to find problems quickly and learn from mistakes.

##Question 02
1.Plan: We decide what work to do.
  Tool: GitHub Issues.

2.Code: We write the code.
  Tool: Git.

3.Build: We prepare the code to run.
  Tool: GitHub Actions.

4.Test: We check the code for errors.
  Tool: pytest.

5.Release: We prepare software for release.
  Tool: Docker.

6.Deploy: We put software on the server.
  Tool: Kubernetes.

7.Operate: We manage the software and servers.
  Tool: Ansible.

8.Monitor: We check if software is working properly.
  Tool: Prometheus.
These stages work in a loop. First four are Dev stages and last four are Ops stages. After Monitor, we again start from Plan.

##Question 03
1.Culture: Team members help each other and don't blame others.
  Action: Review each other's code.

2.Automation: We use tools to do repeated work automatically.
  Action: Use a script for automatic backups.

3.Lean: We do small work instead of doing everything together.
  Action: Make small commits.

4.Measurement: To check work using numbers.
  Action: Count weekly pull requests.

5.Sharing: We share knowledge with our team.
  Action: Share tips on GitHub.

##Question 04
(a) DORA Metrics:
1.Deployment Frequency: How often we release software.
  Type: Speed.
2.Lead Time for Changes: How long a change takes to go live.
  Type: Speed.
3.Change Failure Rate: How many releases cause problems.
  Type: Stability.
4.Time to Restore Service: How quickly we fix a problem.
  Type: Stability.

(b) Three Ways:
1.Automated test fails a push within minutes: Feedback, because we quickly know about the error.

2.Blameless review after an outage: Continual Learning, because we learn from mistakes.

3.Small daily releases instead of one big quarterly release: Flow, because small changes are easier and faster.


## Part 2

### Task 1

Commands:
```
mkdir -p ~/assignment/linux/data/reports ~/assignment/linux/data/archive
ls -R ~/assignment/linux
```

Output:

/home/faraz/assignment/linux:
data

/home/faraz/assignment/linux/data:
archive  reports

Explanation:
mkdir -p creates the full path including the parent folders, and it does not give an error if the folders already exist.

### Task 2

Commands:
```
cd ~/assignment/linux
touch report.txt run.sh
chmod 640 report.txt
chmod 754 run.sh
ls -l
```

Output:
total 4
drwxrwxr-x 4 faraz faraz 4096 Nov 27 23:30 data
-rw-r----- 1 faraz faraz    0 Nov 27 23:48 report.txt
-rwxr-xr-- 1 faraz faraz    0 Nov 27 23:48 run.sh

Screenshot:

![Part 2 Task 2](screenshots/p2t2.png)

Explanation:
report.txt has 640: the owner can read and write (6), the group can only read (4), and others have no access (0).
run.sh has 754: the owner can read, write and run it (7), the group can read and run it (5), and others can only read it (4).
