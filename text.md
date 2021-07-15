The TreeView component represents textual data from a local or remote source in the form of a single-column tree view. The component allows users to select and view loaded data.

This tutorial shows how to add the TreeView to a page, bind it to data, and configure its core features. As a result, you will get a UI component that looks as follows:

_

Refer to the following sections for details on each configuration step. You can also find the full code in the following GitHub repository: <a href="_" target="_blank">getting-started-with-treeview</a>.

[tags] dxtreeview

#### 02 Create a TreeView
[Add DevExtreme to your jQuery application](/concepts/58%20jQuery%20Components/05%20Add%20DevExtreme%20to%20a%20jQuery%20Application/00%20Add%20DevExtreme%20to%20a%20jQuery%20Application.md '/Documentation/Guide/jQuery_Components/Add_DevExtreme_to_a_jQuery_Application/') and use the following code to create a TreeView:

#### 05 Bind the TreeView to Data
The TreeView supports plain and hierarchical (default) data structures. In a hierarchical data structure, each node should have a text, unique identifier, and optionally nest other nodes. Refer to the following demo for more information: [Hierarchical Data Structure](/Demos/WidgetsGallery/Demo/TreeView/HierarchicalDataStructure/).

If a data source has a plain structure, set the [dataStructure](/Documentation/ApiReference/UI_Components/dxTreeView/Configuration/#dataStructure) property to *"plain"*. Each node should have a unique identifier, a text, and a reference to its parent node. If corresponding data fields use custom names, use the keyExpr, parentIdExpr, and itemsExpr properties to specify them. Refer to this demo for details: [Plain Data Structure](https://js.devexpress.com/Demos/WidgetsGallery/Demo/TreeView/FlatDataStructure/).

To bind the TreeView to data, use the dataSource property. The following articles explain how to do this for different data structures:

- [Local Array](/Documentation/Guide/Data_Binding/Specify_a_Data_Source/Local_Array/)
- [Read-Only Data in JSON Format](/Documentation/Guide/Data_Binding/Specify_a_Data_Source/Read-Only_Data_in_JSON_Format/)
- [Web API, PHP, MongoDB](/Documentation/Guide/Data_Binding/Specify_a_Data_Source/Web_API,_PHP,_MongoDB/)
- [OData](/Documentation/Guide/Data_Binding/Specify_a_Data_Source/OData/)
- [Custom Data Sources](/Documentation/Guide/Data_Binding/Specify_a_Data_Source/Custom_Data_Sources/)

In this tutorial, we use the **dataStructure** property to bind a plain array. 

#### 10 Customize Node Appearance
To customize all nodes, specify the [itemTemplate](/Documentation/ApiReference/UI_Components/dxTreeView/Configuration/#itemTemplate) property. If you need to customize individual nodes, specify the [template](/Documentation/ApiReference/UI_Components/dxTreeView/Configuration/items/#template) and other [items[] properties](/Documentation/ApiReference/UI_Components/dxTreeView/Configuration/items/).

If you use jQuery, you can apply a 3rd-party template engine. For details, see the [3rd-Party Template Engines](/Documentation/Guide/UI_Components/Common/Templates/#3rd-Party_Template_Engines) article.

In this tutorial, we make specific nodes [expanded](/Documentation/ApiReference/UI_Components/dxTreeView/Configuration/items/#expanded) and specify the **itemTemplate**.

#### 30 Search Data
Enable the [searchEnabled](/Documentation/ApiReference/UI_Components/dxTreeView/Configuration/#searchEnabled) property to add the search bar. Use the [searchMode](/Documentation/ApiReference/UI_Components/dxTreeView/Configuration/#searchMode) property to specify whether items should contain (default), start with, or match the search string. In this tutorial, the search mode is *"startswith"*:

#### 50 Select Records
To enable node selection, set the [selectByClick](/Documentation/ApiReference/UI_Components/dxTreeView/Configuration/#selectByClick) property to **true**. If you want to add checkboxes for each node, set the [showCheckBoxesMode](/Documentation/ApiReference/UI_Components/dxTreeView/Configuration/#showCheckBoxesMode) property to *"normal"* or *"selectAll"*. The latter mode additionally displays the "Select All" checkbox at the top of the TreeView.

The default selection mode is multiple. As an alternative, you can set the [selectionMode](/Documentation/ApiReference/UI_Components/dxTreeView/Configuration/selectionMode) property to *"single"*.

To obtain the selected node's data, use the [onItemSelectionChanged](/Documentation/ApiReference/UI_Components/dxTreeView/Configuration/#onItemSelectionChanged) function. In the code below, this function displays the selected book and its author:

#### 60 Enable Node Drag & Drop
Drag & Drop allows users to reorder nodes and change their hierarchy. This functionality is not used in this tutorial. For details, refer to the Drag & Drop for Plain Data Structure demo.

#### 70 Enhance Performance on Large Datasets
If you use a large remote dataset, enable the Virtual Mode to enhance performance. In this mode, the TreeView loads a set of child nodes once a user expands the parent node for the first time. Refer to the Virtual Mode demo for details.
