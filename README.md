# IPv6 GlobalRouting Final Report


#### Student: [Shashwat Patni](https://gitlab.com/sHasHh)
#### Mentors: [Tommaso Pecorella](https://gitlab.com/tommypec), Manoj Kumar Rana
#### Organisation: [ns-3 Network Simulator](https://www.nsnam.org/)

---

## 📖 Project Overview

The goal of this project was to extend ns-3’s native **GlobalRouting** protocol to support **IPv6** while minimizing code duplication from the existing IPv4 implementation. The main goal was to come up with a way to minimize code duplication. Explored different programing alternatives to the problem, namely static polymorphism vs dynamic vs a hybrid approach. We finally decided to go with the Static Route due to its various advantages. Along the way we fixed some CRITICAL bugs lurking in the protocol 

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


