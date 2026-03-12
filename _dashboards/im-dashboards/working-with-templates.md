---
layout: default
title: Working with templates
parent: Managing indexes in Dashboards
has_children: false
nav_order: 80
---


# Working with templates

2 sub-pages: component and simple

You can use [Index templates]({{site.url}}{{site.baseurl}}/opensearch/index-templates/) to initialize new indexes with predefined mappings and settings. For example, if you continuously index log data, you can define an index template so that all of the indexes have the same number of shards and replicas as shown in the following image.

<img src="{{site.url}}{{site.baseurl}}/images/admin-ui-index/templates.PNG" alt="User interface showing Templates page">

This page describes how to:

- [Create a template](#creating-a-template)
- [Create a component template]({{site.url}}{{site.baseurl}}/dashboards/im-dashboards/component-templates/)
- [View a template](#viewing-a-template)
- [Edit a template](#editing-a-template)
- [Delete a template](#deleting-a-template)

## Creating a template

To create a template:

1. Select **Index Management** > **Templates**.

1. Choose the **+ Create template** button.

1. On the **Create template** page, enter the template name.

1. Select the **Template type**, `Indexes` or `Data streams`.

1. Enter a comma-separated list of index patterns to apply the template to.

1. Choose a priority for the template. Templates are applied to matching indexes in priority order, highest first.

1. Select a **template method** tile, either **Simple template** or **Componenet template**.

1. To use the **Component template method**, skip these substeps and go to the next step. To use the **Simple template** method, follow these substeps: 

    1. (Optional) In the **Template definition** panel, select one or more index aliases.

    1. Enter the Index settings, including **Number of primary shards**, **Number of replicas**, and **Refresh interval**.

    1. (Optional) Expand the **Advanced settings** panel and add a comma-delimited list of settings in JSON format between the curly braces in the **Specify advanced index settings** area.

    1. In the **Index mapping** panel, select the **Visual Editor** or the **JSON Editor**. 

       If you have configurations that are not supported by the **Visual Editor**, you must use the **JSON Editor** to configure them.
       {: .note}

    1. Add **Index mapping** fields and objects.

1.  If you used the **Simple template** method, skip these substeps. To use the **Component method**, follow these substeps:

    1. (Optional) If you need to create one or more component templates, choose the **Create component template** button and complete the instructions for [Creating a component template]({{site.url}}{{site.baseurl}}/dashboards/im-dashboards/component-templates/).

    1. Select **Associate component templates**.

    1. In the **Associate component templates** dialog, select the component templates to add.

    1. Select the **Associate** button.

    1. Order the component templates. Attributes are applied to the new template in order from the first component template to the last. An attribute is overwritten by the last component template to be applied.

    1. (Optional) Expand the **Override template definition** panel and apply component attributes as specified in the previous step. These values overwrite the values from component templates.

1. (Optional) Select **Preview template** from the confirmation bar to view your completed template. Select **Close** to dismiss the **Preview template** dialog.

1. Select the **Create template** button from the confirmation bar to create your template.


## Viewing a template

To view an existing template:

1. Select the checkbox next to the template you want to edit.

1. Select the **Actions** button.

1. Choose **Edit** from the dropdown list.

1. Choose the **Summary** tab after the **Overview** panel.


## Editing a template

1. Select the checkbox next to the template you want to edit.

1. Select the **Actions** button.

1. Choose **Edit** from the dropdown list.

1. Choose the **Configuration** tab after the **Overview** panel.

1. Edit the fields you want to change in the template. The options are the same as in [**Creating a template**](#creating-a-template).

1. (Optional) In the confirmation bar, select **Preview template** to view the revised template.

1. Choose **Save** to make your changes to the template.


## Deleting a template

Use caution when deleting templates. This action is irreversible.
{: .warning}

1. Select the checkbox next to one or more templates you want to delete.

1. Select the **Actions** button.

1. Choose **Delete** from the dropdown list.

1. Enter `delete` in the confirmation box.

1. Select **Delete**.
