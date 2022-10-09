
RocketBI is a self-service Business Intelligence platform that helps you quickly analyze, drag and drop to visualize Big Data, and collaborate with friends & colleagues right on your web browser.

# GOAL

In this guide, you will install and build a simple dashboard using Rocket.BI.
This is the dashboard:

![rocketbi_chart_1](https://user-images.githubusercontent.com/91059979/194484388-1e74c8cd-64e0-4768-8d78-2ee7a37bba5c.png)

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

#### You will find your ClickHouse data in the tab Data Warehouse > Schemas.

#### Check if your dataset is connected in Settings > Organization Settings:

<img width="800" alt="rocketbi_config_1" src="https://user-images.githubusercontent.com/91059979/194485090-46ce0c18-00af-46af-967b-e886df93362e.png">

#### Use Query Analysis to quickly explore data & do ad hoc insight finding:

![rocketbi_analyze_1](https://user-images.githubusercontent.com/91059979/194485149-c8ca745c-2bbc-43bd-b990-f146bd08b15a.png)

#### Or visualize your data through our Chart builder in the Dashboard tab:

![rocketbi_analyze_2](https://user-images.githubusercontent.com/91059979/194485209-d1f4c308-8900-4017-a820-ad6bb9d7d8f1.gif)

## LET'S BUILD THE DASHBOARD

In Dashboard tab, you will find your reportings there, start visualization by clicking +New

<img width="400" alt="rocketbi_new_chart" src="https://user-images.githubusercontent.com/91059979/194486110-731d2fa6-85ff-4dbc-9849-487dc1ab9d16.png">

You can build **unlimited dashboards** & draw **unlimited charts** in a dashboard.

### Create the Chart Controls

#### Basic Chart Setting
If you create a chart in an empty dashboard, hit Click here to start.
<img width="800" alt="rocketbi_create_chart_1" src="https://user-images.githubusercontent.com/91059979/194486161-9a8e6fdf-b019-4602-b5a0-c63c008c96e0.png">

If you create a chart from a filled dashboard, click Edit in the sidebar menu, then click Adding and select Add chart:
<img width="400" alt="rocketbi_create_chart_2" src="https://user-images.githubusercontent.com/91059979/194486197-3d216af5-7748-4d0b-ae11-2a604b13bb44.png"> <img width="400" alt="rocketbi_create_chart_3" src="https://user-images.githubusercontent.com/91059979/194486231-452bd640-a320-4942-9a1c-7090ca1d5adf.png">

A selection menu for visualization type will appear. Find and select a Tab filter.
![rocketbi_chart_2](https://user-images.githubusercontent.com/91059979/194490118-4c876aa8-e3ff-4943-a0c4-edc8cdbc661c.png)


#### Create a Metrics Control
In the Tab filter setting, select the metric fields you want to use. Make sure to keep check on aggregation setting.
![rocketbi_chart_6](https://user-images.githubusercontent.com/91059979/194493404-dd6199bc-2faf-4a73-b72e-a6370dc490f8.png)

Rename filters & Save Control to Dashboard

<img width="400" alt="Screen Shot 2022-10-07 at 14 15 35" src="https://user-images.githubusercontent.com/91059979/194493738-c085fa53-173b-495a-b654-bffcd092b2e6.png">


#### Create a Date Type Control
Choose a Date field as Main Date column:

![rocketbi_chart_4](https://user-images.githubusercontent.com/91059979/194491853-dfde6481-3700-4636-9986-a35225b71bb0.png)

Add duplicate variants with different lookup ranges. For example, Year, Monthly, Daily date or Day of Week.

![rocketbi_chart_5](https://user-images.githubusercontent.com/91059979/194492541-f912b16a-9eb0-43fd-a905-2ce42d97e995.png)

Rename filters & Save Control to Dashboard

<img width="200" alt="Screen Shot 2022-10-07 at 14 16 04" src="https://user-images.githubusercontent.com/91059979/194494006-2285e434-3e5b-4160-9886-bc1d1e9980a7.png">

## FEATURE HIGHTLIGHT

Manager User's Attribute to custom the data accessibility to the data level

![Row-level Security](https://user-images.githubusercontent.com/91059979/194751159-fdefb0aa-8ab1-4cc2-98ce-f0828c647c69.png)


Drag & zoom in data

<img src={require('./images/rocketbi_dashboard_action_1.png').default} class="image" alt="Zoom in your Chart data" />
<p/>

Click & connect relationship to analyze from multiple dataset

![Relationship Builder](https://user-images.githubusercontent.com/91059979/194750965-9f019221-b1a9-4c72-a782-8de5ea9f99f3.png)
