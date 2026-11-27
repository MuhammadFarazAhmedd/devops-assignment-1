
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



## Part 4

### Task 1

Commands:
```
git switch -c add-notes
echo "# Notes" > notes.md
git add notes.md
git commit -m "Add notes.md"
echo "Branches keep work separate until it is ready." >> notes.md
git commit -am "Edit notes.md"
git switch main
git merge add-notes
git branch -d add-notes
git log --oneline --graph
```

Output:
```
Switched to a new branch 'add-notes'
[add-notes 3963733] Add notes.md
 1 file changed, 1 insertion(+)
 create mode 100644 notes.md
[add-notes 647b737] Edit notes.md
 1 file changed, 1 insertion(+)
Switched to branch 'main'
Your branch is up to date with 'origin/main'.
Updating 432a0c6..647b737
Fast-forward
 notes.md | 2 ++
 1 file changed, 2 insertions(+)
 create mode 100644 notes.md
Deleted branch add-notes (was 647b737).
* 647b737 (HEAD -> main) Edit notes.md
* 3963733 Add notes.md
* 432a0c6 (origin/main) Part 3: Git and GitHub answers
* 801bea4 Part 3: Task 3 answer
* 747bf84 Part 3: add author to README
* 45ff934 Part 2: Task 3 and 4 answers
* c791769 Part 2: Task 3 answer
* 759200b Part 2: Task 1 and 2 answers
* 91758f2 Part 1: DevOps concepts answers
* 5dbd696 Part 3: add README, answers and .gitignore
```

Explanation:
Yes, it was a fast-forward. Nothing new was committed on main after I created add-notes, so Git just moved main forward to the branch's last commit without making a merge commit.




### Task 2

Commands:
```
echo "Hello from main" > greeting.txt
git add greeting.txt
git commit -m "Add greeting.txt"
git switch -c branch-a
echo "Hello from A" > greeting.txt
git commit -am "Branch A greeting"
git switch main
git switch -c branch-b
echo "Hello from B" > greeting.txt
git commit -am "Branch B greeting"
git switch main
git merge branch-a
git merge branch-b
cat greeting.txt
```

Output:
```
[main 2b3315a] Add greeting.txt
 1 file changed, 1 insertion(+)
 create mode 100644 greeting.txt
Switched to a new branch 'branch-a'
[branch-a a95227f] Branch A greeting
 1 file changed, 1 insertion(+), 1 deletion(-)
<<<<<<< HEAD shows my current branch version.
======= separates both versions.

branch-b shows the other branch version.

Git cannot merge them because both branches changed the same line. So we have to choose which version is correct.Switched to branch 'main'
Switched to a new branch 'branch-b'
[branch-b 1226e30] Branch B greeting
 1 file changed, 1 insertion(+), 1 deletion(-)
Switched to branch 'main'
Updating 2b3315a..a95227f
Fast-forward
 greeting.txt | 2 +-
 1 file changed, 1 insertion(+), 1 deletion(-)
Auto-merging greeting.txt
CONFLICT (content): Merge conflict in greeting.txt
Automatic merge failed; fix conflicts and then commit the result.
<<<<<<< HEAD
Hello from A
=======
Hello from B
>>>>>>> branch-b
```

How I fixed it:
```
printf 'Hello from A\nHello from B\n' > greeting.txt
git add greeting.txt
git commit -m "Resolve conflict: keep both greetings"
git branch -d branch-a branch-b
git push
```

Explanation:
<<<<<<< HEAD is the start of the version on my current branch (main).
======= is the line that separates the two versions.
>>>>>>> branch-b is the end of the version coming from branch-b.
Git could not decide because both branches changed the same line in different ways. Only a person knows which version is correct, so Git stops and asks.


## Part 4, Task 3

My pull request to my partner:
https://github.com/alibaqir110-web/devops-assignment-1/pull/1

My partner's pull request to me:
https://github.com/MuhammadFarazAhmedd/devops-assignment-1/pull/1

Partner's name: Ali Baqir

## Part 4, Task 4

Commands:echo "Part 6: scripts are in scripts/ and run with cron." >> notes.md
git commit -am "Add Part 6 notes. Closes #2"
git push

Output:
[main 13e660b] Part 4: Task 3 pull request links
 1 file changed, 81 insertions(+)
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 8 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 1.12 KiB | 1.12 MiB/s, done.
Total 3 (delta 2), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (2/2), completed with 2 local objects.
To github.com:MuhammadFarazAhmedd/devops-assignment-1.git
   8317360..13e660b  main -> main


## Part 5

### Task 1:

