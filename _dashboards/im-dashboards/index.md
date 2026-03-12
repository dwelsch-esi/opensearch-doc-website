---
layout: default
title: Managing indexes in Dashboards
nav_order: 80
has_children: true
redirect_from:
  - /dashboards/admin-ui-index/
  - /dashboards/im-dashboards/
---

# Managing indexes in OpenSearch Dashboards
Introduced 2.5
{: .label .label-purple }

Use the Index Management interface in OpenSearch Dashboards to manage common indexing and data stream operations. You can use the interface as an alternative to REST APIs or YAML configurations to create, read, update, and delete (CRUD) and map indexes, index templates, and aliases. You can also open, close, reindex, shrink, and split indexes; run index status and data validation before submitting requests; and compare changes with previously saved settings before making updates.

The interface is shown in the following image.

![Index Management user interface]({{site.url}}{{site.baseurl}}/images/dashboards/index-management-UI.png)

## Working with Index Management in OpenSearch Dashboards

This page describes how to use the Index Management interface for:

- [Viewing indexes](#viewing-indexes)
- [Searching for an index](#searching-for-an-index)
- [Creating an index](#creating-an-index)
- [Deleting an index](#deleting-an-index)
- [Modifying an index](#modifying-an-index)
- [Closing an index](#closing-an-index)
- [Opening an index](#opening-an-index)
- [Reindexing an index](#reindexing-an-index)
- [Shrinking an index](#shrinking-an-index)
- [Splitting an index](#splitting-an-index)
- [Refreshing an index](#refreshing-an-index)
- [Flushing an index](#flushing-an-index)
- [Clearing an index cache](#clearing-an-index-cache)


### Opening Index Management

1. In OpenSearch Dashboards, select **Management** > **Index Management**.

1. On the **Indexs** page, select **Index Management** > **Indexes**.

### Viewing indexes

The **Indexes** interface displays a list of existing indexes in your OpenSearch cluster. The list provides the following information:

- **Index name**: The name of the index, with a link to a detail page for that index.

- **Health**: The index health, coded as green, yellow, or red.

- **Data stream**: If the _Data stream_ toggle is on, this column indicates whether the index is a data stream.

- **Managed by policy**: Whether the index is attached to a management policy.

- **Status**: Whether the index is closed or open.

- **Total size**: The amount of storage taken up by the index on primaries and replicas.

- **Size of primaries**: The amount of storage taken up by the index on its primary.

- **Total documents**: The number of documents in the index.

- **Deleted documents**: The number of documents that have been deleted from the index.

- **Primaries**: The number of primaries containing the index.

- **Replicas**: The number of replicas containing the index.

### Searching for an index

To search for a specific index:

1. Select **Index Management** > **Indexes**.

1. (Optional) Select **Show data stream indexes** to include data streams in the index list.

1. In the **Indexes** panel, enter a search term in the **Search** text box.

    The list narrows to match the search term.


### Creating an index

To create a new index:

1. Select the **Create index** button in the upper-right corner of the **Indexes** page.

1. Enter a name in the **Index name** field.

1. (Optional) Enter one or more aliases for the index in the **Index alias** field.

1. Enter the number of primary shards for the index or accept the default.

1. Enter the number of replicas for the index or accept the default.

1. Enter the refresh interval for the index or accept the default.

1. (Optional) Use the **Index mapping** editor to map index fields or objects.

1. Select the **Create** button.

### Deleting an index

To delete an index:

Use caution when deleting indexes. This action is irreversible.
{: .warning}

1. Select the checkbox next to one or more indexes you want to delete.

1. Select the **Actions** button.

1. Choose **Delete** from the dropdown list.

1. Enter `delete` in the confirmation box.

1. Select **Delete**.

### Modifying an index

To modify the settings of an existing index:

1. Choose the name of the index you want to modify to bring up the index details page.

1. Go to the tab of the properties you want to modify: **Settings**, **Mappings**, or **Alias**.

1. In the tab, edit the properties you want to change. Some properties cannot be changed.

1. Select **Save**.

1. Repeat the last three steps to modify other property types.

## Closing an index

The [close index]({{site.url}}{{site.baseurl}}/api-reference/index-apis/close-index/) operation closes an index. Once an index is closed, you cannot add data to it or search for any data within the index.

To close an index:

1. Go to **Index Management** > **Index Management**.

1. Select the index you want to close.

1. Choose the **Actions** button.

1. Select **Close** from the dropdown list.

1. In the **Close indexes** confirmation dialog, type `close`.

1. Select the **Close** button.


### Opening an index

The [open index]({{site.url}}{{site.baseurl}}/api-reference/index-apis/open-index/) operation opens a closed index. To add or search for data within an index, the index must be open.

To open an index:

1. Go to **Index Management** > **Index Management**.

1. Select the index you want to open.

1. Choose the **Actions** button.

1. Select **Open** from the dropdown list.

1. In the **Open indexes** confirmation dialog, select the **Open** button.

1. Click `x` to dismiss the confirmation dialog.


### Reindexing an index


The [reindex]({{site.url}}{{site.baseurl}}/api-reference/document-apis/reindex/) operation copies all or a subset of documents from a source index into a destination index.

Before proceeding, check the prerequisite requirements and limitations in [reindex]({{site.url}}{{site.baseurl}}/api-reference/document-apis/reindex/).
{: .important}

To reindex an index:

1. Go to **Index Management** > **Index Management**.

1. Select the index you want to reindex.

1. Choose the **Actions** button.

1. Select **Reindex** from the dropdown list.

    The following images shows the **Reindex** page.

    <img src="{{site.url}}{{site.baseurl}}/images/admin-ui-index/reindex-expanded.png" alt="User interface showing reindex prompt">

1. On the **Reindex** page, verify that the source index is shown in **Specify source indexes or data streams**.

1. Choose to reindex all or a subset of documents in **Specify a reindex option**.

1. (Optional): If you chose to reindex a subset of documents, enter a [query DSL]({{site.url}}{{site.baseurl}}/query-dsl/) expression to select the documents that you want to reindex.

1. (Optional) In the **Configure destination** index box, choose **Create index** to create a new target index.

1. Select a target index in the **Specify a destination index or data stream** dropdown.

1. (Optional) Expand **Advanced settings** and select the advanced options you want.

1. Select the **Reindex** button.


### Shrinking an index

The [shrink]({{site.url}}{{site.baseurl}}/api-reference/index-apis/shrink-index/) index operation copies all of the data in an existing index into a new index with fewer primary shards.

To shrink an index:


1. Go to **Index Management** > **Index Management**.

1. Select the index you want to shrink.

1. Choose the **Actions** button.

1. Select **Shrink** from the dropdown list.

    The following images shows the **Shrink** page.

    <img src="{{site.url}}{{site.baseurl}}/images/admin-ui-index/shrink.png" alt="User interface showing shrink prompt">

1. On the **Shrink** page in the **Target index name** box, enter a name for the new index.

1. In the **Number of primary shards** drop-down, enter the number of primary shards for the new index.

1. In the **Number of replicas** selection box, enter the number of replicas for the new index.

1. (Optional) Select one or more aliases for the new index in **Index alias – optional** drop-down.

1. Select a target index in the **Specify a destination index or data stream** dropdown.

1. (Optional) Expand **Advanced settings** and enter a comma-separated list of advanced settings.

1. Select the **Shrink** button.

1. Dismiss the confirmation dialog.


### Splitting an index

The [split index]({{site.url}}{{site.baseurl}}/api-reference/index-apis/split/) operation splits an existing read-only index into a new index, splitting each primary shard into a number of primary shards in the new index.

1. Go to **Index Management** > **Index Management**.

1. Select the index you want to split.

1. Choose the **Actions** button.

1. Select **Split** from the dropdown list.

    The following images shows the **Shrink** page.

    <img src="{{site.url}}{{site.baseurl}}/images/admin-ui-index/split-expanded.png" alt="User interface showing split page">

1. (Optional) If the index is not read-only, the Split index page displays a warning and a **Block write operations** button. Select the button to continue.

1. On the **Split** page in the **Target index name** box, enter a name for the new index.

1. In the **Number of primary shards** drop-down, enter the number of primary shards for the new index.

1. In the **Number of replicas** selection box, enter the number of replicas for the new index.

1. (Optional) Select one or more aliases for the new index in **Index alias – optional** drop-down.

1. Select a target index in the **Specify a destination index or data stream** dropdown.

1. (Optional) Expand **Advanced settings** and enter a comma-separated list of advanced settings.

1. Select the **Split** button.

1. Dismiss the confirmation dialog.


## Refreshing an index

Refreshing an index moves new documents from memory to new segments, making them searchable. This is normally done periodically as described in [Refresh Index API]({{site.url}}{{site.baseurl}}/api-reference/index-apis/refresh/). You can force a refresh manually at any time.

Refreshing indexes is resource-intensive.
{: .important}

To force a refresh of an index:

1. Select the checkbox next to one or more indexes you want to refresh.

1. Select the **Actions** button.

1. Choose **Refresh** from the dropdown list.

### Flushing an index

The flush operation performs a [Lucene commit](https://lucenenet.apache.org/docs/2.9.4/html/9e5b5681-859f-8190-2a3c-2a0b364f95d8.htm), writing segments to disk and starting a new translog.

The flush operation can be applied only to open indexes.

To flush all indexes, select **Flush** from the **Actions** dropdown list.

To flush a single index:

1. Select the index from the **Indexes** list under **Index Management**.

Select **Flush** from the **Actions** dropdown list.

### Clearing an index cache

The [clear cache operation]({{site.url}}{{site.baseurl}}/api-reference/index-apis/clear-index-cache/) can be applied only to open indexes.
{: .note}

To clear all index caches, select **Clear cache** from the **Actions** dropdown list.

To clear a single index cache:

1. Select the index from the **Indexes** list under **Index Management**.

1. Select **Clear cache** from the **Actions** dropdown list.


## Next steps

- Go to [Index patterns]({{site.url}}{{site.baseurl}}/dashboards/management/index-patterns/) to learn how to retrieve data from multiple indexes.
- Go to [Index policies in OpenSearch Dashboards]({{site.url}}{{site.baseurl}}/dashboards/im-dashboards/index-management/) learn how to use policies to manage indexes.
- Go to [Index templates]({{site.url}}{{site.baseurl}}/dashboards/im-dashboards/working-with-templates/) to learn how to set up templates for creating indexes.
