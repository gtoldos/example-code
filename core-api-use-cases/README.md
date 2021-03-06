Cyc Core API Use Cases
======================

This project provides examples of common usage of the 
[Cyc Core API Suite](https://github.com/cycorp/api-suite).

It is generally recommended that you download the latest release of the Core API Use Cases from the
[releases page](https://github.com/cycorp/example-code/releases), as it will rely on the latest
_released version_ of the Core APIs.

For more information, visit the [Cyc Developer Center](http://dev.cyc.com/).


Requirements
------------

### Java

* `JDK 1.7` or greater.
* [Apache Maven](http://maven.apache.org/), version `3.2` or higher. If you are new to Maven, you 
  may wish to view the [quick start](http://maven.apache.org/run-maven/index.html).

### Cyc Core API Suite

You have two options:

If you are using a [tagged release](https://github.com/cycorp/example-code/releases) of the Core
API Use Cases project, Maven will automatically download and install appropriate versions of the 
Core API libraries for you.

If you are using the latest version of the Use Cases from the 
[git repository](https://github.com/cycorp/example-code), then you will need to manually build
and install the latest \*-SNAPSHOT version of the [Core APIs](https://github.com/cycorp/api-suite)
from source.

### Cyc Server

All of these examples can be run against **ResearchCyc 4.0q** or higher.

All of the code demonstrated here is compatible with **EnterpriseCyc 1.7-preview** or higher, but 
note that, by design, EnterpriseCyc does not contain the _KB content_ necessary to run these 
specific examples.

The Core APIs also include support for the planned upcoming release of **OpenCyc 5.0-preview**,
although OpenCyc does not have support for advanced features such as QuerySearch or 
ProofViewJustification. Classes and methods which are not supported by OpenCyc will reflect this in 
their javadoc description and in their signature by declaring that they throw a 
`com.cyc.session.exception.OpenCycUnsupportedServerException`. All of the example code in 
`com.cyc.core.examples.basics` demonstrates OpenCyc-supported functionality. 

For inquiries about obtaining a suitable version of Cyc, please visit the
[Cyc Dev Center downloads page](http://dev.cyc.com/downloads/).


Getting Started
---------------

This project is intended to demonstrate common usages of the Cyc APIs. It's built in Maven, and it 
should be straightforward to open, modify, and run the examples from any common Java IDE (IntelliJ, 
NetBeans, Eclipse, etc.)

**Note:** Running these examples will alter a Cyc server's KB contents. These code samples should 
not be run against a production system.

Running any code that requires a Cyc server will pop up a GUI panel asking for a Cyc server address.
You may instead specify a Cyc server by setting the Java System property `cyc.session.server` to 
your server's location, in the format `[HOST_NAME]:[BASE_PORT]`; e.g., 
`cyc.session.server=localhost:3600`. See your IDE's documentation for details.

You can also run a particular class from the command line. First, build the project:

    mvn clean compile

Then, for example, if you wanted to run the `BasicWalkthrough` class against a Cyc server at 
`localhost:3600`, you would issue the following command:

    mvn exec:java -Dexec.mainClass="com.cyc.core.examples.basics.BasicWalkthrough" -Dcyc.session.server=localhost:3600

### Logging

Warning and error messages from the Cyc APIs are logged to the console, as well as to a logfile at
`target/cyc-core-use-cases.log`. Note that this logfile will be erased every time the `mvn clean` 
command is run.

If you wish to modify the logging configuration for the Cyc APIs, you can change the settings in 
`src/main/resources/log4j.properties`.


Knowledge Editing and Ontology Development
------------------------------------------

A Cyc application is only as good as the knowledge in Cyc's KB. Read up on 
[ontology development](http://dev.cyc.com/ontology-development/).


Further Documentation
---------------------

Further API documentation, including Javadocs, is available at 
[Cyc Developer Center](http://dev.cyc.com/api/).


Contact
-------

For questions about the APIs or issues with using them, please visit the 
[Cyc Dev Center issues page](http://dev.cyc.com/issues/).
