# 📂 Folder Structure
```
cashback-optimizer/
├── src/
│   ├── main/
│   │   ├── java/
│   │   │   └── com/
│   │   │       └── cashback/
│   │   │           └── optimizer/
│   │   │               ├── CashbackOptimizer.java           # Main CLI entry point
│   │   │               ├── models/
│   │   │               │   ├── PaymentMethod.java          # Payment method data class
│   │   │               │   ├── MerchantRate.java           # Rate mapping data class
│   │   │               │   ├── RewardExpiry.java           # Expiry data for min-heap
│   │   │               │   └── OptimizationResult.java     # Result wrapper class
│   │   │               └── services/
│   │   │                   ├── RateService.java            # HashMap DSA operations
│   │   │                   ├── ExpiryService.java          # PriorityQueue/Min-Heap DSA
│   │   │                   └── OptimizationService.java    # Graph DSA algorithms
│   │   └── resources/
│   │       └── data/
│   │           ├── cashback-rates.json                     # Sample cashback data
│   │           ├── reward-expiry.json                      # NEW: Sample expiry data
│   │           └── categories.json                         # Categories configuration
│   └── test/
│       └── java/
│           └── com/
│               └── cashback/
│                   └── optimizer/
│                       └── services/
│                           ├── RateServiceTest.java        # HashMap tests
│                           ├── ExpiryServiceTest.java      # Min-Heap/PriorityQueue tests
│                           └── OptimizationServiceTest.java # Graph algorithm tests
├── pom.xml                                                 # Maven build configuration
├── README.md                                               # Project documentation
└── .gitignore                                              # Exclude build files
                                           # Exclude build files
