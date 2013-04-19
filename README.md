# Google Analytics plugin for Cordova 2.5.0 on iOS
====================
A iOS Google Analytics SDK 2.0 plugin for Cordova 2.5+

Setup:
---------------------
<ol>
	<li>To install the plugin, move GoogleAnalyticsPlugin.js to your project's www folder and include a reference to it in your html file after cordova.js.</li>
	<li>Drag and drop the 'GoogleAnalytics' folder to the 'Plugins' folder in Xcode</li>
	<li> Install the 'CoreData' and 'SystemConfigration' libraries/frameworks if not already installed. This can be accomplished by opening the project editor and selecting the projects target. At the top of the project editor, click 'Build Phases'. Open the 'Link Binary With Libraries section'. Press the Add (+) button and search for 'CoreData' and 'SystemConfigration' libraries/frameworks. If they are not already included in your project, ensure to add them. 
	<br><b>See this for further information:</b> http://developer.apple.com/library/mac/#recipes/xcode_help-project_editor/Articles/AddingaLibrarytoaTarget.html</li>
	<li>In your config.xml add the following mapping to the <plugins> key:</li>
</ol>	
<pre>
<code>
	&lt;plugin name=&quot;googleAnalyticsPlugin&quot; value=&quot;GoogleAnalyticsPlugin&quot; /&gt;
</code>
</pre>
	
Also, add the following mapping to the <widget> key:
<pre>
<code>
	&lt;access origin=&quot;*&quot; /&gt;
</code>
</pre>	
Overall the config.xml should have the following entries:
<pre>
<code>
	&lt;widget&gt;
	    &lt;plugins&gt;
	        &lt;plugin name=&quot;googleAnalyticsPlugin&quot; value=&quot;GoogleAnalyticsPlugin&quot; /&gt;
	    &lt;/plugins&gt;
	    &lt;access origin=&quot;*&quot; /&gt;
	&lt;/widget&gt;
</code>
</pre>
Example:
---------------------
<pre>
<code>
	&lt;script type=&quot;text/javascript&quot;&gt;
		document.addEventListener(&quot;deviceready&quot;, onDeviceReady, false);
		function onDeviceReady() {
			window.GA.trackerWithTrackingId(&quot;UA-XXXXXXXX-X&quot;);
			window.GA.trackView(&quot;/index&quot;);
		}
	&lt;/script&gt;
</code>
</pre>

Credit:
---------------------
The updated GoogleAnalyticsPlugin.m, GoogleAnalyticsPlugin.h, and GoogleAnalyticsPlugin.js files were courtesy of nocksf in this discussion: https://groups.google.com/d/msg/phonegap/uqYjTmd4w_E/fZvJCpAbtsUJ
