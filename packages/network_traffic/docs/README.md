# Network Traffic Integration

This integration sniffs network packets on a host and dissects
known protocols.

## Network Flows

Overall flow information about the network connections on a
host.

**Exported fields**

| Field | Description | Type |
|---|---|---|
| @timestamp | Event timestamp. | date |
| client.bytes | Bytes sent from the client to the server. | long |
| client.ip | IP address of the client. | ip |
| client.port | Port of the client. | long |
| client.process.args | The command-line of the process that initiated the transaction. | keyword |
| client.process.executable | Absolute path to the client process executable. | keyword |
| client.process.name | The name of the process that initiated the transaction. | keyword |
| client.process.start | The time the client process started. | date |
| client.process.working_directory | The working directory of the client process. | keyword |
| cloud.account.id | The cloud account or organization id used to identify different entities in a multi-tenant environment. Examples: AWS account id, Google Cloud ORG Id, or other unique identifier. | keyword |
| cloud.availability_zone | Availability zone in which this host is running. | keyword |
| cloud.image.id | Image ID for the cloud instance. | keyword |
| cloud.instance.id | Instance ID of the host machine. | keyword |
| cloud.instance.name | Instance name of the host machine. | keyword |
| cloud.machine.type | Machine type of the host machine. | keyword |
| cloud.project.id | Name of the project in Google Cloud. | keyword |
| cloud.provider | Name of the cloud provider. Example values are aws, azure, gcp, or digitalocean. | keyword |
| cloud.region | Region in which this host is running. | keyword |
| container.id | Unique container id. | keyword |
| container.image.name | Name of the image the container was built on. | keyword |
| container.labels | Image labels. | object |
| container.name | Container name. | keyword |
| data_stream.dataset | Data stream dataset. | constant_keyword |
| data_stream.namespace | Data stream namespace. | constant_keyword |
| data_stream.type | Data stream type. | constant_keyword |
| destination.bytes | Bytes sent from the destination to the source. | long |
| destination.ip | IP address of the destination. | ip |
| destination.port | Port of the destination. | long |
| ecs.version | ECS version this event conforms to. | keyword |
| event.category | Event category. The second categorization field in the hierarchy. | keyword |
| event.dataset | Name of the dataset. | keyword |
| event.duration | Duration of the event in nanoseconds. | long |
| event.end | event.end contains the date when the event ended or when the activity was last observed. | date |
| event.kind | The kind of the event. The highest categorization field in the hierarchy. | keyword |
| event.start | event.start contains the date when the event started or when the activity was first observed. | date |
| event.type | Event type. The third categorization field in the hierarchy. | keyword |
| flow.final | Indicates if event is last event in flow. If final is false, the event reports an intermediate flow state only. | boolean |
| flow.id | Internal flow ID based on connection meta data and address. | keyword |
| flow.vlan | VLAN identifier from the 802.1q frame. In case of a multi-tagged frame this field will be an array with the outer tag's VLAN identifier listed first. | long |
| host.architecture | Operating system architecture. | keyword |
| host.containerized | If the host is a container. | boolean |
| host.domain | Name of the domain of which the host is a member. For example, on Windows this could be the host's Active Directory domain or NetBIOS domain name. For Linux this could be the domain of the host's LDAP provider. | keyword |
| host.hostname | Hostname of the host. It normally contains what the `hostname` command returns on the host machine. | keyword |
| host.id | Unique host id. As hostname is not always unique, use values that are meaningful in your environment. Example: The current usage of `beat.name`. | keyword |
| host.ip | Host ip addresses. | ip |
| host.mac | Host mac addresses. | keyword |
| host.name | Name of the host. It can contain what `hostname` returns on Unix systems, the fully qualified domain name, or a name specified by the user. The sender decides which value to use. | keyword |
| host.os.build | OS build information. | keyword |
| host.os.codename | OS codename, if any. | keyword |
| host.os.family | OS family (such as redhat, debian, freebsd, windows). | keyword |
| host.os.kernel | Operating system kernel version as a raw string. | keyword |
| host.os.name | Operating system name, without the version. | keyword |
| host.os.platform | Operating system platform (such centos, ubuntu, windows). | keyword |
| host.os.version | Operating system version as a raw string. | keyword |
| host.type | Type of host. For Cloud providers this can be the machine type like `t2.medium`. If vm, this could be the container, for example, or other information meaningful in your environment. | keyword |
| method | The command/verb/method of the transaction. For HTTP, this is the method name (GET, POST, PUT, and so on), for SQL this is the verb (SELECT, UPDATE, DELETE, and so on). | keyword |
| network.bytes | Total bytes transferred in both directions. | long |
| network.community_id | A hash of source and destination IPs and ports. | keyword |
| network.direction | Direction of the network traffic. | keyword |
| network.forwarded_ip | Host IP address when the source IP address is the proxy. | ip |
| network.protocol | L7 Network protocol name. | keyword |
| network.transport | Protocol Name corresponding to the field `iana_number`. | keyword |
| network.type | In the OSI Model this would be the Network Layer. ipv4, ipv6, ipsec, pim, etc | keyword |
| params | The request parameters. For HTTP, these are the POST or GET parameters. For Thrift-RPC, these are the parameters from the request. | text |
| path | The path the transaction refers to. For HTTP, this is the URL. For SQL databases, this is the table name. For key-value stores, this is the key. | keyword |
| query | The query in a human readable format. For HTTP, it will typically be something like `GET /users/_search?name=test`. For MySQL, it is something like `SELECT id from users where name=test`. | keyword |
| related.ip | All of the IPs seen on your event. | ip |
| request | For text protocols, this is the request as seen on the wire (application layer only). For binary protocols this is our representation of the request. | text |
| resource | The logical resource that this transaction refers to. For HTTP, this is the URL path up to the last slash (/). For example, if the URL is `/users/1`, the resource is `/users`. For databases, the resource is typically the table name. The field is not filled for all transaction types. | keyword |
| response | For text protocols, this is the response as seen on the wire (application layer only). For binary protocols this is our representation of the request. | text |
| server.bytes | Bytes sent from the server to the client. | long |
| server.ip | IP address of the server. | ip |
| server.port | Port of the server. | long |
| server.process.args | The command-line of the process that served the transaction. | keyword |
| server.process.executable | Absolute path to the server process executable. | keyword |
| server.process.name | The name of the process that served the transaction. | keyword |
| server.process.start | The time the server process started. | date |
| server.process.working_directory | The working directory of the server process. | keyword |
| source.bytes | Bytes sent from the source to the destination. | long |
| source.ip | IP address of the source. | ip |
| source.port | Port of the source. | long |
| status | The high level status of the transaction. The way to compute this value depends on the protocol, but the result has a meaning independent of the protocol. | keyword |
| type | The type of the transaction (for example, HTTP, MySQL, Redis, or RUM) or "flow" in case of flows. | keyword |


## Protocols

### AMQP

Fields published for AMQP packets.

**Exported fields**

| Field | Description | Type |
|---|---|---|
| @timestamp | Event timestamp. | date |
| amqp.app-id | Creating application id. | keyword |
| amqp.arguments | Optional additional arguments passed to some methods. Can be of various types. | object |
| amqp.auto-delete | If set, auto-delete queue when unused. | boolean |
| amqp.class-id | Failing method class. | long |
| amqp.consumer-count | The number of consumers of a queue. | long |
| amqp.consumer-tag | Identifier for the consumer, valid within the current channel. | keyword |
| amqp.content-encoding | MIME content encoding. | keyword |
| amqp.content-type | MIME content type. | keyword |
| amqp.correlation-id | Application correlation identifier. | keyword |
| amqp.delivery-mode | Non-persistent (1) or persistent (2). | keyword |
| amqp.delivery-tag | The server-assigned and channel-specific delivery tag. | long |
| amqp.durable | If set, request a durable exchange/queue. | boolean |
| amqp.exchange | Name of the exchange. | keyword |
| amqp.exchange-type | Exchange type. | keyword |
| amqp.exclusive | If set, request an exclusive queue. | boolean |
| amqp.expiration | Message expiration specification. | keyword |
| amqp.headers | Message header field table. | object |
| amqp.if-empty | Delete only if empty. | boolean |
| amqp.if-unused | Delete only if unused. | boolean |
| amqp.immediate | Request immediate delivery. | boolean |
| amqp.mandatory | Indicates mandatory routing. | boolean |
| amqp.message-count | The number of messages in the queue, which will be zero for newly-declared queues. | long |
| amqp.message-id | Application message identifier. | keyword |
| amqp.method-id | Failing method ID. | long |
| amqp.multiple | Acknowledge multiple messages. | boolean |
| amqp.no-ack | If set, the server does not expect acknowledgements for messages. | boolean |
| amqp.no-local | If set, the server will not send messages to the connection that published them. | boolean |
| amqp.no-wait | If set, the server will not respond to the method. | boolean |
| amqp.passive | If set, do not create exchange/queue. | boolean |
| amqp.priority | Message priority, 0 to 9. | long |
| amqp.queue | The queue name identifies the queue within the vhost. | keyword |
| amqp.redelivered | Indicates that the message has been previously delivered to this or another client. | boolean |
| amqp.reply-code | AMQP reply code to an error, similar to http reply-code | long |
| amqp.reply-text | Text explaining the error. | keyword |
| amqp.reply-to | Address to reply to. | keyword |
| amqp.routing-key | Message routing key. | keyword |
| amqp.timestamp | Message timestamp. | keyword |
| amqp.type | Message type name. | keyword |
| amqp.user-id | Creating user id. | keyword |
| client.bytes | Bytes sent from the client to the server. | long |
| client.ip | IP address of the client. | ip |
| client.port | Port of the client. | long |
| client.process.args | The command-line of the process that initiated the transaction. | keyword |
| client.process.executable | Absolute path to the client process executable. | keyword |
| client.process.name | The name of the process that initiated the transaction. | keyword |
| client.process.start | The time the client process started. | date |
| client.process.working_directory | The working directory of the client process. | keyword |
| cloud.account.id | The cloud account or organization id used to identify different entities in a multi-tenant environment. Examples: AWS account id, Google Cloud ORG Id, or other unique identifier. | keyword |
| cloud.availability_zone | Availability zone in which this host is running. | keyword |
| cloud.image.id | Image ID for the cloud instance. | keyword |
| cloud.instance.id | Instance ID of the host machine. | keyword |
| cloud.instance.name | Instance name of the host machine. | keyword |
| cloud.machine.type | Machine type of the host machine. | keyword |
| cloud.project.id | Name of the project in Google Cloud. | keyword |
| cloud.provider | Name of the cloud provider. Example values are aws, azure, gcp, or digitalocean. | keyword |
| cloud.region | Region in which this host is running. | keyword |
| container.id | Unique container id. | keyword |
| container.image.name | Name of the image the container was built on. | keyword |
| container.labels | Image labels. | object |
| container.name | Container name. | keyword |
| data_stream.dataset | Data stream dataset. | constant_keyword |
| data_stream.namespace | Data stream namespace. | constant_keyword |
| data_stream.type | Data stream type. | constant_keyword |
| destination.bytes | Bytes sent from the destination to the source. | long |
| destination.ip | IP address of the destination. | ip |
| destination.port | Port of the destination. | long |
| ecs.version | ECS version this event conforms to. | keyword |
| event.category | Event category. The second categorization field in the hierarchy. | keyword |
| event.dataset | Name of the dataset. | keyword |
| event.duration | Duration of the event in nanoseconds. | long |
| event.end | event.end contains the date when the event ended or when the activity was last observed. | date |
| event.kind | The kind of the event. The highest categorization field in the hierarchy. | keyword |
| event.start | event.start contains the date when the event started or when the activity was first observed. | date |
| event.type | Event type. The third categorization field in the hierarchy. | keyword |
| flow.final | Indicates if event is last event in flow. If final is false, the event reports an intermediate flow state only. | boolean |
| flow.id | Internal flow ID based on connection meta data and address. | keyword |
| flow.vlan | VLAN identifier from the 802.1q frame. In case of a multi-tagged frame this field will be an array with the outer tag's VLAN identifier listed first. | long |
| host.architecture | Operating system architecture. | keyword |
| host.containerized | If the host is a container. | boolean |
| host.domain | Name of the domain of which the host is a member. For example, on Windows this could be the host's Active Directory domain or NetBIOS domain name. For Linux this could be the domain of the host's LDAP provider. | keyword |
| host.hostname | Hostname of the host. It normally contains what the `hostname` command returns on the host machine. | keyword |
| host.id | Unique host id. As hostname is not always unique, use values that are meaningful in your environment. Example: The current usage of `beat.name`. | keyword |
| host.ip | Host ip addresses. | ip |
| host.mac | Host mac addresses. | keyword |
| host.name | Name of the host. It can contain what `hostname` returns on Unix systems, the fully qualified domain name, or a name specified by the user. The sender decides which value to use. | keyword |
| host.os.build | OS build information. | keyword |
| host.os.codename | OS codename, if any. | keyword |
| host.os.family | OS family (such as redhat, debian, freebsd, windows). | keyword |
| host.os.kernel | Operating system kernel version as a raw string. | keyword |
| host.os.name | Operating system name, without the version. | keyword |
| host.os.platform | Operating system platform (such centos, ubuntu, windows). | keyword |
| host.os.version | Operating system version as a raw string. | keyword |
| host.type | Type of host. For Cloud providers this can be the machine type like `t2.medium`. If vm, this could be the container, for example, or other information meaningful in your environment. | keyword |
| method | The command/verb/method of the transaction. For HTTP, this is the method name (GET, POST, PUT, and so on), for SQL this is the verb (SELECT, UPDATE, DELETE, and so on). | keyword |
| network.bytes | Total bytes transferred in both directions. | long |
| network.community_id | A hash of source and destination IPs and ports. | keyword |
| network.direction | Direction of the network traffic. | keyword |
| network.forwarded_ip | Host IP address when the source IP address is the proxy. | ip |
| network.protocol | L7 Network protocol name. | keyword |
| network.transport | Protocol Name corresponding to the field `iana_number`. | keyword |
| network.type | In the OSI Model this would be the Network Layer. ipv4, ipv6, ipsec, pim, etc | keyword |
| params | The request parameters. For HTTP, these are the POST or GET parameters. For Thrift-RPC, these are the parameters from the request. | text |
| path | The path the transaction refers to. For HTTP, this is the URL. For SQL databases, this is the table name. For key-value stores, this is the key. | keyword |
| query | The query in a human readable format. For HTTP, it will typically be something like `GET /users/_search?name=test`. For MySQL, it is something like `SELECT id from users where name=test`. | keyword |
| related.ip | All of the IPs seen on your event. | ip |
| request | For text protocols, this is the request as seen on the wire (application layer only). For binary protocols this is our representation of the request. | text |
| resource | The logical resource that this transaction refers to. For HTTP, this is the URL path up to the last slash (/). For example, if the URL is `/users/1`, the resource is `/users`. For databases, the resource is typically the table name. The field is not filled for all transaction types. | keyword |
| response | For text protocols, this is the response as seen on the wire (application layer only). For binary protocols this is our representation of the request. | text |
| server.bytes | Bytes sent from the server to the client. | long |
| server.ip | IP address of the server. | ip |
| server.port | Port of the server. | long |
| server.process.args | The command-line of the process that served the transaction. | keyword |
| server.process.executable | Absolute path to the server process executable. | keyword |
| server.process.name | The name of the process that served the transaction. | keyword |
| server.process.start | The time the server process started. | date |
| server.process.working_directory | The working directory of the server process. | keyword |
| source.bytes | Bytes sent from the source to the destination. | long |
| source.ip | IP address of the source. | ip |
| source.port | Port of the source. | long |
| status | The high level status of the transaction. The way to compute this value depends on the protocol, but the result has a meaning independent of the protocol. | keyword |
| type | The type of the transaction (for example, HTTP, MySQL, Redis, or RUM) or "flow" in case of flows. | keyword |


### Cassandra

Fields published for Apache Cassandra packets.

**Exported fields**

