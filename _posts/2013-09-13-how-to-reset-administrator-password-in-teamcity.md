---
layout: post
title: How to reset your administrator password in Teamcity 8.0
date: 2013-09-13 16:47:10.000000000 -04:00
categories:
- devops
tags:
- Continuous integration
- JetBrains
- Programming
- Security
- TeamCity
author: qbantek
---
<p>
<span class="image right"><img class="size-full wp-image-81 aligncenter" alt="panic" src="{{ site.baseurl }}/assets/images/panic.jpg" width="200" height="200" /></span>Y
eah, it could happen to any of us. You setup <a class="zem_slink" title="TeamCity" href="http://www.jetbrains.com/teamcity/" target="_blank" rel="homepage">TeamCity</a> 8.0 as a continuous integration server a while ago. It runs perfectly fine, it runs so fine that you never need to log on as an administrator any more. You even forget that it exists, you even forget YOUR PASSWORD! </p>
<p>Now what? Reinstall everything? Try to hack the database? Use some cryptic java commands? What? What?</p>
<p><span class="image left"><img class="size-thumbnail alignleft" alt="Superman" src="{{ site.baseurl }}/assets/images/superman.jpg?w=150" width="150" height="150" /></span>

    No panic needed, the nice people at <a title="JetBrains" href="http://www.jetbrains.com/" target="_blank">JetBrains </a>already thought about this. There is a Super-user token that allow you to get back to the server UI with system administrator permissions.
</p>
<p>Go and get the token from the <span style="color:#000000;"><strong>teamcity-server.log</strong></span> file (search for "Super user authentication token" text).</p>
<p>After that you just need to:</p>
<ol>
    <li>Go to
        <tt><code>[TeamCity server URL]/login.html?super=1</code></tt>
    </li>
    <li>Enter the Super-user token.</li>
    <li>Enjoy the rest of your day</li>
</ol>
<p>References:</p>
<ul>
    <li><a title="Teamcity 8.0 - Super User" href="http://confluence.jetbrains.com/display/TCD8/Super+User" target="_blank">http://confluence.jetbrains.com/display/TCD8/Super+User</a></li>
</ul>