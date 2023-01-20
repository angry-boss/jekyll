---
layout: post
title: "Using a token on the command line."
date: 2023-01-17 22:45:00
categories: github authentication
---
Once you have a token, you can enter it instead of your password when performing Git operations over HTTPS.

For example, on the command line you would enter the following:

$ git clone https://github.com/USERNAME/REPO.git
Username: YOUR_USERNAME
Password: YOUR_TOKEN

The explained tutorial is at https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token
