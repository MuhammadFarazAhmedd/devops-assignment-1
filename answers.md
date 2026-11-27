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
Initialized empty Git repository in /home/faraz/devops-assignment-1/.git/
MuhammadFarazAhmedd
fu96555@gmail.com

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



### Task 3

Commands:
```
cd ~/assignment/linux
printf 'INFO start\nERROR disk full\nINFO user login\nWARN slow response\nERROR timeout\nINFO user logout\nERROR disk full\nINFO backup done\nWARN memory high\nERROR timeout\nINFO restart\nERROR disk full\n' > server.log
grep ERROR server.log | wc -l
grep WARN server.log | wc -l
grep ERROR server.log | grep disk
```

Output:

faraz@faraz-HP-Pavilion-m7-Notebook-PC:~/assignment/linux$ grep ERROR server.log | wc -l
5
faraz@faraz-HP-Pavilion-m7-Notebook-PC:~/assignment/linux$ grep WARN server.log | wc -l
2
faraz@faraz-HP-Pavilion-m7-Notebook-PC:~/assignment/linux$ grep ERROR server.log | grep disk
ERROR disk full
ERROR disk full
ERROR disk full

Explanation:
Grep is used to find lines containing a word. Pipe (|) sends the output to the next command and wc -l counts the lines.


### Task 4

Commands:
```
sleep 600 &
ps
kill 42756
ps
sleep 600 &
ps
kill -9 42929
ps
```

Output:
[1] 42756
    PID TTY          TIME CMD
  12520 pts/0    00:00:00 bash
  42756 pts/0    00:00:00 sleep
  42765 pts/0    00:00:00 ps
    PID TTY          TIME CMD
  12520 pts/0    00:00:00 bash
  42800 pts/0    00:00:00 ps
[1]+  Terminated                 sleep 600
[1] 42929
    PID TTY          TIME CMD
  12520 pts/0    00:00:00 bash
  42929 pts/0    00:00:00 sleep
  42939 pts/0    00:00:00 ps
    PID TTY          TIME CMD
  12520 pts/0    00:00:00 bash
  42956 pts/0    00:00:00 ps
[1]+  Killed                     sleep 600

Screenshot:

![Part 2 Task 4](screenshots/p2t4.png)

Explanation:
kill sends SIGTERM, which is a polite request that lets the program clean up and close, so I use it first. kill -9 sends SIGKILL, which forces the process to stop immediately without any cleanup, so I use it only when a program is stuck.




## Part 3

### Task 3

Commands:
```
echo "Author: Muhammad Faraz Ahmed" >> README.md
git status
git add README.md
git status
git commit -m "Part 3: add author to README"
```

Output after editing (working directory):
```
On branch main
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
	modified:   README.md

no changes added to commit (use "git add" and/or "git commit -a")
```

Output after git add (staging area):
```
On branch main
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
	modified:   README.md

```

Output after git commit (repository):
```
[main 747bf84] Part 3: add author to README
 1 file changed, 1 insertion(+)
```

Explanation:
After I edited README.md, the change was in the working directory. After git add, it moved to the staging area. After git commit, it was saved in the repository.



### Task 4

Commands:
```
git remote add origin git@github.com:MuhammadFarazAhmedd/devops-assignment-1.git
git push -u origin main
git remote -v
git log --oneline
```

Output:
```
origin  git@github.com:MuhammadFarazAhmedd/devops-assignment-1.git (fetch)
origin  git@github.com:MuhammadFarazAhmedd/devops-assignment-1.git (push)
801bea4 (HEAD -> main, origin/main) Part 3: Task 3 answer
747bf84 Part 3: add author to README
45ff934 Part 2: Task 3 and 4 answers
c791769 Part 2: Task 3 answer
759200b Part 2: Task 1 and 2 answers
91758f2 Part 1: DevOps concepts answers
5dbd696 Part 3: add README, answers and .gitignore
```

Explanation:
git remote add origin connects my local folder to the GitHub repository, and origin is just a nickname for that address. git push -u origin main uploads my commits to GitHub and remembers the link, so next time I only need git push.