| Field | Description | Type |
|---|---|---|
| @timestamp | Event timestamp. | date |
| cassandra.no_request | Indicates that there is no request because this is a PUSH message. | boolean |
| cassandra.request.headers.flags | Flags applying to this frame. | keyword |
| cassandra.request.headers.length | A integer representing the length of the body of the frame (a frame is limited to 256MB in length). | long |
| cassandra.request.headers.op | An operation type that distinguishes the actual message. | keyword |
| cassandra.request.headers.stream | A frame has a stream id.  If a client sends a request message with the stream id X, it is guaranteed that the stream id of the response to that message will be X. | keyword |
| cassandra.request.headers.version | The version of the protocol. | keyword |
| cassandra.request.query | The CQL query which client send to cassandra. | keyword |
| cassandra.response.authentication.class | Indicates the full class name of the IAuthenticator in use | keyword |
| cassandra.response.error.code | The error code of the Cassandra response. | long |
| cassandra.response.error.details.alive | Representing the number of replicas that were known to be alive when the request had been processed (since an unavailable exception has been triggered). | long |
| cassandra.response.error.details.arg_types | One string for each argument type (as CQL type) of the failed function. | keyword |
| cassandra.response.error.details.blockfor | Representing the number of replicas whose acknowledgement is required to achieve consistency level. | long |
| cassandra.response.error.details.data_present | It means the replica that was asked for data had responded. | boolean |
| cassandra.response.error.details.function | The name of the failed function. | keyword |
| cassandra.response.error.details.keyspace | The keyspace of the failed function. | keyword |
| cassandra.response.error.details.num_failures | Representing the number of nodes that experience a failure while executing the request. | keyword |
| cassandra.response.error.details.read_consistency | Representing the consistency level of the query that triggered the exception. | keyword |
| cassandra.response.error.details.received | Representing the number of nodes having acknowledged the request. | long |
| cassandra.response.error.details.required | Representing the number of nodes that should be alive to respect consistency level. | long |
| cassandra.response.error.details.stmt_id | Representing the unknown ID. | keyword |
| cassandra.response.error.details.table | The keyspace of the failed function. | keyword |
| cassandra.response.error.details.write_type | Describe the type of the write that timed out. | keyword |
| cassandra.response.error.msg | The error message of the Cassandra response. | keyword |
| cassandra.response.error.type | The error type of the Cassandra response. | keyword |
| cassandra.response.event.change | The message corresponding respectively to the type of change followed by the address of the new/removed node. | keyword |
| cassandra.response.event.host | Representing the node ip. | keyword |
| cassandra.response.event.port | Representing the node port. | long |
| cassandra.response.event.schema_change.args | One string for each argument type (as CQL type). | keyword |
| cassandra.response.event.schema_change.change | Representing the type of changed involved. | keyword |
| cassandra.response.event.schema_change.keyspace | This describes which keyspace has changed. | keyword |
| cassandra.response.event.schema_change.name | The function/aggregate name. | keyword |
| cassandra.response.event.schema_change.object | This describes the name of said affected object (either the table, user type, function, or aggregate name). | keyword |
| cassandra.response.event.schema_change.table | This describes which table has changed. | keyword |
| cassandra.response.event.schema_change.target | Target could be "FUNCTION" or "AGGREGATE", multiple arguments. | keyword |
| cassandra.response.event.type | Representing the event type. | keyword |
| cassandra.response.headers.flags | Flags applying to this frame. | keyword |
| cassandra.response.headers.length | A integer representing the length of the body of the frame (a frame is limited to 256MB in length). | long |
| cassandra.response.headers.op | An operation type that distinguishes the actual message. | keyword |
| cassandra.response.headers.stream | A frame has a stream id.  If a client sends a request message with the stream id X, it is guaranteed that the stream id of the response to that message will be X. | keyword |
| cassandra.response.headers.version | The version of the protocol. | keyword |
| cassandra.response.result.keyspace | Indicating the name of the keyspace that has been set. | keyword |
| cassandra.response.result.prepared.prepared_id | Representing the prepared query ID. | keyword |
| cassandra.response.result.prepared.req_meta.col_count | Representing the number of columns selected by the query that produced this result. | long |
| cassandra.response.result.prepared.req_meta.flags | Provides information on the formatting of the remaining information. | keyword |
| cassandra.response.result.prepared.req_meta.keyspace | Only present after set Global_tables_spec, the keyspace name. | keyword |
| cassandra.response.result.prepared.req_meta.paging_state | The paging_state is a bytes value that should be used in QUERY/EXECUTE to continue paging and retrieve the remainder of the result for this query. | keyword |
| cassandra.response.result.prepared.req_meta.pkey_columns | Representing the PK columns index and counts. | long |
| cassandra.response.result.prepared.req_meta.table | Only present after set Global_tables_spec, the table name. | keyword |
| cassandra.response.result.prepared.resp_meta.col_count | Representing the number of columns selected by the query that produced this result. | long |
| cassandra.response.result.prepared.resp_meta.flags | Provides information on the formatting of the remaining information. | keyword |
| cassandra.response.result.prepared.resp_meta.keyspace | Only present after set Global_tables_spec, the keyspace name. | keyword |
| cassandra.response.result.prepared.resp_meta.paging_state | The paging_state is a bytes value that should be used in QUERY/EXECUTE to continue paging and retrieve the remainder of the result for this query. | keyword |
| cassandra.response.result.prepared.resp_meta.pkey_columns | Representing the PK columns index and counts. | long |
| cassandra.response.result.prepared.resp_meta.table | Only present after set Global_tables_spec, the table name. | keyword |
| cassandra.response.result.rows.meta.col_count | Representing the number of columns selected by the query that produced this result. | long |
| cassandra.response.result.rows.meta.flags | Provides information on the formatting of the remaining information. | keyword |
| cassandra.response.result.rows.meta.keyspace | Only present after set Global_tables_spec, the keyspace name. | keyword |
| cassandra.response.result.rows.meta.paging_state | The paging_state is a bytes value that should be used in QUERY/EXECUTE to continue paging and retrieve the remainder of the result for this query. | keyword |
| cassandra.response.result.rows.meta.pkey_columns | Representing the PK columns index and counts. | long |
| cassandra.response.result.rows.meta.table | Only present after set Global_tables_spec, the table name. | keyword |
| cassandra.response.result.rows.num_rows | Representing the number of rows present in this result. | long |
| cassandra.response.result.schema_change.args | One string for each argument type (as CQL type). | keyword |
| cassandra.response.result.schema_change.change | Representing the type of changed involved. | keyword |
| cassandra.response.result.schema_change.keyspace | This describes which keyspace has changed. | keyword |
| cassandra.response.result.schema_change.name | The function/aggregate name. | keyword |
| cassandra.response.result.schema_change.object | This describes the name of said affected object (either the table, user type, function, or aggregate name). | keyword |
| cassandra.response.result.schema_change.table | This describes which table has changed. | keyword |
| cassandra.response.result.schema_change.target | Target could be "FUNCTION" or "AGGREGATE", multiple arguments. | keyword |
| cassandra.response.result.type | Cassandra result type. | keyword |
| cassandra.response.supported | Indicates which startup options are supported by the server. This message comes as a response to an OPTIONS message. | flattened |
| cassandra.response.warnings | The text of the warnings, only occur when Warning flag was set. | keyword |
| client.bytes | Bytes sent from the client to the server. | long |
| client.ip | IP address of the client. | ip |
| client.port | Port of the client. | long |
| client.process.args | The command-line of the process that initiated the transaction. | keyword |
| client.process.executable | Absolute path to the client process executable. | keyword |
| client.process.name | The name of the process that initiated the transaction. | keyword |
| client.process.start | The time the client process started. | date |
| client.process.working_directory | The working directory of the client process. | keyword |
| cloud.account.id | The cloud account or organization id used to identify different entities in a multi-tenant environment. Examples: AWS account id, Google Cloud ORG Id, or other unique identifier. | keyword |
| cloud.availability_zone | Availability zone in which this host is running. | keyword |
| cloud.image.id | Image ID for the cloud instance. | keyword |
| cloud.instance.id | Instance ID of the host machine. | keyword |
| cloud.instance.name | Instance name of the host machine. | keyword |
| cloud.machine.type | Machine type of the host machine. | keyword |
| cloud.project.id | Name of the project in Google Cloud. | keyword |
| cloud.provider | Name of the cloud provider. Example values are aws, azure, gcp, or digitalocean. | keyword |
| cloud.region | Region in which this host is running. | keyword |
| container.id | Unique container id. | keyword |
| container.image.name | Name of the image the container was built on. | keyword |
| container.labels | Image labels. | object |
| container.name | Container name. | keyword |
| data_stream.dataset | Data stream dataset. | constant_keyword |
| data_stream.namespace | Data stream namespace. | constant_keyword |
| data_stream.type | Data stream type. | constant_keyword |
| destination.bytes | Bytes sent from the destination to the source. | long |
| destination.ip | IP address of the destination. | ip |
| destination.port | Port of the destination. | long |
| ecs.version | ECS version this event conforms to. | keyword |
| event.category | Event category. The second categorization field in the hierarchy. | keyword |
| event.dataset | Name of the dataset. | keyword |
| event.duration | Duration of the event in nanoseconds. | long |
| event.end | event.end contains the date when the event ended or when the activity was last observed. | date |
| event.kind | The kind of the event. The highest categorization field in the hierarchy. | keyword |
| event.start | event.start contains the date when the event started or when the activity was first observed. | date |
| event.type | Event type. The third categorization field in the hierarchy. | keyword |
| flow.final | Indicates if event is last event in flow. If final is false, the event reports an intermediate flow state only. | boolean |
| flow.id | Internal flow ID based on connection meta data and address. | keyword |
| flow.vlan | VLAN identifier from the 802.1q frame. In case of a multi-tagged frame this field will be an array with the outer tag's VLAN identifier listed first. | long |
| host.architecture | Operating system architecture. | keyword |
| host.containerized | If the host is a container. | boolean |
| host.domain | Name of the domain of which the host is a member. For example, on Windows this could be the host's Active Directory domain or NetBIOS domain name. For Linux this could be the domain of the host's LDAP provider. | keyword |
| host.hostname | Hostname of the host. It normally contains what the `hostname` command returns on the host machine. | keyword |
| host.id | Unique host id. As hostname is not always unique, use values that are meaningful in your environment. Example: The current usage of `beat.name`. | keyword |
| host.ip | Host ip addresses. | ip |
| host.mac | Host mac addresses. | keyword |
| host.name | Name of the host. It can contain what `hostname` returns on Unix systems, the fully qualified domain name, or a name specified by the user. The sender decides which value to use. | keyword |
| host.os.build | OS build information. | keyword |
| host.os.codename | OS codename, if any. | keyword |
| host.os.family | OS family (such as redhat, debian, freebsd, windows). | keyword |
| host.os.kernel | Operating system kernel version as a raw string. | keyword |
| host.os.name | Operating system name, without the version. | keyword |
| host.os.platform | Operating system platform (such centos, ubuntu, windows). | keyword |
| host.os.version | Operating system version as a raw string. | keyword |
| host.type | Type of host. For Cloud providers this can be the machine type like `t2.medium`. If vm, this could be the container, for example, or other information meaningful in your environment. | keyword |
| method | The command/verb/method of the transaction. For HTTP, this is the method name (GET, POST, PUT, and so on), for SQL this is the verb (SELECT, UPDATE, DELETE, and so on). | keyword |
| network.bytes | Total bytes transferred in both directions. | long |
| network.community_id | A hash of source and destination IPs and ports. | keyword |
| network.direction | Direction of the network traffic. | keyword |
| network.forwarded_ip | Host IP address when the source IP address is the proxy. | ip |
| network.protocol | L7 Network protocol name. | keyword |
| network.transport | Protocol Name corresponding to the field `iana_number`. | keyword |
| network.type | In the OSI Model this would be the Network Layer. ipv4, ipv6, ipsec, pim, etc | keyword |
| params | The request parameters. For HTTP, these are the POST or GET parameters. For Thrift-RPC, these are the parameters from the request. | text |
| path | The path the transaction refers to. For HTTP, this is the URL. For SQL databases, this is the table name. For key-value stores, this is the key. | keyword |
| query | The query in a human readable format. For HTTP, it will typically be something like `GET /users/_search?name=test`. For MySQL, it is something like `SELECT id from users where name=test`. | keyword |
| related.ip | All of the IPs seen on your event. | ip |
| request | For text protocols, this is the request as seen on the wire (application layer only). For binary protocols this is our representation of the request. | text |
| resource | The logical resource that this transaction refers to. For HTTP, this is the URL path up to the last slash (/). For example, if the URL is `/users/1`, the resource is `/users`. For databases, the resource is typically the table name. The field is not filled for all transaction types. | keyword |
| response | For text protocols, this is the response as seen on the wire (application layer only). For binary protocols this is our representation of the request. | text |
| server.bytes | Bytes sent from the server to the client. | long |
| server.ip | IP address of the server. | ip |
| server.port | Port of the server. | long |
| server.process.args | The command-line of the process that served the transaction. | keyword |
| server.process.executable | Absolute path to the server process executable. | keyword |
| server.process.name | The name of the process that served the transaction. | keyword |
| server.process.start | The time the server process started. | date |
| server.process.working_directory | The working directory of the server process. | keyword |
| source.bytes | Bytes sent from the source to the destination. | long |
| source.ip | IP address of the source. | ip |
| source.port | Port of the source. | long |
| status | The high level status of the transaction. The way to compute this value depends on the protocol, but the result has a meaning independent of the protocol. | keyword |
| type | The type of the transaction (for example, HTTP, MySQL, Redis, or RUM) or "flow" in case of flows. | keyword |


### DHCP

Fields published for DHCPv4 packets.

**Exported fields**

| Field | Description | Type |
|---|---|---|
| @timestamp | Event timestamp. | date |
| client.bytes | Bytes sent from the client to the server. | long |
| client.ip | IP address of the client. | ip |
| client.port | Port of the client. | long |
| client.process.args | The command-line of the process that initiated the transaction. | keyword |
| client.process.executable | Absolute path to the client process executable. | keyword |
| client.process.name | The name of the process that initiated the transaction. | keyword |
| client.process.start | The time the client process started. | date |
| client.process.working_directory | The working directory of the client process. | keyword |
| cloud.account.id | The cloud account or organization id used to identify different entities in a multi-tenant environment. Examples: AWS account id, Google Cloud ORG Id, or other unique identifier. | keyword |
| cloud.availability_zone | Availability zone in which this host is running. | keyword |
| cloud.image.id | Image ID for the cloud instance. | keyword |
| cloud.instance.id | Instance ID of the host machine. | keyword |
| cloud.instance.name | Instance name of the host machine. | keyword |
| cloud.machine.type | Machine type of the host machine. | keyword |
| cloud.project.id | Name of the project in Google Cloud. | keyword |
| cloud.provider | Name of the cloud provider. Example values are aws, azure, gcp, or digitalocean. | keyword |
| cloud.region | Region in which this host is running. | keyword |
| container.id | Unique container id. | keyword |
| container.image.name | Name of the image the container was built on. | keyword |
| container.labels | Image labels. | object |
| container.name | Container name. | keyword |
| data_stream.dataset | Data stream dataset. | constant_keyword |
| data_stream.namespace | Data stream namespace. | constant_keyword |
| data_stream.type | Data stream type. | constant_keyword |
| destination.bytes | Bytes sent from the destination to the source. | long |
| destination.ip | IP address of the destination. | ip |
| destination.port | Port of the destination. | long |
| dhcpv4.assigned_ip | The IP address that the DHCP server is assigning to the client. This field is also known as "your" IP address. | ip |
| dhcpv4.client_ip | The current IP address of the client. | ip |
| dhcpv4.client_mac | The client's MAC address (layer two). | keyword |
| dhcpv4.flags | Flags are set by the client to indicate how the DHCP server should its reply -- either unicast or broadcast. | keyword |
| dhcpv4.hardware_type | The type of hardware used for the local network (Ethernet, LocalTalk, etc). | keyword |
| dhcpv4.hops | The number of hops the DHCP message went through. | long |
| dhcpv4.op_code | The message op code (bootrequest or bootreply). | keyword |
| dhcpv4.option.boot_file_name | This option is used to identify a bootfile when the 'file' field in the DHCP header has been used for DHCP options. | keyword |
| dhcpv4.option.broadcast_address | This option specifies the broadcast address in use on the client's subnet. | ip |
| dhcpv4.option.class_identifier | This option is used by DHCP clients to optionally identify the vendor type and configuration of a DHCP client. Vendors may choose to define specific vendor class identifiers to convey particular configuration or other identification information about a client.  For example, the identifier may encode the client's hardware configuration. | keyword |
| dhcpv4.option.dns_servers | The domain name server option specifies a list of Domain Name System servers available to the client. | ip |
| dhcpv4.option.domain_name | This option specifies the domain name that client should use when resolving hostnames via the Domain Name System. | keyword |
| dhcpv4.option.hostname | This option specifies the name of the client. | keyword |
| dhcpv4.option.ip_address_lease_time_sec | This option is used in a client request (DHCPDISCOVER or DHCPREQUEST) to allow the client to request a lease time for the IP address.  In a server reply (DHCPOFFER), a DHCP server uses this option to specify the lease time it is willing to offer. | long |
| dhcpv4.option.max_dhcp_message_size | This option specifies the maximum length DHCP message that the client is willing to accept. | long |
| dhcpv4.option.message | This option is used by a DHCP server to provide an error message to a DHCP client in a DHCPNAK message in the event of a failure. A client may use this option in a DHCPDECLINE message to indicate the why the client declined the offered parameters. | text |
| dhcpv4.option.message_type | The specific type of DHCP message being sent (e.g. discover, offer, request, decline, ack, nak, release, inform). | keyword |
| dhcpv4.option.ntp_servers | This option specifies a list of IP addresses indicating NTP servers available to the client. | ip |
| dhcpv4.option.parameter_request_list | This option is used by a DHCP client to request values for specified configuration parameters. | keyword |
| dhcpv4.option.rebinding_time_sec | This option specifies the time interval from address assignment until the client transitions to the REBINDING state. | long |
| dhcpv4.option.renewal_time_sec | This option specifies the time interval from address assignment until the client transitions to the RENEWING state. | long |
| dhcpv4.option.requested_ip_address | This option is used in a client request (DHCPDISCOVER) to allow the client to request that a particular IP address be assigned. | ip |
| dhcpv4.option.router | The router option specifies a list of IP addresses for routers on the client's subnet. | ip |
| dhcpv4.option.server_identifier | IP address of the individual DHCP server which handled this message. | ip |
| dhcpv4.option.subnet_mask | The subnet mask that the client should use on the currnet network. | ip |
| dhcpv4.option.time_servers | The time server option specifies a list of RFC 868 time servers available to the client. | ip |
| dhcpv4.option.utc_time_offset_sec | The time offset field specifies the offset of the client's subnet in seconds from Coordinated Universal Time (UTC). | long |
| dhcpv4.option.vendor_identifying_options | A DHCP client may use this option to unambiguously identify the vendor that manufactured the hardware on which the client is running, the software in use, or an industry consortium to which the vendor belongs. This field is described in RFC 3925. | object |
| dhcpv4.relay_ip | The relay IP address used by the client to contact the server (i.e. a DHCP relay server). | ip |
| dhcpv4.seconds | Number of seconds elapsed since client began address acquisition or renewal process. | long |
| dhcpv4.server_ip | The IP address of the DHCP server that the client should use for the next step in the bootstrap process. | ip |
| dhcpv4.server_name | The name of the server sending the message. Optional. Used in DHCPOFFER or DHCPACK messages. | keyword |
| dhcpv4.transaction_id | Transaction ID, a random number chosen by the client, used by the client and server to associate messages and responses between a client and a server. | keyword |
| ecs.version | ECS version this event conforms to. | keyword |
| event.category | Event category. The second categorization field in the hierarchy. | keyword |
| event.dataset | Name of the dataset. | keyword |
| event.duration | Duration of the event in nanoseconds. | long |
| event.end | event.end contains the date when the event ended or when the activity was last observed. | date |
| event.kind | The kind of the event. The highest categorization field in the hierarchy. | keyword |
| event.start | event.start contains the date when the event started or when the activity was first observed. | date |
| event.type | Event type. The third categorization field in the hierarchy. | keyword |
| flow.final | Indicates if event is last event in flow. If final is false, the event reports an intermediate flow state only. | boolean |
| flow.id | Internal flow ID based on connection meta data and address. | keyword |
| flow.vlan | VLAN identifier from the 802.1q frame. In case of a multi-tagged frame this field will be an array with the outer tag's VLAN identifier listed first. | long |
| host.architecture | Operating system architecture. | keyword |
| host.containerized | If the host is a container. | boolean |
| host.domain | Name of the domain of which the host is a member. For example, on Windows this could be the host's Active Directory domain or NetBIOS domain name. For Linux this could be the domain of the host's LDAP provider. | keyword |
| host.hostname | Hostname of the host. It normally contains what the `hostname` command returns on the host machine. | keyword |
| host.id | Unique host id. As hostname is not always unique, use values that are meaningful in your environment. Example: The current usage of `beat.name`. | keyword |
| host.ip | Host ip addresses. | ip |
| host.mac | Host mac addresses. | keyword |
| host.name | Name of the host. It can contain what `hostname` returns on Unix systems, the fully qualified domain name, or a name specified by the user. The sender decides which value to use. | keyword |
| host.os.build | OS build information. | keyword |
| host.os.codename | OS codename, if any. | keyword |
| host.os.family | OS family (such as redhat, debian, freebsd, windows). | keyword |
| host.os.kernel | Operating system kernel version as a raw string. | keyword |
| host.os.name | Operating system name, without the version. | keyword |
| host.os.platform | Operating system platform (such centos, ubuntu, windows). | keyword |
| host.os.version | Operating system version as a raw string. | keyword |
| host.type | Type of host. For Cloud providers this can be the machine type like `t2.medium`. If vm, this could be the container, for example, or other information meaningful in your environment. | keyword |
| method | The command/verb/method of the transaction. For HTTP, this is the method name (GET, POST, PUT, and so on), for SQL this is the verb (SELECT, UPDATE, DELETE, and so on). | keyword |
| network.bytes | Total bytes transferred in both directions. | long |
| network.community_id | A hash of source and destination IPs and ports. | keyword |
| network.direction | Direction of the network traffic. | keyword |
| network.forwarded_ip | Host IP address when the source IP address is the proxy. | ip |
| network.protocol | L7 Network protocol name. | keyword |
| network.transport | Protocol Name corresponding to the field `iana_number`. | keyword |
| network.type | In the OSI Model this would be the Network Layer. ipv4, ipv6, ipsec, pim, etc | keyword |
| params | The request parameters. For HTTP, these are the POST or GET parameters. For Thrift-RPC, these are the parameters from the request. | text |
| path | The path the transaction refers to. For HTTP, this is the URL. For SQL databases, this is the table name. For key-value stores, this is the key. | keyword |
| query | The query in a human readable format. For HTTP, it will typically be something like `GET /users/_search?name=test`. For MySQL, it is something like `SELECT id from users where name=test`. | keyword |
| related.ip | All of the IPs seen on your event. | ip |
| request | For text protocols, this is the request as seen on the wire (application layer only). For binary protocols this is our representation of the request. | text |
| resource | The logical resource that this transaction refers to. For HTTP, this is the URL path up to the last slash (/). For example, if the URL is `/users/1`, the resource is `/users`. For databases, the resource is typically the table name. The field is not filled for all transaction types. | keyword |
| response | For text protocols, this is the response as seen on the wire (application layer only). For binary protocols this is our representation of the request. | text |
| server.bytes | Bytes sent from the server to the client. | long |
| server.ip | IP address of the server. | ip |
| server.port | Port of the server. | long |
| server.process.args | The command-line of the process that served the transaction. | keyword |
| server.process.executable | Absolute path to the server process executable. | keyword |
| server.process.name | The name of the process that served the transaction. | keyword |
| server.process.start | The time the server process started. | date |
| server.process.working_directory | The working directory of the server process. | keyword |
| source.bytes | Bytes sent from the source to the destination. | long |
| source.ip | IP address of the source. | ip |
| source.port | Port of the source. | long |
| status | The high level status of the transaction. The way to compute this value depends on the protocol, but the result has a meaning independent of the protocol. | keyword |
| type | The type of the transaction (for example, HTTP, MySQL, Redis, or RUM) or "flow" in case of flows. | keyword |


