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



<div id="page-toc-source">
                <a class="fragment-anchor" id="customize-icons"></a><span id="customize-icons"></span><h1>Customize Icons</h1>

<p>This section shows how to configure an application's icon for various platforms. Documentation about splash screen images can be found in the Cordova-Plugin-Splashscreen documentation <a href="../reference/cordova-plugin-splashscreen/">Splashscreen plugin docs</a>.</p>

<a class="fragment-anchor" id="configuring-icons-in-the-cli"></a><span id="configuring-icons-in-the-cli"></span><h2>Configuring Icons in the CLI<a class="header-link" href="#configuring-icons-in-the-cli"><i class="glyphicon glyphicon-link"></i></a></h2>

<p>When working in the CLI you can define application icon(s) via the <code>&lt;icon&gt;</code> element (<code>config.xml</code>).
If you do not specify an icon, the Apache Cordova logo is used.</p>
<div class="highlight"><pre><code class="language-xml" data-lang="xml">    <span class="nt">&lt;icon</span> <span class="na">src=</span><span class="s">"res/ios/icon.png"</span> <span class="na">platform=</span><span class="s">"ios"</span> <span class="na">width=</span><span class="s">"57"</span> <span class="na">height=</span><span class="s">"57"</span> <span class="na">density=</span><span class="s">"mdpi"</span> <span class="nt">/&gt;</span>
</code></pre></div>
<table><thead>
<tr>
<th>Attributes</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td>src</td>
<td><em>Required</em> <br> Location of the image file, relative to your project directory.</td>
</tr>
<tr>
<td>platform</td>
<td><em>Optional</em> <br> Target platform</td>
</tr>
<tr>
<td>width</td>
<td><em>Optional</em> <br> Icon width in pixels</td>
</tr>
<tr>
<td>height</td>
<td><em>Optional</em> <br> Icon height in pixels</td>
</tr>
<tr>
<td>target</td>
<td><em>Optional</em> <br> <mark class="logo windows" title="Windows"></mark> <br> Destination filename for the image file and all its MRT companions</td>
</tr>
</tbody></table>

<p>The following configuration can be used to define a single default icon
which will be used for all platforms.</p>
<div class="highlight"><pre><code class="language-xml" data-lang="xml">    <span class="nt">&lt;icon</span> <span class="na">src=</span><span class="s">"res/icon.png"</span> <span class="nt">/&gt;</span>
</code></pre></div>
<p>For each platform, you can also define a pixel-perfect icon set to fit
different screen resolutions.</p>

<a class="fragment-anchor" id="android"></a><span id="android"></span><h2>Android<a class="header-link" href="#android"><i class="glyphicon glyphicon-link"></i></a></h2>

<p>On Android, instead of using a single image for an icon, you can use two images (background and foreground) to create an <strong>Adaptive Icon</strong>.</p>

<table><thead>
<tr>
<th>Attributes</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td>background</td>
<td><em>Required for Adaptive</em> <br> Location of the image (png or vector) relative to your project directory, or color reference</td>
</tr>
<tr>
<td>foreground</td>
<td><em>Required for Adaptive</em> <br> Location of the image (png or vector) relative to your project directory, or color reference</td>
</tr>
<tr>
<td>density</td>
<td><em>Required</em> <br> Specified icon density</td>
</tr>
</tbody></table>

<a class="fragment-anchor" id="adaptive-icons"></a><h3>Adaptive Icons<a class="header-link" href="#adaptive-icons"><i class="glyphicon glyphicon-link"></i></a></h3>

<p>To use the adaptive icons the <code>background</code> and <code>foreground</code> attributes must be defined in place of the <code>src</code> attribute. The <code>src</code> attribute is not used for adaptive icons.</p>

