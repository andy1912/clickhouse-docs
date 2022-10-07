RocketBI is a self-service Business Intelligence platform that helps you quickly analyze, drag and drop to visualize Big Data, and collaborate with friends & colleagues right on your web browser.

# Usecase: Metrics & Date range controller

In this guide, you will build a dashboard in Rocket.BI with a metrics controller & a date range trigger. Then use them inside the chart to enable a dynamic report of different KPIs & DateTime view with one Dashboard. This is the dashboard:

<img src={require('./images/rocketbi_chart_1.png').default} class="image" alt="Sample Dashboard" />
<p/>

## 1. Create Controllers
 
### 1.1 Metrics:
#### Add a Tab filter chart
<img src={require('./images/rocketbi_chart_2.png').default} class="image" alt="Add Tab Filter" />
<p/>

#### Select relevant Metric fields with the desired aggregation.
<img src={require('./images/rocketbi_chart_3.png').default} class="image" alt="Create Metric Control" />
<p/>

#### Rename & Save Control to Dashboard

### 1.2 Date control:
#### Again, add a Tab filter chart

#### Select Main Date Column as a filter.
<img src={require('./images/rocketbi_chart_5.png').default} class="image" alt="Choose a field to usse as Main Date" />
<p/>

#### Add duplicate variants with different lookup ranges. For example, Year, Monthly, Daily date or Day of Week.
<img src={require('./images/rocketbi_chart_6.png').default} class="image" alt="Create Date type Control" />
<p/>

#### Rename filters & Save Control to Dashboard


## 2. Using Control in Chart

#### Add a Column chart
<img src={require('./images/rocketbi_chart_7.png').default} class="image" alt="Add Column Chart" />
<p/>

#### Select Date control as DateTime or X-Axis filter.
<img src={require('./images/rocketbi_chart_8.png').default} class="image" alt="Use Date control" />
<p/>

#### Select Metrics control as Metric fields or Y-Axis filter.
<img src={require('./images/rocketbi_chart_9.png').default} class="image" alt="Use Metrics control" />
<p/>

#### Rename & Save Chart to Dashboard


## 3. Trigger Control to change Chart view
#### Default View
<img src={require('./images/rocketbi_chart_10.png').default} class="image" alt="Default Chart" />
<p/>

#### Choose different Metric
<img src={require('./images/rocketbi_chart_9.png').default} class="image" alt="Select another Metric" />
<p/>

#### Choose different Date type
<img src={require('./images/rocketbi_chart_9.png').default} class="image" alt="Change Date presentation" />
<p/>

# Get Rocket.BI for your system

Since RocketBI is ClickHouse native and an open-source project, all you need is an already deployed ClickHouse database, using Docker and follow these 3 simple steps:
 
## 1. Installation

Prerequisites:
docker-engine 19.0+
docker-compose 2.0+
 
Get the files:
````
wget https://raw.githubusercontent.com/datainsider-co/rocket-bi/main/docker/docker-compose.yml

wget https://raw.githubusercontent.com/datainsider-co/rocket-bi/main/docker/.clickhouse.env
````

## 2. Config your ClickHouse information
 
Edit `.clickhouse.env` with your ClickHouse server's host, port, username, password and cluster name.
 
NOTE: If you're installing RocketBI on the same host with your clickhouse-server, please use `172.17.0.1` as your CLICKHOUSE_HOST instead of localhost for docker to resolve hosts correctly.
 
Start RocketBI with the command:
```
docker-compose up -d
```

## 3. Start exploring your data
 
Open the browser and go to localhost:5050 to enter the web UI.
 
Login to RocketBI with this default account:
`username: hello@gmail.com
`password: 123456

#### You will find your ClickHouse data in the tab Data Warehouse > Schemas.

#### Check if your dataset is connected in Settings > Organization Settings:
<img src={require('./images/rocketbi_config_1.png').default} class="image" alt="Data Sync Status" />
<p/>

#### Use Query Analysis to quickly explore data & do ad hoc insight finding:
<img src={require('./images/rocketbi_analyze_1.png').default} class="image" alt="Rocket.BI Chart Builder" />
<p/>

#### Or visualize your data through our Chart builder in the Dashboard tab:
<img src={require('./images/rocketbi_analyze_2.gif').default} class="image" alt="Rocket.BI Chart Builder" />
<p/>
 
# Contribute to the project:

If you use & love RocketBI, and want to provide your expertise to help enrich the product. Please go to our [RocketBI GitHub](https://github.com/datainsider-co/rocket-bi/blob/main/README.md) document to learn more about our infrastructure and how you can commit.


# Get data insights in seconds
 
This section will guide you through the simple process to quickly explore and build an insightful report with Rocket.BI
 
## 1. Explore dataset schemas

Rocket.BI will automatically discover and sync all datasets in your ClickHouse DB. You can find them in Data Warehouse tab.

Click the name of the database, you can access the Table Schema, Table Data, Measure Schema, Calculated Field, and RLS.

Measure Schema & Calculated Field
Fields created through mathematical functions & syntax will be shown here.
 
RLS - Row-level Security
Setup and check your user-attributed-based data accessibility rule here.
<img src={require('./images/rocketbi_row_level_security.png').default} class="image" alt="Create data access rule for each user group" />
<p/>


## 2. Time-saving Ad hoc Analysis with Query

Not only can you deep-dive into the raw data with SQL, but also drag-and-drop the results into different charts & graphs for a better visual perspective.
#### Write a SQL query
<img src={require('./images/rocketbi_sql_query.png').default} class="image" alt="Ad hoc Query" />
<p/>

#### Visualize the result
Click +Add chart to use the results to build a chart. A selection menu for visualization type will appear. Choose a chart to start:
<img src={require('./images/rocketbi_visualization.png').default} class="image" alt="Build advanced visualized reports" />
<p/>


## 3. Chart builders with advanced customization

In Dashboard tab, you will find your reportings there, start visualization by clicking +New
You can build unlimited dashboards & draw unlimited charts in a dashboard.

#### Create Dashboard & Add charts:
If you create a chart in an empty dashboard, hit Click here to start.
<img src={require('./images/rocketbi_create_chart_1.png').default} class="image" alt="Add First Charts" />
<p/>

If you create a chart from a filled dashboard, click Edit in the sidebar menu:
<img src={require('./images/rocketbi_create_chart_2.png').default} class="image" alt="Edit the Dashboard" />
<p/>

Then click Adding and select Add chart.
<img src={require('./images/rocketbi_create_chart_3.png').default} class="image" alt="Add New Charts" />
<p/>
 
A selection menu for visualization type will appear just like in Query Analysis.


#### Flexible Charts Configuration
In the chart builder, look at the Settings button in the top right corner
<img src={require('./images/rocketbi_chart_config_1.png').default} class="image" alt="Chart Settings" />
<p/>

In the Dashboard Edit, use the Settings icon and select Config Chart.
<img src={require('./images/rocketbi_chart_config_2.png').default} class="image" alt="Chart Configurations" />
<p/>

With each Chart type, the configuration might be different
<img src={require('./images/rocketbi_chart_config_3.png').default} class="image" alt="Configuration Options" />
<p/>


#### Powerful Dashboard Controllers
Drag to zoom in a range
<img src={require('./images/rocketbi_dashboard_action_1.png').default} class="image" alt="Zoom in your Chart data" />
<p/>

Using dynamic controller for metrics & date range to build quicker overview
<img src={require('./images/rocketbi_dashboard_action_2.png').default} class="image" alt="Dynamic Dashboard Controls" />
<p/>
