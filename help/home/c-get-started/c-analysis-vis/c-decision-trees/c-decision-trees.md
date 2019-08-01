---
description: Decision trees are a predictive analytics visualization used to evaluate visitor characteristics and relationships. The Decision Tree Builder generates a decision tree visualization based on a specified positive case and a set of inputs.
seo-description: Decision trees are a predictive analytics visualization used to evaluate visitor characteristics and relationships. The Decision Tree Builder generates a decision tree visualization based on a specified positive case and a set of inputs.
seo-title: Decision Tree Builder
solution: Analytics
title: Decision Tree Builder
topic: Data workbench
uuid: f3bc997d-3168-4698-ad1f-659a7e6b73d5
index: y
internal: n
snippet: y
---

# Decision Tree Builder{#decision-tree-builder}

Decision trees are a predictive analytics visualization used to evaluate visitor characteristics and relationships. The Decision Tree Builder generates a decision tree visualization based on a specified positive case and a set of inputs.

A Decision Tree is a binary classifier with a set of rules (or filters) identifying visitors who satisfy specific rules based on a positive case. A decision tree sets rules to classify visitors who satisfy (or do not satisfy) this positive case. These rules generate a tree map to provide a level of confidence to meet these positive case results.

A Decision Tree is built by examining inputs at each level and choosing the one that provides a maximum gain of information at a specified split point. Split points for each variable-level generates two sets:

* Values less than or equal to the split point, and 
* Values greater than the split point.

Use decision trees to

* Perform meaningful analysis and interpretation in less time. 
* Employ automated segment generation. 
* Quickly make inferences from a model based on a large amount of data.

![](assets/decision_tree_parts.png) 

<table id="table_FCC5D63EF8A843D79B2338BD951025EA"> 
 <tbody> 
  <tr> 
   <td colname="col1" valign="top"> <p><b>Toolbar and Menus</b> </p> <p>The toolbar includes buttons and menu commands for the Decision Tree, including features to set the Positive Case and add Input Listings. </p> <p>Like other visualizations, the <span class="uicontrol"> Element</span> box lets you drag and drop Dimension and Elements, although you can also drag directly from the Finders pane. </p> <p>For additional information, see <a href="../../../../home/c-get-started/c-analysis-vis/c-decision-trees/c-decision-trees-menu.md#concept-bfc4e80651a243d3966cc770b205606c" format="dita" scope="local"> Decision Tree Options</a>. </p> </td> 
   <td colname="col2" valign="top"> <p><b>Input Listing</b> </p> <p>This area displays the inputs into the tree model. They are color coded to match nodes in the Tree Display area. </p> <p>Right-clicking on an input allows you to remove the input from the model and reset. </p> <p>If you hover over a tree node, it will display the split conditions along the branch to that node and the prediction at that node with its confidence value. </p> </td> 
   <td colname="col3" valign="top"> <p><b>Tree Display</b> </p> <p>This area displays the tree model with leaf nodes color-coded based on its prediction: green for a True prediction of the Positive Case, and red for a False prediction. </p> <p>The split nodes are color coded to the inputs that match their selection condition. Hovering over a node displays information about the split and expands the inputs listing to display the split points along the branch and the distribution of the training set. </p> <p>Nodes below a threshold are not displayed by default. Click on an expandable node (indicated by a + symbol) to explore a branch. Click on the root node to return to the full tree display. </p> </td> 
  </tr> 
 </tbody> 
</table>

<a id="section_E800327344194A6DBF37F273D8462E2A"></a>

