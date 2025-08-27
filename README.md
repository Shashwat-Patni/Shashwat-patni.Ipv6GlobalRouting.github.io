# GSoC 2025 – IPv6 GlobalRouting Final Report

This site hosts the **final report** for my Google Summer of Code 2025 project:  
**Extending GlobalRouting to IPv6 in ns-3**.  

It is built using a Jekyll theme and published via GitHub Pages.

---

## 📖 Project Overview

The goal of this project is to extend ns-3’s **GlobalRouting module** to support **IPv6** while minimizing code duplication from the existing IPv4 implementation. The project introduces route computation and forwarding table population for both **global unicast** and **link-local destinations** in IPv6.

Key objectives:
- Extend `Ipv4GlobalRouting` concepts to an **`Ipv6GlobalRouting`** model.  
- Handle **link-local addresses** alongside global unicast addresses.  
- Ensure **minimal code duplication** by reusing existing IPv4 logic where possible.  
- Provide **route visualization and printing** functionality.  
- Add **unit tests** to validate correctness of IPv6 routes.  

---

## 🚀 Features Implemented

- ✅ IPv6 forwarding table population for global and link-local addresses.  
- ✅ Integration with `Ipv6RoutingProtocol` interface.  
- ✅ Symmetric routing validation with test cases.  
- ✅ Route printing utilities (similar to NixRouting).  
- ✅ Code harmonization with existing IPv4GlobalRouting.  

---

## 📂 Repository Layout

- `docs/` – Contains the Jekyll-based report content.  
- `_config.yml` – Jekyll configuration file.  
- `index.md` – Landing page for the final report.  
- `assets/` – Static files (images, diagrams, etc.).  

---

## 📖 Viewing the Report

The report is published here:  
👉 [GSoC 2025 IPv6 GlobalRouting Final Report](https://<your-username>.github.io/<your-repo>/)

---

## ⚙️ How to Run Locally

To view the report locally:

```bash
# Install Jekyll if not already installed
gem install bundler jekyll

# Clone this repository
git clone https://github.com/<your-username>/<your-repo>.git
cd <your-repo>

# Serve locally
bundle exec jekyll serve
