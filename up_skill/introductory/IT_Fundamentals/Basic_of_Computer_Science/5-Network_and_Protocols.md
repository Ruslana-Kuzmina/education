# Network and Protocols

## Network Concept

### Computer Network

A **computer network** is a group of devices (e.g. a laptop, a computer, a
printer, a mobile phone, a camera, etc.) to exchange data.

Devices can be combined in different ways:

- using a wireless connection (WiFi, 3G/4G, Bluetooth)

This is an example when a joint device is a WiFi router. By connecting a camera
and a phone to the router, you can download photos from the camera to your phone.
You can also chat with your friends by connecting your smartphone to 3G/4G mobile
networks or run an online meeting by using a Bluetooth headset connected to your
laptop.

- physically, using a cable

This is an example when the devices are physically connected (using a cable or
a wire). Thus, you can connect a printer to your computer to send and print data

### Computer Network Topology

Geometric representation of how computers are connected to each other is known as
**topology**. Choosing the right topology type can increase performance and reduce
risks.

The most popular ways to connect computers into a network:

- BUS

    The essence of the Bus topology >of combining networks is as follows. There
    is a common data transmission channel. Each computer connects to this channel.
    If it is necessary to send data from computer A to computer D, then the data
    is transferred to a common channel, passes through all consumers (computers
    B, C, E, F, G, H) and then goes to computer D.

- STAR

    Star topology presupposes a central point connected to computers like rays
    of a star. An example of such a topology is a modem to which a laptop, a
    tablet and a phone are connected.

- POINT-to-POINT

    Point-to-point topology is the simplest topology that connects two devices
    directly together with a common link (with a wire or wireless). An example
    of such a topology is conventional telephony.

- Tree

    Tree (or hierarchical) topology assumes that there is a central (or root)
    node at the top level in the hierarchy which is connected to one or more other
    nodes from the second level in the hierarchy with a point-to-point physical
    link. In turn, each of these nodes might also be connected to the nodes from
    the third level in the hierarchy, and so on.

- Hybrid

    As practice shows, when building a global network for companies, a combination
    of several topology types is used rather than one specific topology. This option
    is called Hybrid. For example, Bus and Star topologies can be implemented and
    interconnected by a cable.

## OSI/TCP Model

### OSI Model

The Open Systems Interconnection (OSI) model is a conceptual model used to describe
the constituent parts and the functions of a networking system.
The classic OSI model has 7 layers. Let's consider what each of the levels is
intended for:

- Application - is an interaction layer where applications can access the network
  services.
- Presentation - is responsible for the encoding process and data storage formats.
- Session - maintains connections and is responsible for controlling ports and sessions.
- Transport - is to transfer data and make sure that it is delivered safe and sound.
- Network - decides which physical path the data will take.
- Data link - is designed to isolate some frames and correct errors that could
  occur on the Physical layer.
- Physical - is needed to transmit data over a cable or a radio signal.

### TCP/IP Model

The Transmission Control Protocol/Internet Protocol (TCP/IP) model is a concise
version of the OSI model.
It consist of:

- Application             - HTTP
- Transport               - TCP
- Internet                - IP
- Network (Phisical) Link - Ethernet, Bluetooth

### Protocols

On each layer, certain protocols work.

In this way, on the Application layer we can use a browser. Here data is generated
using the HTTP protocol. If we transfer files, then FTP (File transfer protocol)
can be used. The data that we see on the page can be presented in multiple
different formats: for example, illustrations in PNG format or lists in JSON
format. To receive this data, the TCP or UDP protocol is used, which is responsible
for transportation. If we look at the layer just below, we will see the protocols
of network interactions. The IP protocol is responsible for addressing and routing
across the network. Below is the Ethernet protocol. The last Physical layer can be
directly occupied by the technology which enables you to connect to the network:
DSL, Bluetooth, OTN.

- Application  - HTTP, FTP
- Presentation - PNG, JSON
- Session      - PPTP, SOCKS
- Transport    - UDP, TCP
- Network      - IP, ICMP
- Data link    - ETHERNET
- Physical     - DSL, BLUETOOTH, OTN

## IP, DNS, URL

