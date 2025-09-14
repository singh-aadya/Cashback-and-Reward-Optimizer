# 🏗️ Technical Architecture: DSA-Based Cashback Optimizer (Java)

## ✅ MVP Choice: Java CLI Application
- **Pure Local Processing** → Standalone Java app using **HashMap**, **PriorityQueue**, **Graph** from Collections framework.  
- **User Interaction** → CLI with `Scanner` (e.g., `java CashbackOptimizer optimize grocery 1000`).  
- **Data Storage** → Local JSON files (parsed via Jackson), no DB needed for MVP.  

## 🚀 Future Scaling Path
- **Phase 2** → Add Spring Boot REST API, expose proven DSA core as backend service.  
- **Phase 3** → Android app / web frontend consuming backend APIs.  

---

**Bottom Line**:  
Java CLI = **fast, safe, portable MVP** showcasing advanced DSAs.  
Future = **enterprise-ready scaling** via Spring Boot + multi-platform frontends.  
