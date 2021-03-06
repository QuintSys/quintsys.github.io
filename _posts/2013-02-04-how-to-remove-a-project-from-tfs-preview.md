---
layout: post
title: How to remove a project from TFS Preview
date: 2013-02-04 22:28:52.000000000 -05:00
type: post
published: true
status: publish
categories:
- devops
tags:
- Microsoft
- Microsoft Visual Studio
- Source Control
- Team Foundation Server
- TFS
- TFS Preview
- Tip
author: qbantek
---
<p>By now you probably know that <a class="zem_slink" title="Microsoft" href="http://maps.google.com/maps?ll=47.6395972222,-122.12845&amp;spn=0.01,0.01&amp;q=47.6395972222,-122.12845 (Microsoft)&amp;t=h" target="_blank" rel="geolocation">Microsoft</a> is offering a <a href="https://tfs.visualstudio.com/en-us/" target="_blank">FREE preview of TFS online</a>. If you have a Microsoft account (previously <a class="zem_slink" title="Windows Live ID" href="http://en.wikipedia.org/wiki/Windows_Live_ID" target="_blank" rel="wikipedia">Live Id</a>), you already have a TFS account. Just sign in and start
    <del datetime="2013-02-05T03:14:02+00:00">playing</del> using the features!</p>
<p>So much usage will probably leave a few projects on your account that you don't need at all. Time for some cleanup.
    <br />
    <span style="font-size:16px;">But, how do you delete a project from your TFS Preview account????</span></p>
<ul>
    <li>Open a VS2012 <a class="zem_slink" title="Command Prompt" href="http://en.wikipedia.org/wiki/Command_Prompt" target="_blank" rel="wikipedia">command prompt</a> in administrator mode</li>
    <li>Go to: 
    	<code>%programfiles%\<a class="zem_slink" title="Microsoft Visual Studio" href="http://www.microsoft.com/visualstudio/en-us" target="_blank" rel="homepage">Microsoft Visual Studio</a> 11.0\Common7\<a class="zem_slink" title="Integrated development environment" href="http://en.wikipedia.org/wiki/Integrated_development_environment" target="_blank" rel="wikipedia">IDE</a></code></li>
    <li>Execute the following command (replace myproject and projectname with your own values): 
    	<code>tfsdeleteproject/collection:"https://myproject.tfspreview.com/DefaultCollection/" projectname</code></li>
</ul>
<p>You might be prompted for your credentials and to confirm your request:</p>
<p><code>Warning: Deleting a team project is an irrecoverable operation. All <a class="zem_slink" title="Revision control" href="http://en.wikipedia.org/wiki/Revision_control" target="_blank" rel="wikipedia">version control</a>, work item tracking and Team Foundation build data will be destroyed from the system. The only way to recover this data is by restoring a stored backup of the databases. Are you sure you want to delete the team project and all of its data (Y/N)?</code></p>
<p>Just hit Y and enjoy!</p>
