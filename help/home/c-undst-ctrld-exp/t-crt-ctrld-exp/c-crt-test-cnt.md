---
description: Before you configure the experiment, you should create the alternate content that you want to use in the experiment.
solution: Analytics,Analytics
title: Creating the Test Content
uuid: d7996522-38a6-4bb8-9736-d71157c17b45
exl-id: fd46c6af-37e8-452a-880d-147b7d0cfe21
---
# Creating the Test Content{#creating-the-test-content}

Before you configure the experiment, you should create the alternate content that you want to use in the experiment.

 The control group is sent to the original URI, while the test group is sent to the new, alternate URI.

To avoid confusion, do not reuse test group file names. For example, if you run an experiment using a test group file named [!DNL test2.asp], do not use [!DNL test2.asp] as the name for the test file in your next experiment.

For the hypothesis that moving the “Request a Demo” graphical link on your home page impacts Visitor Conversion, we create the alternate home page containing the “Request a Demo” graphical link in the new position. The following section describes how you then specify that the control group URI [!DNL index.asp] be replaced with the test group URI [!DNL index2.asp] for a certain percentage of visitors.
