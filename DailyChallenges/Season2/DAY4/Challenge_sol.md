<img width="759" height="529" alt="Screenshot 2025-09-13 160215" src="https://github.com/user-attachments/assets/aea5be67-ec34-46e2-938f-8959796b8107" /># ✅ `challenge_solution.md` 

# Day 4: Advanced Git Mastery

**Name:** Manjunath K  
**Date:** 13 September 2025  

---

## ✅ Task 1 – Amend a Commit

### Commands used:
```bash
Adding multiple commits
```

### Screenshot:
<img width="759" height="529" alt="Screenshot 2025-09-13 160215" src="https://github.com/user-attachments/assets/663d50f8-16a1-4dc3-96bb-2c5417d9185f" />

### Diagram:
```mermaid
flowchart TD
    A[Initial commit] --> B[Staged changes]
    B --> C[Amended commit]

---

## ✅ Task 2 – Interactive Rebase

### Screenshot:
<img width="1324" height="851" alt="Screenshot 2025-09-13 154559" src="https://github.com/user-attachments/assets/f2f90a20-926b-436a-b2a1-0c0f83823056" />
<img width="653" height="187" alt="Screenshot 2025-09-13 160247" src="https://github.com/user-attachments/assets/a7307b05-94a5-4b5e-8384-1672e75f84e7" />

### Diagram:
```mermaid
flowchart LR
    A[Change 1] --> B[Change 2]
    B --> C[Change 3]
    D[Rebase] --> E[Squash Commits 2 & 3]
    E --> F[Final Commit]
```

### Result:
The last two commits were combined into one, with the new commit message updated accordingly. The commit history is cleaner and easier to understand.
<img width="844" height="334" alt="Screenshot 2025-09-13 160309" src="https://github.com/user-attachments/assets/eec5e4a0-0670-4707-b55c-4bb902bfe650" />

---

## ✅ Task 3 – Tag a Release

### Commands used:
```bash
git tag -a v2.0.0 -m "Release version 2.0.0"
git push origin --tags
git tag v1.0.0 # Lightweight
```

### Screenshot:

<img width="1104" height="382" alt="Screenshot 2025-09-13 160350" src="https://github.com/user-attachments/assets/6801ecee-3ae4-4f04-90c0-f8a5b3560e50" />


### Diagram:
```mermaid
flowchart LR
    A[Commit] --> B[v2.0.0 Tag]
```

### Result:
A new annotated tag `v2.0.0` was created with a description and pushed to GitHub.

---

## ✅ Task 4 – Sync with Upstream

### Commands used:
```bash
git remote add upstream https://github.com/Sagar2366/LearnWithSagar.git
git fetch upstream
git merge upstream/main
```

### Screenshot:
<img width="1165" height="314" alt="Screenshot 2025-09-13 160438" src="https://github.com/user-attachments/assets/290e5af3-a855-4562-be85-e4935ecf1cbe" />


### Diagram:
```mermaid
flowchart LR
    O[Original Repo] --> U[Upstream]
    U --> Y[Your Fork]
    Y --> L[Local Machine]
    L --fetch upstream--> O
```

### Result:
The upstream repository's changes were successfully merged into the local repository without losing existing changes.

---

## ✅ Task 5 – Stash and Cherry-Pick

### Commands used:
```bash
echo "Stash content" >> file.txt
git add file.txt

git stash

git checkout -b hotfix

random lines for cherry pick

git cherry-pick <commit-hash>   # Replace <commit-hash> with actual commit ID

git stash pop
```

### Screenshot:

<img width="909" height="142" alt="Screenshot 2025-09-13 161040" src="https://github.com/user-attachments/assets/4710cc53-785e-4bd0-8d58-d1f1d82a0ec3" />
<img width="642" height="178" alt="Screenshot 2025-09-13 161403" src="https://github.com/user-attachments/assets/180f758e-3728-44d9-a90d-696e869c8280" />


### Diagram:
```mermaid
flowchart LR
    F[FeatureBranch] --stash--> H[HotfixBranch]
    H --cherry-pick--> A[Applied Commit]
