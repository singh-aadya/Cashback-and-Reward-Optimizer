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
│   │   │               │   └── OptimizationResult.java     # Result wrapper class
│   │   │               └── services/
│   │   │                   ├── RateService.java            # HashMap DSA operations
│   │   │                   ├── ExpiryService.java          # PriorityQueue DSA operations
│   │   │                   └── OptimizationService.java    # Graph DSA algorithms
│   │   └── resources/
│   │       └── data/
│   │           ├── cashback-rates.json                     # Sample cashback data
│   │           └── categories.json                         # Categories configuration
│   └── test/
│       └── java/
│           └── com/
│               └── cashback/
│                   └── optimizer/
│                       └── services/
│                           ├── RateServiceTest.java        # HashMap tests
│                           ├── ExpiryServiceTest.java      # PriorityQueue tests
│                           └── OptimizationServiceTest.java # Graph algorithm tests
├── pom.xml                                                 # Maven build configuration
├── README.md                                               # Project documentation
└── .gitignore                                              # Exclude build files
