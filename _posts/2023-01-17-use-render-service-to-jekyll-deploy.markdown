---
layout: post
title: "Use Render service to Jekyll deploy."
date: 2023-01-17 14:54:00
categories: jekyll update
---
Deploy a Jekyll Static Site

You can deploy a Jekyll static site on Render in under a minute. Your site is served over a lightning-fast global CDN, comes with fully managed TLS certificates, and supports custom domains out of the box.

The sample app for this quick start is deployed at https://jekyll.onrender.com.

Use your existing Jekyll repository, or fork our sample Jekyll repo on GitHub or GitLab.

Create a new Static Site on Render, and give Render permission to access your new repo.

Use the following values during creation:

Build Command	bundle exec jekyll build
Publish Directory	_site
That’s it! Your app will be live on your Render URL as soon as the build finishes.

Additional Notes
See Specifying a Ruby Version if you need to customize the version of Ruby used for your app.

Specifying a Ruby Version

The default Ruby version is listed along with the other supported Native Environments.

You can customize the Ruby version for your app by adding a .ruby-version file or by setting the ruby directive in your Gemfile. If a version is set in both places .ruby-version will take priority.

To avoid any version mismatch confusion it can help to a single version set in .ruby-version and have the Gemfile read from it, for example:

Your .ruby-version could look like this:

3.1.2
Then the Gemfile can reference .ruby-version via the ruby directive:

ruby File.read('.ruby-version').strip