---
layout: default
title: Working with aliases
parent: Managing indexes in Dashboards
has_children: false
nav_order: 90
---

# Working with aliases

An alias is a virtual index name that can point to one or more indexes. If your data is spread across multiple indexes, rather than keeping track of which indexes to query, you can create an alias and query it instead as shown in the following image.

<img src="{{site.url}}{{site.baseurl}}/images/admin-ui-index/aliases.PNG" alt="User interface showing Alias page">

## Creating an alias

To create a new alias:

1. Select the **Create alias** button in the upper-right corner of the **Indexes** page.

    Dashboards displays the **Create alias** dialog.

    <img src="{{site.url}}{{site.baseurl}}/images/admin-ui-index/create-alias.PNG" alt="User interface showing create Alias page">

1. Enter a name in the **Alias name** field.

1. To add an existing index or index pattern to the alias, choose it from the **Indexes or index patterns** drop-down.

1. To add a new index pattern, enter the pattern in the **Indexes or index patterns** drop-down and select a point in the **Create alias** dialog to dismiss the text box.

1. Select the **Create alias** button.


## Editing an alias

To edit an alias, perform the following steps:

1. On the **Aliases** page, select the alias you want to edit.

    Dashboards displays the **Update alias** dialog.

    You cannot change the **Alias name**.
    {: .note}

1. To add an existing index or index pattern to the alias, choose it from the **Indexes or index patterns** drop-down.

1. To remove an existing index or index pattern from the alias, select the `x` at the right of its name in the **Indexes or index patterns** box.

1. To add a new index pattern, enter the pattern in the **Indexes or index patterns** drop-down and select a point in the **Create alias** dialog to dismiss the text box.

1. Select the **Save changes** button.


## Deleting an alias

To delete an alias, perform the following steps:

1. Select the checkboxes of one or more aliases you want to delete.

1. Choose the **Actions** button.

1. Choose **Delete** from the dropdown list.

1. Enter `delete` in the confirmation dialog text box.

1. Select **Delete**.


## Refreshing an alias

Refreshing an alias makes new updates to the alias's indexes visible to search operations.

The refresh operation can be applied only to open indexes associated with the specified aliases.
{: .note}

To refresh an alias:

1. On the **Aliases** page, select the alias you want to refresh.

1. Select **Refresh** from the **Actions** dropdown list.

1. In the **Refresh aliases** dialog, select **Refresh**.


## Flushing an alias


The flush operation performs a [Lucene commit](https://lucenenet.apache.org/docs/2.9.4/html/9e5b5681-859f-8190-2a3c-2a0b364f95d8.htm), writing segments to disk and starting a new translog.

The flush operation can be applied only to open indexes associated with the specified aliases.
{: .note}

To flush an alias:


1. On the **Aliases** page, select the alias you want to flush.

1. Select **Flush** from the **Actions** dropdown list.

1. In the **Flush aliases** dialog, select **Flush**.


## Clearing an alias cache

The [clear cache operation]({{site.url}}{{site.baseurl}}/api-reference/index-apis/clear-index-cache/) can be applied only to open indexes associated with the specified aliases.

To clear caches for an alias:

1. On the **Aliases** page, select the alias for which you want to clear the cache.

1. Select **Clear cache** from the **Actions** dropdown list.

1. In the **Clear cache for aliases** dialog, select **Clear cache**.
