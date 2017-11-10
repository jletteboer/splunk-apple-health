Apple Health App for Splunk
===========================

Requirements
------------
* [**Splunk Enterprise 6.6+**](https://www.spunk.com)
* [**Apple Health**](https://www.apple.com/ios/health/)

**Installed Splunk Add-ons**

* [**Machine Learning Toolkit**](https://splunkbase.splunk.com/app/2890/)
* [**Python for Scientific Computing**](https://splunkbase.splunk.com/app/2890/#/details)
* [**Punchcard**](https://splunkbase.splunk.com/app/3129/)
* [**Status Indicator**](https://splunkbase.splunk.com/app/3119/)

Installation
------------

**Method: #1**

#### Install via Splunk Package

First, you'll need to export a Splunk Package by cloning the repo and exporting
the contents.

```
$ git clone https://github.com/jletteboer/splunk-apple-health.git apple_health
$ cd apple_health
$ git archive \
    --format=tar.gz \
    --prefix= apple_health/ \
    --output= apple_health.tar.gz \
    HEAD
$ mv apple_health.tar.gz apple_health.spl
```

After exporting the Splunk Package `.spl`, you can install the package using
Splunk's built-in Apps page.

1. Select "Manage Apps" from the Apps dropdown.
1. Select the "Install app from file" button.
1. Select the generated `apple_health.spl ` package.
1. Splunk will walk you through all required setup.

External Resource: Splunk GUI Installation Interface - [Splunk Documentation - Install App](https://docs.splunk.com/Documentation/AddOns/released/Overview/Distributedinstall "Splunk Docs")


**Method: #2**

#### Install via Git Clone

You can install the git repository directly into your Splunk app contents and
keep the scripts updated.

```
$ export SPLUNK_HOME="/path/to/Splunk"
$ cd $SPLUNK_HOME/etc/apps
$ git clone https://github.com/jletteboer/splunk-apple-health.git apple_health
```

Restart Splunk after cloning the repository.

Adding your own Apple Health data
--------------------------------

Follow my [blog](http://www.networkx.nl/data-science/visualising-health-data/) for exporting, transforming the data.

If the data is transformed save the csv files into the **$SPLUNK\_HOME/etc/apps/apple_health/data/** directory.

License
-------

See [LICENSE](LICENSE) file.

Screenshots
-----------
![alt text](http://www.networkx.nl/wp-content/uploads/2017/09/num1.png)
![alt text](http://www.networkx.nl/wp-content/uploads/2017/09/num2.png)