**Commands:**
sudo apt update
sudo apt install -y apache2
systemctl status apache2
sudo systemctl stop apache2
systemctl status apache2
curl localhost
sudo systemctl start apache2
sudo systemctl enable apache2
systemctl is-enabled apache2
sudo journalctl -u apache2 --since today

**Output:**
- After install, status shows:
  Active: active (running) since Sat 2026-11-28 02:27:29 PKT
- After stop, status shows:
  Active: inactive (dead)
- curl localhost shows:
  curl: (7) Failed to connect to localhost port 80 after 0 ms: Couldn't connect to server
- systemctl is-enabled apache2 shows:
  enabled
- journalctl shows lines like:
  Nov 28 02:27:29 faraz-HP-Pavilion-m7-Notebook-PC systemd[1]: Starting apache2.service - The Apache HTTP Server...
  Nov 28 02:27:29 faraz-HP-Pavilion-m7-Notebook-PC systemd[1]: Started apache2.service - The Apache HTTP Server.

(Screenshots: screenshots/p5t1-stopped.png and screenshots/p5t1.png)

**Explanation:**
systemctl start runs the service right now, but it will not start again after a reboot. systemctl enable makes it start automatically at every boot, but it does not start it right now.
After stop, the status is inactive (dead) and curl cannot connect because nothing is listening on port 80. journalctl -u apache2 --since today shows only today's logs of the apache2 service.

### Task 2: 

**Commands:**
export APP_ENV=staging
echo $APP_ENV
printenv APP_ENV

**Output (first terminal):**
staging
staging

**Output (new terminal):**
(empty line)
(empty line)

**Explanation:**
export only sets the variable for the current terminal. A new terminal starts fresh, so the variable is gone. To make it permanent I would add export APP_ENV=staging to the ~/.bashrc file.


## Task 3:

Commands:
```
sudo systemctl enable --now ssh
hostname -I
whoami
ssh-copy-id ali@192.168.0.39
ssh ali@192.168.0.39
whoami
exit
echo "Hello from Faraz" > hello-from-faraz.txt
scp hello-from-faraz.txt ali@192.168.0.39:~/
ssh ali@192.168.0.39 "cat ~/.ssh/authorized_keys"
```

Output:
```
My machine:
192.168.0.35
faraz

Partner's machine (Ali):
192.168.0.39
ali

/usr/bin/ssh-copy-id: INFO: Source of key(s) to be installed: ssh-add -L
The authenticity of host '192.168.0.39 (192.168.0.39)' can't be established.
ED25519 key fingerprint is: SHA256:GLcqP+eANRFD9spljsJQekOCfu25tQW1jgKqYrJDcZk
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
/usr/bin/ssh-copy-id: INFO: 1 key(s) remain to be installed -- if you are prompted now it is to install the new keys
ali@192.168.0.39's password:

Number of key(s) added: 1

Login with no password:
ali@ali-ThinkPad-T450:~$ whoami
ali
ali@ali-ThinkPad-T450:~$ exit
logout
Connection to 192.168.0.39 closed.

File copy:
hello-from-faraz.txt     100%   17     3.2KB/s   00:00

Partner's authorized_keys:
ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAIMCQaaH84osK8AZZSZjWJUspmGZwkifMIHxqRGvAg6ff fu96555@gmail.com
```

Explanation:
He writes his own explanation — same points as yours: the private key (`~/.ssh/id_ed25519`, no `.pub`) must stay on his machine only; the public key is safe to share and is what gets installed in your authorized_keys; if someone copies his private key they can log in as him to every machine and GitHub account that trusts it.

Tell him to word it himself — the assignment says partner tasks are shared work but each person submits their own answers.


## Part 6

### Task 1: sys_report.sh

Script:
#!/bin/bash
HOST=$(hostname)
TODAY=$(date +%Y-%m-%d)

echo "Hostname: $HOST"
echo "Date: $TODAY"
echo "Current user: $(whoami)"
echo "Disk usage of /:"
df -h /

Commands:
cd ~/devops-assignment-1/scripts
nano sys_report.sh
chmod +x sys_report.sh
./sys_report.sh

Output:
Hostname: faraz-HP-Pavilion-m7-Notebook-PC
Date: 2026-11-28
Current user: faraz
Disk usage of /:
Filesystem      Size  Used Avail Use% Mounted on
/dev/sdb4        53G   12G   39G  24% /

Explanation:
The script stores the hostname and today's date in variables using $( ), which runs a command and saves its answer. It then prints the hostname, date, current user and the disk usage of / using df -h (human-readable sizes). chmod +x gives the file execute permission so it can be run with ./sys_report.sh.
