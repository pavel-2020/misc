The TreeView component represents textual data from a local or remote source in the form of a single-column tree view. The component allows users to select and view loaded data.

This tutorial shows how to add the TreeView to a page, bind it to data, and configure its core features. As a result, you will get a UI component that looks as follows:

_

Refer to the following sections for details on each configuration step. You can also find the full code in the following GitHub repository: <a href="_" target="_blank">getting-started-with-treeview</a>.

[tags] dxtreeview

#### 02 Create a TreeView
[Add DevExtreme to your jQuery application](/concepts/58%20jQuery%20Components/05%20Add%20DevExtreme%20to%20a%20jQuery%20Application/00%20Add%20DevExtreme%20to%20a%20jQuery%20Application.md '/Documentation/Guide/jQuery_Components/Add_DevExtreme_to_a_jQuery_Application/') and use the following code to create a TreeView:

#### 05 Bind the TreeView to Data
The TreeView supports plain and hierarchical (default) data structures. In a hierarchical data structure, each node should have a text, unique identifier, and optionally nest other nodes. Refer to the following demo for more information: [Hierarchical Data Structure](/Demos/WidgetsGallery/Demo/TreeView/HierarchicalDataStructure/).

If a data source has a plain structure, set the [dataStructure](/Documentation/ApiReference/UI_Components/dxTreeView/Configuration/#dataStructure) property to *"plain"*. Each node should reference its child node, specify a text and a unique identifier. Refer to this demo for details: [Plain Data Structure](https://js.devexpress.com/Demos/WidgetsGallery/Demo/TreeView/FlatDataStructure/).

The TreeView component can load data from different data source types. To use a local array, assign it to the [items](/Documentation/ApiReference/UI_Components/dxTreeView/Configuration/#items) property. 

If you want to use a remote data source or apply the data-shaping API, use the dataSource property instead. The following articles explain how to do this for different data structures:

- [Local Array](/Documentation/Guide/Data_Binding/Specify_a_Data_Source/Local_Array/)
- [Read-Only Data in JSON Format](/Documentation/Guide/Data_Binding/Specify_a_Data_Source/Read-Only_Data_in_JSON_Format/)
- [Web API, PHP, MongoDB](/Documentation/Guide/Data_Binding/Specify_a_Data_Source/Web_API,_PHP,_MongoDB/)
- [OData](/Documentation/Guide/Data_Binding/Specify_a_Data_Source/OData/)
- [Custom Data Sources](/Documentation/Guide/Data_Binding/Specify_a_Data_Source/Custom_Data_Sources/)

In this tutorial, we use the **items[]** property to bind a hierarchical array. 

#### 10 Customize Node Appearance
To customize all nodes, specify the [itemTemplate](/Documentation/ApiReference/UI_Components/dxTreeView/Configuration/#itemTemplate) property. If you need to customize individual nodes, specify the [template](/Documentation/ApiReference/UI_Components/dxTreeView/Configuration/items/#template) and other [items[] properties](/Documentation/ApiReference/UI_Components/dxTreeView/Configuration/items/).

If you use jQuery, you can apply a 3rd-party template engine. For details, see the [3rd-Party Template Engines](/Documentation/Guide/UI_Components/Common/Templates/#3rd-Party_Template_Engines) article.

In this tutorial, we make specific nodes [expanded](/Documentation/ApiReference/UI_Components/dxTreeView/Configuration/items/#expanded) and specify the **itemTemplate**.

#### 30 Search Data
Enable the [searchEnabled](/Documentation/ApiReference/UI_Components/dxTreeView/Configuration/#searchEnabled) property to add the search bar. Use the [searchMode](/Documentation/ApiReference/UI_Components/dxTreeView/Configuration/#searchMode) property to specify whether items should contain (default), start with, or match the search string. In this tutorial, the search mode is *"startswith"*:

#### 50 Select Records
To enable node selection, set the [selectByClick](/Documentation/ApiReference/UI_Components/dxTreeView/Configuration/#selectByClick) property to **true**. If you want to add checkboxes for each node, set the [showCheckBoxesMode](/Documentation/ApiReference/UI_Components/dxTreeView/Configuration/#showCheckBoxesMode) property to *"normal"* or *"selectAll"*. The latter mode additionally displays the "Select All" checkbox at the top of the TreeView.

The default selection mode is multiple. As an alternative, you can set the [selectionMode](/Documentation/ApiReference/UI_Components/dxTreeView/Configuration/selectionMode) property to *"single"*.

To obtain the selected node's data, use the [onSelectionChanged](/Documentation/ApiReference/UI_Components/dxTreeView/Configuration/#onSelectionChanged) function. In the code below, this function displays the selected book and its author:

#### 70 Enhance Performance on Large Datasets
If the dataset is large, enable the Virtual Mode to enhance performance. In this mode, the TreeView loads a set of child nodes once a user expands the parent node for the first time. 

To enable this feature, set the [virtualModeEnabled](/Documentation/ApiReference/UI_Components/dxTreeView/Configuration/#virtualModeEnabled) property to **true**. Note that this mode is only available when the TreeView's [dataStructure](/Documentation/ApiReference/UI_Components/dxTreeView/Configuration/#dataStructure) is plain.

When the data source is remote, the TreeView requests data for each expanded node. To prevent this for nodes that do not nest others, set the [hasItems](/Documentation/ApiReference/UI_Components/dxTreeView/Configuration/items/#hasItems) field to **false** for the corresponding data objects.

As an alternative to virtual mode, you can use a custom logic to process requested data. To do this, specify the [createChildren](/Documentation/ApiReference/UI_Components/dxTreeView/Configuration/#createChildren) function as shown in the [Load Data on Demand](/Demos/WidgetsGallery/Demo/TreeView/LoadDataOnDemand) demo.