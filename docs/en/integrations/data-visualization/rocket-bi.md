---
sidebar_label: Rocket.BI
sidebar_position: 
slug: /en/integrations/rocket-bi
keywords: [clickhouse, rocketbi, connect, integrate, ui]
description: RocketBI is a self-service Business Intelligence platform that helps you quickly analyze Big Data, do drag-n-drop visualization, and collaborate with colleagues right on your web browser.
---

<div class="adopters-table">

|Name|Logo|Category|Description|Resources|
|------|----|----------------|------------------|-------------|
|Rocket.BI|![rocket_bi](https://user-images.githubusercontent.com/91059979/194752634-99afc83d-6e1b-41e1-91d3-f8a22866b9e7.svg)|Data visualization|RocketBI is a self-service Business Intelligence platform that helps you quickly analyze Big Data, do drag-n-drop visualization, and collaborate with colleagues right on your web browser.|[Documentation](../en/integrations/rocket-bi)|
</div>


# GOAL

In this guide, you will install and build a simple dashboard using Rocket.BI.
This is the dashboard:
<img width="800" alt="github_rocketbi2" src="https://user-images.githubusercontent.com/91059979/194797668-65eabfb2-9bfb-447f-be24-846b8c797829.gif">


## INSTALL

Before we go deeper in create an advance dashboard with Rocket.BI, making sure you have rocket.bi platform on your ClickHouse server and the data is connected & up-to-date. Here are the step by step guide on the configuration:

### 1. Setting up Rocket.BI

Prerequisites:
docker-engine 19.0+
docker-compose 2.0+
 
Get the files:
````
wget https://raw.githubusercontent.com/datainsider-co/rocket-bi/main/docker/docker-compose.yml

wget https://raw.githubusercontent.com/datainsider-co/rocket-bi/main/docker/.clickhouse.env
````
### 2. Config your ClickHouse information
 
Edit `.clickhouse.env` with your ClickHouse server's host, port, username, password and cluster name.
 
NOTE: If you're installing RocketBI on the same host with your clickhouse-server, please use `172.17.0.1` as your CLICKHOUSE_HOST instead of localhost for docker to resolve hosts correctly.
 
Start RocketBI with the command:
```
docker-compose up -d
```

### 3. Start exploring your data
 
Open the browser and go to localhost:5050 to enter the web UI.
 
Login to RocketBI with this default account:
```
username: hello@gmail.com
password: 123456
```

You will find your ClickHouse data in the tab Data Warehouse > Schemas

Check if your dataset is connected in Settings > Organization Settings:

<img width="650" alt="rocketbi_config_1" src="https://user-images.githubusercontent.com/91059979/194485090-46ce0c18-00af-46af-967b-e886df93362e.png">

Use Query Analysis to quickly explore data & do ad hoc insight finding:
<img width="650" alt="Ad hoc Analysis" src="https://user-images.githubusercontent.com/91059979/194798326-4e64b2c8-d127-4ab3-ae6e-6364e6034e15.png">

Or visualize your data through Chart builder in Dashboard tab.

## LET'S BUILD THE DASHBOARD

In Dashboard, you will find your reportings, start visualization by clicking +New
You can build **unlimited dashboards** & draw **unlimited charts** in a dashboard.

<img width="800" alt="rocketbi_create_chart" src="https://user-images.githubusercontent.com/91059979/194799689-3ad88958-b7a8-4b3f-a98d-7af8b198d684.gif">


### Build the Chart Controls

#### Create a Metrics Control
In the Tab filter, select metric fields you want to use. Make sure to keep check on aggregation setting.
<img width="650" alt="rocketbi_chart_6" src="https://user-images.githubusercontent.com/91059979/194493404-dd6199bc-2faf-4a73-b72e-a6370dc490f8.png">

Rename filters & Save Control to Dashboard <img width="400" alt="Metrics Control" src="https://user-images.githubusercontent.com/91059979/194493738-c085fa53-173b-495a-b654-bffcd092b2e6.png">


#### Create a Date Type Control
Choose a Date field as Main Date column:

<img width="650" alt="rocketbi_chart_4" src="https://user-images.githubusercontent.com/91059979/194491853-dfde6481-3700-4636-9986-a35225b71bb0.png">

Add duplicate variants with different lookup ranges. For example, Year, Monthly, Daily date or Day of Week.

<img width="650" alt="rocketbi_chart_5" src="https://user-images.githubusercontent.com/91059979/194492541-f912b16a-9eb0-43fd-a905-2ce42d97e995.png">

Rename filters & Save Control to Dashboard

<img width="200" alt="Date Range Control" src="https://user-images.githubusercontent.com/91059979/194494006-2285e434-3e5b-4160-9886-bc1d1e9980a7.png">


## FEATURE HIGHTLIGHT

Manager User's Attribute to custom the data accessibility to the data level

<img width="650" alt="Row-level Security" src="https://user-images.githubusercontent.com/91059979/194751159-fdefb0aa-8ab1-4cc2-98ce-f0828c647c69.png">


Calculated & Measurement Fields in Chart builder to create a dynamic view of data

<img width="650" alt="calculate-measurement-field" src="https://user-images.githubusercontent.com/91059979/194797687-d3fd3b8c-5398-4d4e-af0c-864b759096b7.png">


Click & connect relationship frome multiple tables, and do cross sources analysis

<img width="650" alt="Relationship Builder" src="https://user-images.githubusercontent.com/91059979/194750965-9f019221-b1a9-4c72-a782-8de5ea9f99f3.png">

