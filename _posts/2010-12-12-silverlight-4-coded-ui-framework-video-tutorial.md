---
layout: post
title: Silverlight 4 – Coded UI Framework Video Tutorial
excerpt: ""
tags: 
comments: true
---
<br>
With the release of[Visual Studio 2010 Feature Pack 2](http://msdn.microsoft.com/en-us/vstudio/ff655021) Microsoft included the Coded UI Test framework. With this release it is possible to create automated test with just a few mouse clicks. This is a very powerful feature that all Silverlight developers need to learn. Instead of my normal blog post I have created a video tutorial that walks you through it starting from “File” –> New Project. I hope you enjoy and please leave feedback.
<br>
Video Tutorial (short 9 minute video):
<br>
<embed width="600" height="361" type="application/x-shockwave-flash" allowfullscreen="true" allownetworking="all" wmode="transparent" src="http://static.photobucket.com/player.swf" flashvars="file=http%3A%2F%2Fvid1121.photobucket.com%2Falbums%2Fl508%2Fmbcrump%2FScreenCapture_12-11-201045608PM.mp4">
<br>
Slides from the demo (only 3):
<br>
<div style="width: 425px" id="__ss_6121431">**[Silverlight 4 – Coded UI Testing](http://www.slideshare.net/mbcrump/silverlight-4-coded-ui-testing "Silverlight 4 – Coded UI Testing")**<embed height="355" name="__sse6121431" type="application/x-shockwave-flash" width="425" src="http://static.slidesharecdn.com/swf/ssplayer2.swf?doc=silverlight4codedui-101211181425-phpapp02&stripped_title=silverlight-4-coded-ui-testing&userName=mbcrump" allowfullscreen="true" allowscriptaccess="always">
<br>
Code for the MainPage.xaml that was used in the Demo. For the sake of time I did not go into the[AutomationProperties.Name](http://msdn.microsoft.com/en-us/library/ms606856.aspx) that I used for the TextBox or Button. I added that for each element .
<br>
	&lt;Grid x:Name="LayoutRoot" Background="White" Height="100" Width="350"&gt;      	&lt;Grid.ColumnDefinitions&gt;          &lt;ColumnDefinition/&gt;          	&lt;ColumnDefinition/&gt;      &lt;/Grid.ColumnDefinitions&gt;      	&lt;Grid.RowDefinitions&gt;          &lt;RowDefinition/&gt;          &lt;RowDefinition/&gt;      	&lt;/Grid.RowDefinitions&gt;      &lt;TextBlock Padding="15" Grid.Column="0" 	TextAlignment="Right"&gt;Name&lt;/TextBlock&gt;      &lt;TextBox 	AutomationProperties.Name="txtAP" Grid.Column="1" Height="25" TextAlignment="Right" 	Name="txtName" /&gt;      &lt;Button AutomationProperties.Name="btnAP" Grid.Row="1" 	Grid.Column="1" Content="Click for Name"             x:Name="btnMessage" 	Click="btnMessage_Click" /&gt;  &lt;/Grid&gt;