---
layout: default
title: Index rollup
parent: Managing indexes in Dashboards
has_children: false
nav_order: 70
---

## Rollup jobs

The **Rollup Jobs** section under **Index Management** allows you to create or update index rollup jobs.

To create a rollup job, perform the following steps:

1. Choose the **Create rollup job** button on the **Rollup Jobs** page under **Index Management**.
1. Set the name, source index, and target index.
1. Choose **Next**.
1. Set the timestamp field and interval type.
1. Optionally, set additional aggregations and metrics.
1. Choose **Next**.
1. Under **Schedule**, check or uncheck **Enable job by default**.
1. Set the **Continuous**, **Execution frequency**, **Rollup interval**, and **Pages per execution** settings.
1. Additionally, you can set an execution delay.
1. Choose **Next**.
1. Review the settings for the rollup job and choose **Create**.

You can also enable and disable rollup jobs by choosing the corresponding buttons on the **Rollup Jobs** page.

## Transform jobs

You can create, start, stop, and complete operations with [transform]({{site.url}}{{site.baseurl}}/im-plugin/index-transforms/transforms-apis/) jobs.

To create a transform job, perform the following steps:

1. Choose the **Create transform job** button on the **Transform Jobs** page under **Index Management**.
1. Set the name, source index, and target index.
1. Choose **Next**.
1. Select the fields to transform. From the table, select a field you want to transform by choosing **+** next to the field name.
1. Choose **Next**.
1. Check or uncheck **Job enabled by default**.
1. Set the transform execution interval and whether the schedule is continuous.
1. Optionally, set pages per execution under the **Advanced** dropdown list.
1. Choose **Next**.
1. Review the settings for the rollup job and choose **Create**.

You can also enable and disable rollup jobs by choosing the corresponding buttons on the **Transform Jobs** page.

## Long-running operation status check 

Certain index operations take additional time to complete (usually more than 30 seconds, but up to tens of minutes or hours). This is tracked in the index status column on the **Indexes** page.

You can check the status of the reindex, shrink, and split operations because they are one-time, non-recursive operations.

## Security integration

  Permission control is managed with existing [permissions]({{site.url}}{{site.baseurl}}/security-plugin/access-control/permissions/) or action groups that are enforced at the API level. There is currently no UI-level permission control. Users with permission to access the ISM plugin are able to view new pages. They can also make changes if they have permission to run the related APIs.

## Error handling

Similar to API calls, if the operation fails immediately, you will be notified with an error message. However, if it is a long-running operation, you will be notified of the failure at the time of failure, or you can check the index status on the **Indexes** page.
 