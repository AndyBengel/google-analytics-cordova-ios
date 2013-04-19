# Google Analytics plugin for Cordova 2.5.0 on iOS
====================
A iOS Google Analytics SDK 2.0 plugin for Cordova 2.5+

Setup:
---------------------
1) To install the plugin, move GoogleAnalyticsPlugin.js to your project's www folder and include a reference to it in your html file after cordova.js.
2) Drag and drop the 'GoogleAnalytics' folder to the 'Plugins' folder in Xcode
3) Install the 'CoreData' and 'SystemConfigration' libraries/frameworks if not already installed. This can be accomplished by opening the project editor and selecting the projects target. At the top of the project editor, click 'Build Phases'. Open the 'Link Binary With Libraries section'. Press the Add (+) button and search for 'CoreData' and 'SystemConfigration' libraries/frameworks. If they are not already included in your project, ensure to add them. See this for further information: http://developer.apple.com/library/mac/#recipes/xcode_help-project_editor/Articles/AddingaLibrarytoaTarget.html
4) In your config.xml add the following mapping to the <plugins> key:
<pre>
<code>
<plugin name="googleAnalyticsPlugin" value="GoogleAnalyticsPlugin" />
</code>
</pre>

Also, add the following mapping to the <widget> key:
<pre>
<code>
<access origin="*" />
</code>
</pre>

Overall the config.xml should have the following entries:
<pre>
<code>
<widget>
    <plugins>
        <plugin name="googleAnalyticsPlugin" value="GoogleAnalyticsPlugin" />
    </plugins>
    <access origin="*" />
</widget>
</code>
</pre>

Example:
---------------------
<pre>
<code>
	<script type="text/javascript">
		document.addEventListener("deviceready", onDeviceReady, false);
		function onDeviceReady() {
			window.GA.trackerWithTrackingId("UA-XXXXXXXX-X");
			window.GA.trackView("/index");
		}
	</script>
</code>
</pre>

Credit:
---------------------
The updated GoogleAnalyticsPlugin.m, GoogleAnalyticsPlugin.h, and GoogleAnalyticsPlugin.js files were courtesy of nocksf in this discussion: https://groups.google.com/d/msg/phonegap/uqYjTmd4w_E/fZvJCpAbtsUJ