<a class="fragment-anchor" id="adaptive-icon-with-images"></a><h4>Adaptive Icon with Images:<a class="header-link" href="#adaptive-icon-with-images"><i class="glyphicon glyphicon-link"></i></a></h4>
<div class="highlight"><pre><code class="language-xml" data-lang="xml"><span class="nt">&lt;platform</span> <span class="na">name=</span><span class="s">"android"</span><span class="nt">&gt;</span>
  <span class="nt">&lt;icon</span> <span class="na">background=</span><span class="s">"res/icon/android/ldpi-background.png"</span> <span class="na">density=</span><span class="s">"ldpi"</span> <span class="na">foreground=</span><span class="s">"res/icon/android/ldpi-foreground.png"</span> <span class="nt">/&gt;</span>
  <span class="nt">&lt;icon</span> <span class="na">background=</span><span class="s">"res/icon/android/mdpi-background.png"</span> <span class="na">density=</span><span class="s">"mdpi"</span> <span class="na">foreground=</span><span class="s">"res/icon/android/mdpi-foreground.png"</span> <span class="nt">/&gt;</span>
  <span class="nt">&lt;icon</span> <span class="na">background=</span><span class="s">"res/icon/android/hdpi-background.png"</span> <span class="na">density=</span><span class="s">"hdpi"</span> <span class="na">foreground=</span><span class="s">"res/icon/android/hdpi-foreground.png"</span> <span class="nt">/&gt;</span>
  <span class="nt">&lt;icon</span> <span class="na">background=</span><span class="s">"res/icon/android/xhdpi-background.png"</span> <span class="na">density=</span><span class="s">"xhdpi"</span> <span class="na">foreground=</span><span class="s">"res/icon/android/xhdpi-foreground.png"</span> <span class="nt">/&gt;</span>
  <span class="nt">&lt;icon</span> <span class="na">background=</span><span class="s">"res/icon/android/xxhdpi-background.png"</span> <span class="na">density=</span><span class="s">"xxhdpi"</span> <span class="na">foreground=</span><span class="s">"res/icon/android/xxhdpi-foreground.png"</span> <span class="nt">/&gt;</span>
  <span class="nt">&lt;icon</span> <span class="na">background=</span><span class="s">"res/icon/android/xxxhdpi-background.png"</span> <span class="na">density=</span><span class="s">"xxxhdpi"</span> <span class="na">foreground=</span><span class="s">"res/icon/android/xxxhdpi-foreground.png"</span> <span class="nt">/&gt;</span>
<span class="nt">&lt;/platform&gt;</span>
</code></pre></div>
<p><strong>Note:</strong> In this example, the foreground image will also be used as the fallback icon for Android devices that do not support the adaptive icons. The fallback icon can be overridden by setting the src attribute.</p>

<a class="fragment-anchor" id="adaptive-icon-with-vectors"></a><h4>Adaptive Icon with Vectors:<a class="header-link" href="#adaptive-icon-with-vectors"><i class="glyphicon glyphicon-link"></i></a></h4>
<div class="highlight"><pre><code class="language-xml" data-lang="xml"><span class="nt">&lt;platform</span> <span class="na">name=</span><span class="s">"android"</span><span class="nt">&gt;</span>
  <span class="nt">&lt;icon</span> <span class="na">background=</span><span class="s">"res/icon/android/ldpi-background.xml"</span> <span class="na">density=</span><span class="s">"ldpi"</span> <span class="na">foreground=</span><span class="s">"res/icon/android/ldpi-foreground.xml"</span> <span class="na">src=</span><span class="s">"res/android/ldpi.png"</span> <span class="nt">/&gt;</span>
  <span class="nt">&lt;icon</span> <span class="na">background=</span><span class="s">"res/icon/android/mdpi-background.xml"</span> <span class="na">density=</span><span class="s">"mdpi"</span> <span class="na">foreground=</span><span class="s">"res/icon/android/mdpi-foreground.xml"</span> <span class="na">src=</span><span class="s">"res/android/mdpi.png"</span> <span class="nt">/&gt;</span>
  <span class="nt">&lt;icon</span> <span class="na">background=</span><span class="s">"res/icon/android/hdpi-background.xml"</span> <span class="na">density=</span><span class="s">"hdpi"</span> <span class="na">foreground=</span><span class="s">"res/icon/android/hdpi-foreground.xml"</span> <span class="na">src=</span><span class="s">"res/android/hdpi.png"</span> <span class="nt">/&gt;</span>
  <span class="nt">&lt;icon</span> <span class="na">background=</span><span class="s">"res/icon/android/xhdpi-background.xml"</span> <span class="na">density=</span><span class="s">"xhdpi"</span> <span class="na">foreground=</span><span class="s">"res/icon/android/xhdpi-foreground.xml"</span> <span class="na">src=</span><span class="s">"res/android/xhdpi.png"</span> <span class="nt">/&gt;</span>
  <span class="nt">&lt;icon</span> <span class="na">background=</span><span class="s">"res/icon/android/xxhdpi-background.xml"</span> <span class="na">density=</span><span class="s">"xxhdpi"</span> <span class="na">foreground=</span><span class="s">"res/icon/android/xxhdpi-foreground.xml"</span> <span class="na">src=</span><span class="s">"res/android/xxhdpi.png"</span> <span class="nt">/&gt;</span>
  <span class="nt">&lt;icon</span> <span class="na">background=</span><span class="s">"res/icon/android/xxxhdpi-background.xml"</span> <span class="na">density=</span><span class="s">"xxxhdpi"</span> <span class="na">foreground=</span><span class="s">"res/icon/android/xxxhdpi-foreground.xml"</span> <span class="na">src=</span><span class="s">"res/android/xxxhdpi.png"</span> <span class="nt">/&gt;</span>
