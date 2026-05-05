---
title: "Resource instance rules for OneLake in Microsoft Fabric (Preview)"
url: "https://community.fabric.microsoft.com/t5/Fabric-Updates-Blogs/Resource-instance-rules-for-OneLake-in-Microsoft-Fabric-Preview/ba-p/5171998"
date: "Thu, 23 Apr 2026 17:30:00 GMT"
author: "HARMEETGILL"
feed_url: "https://community.fabric.microsoft.com/oxcrx34285/rss/board?board.id=fbc_fabricupdatesblogs"
---
<p>As enterprises adopt OneLake as their unified data lake for analytics, securing how external services access data in OneLake becomes increasingly important—especially in environments where public internet access must be tightly controlled.</p>

<p>Today, we’re introducing resource instance rules for OneLake in preview. This new capability allows workspace admins to explicitly allow inbound access from trusted Azure resource instances, without relying on IP allowlists or requiring private networking in every scenario.</p>

<p>Resource instance rules provide a resource‑identity-based inbound access model for OneLake, designed specifically for secure service‑to‑service access from trusted Azure resource instances.
</p><h2>What are resource instance rules?</h2>
Resource instance rules allow a Fabric workspace admin to define an allowlist of trusted Azure resource instances that are permitted to access the workspace’s OneLake data. Access over public endpoint is allowed only for requests originating from approved Azure resource identities<strong>.</strong><p></p>

<p>Resource Instance Rules can coexist with Private Link and IP firewall rules, allowing customers to combine identity‑based and network‑based controls based on their architecture.</p>

<p><strong><span class="lia-inline-image-display-wrapper"><img alt="The_image_depicts_a_configuration_interface_in_Workspace_settings_offering_optio" src="https://community.fabric.microsoft.com/t5/image/serverpage/image-id/1335425i4881BAB50AC764B7/image-size/large?v=v2&amp;px=999" title="the-image-depicts-a-configuration-interface-in-wo.jpeg" /><span class="lia-inline-image-caption">The_image_depicts_a_configuration_interface_in_Workspace_settings_offering_optio</span></span></strong></p>

<p><em>Figure: Workspace settings to add trusted resource instances.</em>
</p><h2>Why Resource Instance Rules for OneLake?</h2>
OneLake already integrates with Fabric’s robust security capabilities, including Private Link, IP firewall rules, and identity‑based access controls. However, customers integrating Azure services with OneLake often encounter challenges such as dynamic or unknown outbound IP addresses from managed Azure services, the operational complexity of maintaining IP‑based allowlists, and scenarios where private connectivity is not practical for every service.<p></p>

<p>Resource Instance Rules address these challenges by allowing access to OneLake to be restricted based on Azure resource identity, rather than network location.</p>

<p>With resource instance rules, customers can block public access to OneLake while still enabling access from explicitly trusted Azure resource instances, with controls enforced at the network layer before data permissions are evaluated. This results in a more precise and manageable security model for OneLake access.
</p><h2>How to get started with resource instance rules</h2>
Tenant admin must enable&nbsp;<strong>Configure workspace-level IP firewall rules and trusted resource instances</strong>&nbsp;in the Fabric admin portal.
<h3>As a Fabric workspace admin</h3>
<ol>
 	<li>Navigate to&nbsp;<strong>Workspace Settings</strong>&nbsp;in the target workspace and select&nbsp;<strong>Allow Connections from Selected Networks and Workspace Private Links</strong>.</li>
 	<li>Select&nbsp;<strong>Edit</strong>&nbsp;under <strong>Allow Inbound trusted resources (Preview)</strong>.</li>
 	<li>Add one or more Azure resource instance ARM IDs as trusted resources and save.</li>
</ol>
When a request attempts to access OneLake over a public endpoint, it validates the calling resource’s identity against the configured allowlist and allows or blocks the request accordingly.
<h2>Try resource instance rules for OneLake today</h2>
Resource instance rules give you a new way to secure OneLake by trusting Azure resource identities instead of network locations, making it easier to integrate managed Azure services while keeping public access locked down. By combining resource instance rules with existing protections like Private Link and IP firewall rules, you can apply the right level of network security for each OneLake scenario.<p></p>

<p>If you’re looking to enable secure service‑to‑service access to OneLake while maintaining strong network controls, we encourage you to try resource instance rules and share your feedback.</p>

<p>Refer to <a href="https://go.microsoft.com/fwlink/?LinkId=2355227" rel="noopener" target="_blank">Resource Instance rules for Inbound access</a> to learn more.</p>
