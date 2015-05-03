Save-Documents-Connector
========================

Description
-----------
This connector allow you to save all the document upload on the process instance they are attached to.

What's included
---------------
.bos file includes a demonstration process and connector source code.

Requirements
------------
- Process has been created with Bonita Community version 6.5.1. So you must use Community or Subscription edition with version 6.5.1 or higher to import it.

Important
---------
- If two (or more) uploaded files share the same name, they will override each other on the file system.
- Connector hasn't been tested if document content is empty.

How to debug in Bonita Studio
-----------------------------
First of all, adjust the log level for the connector:
- Go to your Studio installation folder
- Go to `workspace/tomcat/conf` folder (assuming you are using the default workspace)
- Edit the `logging.properties` file
- Add the following line at the end of the file: `org.bonitasoft.connectors.SaveAllDocumentsOnFileSystemImpl.level = FINEST`

In order for your configuration modification to be taken into account you need to restart the Tomcat embedded in the Studio: in Studio `Server` menu select `Restart web server`.

Run your process and then check the Bonita Engine log file:
- Go to Studio `Help` menu -> `Bonita BPM Engine log`
- or go to your Studio installation folder and go to `workspace/tomcat/logs` folder and open the latest `bonita-YYYY-MM-DD.log`

In the log file search for: `org.bonitasoft.connectors.SaveAllDocumentsOnFileSystemImpl`

Edit connector implementation
-----------------------------
In order to edit the connector implementation you first need to add SLF4J API jar file to your workspace classloader:
Go to Studio `Development` menu -> `Manage jars...` click on `Import...` button and go to your Studio installation folder and move to `workspace/tomcat/lib/bonita` and select `slf4j-api-1.6.1.jar`

Now you can go to `Development` menu -> `Connectors` -> `Edit implementation...` and select the connector to modify it.

License
-------
* [Apache License, Version 2.0](http://www.apache.org/licenses/LICENSE-2.0)