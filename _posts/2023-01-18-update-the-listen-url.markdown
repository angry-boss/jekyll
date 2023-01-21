---
layout: post
title: "Update the listen URL."
date: 2023-01-18 11:10:00
categories: gerrit
---
To prevent outside connections from contacting your new Gerrit instance (strongly recommended), change the URL on which Gerrit listens from * to localhost. For example:

git config --file $GERRIT_SITE/etc/gerrit.config httpd.listenUrl 'http://localhost:8080'
