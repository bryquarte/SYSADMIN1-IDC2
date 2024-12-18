![image](https://github.com/user-attachments/assets/1c108de5-5620-4858-986e-958f6d27460b)


# SYSADM1 -- Capacity Management & Planning

**Part 2. Network Scalability Analysis**

Recall the e-commerce website scenario we discussed earlier. Given the
expected surge in traffic, analyze the provided network topology
diagram. Identify potential bottlenecks and areas where scalability
might be a concern. Propose specific strategies to improve the
network\'s scalability and performance to ensure a seamless user
experience during the peak traffic period. Consider factors such as
increased user demand, new applications, and security threats.


![image](https://github.com/user-attachments/assets/c7477791-5810-4199-8948-e5890f5b3c31)





Potential Bottlenecks and Scalability Concerns

Core Switch Overload:
  
  The core switch (5600) is a single point of failure and may become a bottleneck if traffic from all VLANs and the internet exceeds its capacity.
  
  Lack of redundancy in the core switch could lead to downtime if it fails.

Edge Router Bandwidth:
  
  The edge router may not have sufficient bandwidth to handle the surge in traffic from the internet during peak periods.

VLAN Segmentation:
  
  Traffic within VLANs may be manageable, but inter-VLAN communication could overload the core switch if not optimized.

  Lack of Quality of Service (QoS) policies could lead to congestion for critical traffic.

Server Scalability:
  
  Each VLAN has a limited number of servers. If demand increases, the current server capacity may not be sufficient.

Security Risks:
  
  The topology lacks visible security measures, such as firewalls or intrusion detection/prevention systems (IDS/IPS), making it vulnerable to attacks like DDoS or unauthorized access.

Proposed Scalability and Performance Improvements
1. Core Switch Redundancy

Solution: Deploy a secondary core switch in a high-availability (HA) configuration to eliminate the single point of failure.
Benefit: Ensures continuous operation even if the primary switch fails.
Drawback: Increases cost and complexity.

2. Edge Router Upgrade

Solution: Upgrade the edge router to a higher-capacity model or deploy multiple routers in a load-balanced configuration.
Benefit: Handles increased internet traffic and provides redundancy.
Drawback: Requires additional configuration and investment.

3. Server Scaling

Solution: Implement horizontal scaling by adding more servers to each VLAN. Use virtualization or containerization (e.g., Docker, Kubernetes) to maximize resource utilization.
Benefit: Dynamically adjusts server capacity based on demand.
Drawback: Requires additional hardware or cloud resources.

4. Load Balancing

Solution: Deploy load balancers for each VLAN to distribute traffic evenly across servers.
Benefit: Prevents server overload and improves response times.
Drawback: Adds complexity to the network.

5. Caching and CDN

Solution: Use caching mechanisms and integrate a Content Delivery Network (CDN) to offload static content delivery.
Benefit: Reduces load on servers and improves user experience.
Drawback: May not benefit dynamic content.

6. Inter-VLAN Routing Optimization

Solution: Implement Layer 3 switches or routers with optimized routing protocols (e.g., OSPF, BGP) for inter-VLAN communication.
Benefit: Reduces latency and improves traffic flow between VLANs.
Drawback: Requires advanced configuration.

7. Security Enhancements

Solution: Deploy firewalls, IDS/IPS, and DDoS protection at the edge router and core switch levels.
Benefit: Protects the network from external and internal threats.
Drawback: Increases cost and requires ongoing management.

8. Monitoring and Alerting

Solution: Implement network monitoring tools (e.g., Nagios, SolarWinds) to track performance and detect issues in real time.
Benefit: Proactively identifies bottlenecks and security threats.
Drawback: Requires additional resources for setup and maintenance.

![image](https://github.com/user-attachments/assets/3748b6b1-62aa-4c33-9d3e-175da98fb519)

Proposed Design Enhancements

Backup Internet:

Add a backup internet in case the other one messes up.

Redundant Core Switch:
  
  Add a secondary core switch in an HA configuration.
  Use link aggregation (e.g., LACP) to increase bandwidth between the core switch and Layer 2 switches.

Edge Router Upgrade:
  
  Deploy a second edge router with load balancing.
  Implement firewall and DDoS protection at the edge.

Server Scaling and Load Balancing:
  
  Add more servers to each VLAN and deploy load balancers to distribute traffic.
  You can implement EIGRP or CEF or use static routing for load balancing.

Caching and CDN:
  
  Integrate a CDN for static content and implement caching mechanisms for dynamic content.

Security Measures:
  
  Deploy firewalls and IDS/IPS at critical points in the network.
  Segment VLANs further to isolate sensitive data and applications.

Monitoring:
  
  Use monitoring tools to track network performance and detect anomalies.
  Evaluation and Justification

Cost:
  
  While adding redundancy and scaling servers increases costs, these investments are justified to ensure uptime and performance  during peak traffic.

Complexity:
  The proposed solutions add complexity but are necessary to handle increased demand and ensure security.

Impact:
  
  These enhancements will significantly improve scalability, performance, and security, ensuring a seamless user experience during peak traffic periods.
  By implementing these strategies, the network will be better equipped to handle increased traffic, maintain performance, and mitigate security risks.