### DNS

Fields published for DNS packets.

**Exported fields**

| Field | Description | Type |
|---|---|---|
| @timestamp | Event timestamp. | date |
| client.bytes | Bytes sent from the client to the server. | long |
| client.ip | IP address of the client. | ip |
| client.port | Port of the client. | long |
| client.process.args | The command-line of the process that initiated the transaction. | keyword |
| client.process.executable | Absolute path to the client process executable. | keyword |
| client.process.name | The name of the process that initiated the transaction. | keyword |
| client.process.start | The time the client process started. | date |
| client.process.working_directory | The working directory of the client process. | keyword |
| cloud.account.id | The cloud account or organization id used to identify different entities in a multi-tenant environment. Examples: AWS account id, Google Cloud ORG Id, or other unique identifier. | keyword |
| cloud.availability_zone | Availability zone in which this host is running. | keyword |
| cloud.image.id | Image ID for the cloud instance. | keyword |
| cloud.instance.id | Instance ID of the host machine. | keyword |
| cloud.instance.name | Instance name of the host machine. | keyword |
| cloud.machine.type | Machine type of the host machine. | keyword |
| cloud.project.id | Name of the project in Google Cloud. | keyword |
| cloud.provider | Name of the cloud provider. Example values are aws, azure, gcp, or digitalocean. | keyword |
| cloud.region | Region in which this host is running. | keyword |
| container.id | Unique container id. | keyword |
| container.image.name | Name of the image the container was built on. | keyword |
| container.labels | Image labels. | object |
| container.name | Container name. | keyword |
| data_stream.dataset | Data stream dataset. | constant_keyword |
| data_stream.namespace | Data stream namespace. | constant_keyword |
| data_stream.type | Data stream type. | constant_keyword |
| destination.bytes | Bytes sent from the destination to the source. | long |
| destination.ip | IP address of the destination. | ip |
| destination.port | Port of the destination. | long |
| dns.additionals | An array containing a dictionary for each additional section from the answer. | object |
| dns.additionals.class | The class of DNS data contained in this resource record. | keyword |
| dns.additionals.data | The data describing the resource. The meaning of this data depends on the type and class of the resource record. | keyword |
| dns.additionals.name | The domain name to which this resource record pertains. | keyword |
| dns.additionals.ttl | The time interval in seconds that this resource record may be cached before it should be discarded. Zero values mean that the data should not be cached. | long |
| dns.additionals.type | The type of data contained in this resource record. | keyword |
| dns.additionals_count | The number of resource records contained in the `dns.additionals` field. The `dns.additionals` field may or may not be included depending on the configuration of Packetbeat. | long |
| dns.answers | Array of DNS answers. | object |
| dns.answers_count | The number of resource records contained in the `dns.answers` field. | long |
| dns.authorities | An array containing a dictionary for each authority section from the answer. | object |
| dns.authorities.class | The class of DNS data contained in this resource record. | keyword |
| dns.authorities.name | The domain name to which this resource record pertains. | keyword |
| dns.authorities.type | The type of data contained in this resource record. | keyword |
| dns.authorities_count | The number of resource records contained in the `dns.authorities` field. The `dns.authorities` field may or may not be included depending on the configuration of Packetbeat. | long |
| dns.flags.authentic_data | A DNS flag specifying that the recursive server considers the response authentic. | boolean |
| dns.flags.authoritative | A DNS flag specifying that the responding server is an authority for the domain name used in the question. | boolean |
| dns.flags.checking_disabled | A DNS flag specifying that the client disables the server signature validation of the query. | boolean |
| dns.flags.recursion_available | A DNS flag specifying whether recursive query support is available in the name server. | boolean |
| dns.flags.recursion_desired | A DNS flag specifying that the client directs the server to pursue a query recursively. Recursive query support is optional. | boolean |
| dns.flags.truncated_response | A DNS flag specifying that only the first 512 bytes of the reply were returned. | boolean |
| dns.header_flags | Array of DNS header flags. | keyword |
| dns.id | The DNS packet identifier assigned by the program that generated the query. The identifier is copied to the response. | keyword |
| dns.op_code | The DNS operation code that specifies the kind of query in the message. | keyword |
| dns.opt.do | If set, the transaction uses DNSSEC. | boolean |
| dns.opt.ext_rcode | Extended response code field. | keyword |
| dns.opt.udp_size | Requestor's UDP payload size (in bytes). | long |
| dns.opt.version | The EDNS version. | keyword |
| dns.question.class | The class of records being queried. | keyword |
| dns.question.etld_plus_one | The effective top-level domain (eTLD) plus one more label. For example, the eTLD+1 for "foo.bar.golang.org." is "golang.org.". The data for determining the eTLD comes from an embedded copy of the data from http://publicsuffix.org. | keyword |
| dns.question.name | The name being queried. | keyword |
| dns.question.registered_domain | The highest registered domain, stripped of the subdomain. | keyword |
| dns.question.subdomain | The subdomain of the domain. | keyword |
| dns.question.top_level_domain | The effective top level domain (com, org, net, co.uk). | keyword |
| dns.question.type | The type of record being queried. | keyword |
| dns.resolved_ip | Array containing all IPs seen in answers.data | ip |
| dns.response_code | The DNS response code. | keyword |
| dns.type | The type of DNS event captured, query or answer. | keyword |
| ecs.version | ECS version this event conforms to. | keyword |
| event.category | Event category. The second categorization field in the hierarchy. | keyword |
| event.dataset | Name of the dataset. | keyword |
| event.duration | Duration of the event in nanoseconds. | long |
| event.end | event.end contains the date when the event ended or when the activity was last observed. | date |
| event.kind | The kind of the event. The highest categorization field in the hierarchy. | keyword |
| event.start | event.start contains the date when the event started or when the activity was first observed. | date |
| event.type | Event type. The third categorization field in the hierarchy. | keyword |
| flow.final | Indicates if event is last event in flow. If final is false, the event reports an intermediate flow state only. | boolean |
| flow.id | Internal flow ID based on connection meta data and address. | keyword |
| flow.vlan | VLAN identifier from the 802.1q frame. In case of a multi-tagged frame this field will be an array with the outer tag's VLAN identifier listed first. | long |
| host.architecture | Operating system architecture. | keyword |
| host.containerized | If the host is a container. | boolean |
| host.domain | Name of the domain of which the host is a member. For example, on Windows this could be the host's Active Directory domain or NetBIOS domain name. For Linux this could be the domain of the host's LDAP provider. | keyword |
| host.hostname | Hostname of the host. It normally contains what the `hostname` command returns on the host machine. | keyword |
| host.id | Unique host id. As hostname is not always unique, use values that are meaningful in your environment. Example: The current usage of `beat.name`. | keyword |
| host.ip | Host ip addresses. | ip |
| host.mac | Host mac addresses. | keyword |
| host.name | Name of the host. It can contain what `hostname` returns on Unix systems, the fully qualified domain name, or a name specified by the user. The sender decides which value to use. | keyword |
| host.os.build | OS build information. | keyword |
| host.os.codename | OS codename, if any. | keyword |
| host.os.family | OS family (such as redhat, debian, freebsd, windows). | keyword |
| host.os.kernel | Operating system kernel version as a raw string. | keyword |
| host.os.name | Operating system name, without the version. | keyword |
| host.os.platform | Operating system platform (such centos, ubuntu, windows). | keyword |
| host.os.version | Operating system version as a raw string. | keyword |
| host.type | Type of host. For Cloud providers this can be the machine type like `t2.medium`. If vm, this could be the container, for example, or other information meaningful in your environment. | keyword |
| method | The command/verb/method of the transaction. For HTTP, this is the method name (GET, POST, PUT, and so on), for SQL this is the verb (SELECT, UPDATE, DELETE, and so on). | keyword |
| network.bytes | Total bytes transferred in both directions. | long |
| network.community_id | A hash of source and destination IPs and ports. | keyword |
| network.direction | Direction of the network traffic. | keyword |
| network.forwarded_ip | Host IP address when the source IP address is the proxy. | ip |
| network.protocol | L7 Network protocol name. | keyword |
| network.transport | Protocol Name corresponding to the field `iana_number`. | keyword |
| network.type | In the OSI Model this would be the Network Layer. ipv4, ipv6, ipsec, pim, etc | keyword |
| params | The request parameters. For HTTP, these are the POST or GET parameters. For Thrift-RPC, these are the parameters from the request. | text |
| path | The path the transaction refers to. For HTTP, this is the URL. For SQL databases, this is the table name. For key-value stores, this is the key. | keyword |
| query | The query in a human readable format. For HTTP, it will typically be something like `GET /users/_search?name=test`. For MySQL, it is something like `SELECT id from users where name=test`. | keyword |
| related.ip | All of the IPs seen on your event. | ip |
| request | For text protocols, this is the request as seen on the wire (application layer only). For binary protocols this is our representation of the request. | text |
| resource | The logical resource that this transaction refers to. For HTTP, this is the URL path up to the last slash (/). For example, if the URL is `/users/1`, the resource is `/users`. For databases, the resource is typically the table name. The field is not filled for all transaction types. | keyword |
| response | For text protocols, this is the response as seen on the wire (application layer only). For binary protocols this is our representation of the request. | text |
| server.bytes | Bytes sent from the server to the client. | long |
| server.ip | IP address of the server. | ip |
| server.port | Port of the server. | long |
| server.process.args | The command-line of the process that served the transaction. | keyword |
| server.process.executable | Absolute path to the server process executable. | keyword |
| server.process.name | The name of the process that served the transaction. | keyword |
| server.process.start | The time the server process started. | date |
| server.process.working_directory | The working directory of the server process. | keyword |
| source.bytes | Bytes sent from the source to the destination. | long |
| source.ip | IP address of the source. | ip |
| source.port | Port of the source. | long |
| status | The high level status of the transaction. The way to compute this value depends on the protocol, but the result has a meaning independent of the protocol. | keyword |
| type | The type of the transaction (for example, HTTP, MySQL, Redis, or RUM) or "flow" in case of flows. | keyword |


### HTTP

Fields published for HTTP packets.

**Exported fields**

| Field | Description | Type |
|---|---|---|
| @timestamp | Event timestamp. | date |
| client.bytes | Bytes sent from the client to the server. | long |
| client.ip | IP address of the client. | ip |
| client.port | Port of the client. | long |
| client.process.args | The command-line of the process that initiated the transaction. | keyword |
| client.process.executable | Absolute path to the client process executable. | keyword |
| client.process.name | The name of the process that initiated the transaction. | keyword |
| client.process.start | The time the client process started. | date |
| client.process.working_directory | The working directory of the client process. | keyword |
| cloud.account.id | The cloud account or organization id used to identify different entities in a multi-tenant environment. Examples: AWS account id, Google Cloud ORG Id, or other unique identifier. | keyword |
| cloud.availability_zone | Availability zone in which this host is running. | keyword |
| cloud.image.id | Image ID for the cloud instance. | keyword |
| cloud.instance.id | Instance ID of the host machine. | keyword |
| cloud.instance.name | Instance name of the host machine. | keyword |
| cloud.machine.type | Machine type of the host machine. | keyword |
| cloud.project.id | Name of the project in Google Cloud. | keyword |
| cloud.provider | Name of the cloud provider. Example values are aws, azure, gcp, or digitalocean. | keyword |
| cloud.region | Region in which this host is running. | keyword |
| container.id | Unique container id. | keyword |
| container.image.name | Name of the image the container was built on. | keyword |
| container.labels | Image labels. | object |
| container.name | Container name. | keyword |
| data_stream.dataset | Data stream dataset. | constant_keyword |
| data_stream.namespace | Data stream namespace. | constant_keyword |
| data_stream.type | Data stream type. | constant_keyword |
| destination.bytes | Bytes sent from the destination to the source. | long |
| destination.domain | Destination domain. | keyword |
| destination.ip | IP address of the destination. | ip |
| destination.port | Port of the destination. | long |
| ecs.version | ECS version this event conforms to. | keyword |
| event.category | Event category. The second categorization field in the hierarchy. | keyword |
| event.dataset | Name of the dataset. | keyword |
| event.duration | Duration of the event in nanoseconds. | long |
| event.end | event.end contains the date when the event ended or when the activity was last observed. | date |
| event.kind | The kind of the event. The highest categorization field in the hierarchy. | keyword |
| event.start | event.start contains the date when the event started or when the activity was first observed. | date |
| event.type | Event type. The third categorization field in the hierarchy. | keyword |
| flow.final | Indicates if event is last event in flow. If final is false, the event reports an intermediate flow state only. | boolean |
| flow.id | Internal flow ID based on connection meta data and address. | keyword |
| flow.vlan | VLAN identifier from the 802.1q frame. In case of a multi-tagged frame this field will be an array with the outer tag's VLAN identifier listed first. | long |
| host.architecture | Operating system architecture. | keyword |
| host.containerized | If the host is a container. | boolean |
| host.domain | Name of the domain of which the host is a member. For example, on Windows this could be the host's Active Directory domain or NetBIOS domain name. For Linux this could be the domain of the host's LDAP provider. | keyword |
| host.hostname | Hostname of the host. It normally contains what the `hostname` command returns on the host machine. | keyword |
| host.id | Unique host id. As hostname is not always unique, use values that are meaningful in your environment. Example: The current usage of `beat.name`. | keyword |
| host.ip | Host ip addresses. | ip |
| host.mac | Host mac addresses. | keyword |
| host.name | Name of the host. It can contain what `hostname` returns on Unix systems, the fully qualified domain name, or a name specified by the user. The sender decides which value to use. | keyword |
| host.os.build | OS build information. | keyword |
| host.os.codename | OS codename, if any. | keyword |
| host.os.family | OS family (such as redhat, debian, freebsd, windows). | keyword |
| host.os.kernel | Operating system kernel version as a raw string. | keyword |
| host.os.name | Operating system name, without the version. | keyword |
| host.os.platform | Operating system platform (such centos, ubuntu, windows). | keyword |
| host.os.version | Operating system version as a raw string. | keyword |
| host.type | Type of host. For Cloud providers this can be the machine type like `t2.medium`. If vm, this could be the container, for example, or other information meaningful in your environment. | keyword |
| http.request.body.bytes | Size in bytes of the request body. | long |
| http.request.bytes | Total size in bytes of the request (body and headers). | long |
| http.request.headers | A map containing the captured header fields from the request. Which headers to capture is configurable. If headers with the same header name are present in the message, they will be separated by commas. | flattened |
| http.request.method | HTTP request method. | keyword |
| http.request.referrer | Referrer for this HTTP request. | keyword |
| http.response.body.bytes | Size in bytes of the response body. | long |
| http.response.bytes | Total size in bytes of the response (body and headers). | long |
| http.response.headers | A map containing the captured header fields from the response. Which headers to capture is configurable. If headers with the same header name are present in the message, they will be separated by commas. | flattened |
| http.response.status_code | HTTP response status code. | long |
| http.response.status_phrase | The HTTP status phrase. | keyword |
| http.version | HTTP version. | keyword |
| method | The command/verb/method of the transaction. For HTTP, this is the method name (GET, POST, PUT, and so on), for SQL this is the verb (SELECT, UPDATE, DELETE, and so on). | keyword |
| network.bytes | Total bytes transferred in both directions. | long |
| network.community_id | A hash of source and destination IPs and ports. | keyword |
| network.direction | Direction of the network traffic. | keyword |
| network.forwarded_ip | Host IP address when the source IP address is the proxy. | ip |
| network.protocol | L7 Network protocol name. | keyword |
| network.transport | Protocol Name corresponding to the field `iana_number`. | keyword |
| network.type | In the OSI Model this would be the Network Layer. ipv4, ipv6, ipsec, pim, etc | keyword |
| params | The request parameters. For HTTP, these are the POST or GET parameters. For Thrift-RPC, these are the parameters from the request. | text |
| path | The path the transaction refers to. For HTTP, this is the URL. For SQL databases, this is the table name. For key-value stores, this is the key. | keyword |
| query | The query in a human readable format. For HTTP, it will typically be something like `GET /users/_search?name=test`. For MySQL, it is something like `SELECT id from users where name=test`. | keyword |
| related.hosts | All the host identifiers seen on your event. | keyword |
| related.ip | All of the IPs seen on your event. | ip |
| request | For text protocols, this is the request as seen on the wire (application layer only). For binary protocols this is our representation of the request. | text |
| resource | The logical resource that this transaction refers to. For HTTP, this is the URL path up to the last slash (/). For example, if the URL is `/users/1`, the resource is `/users`. For databases, the resource is typically the table name. The field is not filled for all transaction types. | keyword |
| response | For text protocols, this is the response as seen on the wire (application layer only). For binary protocols this is our representation of the request. | text |
| server.bytes | Bytes sent from the server to the client. | long |
| server.domain | Server domain. | keyword |
| server.ip | IP address of the server. | ip |
| server.port | Port of the server. | long |
| server.process.args | The command-line of the process that served the transaction. | keyword |
| server.process.executable | Absolute path to the server process executable. | keyword |
| server.process.name | The name of the process that served the transaction. | keyword |
| server.process.start | The time the server process started. | date |
| server.process.working_directory | The working directory of the server process. | keyword |
| source.bytes | Bytes sent from the source to the destination. | long |
| source.ip | IP address of the source. | ip |
| source.port | Port of the source. | long |
| status | The high level status of the transaction. The way to compute this value depends on the protocol, but the result has a meaning independent of the protocol. | keyword |
| type | The type of the transaction (for example, HTTP, MySQL, Redis, or RUM) or "flow" in case of flows. | keyword |
| url.domain | Domain of the url. | keyword |
| url.extension | File extension from the request url, excluding the leading dot. | keyword |
| url.full | Full unparsed URL. | keyword |
| url.path | Path of the request, such as "/search". | keyword |
| url.port | Port of the request, such as 443. | long |
| url.query | Query string of the request. | keyword |
| url.scheme | Scheme of the url. | keyword |
| user_agent.original | Unparsed user_agent string. | keyword |


