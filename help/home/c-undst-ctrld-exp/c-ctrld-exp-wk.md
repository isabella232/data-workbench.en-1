---
description: In an experiment, you can define any number of test groups in addition to the control group.
solution: Analytics,Analytics
title: How Do Controlled Experiments Work?
topic: Data workbench
uuid: 9549e2ab-dca9-4fb1-9729-65072f951900
exl-id: 1d3af6a2-078e-4eb8-848e-685f531a60c5
---
# How Do Controlled Experiments Work?{#how-do-controlled-experiments-work}

In an experiment, you can define any number of test groups in addition to the control group.

When an experiment is running, all visitors to your website become part of the experiment, either as part of a test group or of the control group, as soon as they access any page involved in the experiment. Visitors are allocated to your experiment groups randomly, in proportions defined during the experiment configuration.

Controlled experiments are implemented using the [!DNL Sensor] software that is installed on each of the content servers in your web cluster. As the content servers receive requests, [!DNL Sensor] randomly selects visitors for your test groups and redirects their page requests to the experimental content. When [!DNL Sensor] selects a visitor to view the test content, the address bar continues to list the originally requested URI but the visitor is routed to the test URI. Because this process takes place internally in the server application, users are not aware of when they are being tested, which is an important consideration for unbiased experimentation.

[!DNL Sensor] passes the test URIs, not the original URI displayed to the user, to the log files for use in analysis.

The results of the experiments can be analyzed easily using [!DNL Insight] to determine whether the experimental hypothesis that you were testing is correct.

>[!NOTE]
>
>Adobe strongly recommends that controlled experiments be coordinated and performed with input from those individuals in your organization who are responsible for configuring and maintaining your analysis datasets.
