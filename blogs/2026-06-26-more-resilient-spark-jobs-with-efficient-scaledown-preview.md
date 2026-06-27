---
title: "More resilient Spark jobs with Efficient Scaledown (Preview)"
url: "https://community.fabric.microsoft.com/t5/Fabric-Updates-Blog/More-resilient-Spark-jobs-with-Efficient-Scaledown-Preview/ba-p/5212071"
date: "2026-06-26"
author: "Santhosh_Ravin1"
feed_url: "https://community.fabric.microsoft.com/oxcrx34285/rss/board?board.id=fbc_fabricupdatesblogs"
---
Running large-scale data engineering workloads in Apache Spark often means dealing with expensive shuffle operations. Shuffle is one of the most resource-intensive operations that Spark runs on most, if not all, jobs. When executors holding shuffle data are removed during scale-down, Spark must re-execute entire stages—causing task retries, wasted compute, and unpredictable job runtimes.