### ICMP

Fields published for ICMP packets.

**Exported fields**

| Field | Description | Type |
|---|---|---|
| @timestamp | Event timestamp. | date |
| client.bytes | Bytes sent from the client to the server. | long |
| client.ip | IP address of the client. | ip |
| client.port | Port of the client. | long |
| client.process.args | The command-line of the process that initiated the transaction. | keyword |
| client.process.executable | Absolute path to the client process executable. | keyword |
| client.process.name | The name of the process that initiated the transaction. | keyword |
| client.process.start | The time the client process started. | date |
| client.process.working_directory | The working directory of the client process. | keyword |
| cloud.account.id | The cloud account or organization id used to identify different entities in a multi-tenant environment. Examples: AWS account id, Google Cloud ORG Id, or other unique identifier. | keyword |
| cloud.availability_zone | Availability zone in which this host is running. | keyword |
| cloud.image.id | Image ID for the cloud instance. | keyword |
| cloud.instance.id | Instance ID of the host machine. | keyword |
| cloud.instance.name | Instance name of the host machine. | keyword |
| cloud.machine.type | Machine type of the host machine. | keyword |
| cloud.project.id | Name of the project in Google Cloud. | keyword |
| cloud.provider | Name of the cloud provider. Example values are aws, azure, gcp, or digitalocean. | keyword |
| cloud.region | Region in which this host is running. | keyword |
| container.id | Unique container id. | keyword |
| container.image.name | Name of the image the container was built on. | keyword |
| container.labels | Image labels. | object |
| container.name | Container name. | keyword |
| data_stream.dataset | Data stream dataset. | constant_keyword |
| data_stream.namespace | Data stream namespace. | constant_keyword |
| data_stream.type | Data stream type. | constant_keyword |
| destination.bytes | Bytes sent from the destination to the source. | long |
| destination.ip | IP address of the destination. | ip |
| destination.port | Port of the destination. | long |
| ecs.version | ECS version this event conforms to. | keyword |
| event.category | Event category. The second categorization field in the hierarchy. | keyword |
| event.dataset | Name of the dataset. | keyword |
| event.duration | Duration of the event in nanoseconds. | long |
| event.end | event.end contains the date when the event ended or when the activity was last observed. | date |
| event.kind | The kind of the event. The highest categorization field in the hierarchy. | keyword |
| event.start | event.start contains the date when the event started or when the activity was first observed. | date |
| event.type | Event type. The third categorization field in the hierarchy. | keyword |
| flow.final | Indicates if event is last event in flow. If final is false, the event reports an intermediate flow state only. | boolean |
| flow.id | Internal flow ID based on connection meta data and address. | keyword |
| flow.vlan | VLAN identifier from the 802.1q frame. In case of a multi-tagged frame this field will be an array with the outer tag's VLAN identifier listed first. | long |
| host.architecture | Operating system architecture. | keyword |
| host.containerized | If the host is a container. | boolean |
| host.domain | Name of the domain of which the host is a member. For example, on Windows this could be the host's Active Directory domain or NetBIOS domain name. For Linux this could be the domain of the host's LDAP provider. | keyword |
| host.hostname | Hostname of the host. It normally contains what the `hostname` command returns on the host machine. | keyword |
| host.id | Unique host id. As hostname is not always unique, use values that are meaningful in your environment. Example: The current usage of `beat.name`. | keyword |
| host.ip | Host ip addresses. | ip |
| host.mac | Host mac addresses. | keyword |
| host.name | Name of the host. It can contain what `hostname` returns on Unix systems, the fully qualified domain name, or a name specified by the user. The sender decides which value to use. | keyword |
| host.os.build | OS build information. | keyword |
| host.os.codename | OS codename, if any. | keyword |
| host.os.family | OS family (such as redhat, debian, freebsd, windows). | keyword |
| host.os.kernel | Operating system kernel version as a raw string. | keyword |
| host.os.name | Operating system name, without the version. | keyword |
| host.os.platform | Operating system platform (such centos, ubuntu, windows). | keyword |
| host.os.version | Operating system version as a raw string. | keyword |
| host.type | Type of host. For Cloud providers this can be the machine type like `t2.medium`. If vm, this could be the container, for example, or other information meaningful in your environment. | keyword |
| icmp.request.code | The request code. | long |
| icmp.request.message | A human readable form of the request. | keyword |
| icmp.request.type | The request type. | long |
| icmp.response.code | The response code. | long |
| icmp.response.message | A human readable form of the response. | keyword |
| icmp.response.type | The response type. | long |
| icmp.version | The version of the ICMP protocol. | long |
| method | The command/verb/method of the transaction. For HTTP, this is the method name (GET, POST, PUT, and so on), for SQL this is the verb (SELECT, UPDATE, DELETE, and so on). | keyword |
| network.bytes | Total bytes transferred in both directions. | long |
| network.community_id | A hash of source and destination IPs and ports. | keyword |
| network.direction | Direction of the network traffic. | keyword |
| network.forwarded_ip | Host IP address when the source IP address is the proxy. | ip |
| network.protocol | L7 Network protocol name. | keyword |
| network.transport | Protocol Name corresponding to the field `iana_number`. | keyword |
| network.type | In the OSI Model this would be the Network Layer. ipv4, ipv6, ipsec, pim, etc | keyword |
| params | The request parameters. For HTTP, these are the POST or GET parameters. For Thrift-RPC, these are the parameters from the request. | text |
| path | The path the transaction refers to. For HTTP, this is the URL. For SQL databases, this is the table name. For key-value stores, this is the key. | keyword |
| query | The query in a human readable format. For HTTP, it will typically be something like `GET /users/_search?name=test`. For MySQL, it is something like `SELECT id from users where name=test`. | keyword |
| related.ip | All of the IPs seen on your event. | ip |
| request | For text protocols, this is the request as seen on the wire (application layer only). For binary protocols this is our representation of the request. | text |
| resource | The logical resource that this transaction refers to. For HTTP, this is the URL path up to the last slash (/). For example, if the URL is `/users/1`, the resource is `/users`. For databases, the resource is typically the table name. The field is not filled for all transaction types. | keyword |
| response | For text protocols, this is the response as seen on the wire (application layer only). For binary protocols this is our representation of the request. | text |
| server.bytes | Bytes sent from the server to the client. | long |
| server.ip | IP address of the server. | ip |
| server.port | Port of the server. | long |
| server.process.args | The command-line of the process that served the transaction. | keyword |
| server.process.executable | Absolute path to the server process executable. | keyword |
| server.process.name | The name of the process that served the transaction. | keyword |
| server.process.start | The time the server process started. | date |
| server.process.working_directory | The working directory of the server process. | keyword |
| source.bytes | Bytes sent from the source to the destination. | long |
| source.ip | IP address of the source. | ip |
| source.port | Port of the source. | long |
| status | The high level status of the transaction. The way to compute this value depends on the protocol, but the result has a meaning independent of the protocol. | keyword |
| type | The type of the transaction (for example, HTTP, MySQL, Redis, or RUM) or "flow" in case of flows. | keyword |


### Memcached

Fields published for Memcached packets.

**Exported fields**

| Field | Description | Type |
|---|---|---|
| @timestamp | Event timestamp. | date |
| client.bytes | Bytes sent from the client to the server. | long |
| client.ip | IP address of the client. | ip |
| client.port | Port of the client. | long |
| client.process.args | The command-line of the process that initiated the transaction. | keyword |
| client.process.executable | Absolute path to the client process executable. | keyword |
| client.process.name | The name of the process that initiated the transaction. | keyword |
| client.process.start | The time the client process started. | date |
| client.process.working_directory | The working directory of the client process. | keyword |
| cloud.account.id | The cloud account or organization id used to identify different entities in a multi-tenant environment. Examples: AWS account id, Google Cloud ORG Id, or other unique identifier. | keyword |
| cloud.availability_zone | Availability zone in which this host is running. | keyword |
| cloud.image.id | Image ID for the cloud instance. | keyword |
| cloud.instance.id | Instance ID of the host machine. | keyword |
| cloud.instance.name | Instance name of the host machine. | keyword |
| cloud.machine.type | Machine type of the host machine. | keyword |
| cloud.project.id | Name of the project in Google Cloud. | keyword |
| cloud.provider | Name of the cloud provider. Example values are aws, azure, gcp, or digitalocean. | keyword |
| cloud.region | Region in which this host is running. | keyword |
| container.id | Unique container id. | keyword |
| container.image.name | Name of the image the container was built on. | keyword |
| container.labels | Image labels. | object |
| container.name | Container name. | keyword |
| data_stream.dataset | Data stream dataset. | constant_keyword |
| data_stream.namespace | Data stream namespace. | constant_keyword |
| data_stream.type | Data stream type. | constant_keyword |
| destination.bytes | Bytes sent from the destination to the source. | long |
| destination.ip | IP address of the destination. | ip |
| destination.port | Port of the destination. | long |
| ecs.version | ECS version this event conforms to. | keyword |
| event.category | Event category. The second categorization field in the hierarchy. | keyword |
| event.dataset | Name of the dataset. | keyword |
| event.duration | Duration of the event in nanoseconds. | long |
| event.end | event.end contains the date when the event ended or when the activity was last observed. | date |
| event.kind | The kind of the event. The highest categorization field in the hierarchy. | keyword |
| event.start | event.start contains the date when the event started or when the activity was first observed. | date |
| event.type | Event type. The third categorization field in the hierarchy. | keyword |
| flow.final | Indicates if event is last event in flow. If final is false, the event reports an intermediate flow state only. | boolean |
| flow.id | Internal flow ID based on connection meta data and address. | keyword |
| flow.vlan | VLAN identifier from the 802.1q frame. In case of a multi-tagged frame this field will be an array with the outer tag's VLAN identifier listed first. | long |
| host.architecture | Operating system architecture. | keyword |
| host.containerized | If the host is a container. | boolean |
| host.domain | Name of the domain of which the host is a member. For example, on Windows this could be the host's Active Directory domain or NetBIOS domain name. For Linux this could be the domain of the host's LDAP provider. | keyword |
| host.hostname | Hostname of the host. It normally contains what the `hostname` command returns on the host machine. | keyword |
| host.id | Unique host id. As hostname is not always unique, use values that are meaningful in your environment. Example: The current usage of `beat.name`. | keyword |
| host.ip | Host ip addresses. | ip |
| host.mac | Host mac addresses. | keyword |
| host.name | Name of the host. It can contain what `hostname` returns on Unix systems, the fully qualified domain name, or a name specified by the user. The sender decides which value to use. | keyword |
| host.os.build | OS build information. | keyword |
| host.os.codename | OS codename, if any. | keyword |
| host.os.family | OS family (such as redhat, debian, freebsd, windows). | keyword |
| host.os.kernel | Operating system kernel version as a raw string. | keyword |
| host.os.name | Operating system name, without the version. | keyword |
| host.os.platform | Operating system platform (such centos, ubuntu, windows). | keyword |
| host.os.version | Operating system version as a raw string. | keyword |
| host.type | Type of host. For Cloud providers this can be the machine type like `t2.medium`. If vm, this could be the container, for example, or other information meaningful in your environment. | keyword |
| memcache.protocol_type | The memcache protocol implementation. The value can be "binary" for binary-based, "text" for text-based, or "unknown" for an unknown memcache protocol type. | keyword |
| memcache.request.automove | The automove mode in the 'slab automove' command expressed as a string. This value can be "standby"(=0), "slow"(=1), "aggressive"(=2), or the raw value if the value is unknown. | keyword |
| memcache.request.bytes | The byte count of the values being transferred. | long |
| memcache.request.cas_unique | The CAS (compare-and-swap) identifier if present. | long |
| memcache.request.command | The memcache command being requested in the memcache text protocol. For example "set" or "get". The binary protocol opcodes are translated into memcache text protocol commands. | keyword |
| memcache.request.count_values | The number of values found in the memcache request message. If the command does not send any data, this field is missing. | long |
| memcache.request.delta | The counter increment/decrement delta value. | long |
| memcache.request.dest_class | The destination class id in 'slab reassign' command. | long |
| memcache.request.exptime | The data expiry time in seconds sent with the memcache command (if present). If the value is <30 days, the expiry time is relative to "now", or else it is an absolute Unix time in seconds (32-bit). | long |
| memcache.request.flags | The memcache command flags sent in the request (if present). | long |
| memcache.request.initial | The counter increment/decrement initial value parameter (binary protocol only). | long |
| memcache.request.keys | The list of keys sent in the store or load commands. | array |
| memcache.request.line | The raw command line for unknown commands ONLY. | keyword |
| memcache.request.noreply | Set to true if noreply was set in the request. The `memcache.response` field will be missing. | boolean |
| memcache.request.opaque | The binary protocol opaque header value used for correlating request with response messages. | long |
| memcache.request.opcode | The binary protocol message opcode name. | keyword |
| memcache.request.opcode_value | The binary protocol message opcode value. | long |
| memcache.request.quiet | Set to true if the binary protocol message is to be treated as a quiet message. | boolean |
| memcache.request.raw_args | The text protocol raw arguments for the "stats ..." and "lru crawl ..." commands. | keyword |
| memcache.request.sleep_us | The sleep setting in microseconds for the 'lru_crawler sleep' command. | long |
| memcache.request.source_class | The source class id in 'slab reassign' command. | long |
| memcache.request.type | The memcache command classification. This value can be "UNKNOWN", "Load", "Store", "Delete", "Counter", "Info", "SlabCtrl", "LRUCrawler", "Stats", "Success", "Fail", or "Auth". | keyword |
| memcache.request.values | The list of base64 encoded values sent with the request (if present). | array |
| memcache.request.vbucket | The vbucket index sent in the binary message. | long |
| memcache.request.verbosity | The value of the memcache "verbosity" command. | long |
| memcache.response.bytes | The byte count of the values being transferred. | long |
| memcache.response.cas_unique | The CAS (compare-and-swap) identifier to be used with CAS-based updates (if present). | long |
| memcache.response.command | Either the text based protocol response message type or the name of the originating request if binary protocol is used. | keyword |
| memcache.response.count_values | The number of values found in the memcache response message. If the command does not send any data, this field is missing. | long |
| memcache.response.error_msg | The optional error message in the memcache response (text based protocol only). | keyword |
| memcache.response.flags | The memcache message flags sent in the response (if present). | long |
| memcache.response.keys | The list of keys returned for the load command (if present). | array |
| memcache.response.opaque | The binary protocol opaque header value used for correlating request with response messages. | long |
| memcache.response.opcode | The binary protocol message opcode name. | keyword |
| memcache.response.opcode_value | The binary protocol message opcode value. | long |
| memcache.response.stats | The list of statistic values returned. Each entry is a dictionary with the fields "name" and "value". | array |
| memcache.response.status | The textual representation of the response error code (binary protocol only). | keyword |
| memcache.response.status_code | The status code value returned in the response (binary protocol only). | long |
| memcache.response.type | The memcache command classification. This value can be "UNKNOWN", "Load", "Store", "Delete", "Counter", "Info", "SlabCtrl", "LRUCrawler", "Stats", "Success", "Fail", or "Auth". The text based protocol will employ any of these, whereas the binary based protocol will mirror the request commands only (see `memcache.response.status` for binary protocol). | keyword |
| memcache.response.value | The counter value returned by a counter operation. | long |
| memcache.response.values | The list of base64 encoded values sent with the response (if present). | array |
| memcache.response.version | The returned memcache version string. | keyword |
| method | The command/verb/method of the transaction. For HTTP, this is the method name (GET, POST, PUT, and so on), for SQL this is the verb (SELECT, UPDATE, DELETE, and so on). | keyword |
| network.bytes | Total bytes transferred in both directions. | long |
| network.community_id | A hash of source and destination IPs and ports. | keyword |
| network.direction | Direction of the network traffic. | keyword |
| network.forwarded_ip | Host IP address when the source IP address is the proxy. | ip |
| network.protocol | L7 Network protocol name. | keyword |
| network.transport | Protocol Name corresponding to the field `iana_number`. | keyword |
| network.type | In the OSI Model this would be the Network Layer. ipv4, ipv6, ipsec, pim, etc | keyword |
| params | The request parameters. For HTTP, these are the POST or GET parameters. For Thrift-RPC, these are the parameters from the request. | text |
| path | The path the transaction refers to. For HTTP, this is the URL. For SQL databases, this is the table name. For key-value stores, this is the key. | keyword |
| query | The query in a human readable format. For HTTP, it will typically be something like `GET /users/_search?name=test`. For MySQL, it is something like `SELECT id from users where name=test`. | keyword |
| related.ip | All of the IPs seen on your event. | ip |
| request | For text protocols, this is the request as seen on the wire (application layer only). For binary protocols this is our representation of the request. | text |
| resource | The logical resource that this transaction refers to. For HTTP, this is the URL path up to the last slash (/). For example, if the URL is `/users/1`, the resource is `/users`. For databases, the resource is typically the table name. The field is not filled for all transaction types. | keyword |
| response | For text protocols, this is the response as seen on the wire (application layer only). For binary protocols this is our representation of the request. | text |
| server.bytes | Bytes sent from the server to the client. | long |
| server.ip | IP address of the server. | ip |
| server.port | Port of the server. | long |
| server.process.args | The command-line of the process that served the transaction. | keyword |
| server.process.executable | Absolute path to the server process executable. | keyword |
| server.process.name | The name of the process that served the transaction. | keyword |
| server.process.start | The time the server process started. | date |
| server.process.working_directory | The working directory of the server process. | keyword |
| source.bytes | Bytes sent from the source to the destination. | long |
| source.ip | IP address of the source. | ip |
| source.port | Port of the source. | long |
| status | The high level status of the transaction. The way to compute this value depends on the protocol, but the result has a meaning independent of the protocol. | keyword |
| type | The type of the transaction (for example, HTTP, MySQL, Redis, or RUM) or "flow" in case of flows. | keyword |