The **Internet Protocol** (IP) is a communications protocol for routing and
addressing packets of data across a computer network. Its task is to deliver the
packet from the source host to the destination host using only an IP address in
the packet header.

While IP can be used to access information on the Internet, people most frequently
use those domain names that could be easily memorized, like google.com. The
**Domain Name System** (DNS) is basically the phonebook of the Internet. The purpose
of DNS is to translate domain names to IP addresses. DNS resolution is a process
of converting a hostname into an IP address.
The DNS resolution process involves 4 types of servers:

- DNS Resolver

    The resolver is responsible for handling DNS resolution requests from clients.
    Usually, the IP address of this server is given by the Internet Service Providers
    to their clients, but it is also possible to use publicly available resolver
    services, among which Google’s (8.8.8.8) and Cloudflare’s (1.1.1.1) are most
    popular.

- Root NameServer

    The resolver starts its quest of translating a hostname to an IP address by
    querying one of the DNS root servers with a domain name it is trying to resolve.
    The root nameservers are known to every resolver. Based on the extension of
    the domain (.com, .org, .edu, etc), the root name server directs the resolver
    to a specific top-level domain (TLD) name server.

- Top Level Domain Server

    TLD name servers are responsible for all domain names that have a common
    omain extension. If the request was for google.com, the TLD name server would
    point the resolver to the Authoritative name server responsible for this
    domain name.

- Authoritative NameServer

    This is the final step. The Authoritative name servers contain information
    specific to the domain name it serves (for example, google.com). It returns
    the IP address to the resolver.

This chain of requests takes a lot of time. To speed up the process, DNS records
are temporarily saved (cached) at various stages of the process:

- Browser DNS caching. Modern web browsers cache DNS records for a small amount
  of time.
- Operating system caching. The DNS resolution request from an application may
  not leave your machine if your operating system has already made a request for
  that domain name and has it in its cache.
- DNS server caching. Each type of the DNS server may cache responses it received
  from other DNS servers.

A **Uniform Resource Locator** (URL), often called a web address, is a reference
to a web resource that specifies its location on a computer network and a protocol
for retrieving it.

A typical URL can be found in the address bar of a web browser. Let us have a closer
look at the parts of a URL using the following example:

- Protocol
- Hostname
- Port
- File Path
- Pairs of parameters and values
- Location

```bash
   <protocol>://<domain>:<port>/<path>?<query:name>=<query:value>&...
```

## HTTP

The **Hypertext Transfer Protocol** (HTTP) is the foundation of the World Wide
Web. It is the essential protocol to view web pages and surf the Internet. HTTP
is an application layer protocol. The most used version of HTTP is HTTP/2. A
typical process of communications over HTTP presupposes a client making a request
to a server, which then sends a response message .

The server responds with an HTTP response which also has a header.

This response has the following elements:

- **The version of the HTTP protocol**. (here, HTTP/1.1)

- **HTTP status code**. It is “200 OK” in this case. This is a standard response
  for a successful HTTP request. There are several predefined response codes divided
  into five categories: 1XX – Informational, 2XX – Successful, 3XX – Redirection,
  4XX – Client Error, 5XX – Server Error.

- **HTTP response headers**. They are there to help a client interpret the received
  information. In our example, a Content-Encoding header shows the compression method
  used by a server, a Content-Type header indicates the type of content returned
  in the response body, a Content-Length header is the length of the response body
  in bytes. There are many other headers which will not be elaborated on here.

- **Response body**. Typically, this is an HTML page returned by a server.
  The POST method also includes a request body. It contains information that is
  submitted to a web server.

## Networking Commands

There are several networking command line tools available in an OS. They exist
to see the information about network interface configuration, check if a resource
on the network is available, resolve a domain name, etc.. The most useful Windows
tools are:

|Command Name    | Description                                               |
|----------------|-----------------------------------------------------------|
|hostname        |displays the hostname of a computer                        |
|ipconfig        |displays network configuration                             |
|ping            |sends echo request messages to another computer            |
|tracert         |shows the path taken by packets to a destination computer  |
|netstat         |displays active TCP connections                            |
|nslookup        |performs a DNS query                                       |