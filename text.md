The TreeList component uses a multi-column tree view to display data from a local or remote store and allows users to sort, group, filter, and perform other operations.

This tutorial shows how to add the TreeList to a page, bind it to data, and configure its core features. As a result, you will get a UI component that looks as follows:

<demo code>

Refer to the following sections for details on each configuration step. You can also find the full code in the following GitHub repository: <a href="https://github.com/DevExpress-Examples/getting-started-with-datagrid" target="_blank">getting-started-with-datagrid</a>.

[tags] dxtreelist

#### 02 Create a TreeList
[Add DevExtreme to your jQuery application]() and use the following code to create a TreeList:

#### 05 Bind the TreeList to Data
TreeList can load data from the following sources:

* Local data array

* Read-Only Data in JSON Format

* Web API, PHP, MongoDB

* OData

* Custom Data Sources.

The data array can have a plain (default) or tree structure. In this tutorial, we will use the former. In this case, each data item must reference the parent node (the `parentId` default field) and have a unique identifier (the `id` default field). Since data items use non-default field names, we have specified them in the keyExpr and parentIdExpr properties. Also, we have specified the custom root node's identifier in the rootValue property (the default value is 0).

#### 07 Expand Rows
The default behavior is to collapse all rows on TreeList load. In this tutorial, we will enable the autoExpandAll property to expand them all. You can also specify certain rows in the expandedRowKeys property to expand them only.

#### 10 Customize Columns
**0 Customize Columns**          
To customize columns, declare the [columns]() array. This array can contain objects (column configurations) and text strings (data field names). Use objects if you need to customize columns.

