---
title: What is the best branching strategy?
published: true
description: 
tags: #git
cover_image: 
---

# How it started

Recently we had a discussion within our platform team about creating documentation for other teams about branching strategy for storing Infrastruture as Code files as well as application code. After some interesting and intensive discussion we agreed on Trunk Based branching strategy following Keep it Simple approach(KISS). I explored this topic wide and deep so decided to create this note for future reference and it might be helpfull for others. In this type of decissions it always depends and I think there is no silver bullet but it is good to make a thoughfull decission based on some disccusions.

# What we have and what we were considering?

There is a couple of different branching strategies from quite complex like Git flow to the simplest like Trunk based but there are a few more: Github flow, Gitlab flow, environment branching and so on...
In our case we were discussing mostly two strategies: environment branching and trunk based. Idea behind the first one was to have a secure approach where each environment has its own branch which allows better control over the source code and releases and reduce the chance of potential bugs. IN other hand we had trunk based which is very simple so easy to use.

Below is a table comparing the two. 
| Aspect                    | Environment Branching                            | Trunk Based                                     |
|---------------------------|--------------------------------------------------|-------------------------------------------------|
| **Complexity**            | High complexity with multiple branches to manage.| Simple, with a single branch as the source of truth. |
| **Collaboration**         | Challenging due to potential conflicts in multiple branches.| Easier, as developers work on a single branch and integrate continuously. |
| **Release Management**    | Easier to control releases for specific environments.| Requires feature toggles and robust CI/CD pipelines for controlled releases. |
| **Bug Tracking**          | Easier to isolate bugs to specific branches/environments.| More challenging, as all changes are in the main branch. |
| **CI/CD Compatibility**   | May require complex pipelines for branch-specific builds.| Simplifies pipelines with a single branch focus. |
| **Scalability**           | Can become difficult to manage with large teams or multiple environments.| Scales well with proper CI/CD practices. |
| **Speed of Delivery**     | Slower, as merging and resolving conflicts can take time.| Faster, with continuous delivery enabling frequent releases. |
| **Learning Curve**        | Steeper, especially for teams unfamiliar with managing multiple branches.| Lower, as it relies on a straightforward workflow. |
| **Code Stability**        | Higher for specific environments but harder to integrate fixes across branches.| Lower initially but improves with robust testing and automation. |
| **Use Case Suitability**  | Best for projects with strict environment segregation or high-risk changes.| Ideal for fast-paced development and teams prioritizing simplicity. |



![Environment branching vs Trunk-based devlopment](../img/branching.png)

# So why Trunk Based?

To keep it simple stupid! (KISS) As mentioned at the begginning there is no silver bullet so let's start from the simple one and add complexity over time. Simple solution are easier to understand and implement which is especially important when creating some recommendations. So even though first option was more robust it was also more complex which could lead to misunderstaing in teams that would use it and lead issues with merge conflicts and different code versions across branches. 

# If you want to know more

Below are articles I have explored during reaserch around this topic
- [Git branching strategy - MS Learn](https://learn.microsoft.com/en-us/azure/devops/repos/git/git-branching-guidance?view=azure-devops)
- [Choosing the Right Git Branching Strategy](https://medium.com/@sreekanth.thummala/choosing-the-right-git-branching-strategy-a-comparative-analysis-f5e635443423)
- [Stop Using Branches for Deploying to Different GitOps Environments](https://codefresh.io/blog/stop-using-branches-deploying-different-gitops-environments/)
