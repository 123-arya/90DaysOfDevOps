# Task 1: Understanding Branches

1. What is a branch in Git?

A Git branch is a separate workspace used to make changes without affecting the main project.
Once the work is complete, the changes can be merged back into the main or master branch.

Branches make it easy to:
- Manage different tasks or features independently.
- Test changes without affecting live code.
- Collaborate with others efficiently.

2. Why do we use branches instead of committing everything to main?

Using branches instead of committing directly to the main (or master) branch is a fundamental practice in software development that provides isolation, safety, and organization. While main usually holds the stable, production-ready code, branches allow developers to experiment, build features, or fix bugs without risking the stability of the entire project. 

3. What is HEAD in Git?

HEAD is a symbolic reference that points to the commit you are currently working on.

4. What happens to your files when you switch branches?

Files tracked in both branches update to the new branch's version, files unique to the old branch are removed, and files unique to the new branch appear. 
