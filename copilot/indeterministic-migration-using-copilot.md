# Indeterministic Migration using Copilot

I am working on helping the non-tech colleagues to migrate their vibe coded websites to compliant solution using Copilot. There can be any type of website and of any size. If there is some important data in the website, it should be separated out and served from a secure place where there are more controls both for admins and website owners.

## Architected the skills and subagents in following ways:

* Skills are divided into different parts, for example:
	* **init** - to ask users for website metadata and path for original website
	* **prepare** - to divide the whole website into independent subtasks and running parallel subagents to prepare individual tasks.
	* **implement** - to implement each independent subtasks in parallel, if there is a dependent subtask execute that first.
	* **upload & test** - upload the important data to the secure place, and test the website locally by serving the data from secure place directly.
	* **deploy** - deploy the website

## Learnings

* Earlier all the skills were running in the main session without subagents which was bloating the main session and ending up with incorrect output.
* So updated the skills to start using subagents using LOOP method, which says PLAN -> ACT -> VERIFY -> Check against the output against the plan or stop (if there are pending items start the loop again).

> Issues with this new architecture: significant increase in completing the whole process after introducing plan and verify.

