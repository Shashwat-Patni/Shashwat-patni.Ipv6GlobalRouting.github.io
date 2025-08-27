# IPv6 GlobalRouting Final Report


#### Student: [Shashwat Patni](https://gitlab.com/sHasHh)
#### Mentors: [Tommaso Pecorella](https://gitlab.com/tommypec), Manoj Kumar Rana
#### Organisation: [ns-3 Network Simulator](https://www.nsnam.org/)

---

## 📖 Project Overview

The goal of this project was to extend ns-3’s native **GlobalRouting** protocol to support **IPv6** while minimizing code duplication from the existing IPv4 implementation. Global Routing is based on the quagga implementation of the OSPF Routing Protocol (RFC 2328) . The original Implementation was designed to work for IPv4
For Phase 1: In order to make it work for Ipv6 , we Refactored the code for the API to a generic base. 
For Phase 2: we Instantiated it for the two address types using Template MetaProgramming.
Along the way we faced some obstacles:
One of the main goals was to come up with a way to minimize code duplication.
During the Project we Explored different programing alternatives to the problem, namely static polymorphism vs dynamic vs a hybrid approach. Each Design came with its own Pros and Cons . We felt that Template Meta-Programming offerred the best alternative. The tradeoff between dynamic and Static Polymorphism was runtime Performance vs Compile time Checks and complexity with the code base . We finally decided to go with the Static Route due to its various advantages. 
We actually developed both versions halfway , to better understand each in GlobalRoutings Context. This way we could understand that Using Runtime Checks was not good enough for our use case.



Along the way we found and fixed some CRITICAL bugs lurking in the protocol . 

Key objectives:
- Refactor Ipv4 Implementation of Global Routing To a generic Global Routing Implementation to allow for the further extention to IPv6
- Handle **link-local addresses** alongside global unicast addresses.  
- Ensure **minimal code duplication** by reusing existing IPv4 logic where possible.  
- Provide **route visualization and printing** functionality.  
- Add **unit tests** to validate correctness of IPv6 routes.
- Explore Alternatives to refactoring and extending such protocols.  

---

## 🚀 Features Implemented

- A Ipv6 Implementation of Global Routing

---

## Merge Requests and Commits Summary

| No. | Name | Status | Commit |
|-----|------|--------|--------|
| [1] |      |        |        |
| [2] |      |        |        |
| [3] |      |        |        |
| [4] |      |        |        |

---

## Milestones



---


