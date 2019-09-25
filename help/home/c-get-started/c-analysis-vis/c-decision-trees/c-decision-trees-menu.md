---
description: The Decision Tree menu includes features to set the positive use case, filters, leaf distribution options, confusion matrix, and other advanced options.
seo-description: The Decision Tree menu includes features to set the positive use case, filters, leaf distribution options, confusion matrix, and other advanced options.
seo-title: Decision Tree Options
title: Decision Tree Options
uuid: 6439c6d4-60ac-4324-b870-b452a63b7ba1
---

# Decision Tree Options{#decision-tree-options}

The Decision Tree menu includes features to set the positive use case, filters, leaf distribution options, confusion matrix, and other advanced options.

<table id="table_0CBCCB0856E2469EBE8846B413CAB114"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Toolbar buttons </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Go </td> 
   <td colname="col2"> Click to run the decision tree algorithm and display the visualization. This is grayed-out until there are inputs. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Reset </td> 
   <td colname="col2"> Clears inputs and decision tree model and resets the process. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Save </td> 
   <td colname="col2"><b>Save the Decision Tree</b>. You can save the Decision Tree in different formats: 
    <ul id="ul_F7C7836C06D64912893113E8EEA05704"> 
     <li id="li_D2D8451A679243F1BC67C3B80CA5F83F">Predictive Markup Language (<b>PMML</b>), an XML-based file format used by applications to describe and exchange decision tree models. </li> 
     <li id="li_88C4B3E050CA4EFC9B7FA8BD446A9C55"><b>Text</b> displaying simple columns and rows of true or false, percentages, number of members, and input values. </li> 
     <li id="li_3F871B88F3FA41E9B95EFF5A181E3D57">A <b>Dimension</b> with branches corresponding to predicted outcome elements. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Options </td> 
   <td colname="col2"> See table below for Options menu. </td> 
  </tr> 
 </tbody> 
</table>

<table id="table_24D84440D0354C70928E8927624DB255"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Options menu </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Set Positive Case </td> 
   <td colname="col2"> Defines the current workspace selection as the model's Positive Case. Clears the case if no selection exists. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Set Population Filter </td> 
   <td colname="col2"> Defines the current workspace selection as the model's Population Filter and will be drawn from visitors who satisfy this condition. The default is "Everyone." </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Show Complex Filter Description </td> 
   <td colname="col2"> Displays descriptions of the defined filters. Click to view the filtering scripts for the Positive Case and Population Filter. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Hide Nodes </td> 
   <td colname="col2"> Hides nodes with only a small percentage of the population. This menu command displays only when the decision tree is displayed. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Confusion Matrix </td> 
   <td colname="col2"> <p>Click <span class="uicontrol"> Options</span> &gt; <span class="uicontrol"> Confusion Matrix</span> to view the Accuracy, Recall, Precision and F-Score values. The closer to 100 percent, the better the score. </p> <p>The Confusion Matrix gives four counts of accuracy of the model using a combination of values: 
     <ul id="ul_D9D512F5D74B44BDBD27B1912DF4CB02"> 
      <li id="li_28C541DF1CB543FEAF2D13C2F329DB52">Actual Positive (AP) </li> 
      <li id="li_56233006A1544D95A72CE096CA55C1E6">Predicted Positive (PP) </li> 
      <li id="li_375FB2D6A0A3418A9AD377C9EBB65386">Actual Negative (AN) </li> 
      <li id="li_07A5D23A36BA4D448C25C1414836EB8E">Predicted Negative (PN) </li> 
     </ul> </p> <p>Tip:  These numbers are obtained by applying the resulted scoring model of the 20 percent testing data withheld and already known as the true answer. If the score is greater than 50 percent, it is predicted as a positive case (that matches the defined filter). Then, Accuracy = (TP + TN)/(TP + FP + TN + FN), Recall = TP / (TP + FN), and Precision = TP / (TP + FP). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Display Legend </td> 
   <td colname="col2">Allows you to toggle a legend key on and off in the Decision Tree. <img placement="break" id="image_D5B9415A48C04619955BD96970F720A1" src="assets/decison_tree_legend.png" />This menu command displays only when the decision tree is displayed. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Advanced </td> 
   <td colname="col2"> Click to open Advanced menu for in-depth use of Decision Tree. See table below for menu options. </td> 
  </tr> 
 </tbody> 
</table>

<table id="table_91E4A74BFB224ABD889147324AC2910F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Advanced menu </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Training Set Size </td> 
   <td colname="col2"> <p>Controls the size of the training set used for the model building. Larger sets take longer to train, smaller sets take less time. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Input Normalization </td> 
   <td colname="col2"> <p> Allows the user to specify whether to use the Min-Max or the Z Score technique to normalize inputs into the model. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SMOTE Over-Sampling Factor </td> 
   <td colname="col2"> When the Positive Case does not occur very often (less than 10 percent) in the training sample, SMOTE is used to provide additional samples. This option allows the user to indicate how many more samples to create using SMOTE. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Leaf Class Distribution Threshold </td> 
   <td colname="col2"> Allows you to set the threshold assumed for a leaf during the tree building process. By default, all members of a node must be identical for it to be a leaf (prior to pruning stage). </td> 
  </tr> 
 </tbody> 
</table>

