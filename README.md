# Project-06-acls
his project builds on Project 5 (OSPF + VLANs). The goal is to enforce **security policies** between VLANs and the branch office using **Extended Access Control Lists (ACLs)**.

# Network Design
- Head Office VLANs:
  - HR – 192.168.10.0/24
  - IT – 192.168.20.0/24
  - Finance – 192.168.30.0/24
- Branch Office LAN – 192.168.40.0/24
- Finance Server – 192.168.30.100
- WAN Link – 10.0.0.0/30

# Security Policies
| Source | Destination | Result |
|--------|------------|--------|
| HR     | IT        | Deny   |
| HR     | Finance   | Allow  |
| IT     | All       | Allow  |
| Finance| HR        | Allow  |
| Branch | Finance Server | Allow |
| Branch | HQ PCs    | Deny   |

# Technologies Used
- Extended ACLs
- VLANs
- Router-on-a-Stick
- OSPF for dynamic routing
- ICMP testing

# Verification
- Branch PC can ping Finance Server only
- HR PC cannot reach IT
- ACL hit counters confirm rules are enforced
- OSPF routes remain functional

# Key Learning Outcomes
- Implementing extended ACLs to enforce real-world security policies
- Understanding ACL order, direction, and placement
- Maintaining dynamic routing while controlling traffic
- Troubleshooting blocked traffic
