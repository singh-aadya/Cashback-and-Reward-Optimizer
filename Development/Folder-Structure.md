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
