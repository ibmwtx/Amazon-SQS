# Amazon-SQS

Amazon Simple Queue Service (SQS) is a fast, reliable, scalable, fully managed message queuing service. SQS makes it simple and cost-effective to decouple the components of a cloud application. You can use SQS to transmit any volume of data, at any level of throughput, without losing messages or requiring other services to be always available. ITX SQS adapter supports reading , writing and listen message on a SQS queue.

Minimum Requirements :

ITX v9.0.0.x

Command Alias :

Adapter commands can be specified by using a command string on the command line or creating a command file that contains adapter commands. The execution command syntax is:

-IM[alias] card_num
-OM[alias] card_num

where -IM is the Input Source Override execution command and -OM is the Output Target Override execution command, alias is the adapter alias, and card_num is the number of the input or output card. The following table shows the adapter alias and its execution command.

Adapter : Amazon Simple Notification Service
Alias : ASQS
As Input : -IMASQScard_num
As Output : -OMASQScard_num
Amazon SQS Adapter commands

The following table lists valid commands for the Amazon SNS Adapter. The adapter supports only outbound.

Queue Name (-Q) : SQS Queue Name
Access Key (-A) : Access Key to connect to the SNS Service
Secret Key (-S ) : Secret Key
Time out (-O) : Visibility Time out (http://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/AboutVT.html)
Listen (-L) : Listen interval on the Queue in milliseconds
Preserve (-P) : Preserve the messages. 
Batch (-B) : Number of messages to read

Amazon SNS Adapter Command Line Examples

Inbound Adapter : 

Adapter Command Line : -A ***  -S ***  -Q queue_1
GET RULE : GET ("ASQS", "-A ***  -S ***  -Q queue_1")

Outbound Adapter :

Line :-A **** -S *** -Q queue_1 -B 2 -L 10
PUT RULE : PUT("ASQS", "-A **** -S *** -Q queue_1 -T", Input))


Amazon Adapter Installation Instructions

a) create a folder com.ibm.itx.amazon.sqs under WTX INSTALL/jars directory b) Drop m4sqs.jar in to WTX INSTALL/jars/com.ibm.itx.amazon.sqs
c) Edit adapters.xml and add the following line

<M4Adapter name="Amazon SQS" alias="ASQS" id="175" type="app" class="com/ibm/itx/amazon/sqs"/>

d) Download Amazon SNS SDK Java artifacts from Tools for Amazon Web Services. From the zip file, Copy aws-java-sdk-1.xxx.jar, ccommons-codec-1.xx.jar, commons-lang3-xxx.jar.jar, commons-logging-1.xx.jar, pofluent-hc-4.xx.jar,httpclient-xx.jar, httpclient-cache-4.xx.jar, httpcore-4.xx.jar, httpmime-4.xx.jar, jackson-annotations-2.xx.jar, jackson-core-2.xx.jar, jackson-databind-2.x.jar and joda-time-2.x.jar to WTX INSTALL DIR/jars/com.ibm.itx.amazon.sqs

d) Invoke cleanextenderstudio.bat to invoke Design Studio
Note : For any defects or usage concerns, please open an issue ticket and shall be addressed.