```

### Result:
Uncommitted changes were safely stored using `git stash`, applied to another branch using `git cherry-pick`, and then restored using `git stash pop`.

---

## ✅ Task 6 – Reset

### Commands used:
```bash
git reset --soft HEAD~1
git reset --mixed HEAD~1
git reset --hard HEAD~1
```

### Diagram:
flowchart TD
    subgraph Soft["git reset --soft"]
        H1[HEAD → Moves to target commit]
        I1[Index (Staging Area) → Keeps changes]
        W1[Working Directory → Keeps changes]
    end

    subgraph Mixed["git reset --mixed (default)"]
        H2[HEAD → Moves to target commit]
        I2[Index → Reset to commit (unstages changes)]
        W2[Working Directory → Keeps changes]
    end

    subgraph Hard["git reset --hard"]
        H3[HEAD → Moves to target commit]
        I3[Index → Reset to commit]
        W3[Working Directory → Discards changes]
    end


### Result:
The feature branch was rebased onto the main branch, conflicts were resolved, and the history is now linear.
git soft:
<img width="1087" height="779" alt="Screenshot 2025-09-13 163033" src="https://github.com/user-attachments/assets/16809662-7882-475c-9df2-2c1f8e6a8234" />
<img width="1316" height="199" alt="Screenshot 2025-09-13 163102" src="https://github.com/user-attachments/assets/d67780c5-cd19-448c-9bea-28cffce1a769" />
<img width="873" height="178" alt="Screenshot 2025-09-13 163123" src="https://github.com/user-attachments/assets/0ed3699d-d8c9-4677-b61c-966ad4d3eed5" />
git mixed:
<img width="1087" height="779" alt="Screenshot 2025-09-13 163033" src="https://github.com/user-attachments/assets/26d4957a-4996-47da-817e-7ab61f3401b8" />
<img width="1315" height="190" alt="Screenshot 2025-09-13 163146" src="https://github.com/user-attachments/assets/d7a274b4-eaf7-489d-9e1e-0591dbec3251" />
<img width="1052" height="204" alt="Screenshot 2025-09-13 163206" src="https://github.com/user-attachments/assets/c39a3f3b-a069-4764-996b-fafe6d7c720d" />
git hard:
<img width="1087" height="779" alt="Screenshot 2025-09-13 163033" src="https://github.com/user-attachments/assets/48614277-a663-48a3-8ecc-d5955f27cd50" />
<img width="1322" height="204" alt="Screenshot 2025-09-13 163224" src="https://github.com/user-attachments/assets/13300117-acd6-405b-9945-836103de365d" />
<img width="683" height="120" alt="Screenshot 2025-09-13 163241" src="https://github.com/user-attachments/assets/6dbb089e-1a9e-43dd-8b3d-50cd30da66c2" />


---

## ✅ Task 7 – Undo with Revert

### Commands used:
```bash
git revert <commit-hash>   # Replace <commit-hash> with actual commit ID

git log --oneline
```

### Screenshot:

<img width="800" height="275" alt="image" src="https://github.com/user-attachments/assets/2c05f567-a997-4bcc-8f33-a185c99bf7ae" />
<img width="887" height="132" alt="image" src="https://github.com/user-attachments/assets/79e605e9-ee97-4176-8997-6d68191c08f3" />


### Diagram:
```mermaid
flowchart LR
    A[Original Commit] --> B[Revert Commit]
```

### Result:
A new commit was created that undoes the changes introduced by the specified commit, keeping history safe and intact.

---

## ✅ Task 8 – Branching Strategies

### Gitflow
- Description: A structured workflow for teams with scheduled releases, using feature, release, and hotfix branches.

```mermaid
graph TD
    A[main] --> B[develop]
    B --> C[feature]
    B --> D[release]
    A --> E[hotfix]
```

### GitHub Flow
- Description: A lightweight workflow where all work is done in feature branches and merged into main after review.

```mermaid
graph TD
    A[main] --> B[feature]
    B --> A
```

### Trunk-Based Development
- Description: Developers commit directly to the main branch, using feature toggles to manage incomplete features.

```mermaid
graph TD
    A[main] --> B[dev changes]
    B --> A
```

### Chosen Strategies

1. **For a small team with continuous deployment → GitHub Flow**
   **Reason:** It's simple, quick, and reduces overhead while allowing fast deployments.

2. **For a large team with monthly releases → Gitflow**
   **Reason:** It offers a controlled environment with multiple branches that suit scheduled releases and better quality assurance.

---


---

## ✅ Submission Checklist

- ✅ Completed all tasks with commands and explanations
- ✅ Added diagrams for each workflow
- ✅ Inserted screenshots under each command block
- ✅ Pushed code to GitHub
- ✅ Created PR titled **Day 4: Advanced Git Mastery**
- ✅ Shared on LinkedIn with hashtags: `#getfitwithsagar #DevOpsForAll`

---
