# kartik
Set 1:
Jira / JQL Questions:
Create a Jira Cloud instance and navigate to a new project board:

To create a new Jira Cloud instance, go to Jira Cloud and sign up for an account.

After logging in, you can create a new project by selecting Create Project and following the steps to create a project based on your preferred template (e.g., Scrum, Kanban).

To navigate to your project board, select the project from the Jira dashboard.

Write a JQL to find all issues assigned to you with status = "In Progress":

jql
Copy
Edit
assignee = currentUser() AND status = "In Progress"
Create a filter to track high-priority issues and save it:

To create a filter, go to Filters > Create Filter.

Use the following JQL to filter high-priority issues:

jql
Copy
Edit
priority = High
Save the filter and give it a name.

Show all issues created in the last 10 days and unresolved:

jql
Copy
Edit
created >= -10d AND resolution = Unresolved
Write JQL to find all bugs resolved in the last 5 days:

jql
Copy
Edit
issuetype = Bug AND resolution = Resolved AND resolved >= -5d
Git / GitHub Questions:
Initialize Git in a new local folder, create a GitHub repo, and push code:

Initialize Git in a folder:

bash
Copy
Edit
git init
Create a GitHub repo on GitHub and copy the repository URL.

Add the remote repository:

bash
Copy
Edit
git remote add origin <repo-url>
Push the code:

bash
Copy
Edit
git push -u origin master
Git commands to stage, commit with message, and push to remote:

bash
Copy
Edit
git add .
git commit -m "Commit message"
git push origin master
Recover a deleted file locally using Git:

If the file was staged but not committed:

bash
Copy
Edit
git restore --staged <file-path>
If the file was modified but not staged:

bash
Copy
Edit
git restore <file-path>
If the file was deleted after the last commit:

bash
Copy
Edit
git checkout HEAD -- <file-path>
Set 2:
Jira / JQL Questions:
Create and configure a Scrum project in Jira:

Create a new Scrum project in Jira by selecting Create Project and choosing the Scrum template.

Once created, configure the board, sprints, and issue types as per your workflow needs.

Write JQL to find issues where status changed from "To Do" to "In Progress" in the last 7 days:

jql
Copy
Edit
status CHANGED FROM "To Do" TO "In Progress" DURING (-7d, now())
Find overdue issues assigned to yourself using JQL:

jql
Copy
Edit
assignee = currentUser() AND due < now() AND resolution = Unresolved
Show unresolved tasks from the current sprint using JQL:

jql
Copy
Edit
sprint in openSprints() AND resolution = Unresolved
Git / GitHub Questions:
Create a GitHub repo, add a README.md, and share with a teammate:

Create a GitHub repo on GitHub and copy the repository URL.

Add a README.md file to your local project and push the changes:

bash
Copy
Edit
echo "# Project Title" > README.md
git add README.md
git commit -m "Add README.md"
git push origin master
Share the repository URL with your teammate.

Create a new Git branch for a feature and merge it after completion:

bash
Copy
Edit
git checkout -b feature-branch
# make changes and commit
git commit -m "Add feature"
git push origin feature-branch
After the feature is complete and the pull request is approved, merge it:

bash
Copy
Edit
git checkout master
git merge feature-branch
git push origin master
Add branch protection on main and require PR reviews:

Go to Settings > Branches > Branch protection rules.

Select the main branch and enable Require pull request reviews before merging.

Set 3:
Jira / JQL Questions:
Add a custom status "Code Review" to a Jira workflow and update transitions:

Go to Jira Settings > Issues > Workflows.

Edit the workflow, add the "Code Review" status, and set transitions from the relevant statuses to "Code Review" and vice versa.

JQL: Find tasks that moved to “Code Review” in the past 5 days:

jql
Copy
Edit
status CHANGED TO "Code Review" DURING (-5d, now())
JQL: List issues where status changed from “In Progress” to “Blocked”:

jql
Copy
Edit
status CHANGED FROM "In Progress" TO "Blocked"
JQL: Find stories that never transitioned to "Testing":

jql
Copy
Edit
issuetype = Story AND status NOT IN ("Testing")
JQL: Find unresolved issues due in the next 3 days:

jql
Copy
Edit
resolution = Unresolved AND due <= 3d
Git / GitHub Questions:
Create and push a new branch search-feature, open a pull request:

bash
Copy
Edit
git checkout -b search-feature
# Make changes and commit
git commit -m "Add search feature"
git push origin search-feature
Open a pull request on GitHub by navigating to the repo and selecting Compare & pull request.

Merge changes into the main branch after PR approval:

Once the PR is approved, click Merge pull request on GitHub to merge the changes into the main branch.

Set 4:
Jira / JQL Questions:
Build a Jira dashboard showing open issues, sprints, and completed tasks:

Go to Dashboards > Create Dashboard.

Add gadgets like Filter Results, Sprint Health, Pie Chart, etc., and configure them with the relevant filters for open issues, sprints, and completed tasks.

JQL: Find unresolved issues labeled “security”:

jql
Copy
Edit
labels = security AND resolution = Unresolved
JQL: List issues created in the last 7 days under the API component:

jql
Copy
Edit
component = API AND created >= -7d
JQL: Show issues reported by devops@example.com:

jql
Copy
Edit
reporter = devops@example.com
JQL: Filter issues in the current sprint and assigned to your team:

jql
Copy
Edit
sprint in openSprints() AND assignee in (teamMember1, teamMember2, teamMember3)
Git / GitHub Questions:
Resolve a Git merge conflict: view, edit, and complete the merge:

When Git detects a conflict during a merge, open the conflicting files, resolve the conflicts, and save the changes.

Stage the resolved files:

bash
Copy
Edit
git add <resolved-file>
Complete the merge:

bash
Copy
Edit
git commit
Pull remote updates without losing local changes:

To avoid losing local changes, you can use:

bash
Copy
Edit
git stash
git pull origin master
git stash pop
