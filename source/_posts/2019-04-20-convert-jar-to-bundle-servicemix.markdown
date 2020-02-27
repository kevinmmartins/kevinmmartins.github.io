---
layout: post
title:  "Convert JAR to bundle in ServiceMix"
date:   2019-04-20 18:04:52
comments: true
image: https://svn.apache.org/repos/asf/servicemix/sandbox/images/logo-smx-tm-feather.png
categories: servicemix
---
Sometimes we need to add a new bundle in Servicemix being a Jar.
Performing the conversion and installing in OSGI may not be easy however this tutorial will help you.

Execute the command:

```
./bin/servicemix
```

Ubuntu :

```
osgi:install -s wrap:file:////"jar_location Ex: /lib/ojdbc6-13.jar"
```

Windows:

```
osgi:install -s wrap:file:"jar location Ex: D:/lib/ojdbc6-13.jar"
```

Execute shutdown command, choose yes option.

Now your Jar will be avaliable
