---
title: "Simplify Real-Time Pipelines with the Fabric Eventstreams SQL Operator (Generally Available)"
url: "https://community.fabric.microsoft.com/t5/Fabric-Updates-Blogs/Simplify-Real-Time-Pipelines-with-the-Fabric-Eventstreams-SQL/ba-p/5171983"
date: "Tue, 28 Apr 2026 16:00:00 GMT"
author: "vashriva"
feed_url: "https://community.fabric.microsoft.com/oxcrx34285/rss/board?board.id=fbc_fabricupdatesblogs"
---
<p>The SQL operator was first introduced in preview to give customers an early look at a code‑first transformation experience in Fabric Eventstreams. During preview, customers used the SQL operator to simplify real-time pipelines, consolidate transformation logic, and unlock advanced scenarios using familiar SQL semantics. Feedback from this phase directly shaped the GA release—driving improvements across multi‑destination support, event‑time processing, testing capabilities, and overall production readiness.</p>

<p>Building on this preview momentum, we’ve reached the next milestone for <strong>SQL operator </strong>in Fabric Eventstreams, a powerful, code‑first way to transform and route data across Fabric’s Real-Time Intelligence experiences. This complements Eventstream’s no-code capabilities, giving engineers the flexibility to choose the right abstraction for their scenarios.</p>

<p>With this release, you can define transformation and routing logic <strong>once</strong> using familiar SQL semantics and seamlessly deliver streaming results to <strong>multiple destinations in parallel</strong>—all from a single operator.
</p><h2>What’s new</h2>
The SQL operator is now production‑ready with support for:<p></p>

<p><strong>Multiple destinations from a single SQL operator</strong> - Fan out processed events simultaneously to Eventhouse, Lakehouse, Activator, or downstream Eventstreams—without duplicating pipelines.</p>

<p><span class="lia-inline-image-display-wrapper"><img alt="Screenshot_of_an_eventstream_toplogy_depicting_a_EcommerceOrderEvents_custom_end" src="https://community.fabric.microsoft.com/t5/image/serverpage/image-id/1335381i0432934DF0B48DE7/image-size/large?v=v2&amp;px=999" title="screenshot-of-an-eventstream-toplogy-depicting-a-e.png" /><span class="lia-inline-image-caption">Screenshot_of_an_eventstream_toplogy_depicting_a_EcommerceOrderEvents_custom_end</span></span></p>

<p><em>Figure: Eventstream topology using SQL operator writing to multiple outputs.</em></p>

<p><strong>Built‑in testing experience</strong> - Validate transformations for individual outputs before publishing, making it easier to author and debug complex streaming logic.</p>

<p><span class="lia-inline-image-display-wrapper"><img alt="Screenshot_of_a_code_editor_displaying_a_SQL_query_designed_to_read_and_analyze" src="https://community.fabric.microsoft.com/t5/image/serverpage/image-id/1335383i78AC90D1866D82BB/image-size/large?v=v2&amp;px=999" title="screenshot-of-a-code-editor-displaying-a-sql-query.png" /><span class="lia-inline-image-caption">Screenshot_of_a_code_editor_displaying_a_SQL_query_designed_to_read_and_analyze</span></span></p>

<p><em>Figure: An updated explorer and test results design for multiple outputs.</em></p>

<p><strong>Event‑time processing</strong> - Process events based on event timestamps in the payload, with built‑in controls for handling late and out‑of‑order data.</p>

<p><strong><span class="lia-inline-image-display-wrapper"><img alt="Screenshot_of_an_eventstream_in_edit_mode_that_has_a_customer_endpoint_source_an" src="https://community.fabric.microsoft.com/t5/image/serverpage/image-id/1335385i9328196E4E698D41/image-size/large?v=v2&amp;px=999" title="screenshot-of-an-eventstream-in-edit-mode-that-has.png" /><span class="lia-inline-image-caption">Screenshot_of_an_eventstream_in_edit_mode_that_has_a_customer_endpoint_source_an</span></span></strong></p>

<p><em>Figure: New advanced settings to configure late arrival and out of order threshold.</em>
</p><h2>Why this matters</h2>
In enterprise data platforms, multiple systems like analytics, alerting, workflows, storage etc. depend upon the output of real-time pipelines. Previously, serving multiple such downstream consumers often led to more complex topologies or scattered transformation logic.<p></p>

<p>With the SQL operator in Fabric Eventstreams, you can:
<ul>
 	<li>Centralize transformation and routing logic in one place.</li>
 	<li>Reduce pipeline complexity and operational overhead.</li>
 	<li>Iterate faster with confidence using built‑in testing.</li>
 	<li>Scale real-time architectures without sacrificing clarity or performance.</li>
 	<li>Handle late arrival and out-of-order events with ease.</li>
</ul>
This milestone brings the proven SQL query model of Azure Stream Analytics directly into Fabric’s unified Real-Time Intelligence experience.
</p><h2>Built for Real-Time Intelligence scenarios</h2>
From IoT monitoring and real-time dashboards to alerting and historical analysis, the SQL operator enables a wide range of real-time scenarios—using one lightweight, maintainable transformation node.<p></p>

<p>You decide what data each destination receives, while Fabric handles the parallel delivery at scale.
</p><h2>Get started today</h2>
Explore these resources to learn more and start building:
<ul>
 	<li><a href="https://learn.microsoft.com/fabric/real-time-intelligence/event-streams/overview?tabs=enhancedcapabilities" rel="noopener" target="_blank">Microsoft Fabric Eventstreams Overview</a></li>
 	<li><a href="https://learn.microsoft.com/fabric/real-time-intelligence/event-streams/process-events-using-sql-code-editor" rel="noopener" target="_blank">Process Events Using a SQL Operator</a></li>
 	<li><a href="https://blog.fabric.microsoft.com/blog/from-clicks-to-code-sql-operator-now-in-public-preview-under-fabric-eventstream?ft=All" rel="noopener" target="_blank">From Clicks to Code: SQL Operator under Fabric Eventstream</a></li>
</ul>
We can’t wait to see how you use the SQL operator to simplify real-time pipelines and unlock new streaming scenarios in Fabric.
<h2>We’d love your feedback!</h2>
If you find this blog helpful, please give it a thumbs up!<p></p>

<p>We would love to hear what real-time scenarios you’re exploring and what topics you’d like us to cover in future posts. Drop us a comment or reach out to us at&nbsp;<a href="mailto:askeventstreams@microsoft.com" rel="noopener" target="_blank">askeventstreams@microsoft.com</a></p>

<p>Have new feature ideas? Submit them at&nbsp;<a href="https://community.fabric.microsoft.com/t5/Fabric-Ideas/idb-p/fbc_ideas" rel="noopener" target="_blank">Fabric Ideas – Microsoft Fabric Community</a></p>
