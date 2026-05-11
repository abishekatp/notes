System Design:

Reference - System Design Source FreeCodeCamp by Hayk Simonyan - https://youtu.be/C842vFY5kRo?si=Tm73l9rpJO1lqpsl

- First design a simple single server setup with DB, App Server and Cache everything in a single machine. Client is either web application or mobile application
- First step of scaling: choosing correct DB: 
    - SQL: PostgreSQL, MySQL, Oracle, SQLite, Microsoft SQL
        - All DBs use structure tables with predefined schema.
        - Because of that ensure ACID: Atomicity - either full transaction success or failure, no intermediate state, Consistency - move the server from one valid state to another valid state, Isolation - When concurrent transactions are run it makes sure DB state is consistent and correct and there are no conflicts created and finally Durability - when server crashes make sure data is safe by either copying data to disk in regular interval and using other approaches like write ahead log.

    - NoSQL: Document DB(MangoDB, Couch DB), Key-Value Storage(Redis, DynamoDB), Wide Column Store(Cassandra, HBase), Graph DB(Neo4j)
        - Document DB: uses nested JSON documents to give most flexible schema. Easy scalability for large unstructured data.
        - Key-Value Storage: is generally used for caching and quick access of some data.
        - Wide column storage: can be used for storing large amounts of unstructured data without any nested structure in a columnar tables by grouping rows with similar columns into a column family. Efficient for writing and reading specific columns without reading the whole row. Also efficiently manages storage columns with empty value for many rows can be grouped into separate column family.
        - Graph DB: can be used for storing social networking data where we need to access the all the related data quickly without complex join queries.

--- 

- Scaling:
    - Vertical Scaling: Increasing the machine capacity. There is some upper limit for this and becomes costly
    - Horizontal Scaling: Works well for large systems. But need extra care for setup and maintenance. It also gives redundancy.

---

- Load Balancing: To work with horizontal scaling we need load balancing. It will distribute the load across multiple server. It will handle fault tolerance.
    - 7 commonly used loan balancing strategies: Round Robin, Least Connections, Least Response Time(also considers active connections), IP Hash(same client to same server), Weighted Algorithms(weighted round robin or weighted least connections), Geographical Algorithms, Consistent Hashing(IP Address -> Hash value -> locates in a hash ring  -> closest  server in the hash ring)
    - To implement fault tolerance load balancers use regular health check ups on all of the servers.
    - E.g Software LB - NGINX, HAProxy(Open source). Hardware LB - F5, Citrix, 
    - Cloud options - Elastic Load Balancing for AWS, Azure Load balancing, Google Cloud Load Balancing

--- 

- SPOF: Single Point of Failure. Any component of the system that could stop the whole system if it fails.
    - E.g Data base failure or Load balancer failure in case if we don’t have redundant DB or LB.
    - Redundancy: have more than one load balancer. 
    - Health check and monitoring for load balancers itself.
    - Self healing system: when one load balancer goes off, automatically initiate another load balancer as a replacement.

---

