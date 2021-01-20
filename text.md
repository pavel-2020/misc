The **Button** is the UI component that performs an action when a user clicks it. This tutorial shows how to add the **Button** to a page, apply styling, and configure the core features. As a result, you will get the following UI component:

<div class="simulator-desktop-container" data-view="/Content/Applications/20_2/GettingStartedWith/Button/index.html, /Content/Applications/20_2/GettingStartedWith/Button/index.js, /Content/Applications/20_2/GettingStartedWith/Button/index.css"></div>

Refer to the following sections for details on each configuration step. You can also find the full code in the following GitHub repository: <a href="https://github.com/DevExpress-Examples/getting-started-with-button" target="_blank">getting-started-with-button</a>.

[tags] dxbutton


#### Create a Button
Add DevExtreme to your jQuery application, create a Button and set its text to "Click me!":

[code]

#### Handle the Click Event
You can implement any behavior that occurs when a user clicks a button. For this, use the [onClick](/Documentation/ApiReference/UI_Widgets/dxButton/Configuration/#onClick) handler. In this tutorial, we will display a toast message:

[code]


#### Stylize the Button
##### Specify a styling mode
The styling mode defines whether a Button has a colored border (*"outlined"*), a colored background (*"contained*" - default), or none of them (*"text"*). We will use a colored border. For this, set the [stylingMode](/Documentation/ApiReference/UI_Widgets/dxButton/Configuration/#stylingMode) property to *"outlined"*.

##### Specify a type
The button [type](/Documentation/ApiReference/UI_Widgets/dxButton/Configuration/#type) property defines its color. The following types are available: *"danger"* (red), *"default"* (blue), *"normal"* (transparent), *"success"* (green), and *"back"* (transparent). The type of *"back"* is special - it ignores the **text**, **stylingMode** and other properties and transforms the UI component into a left arrow button. In this tutorial, we will set the **type** to *"success"*.

[code]


#### Add an icon
Apart from text, buttons can also display [icons from different sources](https://js.devexpress.com/Documentation/Guide/Themes_and_Styles/Icons/). To add an icon, specify the [icon](/Documentation/ApiReference/UI_Widgets/dxButton/Configuration/#icon) property (applies to all types except *"back"*). In this tutorial, we will use the [DevExtreme icon library](/Documentation/Guide/Themes_and_Styles/Icons/#Built-In_Icon_Library):

[code]


You have configured basic **Button** features. To take a more detailed look at this UI component, explore the following resources:

- [Demos](https://js.devexpress.com/Demos/WidgetsGallery/Demo/Button/Overview) 
- [API Reference](/Documentation/ApiReference/UI_Widgets/dxButton/)