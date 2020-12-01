The **Button** is the component that performs an action when a user clicks it. This tutorial shows how to add the **Button** to a page, apply styling, and configure the core features. As a result, you will get the following widget:

<div class="simulator-desktop-container" data-view="/Content/Applications/20_2/GettingStartedWith/Button/index.html, /Content/Applications/20_2/GettingStartedWith/Button/index.js, /Content/Applications/20_2/GettingStartedWith/Button/index.css"></div>

Refer to the following sections for details on each configuration step. You can also find the full code in the following GitHub repository: <a href="https://github.com/DevExpress-Examples/getting-started-with-button" target="_blank">getting-started-with-button</a>.

[tags] dxbutton


#### Create a Button
Add DevExtreme to your jQuery application and use the following code to create a Button:

[code]


#### Specify a custom type
The widget supports these 5 types: *"back"*, *"danger"*, *"default"*, *"normal"*, and *"success"*. We will set the [type](/Documentation/ApiReference/UI_Widgets/dxButton/Configuration/#type) option to *"success"* to make the widget green.

[code]


#### Specify a styling mode
The styling mode defines whether a button has a colored border (*"outlined"*), a colored background (*"contained*" - default), or none of them (*"text"*). We will use a colored border. For this, set the [stylingMode](/Documentation/ApiReference/UI_Widgets/dxButton/Configuration/#stylingMode) option to *"outlined"*:

[code]


#### Add an icon
Apart from text, buttons can also display various types of icons. To add one, specify the [icon](/Documentation/ApiReference/UI_Widgets/dxButton/Configuration/#icon) option. In this tutorial, we will use the [DevExtreme icon library](/Documentation/Guide/Themes_and_Styles/Icons/#Built-In_Icon_Library):

[code]


#### Set custom height and width
Use the [height](/Documentation/ApiReference/UI_Widgets/dxButton/Configuration/#height) and [width](/Documentation/ApiReference/UI_Widgets/dxButton/Configuration/#width) options:

[code]


#### Add a hint
When a user hovers over a button, it can show an informational text box next to the cursor. Specify this text in the [hint](/Documentation/ApiReference/UI_Widgets/dxButton/Configuration/#hint) option:

[code]


#### Handle the click event
You can use the [onClick](/Documentation/ApiReference/UI_Widgets/dxButton/Configuration/#onClick) handler to implement any behavior that occurs when a user clicks a button. In this tutorial, we will display a toast message:

[code]

You have configured basic **Button** features. To take a more detailed look at this widget, explore the following resources:

- [Demos](https://js.devexpress.com/Demos/WidgetsGallery/Demo/Button/Overview) 
- [API Reference](/Documentation/ApiReference/UI_Widgets/dxButton/)