

# 🎯 Step 1 → Version Control with Git

Concept :
👉 Git is Version Control System (VCS).

Git helps track changes in your code, collaborate with teams, and rollback if something breaks.


Real Life Example:

If you write 100 files in project . some bug occurred.

Use Git easily go to previous version → Bug-free version will be restore.


🧑‍💻 Step 1 → Git (Version Control with Git)

🔹 Concept (தமிழ் + English)

தமிழ்: Git என்பது code changes-ஐ save பண்ணும் ஒரு "time machine" மாதிரி. ஒவ்வொரு commit-ம் ஒரு snapshot. நம்ம தவறா code எழுதினாலும் பழைய safe version-க்கு easy-ஆ back போகலாம்.

English: Git is a Version Control System (VCS). It tracks changes, allows team collaboration, branching, merging, and rollback to older versions.



---

🔹 Why Git? (ஏன் Git தேவை?)

Accident-ஆ code delete ஆயிடுச்சு → Git restore பண்ணும்.

Team-ல பல பேர் ஒரே project-ல வேலை பண்ணுறாங்க → Git merge பண்ணும்.

History maintain பண்ணும் → யார், எப்போ, என்ன change பண்ணினாங்க தெரிய வரும்.



---

🔹 Real-Life Example

உதாரணம்:

ஒரு book எழுதுறீங்க. ஒவ்வொரு நாளும் new draft save பண்ணுறீங்க → draft_v1, draft_v2, draft_v3.

ஒருநாள் தவறா something delete பண்ணிட்டீங்க. பழைய draft-க்கு போய்ட்டு safe copy எடுக்கலாம்.

அதுதான் Git software-ல செய்றது.



---

🔹 Git Workflow (Simple Tamil + English)

1. Working Directory → உங்க files (code).


2. Staging Area → Next commit-க்கு ready files.


3. Repository (Repo) → Permanent history (commits).



Flow:
Working Directory → git add → Staging → git commit → Repo


---

🔹 Git Commands (Basic)

1️⃣ Create a Git Repo

git init

👉 புதிய Git repository உருவாக்கும். (New project start)


---

2️⃣ Check Status

git status

👉 எந்த files modified ஆனது, staged ஆனது, untracked files என்னென்ன என்பதை காண்பிக்கும்.


---

3️⃣ Add Files to Staging

git add file1.cpp
git add .

👉 file1.cpp next commit-க்கு ready ஆகும். ( . = எல்லா files add ஆகும்)


---

4️⃣ Commit Changes

git commit -m "Added file1.cpp with Hello World"

👉 ஒரு snapshot save ஆகும் (History point).


---

5️⃣ View History

git log

👉 எல்லா commits history-யும் காண்பிக்கும்.


---

6️⃣ Branching & Merging

git branch feature-x      # புதிய branch create
git checkout feature-x    # அந்த branch-க்கு switch
git merge feature-x       # branch merge back

👉 தனியா work பண்ணி later main project-க்கு merge பண்ணலாம்.


---

🔹 Small Code Example (C++)

hello.cpp

#include <iostream>
using namespace std;

int main() {
    cout << "Hello, Git World!" << endl;
    return 0;
}

Git Usage:

git init
git add hello.cpp
git commit -m "Initial commit with hello.cpp"


---


# 🧑‍💻 Git Setup & First Practice on PC

🔹 Step 1 → Install Git

1. Go to 👉 https://git-scm.com/downloads


2. உங்க OS (Windows/Linux/Mac) choose பண்ணி install பண்ணுங்க.


3. Install ஆனதுக்குப் பிறகு check பண்ண:

git --version

Example output:

git version 2.46.0




---

🔹 Step 2 → Configure Git (First Time Setup)

git config --global user.name "Kishore"
git config --global user.email "kishore@example.com"

👉 இது உங்க commit history-ல author name & email save ஆகும்.

Check பண்ண:

git config --list


---

🔹 Step 3 → Create Your First Repo

