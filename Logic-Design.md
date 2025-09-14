
## **Data Structures Used in Cashback Optimizer with Logic Design 🔧**

### **1. HashMap - Rate Lookup System**

**Structure Design:**
```java
Map<String, Map<String, Double>> cashbackRates
// Outer Map: Category → Inner Map
// Inner Map: Platform → Cashback Rate
````

**Logic Implementation:**

* **Key**: Category name (e.g., "grocery", "fuel", "dining")
* **Value**: Another HashMap containing platform→rate mappings
* **Example**: `cashbackRates.get("grocery").get("hdfc_credit")` returns `4.0`

**Why This Design:**

* **O(1) Access Time**: Direct hash-based lookup without iteration
* **Nested Structure**: Organizes rates by category for logical grouping
* **Memory Efficient**: Only stores existing combinations, not sparse matrix

**Use Cases:**

* Find best rate for specific category: `getBestRateForCategory("grocery")`
* Compare all platforms for one category: `getAllRatesForCategory("dining")`
* Validate platform availability: `isRateAvailable("fuel", "paytm")`

---

### **2. PriorityQueue (Min-Heap) - Expiry Management**

**Structure Design:**

```java
PriorityQueue<RewardExpiry> expiryQueue = new PriorityQueue<>(
    (a, b) -> a.getExpiryDate().compareTo(b.getExpiryDate())
);
```

**Logic Implementation:**

* **Elements**: `RewardExpiry` objects containing {amount, platform, expiryDate}
* **Ordering**: Earliest expiry date always at heap root (min-heap property)
* **Comparator**: Custom comparison based on LocalDate values

**Why This Design:**

* **Automatic Sorting**: Heap maintains order without explicit sorting
* **O(1) Peek**: Instantly access most urgent expiring reward
* **O(log n) Operations**: Efficient insertion and deletion

**Use Cases:**

* Get next expiring reward: `expiryQueue.peek()`
* Add new reward: `expiryQueue.offer(new RewardExpiry(...))`
* Remove expired rewards: `expiryQueue.poll()` when date passed

---

### **3. Graph (Adjacency List) - Multi-Constraint Optimization**

**Structure Design:**

```java
Map<String, List<Edge>> adjacencyList
// Key: Payment Method Node
// Value: List of connected platforms with weights (cashback rates)

class Edge {
    String targetPlatform;
    double cashbackRate;
    String category;
}
```

**Logic Implementation:**

* **Nodes**: Payment platforms (hdfc\_credit, paytm, google\_pay)
* **Edges**: Connections with weights representing cashback rates
* **Directed Graph**: Different rates for same platform across categories

**Why This Design:**

* **Multi-Path Analysis**: Compare complex routing through different platforms
* **Weight-Based Optimization**: Edges carry cashback rate information
* **Flexible Constraints**: Add spending limits, category restrictions as edge properties

**Use Cases:**

* Find optimal payment sequence for multiple purchases
* Calculate maximum cashback across category combinations
* Identify platform dependencies and restrictions

---

### **4. ArrayList - Category and Platform Management**

**Structure Design:**

```java
List<String> availableCategories = Arrays.asList(
    "grocery", "fuel", "dining", "online_shopping"
);
List<String> connectedPlatforms = new ArrayList<>();
```

**Logic Implementation:**

* **Dynamic Sizing**: Grows as user connects more platforms
* **Index-Based Access**: O(1) random access for validation
* **Ordered Collection**: Maintains insertion order for consistent display

**Why This Design:**

* **Validation Lists**: Check if category/platform exists before processing
* **Configuration Management**: Store available options loaded from JSON
* **User State Tracking**: Maintain list of user's connected accounts

**Use Cases:**

* Validate input categories: `availableCategories.contains(userInput)`
* Display connected platforms: iterate through `connectedPlatforms`
* Add new platform: `connectedPlatforms.add(newPlatform)`

---

### **5. LinkedHashMap - Ordered Results Display**

**Structure Design:**

```java
LinkedHashMap<String, Double> sortedResults = new LinkedHashMap<>();
// Maintains insertion order while providing HashMap performance
```

**Logic Implementation:**

* **Preserves Order**: Results displayed in descending cashback rate order
* **Key-Value Pairs**: Platform name → calculated cashback amount
* **Iteration Predictability**: Consistent ordering for user experience

**Why This Design:**

* **Sorted Output**: Display best options first without separate sorting
* **HashMap Performance**: O(1) access with ordering guarantee
* **Professional Display**: Consistent result presentation

**Use Cases:**

* Display optimization results in ranked order
* Maintain platform preference ordering
* Generate reports with consistent formatting

---

### **Integration Logic Flow:**

```
User Input → HashMap (validate & lookup) → Graph (optimize path) → 
PriorityQueue (check expiry) → LinkedHashMap (display results)
```

**Each data structure serves a specific algorithmic purpose while working together to create the complete optimization system! 🎯**

```

---

Do you want me to also add a **diagram (flow arrows + DSAs)** in Markdown/ASCII so the integration logic is visually clearer for a README or report?
```
