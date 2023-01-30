---
layout: post
title: "To rename the default branch"
date: 2023-01-28 13:54:00
categories: git
---
You can update it by running the following commands.

git branch -m main master
git fetch origin
git branch -u origin/master master
git remote set-head origin -a