- API Design: A contract that defines the allowed request, how to make them and what to expect as response
    - Key Advantages:
        - Encapsulation and Abstraction mechanism: exposes system functionalities without exposing implementation details.
        - Service Contract(SLA) and System Boundaries: defines clear interfaces between system components.
        - Decoupling components: All the services are loosely coupled allowing them to scale independently and language agnostically.
        - Security and Access Control: Can manager authentication, authorisation, Request Rate Limitations and Input Validation and clean up.

    - Core API Styles:
        - REST(Representational State Transfer): Resource based using HTTP, Stateless(each API request is complete and independent),  Standard methods like GET, POST, PUT, DELETE, PATCH, HEAD. Most commonly used in Web and Mobile Apps.
        - GraphQL: Query Language(clients request exactly what they need), Single Endpoint for all operations(just send different query or mutation), Query for read, Mutation for update and Subscription real time. It has minimal round trips. It is used in Complex UIs.
            - GraphQL is not just sending frontend constructed query to the backend. It has defined clear schema so it can validate the query correctness. Also in the backend we can define Query and Field resolvers to check whether user has access to those rows or fields. But at the end these resolvers are extra compute for the server. 
        - gRPC(Google Remote Procedure Call): Treats remote services as local function calls. Binary Serialisation and Deserialisations using Protocol buffer schema definition. Methods as RPCs in Proto file, Communication Types(Unary, Client streaming, Server Streaming and Bidirectional streaming). It is high performance and least used one. Useful with Micro-services.
            -  It is Action Oriented(where REST is resource oriented and GraphQL is Query Oriented).
            - We have rigid contract defined in Proto file with data structure and method signatures. Based on this it generates code for serialisation and deserialisations with strict rules and versioning.
            - Multiplexing: sending multiple requests and receiving responses over single connection. Streaming: Bidirectional open streaming where both sides can push data to the other side.
            - Use: can be used for communication between micro-services in fact it is the industry standard. It is not generally used for browsers due to its nature of strict and binary.

    - Hybrid Approach: We can have 100s of micro-services communicating to each other using gRPC protocol in a most efficient way. Then we will have translation layer which will be accessed by clients. These translation layers can handle either REST or GraphQL based on the complexity of the data. In GraphQL case translation layer will handler query validation and resolvers.
        - Performance: You see the binary serialisation and deserialisation is 6 to 10 time faster than JSON parsing. So when multiple micro services work together this improves the performance drastically.

    - The four Key Design Principles: The best API is the one that developer can user without even referring to the documentation.
        - Consistency: consistent naming and patterns for the API design.
        - Simplicity: Should be simple and intuitive and focus on the use cases
        - Security: Authentication, Authorisation, Rae limit and Input Validation
        - Performance: Caching Strategies, Pagination, Minimise payloads and reduce round trips.

--- 

- The API Design Process:
    - Consider core use cases and user stories.
    - Define the Scope and Boundaries. For example which features are more critical and impactful to be implemented first.
    - Determine performance requirements. Also consider the bottlenecks for future scaling and performance.
    - Consider Security Constraints.
    - Design Approaches: 
        - Top-Down: Start with hight level requirements and workflows
        - Bottom-up: If we already have data model and some API on top of which we need to design.
        - Contract-first: First define API input and output constraints.
    - Life cycle: Design -> Development -> Deploy & Monitor -> Maintenance -> Deprecation & Retirement

---

