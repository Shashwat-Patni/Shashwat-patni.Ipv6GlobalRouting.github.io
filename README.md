# IPv6 GlobalRouting Final Report


#### Student: [Shashwat Patni](https://gitlab.com/sHasHh)
#### Mentors: [Tommaso Pecorella](https://gitlab.com/tommypec), Manoj Kumar Rana
#### Organisation: [ns-3 Network Simulator](https://www.nsnam.org/)

---

## 📖 Project Overview

The goal of this project was to extend ns-3’s native **GlobalRouting** protocol to support **IPv6** while minimizing code duplication from the existing IPv4 implementation. Global Routing is based on the quagga implementation of the OSPF Routing Protocol (RFC 2328) . The original Implementation was designed to work for IPv4


Along the way we faced some obstacles:

One of the main goals was to come up with a way to minimize code duplication.
During the Project we Explored different programing alternatives to the problem, namely static polymorphism vs dynamic vs a hybrid approach. Each Design came with its own Pros and Cons . We felt that Template Meta-Programming offerred the best alternative. The tradeoff between dynamic and Static Polymorphism was runtime 
Performance vs Compile time Checks and complexity with the code base . We finally decided to go with the Static Route due to its various advantages. 

We actually developed both versions halfway , to better understand each in GlobalRoutings Context. This way we could understand that using Runtime Checks was not good enough for our use case.



Along the way we found and fixed some CRITICAL bugs lurking in the protocol . 

## Features Implemented
- Refactor Ipv4 Implementation of Global Routing To a generic API to allow for the further extention to IPv6
- Handle **link-local addresses** alongside global unicast addresses. Link Local Addresses are not routed by definition but are used as Next Hop entries in the Forwarding Tables for IPv6.  
- Ensure **minimal code duplication** by reusing existing IPv4 logic where possible.  
- Provide **route visualization and printing** functionality.  
- Add **unit tests** to validate correctness of IPv6 routes.
- Handle Non-onlink addresses by asserting when encountering them.
- Handle the route Forwarding Differences between IPv4 and IPv6 for the network 3 Layer 

## Merge Requests and Commits Summary

| No. | Name | Status | Commit |
|-----|------|--------|--------|
| [1] | internet: test: Add Tests for GlobalRouting     | Merged       |  [[1]](https://gitlab.com/nsnam/ns-3-dev/-/commit/d1134f2b43fe06e66cea4ef7b79e950024be6fdd?merge_request_iid=2471) [[2]](https://gitlab.com/nsnam/ns-3-dev/-/commit/91717fd8d107934d55a25d8cf6bca81cb1e21ee6?merge_request_iid=2471) |
| [2] | internet: (fixes #1243) GlobalRouting: Change NextHopCalculation from Network to Attached Router       | Merged        | [[1]](https://gitlab.com/nsnam/ns-3-dev/-/commit/ad089436accb2781da2c0b40690725adf1433106?merge_request_iid=2483) [[2]](https://gitlab.com/nsnam/ns-3-dev/-/commit/5cc5c00619774e4e3f2a7fd5ef135a86eddbf2bb?merge_request_iid=2483)        |
| [3] |      |        |        |
| [4] |      |        |        |

---

## Milestones

For Phase 1: In order to make GlobalRouting work for Ipv6 , we Refactored the code for the API to a generic Templated base. Fixed Bugs  along the way, developed a Linux Like TraceRoute Functionality for GlobalRouting.

For Phase 2: we Instantiated it for the two address types using Template MetaProgramming. Added Extensive Tests and Documentation.

The following are the deliverables and the source code for each Milestone:

---