<span class="nt">&lt;/platform&gt;</span>
</code></pre></div>
<p><strong>Note:</strong> In this example, the src attribute must be defined when then foreground attribute is defined with a vector or color.</p>

<a class="fragment-anchor" id="adaptive-icon-with-colors"></a><h4>Adaptive Icon with Colors:<a class="header-link" href="#adaptive-icon-with-colors"><i class="glyphicon glyphicon-link"></i></a></h4>

<p>Create a <code>res/values/colors.xml</code> resource file in your project directory to store the app's color definitions.</p>
<div class="highlight"><pre><code class="language-xml" data-lang="xml"><span class="cp">&lt;?xml version="1.0" encoding="utf-8"?&gt;</span>
<span class="nt">&lt;resources&gt;</span>
    <span class="nt">&lt;color</span> <span class="na">name=</span><span class="s">"background"</span><span class="nt">&gt;</span>#FF0000<span class="nt">&lt;/color&gt;</span>
<span class="nt">&lt;/resources&gt;</span>
</code></pre></div>
<p>In the <code>config.xml</code>, we will add <code>resource-file</code> to copy the <code>colors.xml</code> into the approprate location so that the colors are available during build time.</p>
<div class="highlight"><pre><code class="language-xml" data-lang="xml"><span class="nt">&lt;platform</span> <span class="na">name=</span><span class="s">"android"</span><span class="nt">&gt;</span>
  <span class="nt">&lt;resource-file</span> <span class="na">src=</span><span class="s">"res/values/colors.xml"</span> <span class="na">target=</span><span class="s">"/app/src/main/res/values/colors.xml"</span> <span class="nt">/&gt;</span>

  <span class="nt">&lt;icon</span> <span class="na">background=</span><span class="s">"@color/background"</span> <span class="na">density=</span><span class="s">"ldpi"</span> <span class="na">foreground=</span><span class="s">"res/icon/android/ldpi-foreground.png"</span> <span class="nt">/&gt;</span>
  <span class="nt">&lt;icon</span> <span class="na">background=</span><span class="s">"@color/background"</span> <span class="na">density=</span><span class="s">"mdpi"</span> <span class="na">foreground=</span><span class="s">"res/icon/android/mdpi-foreground.png"</span> <span class="nt">/&gt;</span>
  <span class="nt">&lt;icon</span> <span class="na">background=</span><span class="s">"@color/background"</span> <span class="na">density=</span><span class="s">"hdpi"</span> <span class="na">foreground=</span><span class="s">"res/icon/android/hdpi-foreground.png"</span> <span class="nt">/&gt;</span>
  <span class="nt">&lt;icon</span> <span class="na">background=</span><span class="s">"@color/background"</span> <span class="na">density=</span><span class="s">"xhdpi"</span> <span class="na">foreground=</span><span class="s">"res/icon/android/xhdpi-foreground.png"</span> <span class="nt">/&gt;</span>
  <span class="nt">&lt;icon</span> <span class="na">background=</span><span class="s">"@color/background"</span> <span class="na">density=</span><span class="s">"xxhdpi"</span> <span class="na">foreground=</span><span class="s">"res/icon/android/xxhdpi-foreground.png"</span> <span class="nt">/&gt;</span>
  <span class="nt">&lt;icon</span> <span class="na">background=</span><span class="s">"@color/background"</span> <span class="na">density=</span><span class="s">"xxxhdpi"</span> <span class="na">foreground=</span><span class="s">"res/icon/android/xxxhdpi-foreground.png"</span> <span class="nt">/&gt;</span>
