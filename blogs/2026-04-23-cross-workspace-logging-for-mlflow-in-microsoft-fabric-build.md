---
title: "Cross-workspace logging for MLflow in Microsoft Fabric: Build MLOps workflows with confidence (Generally Available)"
url: "https://community.fabric.microsoft.com/t5/Fabric-Updates-Blogs/Cross-workspace-logging-for-MLflow-in-Microsoft-Fabric-Build/ba-p/5172000"
date: "Thu, 23 Apr 2026 17:00:00 GMT"
author: "ruxu"
feed_url: "https://community.fabric.microsoft.com/oxcrx34285/rss/board?board.id=fbc_fabricupdatesblogs"
---
<p>Machine learning teams need more than a great model — they need a reliable way to move that model from experimentation to production. Cross-workspace logging for MLflow in Microsoft Fabric, is a capability that enables you to build end-to-end MLOps workflows using the standard MLflow APIs you already know.</p>

<p><span class="lia-inline-image-display-wrapper"><img alt="Log_ML_models_from_Databricks_to_Fabric" src="https://community.fabric.microsoft.com/t5/image/serverpage/image-id/1335426iF60668F10E01BC2B/image-size/large?v=v2&amp;px=999" title="log-ml-models-from-databricks-to-fabric-.gif" /><span class="lia-inline-image-caption">Log_ML_models_from_Databricks_to_Fabric</span></span></p>

<p><em>Figure: Animated gif of Log ML models from Databricks to Fabric.</em>
</p><h2>The challenge: Bridging the gap between experimentation and production</h2>
If you've ever trained a model in a development notebook and then struggled to get it safely into production, you're not alone. Most ML teams face a common set of pain points:
<ul>
 	<li><strong>No environment separation</strong> -Experiments, validated models, and production models all live in the same workspace, making it hard to enforce quality gates or maintain audit trails.</li>
</ul>
<strong>No way to move ML artifacts between workspaces -</strong> Before cross-workspace logging, Fabric had no export/import capability for ML experiments and models. The only way to get a model into another workspace was to sync the notebook code and training data, then retrain the model from scratch in the target workspace — a time-consuming, error-prone process that wasted compute and introduced reproducibility risk.
<ul>
 	<li><strong>Scattered ML assets -</strong> Teams training models in Azure Databricks, Azure Machine Learning, or local environments have no easy way to consolidate those assets into Fabric for unified governance and deployment.</li>
</ul>
Cross-workspace logging solves these problems by letting you log MLflow experiments and models to any Fabric workspace — from any environment.
<h2>What's new</h2>
Cross-workspace logging works through the synapseml-mlflow package, which provides a Fabric-compatible MLflow tracking plugin. The core idea is simple: set the MLFLOW_TRACKING_URI* to point at your target workspace and use standard MLflow commands. Your experiments, metrics, parameters, and registered models land in the workspace you choose — not just the one you're running in.<br />
<pre>import os<p></p>

<p>target_workspace_id = "&lt;your-target-workspace-id&gt;"</p>

<p>os.environ["MLFLOW_TRACKING_URI"] = (</p>

<p>f"sds://api.fabric.microsoft.com/v1/workspaces/{target_workspace_id}/mlflow"</p>

<p>)</p></pre><br />
That's it. From here, every mlflow.set_experiment(), mlflow.log_metric(), and mlflow.register_model() call writes to the target workspace.<p></p>

<p>Please note: If your current workspace has OAP enabled, you must config a&nbsp;<a href="https://learn.microsoft.com/fabric/security/workspace-outbound-access-protection-allow-list-endpoint#allow-outbound-access-to-another-workspace-in-the-tenant" rel="noopener" target="_blank">cross-workspace managed private endpoint</a>&nbsp;from the source workspace to the target workspace and route the tracking URI through the private endpoint.
</p><h2>Cross-workspace logging capabilities</h2>
<h3>Dev → Test → Prod MLOps workflows</h3>
Separate your ML lifecycle into distinct workspaces — Development for experimentation, Test for validation, and Production for serving. Train and iterate freely in a development workspace. When a model passes your quality bar, promote it to Test by logging it cross-workspace. After validation, promote to a production workspace. Each workspace maintains its own experiments, models, and access controls, giving you clear audit trails and governance boundaries.
<h3>Bring existing ML assets into Fabric</h3>
Already training models in Azure Databricks, Azure Machine Learning, or on your local machine? You don't need to rebuild your training pipelines. Install synapseml-mlflow, authenticate with your Fabric workspace, and log your experiments and models directly into Fabric. This consolidates your ML assets in one place for unified governance and downstream deployment — without changing your existing training code.
<h3>Train where the data lives, serve from a separate workspace</h3>
Many enterprise customers have strict data governance policies that dictate production data can only be accessed within a locked-down workspace with tightly controlled permissions. Before cross-workspace logging, this meant serving and training had to happen in the same workspace, limiting who could access the deployed model. Now, data scientists can train models in the secured workspace with access to production data and log the trained model to a separate serving workspace with broader access — keeping sensitive data contained while making models available for downstream consumption.
<h2>Built for enterprise security</h2>
For organizations with strict network security requirements, cross-workspace logging works in workspaces with Outbound Access Protection (OAP) enabled. Cross-workspace logging to a different workspace requires a managed private endpoint, while logging within the same workspace and from outside Fabric works without additional configuration. Your data stays protected while your ML workflows stay productive.
<h2>Get started</h2>
Getting started takes three steps:
<ol>
 	<li><strong>Install the plugin</strong> in your Fabric notebook:</li>
</ol>
<pre>%pip install -U "synapseml-mlflow[online-notebook]" "mlflow-skinny&lt;=2.22.2"</pre><br />
<strong>2. Set the tracking URI</strong> to your target workspace.<p></p>

<p><strong>3. Use standard MLflow APIs</strong> — set_experiment, log_metric, log_model, register_model — exactly as you do today.</p>

<p>For environments outside Fabric (Databricks, local, Azure ML), install synapseml-mlflow and authenticate using DefaultAzureCredential, DeviceCodeCredential, or a service principal.
</p><h2>Learn more</h2>
Explore the <a href="https://learn.microsoft.com/fabric/data-science/machine-learning-cross-workspace-logging" rel="noopener" target="_blank">Cross-workspace logging documentation</a> for step-by-step instructions for Fabric notebooks, Azure Databricks, local environments, and OAP-enabled workspaces.<p></p>

<p>Share your feedback with us through the <a href="https://community.fabric.microsoft.com/" rel="noopener" target="_blank">Fabric Community</a> or reach out on <a href="https://www.reddit.com/r/MicrosoftFabric/" rel="noopener" target="_blank">Reddit</a>.</p>