- API Protocols:
    - Application Layer Protocols(Layer 7):
        - All HTTP, Web socket and gRPC are Application Layer(Layer 7) protocols. In the OSI model they both depend on TCP for transporting actual bits on Layer 4. While choosing consider interaction patterns, Performance needs, client compatibility, Payload size, Security needs and developer experience.

        - HTTP/HTTPS(Request-Response): this protocol can be used for REST or GraphQL.
            - Has HTTP methods: GET, POST, PUT, DELETE, PATCH, HEAD and others.
            - Common header like Content-Type, Authorisation, Accept, Cache-Control, User-Agent and others.
            - Status Codex 2xx - Success, 3xx - Redirection, 4xx - Client error, 5xx - Server error.
            - HTTPS: Same as HTTP with TLS/SSL encryption mechanism.
        - WebSocket(Full-Duplex): It can be used for live chat, multi player games or live streaming application where you need real time and/or bidirectional data. It starts as HTTP upgrade request and the switches to the web socket on that same connection.
        - gRPC protocol is a framework built on top of HTTP/2  and used for micro services. It uses HTTP/2 for its bidirectional streaming and Binary Framing. It is based on the protocol buffers. All the encoding and decoding happens based on the schema defined in protobuf file.
        - AMQP(Advanced Message Queuing Protocol): is an asynchronous, open-standard application layer protocol designed for passing messages between different systems and organisations. It does not require all the participants to be active at the exact same time. Developed by JP Morgan for mission critical Banking systems. 
            - It will have the message broker for queuing and routing message between producer and consumer systems.
            - Producer and Consumer can asynchronously communicate over a message broker using pushing into and pulling from queues. 
            - Exchange can be one on one, fan out or topic based communication between producer and consumer.

        - WebRTC(Web Real Time Communication): used for direct peer-to-peer audio, video and data streaming between browsers and devices. Only need a server to configure initial setup. It is free, open source, open standard, wildly adapted and source encrypted by default.
        - SSE(Server Sent Events): It is a unidirectional push protocol where server sends data over HTTP connection.
        - MQTT(Message Queuing Telemetry Transport): A light weight publish-subscribe protocol ideal fr iOT devices and low bandwidth sensors.
        - SMTP/IMAP/POP3: This is the standard suit for emails. SMTP is for sending, IMAP and POP3 is for receiving it from server.
        - SSH(Secure Shell): provide secure and encrypted way to remotely login and manager servers view command line terrace.
        - WebTransport: A new standard for low latency, bidirectional communication between browsers and servers. intended to be more efficient successor of WebSockets.
        - DNS(Domain Name System): For mapping human readable domain names into numerical IP Addresses. It lives at the application layer.
        - DHCP(Dynamic Host Configuration Protocol): is a protocol that automatically assign a IP address to your device when you connect to a network.
        - VoIP(Voice over Internet Protocol): It is not a single protocol. It is a category of technologies that allows to make audio/video call over an internet. It uses SIP(Session Initiation Protocol) to find and establish a call. RTP(Real-time Transport Protocol) to actually carry the audio/video data. Used in Whatsapp Calls, Zoom, Skype.

    - Presentation Layer(Layer 6)
        - Though TLS and its predecessor SSL are considered as Layer 7 in common 4 Layer terminology, we put them here for now.
        - TLS(Transport Layer Security) and SSL(Secure Socket Layer):  are cryptographic protocols that provide security and data integrity for communication over computer network. SSL is older and depreciated. TLS is modern and currently in use. Even the term SSL certificates are used in reference to the TLS technology now days.
        - TLS 1.0 and 1.1 are depreciated on 2021. TLS 1.2 and 1.3 are the current standards as of 2026.
        - How They Work?
            - Protocol Negotiations: decides on TLS version and encryption algorithm.
            - Authentication: Client verifies SSL/TLS certificate from CA(Certificate Authority) for legitimacy.
            - Key Exchange: they use asymmetric encryption(Public/Private keys) to securely generate shared symmetric session key without any third party seeing it.
            - Secure Communication: once the handshake is done they use symmetric session key for encryption and decryption.
        - Key Exchange:
            - In first step Serve can send public key to client which client can use to send a symmetric session key with server. When we use asymmetric public key to encrypt the session key then only private key can decrypt it. Later this same symmetric session keys can be used for both encryption and decryption which is much faster.
            - Asymmetric Algorithms: 
                - RSA(Rivest-Shamis-Adleman): The classical algorithm based on factoring the large prime numbers.
                - ECC(Elliptical Curve Cryptography) is the modern successor of RSA. It uses complex math of elliptical curves. As secure as RSA with smaller keys. 256-bit ECC will be same as 3072-bit RSA. 
                - DSA and ECDSA: used for Digital Signatures. ECDSA is the elliptical curve version DSA which is used in Bitcoin and Ethereum.
                - PQC(Post Quantum Cryptography): these are new asymmetric algorithms like ML-KEM and ML-DSA are designed specifically for quantum proof.

    - Transport Layer Protocols(Layer 4):
        - QUIC(Quick UDP Internet Connection): It is a Transport Layer Network protocol developed by Google that combines the speed of UDP with the reliability of TCP.
            - It is foundation for HTTP/3. It is also used in WebTransport protocol.
            - Built on top of UDP so it lives on application space(like browsers), so it can easily be updated to newer versions. Whereas the TCP is tightly integrated with OS and hard to update frequently. 
            - It adapted techniques like Packet Recovery and Congestion Control from the TCP protocol. 
            - 0-RTT: It provides 1 round trip time for the first handshake, it establishes both connection and encryption on the single handshake. Then subsequent network calls are 0-RTT. 
            - Eliminate Head-of-Line Block: It doesn’t block all the streams if a packet is lost in a stream. This is because here packets are sent in independent streams unlike TCP where we have only single sequential stream.
        - TCP(Transmission Control Protocol): used in HTTP1.1 & 2, WebSocket, AMQP, gRPC, SSE, MQTT, SMTP/IMAP/POP3, SSH all uses TCP under the hood. 
            - It is connection based protocol. It has a 3-way handshake for client connection request, server connection acknowledgement and client connection acknowledgement from the client. 
            - It provides reliability and avoids data packet loss by retransmission of the lost packets. 
            - It uses single stream to send and receive data in ordered manner.
            - It checks for error correction in the transmitted data.
        - UDP(User Datagram Protocol): used in WebRTC, DNS, DHCP, VoIP where data packet loss is not critical enough to pause the entire transmission.
            - Here DNS and DHCP uses UDP even though accuracy is important because the message is tiny. 
            - It is connection less and doesn’t care about packet loss. Just fire the data and ignore the rest ideology is user here.

    - Network Layer Protocols(Layer 3):
        - IP(Internet Protocol) is used to assign unique numerical IP addresses to each device over the internet. It is used for addressing and routing data packets across internet. Primarily using IPv4(32 bit) and IPv6(128 bit). 
        - It is connectionless and only focus on defining format and most efficient delivery routes for the data packets(datagrams). TCP makes sure the reliable connection for transmission of the data packets.

    - Data Link(Layer 2) and Physical Layer(Layer 1): 
        - The data link layer includes Ethernet, Wifi and Bluetooth. But these standards span both physical layer and data link layer. The final level is the Physical layer. 
        - For example in case of blue tooth the data link layer takes care of scanning, advertising and maintaining device connection. The physical layer takes care of defining 2.4GHz radio band, frequency hopping and signal modulation.
        - Data link layer has two sub layer MAC(Media access control) and LLC(Logical Link Control)
            - MAC: closer to hardware and handle physical ID, how multiple devices uses same medium like air or wire without collision and handle error detection.
            - LLC: Bridge between above layer. Based on which protocol used in above layer it flow controls the data to match the receivers speed.

