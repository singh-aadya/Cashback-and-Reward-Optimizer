 📂 Folder Structure
```plaintext
cashback-optimizer/
├── src/
│ ├── main/
│ │ ├── java/com/cashback/optimizer/
│ │ │ ├── CashbackOptimizer.java # Main entry (CLI parser & service coordinator)
│ │ │ ├── models/
│ │ │ │ ├── PaymentMethod.java # POJO → platform name, type, cashback rate
│ │ │ │ ├── MerchantRate.java # POJO → category–platform–rate mapping
│ │ │ │ └── OptimizationResult.java # POJO → best method + alternatives + savings
│ │ │ └── services/
│ │ │ ├── RateService.java # HashMap lookups (O(1) rate queries)
│ │ │ ├── ExpiryService.java # Min-heap (PriorityQueue) for reward expiry
│ │ │ └── OptimizationService.java # Graph algorithms → optimal payment path
│ │ └── resources/data/
│ │ ├── cashback-rates.json # Sample category→platform→rate data
│ │ └── categories.json # Config list of categories & platforms
│ └── test/java/com/cashback/optimizer/services/
│ ├── RateServiceTest.java # Unit tests for HashMap lookup logic
│ ├── ExpiryServiceTest.java # (To-do) Tests for expiry min-heap
│ └── OptimizationServiceTest.java # (To-do) Tests for graph-based optimization


*POJO-Plain Old Java Object

# 🏗️ The DSA Cashback Optimizer: Technical Architecture Journey

## 📦 Application Container
- **Entry**: `java -jar cashback-optimizer.jar`  
- **Dependency Mgmt**: Maven `pom.xml` → Jackson (JSON), JUnit (testing), Shade (JAR packaging)  

## 💾 Runtime Memory Space
- **JVM Classloader** loads `com.cashback.optimizer` packages  
- **Services** → Singleton pattern for core logic  
- **Models** → Instantiated on heap as needed  

## 🎮 Main Thread Controller
- **`CashbackOptimizer.java`** → `main()` entry point  
- Parses CLI args → Dispatches commands to services  
- Functions as **controller** in MVC-style pattern  

## 📊 Data Transfer Objects (`models/`)
- **PaymentMethod.java** → Encapsulates platform metadata  
- **MerchantRate.java** → Maps category–platform–rate  
- **OptimizationResult.java** → Clean DTO for returning best method + alternatives  

## ⚙️ Business Logic (`services/`)
- **RateService** → `HashMap` lookups (O(1)) for category→platform→rate  
- **ExpiryService** → `PriorityQueue` (min-heap) for reward expiries  
- **OptimizationService** → Graph (adjacency list + Dijkstra/greedy) for optimal paths  

## 📂 Persistent Storage (`resources/data/`)
- **cashback-rates.json** → Deserialized into HashMap with Jackson  
- **categories.json** → Loaded into ArrayList for validation/enumeration  

## 🧪 Test Environment (`src/test/java/`)
- **RateServiceTest** → Validates O(1) lookups + performance benchmarks  
- **ExpiryServiceTest** → Tests heap property (insert/delete/ordering)  
- **OptimizationServiceTest** → Mocks graphs, validates shortest-path correctness  

## 🔄 Build & Deployment
- Maven lifecycle: `validate → compile → test → package → verify`  
- Shade plugin → Fat JAR with dependencies → **standalone execution**  

---

✅ **Fusion of Enterprise Java + Core CS DSAs** → A portfolio-grade project that proves **engineering depth + algorithmic rigor**.