**3 Reorder Columns**          
To reorder columns, change their order in the **columns** array. Users can also reorder columns if you enable the [allowColumnReordering](/Documentation/ApiReference/UI_Components/dxTreeList/Configuration/#allowColumnReordering) property.

**5 Resize Columns**        
TreeList columns have equal widths by default. You can set each column's [width](/Documentation/ApiReference/UI_Components/dxTreeList/Configuration/columns/#width) or indicate that all columns should adjust their widths to their content ([columnAutoWidth](/Documentation/ApiReference/UI_Components/dxTreeList/Configuration/#columnAutoWidth)). Users can resize columns if you enable the [allowColumnResizing](/Documentation/ApiReference/UI_Components/dxTreeList/Configuration/#allowColumnResizing) property.

**6 Fix Columns**          
When the width of all columns exceeds the UI component's width, users can scroll the grid horizontally. If you set the [columnFixing](/Documentation/ApiReference/UI_Components/dxTreeList/Configuration/columnFixing/).[enabled](/Documentation/ApiReference/UI_Components/dxTreeList/Configuration/columnFixing/#enabled) property to **true**, users can show certain columns in the view regardless of how far they scroll the grid.

You can also enable a column's [fixed](/Documentation/ApiReference/UI_Components/dxTreeList/Configuration/columns/#fixed) property in code. This fixes the column to the UI component's left edge. To change the position, set the [fixedPosition](/Documentation/ApiReference/UI_Components/dxTreeList/Configuration/columns/#fixedPosition) property.

The following code fixes the `FullName` column to the default position and allows users to fix and unfix columns at runtime:

**8 Hide Columns**        
The TreeList displays all columns from the **columns** array. To hide a column, set its [visible](/Documentation/ApiReference/UI_Components/dxTreeList/Configuration/columns/#visible) property to **false**. Hidden columns appear in the [columnChooser](/Documentation/ApiReference/UI_Components/dxTreeList/Configuration/columnChooser/). Users can restore hidden columns from it. To enable the column chooser, set the **columnChooser**.[enabled](/Documentation/ApiReference/UI_Components/dxTreeList/Configuration/columnChooser/#enabled) property to **true**. If a column should not be visible even in the column chooser, simply do not declare it in the **columns** array.

#### 20 Sort Data
The **sorting**.[mode](/Documentation/ApiReference/UI_Components/dxTreeList/Configuration/sorting/#mode) property specifies whether users can sort records by single or multiple columns. This tutorial uses the default sorting mode - single. 

You can also set a column's [sortOrder](/Documentation/ApiReference/UI_Components/dxTreeList/Configuration/columns/#sortOrder) and [sortIndex](/Documentation/ApiReference/UI_Components/dxTreeList/Configuration/columns/#sortIndex) properties to specify the initial sorting settings. **sortIndex** applies only in multiple sorting mode.

#### 30 Filter and Search Data
The TreeList includes the following UI elements used to filter and search data:

- [filterRow](/Documentation/ApiReference/UI_Components/dxTreeList/Configuration/filterRow/)
- [headerFilter](/Documentation/ApiReference/UI_Components/dxTreeList/Configuration/columns/headerFilter/)
- [filterPanel](/Documentation/ApiReference/UI_Components/dxTreeList/Configuration/filterPanel/) with [filterBuilder](/Documentation/ApiReference/UI_Components/dxTreeList/Configuration/#filterBuilder)
- [searchPanel](/Documentation/ApiReference/UI_Components/dxTreeList/Configuration/searchPanel/)

In this tutorial, the **filterRow** and **searchPanel** are displayed:

#### 40 Edit and Validate Data
Users can add, update, and delete records. To allow these operations, enable the [allowAdding](/Documentation/ApiReference/UI_Components/dxTreeList/Configuration/editing/#allowAdding), [allowUpdating](/Documentation/ApiReference/UI_Components/dxTreeList/Configuration/editing/#allowUpdating), and [allowDeleting](/Documentation/ApiReference/UI_Components/dxTreeList/Configuration/editing/#allowDeleting) properties in the [editing](/Documentation/ApiReference/UI_Components/dxTreeList/Configuration/editing/) object. Multiple [edit modes](/Documentation/ApiReference/UI_Components/dxTreeList/Configuration/editing/#mode) are available. This tutorial uses the pop-up edit mode.

DevExtreme includes a validation engine that checks edited values before they are saved. This engine supports different validation rule types, such as [Email](/Documentation/ApiReference/UI_Components/dxValidator/Validation_Rules/EmailRule/), [Compare](/Documentation/ApiReference/UI_Components/dxValidator/Validation_Rules/CompareRule/), [Range](/Documentation/ApiReference/UI_Components/dxValidator/Validation_Rules/RangeRule/), and more. Validation rules are specified per column; one column can use multiple rules. The code below assigns the [Required](/Documentation/ApiReference/UI_Components/dxValidator/Validation_Rules/RequiredRule/) rule to several columns.

#### 50 Select Records
The TreeList supports single and multiple record selection modes. Use the **selection**.[mode](/Documentation/ApiReference/UI_Components/dxTreeList/Configuration/selection/#mode) property to specify the mode.

You can obtain the selected record's data in the [onSelectionChanged](/Documentation/ApiReference/UI_Components/dxTreeList/Configuration/#onSelectionChanged) function. In the code below, this function displays the selected employee under the TreeList:

#### 60 Enable Row Drag & Drop
Users can drag and drop nodes to reorder them or change their hierarchy. To enable these features, do the following:

1. Set the allowReordering and allowDropInsideItem properties to true.

2. Implement the onDragChange function.           
Inside the function, prevent a node from being placed among its child nodes: cancel the drop event if a user places a node in the invalid position.

1. Implement the onReorder function.          
Inside the function, change the parent ID of the reordered node and the node's index in the data array. If the node was dropped onto another node, changing the parent ID is sufficient.

To perform drag & drop operations, use the drag icons in the leftmost column. If you want to hide them and use rows instead, set the showDragIcons property to false.

#### 70 Enable Pagination
When paging is enabled, TreeList processes records page by page instead of processing them all at once. To add paging, set the paging.enabled property to **true** and specify the optimal number of records per page in the paging.pageSize property. Use this feature if your tests show noticeable lags without this feature.
