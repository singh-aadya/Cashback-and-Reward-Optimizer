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
│   │   │               │   ├── CategoryBudget.java         # Category spending data
│   │   │               │   ├── PlatformConstraint.java     # Platform limits & constraints
│   │   │               │   ├── AllocationResult.java       # DP optimization result
│   │   │               │   └── OptimizationResult.java     # Basic result wrapper
│   │   │               └── services/
│   │   │                   ├── RateService.java            # HashMap DSA operations
│   │   │                   ├── ExpiryService.java          # PriorityQueue/Min-Heap DSA
│   │   │                   ├── DynamicProgrammingService.java # DP Algorithm Core
│   │   │                   └── OptimizationService.java    # Coordinates all optimizations
│   │   └── resources/
│   │       └── data/
│   │           ├── cashback-rates.json                     # Sample cashback data
│   │           ├── platform-constraints.json               # Platform limits & rules
│   │           ├── reward-expiry.json                      # Sample expiry data
│   │           └── categories.json                         # Categories configuration
│   └── test/
│       └── java/
│           └── com/
│               └── cashback/
│                   └── optimizer/
│                       └── services/
│                           ├── RateServiceTest.java        # HashMap tests
│                           ├── ExpiryServiceTest.java      # Min-Heap/PriorityQueue tests
│                           ├── DynamicProgrammingServiceTest.java # DP Algorithm tests
│                           └── OptimizationServiceTest.java # Integration tests
├── pom.xml                                                 # Maven build configuration
├── README.md                                               # Project documentation
└── .gitignore                                              # Exclude build files
    # Exclude build files
