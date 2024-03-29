---
description: Path browsers can be configured to work with any combination of base dimension, group dimension, level dimension, and metric that makes sense for your application and dataset.
title: Configure a path browser
uuid: 1ba3fb6e-b76f-428f-b6ec-077669c3b305
exl-id: be6a68f7-e3e3-4207-a112-3a4fdd5c5f57
---
# Configure a path browser{#configure-a-path-browser}

Path browsers can be configured to work with any combination of base dimension, group dimension, level dimension, and metric that makes sense for your application and dataset.

 After you configure a path browser, it is listed with other path browsers in the [!DNL Add Visualization] menu. 

1. In the [!DNL Profile Manager], click **[!UICONTROL Menu]**, then click **[!UICONTROL Add Visualization]** and **[!UICONTROL Path Browser]**.

   At least one [!DNL *.vw] file resides in the Path Browser directory. 

1. Right-click the check mark for the desired file and click **[!UICONTROL Make Local]**.
1. Right-click the check mark for the file in the [!DNL User] column and click **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**.
1. Edit the parameters of the file using the following sample file and table as guides:

   ```
   window = simpleBorderWindow: 
     client = pathBrowser: 
       Left Path = vector: 0 items
       Map = ref: wdata/model/dim/base dimension name
       Map Group = ref: wdata/model/dim/group dimension name
       Map Level = ref: wdata/model/dim/level dimension name
       Metric = ref: wdata/model/metric/metric name
       Right Path = vector: 0 items
       size = v3d: (673, 279, 0)
     pos = v3d: (714, 143, 0)
     size = v3d: (673, 298, 0)
   ```

<table id="table_1DCCB4B24B554B72A781B304B5EB155E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> For this parameter... </th> 
   <th colname="col2" class="entry"> Provide this information... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><i>Base dimension name</i> </p> </td> 
   <td colname="col2"> <p>The name of the dimension whose elements appear on the path browser. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><i>Group dimension name</i> </p> </td> 
   <td colname="col2"> <p>The name of the dimension that determines how the elements of the level dimension are grouped to form the paths in a path browser. Specifically, the level dimension elements associated with a single path in a path browser cannot span more than one element of a group dimension. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><i>Level dimension name</i> </p> </td> 
   <td colname="col2"> <p>The name of the level (parent) of the base dimension whose elements you drag to the path browser. As you follow a path from one base dimension element to the next, you move from one level dimension element to the next. When you select a path of base dimension elements, you are selecting data for the corresponding elements of the level dimension. The selection always includes the elements of the level dimension that relate to the root, and it is refined by adding more elements to the path. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><i>Metric name</i> </p> </td> 
   <td colname="col2"> <p>The name of the metric whose value for a given element is proportional to the thickness of the path leading to that element. </p> </td> 
  </tr> 
 </tbody> 
</table>

   >[!NOTE]
   >
   >For more information about the base dimension, group dimension, level dimension, and metric for a path browser, see [Path Browsers](../../../home/c-get-started/c-analysis-vis/c-path-browsers/c-path-browsers.md#concept-f2e9fdafed6e49c2bd111ab425cd6e2b).

1. In Notepad, click **[!UICONTROL File]** > **[!UICONTROL Save As]** to save the file with a new name based on the group dimension, that is, *Group dimension name*.vw.

   Make sure that you save the file to the Path Browser directory.

   >[!NOTE]
   >
   >To make sure that your path browser is saved as a [!DNL *.vw] file, in the [!DNL Save As] window, set Save as type to All Files.

1. (Optional) To make the changes available to all users of the working profile, in the [!DNL Profile Manager], right-click the check mark for the file in the [!DNL User] column and click **[!UICONTROL Save to]** > *< **[!UICONTROL working profile name]**>*.
