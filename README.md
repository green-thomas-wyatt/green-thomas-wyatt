# 🗺️ Geospatial Franchise Site Selection & Ranking Model
<div align="center">
[![Python](https://img.shields.io/badge/Python-3.9%2B-blue.svg?logo=python&logoColor=white)](https://www.python.org/)
[![Apache Spark](https://img.shields.io/badge/Apache%20Spark-3.x-orange.svg?logo=apachespark&logoColor=white)](https://spark.apache.org/)
[![PySpark](https://img.shields.io/badge/PySpark-Enabled-E25A1C.svg?logo=apachespark&logoColor=white)](https://spark.apache.org/docs/latest/api/python/)
[![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-1.2%2B-F7931E.svg?logo=scikit-learn&logoColor=white)](https://scikit-learn.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
*An end-to-end Big Data geospatial intelligence pipeline and machine learning ranking engine to forecast commercial viability and optimize site selection for fast-food restaurant franchises.*
</div>
---
## 📌 Executive Summary
Selecting optimal brick-and-mortar franchise locations is a high-stakes, multi-million dollar capital allocation decision. Traditional site selection relies on isolated demographic reports or static traffic surveys, failing to account for nonlinear interactions between hyper-local competitor saturation, drive-through infrastructure, consumer purchasing power, and historical customer sentiment.
This project delivers an automated **Big Data geospatial ranking pipeline** built on **Apache Spark (PySpark)** and **Random Forest regression**. By fusing multi-source heterogeneous datasets across millions of records—including **US Census demographic tables**, **economic census reports**, **Yelp commercial performance data**, and **OpenStreetMap (OSM) road/amenity layers**—the system generates a normalized **Location Viability Index (Success Score)** for any target U.S. ZIP code or coordinate quadrant.
---
## 🏗️ Architecture & Data Pipeline
```mermaid
flowchart TD
    subgraph Ingestion["1. Multi-Source Ingestion"]
        Yelp["Yelp Academic Dataset\n(JSON: Stars, Reviews, Categories)"]
        CensusDemo["US Census ACS DP05\n(CSV: Total Pop, Age Bands)"]
        CensusEcon["US Census ACS DP03\n(CSV: Median Household Income)"]
        OSM["OpenStreetMap\n(CSV/XML: Nodes, Drive-Thrus, Amenities)"]

