# Jira SAML 2.0 Plugin

A plugin that lets Atlassian JIRA support connecting to a SAML 2.0 IdP.

## Usage
Please see the [wiki page](https://github.com/bitium/jira-saml-plugin/wiki/Installation-and-Usage-Instructions) for usage information

## Development Setup

Note: this assumes you have a JDK installed and configured.

### 1. Install the Atlassian SDK

  For Ubuntu/Debian Linux (for other OSes, see [here](https://developer.atlassian.com/server/framework/atlassian-sdk/downloads/)):
  1. ```sudo sh -c 'echo "deb https://packages.atlassian.com/atlassian-sdk-deb stable contrib" >>/etc/apt/sources.list'```
  2. ```wget https://packages.atlassian.com/api/gpg/key/public```
  3. ```apt-key add public```
  4. ```sudo apt-get update```
  5. ```sudo apt-get install atlassian-plugin-sdk```

### 2. Install the Atlassian SAML Commons to your global Maven Repo

  1. ```git clone https://github.com/bitium/atlassian-saml.git```
  2. ```cd atlassian-saml```
  3. ```atlas-mvn clean install```
  
### 3. Compile the install the Plugin ###

  1. ```git clone https://github.com/cbanack/jira-saml-plugin.git```
  2. ```cd jira-saml-plugin```
  3. ```atlas-mvn clean package```
  4. the plugin's JAR can now be found in the ```target``` folder
  5. go to JIRA, login and go to the "Manage Add-ons" admin area
  6. select the option to "upload a plugin"
  7. upload the JAR.  this installs the plugin overwriting any previous installation
  8. go to the "SAML 2.0 Plugin Configuration" section in the "system" admin area.
  9. you're now looking at the UI for this plugin.

### 4. (Optional) Run the plugin in a local JIRA instance

  1. go to the ```jira-saml-plugin``` folder
  2. run ```atlas-run``` to (re)build the plugin and start a local jira
  3. after everything compiles and JIRA starts, a URL will be displayed
  4. enter the url into your browser to go to the local JIRA
    * username: ```admin```
    * password: ```admin```
  5. create a sample project so you can acccess the "system" admin area.
  6. go to the "SAML 2.0 Plugin Configuration" section in the "system" admin area.
  7. you're now looking at the UI for this plugin.

### Tips
  1. Use Atlassian [QuickReload](https://developer.atlassian.com/docs/developer-tools/automatic-plugin-reinstallation-with-quickreload) plugin to speed up developement by automatically deploying changes without needing to restart the host application.
  
  2. A remote debugger can be attached after launching the host app using ```atlas-debug --product jira```, see [Creating a Remote Debug Target](https://developer.atlassian.com/docs/developer-tools/working-in-an-ide/creating-a-remote-debug-target)

## Licensing
  This plugin is licensed under [GPLv3](LICENSE).
