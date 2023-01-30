---
layout: post
title: "Validating Your Version of Xcode."
date: 2023-01-22 13:11:00
categories: xcode
---
Validating Your Version of Xcode
September 22, 2015

We recently removed apps from the App Store that were built with a counterfeit version of Xcode which had the potential to cause harm to customers. You should always download Xcode directly from the Mac App Store, or from the Apple Developer website, and leave Gatekeeper enabled on all your systems to protect against tampered software.

When you download Xcode from the Mac App Store, OS X automatically checks the code signature for Xcode and validates that it is code signed by Apple. When you download Xcode from the Apple Developer website, the code signature is also automatically checked and validated by default as long as you have not disabled Gatekeeper.

Whether you downloaded Xcode from Apple or received Xcode from another source, such as a USB or Thunderbolt disk, or over a local network, you can easily verify the integrity of your copy of Xcode.

To verify the identity of your copy of Xcode run the following command in Terminal on a system with Gatekeeper enabled:
spctl --assess --verbose /Applications/Xcode.app

where /Applications/ is the directory where Xcode is installed. This tool performs the same checks that Gatekeeper uses to validate the code signatures of applications. The tool can take up to several minutes to complete the assessment for Xcode.

The tool should return the following result for a version of Xcode downloaded from the Mac App Store:
/Applications/Xcode.app: accepted
source=Mac App Store

and for a version downloaded from the Apple Developer web site, the result should read either
/Applications/Xcode.app: accepted
source=Apple

or

/Applications/Xcode.app: accepted
source=Apple System

Any result other than ‘accepted’ or any source other than ‘Mac App Store’, ‘Apple System’ or ‘Apple’ indicates that the application signature is not valid for Xcode. You should download a clean copy of Xcode and recompile your apps before submitting them for review.