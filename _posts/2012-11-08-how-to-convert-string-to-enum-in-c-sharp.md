---
layout: post
title: How to convert string to Enum in C#
date: 2012-11-08 10:47:50.000000000 -05:00
type: post
published: true
status: publish
categories:
- Code
tags:
- ".NET Framework"
- C#
- Convert
- Enum
- Enumerated type
- Source code
- String
- Typeof
author: qbantek
---
<p>This is a common task for C# programmers. You have a string value and need to convert it to the equivalent <a class="zem_slink" title="Enumerated type" href="http://en.wikipedia.org/wiki/Enumerated_type" target="_blank" rel="wikipedia">Enum</a> value. Piece o' cake: code some nifty <code>switch</code> statement or maybe a bunch of <code>if / else</code> conditions to test for every possible match, right? ... er, NO.</p>
<p>Say you have declared an Enum like:</p>

{% highlight csharp %}public enum FeedBackMessageType { None = 0, Success, Warning, Error }{% endhighlight %}

<p>Then you should be able to convert a string like:</p>

{% highlight csharp %}var type = (FeedBackMessageType) Enum.Parse(typeof(FeedBackMessageType), "Success", true);{% endhighlight %}

<p>If you are trying to convert a string that doesn't match any of values from the enum, you will get a ArgumentException. How to avoid this? Try:</p>
{% highlight csharp %}var invalidMessageType = "Info"; 
var type = Enum.IsDefined(typeof(FeedBackMessageType), invalidMessageType) 
		? (FeedBackMessageType) Enum.Parse(typeof(FeedBackMessageType), invalidMessageType, true) 
		: FeedBackMessageType.None;{% endhighlight %}

<p>One caveat, the <code>IsDefined</code> method has no <code>ignore case</code> parameter. According to <a title="MSDN - Enum.IsDefined Method" href="http://bit.ly/UnSCy7">MSDN</a>: <em>The characters in the string must have the same case as the enumeration member name.</em> :/</p>
<p>References:</p>
<ul>
    <li><a href="http://bit.ly/Z6p1bo" title="Enum.Parse Method (Type, String, Boolean)">http://msdn.microsoft.com/en-us/library/kxydatf9.aspx</a></li>
    <li><a href="http://bit.ly/UnSCy7" title="Enum.IsDefined Method">http://msdn.microsoft.com/en-us/library/system.enum.isdefined.aspx</a></li>
</ul>