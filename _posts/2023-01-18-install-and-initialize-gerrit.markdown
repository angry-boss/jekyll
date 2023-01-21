---
layout: post
title: "Install and initialize Gerrit."
date: 2023-01-18 10:53:00
categories: gerrit
---
From the command line, enter:

export GERRIT_SITE=~/gerrit_testsite
java -jar /private/var/gerrit/gerrit.war init --batch --dev -d $GERRIT_SITE
This command takes two parameters:

--batch assigns default values to several Gerrit configuration options. To learn more about these options, see Configuration.

--dev configures the Gerrit server to use the authentication option, DEVELOPMENT_BECOME_ANY_ACCOUNT, which enables you to switch between different users to explore how Gerrit works. To learn more about setting up Gerrit for development, see Gerrit Code Review: Developer Setup.

While this command executes, status messages are displayed in the terminal window. For example:

Generating SSH host key ... rsa(simple)... done
Initialized /home/gerrit/gerrit_testsite
Executing /home/gerrit/gerrit_testsite/bin/gerrit.sh start
Starting Gerrit Code Review: OK
The last message confirms that the Gerrit service is running:

Starting Gerrit Code Review: OK.
