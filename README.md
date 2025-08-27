# IPv6 GlobalRouting


#### Student: [Shashwat Patni](https://gitlab.com/sHasHh)
#### Mentors: [Tommaso Pecorella](https://gitlab.com/tommypec), Manoj Kumar Rana
#### Organisation: [ns-3 Network Simulator](https://www.nsnam.org/)
#### Project Wiki: [link](https://www.nsnam.org/wiki/GSOC2025Ipv6GlobalRouting)

---

## 📖 Project Overview

The goal of this project was to extend ns-3’s native **GlobalRouting** protocol to support **IPv6** while minimizing code duplication from the existing IPv4 implementation. Global Routing is based on the quagga implementation of the OSPF Routing Protocol (RFC 2328) and uses the Djikstra Shortest path algorithm to compute paths for a single area network configuration. The problem is that GlobalRouting doesn't work for IPv6, and that's a huge limitation. The goal of the project was to fix that limitation  . Over the summer , we extended and refactored the code , to make globalRouting Also Work for IPv6 , using the same fundamental Algorithm, and tweaks to handle IPv6 vs IPv4 Differences.


Along the way we faced some obstacles:

One of the main goals was to come up with a way to minimize code duplication.
During the Project we Explored different programing alternatives to the problem, namely static polymorphism vs dynamic vs a hybrid approach. Each Design came with its own Pros and Cons . We felt that Template Meta-Programming offerred the best alternative. The tradeoff between dynamic and Static Polymorphism was runtime Performance vs Compile time Checks and complexity with the code base . We finally decided to go with the Static Route due to its various advantages. 
We actually developed both versions halfway , to better understand each in GlobalRoutings Context. This way we could understand that using Runtime Checks was not good enough for our use case.

After discussing with Mentors it was decided to use the Static Polymorphism approach to Generalize IPv4GlobalRouting to the generic GlobalRouting using template Meta-Programming. Using Compile Time Checks , we instantiated Two versions of the template , one for each of the address class.


Along the way I found and fixed some CRITICAL bugs lurking in the protocol and also added a few performance improvements.

---

## Merge Requests and Commits Summary

| No. | Name | Status | Commit |
|-----|------|--------|--------|
| [1] | [internet: test: Add Tests for GlobalRouting](https://gitlab.com/nsnam/ns-3-dev/-/merge_requests/2471)     | Merged       |  [[1]](https://gitlab.com/nsnam/ns-3-dev/-/commit/d1134f2b43fe06e66cea4ef7b79e950024be6fdd?merge_request_iid=2471) [[2]](https://gitlab.com/nsnam/ns-3-dev/-/commit/91717fd8d107934d55a25d8cf6bca81cb1e21ee6?merge_request_iid=2471) |
| [2] | [internet: (fixes #1243) GlobalRouting: Change NextHopCalculation from Network to Attached Router](https://gitlab.com/nsnam/ns-3-dev/-/merge_requests/2483)       | Merged        | [[1]](https://gitlab.com/nsnam/ns-3-dev/-/commit/ad089436accb2781da2c0b40690725adf1433106?merge_request_iid=2483) [[2]](https://gitlab.com/nsnam/ns-3-dev/-/commit/5cc5c00619774e4e3f2a7fd5ef135a86eddbf2bb?merge_request_iid=2483)        |
| [3] | [internet: Add Ptr member to SPFVertex to Improve Performance](https://gitlab.com/nsnam/ns-3-dev/-/merge_requests/2498)      | Merged       | [[1]](https://gitlab.com/nsnam/ns-3-dev/-/commit/fb3510cee2c3b302706639f4a98aa00fe7bce4e6?merge_request_iid=2498)       |
| [4] | [internet: (fixes #1242) Remove Identical Route entries and document known limitations for GlobalRouting](https://gitlab.com/nsnam/ns-3-dev/-/merge_requests/2517)      | Merged       | [[1]](https://gitlab.com/nsnam/ns-3-dev/-/commit/3ff4a45e75aacf4f8e20f976d9b888df5d300600?merge_request_iid=2517) [[2]](https://gitlab.com/nsnam/ns-3-dev/-/commit/0984797a756f7a7158d383999f29e0091d1fe1cd?merge_request_iid=2517)      |
| [5] | [internet: Add PrintRoute function For Global Routing](https://gitlab.com/nsnam/ns-3-dev/-/merge_requests/2434)                            | In Review         | [[1]](https://gitlab.com/nsnam/ns-3-dev/-/commit/7bf68fc46dbf6a59b258758d54824df9ca723e3e?merge_request_iid=2434) |
| [6] | [internet: Generalize Ipv4GlobalRouting to Generic Global Routing Classes using Templates](https://gitlab.com/nsnam/ns-3-dev/-/merge_requests/2508) | In Review | - |
| [7] | [internet: Add Ipv6 Support to Global Routing](https://gitlab.com/nsnam/ns-3-dev/-/merge_requests/2530) | In Review | - |

---

## Features Implemented
- Refactor Ipv4 Implementation of Global Routing To a generic API to allow for the further extention to IPv6
- Handle **link-local addresses** alongside global unicast addresses. Link Local Addresses are not routed by definition but are used as Next Hop entries in the Forwarding Tables for IPv6.  
- Ensure **minimal code duplication** by reusing existing IPv4 logic where possible.  
- Provide **route visualization and printing** functionality.  
- Add **unit tests** to validate correctness of IPv6 routes.
- Handle Non-onlink addresses by asserting when encountering them.
- Handle the route Forwarding Differences between IPv4 and IPv6 for the network 3 Layer

---

## Milestones

The Project was divided into three Phases and two Milestones:

Phase 1:
- Port existing Ipv4GlobalRouting to generic GlobalRouting
- Generalize ipv4-global-routing-test-suite and global-route-manager-impl-test-suite
- Create tests and verify GlobalRouting works for Ipv4 after templatization
- Design Tests for Ipv6 Specific Properties for GlobalRouting
- Introduce Type Aliases for IP classes

Phase 2:

- Extend GlobalRouting to IPv6
- Handle the Implementation differences of IPv6

Phase 3:
- Work On suggested Changes
- Add Documentation For IPv6 GlobalRouting
- Prepare edge Testcases, Check for Bugs , fix any remaining issues
- Discuss any new features to GlobalRouting

|Milestone 1| Generalize Ipv4GlobalRouting to Generic Global Routing Classes using Templates |[Source Code]()|
|Milestone 2| Add Ipv6 Support to Global Routing |[Source Code]()|


---

## My Experience



