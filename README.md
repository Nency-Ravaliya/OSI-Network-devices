# OSI-Network-devices

# Network Communication Example: Browsing the Internet from Your Laptop

## Scenario
Imagine you're at home browsing the internet from your laptop. Your laptop is connected to your home Wi-Fi, and you want to access google.com. Here's how the different network devices work across various layers of the OSI model in this simple scenario.

### Layer 1: Physical Layer
This is the "wire" layer — where physical connections like cables, Wi-Fi signals, or fiber optics work.

- **Device Example**: A network cable or a Wi-Fi connection.
- **Attributes/Parameters**: No specific address here, just physical signals (electric or radio waves).
- **Example in Our Scenario**: Your laptop connects to the router wirelessly via Wi-Fi.

### Layer 2: Data Link Layer
At this layer, MAC addresses are used for communication between devices on the same local network (LAN).

- **Device Example**: Switch or Bridge.
  - **Switch**: Connects devices within the same network (like your laptop, printer, and smart TV).
  - **Bridge**: Connects two different LAN segments within the same network.
- **Attributes/Parameters**:
  - **MAC Address**: Unique hardware address of a device's network interface (e.g., your laptop’s Wi-Fi card).
  - **Frame**: Data sent between devices at this layer.
- **Example in Our Scenario**: 
  - Your laptop sends a request to the Wi-Fi router. The request includes your laptop's MAC address as the source and the router’s MAC address as the destination.

#### Key Devices:
- **Switches** handle traffic inside the LAN using MAC addresses.
- **Bridges** connect two parts of the same network (if there are multiple segments).

### Layer 3: Network Layer
At this layer, IP addresses and routing between different networks (like from your home network to the internet) are managed. Routers operate here.

- **Device Example**: Router
  - **Router**: Routes data between different networks (like your home network and the wider internet).
- **Attributes/Parameters**:
  - **IP Address**: Logical address assigned to each device (e.g., your laptop may have IP 192.168.1.10).
  - **Subnet Mask**: Defines which part of the IP address identifies the network (e.g., 255.255.255.0).
  - **Gateway**: The IP address of the device that forwards data to other networks (usually your router’s IP).
- **Example in Our Scenario**: 
  - Your laptop has a private IP (e.g., 192.168.1.10). The router has a public IP (e.g., 203.0.113.5).
  - When you request google.com, the router forwards your request from your local network to the internet using your router's public IP.

#### Key Device:
- **Router** connects your home network (LAN) to the internet (WAN). It forwards packets using IP addresses.

### Layer 4: Transport Layer
This layer ensures reliable data delivery between devices.

- **Attributes/Parameters**:
  - **Port Number**: Identifies specific services on a device (e.g., port 80 for HTTP, port 443 for HTTPS).
  - **Protocol**: Common protocols are TCP (reliable, ordered data delivery) and UDP (faster, less reliable).
- **Example in Our Scenario**:
  - Your request to google.com uses TCP and port 80 (HTTP) or port 443 (HTTPS).

### Layer 5 - Layer 7: Application Layers
These layers deal with application-level functions such as encryption, formatting data, and user interaction.

- **Attributes/Parameters**:
  - **Application Protocols**: HTTP, HTTPS, DNS, etc.
- **Example in Our Scenario**: 
  - When you type "google.com" in the browser, the DNS protocol translates it into an IP address (e.g., 142.250.190.14), and the HTTP protocol retrieves the web page.

## Key Components and Attributes

| Component      | OSI Layer | Attributes/Parameters            | Role in Network                             |
|----------------|-----------|-----------------------------------|---------------------------------------------|
| **Router**     | Layer 3   | IP Address, Subnet, Gateway       | Connects different networks (e.g., home network to internet) |
| **Switch**     | Layer 2   | MAC Address                      | Connects devices within the same network (LAN) |
| **Bridge**     | Layer 2   | MAC Address                      | Connects two LAN segments                   |
| **Hop**        | Layer 3   | IP Address                       | Each router a packet passes through from source to destination |
| **Wi-Fi/Cable**| Layer 1   | Physical signal (radio/electric)  | Connects devices physically or wirelessly   |

## Example Workflow with All Components:

1. **Laptop → Wi-Fi (Layer 1, 2)**
   - Your laptop sends a request (via its MAC address) over Wi-Fi to your router’s MAC address.

2. **Router (Layer 3)**
   - Your router sees the IP address for google.com, forwards the request to the next hop on the internet.

3. **Internet Hops (Layer 3)**
   - The data goes through several routers (hops), each forwarding the request closer to google.com based on IP addresses.

4. **Google Server (Layer 3, 4, 7)**
   - Google’s server receives the request on port 443 (HTTPS) and sends back the webpage.

## Summary of Attributes:
- **MAC Address (Layer 2)**: Physical hardware address used for communication within a local network.
- **IP Address (Layer 3)**: Logical address used for communication between networks.
- **Subnet Mask (Layer 3)**: Defines the network portion of an IP address.
- **Port (Layer 4)**: Identifies services on a device (e.g., web server).
- **Hop (Layer 3)**: Each router or gateway a packet passes through on its way to the destination.
