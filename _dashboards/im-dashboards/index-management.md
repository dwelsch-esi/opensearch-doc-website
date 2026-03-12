---
layout: default
title: Index policies in OpenSearch Dashboards
parent: Managing indexes in Dashboards
has_children: false
nav_order: 16
redirect_from:
  - /dashboards/admin-ui-index/index-management/
---

# Index policies in OpenSearch Dashboards
Introduced 2.5
{: .label .label-purple }

In **Index Management**, you can perform the operations available in the [Index API]({{site.url}}{{site.baseurl}}/api-reference/index-apis/index/), including automating index management using policies as described in [Index policies]({{site.url}}{{site.baseurl}}/im-plugin/ism/index/).

## Index policies

[Policies]({{site.url}}{{site.baseurl}}/im-plugin/ism/policies/) are configurations that define the possible states of an index, the actions to perform when an index enters a given state, and the conditions that must be met to transition between states. You can think of policy as a state machine that you can apply to one or more indexes.

1. **States**: You define the states of an index. For example, you might define the states `hot`, `warm`, or `delete`. See [States]({{site.url}}{{site.baseurl}}/im-plugin/ism/policies/#states).
1. **Actions**: You specify actions to be triggered when an index enters a given state, such as performing a rollover. See [Actions]({{site.url}}{{site.baseurl}}/im-plugin/ism/policies/#actions).
1. **Transitions**: These are conditions that must be met for an index to move to a new state. For example, move indexes that are more than 8 weeks old to the `delete` state. See [Transitions]({{site.url}}{{site.baseurl}}/im-plugin/ism/policies/#transitions).

For example, if you analyze time-series data, you likely want to periodically perform certain operations on older indexes, such as reducing replica count or deleting them. You can use **Index policies** to automate these periodic administrative operations by triggering them based on changes in the index age, index size, or number of documents. You can add actions that also send notification messages.

You have complete flexibility in designing your policies. You can create any number of states. For any state, you can specify any number of actions and transition to any other state.


## Creating an index

You can create an index by using a document as a base, or create an empty index for later use. See [Creating an index]({{site.url}}{{site.baseurl}}/dashboards/im-dashboards/index/#creating-an-index).


## Applying a policy

Applying a policy is attaching a policy to an index.

To attach a policy to an index:

1. Under **Index Management**, choose **Indexes**.

1. Select one or more indexes to which you want to attach your policy.

1. Choose **Actions** > **Apply policy**.

1. From the **Apply policy** dialog, select the policy you want to apply.

    <img src="{{site.url}}{{site.baseurl}}/images/admin-ui-index/apply-policy.PNG" alt="User interface showing apply policy prompt">

    View the preview of your policy.

1. (Optional): Specify a rollover alias if your policy includes a rollover operation. The alias must already exist. For more information about the rollover operation, see [rollover]({{site.url}}{{site.baseurl}}/im-plugin/ism/policies#rollover).

1. Choose the **Apply** button.

    After you attach a policy to an index, Index State Management (ISM) creates a job that runs every 5 minutes by default to perform policy actions, check conditions, and transition the index into different states. To change the default time interval for this job, see [Settings]({{site.url}}{{site.baseurl}}/im-plugin/ism/settings/).

Policy jobs don't run if the cluster state is red.
{: .note}


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
 