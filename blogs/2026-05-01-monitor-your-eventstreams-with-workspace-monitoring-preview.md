---
title: "Monitor your Eventstreams with workspace monitoring (Preview)"
url: "https://community.fabric.microsoft.com/t5/Fabric-Updates-Blogs/Monitor-your-Eventstreams-with-workspace-monitoring-Preview/ba-p/5161116"
date: "Fri, 01 May 2026 21:20:19 GMT"
author: "anboisve"
feed_url: "https://community.fabric.microsoft.com/oxcrx34285/rss/board?board.id=fbc_fabricupdatesblogs"
---
<p>Do you ever wonder how much data volume is flowing in and out of your Eventstream? Or wish you could query the health or errors in one place without selecting each Eventstream component? Now you can.</p>
<p>Eventstream observability through Workspace Monitoring provides monitoring to your streaming pipelines with a single toggle and minimal configuration. Simply enable Workspace Monitoring in your workspace settings, and three purpose-built tables are automatically created in your monitoring Eventhouse — no code, minimal setup, and no managing infrastructure.</p>
<p></p>
<p>In a few steps, you can start collecting health, performance, and error data from every Eventstream in your workspace — all queryable with KQL in a monitoring Eventhouse that Fabric creates and manages for you.</p>
<p><span class="lia-inline-image-display-wrapper lia-image-align-inline"><img alt="The_monitoring_Eventhouse_database_expanded_in_the_database_explorer_showing_the" src="https://community.fabric.microsoft.com/t5/image/serverpage/image-id/1335352i0780A308FBD8764A/image-size/large?v=v2&amp;px=999" title="the-monitoring-eventhouse-database-expanded-in-the.png" /><span class="lia-inline-image-caption">The_monitoring_Eventhouse_database_expanded_in_the_database_explorer_showing_the</span></span></p>
<p><em>Figure: High-level overview image showing the monitoring Eventhouse with the three Eventstream tables.</em></p>
<h2>Why this matters</h2>
<p>Eventstreams are often at the heart of real-time data pipelines. They connect sources to destinations, apply transformations, and keep data flowing. But streaming pipelines are only as reliable as your ability to see what’s happening inside them.</p>
<p>&nbsp;</p>
<p>Capabilities with Eventstream workspace monitoring:</p>
<ul>
<li>See every node’s status — running, paused, failed, or creating — across all Eventstreams in a workspace.</li>
<li>Track data volumes over time — incoming messages, outgoing messages, bytes in, bytes out — with per-minute granularity.</li>
<li>Spot processing bottlenecks before they become outages — watermark delay and backlogged event counts tell you when processing is falling behind.</li>
<li>Identify error patterns — runtime errors, deserialization failures, and data conversion issues, all broken down by type and time window.</li>
<li>Build custom KQL queries, dashboards, and alerts on top of the monitoring data — using the same Eventhouse and KQL experience you already know.</li>
</ul>
<p>&nbsp;</p>
<h2>What’s included in Preview</h2>
<p>When you enable workspace monitoring, Fabric automatically creates three Eventstream tables in your monitoring Eventhouse database:</p>
<h3>EventStreamNodeStatus</h3>
<p>Tracks the health of every node in your Eventstream — sources, destinations, default streams, and derived streams. Each row tells you: is this node running? When was it last checked? What type of node is it?</p>
<p>&nbsp;</p>
<p>Node status is updated approximately every <strong>six</strong> hours, giving you a historical record of node health over time.</p>
<h3>EventStreamMetrics</h3>
<p>Captures data flow metrics updated every minute. This is where you go to answer the big questions: How much data is flowing? Is processing keeping up? Where’s the bottleneck?</p>
<p>&nbsp;</p>
<p>Key metrics include:</p>
<ul>
<li><strong>Incoming/Outgoing Messages and Bytes</strong> — Volume flowing through your streams.</li>
<li><strong>Watermark Delay</strong> — How far behind processing is from the latest event. A rising delay is an early warning sign.</li>
<li><strong>Backlogged Input Events</strong> — Events waiting to be processed. High backlogs mean your processing capacity needs attention.</li>
<li><strong>Input and Output Events</strong> — Event counts at the processor level, so you can verify data is making it all the way through.</li>
</ul>
<p>&nbsp;</p>
<h3>EventStreamErrorMetrics</h3>
<p>Tracks error counts by type, updated every minute. Instead of guessing what went wrong, you can see exactly how many runtime errors, deserialization errors, and data conversion errors occurred — and when.</p>
<p>&nbsp;</p>
<p>For example, a spike in deserialization errors usually means the data format being sent doesn’t match what your Eventstream expects — a common issue when upstream systems change their schema without notice.</p>
<h2>Get started in minutes</h2>
<p>Setting up monitoring takes less than a minute:</p>
<p>&nbsp;</p>
<p>1. Open your workspace and go to Workspace settings.</p>
<p>2. Select Monitoring in the left navigation.</p>
<p>3. Select + Eventhouse — Fabric creates the monitoring database automatically.</p>
<p>4. Open the monitoring Eventhouse and start querying your Eventstream tables.</p>
<p>That’s it. No configuration, no SDK, no code.</p>
<p><span class="lia-inline-image-display-wrapper lia-image-align-inline"><img alt="Workspace_settings_panel_with_the_Monitoring_section_selected_in_the_left_naviga" src="https://community.fabric.microsoft.com/t5/image/serverpage/image-id/1335354iB6CE323019404935/image-size/large?v=v2&amp;px=999" title="workspace-settings-panel-with-the-monitoring-secti.png" /><span class="lia-inline-image-caption">Workspace_settings_panel_with_the_Monitoring_section_selected_in_the_left_naviga</span></span></p>
<p><em>Figure: The Workspace settings &gt; Monitoring panel showing the + Eventhouse button.</em></p>
<h2>Additional step for existing Eventstreams</h2>
<p>If you enable monitoring in a workspace that already has Eventstreams, those existing Eventstreams need to be <strong>republished once</strong> for monitoring data to start flowing. This is because the monitoring configuration is applied at publish time.</p>
<p>&nbsp;</p>
<p>Open the existing Eventstream, make a small edit (add and remove a node, for example), and select Publish. New Eventstreams created after you enable monitoring will work automatically — no extra steps needed.</p>
<h2>What’s next</h2>
<p>This is the start. This preview includes metrics, error counts, and node status—providing a foundation for understanding your Eventstreams. Future releases will add:</p>
<ul>
<li>Diagnostic logs — detailed error messages with root cause and suggested actions, so you can troubleshoot without opening a support ticket.</li>
<li>More frequent node status updates — to close the gap between current 6-hour emissions and real-time awareness.</li>
<li>Additional metrics — based on your feedback and real-world usage patterns.</li>
</ul>
<h2>Try it today</h2>
<p>1. Enable workspace monitoring in your workspace settings.</p>
<p>&nbsp;</p>
<p>2. Open the monitoring Eventhouse and explore the Eventstream tables.</p>
<p>3. Run a few queries and see what your data is telling you.</p>
<p>We’d love to hear what you think. Share your feedback through the <a href="https://community.fabric.microsoft.com/" rel="noopener" target="_blank">Fabric community</a>, <a href="https://community.fabric.microsoft.com/t5/Fabric-Ideas/idb-p/fbc_ideas" rel="noopener" target="_blank">Fabric Ideas</a>, or directly with our team (nrtpmteam@microsoft.com). Your input shapes what we build next.</p>
<h2>Learn more</h2>
<ul>
<li><a href="https://aka.ms/Eventstream-Observability" rel="noopener" target="_blank">Eventstream Observability</a></li>
<li><a href="https://learn.microsoft.com/fabric/real-time-intelligence/event-streams/overview?tabs=enhancedcapabilities" rel="noopener" target="_blank">Eventstreams Overview</a></li>
<li><a href="https://learn.microsoft.com/fabric/fundamentals/workspace-monitoring-overview" rel="noopener" target="_blank">Workspace Monitoring Overview</a></li>
<li><a href="https://learn.microsoft.com/fabric/fundamentals/enable-workspace-monitoring" rel="noopener" target="_blank">Enable Workspace Monitoring — Step-by-Step Setup Guide</a></li>
<li><a href="https://learn.microsoft.com/kusto/query/?view=microsoft-fabric" rel="noopener" target="_blank">Kusto Query Language (KQL) Overview — Learn the Query Language</a></li>
</ul>
<p>&nbsp;</p>