### MongoDB

Fields published for MongoDB packets.

**Exported fields**

| Field | Description | Type |
|---|---|---|
| @timestamp | Event timestamp. | date |
| client.bytes | Bytes sent from the client to the server. | long |
| client.ip | IP address of the client. | ip |
| client.port | Port of the client. | long |
| client.process.args | The command-line of the process that initiated the transaction. | keyword |
| client.process.executable | Absolute path to the client process executable. | keyword |
| client.process.name | The name of the process that initiated the transaction. | keyword |
| client.process.start | The time the client process started. | date |
| client.process.working_directory | The working directory of the client process. | keyword |
| cloud.account.id | The cloud account or organization id used to identify different entities in a multi-tenant environment. Examples: AWS account id, Google Cloud ORG Id, or other unique identifier. | keyword |
| cloud.availability_zone | Availability zone in which this host is running. | keyword |
| cloud.image.id | Image ID for the cloud instance. | keyword |
| cloud.instance.id | Instance ID of the host machine. | keyword |
| cloud.instance.name | Instance name of the host machine. | keyword |
| cloud.machine.type | Machine type of the host machine. | keyword |
| cloud.project.id | Name of the project in Google Cloud. | keyword |
| cloud.provider | Name of the cloud provider. Example values are aws, azure, gcp, or digitalocean. | keyword |
| cloud.region | Region in which this host is running. | keyword |
| container.id | Unique container id. | keyword |
| container.image.name | Name of the image the container was built on. | keyword |
| container.labels | Image labels. | object |
| container.name | Container name. | keyword |
| data_stream.dataset | Data stream dataset. | constant_keyword |
| data_stream.namespace | Data stream namespace. | constant_keyword |
| data_stream.type | Data stream type. | constant_keyword |
| destination.bytes | Bytes sent from the destination to the source. | long |
| destination.ip | IP address of the destination. | ip |
| destination.port | Port of the destination. | long |
| ecs.version | ECS version this event conforms to. | keyword |
| event.category | Event category. The second categorization field in the hierarchy. | keyword |
| event.dataset | Name of the dataset. | keyword |
| event.duration | Duration of the event in nanoseconds. | long |
| event.end | event.end contains the date when the event ended or when the activity was last observed. | date |
| event.kind | The kind of the event. The highest categorization field in the hierarchy. | keyword |
| event.start | event.start contains the date when the event started or when the activity was first observed. | date |
| event.type | Event type. The third categorization field in the hierarchy. | keyword |
| flow.final | Indicates if event is last event in flow. If final is false, the event reports an intermediate flow state only. | boolean |
| flow.id | Internal flow ID based on connection meta data and address. | keyword |
| flow.vlan | VLAN identifier from the 802.1q frame. In case of a multi-tagged frame this field will be an array with the outer tag's VLAN identifier listed first. | long |
| host.architecture | Operating system architecture. | keyword |
| host.containerized | If the host is a container. | boolean |
| host.domain | Name of the domain of which the host is a member. For example, on Windows this could be the host's Active Directory domain or NetBIOS domain name. For Linux this could be the domain of the host's LDAP provider. | keyword |
| host.hostname | Hostname of the host. It normally contains what the `hostname` command returns on the host machine. | keyword |
| host.id | Unique host id. As hostname is not always unique, use values that are meaningful in your environment. Example: The current usage of `beat.name`. | keyword |
| host.ip | Host ip addresses. | ip |
| host.mac | Host mac addresses. | keyword |
| host.name | Name of the host. It can contain what `hostname` returns on Unix systems, the fully qualified domain name, or a name specified by the user. The sender decides which value to use. | keyword |
| host.os.build | OS build information. | keyword |
| host.os.codename | OS codename, if any. | keyword |
| host.os.family | OS family (such as redhat, debian, freebsd, windows). | keyword |
| host.os.kernel | Operating system kernel version as a raw string. | keyword |
| host.os.name | Operating system name, without the version. | keyword |
| host.os.platform | Operating system platform (such centos, ubuntu, windows). | keyword |
| host.os.version | Operating system version as a raw string. | keyword |
| host.type | Type of host. For Cloud providers this can be the machine type like `t2.medium`. If vm, this could be the container, for example, or other information meaningful in your environment. | keyword |
| method | The command/verb/method of the transaction. For HTTP, this is the method name (GET, POST, PUT, and so on), for SQL this is the verb (SELECT, UPDATE, DELETE, and so on). | keyword |
| mongodb.cursorId | The cursor identifier returned in the OP_REPLY. This must be the value that was returned from the database. | keyword |
| mongodb.error | If the MongoDB request has resulted in an error, this field contains the error message returned by the server. | keyword |
| mongodb.fullCollectionName | The full collection name. The full collection name is the concatenation of the database name with the collection name, using a dot (.) for the concatenation. For example, for the database foo and the collection bar, the full collection name is foo.bar. | keyword |
| mongodb.numberReturned | The number of documents in the reply. | long |
| mongodb.numberToReturn | The requested maximum number of documents to be returned. | long |
| mongodb.numberToSkip | Sets the number of documents to omit - starting from the first document in the resulting dataset - when returning the result of the query. | long |
| mongodb.query | A JSON document that represents the query. The query will contain one or more elements, all of which must match for a document to be included in the result set. Possible elements include $query, $orderby, $hint, $explain, and $snapshot. | keyword |
| mongodb.returnFieldsSelector | A JSON document that limits the fields in the returned documents. The returnFieldsSelector contains one or more elements, each of which is the name of a field that should be returned, and the integer value 1. | keyword |
| mongodb.selector | A BSON document that specifies the query for selecting the document to update or delete. | keyword |
| mongodb.startingFrom | Where in the cursor this reply is starting. | keyword |
| mongodb.update | A BSON document that specifies the update to be performed. For information on specifying updates, see the Update Operations documentation from the MongoDB Manual. | keyword |
| network.bytes | Total bytes transferred in both directions. | long |
| network.community_id | A hash of source and destination IPs and ports. | keyword |
| network.direction | Direction of the network traffic. | keyword |
| network.forwarded_ip | Host IP address when the source IP address is the proxy. | ip |
| network.protocol | L7 Network protocol name. | keyword |
| network.transport | Protocol Name corresponding to the field `iana_number`. | keyword |
| network.type | In the OSI Model this would be the Network Layer. ipv4, ipv6, ipsec, pim, etc | keyword |
| params | The request parameters. For HTTP, these are the POST or GET parameters. For Thrift-RPC, these are the parameters from the request. | text |
| path | The path the transaction refers to. For HTTP, this is the URL. For SQL databases, this is the table name. For key-value stores, this is the key. | keyword |
| query | The query in a human readable format. For HTTP, it will typically be something like `GET /users/_search?name=test`. For MySQL, it is something like `SELECT id from users where name=test`. | keyword |
| related.ip | All of the IPs seen on your event. | ip |
| request | For text protocols, this is the request as seen on the wire (application layer only). For binary protocols this is our representation of the request. | text |
| resource | The logical resource that this transaction refers to. For HTTP, this is the URL path up to the last slash (/). For example, if the URL is `/users/1`, the resource is `/users`. For databases, the resource is typically the table name. The field is not filled for all transaction types. | keyword |
| response | For text protocols, this is the response as seen on the wire (application layer only). For binary protocols this is our representation of the request. | text |
| server.bytes | Bytes sent from the server to the client. | long |
| server.ip | IP address of the server. | ip |
| server.port | Port of the server. | long |
| server.process.args | The command-line of the process that served the transaction. | keyword |
| server.process.executable | Absolute path to the server process executable. | keyword |
| server.process.name | The name of the process that served the transaction. | keyword |
| server.process.start | The time the server process started. | date |
| server.process.working_directory | The working directory of the server process. | keyword |
| source.bytes | Bytes sent from the source to the destination. | long |
| source.ip | IP address of the source. | ip |
| source.port | Port of the source. | long |
| status | The high level status of the transaction. The way to compute this value depends on the protocol, but the result has a meaning independent of the protocol. | keyword |
| type | The type of the transaction (for example, HTTP, MySQL, Redis, or RUM) or "flow" in case of flows. | keyword |


### MySQL

Fields published for MySQL packets.

**Exported fields**

| Field | Description | Type |
|---|---|---|
| @timestamp | Event timestamp. | date |
| client.bytes | Bytes sent from the client to the server. | long |
| client.ip | IP address of the client. | ip |
| client.port | Port of the client. | long |
| client.process.args | The command-line of the process that initiated the transaction. | keyword |
| client.process.executable | Absolute path to the client process executable. | keyword |
| client.process.name | The name of the process that initiated the transaction. | keyword |
| client.process.start | The time the client process started. | date |
| client.process.working_directory | The working directory of the client process. | keyword |
| cloud.account.id | The cloud account or organization id used to identify different entities in a multi-tenant environment. Examples: AWS account id, Google Cloud ORG Id, or other unique identifier. | keyword |
| cloud.availability_zone | Availability zone in which this host is running. | keyword |
| cloud.image.id | Image ID for the cloud instance. | keyword |
| cloud.instance.id | Instance ID of the host machine. | keyword |
| cloud.instance.name | Instance name of the host machine. | keyword |
| cloud.machine.type | Machine type of the host machine. | keyword |
| cloud.project.id | Name of the project in Google Cloud. | keyword |
| cloud.provider | Name of the cloud provider. Example values are aws, azure, gcp, or digitalocean. | keyword |
| cloud.region | Region in which this host is running. | keyword |
| container.id | Unique container id. | keyword |
| container.image.name | Name of the image the container was built on. | keyword |
| container.labels | Image labels. | object |
| container.name | Container name. | keyword |
| data_stream.dataset | Data stream dataset. | constant_keyword |
| data_stream.namespace | Data stream namespace. | constant_keyword |
| data_stream.type | Data stream type. | constant_keyword |
| destination.bytes | Bytes sent from the destination to the source. | long |
| destination.ip | IP address of the destination. | ip |
| destination.port | Port of the destination. | long |
| ecs.version | ECS version this event conforms to. | keyword |
| event.category | Event category. The second categorization field in the hierarchy. | keyword |
| event.dataset | Name of the dataset. | keyword |
| event.duration | Duration of the event in nanoseconds. | long |
| event.end | event.end contains the date when the event ended or when the activity was last observed. | date |
| event.kind | The kind of the event. The highest categorization field in the hierarchy. | keyword |
| event.start | event.start contains the date when the event started or when the activity was first observed. | date |
| event.type | Event type. The third categorization field in the hierarchy. | keyword |
| flow.final | Indicates if event is last event in flow. If final is false, the event reports an intermediate flow state only. | boolean |
| flow.id | Internal flow ID based on connection meta data and address. | keyword |
| flow.vlan | VLAN identifier from the 802.1q frame. In case of a multi-tagged frame this field will be an array with the outer tag's VLAN identifier listed first. | long |
| host.architecture | Operating system architecture. | keyword |
| host.containerized | If the host is a container. | boolean |
| host.domain | Name of the domain of which the host is a member. For example, on Windows this could be the host's Active Directory domain or NetBIOS domain name. For Linux this could be the domain of the host's LDAP provider. | keyword |
| host.hostname | Hostname of the host. It normally contains what the `hostname` command returns on the host machine. | keyword |
| host.id | Unique host id. As hostname is not always unique, use values that are meaningful in your environment. Example: The current usage of `beat.name`. | keyword |
| host.ip | Host ip addresses. | ip |
| host.mac | Host mac addresses. | keyword |
| host.name | Name of the host. It can contain what `hostname` returns on Unix systems, the fully qualified domain name, or a name specified by the user. The sender decides which value to use. | keyword |
| host.os.build | OS build information. | keyword |
| host.os.codename | OS codename, if any. | keyword |
| host.os.family | OS family (such as redhat, debian, freebsd, windows). | keyword |
| host.os.kernel | Operating system kernel version as a raw string. | keyword |
| host.os.name | Operating system name, without the version. | keyword |
| host.os.platform | Operating system platform (such centos, ubuntu, windows). | keyword |
| host.os.version | Operating system version as a raw string. | keyword |
| host.type | Type of host. For Cloud providers this can be the machine type like `t2.medium`. If vm, this could be the container, for example, or other information meaningful in your environment. | keyword |
| method | The command/verb/method of the transaction. For HTTP, this is the method name (GET, POST, PUT, and so on), for SQL this is the verb (SELECT, UPDATE, DELETE, and so on). | keyword |
| mysql.affected_rows | If the MySQL command is successful, this field contains the affected number of rows of the last statement. | long |
| mysql.error_code | The error code returned by MySQL. | long |
| mysql.error_message | The error info message returned by MySQL. | keyword |
| mysql.insert_id | If the INSERT query is successful, this field contains the id of the newly inserted row. | keyword |
| mysql.num_fields | If the SELECT query is successful, this field is set to the number of fields returned. | long |
| mysql.num_rows | If the SELECT query is successful, this field is set to the number of rows returned. | long |
| mysql.query | The row mysql query as read from the transaction's request. | keyword |
| network.bytes | Total bytes transferred in both directions. | long |
| network.community_id | A hash of source and destination IPs and ports. | keyword |
| network.direction | Direction of the network traffic. | keyword |
| network.forwarded_ip | Host IP address when the source IP address is the proxy. | ip |
| network.protocol | L7 Network protocol name. | keyword |
| network.transport | Protocol Name corresponding to the field `iana_number`. | keyword |
| network.type | In the OSI Model this would be the Network Layer. ipv4, ipv6, ipsec, pim, etc | keyword |
| params | The request parameters. For HTTP, these are the POST or GET parameters. For Thrift-RPC, these are the parameters from the request. | text |
| path | The path the transaction refers to. For HTTP, this is the URL. For SQL databases, this is the table name. For key-value stores, this is the key. | keyword |
| query | The query in a human readable format. For HTTP, it will typically be something like `GET /users/_search?name=test`. For MySQL, it is something like `SELECT id from users where name=test`. | keyword |
| related.ip | All of the IPs seen on your event. | ip |
| request | For text protocols, this is the request as seen on the wire (application layer only). For binary protocols this is our representation of the request. | text |
| resource | The logical resource that this transaction refers to. For HTTP, this is the URL path up to the last slash (/). For example, if the URL is `/users/1`, the resource is `/users`. For databases, the resource is typically the table name. The field is not filled for all transaction types. | keyword |
| response | For text protocols, this is the response as seen on the wire (application layer only). For binary protocols this is our representation of the request. | text |
| server.bytes | Bytes sent from the server to the client. | long |
| server.ip | IP address of the server. | ip |
| server.port | Port of the server. | long |
| server.process.args | The command-line of the process that served the transaction. | keyword |
| server.process.executable | Absolute path to the server process executable. | keyword |
| server.process.name | The name of the process that served the transaction. | keyword |
| server.process.start | The time the server process started. | date |
| server.process.working_directory | The working directory of the server process. | keyword |
| source.bytes | Bytes sent from the source to the destination. | long |
| source.ip | IP address of the source. | ip |
| source.port | Port of the source. | long |
| status | The high level status of the transaction. The way to compute this value depends on the protocol, but the result has a meaning independent of the protocol. | keyword |
| type | The type of the transaction (for example, HTTP, MySQL, Redis, or RUM) or "flow" in case of flows. | keyword |