1. புதிய folder create பண்ணுங்க:

mkdir git-practice
cd git-practice


2. Initialize Git repo:

git init

Output:

Initialized empty Git repository in .../git-practice/.git/




---

🔹 Step 4 → Add First Code

👉 ஒரு simple program create பண்ணுங்க.
hello.cpp

#include <iostream>
using namespace std;

int main() {
    cout << "Hello, Git Practice!" << endl;
    return 0;
}


---

🔹 Step 5 → Track & Commit

1. File status பார்க்க:

git status

(You will see hello.cpp as untracked)


2. File staging area-க்கு add பண்ண:

git add hello.cpp


3. Commit பண்ண:

git commit -m "Initial commit: added hello.cpp"




---

🔹 Step 6 → View History

git log

Output example:

commit a1b2c3d4...
Author: Kishore <kishore@example.com>
Date:   Sun Sep 7 20:00 2025 +0530

    Initial commit: added hello.cpp


---

🔹 Step 7 → Modify & Commit Again

Edit hello.cpp

#include <iostream>
using namespace std;

int main() {
    cout << "Hello, Git Practice!" << endl;
    cout << "Learning Git step by step." << endl;
    return 0;
}

Then run:

git add hello.cpp
git commit -m "Updated hello.cpp with second line"

Check history:

git log --oneline

Example:

b7f8c9d Updated hello.cpp with second line
a1b2c3d Initial commit: added hello.cpp


---


# 🧑‍💻 Step 2 → Branching & Merging

🔹 Concept (தமிழ் + English)

தமிழ்: Branch = தனி பாதை. Main road (main branch) safe-ஆ இருக்கும்போது, side road (branch) எடுத்து புதிய idea try பண்ணலாம். Later அது நல்லா இருந்தா main road-க்கு சேர்த்துக்கலாம் (merge).

English: A branch is like a parallel line of development. You can experiment, fix bugs, or build features without breaking the main code. Later, merge it back into the main branch.



---

🔹 Why Branching? (ஏன் தேவை?)

1. New feature work பண்ணும்போது main project safe-ஆ இருக்கும்.


2. பல பேர் ஒரே project-ல வேலை பண்ணும்போது conflicts குறையும்.


3. Bug fixes, experiments easy.




---

🔹 Git Branch Commands

1️⃣ Create a New Branch

git branch feature1

👉 Creates a new branch called feature1.

2️⃣ Switch to Branch

git checkout feature1

👉 Moves you into that branch. (Now changes here won’t affect main directly).

3️⃣ Create + Switch (Shortcut)

git checkout -b feature1

4️⃣ List Branches

git branch

👉 Shows all branches. (Current branch will have a * mark).

5️⃣ Merge Branch to Main

git checkout main
git merge feature1

👉 Brings all changes from feature1 into main.


---

🔹 Example Practice

Step 1 → Start in Main Branch

git init
echo "#include <iostream>\nusing namespace std;\nint main(){cout<<\"Main code\"<<endl;return 0;}" > main.cpp
git add main.cpp
git commit -m "Initial main.cpp"


---

Step 2 → Create Feature Branch

git checkout -b feature-hello

Modify main.cpp:

#include <iostream>
using namespace std;

int main() {
    cout << "Main code" << endl;
    cout << "Feature: Hello Git Branch!" << endl;
    return 0;
}

Commit it:

git add main.cpp
git commit -m "Added hello message in feature branch"


---

Step 3 → Merge Back to Main

git checkout main
git merge feature-hello

Now main.cpp in main branch will also contain the new line.


---

🔹 Visual (Simple Tamil Idea)

Imagine tree 🌳

Main stem = main

Side branch = feature1

Later side branch joins back → tree grows stronger.



---

🔹 Conflict Example (Optional for Practice)

If you edit the same line in both branches, Git will ask you to resolve the conflict manually before merging.
That’s how teams avoid overwriting each other’s work blindly.