<span class="nt">&lt;/platform&gt;</span>
</code></pre></div>
<a class="fragment-anchor" id="standard-icons"></a><h3>Standard Icons<a class="header-link" href="#standard-icons"><i class="glyphicon glyphicon-link"></i></a></h3>
<div class="highlight"><pre><code class="language-xml" data-lang="xml">    <span class="nt">&lt;platform</span> <span class="na">name=</span><span class="s">"android"</span><span class="nt">&gt;</span>
        <span class="c">&lt;!--
            ldpi    : 36x36 px
            mdpi    : 48x48 px
            hdpi    : 72x72 px
            xhdpi   : 96x96 px
            xxhdpi  : 144x144 px
            xxxhdpi : 192x192 px
        --&gt;</span>
        <span class="nt">&lt;icon</span> <span class="na">src=</span><span class="s">"res/android/ldpi.png"</span> <span class="na">density=</span><span class="s">"ldpi"</span> <span class="nt">/&gt;</span>
        <span class="nt">&lt;icon</span> <span class="na">src=</span><span class="s">"res/android/mdpi.png"</span> <span class="na">density=</span><span class="s">"mdpi"</span> <span class="nt">/&gt;</span>
        <span class="nt">&lt;icon</span> <span class="na">src=</span><span class="s">"res/android/hdpi.png"</span> <span class="na">density=</span><span class="s">"hdpi"</span> <span class="nt">/&gt;</span>
        <span class="nt">&lt;icon</span> <span class="na">src=</span><span class="s">"res/android/xhdpi.png"</span> <span class="na">density=</span><span class="s">"xhdpi"</span> <span class="nt">/&gt;</span>
        <span class="nt">&lt;icon</span> <span class="na">src=</span><span class="s">"res/android/xxhdpi.png"</span> <span class="na">density=</span><span class="s">"xxhdpi"</span> <span class="nt">/&gt;</span>
        <span class="nt">&lt;icon</span> <span class="na">src=</span><span class="s">"res/android/xxxhdpi.png"</span> <span class="na">density=</span><span class="s">"xxxhdpi"</span> <span class="nt">/&gt;</span>
    <span class="nt">&lt;/platform&gt;</span>
</code></pre></div>
<a class="fragment-anchor" id="see-also"></a><h3>See Also<a class="header-link" href="#see-also"><i class="glyphicon glyphicon-link"></i></a></h3>

<ul>
<li><a href="https://www.google.com/design/spec/style/icons.html">Android icon guide</a></li>
<li><a href="http://developer.android.com/guide/practices/screens_support.html">Android - Supporting multiple screens</a></li>
</ul>

<a class="fragment-anchor" id="browser"></a><span id="browser"></span><h2>Browser<a class="header-link" href="#browser"><i class="glyphicon glyphicon-link"></i></a></h2>

<p>Icons are not applicable to the Browser platform.</p>

