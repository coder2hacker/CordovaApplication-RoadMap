# CordovaApplication-RoadMap

# Overview
<ul>
<li>Apache Cordova is an open-source mobile development framework. It allows you to use standard web technologies - HTML5, CSS3, and JavaScript for cross-platform development. Applications execute within wrappers targeted to each platform, and rely on standards-compliant API bindings to access each device's capabilities such as sensors, data, network status, etc.</li>

<li>Use Apache Cordova if you are:</li>

<li>a mobile developer and want to extend an application across more than one platform, without having to re-implement it with each platform's language and tool set.</li>

<li>a web developer and want to deploy a web app that's packaged for distribution in various app store portals.</li>

<li>a mobile developer interested in mixing native application components with a WebView (special browser window) that can access device-level APIs, or if you want to develop a plugin interface between native and WebView components.</li>


# Create your first Cordova app
<p>This guide shows you how to create a JS/HTML Cordova application and deploy them to various native mobile platforms using the cordova command-line interface (CLI). For detailed reference on Cordova command-line, review the CLI reference.</p>

# Installing the Cordova CLI
<p>The Cordova command-line tool is distributed as an npm package.

To install the cordova command-line tool, follow these steps:

Download and install Node.js. On installation you should be able to invoke node and npm on your command line.

(Optional) Download and install a git client, if you don't already have one. Following installation, you should be able to invoke git on your command line. The CLI uses it to download assets when they are referenced using a url to a git repo.

Install the cordova module using npm utility of Node.js. The cordova module will automatically be downloaded by the npm utility.</p>

# on OS X and Linux:
<p>
   $ sudo npm install -g cordova
On OS X and Linux, prefixing the npm command with sudo may be necessary to install this development utility in otherwise restricted directories such as /usr/local/share. If you are using the optional nvm/nave tool or have write access to the install directory, you may be able to omit the sudo prefix. There are more tips available on using npm without sudo, if you desire to do that.</p>

# on Windows:

   C:\>npm install -g cordova
The -g flag above tells npm to install cordova globally. Otherwise it will be installed in the node_modules subdirectory of the current working directory.

Following installation, you should be able to run cordova on the command line with no arguments and it should print help text.

# Create the App
Go to the directory where you maintain your source code, and create a cordova project:

$ cordova create hello com.example.hello HelloWorld
This creates the required directory structure for your cordova app. By default, the cordova create script generates a skeletal web-based application whose home page is the project's www/index.html file.
