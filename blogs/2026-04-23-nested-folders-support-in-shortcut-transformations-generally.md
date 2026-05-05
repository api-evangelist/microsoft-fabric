---
title: "Nested folders support in shortcut transformations (Generally Available)"
url: "https://community.fabric.microsoft.com/t5/Fabric-Updates-Blogs/Nested-folders-support-in-shortcut-transformations-Generally/ba-p/5171995"
date: "Thu, 23 Apr 2026 21:00:00 GMT"
author: "preshah"
feed_url: "https://community.fabric.microsoft.com/oxcrx34285/rss/board?board.id=fbc_fabricupdatesblogs"
---
<p>Nested folders, shortcut transformations, subfolder processing, OneLake, shortcuts, Lakehouse</p>

<p>Data lakes rarely come in flat structures. In practice, data is organized across multi-level folder hierarchies, partitioned by date, region, source system, or business unit. Previously, shortcut transformations processed files at a single folder level, requiring users to set up separate transforms for each subdirectory.</p>

<p>Moving forward, <strong>nested folders support in shortcut transformations </strong>will enable recursive discovery and transformation of files across your entire directory hierarchy, automatically.</p>

<p>This builds on the recently announced <a href="https://blog.fabric.microsoft.com/blog/shortcut-transformations-and-turn-files-into-delta-tables-without-pipelines-generally-available?ft=09-2024:date" rel="noopener" target="_blank">shortcut transformations (Generally Available)</a> for structured file formats (CSV, Parquet, JSON), extending the zero-ETL model to work with hierarchical folder structures out of the box.
</p><h2>Why this matters</h2>
Consider a typical data lake layout: sales data partitioned by year, then quarter, then month, with new folders appearing as time progresses. Previously, transforming this data required targeting each leaf folder individually, or flattening your storage structure to work within the single-level constraint.<p></p>

<p>Neither approach scales well, nor both add manual overhead that shortcut transformations were designed to eliminate.</p>

<p>Nested folders support removes this limitation. You point a shortcut transformation at a top-level folder, and the system takes care of the rest, discovering files across all subdirectories, detecting changes incrementally, and applying transformations consistently across the entire hierarchy.
</p><h2>Key capabilities</h2>
Nested folders support extends shortcut transformations with capabilities designed for hierarchical data layouts.
<h3>Recursive change detection</h3>
The system automatically discovers files across all subdirectories within the target folder. When new files land in any subfolder, they are detected and processed incrementally. No manual intervention, no missed files buried three levels deep.
<h3>Automatic partition pickup</h3>
This is particularly powerful for data lakes with continuous ingestion patterns. When new partitions appear over time (for example, a new month or region folder), they are picked up automatically without requiring reconfiguration.
<h3>Directory structure preservation</h3>
The transformed output maintains the relative folder hierarchy of the source. If your source data lives in sales-data/2026/Q1/jan/transactions.csv, the transformed Delta table preserves that path structure. This ensures traceability, downstream compatibility, and logical organization of transformed data.
<h3>Safety and cycle prevention</h3>
Shortcuts nested inside the target folder are not traversed, only physical folders and files are processed. This prevents infinite recursion, cyclic dependencies, and unexpected data duplication.
<h3>Consistent transformation across all levels</h3>
The same transformation logic, delimiter settings, header configuration, and schema inference applies uniformly to every file discovered across the folder tree. One configuration covers the entire hierarchy.
<h2>Getting started</h2>
<h3>Select a top-level folder as your shortcut target</h3>
In your Lakehouse, create a new table shortcut and browse to the folder that contains your hierarchical data. Select the top-level folder rather than individual subfolders.<p></p>

<p><span class="lia-inline-image-display-wrapper"><img alt="New_shortcut_dialog_in_Microsoft_Fabric_showing_a_OneLake_folder_browser_with_a" src="https://community.fabric.microsoft.com/t5/image/serverpage/image-id/1335422i7AD0B4B1487A4CC0/image-size/large?v=v2&amp;px=999" title="new-shortcut-dialog-in-microsoft-fabric-showing-a.png" /><span class="lia-inline-image-caption">New_shortcut_dialog_in_Microsoft_Fabric_showing_a_OneLake_folder_browser_with_a</span></span></p>

<p><em>Figure: Selecting a source folder in the OneLake shortcut creation wizard in Microsoft Fabric.</em>
</p><h3>Enable subfolder processing</h3>
The "Include subfolders" option is enabled by default; the system is designed to work recursively out of the box. If you need single-level behavior for a specific shortcut, you can opt out by unchecking this option.<p></p>

<p><span class="lia-inline-image-display-wrapper"><img alt="New_Shortcut_dialog_creating_a_CSV-to-Delta_shortcut_from_nested_folders_in_OneL" src="https://community.fabric.microsoft.com/t5/image/serverpage/image-id/1335423iD3D4114EA7712D5C/image-size/large?v=v2&amp;px=999" title="new-shortcut-dialog-creating-a-csv-to-delta-shortc.png" /><span class="lia-inline-image-caption">New_Shortcut_dialog_creating_a_CSV-to-Delta_shortcut_from_nested_folders_in_OneL</span></span></p>

<p><em>Figure: Subfolder option during shortcut creation.</em>
</p><h3>Configure and create</h3>
Set your transformation options (delimiter, headers, table name) and create the shortcut. Fabric will discover all files across the folder hierarchy and begin transforming them into a Delta table.
<h2>Managing nested folder shortcuts</h2>
Shortcut properties clearly indicate whether subfolder transformation is enabled, providing clear visibility into which shortcuts are processing recursively:
<ul>
 	<li>Existing shortcuts created before this feature will show subfolder transformation as "No".</li>
 	<li>New shortcuts with subfolders enabled will show "Yes".</li>
</ul>
<span class="lia-inline-image-display-wrapper"><img alt="Fabric_Manage_Shortcut_panel_for_a_nested_folder_OneLake_shortcut_with_CSV-to-De" src="https://community.fabric.microsoft.com/t5/image/serverpage/image-id/1335424iFF9D34162C48A367/image-size/large?v=v2&amp;px=999" title="fabric-manage-shortcut-panel-for-a-nested-folder-o.png" /><span class="lia-inline-image-caption">Fabric_Manage_Shortcut_panel_for_a_nested_folder_OneLake_shortcut_with_CSV-to-De</span></span><p></p>

<p><em>Figure: Shortcut properties showing subfolder inclusion status.</em>
</p><h2>Resources</h2>
To learn more about nested folders support, configuration options, and how shortcut transformations work with hierarchical data, refer to <a href="https://learn.microsoft.com/fabric/onelake/shortcuts/transformations" rel="noopener" target="_blank">transform structured files into Delta tables.</a><p></p>

<p><strong>We would love to hear your feedback.</strong> What folder structures are you working with? What additional controls would be most valuable? Your input directly shapes what we build next. Let us know in the <a href="https://aka.ms/fabricideas" rel="noopener" target="_blank">Fabric Ideas</a> forum!</p>
