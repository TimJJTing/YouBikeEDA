# Exploring the Future of Urban Mobility: A Deep Dive into YouBike 2.0 in Taipei City

## Outline

1. Introduction
2. Dataset
3. Exploratory Data Analysis (see EDA.ipynb)
   - 3.1 Station / Grid Service Level
   - 3.2 Route and Route Popularity

## 1. Introduction

YouBike, Taiwan's leading public bicycle system, offers 24/7 point-to-point rental and return services, transforming the way residents and visitors navigate urban spaces. With the introduction of YouBike 2.0, featuring a new design for both bikes and stations, the system no longer relies on external electricity, making it more flexible and easier to deploy across the city. This project, YouBike Route Explorer, delves into the deployment strategy of YouBike 2.0 in Taipei City, empowers you to explore usage patterns, popular routes, and how these trends reflect the evolving needs of urban commuters. By preparing and analyzing dataset with this notebook and "seeing" the data with this [exploratory data visualization tool](https://github.com/TimJJTing/YouBike-Route-Explorer), we can uncover insights that could drive more efficient, accessible, and sustainable transportation solutions.

## 2. Dataset

The datasets for this project come from

- [臺北市YouBike見車率統計](https://data.taipei/dataset/detail?id=ba0dafae-043c-4730-b97e-2defd7af766c)
  - 站點ID(stop_id)
  - 站點名稱(stop_name)
  - 車柱數(capacity)
  - 經度(lng)
  - 緯度(lat)
  - 見車等級(category)
  - 點座標(geometry)
- [臺北市YouBike起訖站點統計](https://data.taipei/dataset/detail?id=c7dbdb7c-6bbd-495a-bd23-49b22defd83e)
  - 借車站點ID(on_stop_id)
  - 還車站點ID(off_stop_id)
  - 借車站點名稱(on_stop)
  - 還車站點名稱(off_stop)
  - 交易次數(sum_of_txn_times)
  - 借車站點行政區(TOWNNAME_origin)
  - 還車站點行政區(TOWNNAME_destination)
  - 建議視覺化線寬(width)
  - 線座標(geometry)
- [臺北市YouBike區域互補站點](https://data.taipei/dataset/detail?id=fe8a0ddd-6f70-4e63-92a1-a3463c790a1b)
  - times（互補人數）
  - stop_id1（站點ID1）
  - longitude1（經度）
  - latitude1（緯度）
  - stop_id2（站點ID2）
  - longitude2
  - latitude2

All datasets were originally processed in July 2023.

In this project we use
- `pandas` and `geopandas` for data cleansing and geospatial processing
- `h3` to index geospatial features into hexagonal grids for ease of further aggregation
- `seaborn` and `matplotlib` to visualize data during the EDA process
