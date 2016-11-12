# EPAgent Plug-ins for RabbitMQ

# Description

The EPAgent Plug-ins for RabbitMQ monitors RabbitMQ messaging broker.

* The RabbitMQ_Bindings.pl script gathers binding statistics.
* The RabbitMQ_Channels.pl script gathers channel statistics.
* The RabbitMQ_Connections.pl script gathers connection statistics.
* The RabbitMQ_Exchanges.pl script gathers exchange statistics.
* The RabbitMQ_Nodes.pl script gathers node statistics.
* The RabbitMQ_Queues.pl script gathers queue statistics.

For installation instructions, see the README.md file.

#Short Description

The EPAgent Plug-ins for RabbitMQ monitors RabbitMQ messaging broker.

# APM Version
Tested with CA APM 9.1.4.0 Enterprise Manager, EPAgent 9.1.4.0, RabbitMQ 3.3.0, PERL 5.10.1, and Python 2.7.6.

# Dependencies
Tested with CA APM 9.1.4.0 Enterprise Manager, EPAgent 9.1.4.0, RabbitMQ 3.3.0, PERL 5.10.1, and Python 2.7.6.

# Licensing
Apache License, version 2.0. See [Licensing](https://www.apache.org/licenses/LICENSE-2.0).

# Prerequisite
An installed and configured EPAgent.

Find the version 9.1 to 9.5 documentation on [CA Support,](https://support.ca.com)

Find the version 9.6 to 10.x documentation on [the CA APM wiki at docops.ca.com.](https://docops.ca.com)

# Plug-in Installation and Configuration

1. Extract the plug-in to <*EPAgent_Home*>\epaplugins.
2. Configure the IntroscopeEPAgent.properties file in <*EPAgent_Home*> by adding these stateless plug-in properties:
```
	introscope.epagent.plugins.stateless.names=BINDINGS,CHANNELS,CONNECTIONS,EXCHANGES,NODES,QUEUES (can be appended to a previous entry)
	introscope.epagent.stateless.BINDINGS.command=perl <epa_home>/epaplugins/rabbitmq/RabbitMQ_Bindings.pl --host=HOST_OR_IP_ADDR --port=12345 --user=USERNAME --pswd=PASSWORD
	introscope.epagent.stateless.BINDINGS.delayInSeconds=900
	introscope.epagent.stateless.CHANNELS.command=perl <epa_home>/epaplugins/rabbitmq/RabbitMQ_Channels.pl --host=HOST_OR_IP_ADDR --port=12345 --user=USERNAME --pswd=PASSWORD
	introscope.epagent.stateless.CHANNELS.delayInSeconds=900
	introscope.epagent.stateless.CONNECTIONS.command=perl <epa_home>/epaplugins/rabbitmq/RabbitMQ_Connections.pl --host=HOST_OR_IP_ADDR --port=12345 --user=USERNAME --pswd=PASSWORD
	introscope.epagent.stateless.CONNECTIONS.delayInSeconds=900
	introscope.epagent.stateless.EXCHANGES.command=perl <epa_home>/epaplugins/rabbitmq/RabbitMQ_Exchanges.pl --host=HOST_OR_IP_ADDR --port=12345 --user=USERNAME --pswd=PASSWORD
	introscope.epagent.stateless.EXCHANGES.delayInSeconds=900
	introscope.epagent.stateless.NODES.command=perl <epa_home>/epaplugins/rabbitmq/RabbitMQ_Nodes.pl --host=HOST_OR_IP_ADDR --port=12345 --user=USERNAME --pswd=PASSWORD
	introscope.epagent.stateless.NODES.delayInSeconds=900
	introscope.epagent.stateless.QUEUES.command=perl <epa_home>/epaplugins/rabbitmq/RabbitMQ_Queues.pl --host=HOST_OR_IP_ADDR --port=12345 --user=USERNAME --pswd=PASSWORD
	introscope.epagent.stateless.QUEUES.delayInSeconds=900
```
# Usage

1. Download a copy of the RabbitMQ Management Commandline Tool, [rabbitmqadmin.py.](https://www.rabbitmq.com/management-cli.html)
2. Place the rabbitmqadmin.py file into the <*EPAgent_Home*>\epaplugins directory.
3. Start the EPAgent using the control script in the <*EPAgent_Home*>/bin directory.

# Debug and Troubleshoot
Update the root logger in <*EPAgent_Home*>/IntroscopeEPAgent.properties from INFO to DEBUG, then save. No managed appklication restart needed.

You can also manually execute the plug-in from a console and use the PERL built-in debugger.

Carefully read each plug-in POD section for details about how to run the plug-ins in debug mode. When you are using a newer version than what was tested, the vendor has probabably changed the number of columns in the TSV output. You will notice the difference by comparing the output to the program. Adjust the program accordingly.

# Limitation

Some users have reported and verified that the EPAgent Plug-ins for RabbitMQ output has changed in newer versions of RabbitMQ.
Validate the new output against the the output used to create the EPAgent Plug-ins for RabbitMQ.

# Support
This document and plug-in are made available from CA Technologies. They are provided as examples at no charge as a courtesy to the CA APM Community at large. This plug-in might require modification for use in your environment. However, this plug-in is not supported by CA Technologies, and inclusion in this site should not be construed to be an endorsement or recommendation by CA Technologies. This plug-in is not covered by the CA Technologies software license agreement and there is no explicit or implied warranty from CA Technologies. The plug-in can be used and distributed freely amongst the CA APM Community, but not sold. As such, it is unsupported software, provided as is without warranty of any kind, express or implied, including but not limited to warranties of merchantability and fitness for a particular purpose. CA Technologies does not warrant that this resource will meet your requirements or that the operation of the resource will be uninterrupted or error free or that any defects will be corrected. The use of this plug-in implies that you understand and agree to the terms listed herein.
Although this plug-in is unsupported, please let us know if you have any problems or questions. You can add comments to the CA APM Community site so that the author(s) can attempt to address the issue or question.
Unless explicitly stated otherwise this plug-in is only supported on the same platforms as the CA APM Java agent. 

# Support URL
https://github.com/htdavis/ca-apm-fieldpack-epa-rabbitmq/issues

# Product Compatibilty Matrix
http://pcm.ca.com/

# Categories
Middleware/ESB

# Change Log
Changes for each plug-in version.

Version | Author | Comment
--------|--------|--------
1.0 | Hiko Davis | First version of the plug-ins.