# Hubs for institutions, collaborations, labs, and larger projects

Institutional Xena Hubs allow you to share data, visualizations, and analyses with a specific group of people. Xena Hubs can be set up on any server or in the cloud. You control who has access to the Xena Hub by controlling who has access to the server on which it is hosted.

To make your data publicly available, simply make the server open to the web.

## Download

First, download the ucsc\_xena\_xxx.tar.gz file to your server, here:

[https://genome-cancer.ucsc.edu/download/public/get-xena/index.html](https://genome-cancer.ucsc.edu/download/public/get-xena/index.html)

The file to download is the one called "**Tar archive, no updater or JRE - recommended for linux server** **developments**". Uncompress and extract the .jar file (cavm-xxx-standalone.jar). The current version is 0.25.0.

## Start the hub

The hub can be started with "java -jar cavm-xxx-standalone.jar". Passing option --help will display usage information.

Note that you need to use Java 8 to run the hub.&#x20;

There are several options you will want to set.

To bind an external interface (instead of loopback), use "--host 0.0.0.0".

The connection between your hub and the Xena Browser is through https, use "--certfile" and "--keyfile" options to set them.

There are three paths that can be configured: the database file, the log file, and the root directory for data files to be served. These are set by --database, --logfile, and --root. If you don't set these, they will default to paths under ${HOME}/xena.

```
--database -d default to ${HOME}/xena/database
```

```
--logfile default to ${HOME}/xena/xena.log
```

```
--root -r default to ${HOME}/xena/files/
```

## Example start script for an open-access hub

Copy the content below to a file "start\_script"

```
#!/bin/bash

PORT=7222
LOGFILE=xena/xena7222.log 
DOCROOT=xena/files
DB=xena/myHub

java -jar server.jar -r ${DOCROOT} -d ${DB} --no-gui -p ${PORT} -H 0.0.0.0 --logfile ${LOGFILE} --certfile ${CERTFILE} --keyfile ${KEYFILE}> log 2>&1 &

disown
```

Link server.jar to cavm-x.xx.x-standalone.jar

```
ln -sf cavm-0.xx.0-standalone.jar server.jar
```

Make "start\_script" executable

```
chmod u+x start_script
```

Run "./start\_script"

```
./start_script
```

Your hub is now running on "https://computer-external-ip:7223".

## Getting a security certificate for an open-access hub

When a Xena Hub starts, it opens two consecutive ports, for http and https connections, e.g. 7222 and 7223. HTTP is always the lower number, and HTTPS is always the higher number. This means your hub has two urls

[http://ip:7222](http://ip:7222) or [https://ip:7223](https://ip:7223)&#x20;

**Connecting via HTTP to the hub is no longer supported by modern web browsers, thus you will need to connect via HTTPS**. To do this you will need an HTTPS certificate and private key. Paths to the cert and key are set with --certfile and --keyfile. This might seem redundant for a hub behind a firewall, but the web app has no influence over the security policies of the web browser. HTTPS certificates can be acquired from free public Certificate Authorities, or via NIH InCommon.

Note that [the section below detailing a way to utilize ssh tunneling to get around this](hubs-for-institutions-collaborations-labs-and-larger-projects.md#if-you-dont-have-a-security-certificate-yet), which can be used for testing purposes only.

## Make your data ready

You will need to make your data file ready just like for local Xena hub on your laptop. Please see instructions on [data format specifications](https://ucsc-xena.gitbook.io/project/local-xena-hub/data-format-specifications).

You will also need to make your data's meta-data file (xxx.json) ready. Please see [loading data from the command line](loading-data-from-the-command-line.md) for instructions.

## Load data through command line

Once the hub is running, and input files have been placed in the --root directory, a file can be loaded by running the jar a second time, with the -l option, like

```
ln -sf cavm-x.xx.x-standalone.jar server.jar
```

## Delete data through command line

If your hub is run on the default 7222 port, you can load data with

```
java -jar server.jar -l /path/to/root/file.tsv
```

If your hub is running on a different port, you load data with

```
java -jar server.jar -p ${PORT} -l /path/to/root/file.tsv
```

Please contact us at genome-cancer@soe.ucsc.edu for more assistance.

If your hub is run on the default 7222 port, you can delete data with

```
java -jar server.jar -x /path/to/root/file.tsv
```

If your hub is running on a different port, you delete data with

```
java -jar server.jar -p ${PORT} -l /path/to/root/file.tsv
```

## Viewing data from the hub

Go to Data Hub page [here](https://xenabrowser.net/hub/), add "https:computer-external-ip:7223"

You can now go to the visualization and add a cohort or study listed in your hub.

### If you don't have a security certificate yet

If you don't have a security certificate yet but you would like to verify that the hub is working you can use ssh tunneling. An example of how to do this for AWS is below, where it is assumed that the xena hub is running on port 7222 for http and 7223 for https. In this scenario, you start the hub without using --certfile and --keyfile options.

Assuming that you typically ssh into EC2 on AWS like this,

```
ssh -i "xena.pem" ec2-user@ec2-11-111-11-111.compute-1.amazonaws.com
```

you will now set up an ssh tunnel to port 8000 on your computer. To do this we add the -L option:

```
ssh -i "xena.pem" -L 8000:localhost:7222 ec2-user@ec2-11-111-11-111.compute-1.amazonaws.com
```

Now on your computer, http://localhost:8000 is the same as the http://aws-ip:7222.  Chrome Browser does not allow a connection to http://aws-ip:7222, but it will allow a connection to http://localhost:8000.

After setting up the ssh tunnel go to Data Hub page [here](https://xenabrowser.net/hub/), add "http://localhost:8000".

## How to set up my hub to have a url like [https://tcga.xenahubs.net](https://tcga.xenahubs.net)

Alternatively, you can run the hub behind a reverse proxy, and attach the certificate and keyfile to Apache, Nginx or AWS load balancer configurations. In this scenario, you start the hub without using --certfile and --keyfile options. This is useful if you want your hub to have a url like "[https://tcga.xenahubs.net](https://tcga.xenahubs.net)". You set up your DNS to point the hostname (tcga.xenahubs.net) to ip address of the server on which the hub is running.&#x20;

An example apache configuration on AWS VM

in /etc/httpd/conf/httpd.conf

```
<VirtualHost *:443>
    ServerName tcga.xenahubs.net
    SSLEngine on
    SSLProxyEngine On
    SSLProxyVerify none
    SSLProxyCheckPeerCN off
    SSLProxyCheckPeerName off
    SSLProxyCheckPeerExpire off
    SSLCertificateFile YOURCERTIFICATE
    SSLCertificateKeyFile YOURKEY
    # setup the proxy                                                                                                                                                                                          
    ProxyPreserveHost On
    ProxyPass / https://localhost:9000/
    ProxyPassReverse / https://localhost:9001/
</VirtualHost>
```

## A landing page for my hub

If you have a markdown file called $DOCROOT/data/meta/info.mdown in your hub's document root directory, the markdown file will serve as a splash page for your hub. An example is the _UCSC Toil RNA-seq Recompute_ hub: [https://toil.xenahubs.net](https://atacseq.xenahubs.net). The corresponding markdown file is [this](https://github.com/ucscXena/cohortMetaData/blob/master/hub\_toil.xenahubs.net/info.mdown).

### How do I add a 'Launch Xena' button like the _TOIL_ landing page

`<button class="hubButton" data-cohort="TCGA TARGET GTEx">Launch Xena</button>`

To add a clickable button in the hub landing page, make sure the button has classname **'hubButton'**. You also need to specify the cohort to view, defined by the data parameter **'data-cohort'**. Once users click the button, the visualization wizard will be launched to the specified cohort. You can change the button label.

## A landing page for my cohort

You can also have a landing page for a study cohort. An example is the _TCGA TARGET GTEx_ cohort: [https://xenabrowser.net/datapages/?cohort=TCGA%20TARGET%20GTEx](https://xenabrowser.net/datapages/?cohort=TCGA%20TARGET%20GTEx\&removeHub=https%3A%2F%2Fxena.treehouse.gi.ucsc.edu%3A443). The corresponding markdown file is [this](https://github.com/ucscXena/cohortMetaData/blob/master/hub\_toil.xenahubs.net/info.mdown). The study cohort landing page is also a markdown file, which must be hosted in the [https://github.com/ucscXena/cohortMetaData](https://github.com/ucscXena/cohortMetaData) repository on github. The markdown file called https://github.com/ucscXena/cohortMetaData/cohort\_$cohortName/info.mdown.

### How do I add a "Launch" button like the _TCGA TARGET GTEx_  landing page

`<button class="cohortButton" data-bookmark="bc7f3f46b042bcf5c099439c2816ff01">Example: compare FOXM1 expression</button>`

The button must has a classname **'cohortButton'**. If you have the data parameter '**data-bookmark**', clicking the button will take the user to the bookmark view.  If you don't have the '**data-bookmark**' parameter, clicking the button will take the user to the visualization wizard with an empty spreadsheet. You can change the button label. You can as many button as you want.&#x20;
