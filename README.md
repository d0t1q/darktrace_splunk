Introduction

Darktrace Connector for Splunk combines Darktrace's award-winning Enterprise Immune System technology, uniquely capable of detecting and responding to the most subtle cyber-threats within the network, with Splunk’s leading operational intelligence platform. Powered by advanced machine learning and AI algorithms, the Enterprise Immune System automatically and adaptively learns the ‘pattern of life’ for every user, device and network, in order to detect emerging behaviours that represent real threats.

The app enhances the Splunk UI by populating it with real-time threat alerts from Darktrace’s self-learning technology, allowing corporations to proactively respond to threats and mitigate risk. The alerts link to detailed reports in the Darktrace Threat Visualizer, allowing for a deep analysis of emerging vulnerabilities and early-stage threats. With straightforward installation and an intuitive dashboard, the Darktrace Connector seamlessly integrates with your existing Splunk interface.
Getting Started
1. Install Splunk Enterprise:

If you haven't already installed Splunk Enterprise, download it at http://www.splunk.com/download. For more information about installing and running Splunk Enterprise and system requirements, see the Installation Manual (http://docs.splunk.com/Documentation/Splunk/latest/Installation).
2. Install the Darktrace Connector for Splunk:

For Splunk Server:

Visit Splunkbase, search for Darktrace and Download the App. If you do not have permission to download the app - please contact Darktrace CT or Darktrace directly via https://www.darktrace.com/contact/.

To install Darktrace Connector for Splunk within Splunk Enterprise:
1. Log into Splunk Enterprise.
2. On the Apps menu, click Manage Apps.
3. Click Install app from file.
4. In the Upload app window, click Choose File.
5. Locate the .tar.gz file you just downloaded, and then click Open or Choose.
6. Click Upload.
7. Click Restart Splunk, and then confirm that you want to restart.

To install Darktrace Connector for Splunk directly into Splunk Enterprise:
1. Put the downloaded file in the $SPLUNK_HOME/etc/apps directory.
2. Untar and ungzip your app or add-on, using a tool like tar -xvf (on *nix) or WinZip (on Windows).
3. Restart Splunk.

After you install the Splunk app, you will find it on Splunk Home.

For Splunk Cloud:

To install the Darktrace Connector for Splunk in Splunk Cloud:
1. Log into your Splunk Cloud.
2. On the Apps menu, click on 'Find More Apps'. This should take you to a 'Browse More Apps' page.
3. Find the 'Darktrace Connector for Splunk' App and click on 'Install'.

After you install the Splunk app, you will find it on Splunk Home.
3. Set Up the App to Receive Data:

Upon installing the app, a TCP listening port must be set up for direct interaction with the Darktrace Appliance, TCP input ports can be set up by doing the following:
1. Login to your Splunk instance.
2. Click 'Add Data' either on the main page or under the settings heading in the toolbar in the top right of the screen.
3. Click on 'Monitor'.
4. Select the option 'TCP/UDP' on the left, make sure TCP is selected in the following screen and type in the desired port number.
5. If you wish to only accept data from a single Darktrace Appliance on this port, put the IP address of this device in the 'Only Accept Connection From' field and click 'Next'.
6. Select the 'sourcetype' to be 'darktrace' which should be under the 'Structured' tab.
7. Set App Context to Darktrace then click 'Review' followed by 'Submit' to set the new TCP listening port.

For other input options, such as forwarding ports, please see the Splunk Documentation.
4. Set Up Darktrace to Send Data:

To send data from Darktrace use the settings in our Threat Visualizer, change the following Config settings:
1. Log into Darktrace.
2. From the menu click Config.
3. Set JSON Syslog Alerts to True. Click Save.
4. Enter Syslog Server: IP address of the computer the Splunk app is installed on.
5. Enter the Syslog Port: pick a port number higher than 1024, such as 5514, if the app is not running as sudo.
6. Set JSON Syslog TCP Alerts to True. Click Save.
7. Set Legacy JSON Alert Format False.
8. Click Save.
5. Set Up FQDN for Visualizer Click-Through:

The Darktrace Connector for Splunk will generate clickthrough links, and also display the links for quick analysis. To ensure these links are set up properly, from /config on the Darktrace appliance change FQDN to the proper Darktrace URL. This should be in the form https://<fqdn>/#information.