<a class="fragment-anchor" id="ios"></a><span id="ios"></span><h2>iOS<a class="header-link" href="#ios"><i class="glyphicon glyphicon-link"></i></a></h2>
<div class="highlight"><pre><code class="language-xml" data-lang="xml">    <span class="nt">&lt;platform</span> <span class="na">name=</span><span class="s">"ios"</span><span class="nt">&gt;</span>
        <span class="c">&lt;!-- iOS 8.0+ --&gt;</span>
        <span class="c">&lt;!-- iPhone 6 Plus  --&gt;</span>
        <span class="nt">&lt;icon</span> <span class="na">src=</span><span class="s">"res/ios/icon-60@3x.png"</span> <span class="na">width=</span><span class="s">"180"</span> <span class="na">height=</span><span class="s">"180"</span> <span class="nt">/&gt;</span>
        <span class="c">&lt;!-- iOS 7.0+ --&gt;</span>
        <span class="c">&lt;!-- iPhone / iPod Touch  --&gt;</span>
        <span class="nt">&lt;icon</span> <span class="na">src=</span><span class="s">"res/ios/icon-60.png"</span> <span class="na">width=</span><span class="s">"60"</span> <span class="na">height=</span><span class="s">"60"</span> <span class="nt">/&gt;</span>
        <span class="nt">&lt;icon</span> <span class="na">src=</span><span class="s">"res/ios/icon-60@2x.png"</span> <span class="na">width=</span><span class="s">"120"</span> <span class="na">height=</span><span class="s">"120"</span> <span class="nt">/&gt;</span>
        <span class="c">&lt;!-- iPad --&gt;</span>
        <span class="nt">&lt;icon</span> <span class="na">src=</span><span class="s">"res/ios/icon-76.png"</span> <span class="na">width=</span><span class="s">"76"</span> <span class="na">height=</span><span class="s">"76"</span> <span class="nt">/&gt;</span>
        <span class="nt">&lt;icon</span> <span class="na">src=</span><span class="s">"res/ios/icon-76@2x.png"</span> <span class="na">width=</span><span class="s">"152"</span> <span class="na">height=</span><span class="s">"152"</span> <span class="nt">/&gt;</span>
        <span class="c">&lt;!-- Spotlight Icon --&gt;</span>
        <span class="nt">&lt;icon</span> <span class="na">src=</span><span class="s">"res/ios/icon-40.png"</span> <span class="na">width=</span><span class="s">"40"</span> <span class="na">height=</span><span class="s">"40"</span> <span class="nt">/&gt;</span>
        <span class="nt">&lt;icon</span> <span class="na">src=</span><span class="s">"res/ios/icon-40@2x.png"</span> <span class="na">width=</span><span class="s">"80"</span> <span class="na">height=</span><span class="s">"80"</span> <span class="nt">/&gt;</span>
        <span class="c">&lt;!-- iOS 6.1 --&gt;</span>
        <span class="c">&lt;!-- iPhone / iPod Touch --&gt;</span>
        <span class="nt">&lt;icon</span> <span class="na">src=</span><span class="s">"res/ios/icon.png"</span> <span class="na">width=</span><span class="s">"57"</span> <span class="na">height=</span><span class="s">"57"</span> <span class="nt">/&gt;</span>
        <span class="nt">&lt;icon</span> <span class="na">src=</span><span class="s">"res/ios/icon@2x.png"</span> <span class="na">width=</span><span class="s">"114"</span> <span class="na">height=</span><span class="s">"114"</span> <span class="nt">/&gt;</span>
        <span class="c">&lt;!-- iPad --&gt;</span>
        <span class="nt">&lt;icon</span> <span class="na">src=</span><span class="s">"res/ios/icon-72.png"</span> <span class="na">width=</span><span class="s">"72"</span> <span class="na">height=</span><span class="s">"72"</span> <span class="nt">/&gt;</span>
        <span class="nt">&lt;icon</span> <span class="na">src=</span><span class="s">"res/ios/icon-72@2x.png"</span> <span class="na">width=</span><span class="s">"144"</span> <span class="na">height=</span><span class="s">"144"</span> <span class="nt">/&gt;</span>
        <span class="c">&lt;!-- iPad Pro --&gt;</span>
        <span class="nt">&lt;icon</span> <span class="na">src=</span><span class="s">"res/ios/icon-167.png"</span> <span class="na">width=</span><span class="s">"167"</span> <span class="na">height=</span><span class="s">"167"</span> <span class="nt">/&gt;</span>
        <span class="c">&lt;!-- iPhone Spotlight and Settings Icon --&gt;</span>
        <span class="nt">&lt;icon</span> <span class="na">src=</span><span class="s">"res/ios/icon-small.png"</span> <span class="na">width=</span><span class="s">"29"</span> <span class="na">height=</span><span class="s">"29"</span> <span class="nt">/&gt;</span>
        <span class="nt">&lt;icon</span> <span class="na">src=</span><span class="s">"res/ios/icon-small@2x.png"</span> <span class="na">width=</span><span class="s">"58"</span> <span class="na">height=</span><span class="s">"58"</span> <span class="nt">/&gt;</span>
        <span class="nt">&lt;icon</span> <span class="na">src=</span><span class="s">"res/ios/icon-small@3x.png"</span> <span class="na">width=</span><span class="s">"87"</span> <span class="na">height=</span><span class="s">"87"</span> <span class="nt">/&gt;</span>
        <span class="c">&lt;!-- iPad Spotlight and Settings Icon --&gt;</span>
        <span class="nt">&lt;icon</span> <span class="na">src=</span><span class="s">"res/ios/icon-50.png"</span> <span class="na">width=</span><span class="s">"50"</span> <span class="na">height=</span><span class="s">"50"</span> <span class="nt">/&gt;</span>
        <span class="nt">&lt;icon</span> <span class="na">src=</span><span class="s">"res/ios/icon-50@2x.png"</span> <span class="na">width=</span><span class="s">"100"</span> <span class="na">height=</span><span class="s">"100"</span> <span class="nt">/&gt;</span>
        <span class="c">&lt;!-- iPad Pro --&gt;</span>
        <span class="nt">&lt;icon</span> <span class="na">src=</span><span class="s">"res/ios/icon-83.5@2x.png"</span> <span class="na">width=</span><span class="s">"167"</span> <span class="na">height=</span><span class="s">"167"</span> <span class="nt">/&gt;</span>
    <span class="nt">&lt;/platform&gt;</span>
