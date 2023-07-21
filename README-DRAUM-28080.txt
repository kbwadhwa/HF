*************************** Fix for JMS SSL Certificate issue in Domain name version 22.2.00 ***************************
This HF will apply for REPO, DevStudio and All the Peers.
This HF for both Fresh and upgrade installation.
---------------------------------------------->
Steps to apply HF on REPO and all the Peers
---------------------------------------------->

Unzip DRAUM-28080.zip file , once done you will be able to extract - grid-framework-22.2.00.jar file.

1. Stop the TSO service for all peers
2. Take backup of certificate.keystore and jms-ssl-configuration.xml file from <AO_HOME>/config location and delete both the file.
3. Take backup of grid-framework-22.2.00.jar from <AO_HOME>/tomcat/webapps/<bao_peertype>/WEB-INF/lib and delete the jar file.
4. Extract DRAUM-28080.zip
5. Copy grid-framework-22.2.00.jar from HF to <AO_HOME>/tomcat/webapps/<bao_peertype>/WEB-INF/lib location

NOTE : Below steps are for embedded RSSO only.
-------------------------------------------------
6. Take backup of grid-framework-22.2.00.jar from <AO_HOME>/tomcat/webapps/rsso/WEB-INF/lib and delete it. Do it for (Repo, CDP/HACDP)
7. Copy grid-framework-22.2.00.jar from DRAUM-28080.zip to <AO_HOME>/tomcat/webapps/rsso/WEB-INF/lib. Do it for (Repo, CDP/HACDP)
-------------------------------------------------
8. Start TSO service

---------------------------------------------->
Steps to apply HF in DevStudio
---------------------------------------------->
1. Stop the Dev studio.
2. Goto <DEVSTUDIO_HOME> and open "Development Studio.ini"(configuration setting) file
3. Add -Ddomain.name=<Domain_Name> in "Development Studio.ini"(configuration setting) file. 
	Eg: -Ddomain.name=abc.com
4. Use winzip application to open com.bmc.ao.ui.studio.plugin_1.0.0.jar from <DEVSTUDIO_HOME>\plugins.
5. Take backup of certificate.keystore and jms-ssl-configuration.xml file from <DEVSTUDIO_HOME>\config location and delete both the file.
6. Take backup of grid-framework-22.2.00.jar from com.bmc.ao.ui.studio.plugin_1.0.0.jar (from <DEVSTUDIO_HOME>\plugins) and delete it
7. Copy grid-framework-22.2.00.jar from HF to com.bmc.ao.ui.studio.plugin_1.0.0.jar (from <DEVSTUDIO_HOME>\plugins) using winzip application
8. Take backup and Delete folder named "5" from the location <DEVSTUDIO_HOME>\configuration\org.eclipse.osgi\bundles
9. Start the Dev Studio.