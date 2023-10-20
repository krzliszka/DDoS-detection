
# DDoS attack detection and mitigation in SDN controller
## A software-defined IoT gateway model created during the implentation of the diploma thesis. Proprietary association algorithm was compared with the entropy method.

### Methodology

#### 1. Model
* implementing SDN as IoT gateway
* creating a topology for simulation 
* creating scripts to generate traffic (using Scapy)

![Alt text](/ss/1.png?raw=true "Topology")

#### 2. Simulation
* simulating the given topology with **normal** traffic,
* simulating the given topology with **attack** traffic,
* analyzing and comparing the recorded traffic

![Alt text](/ss/2.png?raw=true "Normal traffic")

![Alt text](/ss/3.png?raw=true "Attack traffic")


#### 3. Detection
* if one MAC address is associated with more than one source IP address, then header information is forged (-> 4. Mitigation)
* if one source IP address is associated with more than the threshold percentage of destination IP address of total connections, then header information is forged (-> 4. Mitigation)


#### 4. Mitigation
* block the traffic from the MAC address by installing the required flow entry
* block the traffic from the MAC address or source IP address by installing the required FLOW_ENTRY

![Alt text](/ss/4.png?raw=true )

![Alt text](/ss/5.png?raw=true )


***
### Conclusions
This project shows the general structure for securing IoT netowrks using SDN as IoT gateway with new method to detect and mitigate DDoS attack. The proposed algorithm calculates the number of destination IP addresses associated with single source IP address and number of source IP addresses with a single MAC address. Then, it compares the calculated values with the threshold values and installs required flow entries accordingly. The results from the simulations shown that the proposed methodology is effective for detecting the attack in a shorter period of time and using minimal number of packets. After detection, the attack is successfully mitigated using flow entries.