---

- RESTful APIs
    - Resource Modelling: Analyse the business use case -> Design Data models -> Base on data models design the resources needed -> Define url patterns to access each resource
        - URL parts: We will use nouns to define each resource and url parts to access that resource. It would be api/v1/order not api/v1/get-order
        - Filtering, Sorting and Pagination: can be implemented using the URL query parameters on the GET request. Saves bandwidth, improves performance and gives frontend more flexibility.

    - HTTP methods: GET(read), POST(create), PUT(full updated), PATCH(partial update), DELETE(delete). GET, OPTIONS and HEAD methods are considered safe and idempotent. The PATCH and POST are unsafe and not idempotent, PUT and DELETE are unsafe and idempotent.
        - Safe means it doesn’t not change servers state. Idempotent means same effect even if action is repeated multiple times. 
        - GET can be retried or prefetched without any issue, but same is not true for POST or PATCH. Other than GET all other methods are capable of changing the server states.

    - Status Codes & Error handling: 2xx, 3xx, 4xx and 5xx error codes for Success, Redirection, Client errors and Server errors respectively. For example 200 OK, 201 created, 400 Bad Request, 401 Unauthorised, 404 Not Found, 500 Internal Server error.

    - Best Practices: 
        - Support filtering, sorting and pagination.
        - Use plural nouns for all the resources.
        - Keep URLs consistent and hierarchical.
        - Follow some versioning mechanism for APIs.

---

- GraphQL APIs
    - Purpose: It was created by Facebook to avoid over-fetching or under-fetching issues with REST. Using this client can request exactly what they want without worrying about how data is stored and retrieved in the backed. It avoids making multiple API calls or defining n number of APIs for different combination of same data.

    - Schema design and Type system: it has Object types, Query, Mutation and Subscription types.
        - Object types: to define the schema like User, Post, Comment, etc.
        - Query, Mutation & Subscription: Same as Object types but defines what a client can request and receive as a response. But remember that the query can select flexible subset of defined return type as a response. Subscription type is for clients to listen to some persistent connection of the server. When a subscribed event is triggered(like adding or deleting a row in a table), the server will push the data to the client over that persistent connection.
        - With the help of query keyword you can get the data, with the help of mutation keyword you can create, updated or delete data.
        - Error: Graphql will always return 200OK, so you need to send error fields explicitly in response.
        - Best Practices: keep schemas small, avoid deeply nested queries(can implement query depth limit), use meaningful names, use input types for Mutations.

--- 

