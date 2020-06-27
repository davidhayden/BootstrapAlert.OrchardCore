# Bootstrap Alert

Bootstrap Alert is an Orchard Core CMS Module that adds a recipe to your Orchard Core CMS Website. When run, the recipe creates an Alert Widget and corresponding template to display a Bootstrap Alert.

## Current Status

[![Build status](https://ci.appveyor.com/api/projects/status/btwxkpt2ihgg8mnt?svg=true)](https://ci.appveyor.com/project/davidhayden/bootstrapalert-orchardcore) [![Status](https://img.shields.io/myget/davidhayden-ci/v/BootstrapAlert.OrchardCore.svg)](https://www.myget.org/feed/davidhayden-ci/package/nuget/BootstrapAlert.OrchardCore)

## Getting Started

The module expects Bootstrap to be used by the Orchard Core CMS website. The module does not come with Bootstrap CSS and JS. Make sure your theme includes the necessary assets for the Alert to look and work properly.

Add the NuGet package, **BootstrapAlert.OrchardCore**, to the Orchard Core CMS Website. Launch the website and sign in as an administrator to enable the module from the dashboard under <i>Configuration</i> -> <i>Features</i>.

![BootstrapAlert.OrchardCore](https://github.com/davidhayden/BootstrapAlert.OrchardCore/blob/master/assets/bootstrap-alert-module.png?raw=true)

The module installs a recipe, called <em>Alert Widget</em>, that adds a widget to display a Bootstrap Alert. You can view and run the recipe from the dashboard under <i>Configuration</i> -> <i>Recipes</i>.

![Alert Widget Recipe](https://github.com/davidhayden/BootstrapAlert.OrchardCore/blob/master/assets/alert-widget-recipe.png?raw=true)

You can view the Alert Content Type (stereotyped as a widget) by displaying the Content Types from the dashboard under <i>Content Definition</i> -> <i>Content Types</i>.

![Alert Content Type](https://github.com/davidhayden/BootstrapAlert.OrchardCore/blob/master/assets/alert-content-type.png?raw=true)

In addition to the Alert Content Type, the recipe also installs a custom liquid template to display the Alert Widget. View the template from the dashboard under <i>Configuration</i> -> <i>Templates</i>.

![Alert Widget Template](https://github.com/davidhayden/BootstrapAlert.OrchardCore/blob/master/assets/alert-widget-template.png?raw=true)

Specify the <em>Type</em> of alert (e.g. Success, Info, Warning, Danger) and the <em>body</em> of the alert when adding it to a zone. The recipe specifies the Standard HTML Editor for the body as it assumes HTML will be used infrequently and sparingly.

![New Alert Widget](https://github.com/davidhayden/BootstrapAlert.OrchardCore/blob/master/assets/new-alert-widget.png?raw=true)

After publishing the widget, navigate to the appropriate area of your website to view the alert.

![Bootstrap Alert Component](https://github.com/davidhayden/BootstrapAlert.OrchardCore/blob/master/assets/bootstrap-alert-component.png?raw=true)

For more information on the the Bootstrap Alert Component, visit the [Bootstrap documentation](https://getbootstrap.com).

## Customization

The Alert Widget produces the suggested HTML mentioned in the Bootstrap documentation and allows one to create an alert with no knowledge of HTML. You can, however, customize the HTML by modifying the liquid template that comes with the module, <em>Widget__Alert</em>. You can modify the template from the dashboard under <i>Configuration</i> -> <i>Templates</i>. See the Orchard Core Documentation for more information on [Templates](https://orchardcore.readthedocs.io/en/latest/OrchardCore.Modules/OrchardCore.Templates/README/).

```html
<div class="alert alert-{{ Model.ContentItem.Content.Alert.Type.Text }}" role="alert">
  {{ Model.Content.HtmlBodyPart | shape_render }}
</div>
```

The [HTML Body Part](https://orchardcore.readthedocs.io/en/latest/OrchardCore.Modules/OrchardCore.Html/README/) used to input the body of the alert uses the <em>Standard</em> HTML Editor. You can change the editor to use a <em>Wysiwyg</em> editor.

![HtmlBody Part Settings](https://github.com/davidhayden/BootstrapAlert.OrchardCore/blob/master/assets/htmlbodypart-settings.png?raw=true)

If you prefer to use <em>Markdown</em> instead of <em>HTML</em>, you can replace the <em>HTML Body Part</em> with the <em>Markdown Body Part</em>. If you do choose <em>Markdown</em>, you will also need to change the template.

![MarkdownBody Part Settings](https://github.com/davidhayden/BootstrapAlert.OrchardCore/blob/master/assets/markdownbodypart.png?raw=true)

```html
<div class="alert alert-{{ Model.ContentItem.Content.Alert.Type.Text }}" role="alert">
  {{ Model.Content.MarkdownBodyPart | shape_render }}
</div>
```

The <em>Type</em> of alert is specified by choosing an option from the <em>Type</em> drop down list. The list comes preconfigued with the following types: <i>Success</i>, <i>Info</i>, <i>Warning</i>, and <i>Danger</i>. The list uses the Predefined List Editor. You can add additional types by editing the <em>Type</em> field and the list of options.

![Predefined List Editor Options](https://github.com/davidhayden/BootstrapAlert.OrchardCore/blob/master/assets/predefined-list-editor.png?raw=true)

## Road map

There are no plans to add any additional features at this time.

## Credits
BootstrapAlert.OrchardCore is created and maintained by David Hayden.

[Bootstrap](https://getbootstrap.com) is a popular front-end component library.