</code></pre></div>
<a class="fragment-anchor" id="see-also"></a><h3>See Also<a class="header-link" href="#see-also"><i class="glyphicon glyphicon-link"></i></a></h3>

<ul>
<li><a href="https://developer.apple.com/library/content/qa/qa1686/_index.html">App Icons on iPad and iPhone</a></li>
</ul>

<a class="fragment-anchor" id="windows"></a><span id="windows"></span><h2>Windows<a class="header-link" href="#windows"><i class="glyphicon glyphicon-link"></i></a></h2>

<p>For Windows the recommended approach to define application icons is to use the <code>target</code> attribute.</p>
<div class="highlight"><pre><code class="language-xml" data-lang="xml">    <span class="nt">&lt;platform</span> <span class="na">name=</span><span class="s">"windows"</span><span class="nt">&gt;</span>
        <span class="nt">&lt;icon</span> <span class="na">src=</span><span class="s">"res/windows/storelogo.png"</span> <span class="na">target=</span><span class="s">"StoreLogo"</span> <span class="nt">/&gt;</span>
        <span class="nt">&lt;icon</span> <span class="na">src=</span><span class="s">"res/windows/smalllogo.png"</span> <span class="na">target=</span><span class="s">"Square30x30Logo"</span> <span class="nt">/&gt;</span>
        <span class="nt">&lt;icon</span> <span class="na">src=</span><span class="s">"res/windows/Square44x44Logo.png"</span> <span class="na">target=</span><span class="s">"Square44x44Logo"</span> <span class="nt">/&gt;</span>
        <span class="nt">&lt;icon</span> <span class="na">src=</span><span class="s">"res/windows/Square70x70Logo.png"</span> <span class="na">target=</span><span class="s">"Square70x70Logo"</span> <span class="nt">/&gt;</span>
        <span class="nt">&lt;icon</span> <span class="na">src=</span><span class="s">"res/windows/Square71x71Logo.png"</span> <span class="na">target=</span><span class="s">"Square71x71Logo"</span> <span class="nt">/&gt;</span>
        <span class="nt">&lt;icon</span> <span class="na">src=</span><span class="s">"res/windows/Square150x150Logo.png"</span> <span class="na">target=</span><span class="s">"Square150x150Logo"</span> <span class="nt">/&gt;</span>
        <span class="nt">&lt;icon</span> <span class="na">src=</span><span class="s">"res/windows/Square310x310Logo.png"</span> <span class="na">target=</span><span class="s">"Square310x310Logo"</span> <span class="nt">/&gt;</span>
        <span class="nt">&lt;icon</span> <span class="na">src=</span><span class="s">"res/windows/Wide310x150Logo.png"</span> <span class="na">target=</span><span class="s">"Wide310x150Logo"</span> <span class="nt">/&gt;</span>
    <span class="nt">&lt;/platform&gt;</span>
</code></pre></div>
<p>where <code>src</code> is the path to the icon which needs to be added.</p>

<p>The Windows platform handles MRT icons automatically, so if you specify <code>src="res/windows/storelogo.png"</code> the following files will be copied into the application's <code>images</code> folder: <code>res/windows/storelogo.scale-100.png</code>, <code>res/windows/storelogo.scale-200.png</code>, etc.</p>

<p>TODO Define what MRT is.</p>

<p>The <code>target</code> attribute specifies the base name for the resultant icons. For every icon file, its destination filename is calculated as <code>target + '.' + MRT_qualifiers + extension(src)</code>. For the icons to display properly in the application, every <code>target</code> value should be one of the icon filenames defined in the application's <code>.appxmanifest</code> file.</p>

<p>Summarizing the above... using the <code>target</code> attribute it is possible to:</p>

<ul>
<li>define a group of icons for different device scale factors using a single <code>&lt;icon ...&gt;</code> element, for example:
<code>xml
&lt;icon src="res/windows/AppListIcon.png" target="Square44x44Logo" /&gt;
</code>
which is equivalent to the following lines:
<code>xml
&lt;icon src="res/windows/Square44x44Logo.scale-100.png" width="44" height="44" /&gt;
&lt;icon src="res/windows/Square44x44Logo.scale-150.png" width="66" height="66" /&gt;
&lt;icon src="res/windows/Square44x44Logo.scale-200.png" width="88" height="88" /&gt;
&lt;icon src="res/windows/Square44x44Logo.scale-240.png" width="106" height="106" /&gt;
</code></li>
<li>define icons with scale factors other than <code>scale-100</code> and <code>scale-240</code> (and any other MRT qualifiers)</li>
</ul>

