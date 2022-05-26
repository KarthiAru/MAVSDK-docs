# mavsdk::MavlinkPassthrough Class Reference
`#include: mavlink_passthrough.h`

----


The [MavlinkPassthrough](classmavsdk_1_1_mavlink_passthrough.md) class provides direct MAVLink access. 


"With great power comes great responsibility." - This plugin allows you to send and receive MAVLink messages. There is no checking or safe-guards, you're on your own, and you have been warned. 


## Data Structures


struct [CommandInt](structmavsdk_1_1_mavlink_passthrough_1_1_command_int.md)

struct [CommandLong](structmavsdk_1_1_mavlink_passthrough_1_1_command_long.md)

## Public Types


Type | Description
--- | ---
enum [Result](#classmavsdk_1_1_mavlink_passthrough_1a265eacaeea064a31de3fe16d1e357793) | Possible results returned for requests.

## Public Member Functions


Type | Name | Description
---: | --- | ---
&nbsp; | [MavlinkPassthrough](#classmavsdk_1_1_mavlink_passthrough_1ad17fc20d2b7c5c6996e0841aaabccb56) ([System](classmavsdk_1_1_system.md) & system) | Constructor. Creates the plugin for a specific [System](classmavsdk_1_1_system.md).
&nbsp; | [MavlinkPassthrough](#classmavsdk_1_1_mavlink_passthrough_1a9d1fdd3c4aeab8e221ac59612944c299) (std::shared_ptr< [System](classmavsdk_1_1_system.md) > system) | Constructor. Creates the plugin for a specific [System](classmavsdk_1_1_system.md).
&nbsp; | [~MavlinkPassthrough](#classmavsdk_1_1_mavlink_passthrough_1a890faef9ad80c3e79e0b785fd07106c8) () | Destructor (internal use only).
&nbsp; | [MavlinkPassthrough](#classmavsdk_1_1_mavlink_passthrough_1ae4b30f9c2c5e938ab965729e27f50ce5) (const [MavlinkPassthrough](classmavsdk_1_1_mavlink_passthrough.md) &)=delete | Copy Constructor (object is not copyable).
[Result](classmavsdk_1_1_mavlink_passthrough.md#classmavsdk_1_1_mavlink_passthrough_1a265eacaeea064a31de3fe16d1e357793) | [send_message](#classmavsdk_1_1_mavlink_passthrough_1ac66d092318fa6d80c5bffea449f4bbaa) (mavlink_message_t & message) | Send message.
[Result](classmavsdk_1_1_mavlink_passthrough.md#classmavsdk_1_1_mavlink_passthrough_1a265eacaeea064a31de3fe16d1e357793) | [send_command_long](#classmavsdk_1_1_mavlink_passthrough_1a7e258aa16b92195e5329e861fb18f8e9) (const [CommandLong](structmavsdk_1_1_mavlink_passthrough_1_1_command_long.md) & command) | Send a MAVLink command_long.
[Result](classmavsdk_1_1_mavlink_passthrough.md#classmavsdk_1_1_mavlink_passthrough_1a265eacaeea064a31de3fe16d1e357793) | [send_command_int](#classmavsdk_1_1_mavlink_passthrough_1a654d67a3b136509c76e2ac804a656ada) (const [CommandInt](structmavsdk_1_1_mavlink_passthrough_1_1_command_int.md) & command) | Send a MAVLink command_long.
void | [subscribe_message_async](#classmavsdk_1_1_mavlink_passthrough_1a6dfb4fedba830dff881deb2e375da571) (uint16_t message_id, std::function< void(const mavlink_message_t &)> callback) | Subscribe to messages using message ID.
uint8_t | [get_our_sysid](#classmavsdk_1_1_mavlink_passthrough_1a985b269c1b78ec3e4e9d9468e46e19be) () const | Get our own system ID.
uint8_t | [get_our_compid](#classmavsdk_1_1_mavlink_passthrough_1a85ddd016ab35d5f3f487b1362723d3cf) () const | Get our own component ID.
uint8_t | [get_target_sysid](#classmavsdk_1_1_mavlink_passthrough_1a2867d1f37649d62e757bbac0a73b3ebd) () const | Get system ID of target.
uint8_t | [get_target_compid](#classmavsdk_1_1_mavlink_passthrough_1a22ecab3905237a2f227f77bbab9afd17) () const | Get target component ID.
void | [intercept_incoming_messages_async](#classmavsdk_1_1_mavlink_passthrough_1a06f6c1d181f966bc9d67c4a69e4aae7a) (std::function< bool(mavlink_message_t &)> callback) | Intercept incoming messages.
void | [intercept_outgoing_messages_async](#classmavsdk_1_1_mavlink_passthrough_1ad06c4f286f8b785a2fc09ee18dfb43c3) (std::function< bool(mavlink_message_t &)> callback) | Intercept outgoing messages.
const [MavlinkPassthrough](classmavsdk_1_1_mavlink_passthrough.md) & | [operator=](#classmavsdk_1_1_mavlink_passthrough_1aa7f49a131a8facf4d05449ec03ce3643) (const [MavlinkPassthrough](classmavsdk_1_1_mavlink_passthrough.md) &)=delete | Equality operator (object is not copyable).


## Constructor & Destructor Documentation


### MavlinkPassthrough() {#classmavsdk_1_1_mavlink_passthrough_1ad17fc20d2b7c5c6996e0841aaabccb56}
```cpp
mavsdk::MavlinkPassthrough::MavlinkPassthrough(System &system)
```


Constructor. Creates the plugin for a specific [System](classmavsdk_1_1_system.md).

The plugin is typically created as shown below: 

```cpp
auto mavlink_passthrough = MavlinkPassthrough(system);
```

**Parameters**

* [System](classmavsdk_1_1_system.md)& **system** - The specific system associated with this plugin.

### MavlinkPassthrough() {#classmavsdk_1_1_mavlink_passthrough_1a9d1fdd3c4aeab8e221ac59612944c299}
```cpp
mavsdk::MavlinkPassthrough::MavlinkPassthrough(std::shared_ptr< System > system)
```


Constructor. Creates the plugin for a specific [System](classmavsdk_1_1_system.md).

The plugin is typically created as shown below: 

```cpp
auto mavlink_passthrough = MavlinkPassthrough(system);
```

**Parameters**

* std::shared_ptr< [System](classmavsdk_1_1_system.md) > **system** - The specific system associated with this plugin.

### ~MavlinkPassthrough() {#classmavsdk_1_1_mavlink_passthrough_1a890faef9ad80c3e79e0b785fd07106c8}
```cpp
mavsdk::MavlinkPassthrough::~MavlinkPassthrough()
```


Destructor (internal use only).


### MavlinkPassthrough() {#classmavsdk_1_1_mavlink_passthrough_1ae4b30f9c2c5e938ab965729e27f50ce5}
```cpp
mavsdk::MavlinkPassthrough::MavlinkPassthrough(const MavlinkPassthrough &)=delete
```


Copy Constructor (object is not copyable).


**Parameters**

* const [MavlinkPassthrough](classmavsdk_1_1_mavlink_passthrough.md)&  - 

## Member Enumeration Documentation


### enum Result {#classmavsdk_1_1_mavlink_passthrough_1a265eacaeea064a31de3fe16d1e357793}


Possible results returned for requests.


Value | Description
--- | ---
<span id="classmavsdk_1_1_mavlink_passthrough_1a265eacaeea064a31de3fe16d1e357793a88183b946cc5f0e8c96b2e66e1c74a7e"></span> `Unknown` | Unknown error. 
<span id="classmavsdk_1_1_mavlink_passthrough_1a265eacaeea064a31de3fe16d1e357793a505a83f220c02df2f85c3810cd9ceb38"></span> `Success` | Success. 
<span id="classmavsdk_1_1_mavlink_passthrough_1a265eacaeea064a31de3fe16d1e357793a094a6f6b0868122a9dd008cb91c083e4"></span> `ConnectionError` | Connection error. 
<span id="classmavsdk_1_1_mavlink_passthrough_1a265eacaeea064a31de3fe16d1e357793aaa075662ac89e0922d349f55d81d7382"></span> `CommandNoSystem` | [System](classmavsdk_1_1_system.md) not available. 
<span id="classmavsdk_1_1_mavlink_passthrough_1a265eacaeea064a31de3fe16d1e357793a236fe685992938e92191d04e69a77762"></span> `CommandBusy` | [System](classmavsdk_1_1_system.md) is busy. 
<span id="classmavsdk_1_1_mavlink_passthrough_1a265eacaeea064a31de3fe16d1e357793a3398e12855176d55f43d53e04f472c8a"></span> `CommandDenied` | Command has been denied. 
<span id="classmavsdk_1_1_mavlink_passthrough_1a265eacaeea064a31de3fe16d1e357793a711552fb22e889145c9769bb9ab88fe5"></span> `CommandUnsupported` | Command is not supported. 
<span id="classmavsdk_1_1_mavlink_passthrough_1a265eacaeea064a31de3fe16d1e357793a309bc1cd528bc8f9a548616ae0a13a17"></span> `CommandTimeout` | A timeout happened. 

## Member Function Documentation


### send_message() {#classmavsdk_1_1_mavlink_passthrough_1ac66d092318fa6d80c5bffea449f4bbaa}
```cpp
Result mavsdk::MavlinkPassthrough::send_message(mavlink_message_t &message)
```


Send message.


**Parameters**

* mavlink_message_t& **message** - 

**Returns**

&emsp;[Result](classmavsdk_1_1_mavlink_passthrough.md#classmavsdk_1_1_mavlink_passthrough_1a265eacaeea064a31de3fe16d1e357793) - result of the request.

### send_command_long() {#classmavsdk_1_1_mavlink_passthrough_1a7e258aa16b92195e5329e861fb18f8e9}
```cpp
Result mavsdk::MavlinkPassthrough::send_command_long(const CommandLong &command)
```


Send a MAVLink command_long.


**Parameters**

* const [CommandLong](structmavsdk_1_1_mavlink_passthrough_1_1_command_long.md)& **command** - Command to send.

**Returns**

&emsp;[Result](classmavsdk_1_1_mavlink_passthrough.md#classmavsdk_1_1_mavlink_passthrough_1a265eacaeea064a31de3fe16d1e357793) - result of the request.

### send_command_int() {#classmavsdk_1_1_mavlink_passthrough_1a654d67a3b136509c76e2ac804a656ada}
```cpp
Result mavsdk::MavlinkPassthrough::send_command_int(const CommandInt &command)
```


Send a MAVLink command_long.


**Parameters**

* const [CommandInt](structmavsdk_1_1_mavlink_passthrough_1_1_command_int.md)& **command** - Command to send.

**Returns**

&emsp;[Result](classmavsdk_1_1_mavlink_passthrough.md#classmavsdk_1_1_mavlink_passthrough_1a265eacaeea064a31de3fe16d1e357793) - result of the request.

### subscribe_message_async() {#classmavsdk_1_1_mavlink_passthrough_1a6dfb4fedba830dff881deb2e375da571}
```cpp
void mavsdk::MavlinkPassthrough::subscribe_message_async(uint16_t message_id, std::function< void(const mavlink_message_t &)> callback)
```


Subscribe to messages using message ID.

This means that all future messages being received will trigger the callback to be called. To stop the subscription, call this method with `nullptr` as the argument.

**Parameters**

* uint16_t **message_id** - The MAVLink message ID.
* std::function< void(const mavlink_message_t &)> **callback** - Callback to be called for message subscription.

### get_our_sysid() {#classmavsdk_1_1_mavlink_passthrough_1a985b269c1b78ec3e4e9d9468e46e19be}
```cpp
uint8_t mavsdk::MavlinkPassthrough::get_our_sysid() const
```


Get our own system ID.


**Returns**

&emsp;uint8_t - our own system ID.

### get_our_compid() {#classmavsdk_1_1_mavlink_passthrough_1a85ddd016ab35d5f3f487b1362723d3cf}
```cpp
uint8_t mavsdk::MavlinkPassthrough::get_our_compid() const
```


Get our own component ID.


**Returns**

&emsp;uint8_t - our own component ID.

### get_target_sysid() {#classmavsdk_1_1_mavlink_passthrough_1a2867d1f37649d62e757bbac0a73b3ebd}
```cpp
uint8_t mavsdk::MavlinkPassthrough::get_target_sysid() const
```


Get system ID of target.


**Returns**

&emsp;uint8_t - system ID of target.

### get_target_compid() {#classmavsdk_1_1_mavlink_passthrough_1a22ecab3905237a2f227f77bbab9afd17}
```cpp
uint8_t mavsdk::MavlinkPassthrough::get_target_compid() const
```


Get target component ID.

This defaults to the component ID of the autopilot (1) if available and otherwise to all components (0).

**Returns**

&emsp;uint8_t - component ID of target.

### intercept_incoming_messages_async() {#classmavsdk_1_1_mavlink_passthrough_1a06f6c1d181f966bc9d67c4a69e4aae7a}
```cpp
void mavsdk::MavlinkPassthrough::intercept_incoming_messages_async(std::function< bool(mavlink_message_t &)> callback)
```


Intercept incoming messages.

This is a hook which allows to change or drop MAVLink messages as they are received before they get forwarded to the core and the other plugins.


> **Note** This functioniality is provided primarily for testing in order to simulate packet drops or actors not adhering to the MAVLink protocols.

**Parameters**

* std::function< bool(mavlink_message_t &)> **callback** - Callback to be called for each incoming message. To drop a message, return 'false' from the callback.

### intercept_outgoing_messages_async() {#classmavsdk_1_1_mavlink_passthrough_1ad06c4f286f8b785a2fc09ee18dfb43c3}
```cpp
void mavsdk::MavlinkPassthrough::intercept_outgoing_messages_async(std::function< bool(mavlink_message_t &)> callback)
```


Intercept outgoing messages.

This is a hook which allows to change or drop MAVLink messages before they are sent.


> **Note** This functioniality is provided primarily for testing in order to simulate packet drops or actors not adhering to the MAVLink protocols.

**Parameters**

* std::function< bool(mavlink_message_t &)> **callback** - Callback to be called for each outgoing message. To drop a message, return 'false' from the callback.

### operator=() {#classmavsdk_1_1_mavlink_passthrough_1aa7f49a131a8facf4d05449ec03ce3643}
```cpp
const MavlinkPassthrough& mavsdk::MavlinkPassthrough::operator=(const MavlinkPassthrough &)=delete
```


Equality operator (object is not copyable).


**Parameters**

* const [MavlinkPassthrough](classmavsdk_1_1_mavlink_passthrough.md)&  - 

**Returns**

&emsp;const [MavlinkPassthrough](classmavsdk_1_1_mavlink_passthrough.md) & - 