### NFS

Fields published for NFS packets.

**Exported fields**

| Field | Description | Type |
|---|---|---|
| @timestamp | Event timestamp. | date |
| client.bytes | Bytes sent from the client to the server. | long |
| client.domain | Client domain. | keyword |
| client.ip | IP address of the client. | ip |
| client.port | Port of the client. | long |
| client.process.args | The command-line of the process that initiated the transaction. | keyword |
| client.process.executable | Absolute path to the client process executable. | keyword |
| client.process.name | The name of the process that initiated the transaction. | keyword |
| client.process.start | The time the client process started. | date |
| client.process.working_directory | The working directory of the client process. | keyword |
| cloud.account.id | The cloud account or organization id used to identify different entities in a multi-tenant environment. Examples: AWS account id, Google Cloud ORG Id, or other unique identifier. | keyword |
| cloud.availability_zone | Availability zone in which this host is running. | keyword |
| cloud.image.id | Image ID for the cloud instance. | keyword |
| cloud.instance.id | Instance ID of the host machine. | keyword |
| cloud.instance.name | Instance name of the host machine. | keyword |
| cloud.machine.type | Machine type of the host machine. | keyword |
| cloud.project.id | Name of the project in Google Cloud. | keyword |
| cloud.provider | Name of the cloud provider. Example values are aws, azure, gcp, or digitalocean. | keyword |
| cloud.region | Region in which this host is running. | keyword |
| container.id | Unique container id. | keyword |
| container.image.name | Name of the image the container was built on. | keyword |
| container.labels | Image labels. | object |
| container.name | Container name. | keyword |
| data_stream.dataset | Data stream dataset. | constant_keyword |
| data_stream.namespace | Data stream namespace. | constant_keyword |
| data_stream.type | Data stream type. | constant_keyword |
| destination.bytes | Bytes sent from the destination to the source. | long |
| destination.ip | IP address of the destination. | ip |
| destination.port | Port of the destination. | long |
| ecs.version | ECS version this event conforms to. | keyword |
| event.category | Event category. The second categorization field in the hierarchy. | keyword |
| event.dataset | Name of the dataset. | keyword |
| event.duration | Duration of the event in nanoseconds. | long |
| event.end | event.end contains the date when the event ended or when the activity was last observed. | date |
| event.kind | The kind of the event. The highest categorization field in the hierarchy. | keyword |
| event.start | event.start contains the date when the event started or when the activity was first observed. | date |
| event.type | Event type. The third categorization field in the hierarchy. | keyword |
| flow.final | Indicates if event is last event in flow. If final is false, the event reports an intermediate flow state only. | boolean |
| flow.id | Internal flow ID based on connection meta data and address. | keyword |
| flow.vlan | VLAN identifier from the 802.1q frame. In case of a multi-tagged frame this field will be an array with the outer tag's VLAN identifier listed first. | long |
| group.id | Unique identifier for the group on the system/platform. | keyword |
| host.architecture | Operating system architecture. | keyword |
| host.containerized | If the host is a container. | boolean |
| host.domain | Name of the domain of which the host is a member. For example, on Windows this could be the host's Active Directory domain or NetBIOS domain name. For Linux this could be the domain of the host's LDAP provider. | keyword |
| host.hostname | Hostname of the host. It normally contains what the `hostname` command returns on the host machine. | keyword |
| host.id | Unique host id. As hostname is not always unique, use values that are meaningful in your environment. Example: The current usage of `beat.name`. | keyword |
| host.ip | Host ip addresses. | ip |
| host.mac | Host mac addresses. | keyword |
| host.name | Name of the host. It can contain what `hostname` returns on Unix systems, the fully qualified domain name, or a name specified by the user. The sender decides which value to use. | keyword |
| host.os.build | OS build information. | keyword |
| host.os.codename | OS codename, if any. | keyword |
| host.os.family | OS family (such as redhat, debian, freebsd, windows). | keyword |
| host.os.kernel | Operating system kernel version as a raw string. | keyword |
| host.os.name | Operating system name, without the version. | keyword |
| host.os.platform | Operating system platform (such centos, ubuntu, windows). | keyword |
| host.os.version | Operating system version as a raw string. | keyword |
| host.type | Type of host. For Cloud providers this can be the machine type like `t2.medium`. If vm, this could be the container, for example, or other information meaningful in your environment. | keyword |
| method | The command/verb/method of the transaction. For HTTP, this is the method name (GET, POST, PUT, and so on), for SQL this is the verb (SELECT, UPDATE, DELETE, and so on). | keyword |
| network.bytes | Total bytes transferred in both directions. | long |
| network.community_id | A hash of source and destination IPs and ports. | keyword |
| network.direction | Direction of the network traffic. | keyword |
| network.forwarded_ip | Host IP address when the source IP address is the proxy. | ip |
| network.protocol | L7 Network protocol name. | keyword |
| network.transport | Protocol Name corresponding to the field `iana_number`. | keyword |
| network.type | In the OSI Model this would be the Network Layer. ipv4, ipv6, ipsec, pim, etc | keyword |
| nfs.minor_version | NFS protocol minor version number. | long |
| nfs.opcode | NFS operation name, or main operation name, in case of COMPOUND calls. | keyword |
| nfs.status | NFS operation reply status. | keyword |
| nfs.tag | NFS v4 COMPOUND operation tag. | keyword |
| nfs.version | NFS protocol version number. | long |
| params | The request parameters. For HTTP, these are the POST or GET parameters. For Thrift-RPC, these are the parameters from the request. | text |
| path | The path the transaction refers to. For HTTP, this is the URL. For SQL databases, this is the table name. For key-value stores, this is the key. | keyword |
| query | The query in a human readable format. For HTTP, it will typically be something like `GET /users/_search?name=test`. For MySQL, it is something like `SELECT id from users where name=test`. | keyword |
| related.ip | All of the IPs seen on your event. | ip |
| request | For text protocols, this is the request as seen on the wire (application layer only). For binary protocols this is our representation of the request. | text |
| resource | The logical resource that this transaction refers to. For HTTP, this is the URL path up to the last slash (/). For example, if the URL is `/users/1`, the resource is `/users`. For databases, the resource is typically the table name. The field is not filled for all transaction types. | keyword |
| response | For text protocols, this is the response as seen on the wire (application layer only). For binary protocols this is our representation of the request. | text |
| rpc.auth_flavor | RPC authentication flavor. | keyword |
| rpc.cred.gid | RPC caller's group id, in case of auth-unix. | long |
| rpc.cred.gids | RPC caller's secondary group ids, in case of auth-unix. | long |
| rpc.cred.machinename | The name of the caller's machine. | keyword |
| rpc.cred.stamp | Arbitrary ID which the caller machine may generate. | long |
| rpc.cred.uid | RPC caller's user id, in case of auth-unix. | long |
| rpc.status | RPC message reply status. | keyword |
| rpc.xid | RPC message transaction identifier. | keyword |
| server.bytes | Bytes sent from the server to the client. | long |
| server.ip | IP address of the server. | ip |
| server.port | Port of the server. | long |
| server.process.args | The command-line of the process that served the transaction. | keyword |
| server.process.executable | Absolute path to the server process executable. | keyword |
| server.process.name | The name of the process that served the transaction. | keyword |
| server.process.start | The time the server process started. | date |
| server.process.working_directory | The working directory of the server process. | keyword |
| source.bytes | Bytes sent from the source to the destination. | long |
| source.domain | Source domain. | keyword |
| source.ip | IP address of the source. | ip |
| source.port | Port of the source. | long |
| status | The high level status of the transaction. The way to compute this value depends on the protocol, but the result has a meaning independent of the protocol. | keyword |
| type | The type of the transaction (for example, HTTP, MySQL, Redis, or RUM) or "flow" in case of flows. | keyword |
| user.id | Unique identifier of the user. | keyword |


### PostgreSQL

Fields published for PostgreSQL packets.

**Exported fields**

| Field | Description | Type |
|---|---|---|
| @timestamp | Event timestamp. | date |
| client.bytes | Bytes sent from the client to the server. | long |
| client.ip | IP address of the client. | ip |
| client.port | Port of the client. | long |
| client.process.args | The command-line of the process that initiated the transaction. | keyword |
| client.process.executable | Absolute path to the client process executable. | keyword |
| client.process.name | The name of the process that initiated the transaction. | keyword |
| client.process.start | The time the client process started. | date |
| client.process.working_directory | The working directory of the client process. | keyword |
| cloud.account.id | The cloud account or organization id used to identify different entities in a multi-tenant environment. Examples: AWS account id, Google Cloud ORG Id, or other unique identifier. | keyword |
| cloud.availability_zone | Availability zone in which this host is running. | keyword |
| cloud.image.id | Image ID for the cloud instance. | keyword |
| cloud.instance.id | Instance ID of the host machine. | keyword |
| cloud.instance.name | Instance name of the host machine. | keyword |
| cloud.machine.type | Machine type of the host machine. | keyword |
| cloud.project.id | Name of the project in Google Cloud. | keyword |
| cloud.provider | Name of the cloud provider. Example values are aws, azure, gcp, or digitalocean. | keyword |
| cloud.region | Region in which this host is running. | keyword |
| container.id | Unique container id. | keyword |
| container.image.name | Name of the image the container was built on. | keyword |
| container.labels | Image labels. | object |
| container.name | Container name. | keyword |
| data_stream.dataset | Data stream dataset. | constant_keyword |
| data_stream.namespace | Data stream namespace. | constant_keyword |
| data_stream.type | Data stream type. | constant_keyword |
| destination.bytes | Bytes sent from the destination to the source. | long |
| destination.ip | IP address of the destination. | ip |
| destination.port | Port of the destination. | long |
| ecs.version | ECS version this event conforms to. | keyword |
| event.category | Event category. The second categorization field in the hierarchy. | keyword |
| event.dataset | Name of the dataset. | keyword |
| event.duration | Duration of the event in nanoseconds. | long |
| event.end | event.end contains the date when the event ended or when the activity was last observed. | date |
| event.kind | The kind of the event. The highest categorization field in the hierarchy. | keyword |
| event.start | event.start contains the date when the event started or when the activity was first observed. | date |
| event.type | Event type. The third categorization field in the hierarchy. | keyword |
| flow.final | Indicates if event is last event in flow. If final is false, the event reports an intermediate flow state only. | boolean |
| flow.id | Internal flow ID based on connection meta data and address. | keyword |
| flow.vlan | VLAN identifier from the 802.1q frame. In case of a multi-tagged frame this field will be an array with the outer tag's VLAN identifier listed first. | long |
| host.architecture | Operating system architecture. | keyword |
| host.containerized | If the host is a container. | boolean |
| host.domain | Name of the domain of which the host is a member. For example, on Windows this could be the host's Active Directory domain or NetBIOS domain name. For Linux this could be the domain of the host's LDAP provider. | keyword |
| host.hostname | Hostname of the host. It normally contains what the `hostname` command returns on the host machine. | keyword |
| host.id | Unique host id. As hostname is not always unique, use values that are meaningful in your environment. Example: The current usage of `beat.name`. | keyword |
| host.ip | Host ip addresses. | ip |
| host.mac | Host mac addresses. | keyword |
| host.name | Name of the host. It can contain what `hostname` returns on Unix systems, the fully qualified domain name, or a name specified by the user. The sender decides which value to use. | keyword |
| host.os.build | OS build information. | keyword |
| host.os.codename | OS codename, if any. | keyword |
| host.os.family | OS family (such as redhat, debian, freebsd, windows). | keyword |
| host.os.kernel | Operating system kernel version as a raw string. | keyword |
| host.os.name | Operating system name, without the version. | keyword |
| host.os.platform | Operating system platform (such centos, ubuntu, windows). | keyword |
| host.os.version | Operating system version as a raw string. | keyword |
| host.type | Type of host. For Cloud providers this can be the machine type like `t2.medium`. If vm, this could be the container, for example, or other information meaningful in your environment. | keyword |
| method | The command/verb/method of the transaction. For HTTP, this is the method name (GET, POST, PUT, and so on), for SQL this is the verb (SELECT, UPDATE, DELETE, and so on). | keyword |
| network.bytes | Total bytes transferred in both directions. | long |
| network.community_id | A hash of source and destination IPs and ports. | keyword |
| network.direction | Direction of the network traffic. | keyword |
| network.forwarded_ip | Host IP address when the source IP address is the proxy. | ip |
| network.protocol | L7 Network protocol name. | keyword |
| network.transport | Protocol Name corresponding to the field `iana_number`. | keyword |
| network.type | In the OSI Model this would be the Network Layer. ipv4, ipv6, ipsec, pim, etc | keyword |
| params | The request parameters. For HTTP, these are the POST or GET parameters. For Thrift-RPC, these are the parameters from the request. | text |
| path | The path the transaction refers to. For HTTP, this is the URL. For SQL databases, this is the table name. For key-value stores, this is the key. | keyword |
| pgsql.error_code | The PostgreSQL error code. | keyword |
| pgsql.error_message | The PostgreSQL error message. | keyword |
| pgsql.error_severity | The PostgreSQL error severity. | keyword |
| pgsql.num_fields | If the SELECT query if successful, this field is set to the number of fields returned. | long |
| pgsql.num_rows | If the SELECT query if successful, this field is set to the number of rows returned. | long |
| query | The query in a human readable format. For HTTP, it will typically be something like `GET /users/_search?name=test`. For MySQL, it is something like `SELECT id from users where name=test`. | keyword |
| related.ip | All of the IPs seen on your event. | ip |
| request | For text protocols, this is the request as seen on the wire (application layer only). For binary protocols this is our representation of the request. | text |
| resource | The logical resource that this transaction refers to. For HTTP, this is the URL path up to the last slash (/). For example, if the URL is `/users/1`, the resource is `/users`. For databases, the resource is typically the table name. The field is not filled for all transaction types. | keyword |
| response | For text protocols, this is the response as seen on the wire (application layer only). For binary protocols this is our representation of the request. | text |
| server.bytes | Bytes sent from the server to the client. | long |
| server.ip | IP address of the server. | ip |
| server.port | Port of the server. | long |
| server.process.args | The command-line of the process that served the transaction. | keyword |
| server.process.executable | Absolute path to the server process executable. | keyword |
| server.process.name | The name of the process that served the transaction. | keyword |
| server.process.start | The time the server process started. | date |
| server.process.working_directory | The working directory of the server process. | keyword |
| source.bytes | Bytes sent from the source to the destination. | long |
| source.ip | IP address of the source. | ip |
| source.port | Port of the source. | long |
| status | The high level status of the transaction. The way to compute this value depends on the protocol, but the result has a meaning independent of the protocol. | keyword |
| type | The type of the transaction (for example, HTTP, MySQL, Redis, or RUM) or "flow" in case of flows. | keyword |


### Redis

Fields published for Redis packets.

**Exported fields**

