---
title: "Improve performance for Python UDFs and complex data types in Microsoft Fabric’s Native Execution Engine"
url: "https://community.fabric.microsoft.com/t5/Fabric-Updates-Blog/Improve-performance-for-Python-UDFs-and-complex-data-types-in/ba-p/5212036"
date: "2026-06-22"
author: "Santhosh_Ravin1"
feed_url: "https://community.fabric.microsoft.com/oxcrx34285/rss/board?board.id=fbc_fabricupdatesblogs"
---
Where this matters: A concrete example For example, you have a data pipeline (extract, transform, load—ETL) that ingests JSON telemetry events, each containing nested arrays of user actions. Your pipeline uses a Python UDF to apply custom business rules—say, classifying events based on logic that doesn’t map cleanly to SQL expressions. Before NEE, this pipeline hits two performance penalties at once: The Python/Scala UDF forces serialization between the JVM and a Python worker for every batch.