- Authentication Methods: This is first step before accessing API gateway, User sends API request to tell us who they are? If user not found in our DB then we will return 401 Unauthorised. If user found then we will grant access. There are different authentication methods.
    - Basic: user first sends request, server returns unauthorised. Then user sends base64 encoded user name and password in the Authorisation header with the prefix Basic. Server validates and gives access to the system. When you send the data through secure HTTPS connection all the headers, body and URL params will be encrypted. But remember that TLS Inspection proxies(like your corporate decryption proxies for security and monitoring purposes) can decrypt your HTTPS connection before re encrypting and sending it to the actual server. This can be done by installing trusted root certificates in your machine.

    - Digest Auth: It is also same as Basic Auth but uses MD5 hashed password instead of plain base64 encoded passwords. MD5 is the message-digest algorithm 5 which converts input of any size into a 128bit irreversible hash value(16 byte or 31 hexadecimal chars). But there is still possibility of collision so it has security issue. There are different ways to store password in DB like plain password, Reversible Encrypted password or Partial Hash(HA1).

    - API Key Auth: First we will generate a particular API key for user and store it DB. When user sends it in Auth header in API request we will cross check it and give access to the resources. These keys are just random strings generated by API provider.

    - Session Based Auth: In the first request user sends user credentials. Server creates session for that user by creating session id, it will be either stored in memory or Redis DB. For the subsequent requests this session id can be sent as a cookie for validation, the browser will automatically attach the cookies to each API request with same domain name. Since session should be stored in server it is stateful method. Easy to logout user by just deleting the session ID in the DB.

    - Token Based Auth:  Similar to session but stores the user information the access token itself instead of DB(Stateless). Also User can have refresh token which they can use to generate new access token whenever their current one expires. It is tough to logout since the user login info is self contained in the access token itself. We need to have some server state or DB table like session key to blacklist logged out users.

---

- Authentication/Authorisation Frameworks:
    - OAuth2: This is a authorisation method. Application asks user to allow access for another application like Google drive to access some user data. User redirected to authorisation page, after the user consent, the application will get a authorisation code. Using the code the app gets an access token, using which the app can access user data. This process for providing the app access to some data, not for identifying any user. So this is authorisation method rather than authentication method.

    - OIDC(Open ID connect): It adds authentication on top of OAuth2. When the app request for authorisation to access data, OAuth provider will send two tokens: one is access token for authorisation, another is user ID token for identifying the user information. After this point your application use this ID token for user identification and session creation by checking with your own database. Most applications use this method for authentication now a days. It is secure and scalable.

    - SSO: it is a user experience, not an authentication or a authorisation method. User only login once using identity provider like Google, Okta, his identity information is stored inside session storage as a global session(as a cookie). When another app request for authentication the same cookie will be used.
        - IdP(Identity Protocols) - SSO uses SAML(Security Assertion Markup Language) or OIDC identity protocol under the hood. SAML is the legacy protocol which uses SAML assertion using XML response. OIDC is modern solution for this use case.

--- 

- Authorisation Methods: This tells what kind of resources the user can access. OAuth2 and JWT help us to uses these methods in practical. 
    - RBAC(Role Based Access Control): access to resource based on user roles. Like Admin, Editor, etc.

    - ABAC(Attribute Based Access Control): Based on user/resource attribute. More complex and flexible. User department, age and other attributes. Resource type, confidentiality and others. Environment attributes like time, location, device type and others.

    - ACL(Access Control List): Each resource has its own permission list. For example each sheet in Google Docs. Each resource has read, write, share and other permissions.

    - Implementation: OAuth2 access/refresh tokens can be generated with specific roles or permissions. Also in Token based authentication, JWT/Bearer tokens can contain user role, scope informations.

---

- Security: The system without security is of no use, regardless of all the other things. It is a painting without a wall. It is the at-most priority of the system. There are some proven techniques to improve the system security.
    - Rate Limiting: We can limit the request rate for per API or per User/IP or overall system level. This will avoid the DDoS attack.

    - CORS(Cross Origin Resource Sharing): Without proper CORS rules, malicious users can make users send request to your website on their behalf.

    - SQL & NoSQL Injection: It is very common one. Always use parameterised queries. Be careful and use validations while constructing queries from user inputs.

    - Firewalls: It acts as a gatekeeper. Filtering the malicious requests from normal requests. 

    - VPN(Virtual Private Networks): Some APIs are private should only allowed access from specific network like corporate internal wifi network. Users can use VPN to access system from outside.

    - CSRF(Cross-Site Request Forgery): Can use explicit CSRF tokens to stop malicious users making write API calls from users browsers using session cookies.

    - XSS(Cross-Site Scripting): Try to never accept scripts form user inputs like comments. When other user fetches this comments, these scripts might be executed on their browser and send information to the malicious users.