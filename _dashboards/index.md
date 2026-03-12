---
layout: default
title: OpenSearch Dashboards
nav_order: 1
has_children: true
nav_exclude: true
permalink: /dashboards/
---

# OpenSearch Dashboards

OpenSearch Dashboards is the web UI for [OpenSearch]({{site.url}}{{site.baseurl}}/getting-started/intro/). You can use OpenSearch Dashboards to perform most tasks you can do with the OpenSearch APIs. You can also create visualizations and data dashboards[^1] with OpenSearch Dashboards.

[^1]: The terminology is confusing. _OpenSearch Dashboards_ and _Dashboards_ refer to the OpenSearch UI. The term _dashboard_ (lower case) refers to a collection of visualizations that you can create in OpenSeaerch Dashboards. See the [glossary]({{site.url}}{{site.baseurl}}/glossary/index/).

## Getting started

To learn more about | Go to
:------------------- | :-----
Exploring OpenSearch Dashboards features | [OpenSearch Dashboards quickstart guide]({{site.url}}{{site.baseurl}}/dashboards/quickstart/)
Viewing a web-based, read-only OpenSearch Dashboards instance | [The OpenSearch Playground](https://playground.opensearch.org/app/home#/)
Installing and configuring an OpenSearch Dashboards instance or Docker image | [Installing OpenSearch Dashboards]({{site.url}}{{site.baseurl}}/install-and-configure/install-dashboards)<br/>and<br/>[Configuring OpenSearch Dashboards]({{site.url}}{{site.baseurl}}/install-and-configure/configuring-dashboards)

## Exploring data

To learn more about   |  Go to | Query languages used
:-------------------   | :-----                     | :-----
Exploring data quickly | [Exploring data with Discover]({{site.url}}{{site.baseurl}}/dashboards/discover/index-discover) | [Dashboard Query Language (DQL)](({{site.url}}{{site.baseurl}}/dashboards/dql/))<br/>or<br/>[Query String Query Language (Lucene)]({{site.url}}{{site.baseurl}}/query-dsl/full-text/query-string/)
Querying pipeline data | [Exploring data with Workbench]({{site.url}}{{site.baseurl}}/dashboards/query-workbench/) | [Structured Query Language (SQL)]({{site.url}}{{site.baseurl}}/sql-and-ppl/sql/)<br/>or<br/>[Piped Processing Language (PPL)]({{site.url}}{{site.baseurl}}/sql-and-ppl/ppl/)
Querying data using the API |[Running queries in the Dev Tools Console]({{site.url}}{{site.baseurl}}/dashboards/visualize/run-queries) | [Query Domain-specific Language (Query DSL)]({{site.url}}{{site.baseurl}}/query-dsl/)

## Visualizing data

To learn more about | Go to
:------------------- | :-----
Creating a visualization | [Creating visualizations]({{site.url}}{{site.baseurl}}/dashboards/visualize/viz-index)
Types of visualizations  | [Visualizations reference]({{site.url}}{{site.baseurl}}/dashboards/visualize/viz-ref)
Composing a dashboard (adding visualizations)    | [Creating dashboards]({{site.url}}{{site.baseurl}}/dashboards/dashboard)

## Managing indexes

To learn more about | Go to
:------------------- | :-----
Managing indexes | [Managing indexes in OpenSearch Dashboards]({{site.url}}{{site.baseurl}}/dashboards/im-dashboards/index)
Index policies | [Index policies in OpenSearch Dashboards]({{site.url}}{{site.baseurl}}/dashboards/im-dashboards/index-management#policies)
Managing data streams | [Data streams]({{site.url}}{{site.baseurl}}/dashboards/im-dashboards/datastreams)
Working with aliases | [Working with aliases]({{site.url}}{{site.baseurl}}/dashboards/im-dashboards/working-with-aliases)
Managing index templates | [Working with templates]({{site.url}}{{site.baseurl}}/dashboards/im-dashboards/working-with-templates)
Index patterns | [Index patterns]({{site.url}}{{site.baseurl}}/dashboards/management/index-patterns)
Rolling indexes over | [Rollover]({{site.url}}{{site.baseurl}}/dashboards/im-dashboards/rollover)
Merging indexes | [Force merge]({{site.url}}{{site.baseurl}}/dashboards/im-dashboards/forcemerge)
Backing up and recovering indexes | [Snapshot management]({{site.url}}{{site.baseurl}}/dashboards/sm-dashboards/)


## Observability

To learn more about | Go to
: --------- | :-------------
[Observability in OpenSearch Dashboards]({{site.url}}{{site.baseurl}}/observing-your-data/index/) | Observe, monitor, and secure data and improve performance across tools and workflows.


## Dashboards Management

To learn more about | Go to
: --------- | :-------------
Managing dashboards | [Dashboards Management]({{site.url}}{{site.baseurl}}/dashboards/management/management-index/)
Manging application setttings | [Manging application setttings]({{site.url}}{{site.baseurl}}/dashboards/im-dashboards/)


## Dev Tools 

To learn more about | Go to
: --------- | :-------------
[Dev Tools]({{site.url}}{{site.baseurl}}/dashboards/dev-tools/index-dev/) | Learn how to run OpenSearch queries in an integrated console.