| Field | Description | Type |
|---|---|---|
| @timestamp | Event timestamp. | date |
| client.bytes | Bytes sent from the client to the server. | long |
| client.ip | IP address of the client. | ip |
| client.port | Port of the client. | long |
| client.process.args | The command-line of the process that initiated the transaction. | keyword |
| client.process.executable | Absolute path to the client process executable. | keyword |
| client.process.name | The name of the process that initiated the transaction. | keyword |
| client.process.start | The time the client process started. | date |
| client.process.working_directory | The working directory of the client process. | keyword |
| cloud.account.id | The cloud account or organization id used to identify different entities in a multi-tenant environment. Examples: AWS account id, Google Cloud ORG Id, or other unique identifier. | keyword |
| cloud.availability_zone | Availability zone in which this host is running. | keyword |
| cloud.image.id | Image ID for the cloud instance. | keyword |
| cloud.instance.id | Instance ID of the host machine. | keyword |
| cloud.instance.name | Instance name of the host machine. | keyword |
| cloud.machine.type | Machine type of the host machine. | keyword |
| cloud.project.id | Name of the project in Google Cloud. | keyword |
| cloud.provider | Name of the cloud provider. Example values are aws, azure, gcp, or digitalocean. | keyword |
| cloud.region | Region in which this host is running. | keyword |
| container.id | Unique container id. | keyword |
| container.image.name | Name of the image the container was built on. | keyword |
| container.labels | Image labels. | object |
| container.name | Container name. | keyword |
| data_stream.dataset | Data stream dataset. | constant_keyword |
| data_stream.namespace | Data stream namespace. | constant_keyword |
| data_stream.type | Data stream type. | constant_keyword |
| destination.bytes | Bytes sent from the destination to the source. | long |
| destination.ip | IP address of the destination. | ip |
| destination.port | Port of the destination. | long |
| ecs.version | ECS version this event conforms to. | keyword |
| event.category | Event category. The second categorization field in the hierarchy. | keyword |
| event.dataset | Name of the dataset. | keyword |
| event.duration | Duration of the event in nanoseconds. | long |
| event.end | event.end contains the date when the event ended or when the activity was last observed. | date |
| event.kind | The kind of the event. The highest categorization field in the hierarchy. | keyword |
| event.start | event.start contains the date when the event started or when the activity was first observed. | date |
| event.type | Event type. The third categorization field in the hierarchy. | keyword |
| flow.final | Indicates if event is last event in flow. If final is false, the event reports an intermediate flow state only. | boolean |
| flow.id | Internal flow ID based on connection meta data and address. | keyword |
| flow.vlan | VLAN identifier from the 802.1q frame. In case of a multi-tagged frame this field will be an array with the outer tag's VLAN identifier listed first. | long |
| host.architecture | Operating system architecture. | keyword |
| host.containerized | If the host is a container. | boolean |
| host.domain | Name of the domain of which the host is a member. For example, on Windows this could be the host's Active Directory domain or NetBIOS domain name. For Linux this could be the domain of the host's LDAP provider. | keyword |
| host.hostname | Hostname of the host. It normally contains what the `hostname` command returns on the host machine. | keyword |
| host.id | Unique host id. As hostname is not always unique, use values that are meaningful in your environment. Example: The current usage of `beat.name`. | keyword |
| host.ip | Host ip addresses. | ip |
| host.mac | Host mac addresses. | keyword |
| host.name | Name of the host. It can contain what `hostname` returns on Unix systems, the fully qualified domain name, or a name specified by the user. The sender decides which value to use. | keyword |
| host.os.build | OS build information. | keyword |
| host.os.codename | OS codename, if any. | keyword |
| host.os.family | OS family (such as redhat, debian, freebsd, windows). | keyword |
| host.os.kernel | Operating system kernel version as a raw string. | keyword |
| host.os.name | Operating system name, without the version. | keyword |
| host.os.platform | Operating system platform (such centos, ubuntu, windows). | keyword |
| host.os.version | Operating system version as a raw string. | keyword |
| host.type | Type of host. For Cloud providers this can be the machine type like `t2.medium`. If vm, this could be the container, for example, or other information meaningful in your environment. | keyword |
| method | The command/verb/method of the transaction. For HTTP, this is the method name (GET, POST, PUT, and so on), for SQL this is the verb (SELECT, UPDATE, DELETE, and so on). | keyword |
| network.bytes | Total bytes transferred in both directions. | long |
| network.community_id | A hash of source and destination IPs and ports. | keyword |
| network.direction | Direction of the network traffic. | keyword |
| network.forwarded_ip | Host IP address when the source IP address is the proxy. | ip |
| network.protocol | L7 Network protocol name. | keyword |
| network.transport | Protocol Name corresponding to the field `iana_number`. | keyword |
| network.type | In the OSI Model this would be the Network Layer. ipv4, ipv6, ipsec, pim, etc | keyword |
| params | The request parameters. For HTTP, these are the POST or GET parameters. For Thrift-RPC, these are the parameters from the request. | text |
| path | The path the transaction refers to. For HTTP, this is the URL. For SQL databases, this is the table name. For key-value stores, this is the key. | keyword |
| query | The query in a human readable format. For HTTP, it will typically be something like `GET /users/_search?name=test`. For MySQL, it is something like `SELECT id from users where name=test`. | keyword |
| redis.error | If the Redis command has resulted in an error, this field contains the error message returned by the Redis server. | keyword |
| redis.return_value | The return value of the Redis command in a human readable format. | keyword |
| related.ip | All of the IPs seen on your event. | ip |
| request | For text protocols, this is the request as seen on the wire (application layer only). For binary protocols this is our representation of the request. | text |
| resource | The logical resource that this transaction refers to. For HTTP, this is the URL path up to the last slash (/). For example, if the URL is `/users/1`, the resource is `/users`. For databases, the resource is typically the table name. The field is not filled for all transaction types. | keyword |
| response | For text protocols, this is the response as seen on the wire (application layer only). For binary protocols this is our representation of the request. | text |
| server.bytes | Bytes sent from the server to the client. | long |
| server.ip | IP address of the server. | ip |
| server.port | Port of the server. | long |
| server.process.args | The command-line of the process that served the transaction. | keyword |
| server.process.executable | Absolute path to the server process executable. | keyword |
| server.process.name | The name of the process that served the transaction. | keyword |
| server.process.start | The time the server process started. | date |
| server.process.working_directory | The working directory of the server process. | keyword |
| source.bytes | Bytes sent from the source to the destination. | long |
| source.ip | IP address of the source. | ip |
| source.port | Port of the source. | long |
| status | The high level status of the transaction. The way to compute this value depends on the protocol, but the result has a meaning independent of the protocol. | keyword |
| type | The type of the transaction (for example, HTTP, MySQL, Redis, or RUM) or "flow" in case of flows. | keyword |


### SIP

Fields published for SIP packets.

**Exported fields**

| Field | Description | Type |
|---|---|---|
| @timestamp | Event timestamp. | date |
| client.bytes | Bytes sent from the client to the server. | long |
| client.ip | IP address of the client. | ip |
| client.port | Port of the client. | long |
| client.process.args | The command-line of the process that initiated the transaction. | keyword |
| client.process.executable | Absolute path to the client process executable. | keyword |
| client.process.name | The name of the process that initiated the transaction. | keyword |
| client.process.start | The time the client process started. | date |
| client.process.working_directory | The working directory of the client process. | keyword |
| cloud.account.id | The cloud account or organization id used to identify different entities in a multi-tenant environment. Examples: AWS account id, Google Cloud ORG Id, or other unique identifier. | keyword |
| cloud.availability_zone | Availability zone in which this host is running. | keyword |
| cloud.image.id | Image ID for the cloud instance. | keyword |
| cloud.instance.id | Instance ID of the host machine. | keyword |
| cloud.instance.name | Instance name of the host machine. | keyword |
| cloud.machine.type | Machine type of the host machine. | keyword |
| cloud.project.id | Name of the project in Google Cloud. | keyword |
| cloud.provider | Name of the cloud provider. Example values are aws, azure, gcp, or digitalocean. | keyword |
| cloud.region | Region in which this host is running. | keyword |
| container.id | Unique container id. | keyword |
| container.image.name | Name of the image the container was built on. | keyword |
| container.labels | Image labels. | object |
| container.name | Container name. | keyword |
| data_stream.dataset | Data stream dataset. | constant_keyword |
| data_stream.namespace | Data stream namespace. | constant_keyword |
| data_stream.type | Data stream type. | constant_keyword |
| destination.bytes | Bytes sent from the destination to the source. | long |
| destination.ip | IP address of the destination. | ip |
| destination.port | Port of the destination. | long |
| ecs.version | ECS version this event conforms to. | keyword |
| event.category | Event category. The second categorization field in the hierarchy. | keyword |
| event.dataset | Name of the dataset. | keyword |
| event.duration | Duration of the event in nanoseconds. | long |
| event.end | event.end contains the date when the event ended or when the activity was last observed. | date |
| event.kind | The kind of the event. The highest categorization field in the hierarchy. | keyword |
| event.start | event.start contains the date when the event started or when the activity was first observed. | date |
| event.type | Event type. The third categorization field in the hierarchy. | keyword |
| flow.final | Indicates if event is last event in flow. If final is false, the event reports an intermediate flow state only. | boolean |
| flow.id | Internal flow ID based on connection meta data and address. | keyword |
| flow.vlan | VLAN identifier from the 802.1q frame. In case of a multi-tagged frame this field will be an array with the outer tag's VLAN identifier listed first. | long |
| host.architecture | Operating system architecture. | keyword |
| host.containerized | If the host is a container. | boolean |
| host.domain | Name of the domain of which the host is a member. For example, on Windows this could be the host's Active Directory domain or NetBIOS domain name. For Linux this could be the domain of the host's LDAP provider. | keyword |
| host.hostname | Hostname of the host. It normally contains what the `hostname` command returns on the host machine. | keyword |
| host.id | Unique host id. As hostname is not always unique, use values that are meaningful in your environment. Example: The current usage of `beat.name`. | keyword |
| host.ip | Host ip addresses. | ip |
| host.mac | Host mac addresses. | keyword |
| host.name | Name of the host. It can contain what `hostname` returns on Unix systems, the fully qualified domain name, or a name specified by the user. The sender decides which value to use. | keyword |
| host.os.build | OS build information. | keyword |
| host.os.codename | OS codename, if any. | keyword |
| host.os.family | OS family (such as redhat, debian, freebsd, windows). | keyword |
| host.os.kernel | Operating system kernel version as a raw string. | keyword |
| host.os.name | Operating system name, without the version. | keyword |
| host.os.platform | Operating system platform (such centos, ubuntu, windows). | keyword |
| host.os.version | Operating system version as a raw string. | keyword |
| host.type | Type of host. For Cloud providers this can be the machine type like `t2.medium`. If vm, this could be the container, for example, or other information meaningful in your environment. | keyword |
| method | The command/verb/method of the transaction. For HTTP, this is the method name (GET, POST, PUT, and so on), for SQL this is the verb (SELECT, UPDATE, DELETE, and so on). | keyword |
| network.application | Application level protocol name. | keyword |
| network.bytes | Total bytes transferred in both directions. | long |
| network.community_id | A hash of source and destination IPs and ports. | keyword |
| network.direction | Direction of the network traffic. | keyword |
| network.forwarded_ip | Host IP address when the source IP address is the proxy. | ip |
| network.iana_number | IANA Protocol Number. | keyword |
| network.protocol | L7 Network protocol name. | keyword |
| network.transport | Protocol Name corresponding to the field `iana_number`. | keyword |
| network.type | In the OSI Model this would be the Network Layer. ipv4, ipv6, ipsec, pim, etc | keyword |
| params | The request parameters. For HTTP, these are the POST or GET parameters. For Thrift-RPC, these are the parameters from the request. | text |
| path | The path the transaction refers to. For HTTP, this is the URL. For SQL databases, this is the table name. For key-value stores, this is the key. | keyword |
| query | The query in a human readable format. For HTTP, it will typically be something like `GET /users/_search?name=test`. For MySQL, it is something like `SELECT id from users where name=test`. | keyword |
| related.hosts | All the host identifiers seen on your event. | keyword |
| related.ip | All of the IPs seen on your event. | ip |
| related.user | All the user names seen on your event. | keyword |
| request | For text protocols, this is the request as seen on the wire (application layer only). For binary protocols this is our representation of the request. | text |
| resource | The logical resource that this transaction refers to. For HTTP, this is the URL path up to the last slash (/). For example, if the URL is `/users/1`, the resource is `/users`. For databases, the resource is typically the table name. The field is not filled for all transaction types. | keyword |
| response | For text protocols, this is the response as seen on the wire (application layer only). For binary protocols this is our representation of the request. | text |
| server.bytes | Bytes sent from the server to the client. | long |
| server.ip | IP address of the server. | ip |
| server.port | Port of the server. | long |
| server.process.args | The command-line of the process that served the transaction. | keyword |
| server.process.executable | Absolute path to the server process executable. | keyword |
| server.process.name | The name of the process that served the transaction. | keyword |
| server.process.start | The time the server process started. | date |
| server.process.working_directory | The working directory of the server process. | keyword |
| sip.accept | Accept header value. | keyword |
| sip.allow | Allowed methods. | keyword |
| sip.auth.realm | Auth realm | keyword |
| sip.auth.scheme | Auth scheme | keyword |
| sip.auth.uri.host | Auth URI host | keyword |
| sip.auth.uri.original | Auth original URI | keyword |
| sip.auth.uri.port | Auth URI port | long |
| sip.auth.uri.scheme | Auth URI scheme | keyword |
| sip.call_id | Call ID. | keyword |
| sip.code | Response status code. | long |
| sip.contact.display_info | Contact display info | keyword |
| sip.contact.expires | Contact expires | keyword |
| sip.contact.line | Contact line | keyword |
| sip.contact.q | Contact Q | keyword |
| sip.contact.transport | Contact transport | keyword |
| sip.contact.uri.host | Contact URI host | keyword |
| sip.contact.uri.original | Contact original URI | keyword |
| sip.contact.uri.port | Contact URI port | long |
| sip.contact.uri.scheme | Contat URI scheme | keyword |
| sip.contact.uri.username | Contact URI user name | keyword |
| sip.content_length |  | long |
| sip.content_type |  | keyword |
| sip.cseq.code | Sequence code. | long |
| sip.cseq.method | Sequence method. | keyword |
| sip.from.display_info | From display info | keyword |
| sip.from.tag | From tag | keyword |
| sip.from.uri.host | From URI host | keyword |
| sip.from.uri.original | From original URI | keyword |
| sip.from.uri.port | From URI port | long |
| sip.from.uri.scheme | From URI scheme | keyword |
| sip.from.uri.username | From URI user name | keyword |
| sip.max_forwards |  | long |
| sip.method | Request method. | keyword |
| sip.private.uri.host | Private URI host. | keyword |
| sip.private.uri.original | Private original URI. | keyword |
| sip.private.uri.port | Private URI port. | long |
| sip.private.uri.scheme | Private URI scheme. | keyword |
| sip.private.uri.username | Private URI user name. | keyword |
| sip.sdp.body.original | SDP original body | keyword |
| sip.sdp.connection.address | SDP connection address | keyword |
| sip.sdp.connection.info | SDP connection info | keyword |
| sip.sdp.owner.ip | SDP owner IP | ip |
| sip.sdp.owner.session_id | SDP owner session ID | keyword |
| sip.sdp.owner.username | SDP owner user name | keyword |
| sip.sdp.owner.version | SDP owner version | keyword |
| sip.sdp.session.name | SDP session name | keyword |
| sip.sdp.version | SDP version | keyword |
| sip.status | Response status phrase. | keyword |
| sip.supported | Supported methods. | keyword |
| sip.to.display_info | To display info | keyword |
| sip.to.tag | To tag | keyword |
| sip.to.uri.host | To URI host | keyword |
| sip.to.uri.original | To original URI | keyword |
| sip.to.uri.port | To URI port | long |
| sip.to.uri.scheme | To URI scheme | keyword |
| sip.to.uri.username | To URI user name | keyword |
| sip.type | Either request or response. | keyword |
| sip.uri.host | The URI host. | keyword |
| sip.uri.original | The original URI. | keyword |
| sip.uri.port | The URI port. | long |
| sip.uri.scheme | The URI scheme. | keyword |
| sip.uri.username | The URI user name. | keyword |
| sip.user_agent.original |  | keyword |
| sip.version | SIP protocol version. | keyword |
| sip.via.original | The original Via value. | keyword |
| source.bytes | Bytes sent from the source to the destination. | long |
| source.ip | IP address of the source. | ip |
| source.port | Port of the source. | long |
| status | The high level status of the transaction. The way to compute this value depends on the protocol, but the result has a meaning independent of the protocol. | keyword |
| type | The type of the transaction (for example, HTTP, MySQL, Redis, or RUM) or "flow" in case of flows. | keyword |
| user.name | Short name or login of the user. | keyword |


### Thrift

Fields published for Thrift packets.

**Exported fields**

| Field | Description | Type |
|---|---|---|
| @timestamp | Event timestamp. | date |
| client.bytes | Bytes sent from the client to the server. | long |
| client.ip | IP address of the client. | ip |
| client.port | Port of the client. | long |
| client.process.args | The command-line of the process that initiated the transaction. | keyword |
| client.process.executable | Absolute path to the client process executable. | keyword |
| client.process.name | The name of the process that initiated the transaction. | keyword |
| client.process.start | The time the client process started. | date |
| client.process.working_directory | The working directory of the client process. | keyword |
| cloud.account.id | The cloud account or organization id used to identify different entities in a multi-tenant environment. Examples: AWS account id, Google Cloud ORG Id, or other unique identifier. | keyword |
| cloud.availability_zone | Availability zone in which this host is running. | keyword |
| cloud.image.id | Image ID for the cloud instance. | keyword |
| cloud.instance.id | Instance ID of the host machine. | keyword |
| cloud.instance.name | Instance name of the host machine. | keyword |
| cloud.machine.type | Machine type of the host machine. | keyword |
| cloud.project.id | Name of the project in Google Cloud. | keyword |
| cloud.provider | Name of the cloud provider. Example values are aws, azure, gcp, or digitalocean. | keyword |
| cloud.region | Region in which this host is running. | keyword |
| container.id | Unique container id. | keyword |
| container.image.name | Name of the image the container was built on. | keyword |
| container.labels | Image labels. | object |
| container.name | Container name. | keyword |
| data_stream.dataset | Data stream dataset. | constant_keyword |
| data_stream.namespace | Data stream namespace. | constant_keyword |
| data_stream.type | Data stream type. | constant_keyword |
| destination.bytes | Bytes sent from the destination to the source. | long |
| destination.ip | IP address of the destination. | ip |
| destination.port | Port of the destination. | long |
| ecs.version | ECS version this event conforms to. | keyword |
| event.category | Event category. The second categorization field in the hierarchy. | keyword |
| event.dataset | Name of the dataset. | keyword |
| event.duration | Duration of the event in nanoseconds. | long |
| event.end | event.end contains the date when the event ended or when the activity was last observed. | date |
| event.kind | The kind of the event. The highest categorization field in the hierarchy. | keyword |
| event.start | event.start contains the date when the event started or when the activity was first observed. | date |
| event.type | Event type. The third categorization field in the hierarchy. | keyword |
| flow.final | Indicates if event is last event in flow. If final is false, the event reports an intermediate flow state only. | boolean |
| flow.id | Internal flow ID based on connection meta data and address. | keyword |
| flow.vlan | VLAN identifier from the 802.1q frame. In case of a multi-tagged frame this field will be an array with the outer tag's VLAN identifier listed first. | long |
| host.architecture | Operating system architecture. | keyword |
| host.containerized | If the host is a container. | boolean |
| host.domain | Name of the domain of which the host is a member. For example, on Windows this could be the host's Active Directory domain or NetBIOS domain name. For Linux this could be the domain of the host's LDAP provider. | keyword |
| host.hostname | Hostname of the host. It normally contains what the `hostname` command returns on the host machine. | keyword |
| host.id | Unique host id. As hostname is not always unique, use values that are meaningful in your environment. Example: The current usage of `beat.name`. | keyword |
| host.ip | Host ip addresses. | ip |
| host.mac | Host mac addresses. | keyword |
| host.name | Name of the host. It can contain what `hostname` returns on Unix systems, the fully qualified domain name, or a name specified by the user. The sender decides which value to use. | keyword |
| host.os.build | OS build information. | keyword |
| host.os.codename | OS codename, if any. | keyword |
| host.os.family | OS family (such as redhat, debian, freebsd, windows). | keyword |
| host.os.kernel | Operating system kernel version as a raw string. | keyword |
| host.os.name | Operating system name, without the version. | keyword |
| host.os.platform | Operating system platform (such centos, ubuntu, windows). | keyword |
| host.os.version | Operating system version as a raw string. | keyword |
| host.type | Type of host. For Cloud providers this can be the machine type like `t2.medium`. If vm, this could be the container, for example, or other information meaningful in your environment. | keyword |
| method | The command/verb/method of the transaction. For HTTP, this is the method name (GET, POST, PUT, and so on), for SQL this is the verb (SELECT, UPDATE, DELETE, and so on). | keyword |
| network.bytes | Total bytes transferred in both directions. | long |
| network.community_id | A hash of source and destination IPs and ports. | keyword |
| network.direction | Direction of the network traffic. | keyword |
| network.forwarded_ip | Host IP address when the source IP address is the proxy. | ip |
| network.protocol | L7 Network protocol name. | keyword |
| network.transport | Protocol Name corresponding to the field `iana_number`. | keyword |
| network.type | In the OSI Model this would be the Network Layer. ipv4, ipv6, ipsec, pim, etc | keyword |
| params | The request parameters. For HTTP, these are the POST or GET parameters. For Thrift-RPC, these are the parameters from the request. | text |
| path | The path the transaction refers to. For HTTP, this is the URL. For SQL databases, this is the table name. For key-value stores, this is the key. | keyword |
| query | The query in a human readable format. For HTTP, it will typically be something like `GET /users/_search?name=test`. For MySQL, it is something like `SELECT id from users where name=test`. | keyword |
| related.ip | All of the IPs seen on your event. | ip |
| request | For text protocols, this is the request as seen on the wire (application layer only). For binary protocols this is our representation of the request. | text |
| resource | The logical resource that this transaction refers to. For HTTP, this is the URL path up to the last slash (/). For example, if the URL is `/users/1`, the resource is `/users`. For databases, the resource is typically the table name. The field is not filled for all transaction types. | keyword |
| response | For text protocols, this is the response as seen on the wire (application layer only). For binary protocols this is our representation of the request. | text |
| server.bytes | Bytes sent from the server to the client. | long |
| server.ip | IP address of the server. | ip |
| server.port | Port of the server. | long |
| server.process.args | The command-line of the process that served the transaction. | keyword |
| server.process.executable | Absolute path to the server process executable. | keyword |
| server.process.name | The name of the process that served the transaction. | keyword |
| server.process.start | The time the server process started. | date |
| server.process.working_directory | The working directory of the server process. | keyword |
| source.bytes | Bytes sent from the source to the destination. | long |
| source.ip | IP address of the source. | ip |
| source.port | Port of the source. | long |
| status | The high level status of the transaction. The way to compute this value depends on the protocol, but the result has a meaning independent of the protocol. | keyword |
| thrift.exceptions | If the call resulted in exceptions, this field contains the exceptions in a human readable format. | keyword |
| thrift.params | The RPC method call parameters in a human readable format. If the IDL files are available, the parameters use names whenever possible. Otherwise, the IDs from the message are used. | keyword |
| thrift.return_value | The value returned by the Thrift-RPC call. This is encoded in a human readable format. | keyword |
| thrift.service | The name of the Thrift-RPC service as defined in the IDL files. | keyword |
| type | The type of the transaction (for example, HTTP, MySQL, Redis, or RUM) or "flow" in case of flows. | keyword |


