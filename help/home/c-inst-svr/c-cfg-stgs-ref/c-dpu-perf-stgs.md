---
description: Instructions to tune DPU performance.
title: DPU Performance Settings
uuid: e2b87548-7eb3-4f82-a94e-8ec7c3dc27c2
exl-id: 738c3a76-f8b4-4d84-86ee-ce9b99f50dae
---
# DPU Performance Settings{#dpu-performance-settings}

Instructions to tune DPU performance.

Complete the following parameters in the * [!DNL Insight Server] installation directory*\Components\DPU.cfg file.

|  Parameter  | Description  |
|---|---|
|  Execution Batch Count  | This is a tuning parameter. The default value is 65536. You can specify arbitrarily small execution batch counts. Please contact Adobe before making any changes to this value.  |
|  Execution Batches  | This is a tuning parameter. The default value is 128. Please contact Adobe before making any changes to this value.  |
|  Execution Time  | This is a tuning parameter. The default value is 0.100. Please contact Adobe before making any changes to this value.  |
|  Field Dump on Error  |This parameter can be set to true or false. If set to true, [!DNL Insight Server] creates a file named [!DNL Field Dump number.txt] in its Trace directory whenever execution engine errors occur. The [!DNL Field Dump] < [!DNL number]> [!DNL .txt] is useful for troubleshooting.  |
|  Profile Path  | Location in which to store files for all profiles. The default location is Profiles\.  |
|  Query Memory Limit  |Amount of memory (in bytes) that [!DNL Insight Server] reserves to store query results. The default value is 100000000 (100MB.) If more space for query results is required (for example, to allow more simultaneous users), the setting can be increased, but you must continue to check the [!DNL Insight Server’s] memory load.  |
|  State Path  | Location of system state files. The default location is State\.  |
|  Threads  |A performance tuning parameter for [!DNL Insight Server] machines with multiple processors. In general, for any n-core system, this value should be set to n. The default value is 1. |
|  User Path  | Location of authorized users’ files. The default location is Users\.  |
