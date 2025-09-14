 #📂 Folder Structure
cashback-optimizer/
├── src/
│   ├── main/
│   │   ├── java/
│   │   │   └── com/
│   │   │       └── cashback/
│   │   │           └── optimizer/
│   │   │               ├── CashbackOptimizer.java           # Main entry point - parses CLI commands, coordinates services
│   │   │               ├── models/
│   │   │               │   ├── PaymentMethod.java          # Data class - stores platform name, type, cashback rate
│   │   │               │   ├── MerchantRate.java           # Data class - category-platform-rate mapping structure  
│   │   │               │   └── OptimizationResult.java     # Result wrapper - best method + alternatives + savings
│   │   │               └── services/
│   │   │                   ├── RateService.java            # HashMap operations - O(1) rate lookups by category/platform
│   │   │                   ├── ExpiryService.java          # PriorityQueue - manages reward expiry dates using min-heap
│   │   │                   └── OptimizationService.java    # Graph algorithms - finds optimal payment path across constraints
│   │   └── resources/
│   │       └── data/
│   │           ├── cashback-rates.json                     # Sample data - category→platform→rate mappings for testing
│   │           └── categories.json                         # Configuration - available categories and platform lists
│   └── test/
│       └── java/
│           └── com/
│               └── cashback/
│                   └── optimizer/
│                       └── services/
│                           ├── RateServiceTest.java        # Unit tests - verify HashMap lookup correctness &