### TLS

Fields published for TLS packets.

**Exported fields**

| Field | Description | Type |
|---|---|---|
| @timestamp | Event timestamp. | date |
| client.bytes | Bytes sent from the client to the server. | long |
| client.ip | IP address of the client. | ip |
| client.port | Port of the client. | long |
| client.process.args | The command-line of the process that initiated the transaction. | keyword |
| client.process.executable | Absolute path to the client process executable. | keyword |
| client.process.name | The name of the process that initiated the transaction. | keyword |
| client.process.start | The time the client process started. | date |
| client.process.working_directory | The working directory of the client process. | keyword |
| cloud.account.id | The cloud account or organization id used to identify different entities in a multi-tenant environment. Examples: AWS account id, Google Cloud ORG Id, or other unique identifier. | keyword |
| cloud.availability_zone | Availability zone in which this host is running. | keyword |
| cloud.image.id | Image ID for the cloud instance. | keyword |
| cloud.instance.id | Instance ID of the host machine. | keyword |
| cloud.instance.name | Instance name of the host machine. | keyword |
| cloud.machine.type | Machine type of the host machine. | keyword |
| cloud.project.id | Name of the project in Google Cloud. | keyword |
| cloud.provider | Name of the cloud provider. Example values are aws, azure, gcp, or digitalocean. | keyword |
| cloud.region | Region in which this host is running. | keyword |
| container.id | Unique container id. | keyword |
| container.image.name | Name of the image the container was built on. | keyword |
| container.labels | Image labels. | object |
| container.name | Container name. | keyword |
| data_stream.dataset | Data stream dataset. | constant_keyword |
| data_stream.namespace | Data stream namespace. | constant_keyword |
| data_stream.type | Data stream type. | constant_keyword |
| destination.bytes | Bytes sent from the destination to the source. | long |
| destination.domain | Destination domain. | keyword |
| destination.ip | IP address of the destination. | ip |
| destination.port | Port of the destination. | long |
| ecs.version | ECS version this event conforms to. | keyword |
| event.category | Event category. The second categorization field in the hierarchy. | keyword |
| event.dataset | Name of the dataset. | keyword |
| event.duration | Duration of the event in nanoseconds. | long |
| event.end | event.end contains the date when the event ended or when the activity was last observed. | date |
| event.kind | The kind of the event. The highest categorization field in the hierarchy. | keyword |
| event.start | event.start contains the date when the event started or when the activity was first observed. | date |
| event.type | Event type. The third categorization field in the hierarchy. | keyword |
| flow.final | Indicates if event is last event in flow. If final is false, the event reports an intermediate flow state only. | boolean |
| flow.id | Internal flow ID based on connection meta data and address. | keyword |
| flow.vlan | VLAN identifier from the 802.1q frame. In case of a multi-tagged frame this field will be an array with the outer tag's VLAN identifier listed first. | long |
| host.architecture | Operating system architecture. | keyword |
| host.containerized | If the host is a container. | boolean |
| host.domain | Name of the domain of which the host is a member. For example, on Windows this could be the host's Active Directory domain or NetBIOS domain name. For Linux this could be the domain of the host's LDAP provider. | keyword |
| host.hostname | Hostname of the host. It normally contains what the `hostname` command returns on the host machine. | keyword |
| host.id | Unique host id. As hostname is not always unique, use values that are meaningful in your environment. Example: The current usage of `beat.name`. | keyword |
| host.ip | Host ip addresses. | ip |
| host.mac | Host mac addresses. | keyword |
| host.name | Name of the host. It can contain what `hostname` returns on Unix systems, the fully qualified domain name, or a name specified by the user. The sender decides which value to use. | keyword |
| host.os.build | OS build information. | keyword |
| host.os.codename | OS codename, if any. | keyword |
| host.os.family | OS family (such as redhat, debian, freebsd, windows). | keyword |
| host.os.kernel | Operating system kernel version as a raw string. | keyword |
| host.os.name | Operating system name, without the version. | keyword |
| host.os.platform | Operating system platform (such centos, ubuntu, windows). | keyword |
| host.os.version | Operating system version as a raw string. | keyword |
| host.type | Type of host. For Cloud providers this can be the machine type like `t2.medium`. If vm, this could be the container, for example, or other information meaningful in your environment. | keyword |
| method | The command/verb/method of the transaction. For HTTP, this is the method name (GET, POST, PUT, and so on), for SQL this is the verb (SELECT, UPDATE, DELETE, and so on). | keyword |
| network.bytes | Total bytes transferred in both directions. | long |
| network.community_id | A hash of source and destination IPs and ports. | keyword |
| network.direction | Direction of the network traffic. | keyword |
| network.forwarded_ip | Host IP address when the source IP address is the proxy. | ip |
| network.protocol | L7 Network protocol name. | keyword |
| network.transport | Protocol Name corresponding to the field `iana_number`. | keyword |
| network.type | In the OSI Model this would be the Network Layer. ipv4, ipv6, ipsec, pim, etc | keyword |
| params | The request parameters. For HTTP, these are the POST or GET parameters. For Thrift-RPC, these are the parameters from the request. | text |
| path | The path the transaction refers to. For HTTP, this is the URL. For SQL databases, this is the table name. For key-value stores, this is the key. | keyword |
| query | The query in a human readable format. For HTTP, it will typically be something like `GET /users/_search?name=test`. For MySQL, it is something like `SELECT id from users where name=test`. | keyword |
| related.ip | All of the IPs seen on your event. | ip |
| request | For text protocols, this is the request as seen on the wire (application layer only). For binary protocols this is our representation of the request. | text |
| resource | The logical resource that this transaction refers to. For HTTP, this is the URL path up to the last slash (/). For example, if the URL is `/users/1`, the resource is `/users`. For databases, the resource is typically the table name. The field is not filled for all transaction types. | keyword |
| response | For text protocols, this is the response as seen on the wire (application layer only). For binary protocols this is our representation of the request. | text |
| server.bytes | Bytes sent from the server to the client. | long |
| server.domain | Server domain. | keyword |
| server.ip | IP address of the server. | ip |
| server.port | Port of the server. | long |
| server.process.args | The command-line of the process that served the transaction. | keyword |
| server.process.executable | Absolute path to the server process executable. | keyword |
| server.process.name | The name of the process that served the transaction. | keyword |
| server.process.start | The time the server process started. | date |
| server.process.working_directory | The working directory of the server process. | keyword |
| source.bytes | Bytes sent from the source to the destination. | long |
| source.ip | IP address of the source. | ip |
| source.port | Port of the source. | long |
| status | The high level status of the transaction. The way to compute this value depends on the protocol, but the result has a meaning independent of the protocol. | keyword |
| tls.cipher | String indicating the cipher used during the current connection. | keyword |
| tls.client.ja3 | A hash that identifies clients based on how they perform an SSL/TLS handshake. | keyword |
| tls.client.server_name | Hostname the client is trying to connect to. Also called the SNI. | keyword |
| tls.client.supported_ciphers | Array of ciphers offered by the client during the client hello. | keyword |
| tls.client.x509.issuer.province | Province or region within country. | keyword |
| tls.client.x509.subject.province | Province or region within country. | keyword |
| tls.client.x509.version | Version of x509 format. | keyword |
| tls.detailed.alert_types | An array containing the TLS alert type for every alert received. | keyword |
| tls.detailed.client_certificate.alternative_names | Subject Alternative Names for this certificate. | keyword |
| tls.detailed.client_certificate.issuer.common_name | Name or host name identified by the certificate. | keyword |
| tls.detailed.client_certificate.issuer.country | Country code. | keyword |
| tls.detailed.client_certificate.issuer.distinguished_name | Distinguished name (DN) of the certificate issuer entity. | keyword |
| tls.detailed.client_certificate.issuer.locality | Locality. | keyword |
| tls.detailed.client_certificate.issuer.organization | Organization name. | keyword |
| tls.detailed.client_certificate.issuer.organizational_unit | Unit within organization. | keyword |
| tls.detailed.client_certificate.issuer.province | Province or region within country. | keyword |
| tls.detailed.client_certificate.not_after | Date after which the certificate expires. | date |
| tls.detailed.client_certificate.not_before | Date before which the certificate is not valid. | date |
| tls.detailed.client_certificate.public_key_algorithm | The algorithm used for this certificate's public key. One of RSA, DSA or ECDSA. | keyword |
| tls.detailed.client_certificate.public_key_size | Size of the public key. | long |
| tls.detailed.client_certificate.serial_number | The certificate's serial number. | keyword |
| tls.detailed.client_certificate.signature_algorithm | The algorithm used for the certificate's signature. | keyword |
| tls.detailed.client_certificate.subject.common_name | Name or host name identified by the certificate. | keyword |
| tls.detailed.client_certificate.subject.country | Country code. | keyword |
| tls.detailed.client_certificate.subject.distinguished_name | Distinguished name (DN) of the certificate subject entity. | keyword |
| tls.detailed.client_certificate.subject.locality | Locality. | keyword |
| tls.detailed.client_certificate.subject.organization | Organization name. | keyword |
| tls.detailed.client_certificate.subject.organizational_unit | Unit within organization. | keyword |
| tls.detailed.client_certificate.subject.province | Province or region within country. | keyword |
| tls.detailed.client_certificate.version | X509 format version. | long |
| tls.detailed.client_certificate.version_number | Version of x509 format. | keyword |
| tls.detailed.client_certificate_chain | Chain of trust for the client certificate. | keyword |
| tls.detailed.client_certificate_requested | Whether the server has requested the client to authenticate itself using a client certificate. | boolean |
| tls.detailed.client_hello.extensions._unparsed_ | List of extensions that were left unparsed by Packetbeat. | keyword |
| tls.detailed.client_hello.extensions.application_layer_protocol_negotiation | List of application-layer protocols the client is willing to use. | keyword |
| tls.detailed.client_hello.extensions.ec_points_formats | List of Elliptic Curve (EC) point formats. Indicates the set of point formats that the client can parse. | keyword |
| tls.detailed.client_hello.extensions.server_name_indication | List of hostnames | keyword |
| tls.detailed.client_hello.extensions.session_ticket | Length of the session ticket, if provided, or an empty string to advertise support for tickets. | keyword |
| tls.detailed.client_hello.extensions.signature_algorithms | List of signature algorithms that may be use in digital signatures. | keyword |
| tls.detailed.client_hello.extensions.supported_groups | List of Elliptic Curve Cryptography (ECC) curve groups supported by the client. | keyword |
| tls.detailed.client_hello.extensions.supported_versions | List of TLS versions that the client is willing to use. | keyword |
| tls.detailed.client_hello.session_id | Unique number to identify the session for the corresponding connection with the client. | keyword |
| tls.detailed.client_hello.supported_compression_methods | The list of compression methods the client supports. See https://www.iana.org/assignments/comp-meth-ids/comp-meth-ids.xhtml | keyword |
| tls.detailed.client_hello.version | The version of the TLS protocol by which the client wishes to communicate during this session. | keyword |
| tls.detailed.resumption_method | If the session has been resumed, the underlying method used. One of "id" for TLS session ID or "ticket" for TLS ticket extension. | keyword |
| tls.detailed.server_certificate.alternative_names | Subject Alternative Names for this certificate. | keyword |
| tls.detailed.server_certificate.issuer.common_name | Name or host name identified by the certificate. | keyword |
| tls.detailed.server_certificate.issuer.country | Country code. | keyword |
| tls.detailed.server_certificate.issuer.distinguished_name | Distinguished name (DN) of the certificate issuer entity. | keyword |
| tls.detailed.server_certificate.issuer.locality | Locality. | keyword |
| tls.detailed.server_certificate.issuer.organization | Organization name. | keyword |
| tls.detailed.server_certificate.issuer.organizational_unit | Unit within organization. | keyword |
| tls.detailed.server_certificate.issuer.province | Province or region within country. | keyword |
| tls.detailed.server_certificate.issuer.state_or_province | Province or region within country. | keyword |
| tls.detailed.server_certificate.not_after | Date after which the certificate expires. | date |
| tls.detailed.server_certificate.not_before | Date before which the certificate is not valid. | date |
| tls.detailed.server_certificate.public_key_algorithm | The algorithm used for this certificate's public key. One of RSA, DSA or ECDSA. | keyword |
| tls.detailed.server_certificate.public_key_size | Size of the public key. | long |
| tls.detailed.server_certificate.serial_number | The certificate's serial number. | keyword |
| tls.detailed.server_certificate.signature_algorithm | The algorithm used for the certificate's signature. | keyword |
| tls.detailed.server_certificate.subject.common_name | Name or host name identified by the certificate. | keyword |
| tls.detailed.server_certificate.subject.country | Country code. | keyword |
| tls.detailed.server_certificate.subject.distinguished_name | Distinguished name (DN) of the certificate subject entity. | keyword |
| tls.detailed.server_certificate.subject.locality | Locality. | keyword |
| tls.detailed.server_certificate.subject.organization | Organization name. | keyword |
| tls.detailed.server_certificate.subject.organizational_unit | Unit within organization. | keyword |
| tls.detailed.server_certificate.subject.province | Province or region within country. | keyword |
| tls.detailed.server_certificate.subject.state_or_province | Province or region within country. | keyword |
| tls.detailed.server_certificate.version | X509 format version. | long |
| tls.detailed.server_certificate.version_number | Version of x509 format. | keyword |
| tls.detailed.server_certificate_chain | Chain of trust for the server certificate. | keyword |
| tls.detailed.server_hello.extensions._unparsed_ | List of extensions that were left unparsed by Packetbeat. | keyword |
| tls.detailed.server_hello.extensions.application_layer_protocol_negotiation | Negotiated application layer protocol | keyword |
| tls.detailed.server_hello.extensions.ec_points_formats | List of Elliptic Curve (EC) point formats. Indicates the set of point formats that the server can parse. | keyword |
| tls.detailed.server_hello.extensions.session_ticket | Used to announce that a session ticket will be provided by the server. Always an empty string. | keyword |
| tls.detailed.server_hello.extensions.supported_versions | Negotiated TLS version to be used. | keyword |
| tls.detailed.server_hello.selected_compression_method | The compression method selected by the server from the list provided in the client hello. | keyword |
| tls.detailed.server_hello.session_id | Unique number to identify the session for the corresponding connection with the client. | keyword |
| tls.detailed.server_hello.version | The version of the TLS protocol that is used for this session. It is the highest version supported by the server not exceeding the version requested in the client hello. | keyword |
| tls.detailed.version | The version of the TLS protocol used. | keyword |
| tls.established | Boolean flag indicating if the TLS negotiation was successful and transitioned to an encrypted tunnel. | boolean |
| tls.resumed | Boolean flag indicating if this TLS connection was resumed from an existing TLS negotiation. | boolean |
| tls.server.x509.issuer.province | Province or region within country. | keyword |
| tls.server.x509.subject.province | Province or region within country. | keyword |
| tls.server.x509.version | Version of x509 format. | keyword |
| tls.version | Numeric part of the version parsed from the original string. | keyword |
| tls.version_protocol | Normalized lowercase protocol name parsed from original string. | keyword |
| type | The type of the transaction (for example, HTTP, MySQL, Redis, or RUM) or "flow" in case of flows. | keyword |

