
---

# 📘 `challenge_solution.md` – Complete Answer (English, Windows-specific)

## DevOps SRE Daily Challenge – Day 3

### Git Collaboration and Version Control

**Name:** Manjunath K
**Date:** 11 September 2025

---

## ✅ Introduction

Today’s challenge focused on learning Git collaboration and version control using both **GitHub** and **GitLab**. These tools are critical in DevOps and SRE workflows as they allow multiple team members to collaborate effectively, track changes, and resolve conflicts without affecting the main codebase.

Through this challenge, I practiced:

* Setting up Git on Killerkoda.
* Cloning and configuring repositories.
* Creating branches and making changes.
* Handling merge conflicts.
* Using pull requests and merge requests for code reviews.
* Applying similar workflows on both GitHub and GitLab.

This exercise gave me hands-on experience with distributed version control systems and collaboration strategies essential for modern software development.

---

## ✅ Environment Setup (Windows)

### Installing Git on Windows

From killerkoda

### Configuring Git

```bash
git config --global user.name "ManjunathReddy9398"
git config --global user.email "manjunathreddy9398@gmail.com"
```

Example output:
<img width="1042" height="67" alt="image" src="https://github.com/user-attachments/assets/58952bc7-bddd-4f26-a0fc-7e32d0f8a210" />

---
## ✅ GitHub Setup

1. Created a GitHub account.

2. Created a second account to simulate code reviews.

3. Configured SSH access for both accounts.

4. Forked the challenge repository:

   `https://github.com/Sagar2366/LearnWithSagar`

5. Cloned the forked repository:

   ```bash
   git clone https://github.com/ManjunathReddy9398/LearnWithSagar.git
   ```

   Example output:

  <img width="697" height="40" alt="image" src="https://github.com/user-attachments/assets/2dcec7d6-161a-4b95-974b-4f2ad53e08f1" />


6. Navigated to the challenge directory:

   ```
   cd LearnWithSagar/DailyChallenges/Season2/Day3/
   ```
   <img width="1007" height="446" alt="image" src="https://github.com/user-attachments/assets/f196e06f-828c-4983-9594-4eea1b54f002" />
   Git commit:
   <img width="917" height="91" alt="image" src="https://github.com/user-attachments/assets/506adeaa-d045-4882-97aa-39c1b775ec22" />
   <img width="1077" height="111" alt="image" src="https://github.com/user-attachments/assets/63f57590-4d30-4a23-8cf9-ab3d827f0067" />

   Git PushL:
   <img width="1327" height="313" alt="image" src="https://github.com/user-attachments/assets/68f48c3e-9e5c-4fde-948f-f2f424901441" />

   Git merge:
   <img width="881" height="200" alt="image" src="https://github.com/user-attachments/assets/03780b9c-15a6-4c36-90df-aa1f96f0df85" />

## ✅ Commands Used

```bash
git --version
git config --global user.name "..."
git config --global user.email "..."
git clone <repository-url>
git checkout -b <branch-name>
git diff
git add .
git commit -m "message"
git commit --amend -m "new message"
git push origin <branch-name>
git pull origin main
git merge main
git branch -d <branch-name>
git push origin --delete <branch-name>
git log --oneline
git log --stat
git log --pretty=format:"%h - %an, %ar : %s"
```

---

## ✅ Simulating and Avoiding Merge Conflicts – Git Branching Strategy

### 📌 **Goal**

* Understand how merge conflicts happen.
* Learn how to structure branches to avoid them.
* Create a workflow where developers work independently but integrate smoothly.

---

## ✅ 1. What is a Merge Conflict?

A merge conflict occurs when:

* Two branches change the same lines in a file.
* Git cannot automatically decide which change to keep.

You resolved it by:

1. Pulling the latest changes from `main`.
2. Merging `main` into your feature branch.
3. Manually resolving conflicts and committing the result.

---

## ✅ 2. Why Conflicts Happen

* Multiple developers editing the same file on the same branch.
* Working on outdated code without pulling updates.
* Direct commits to the main branch without integration steps.

---

## ✅ Key Concepts Learned

### What I Learned

* Git is a distributed system that works offline.
* Branches allow experimenting without affecting the main codebase.
* Merge conflicts are natural and can be resolved with structured workflows.
* GitHub and GitLab both provide interfaces to manage collaboration.
* Commands like `git commit --amend`, `git diff`, `git log`, `git push`, and `git pull` are essential for tracking progress.
* Pull requests and merge requests formalize the review process.

---

### Collaboration Insights

* Communication and version control tools help coordinate work between teams.
* Structured reviews improve code quality and reduce errors.
* Resolving conflicts requires understanding how Git tracks changes.

---

## ✅ Final Submission

* Saved this file as `challenge_solution.md`.
* Committed and pushed it to my GitHub repository.
* Shared the link on social media with hashtags:
  `#getfitwithsagar #SRELife #DevOpsForAll`.
* Tagged the community for feedback and collaboration.

---

## ✅ Community Links

* **Discord** – [Join here](https://discord.gg/mNDm39qB8t)
* **Google Group** – [Join here](https://groups.google.com/forum/#!forum/daily-devops-sre-challenge-series/join)
* **YouTube Channel** – [Subscribe here](https://www.youtube.com/@Sagar.Utekar)

---

## ✅ Conclusion

This challenge gave me hands-on experience with Git workflows on both GitHub and GitLab. Using Git on KillerKoda, I learned how to create branches, commit changes, resolve conflicts, and collaborate effectively. These skills are essential for working in DevOps and SRE roles, and this challenge helped build confidence in using version control systems in real-world environments.

---

**Happy Learning!**
– Swayam Bhuyan

---

Let me know if you want this as a `.md` file or formatted in another way for direct upload. All images have been included as you originally structured them!
