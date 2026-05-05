---
title: "Bring your Dremio data into OneLake (Preview)"
url: "https://community.fabric.microsoft.com/t5/Fabric-Updates-Blogs/Bring-your-Dremio-data-into-OneLake-Preview/ba-p/5171986"
date: "Mon, 27 Apr 2026 19:00:00 GMT"
author: "Matthew_Hicks"
feed_url: "https://community.fabric.microsoft.com/oxcrx34285/rss/board?board.id=fbc_fabricupdatesblogs"
---
<p>Starting today, Microsoft Fabric customers who use Dremio's Agentic Lakehouse Platform can seamlessly bring their Dremio-managed data into Microsoft OneLake, without data duplication, unlocking the full suite of Fabric workloads and integrations.</p>

<p><span class="lia-inline-image-display-wrapper"><img alt="Screenshot_of_the_Microsoft_Fabric_interface_showing_the_New_item_menu_with_four" src="https://community.fabric.microsoft.com/t5/image/serverpage/image-id/1335386i2231EEF6E3006255/image-size/large?v=v2&amp;px=999" title="screenshot-of-the-microsoft-fabric-interface-showi.png" /><span class="lia-inline-image-caption">Screenshot_of_the_Microsoft_Fabric_interface_showing_the_New_item_menu_with_four</span></span></p>

<p><em>Figure: Creating a new Mirrored Dremio catalog item in Fabric.</em>
</p><h2>Bringing Dremio data into Fabric — simplified</h2>
Many organizations rely on Dremio as their lakehouse platform, managing large-scale Iceberg tables across cloud storage. Both OneLake and Dremio are committed to leveraging the Apache Iceberg open standard, and the new <strong>Mirrored Dremio catalog item</strong> makes it easy to connect Fabric to your Dremio environment. Simply select the tables you want, and have them appear in OneLake automatically; no data movement or ETL pipelines required. Under the hood, it uses <strong>shortcuts</strong>&nbsp;for a&nbsp;<strong>zero-copy</strong>&nbsp;approach: your data stays where it is, and Fabric creates metadata references that make it accessible across the platform.<p></p>

<p>How it works:
<ul>
 	<li><strong>Connect: </strong>Create or select a connection to your Dremio Iceberg REST Catalog endpoint. Dremio supports credential vending, so Fabric can securely access your data without additional storage credentials.</li>
 	<li><strong>Select:</strong>&nbsp;Browse your Dremio namespaces and choose which tables to mirror. You can optionally have new tables automatically included as they're added in Dremio.</li>
 	<li><strong>Mirror: </strong>&nbsp;Fabric mirrors the catalog metadata and creates shortcuts to your data in OneLake. Tables are available within seconds, and an ongoing sync keeps everything up to date, reflecting changes automatically.</li>
</ul>
No data copying. No pipelines to build. No infrastructure to manage.
</p><h2>Getting started</h2>
It only takes a few simple steps to <a href="http://aka.ms/OneLakeMirroredCatalogDocs/Dremio" rel="noopener" target="_blank">get started</a>:
<ol>
 	<li>Open your Fabric workspace and select&nbsp;<strong>New item</strong>.</li>
 	<li>Choose&nbsp;<strong>Mirrored Dremio catalog</strong>.</li>
 	<li>Create your Dremio connection, signing in or entering your Personal Access Token (PAT).</li>
 	<li>Select the namespaces and tables you'd like to mirror into Fabric.</li>
 	<li>Start mirroring! Your Dremio tables will appear in OneLake within seconds.</li>
</ol>
From there, open the SQL analytics endpoint and start querying your data. Your Dremio data is ready to use across Fabric!
<h2>What's next</h2>
This is just the beginning for catalog mirroring in Fabric. The mirrored Dremio catalog is part of a broader initiative to support a wide range of Iceberg catalog sources, with additional services coming in the months ahead. We're also working on features like on-premises gateway connectivity to handle cases where your network connectivity may be restricted.
<h2>We want your feedback</h2>
We’d love to hear about your experience with this feature. Share your feedback and request features through the <a href="http://aka.ms/fabricideas" rel="noopener" target="_blank">Fabric Ideas site</a>.<p></p>

<p><a href="http://aka.ms/OneLakeMirroredCatalogDocs/Dremio" rel="noopener" target="_blank">Try the mirrored Dremio catalog today</a>, and bring your Dremio data into the full power of Microsoft Fabric — with zero copies, zero pipelines, and zero hassle.</p>