<p>Although it is not recommended, it is also possible to define icons using the <code>width</code> and <code>height</code> attributes:</p>
<div class="highlight"><pre><code class="language-xml" data-lang="xml">    <span class="nt">&lt;platform</span> <span class="na">name=</span><span class="s">"windows"</span><span class="nt">&gt;</span>
        <span class="nt">&lt;icon</span> <span class="na">src=</span><span class="s">"res/windows/logo.png"</span> <span class="na">width=</span><span class="s">"150"</span> <span class="na">height=</span><span class="s">"150"</span> <span class="nt">/&gt;</span>
        <span class="nt">&lt;icon</span> <span class="na">src=</span><span class="s">"res/windows/smalllogo.png"</span> <span class="na">width=</span><span class="s">"30"</span> <span class="na">height=</span><span class="s">"30"</span> <span class="nt">/&gt;</span>
        <span class="nt">&lt;icon</span> <span class="na">src=</span><span class="s">"res/windows/storelogo.png"</span> <span class="na">width=</span><span class="s">"50"</span> <span class="na">height=</span><span class="s">"50"</span> <span class="nt">/&gt;</span>
        <span class="nt">&lt;icon</span> <span class="na">src=</span><span class="s">"res/windows/Square44x44Logo.scale-100.png"</span> <span class="na">width=</span><span class="s">"44"</span> <span class="na">height=</span><span class="s">"44"</span> <span class="nt">/&gt;</span>
        <span class="nt">&lt;icon</span> <span class="na">src=</span><span class="s">"res/windows/Square44x44Logo.scale-240.png"</span> <span class="na">width=</span><span class="s">"106"</span> <span class="na">height=</span><span class="s">"106"</span> <span class="nt">/&gt;</span>
        <span class="nt">&lt;icon</span> <span class="na">src=</span><span class="s">"res/windows/Square70x70Logo.scale-100.png"</span> <span class="na">width=</span><span class="s">"70"</span> <span class="na">height=</span><span class="s">"70"</span> <span class="nt">/&gt;</span>
        <span class="nt">&lt;icon</span> <span class="na">src=</span><span class="s">"res/windows/Square71x71Logo.scale-100.png"</span> <span class="na">width=</span><span class="s">"71"</span> <span class="na">height=</span><span class="s">"71"</span> <span class="nt">/&gt;</span>
        <span class="nt">&lt;icon</span> <span class="na">src=</span><span class="s">"res/windows/Square71x71Logo.scale-240.png"</span> <span class="na">width=</span><span class="s">"170"</span> <span class="na">height=</span><span class="s">"170"</span> <span class="nt">/&gt;</span>
        <span class="nt">&lt;icon</span> <span class="na">src=</span><span class="s">"res/windows/Square150x150Logo.scale-240.png"</span> <span class="na">width=</span><span class="s">"360"</span> <span class="na">height=</span><span class="s">"360"</span> <span class="nt">/&gt;</span>
        <span class="nt">&lt;icon</span> <span class="na">src=</span><span class="s">"res/windows/Square310x310Logo.scale-100.png"</span> <span class="na">width=</span><span class="s">"310"</span> <span class="na">height=</span><span class="s">"310"</span> <span class="nt">/&gt;</span>
        <span class="nt">&lt;icon</span> <span class="na">src=</span><span class="s">"res/windows/Wide310x150Logo.scale-100.png"</span> <span class="na">width=</span><span class="s">"310"</span> <span class="na">height=</span><span class="s">"150"</span> <span class="nt">/&gt;</span>
        <span class="nt">&lt;icon</span> <span class="na">src=</span><span class="s">"res/windows/Wide310x150Logo.scale-240.png"</span> <span class="na">width=</span><span class="s">"744"</span> <span class="na">height=</span><span class="s">"360"</span> <span class="nt">/&gt;</span>
    <span class="nt">&lt;/platform&gt;</span>
</code></pre></div>
<a class="fragment-anchor" id="see-also"></a><h3>See Also:<a class="header-link" href="#see-also"><i class="glyphicon glyphicon-link"></i></a></h3>

