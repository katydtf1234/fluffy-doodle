## Build Instructions
  * Download and install [Apache Ant](http://ant.apache.org/bindownload.cgi)
  * Download and install [Antenna](http://antenna.sourceforge.net/)
  * Download and install [bb-ant-tools](http://bb-ant-tools.sourceforge.net/)
  * Download and install [Eclipse with BlackBerry plug-ins](http://na.blackberry.com/eng/developers/javaappdev/javaeclipseplug.jsp) or the [BlackBerry JDE](http://na.blackberry.com/eng/developers/javaappdev/javadevenv.jsp)
  * ` git clone https://github.com/google/google-authenticator.git `
  * ` cd google-authenticator/mobile/blackberry `
  * Create file ` local.properties ` in project root (see example below)
  * Run ` ant release `

## Signing Instructions
  * Before building, copy ` sigtool.csk ` and ` sigtool.db ` to the ` bin/ ` directory of the SDK identified by ` jdehome ` in ` local.properties `
  * Run ` ant release `
  * Enter password when prompted

## Deployment Instructions
  * Download and install [ActivePython](http://www.activestate.com/activepython/)
  * Download and install [Google App Engine SDK for Python](http://code.google.com/appengine/downloads.html#Google_App_Engine_SDK_for_Python)
  * Run ` ant release `
  * ` appcfg.py update release\<version> `

## Tips
  * If you get a ` MissingResourceException ` in the simulator, try running ` clean.bat ` in the ` simulator ` directory (for example, ` C:\Program Files\Eclipse\plugins\net.rim.eide.componentpack4.5.0_4.5.0.16\components\simulator `)
  * To manually regenerate ` com.google.authenticator.blackberry.resource.AuthenticatorResource ` in Eclipse, use the _Validate_ button in the resource editor.
  * Do not change the COD file name; the BlackBerry platform uses this to identify an application and if a user upgrades to a COD with a different name they will end up with multiple installations.

## Sample ` local.properties ` File

```
java.home=C:/Program Files (x86)/Java/jdk1.6.0_22
jdehome=C:/Eclipse/plugins/net.rim.ejde.componentpack4.5.0_4.5.0.28/components
jdehome45=C:/Eclipse/plugins/net.rim.ejde.componentpack4.5.0_4.5.0.28/components
jdehome46=C:/Eclipse/plugins/net.rim.ejde.componentpack4.6.0_4.6.0.23/components
jdehome47=C:/Eclipse/plugins/net.rim.ejde.componentpack4.7.0_4.7.0.57/components
jdehome50=C:/Eclipse/plugins/net.rim.ejde.componentpack5.0.0_5.0.0.25/components
jdehome60=C:/Eclipse/plugins/net.rim.ejde.componentpack6.0.0_6.0.0.29/components
appengine.application=myauthenticator
appengine.version=1
appengine.url=http://myauthenticator.appspot.com/
```