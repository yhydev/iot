---
keyword: [Internet of Things, IoT, IoT Platform, IoT application, device]
---

# Terms

The article describes the terms that are used in IoT Platform.

## Terms

|Term|Description|
|----|-----------|
|product|A product is a set of devices that have the same features. IoT Platform issues a unique ProductKey for each product.|
|device|A physical device that belongs to a product. IoT Platform issues a DeviceName that is unique under the same product for each device. Devices can directly connect to IoT Platform, or be attached as sub-devices to a gateway that is connected to IoT Platform.|
|group|IoT Platform allows you to create device groups. Each device group can contain devices of different products. You can use device groups to manage devices across products.|
|gateway|A gateway can directly connect to IoT Platform and allows you to manage sub-devices. Sub-devices can communicate with IoT Platform only by using a gateway.|
|sub-device|Sub-devices cannot directly connect to IoT Platform and must be attached to a gateway.|
|device certificate|A device certificate consists of ProductKey, DeviceName, and DeviceSecret. -   ProductKey is the unique identifier of a product in IoT Platform. This parameter is required in device authentication and communication. You must safely keep this parameter.
-   DeviceName is the device name that is generated by IoT Platform during device registration. You can also upload custom device names. Each device has a unique DeviceName under the same product. This parameter is required in device authentication and communication. You must safely keep this parameter.
-   DeviceSecret is the private key that is issued by IoT Platform for each device. DeviceSecret is used in pair with DeviceName. This parameter is required in device authentication and communication. You must safely keep this parameter. |
|ProductSecret|ProductSecret is the private key that is issued by IoT Platform for each product. ProductSecret is used in pair with ProductKey for unique-certificate-per-product authentication. This parameter is required in device authentication and communication. You must safely keep this parameter.|
|Topic|A topic is a UTF-8 character string that is used as a transmission medium during publish/subscribe communication. A device can publish messages to a topic or subscribe to messages from a topic.|
|topic category|A topic category is a set of topics that are associated with different devices under the same product. $\{productKey\} and $\{deviceName\} are used to specify a unique device. A topic category is applicable to all devices under the same product.|
|Publish|The allowed operation of a topic. If the Allowed Operation parameter of a topic is set to Publish, you can publish messages to the topic.|
|Subscribe|The allowed operation of a topic. If the Allowed Operation parameter of a topic is set to Subscribe, you can subscribe to messages from the topic.|
|RRPC|RRPC is short for revert-RPC. A remote procedure call \(RPC\) uses the client/server mode, and allows you to request a remote service without understanding the underlying protocol. An RRPC allows you to send a request from the server to a device and receive a response from the device.|
|tag|You can add tags to products, devices, and groups. -   Product tags are used to describe the information that is common to all devices under the same product.
-   Device tags are used to describe the unique features of devices. You can add custom tags based on your needs.
-   Group tags are used to describe the information that is common to all devices in a group. |
|Alink protocol|The protocol for communication between the devices and IoT Platform.|
|TSL model|IoT Platform uses the Thing Specification Language \(TSL\) to describe device features. A TSL model defines the device properties, services, and events. TSL models use the JSON format. You can organize data based on a TSL model and submit the data to IoT Platform.|
|property|A TSL feature that describes the running status of a device, such as the temperature information that is collected by an environmental monitoring device. Properties support the GET and SET request methods. Applications can send requests to retrieve and set properties.|
|desired property value|IoT Platform allows you to set desired property values for a device. If the device is online, the property values on the device is updated in real time. If the device is offline, the desired property values are cached in IoT Platform. After the device goes online, it obtains the desired property values and updates the property values on the device.|
|service|A TSL feature that describes the capabilities or methods of a device. These capabilities or methods can be used by external requesters. You can specify the input and output parameters of a service. Compared with properties, services can use one command to implement more complex business logic, such as performing a specific task.|
|event|A TSL feature that describes the runtime events of a device. Typically, an event contains a notification that requires action or attention. An event may contain multiple output parameters. For example, an event may be a notification that a task is completed, a device fault that has occurred, or a temperature alert. You can subscribe to or push events.|
|data parsing script|For devices that use pass-through or custom-format data, you must write data parsing scripts in IoT Platform to parse the data. You must convert the binary data or custom JSON data that is submitted by the devices to the Alink JSON data that is supported by IoT Platform. You must also convert the Alink JSON data that is sent by IoT Platform to the custom-format data that is supported by the devices.|
|device shadow|A device shadow is a JSON file that is used to store the status information of a device or application. Each device has a unique device shadow in IoT Platform. Device shadows allow you to obtain and set the status of devices by using the MQTT or HTTP protocol regardless of whether the devices are connected to the Internet.|
|rules engine|You can create and configure rules in IoT Platform to achieve the following features: server-side subscription, data forwarding, and scene orchestration.|
|server-side subscription|Your business server can subscribe to messages of a product in IoT Platform. The following types of messages are included: upstream device messages, notifications of device status changes, notifications when a gateway discovers new sub-devices, notifications of device lifecycle changes, and notifications of device topology changes. Server-side subscription supports the following two methods: -   AMQP: uses the Advanced Message Queuing Protocol \(AMQP\) to implement a server-side subscription. Your server connects to IoT Platform by using the AMQP protocol and receives messages from IoT Platform.
-   MNS: forwards messages to a specified Message Service \(MNS\) queue. Then, your server receives messages from the MNS queue. |
|data forwarding|You can use the data forwarding feature to forward data from a topic to another topic or another Alibaba Cloud service for storage or processing.|
|scene orchestration|You can use the scene orchestration feature to develop automated business logic in a visualized manner. You can define interaction rules between devices and deploy the rules in IoT Platform or edge instances.|
|unique-certificate-per-device authentication|A device certificate is burned to each device. The device certificate includes a ProductKey, DeviceName, and DeviceSecret. When you connect a device to IoT Platform, IoT Platform authenticates the device based on the certificate.|
|unique-certificate-per-product authentication|A product certificate is burned to all devices under the same product. A product certificate includes a ProductKey and ProductSecret. When a device sends an activation request, IoT Platform authenticates the device based on the certificate. If the authentication succeeds, IoT Platform issues a DeviceSecret to the device. Then, the device uses the DeviceSecret to connect with IoT Platform.|
|public instance|You can manage resources such as products, devices, and rules in IoT Platform instances.IoT Platform provides public instances by default. Public instances are deployed on Alibaba Cloud classic networks. Each public instance is shared by multiple Alibaba Cloud accounts. These accounts are logically isolated. |

