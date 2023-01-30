---
layout: post
title: "Restart the Gerrit service."
date: 2023-01-18 11:17:00
categories: gerrit
---
You must restart the Gerrit service for your authentication type and listen URL changes to take effect:

$GERRIT_SITE/bin/gerrit.sh restart