<ul>
<li><a href="https://msdn.microsoft.com/en-us/library/windows/apps/mt412102.aspx">Windows 10 platform guidelines for icons</a>.</li>
<li><a href="https://msdn.microsoft.com/en-us/library/windows/apps/xaml/hh781198.aspx">Windows 8.1 tiles and icons sizes</a></li>
</ul>

<a class="fragment-anchor" id="electron"></a><span id="electron"></span><h2>Electron<a class="header-link" href="#electron"><i class="glyphicon glyphicon-link"></i></a></h2>

<a class="fragment-anchor" id="customizing-the-application's-icon"></a><h3>Customizing the Application's Icon<a class="header-link" href="#customizing-the-application's-icon"><i class="glyphicon glyphicon-link"></i></a></h3>

<p>Customized icon(s) can be declared with the <code>&lt;icon&gt;</code> element(s) in the <code>config.xml</code> file. There are two types of icons that can be defined, the application icon and the package installer icon. These icons should be defined in the Electron's platform node <code>&lt;platform name="electron"&gt;</code>.</p>

<p>One icon can be used for the application and installer, but this icon should be at least <strong>512x512</strong> pixels to work across all operating systems.</p>

<p><em>Notice: If a customized icon is not provided, the Apache Cordova default icons are used.</em></p>

<p><em>Notice: macOS does not display custom icons when using <code>cordova run</code>. It defaults to the Electron's icon.</em></p>
<div class="highlight"><pre><code class="language-xml" data-lang="xml"><span class="nt">&lt;platform</span> <span class="na">name=</span><span class="s">"electron"</span><span class="nt">&gt;</span>
    <span class="nt">&lt;icon</span> <span class="na">src=</span><span class="s">"res/electron/icon.png"</span> <span class="nt">/&gt;</span>
<span class="nt">&lt;/platform&gt;</span>
</code></pre></div>
<p>You can supply unique icons for the application and installer by setting the <code>target</code> attribute. As mentioned above, the installer image should be <strong>512x512</strong> pixels to work across all platforms.</p>
<div class="highlight"><pre><code class="language-xml" data-lang="xml"><span class="nt">&lt;platform</span> <span class="na">name=</span><span class="s">"electron"</span><span class="nt">&gt;</span>
    <span class="nt">&lt;icon</span> <span class="na">src=</span><span class="s">"res/electron/app.png"</span> <span class="na">target=</span><span class="s">"app"</span> <span class="nt">/&gt;</span>
    <span class="nt">&lt;icon</span> <span class="na">src=</span><span class="s">"res/electron/installer.png"</span> <span class="na">target=</span><span class="s">"installer"</span> <span class="nt">/&gt;</span>
<span class="nt">&lt;/platform&gt;</span>
</code></pre></div>
<p>For devices that support high-DPI resolutions, such as Apple's Retina display, you can create a set of images with the same base filename but suffix with its multiplier.</p>

<p>For example, if the base image's filename <code>icon.png</code> and is the standard resolution, then <code>icon@2x.png</code> will be treated as a high-resolution image that with a DPI doubled from the base.</p>

<ul>
<li>icon.png (256px x 256px)</li>
<li>icon@2x.png (512px x 512px)</li>
</ul>

<p>If you want to support displays with different DPI densities at the same time, you can put images with different sizes in the same folder and use the filename without DPI suffixes. For example:</p>
<div class="highlight"><pre><code class="language-xml" data-lang="xml"><span class="nt">&lt;platform</span> <span class="na">name=</span><span class="s">"electron"</span><span class="nt">&gt;</span>
    <span class="nt">&lt;icon</span> <span class="na">src=</span><span class="s">"res/electron/icon.png"</span> <span class="nt">/&gt;</span>
    <span class="nt">&lt;icon</span> <span class="na">src=</span><span class="s">"res/electron/icon@1.5x.png"</span> <span class="nt">/&gt;</span>
    <span class="nt">&lt;icon</span> <span class="na">src=</span><span class="s">"res/electron/icon@2x.png"</span> <span class="nt">/&gt;</span>
    <span class="nt">&lt;icon</span> <span class="na">src=</span><span class="s">"res/electron/icon@4x.png"</span> <span class="na">target=</span><span class="s">"installer"</span> <span class="nt">/&gt;</span>
<span class="nt">&lt;/platform&gt;</span>
</code></pre></div>

            



