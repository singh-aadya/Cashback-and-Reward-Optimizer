## **Operations for Each Data Structure in Cashback Optimizer 🔧**

### **1. HashMap Operations (RateService.java)**

#### **Core Operations:**
- **PUT**: `cashbackRates.put(category, platformRateMap)` – Add/update cashback rates for category  
- **GET**: `cashbackRates.get(category).get(platform)` – Retrieve specific rate (O(1))  
- **CONTAINS_KEY**: `cashbackRates.containsKey(category)` – Validate category exists  
- **KEY_SET**: `cashbackRates.keySet()` – Get all available categories  
- **VALUES**: `cashbackRates.get(category).values()` – Get all rates for category  

#### **Business Logic Operations:**
- **findBestRate(category)** – Iterate inner map to find maximum rate  
- **compareRates(category, amount)** – Calculate cashback amounts across all platforms  
- **addNewPlatform(category, platform, rate)** – Insert new platform-rate mapping  
- **updateRate(category, platform, newRate)** – Modify existing rate  
- **getAllPlatformsForCategory(category)** – Return all platform names  

---

### **2. PriorityQueue/Min-Heap Operations (ExpiryService.java)**

#### **Core Operations:**
- **OFFER/ADD**: `expiryQueue.offer(rewardExpiry)` – Insert reward with heap ordering (O(log n))  
- **PEEK**: `expiryQueue.peek()` – Get next expiring reward (O(1))  
- **POLL/REMOVE**: `expiryQueue.poll()` – Remove & return soonest expiry (O(log n))  
- **SIZE**: `expiryQueue.size()` – Count pending rewards  
- **IS_EMPTY**: `expiryQueue.isEmpty()` – Check if queue is empty  

#### **Business Logic Operations:**
- **addReward(platform, amount, expiryDate)** – Create and insert `RewardExpiry`  
- **getUpcomingExpiries(days)** – Filter rewards expiring in N days  
- **removeExpiredRewards()** – Poll past-dated rewards  
- **getTotalExpiringAmount()** – Sum amounts of all pending rewards  
- **getUrgentNotifications()** – Return rewards expiring in 24h  

---

### **3. Graph/Adjacency List Operations (OptimizationService.java)**

#### **Core Operations:**
- **PUT**: `adjacencyList.put(node, edgeList)` – Add node with connections  
- **GET**: `adjacencyList.get(node)` – Retrieve edges from node  
- **ADD_EDGE**: `edgeList.add(new Edge(target, weight, category))` – Add connection  
- **ITERATE**: Loop through `adjacencyList` entries  
- **CONTAINS_KEY**: `adjacencyList.containsKey(platform)` – Check platform  

#### **Business Logic Operations:**
- **buildGraph()** – Construct graph from rate data  
- **findOptimalPath(startPlatform, targetCategory)** – Modified Dijkstra’s algorithm  
- **calculateMaxCashback(purchaseList)** – Multi-category optimization  
- **getConnectedPlatforms(platform)** – List of reachable platforms  
- **findShortestPath(source, destination)** – BFS/DFS traversal  

---

### **4. ArrayList Operations (Category/Platform Management)**

#### **Core Operations:**
- **ADD**: `connectedPlatforms.add(platform)` – Add platform  
- **GET**: `availableCategories.get(index)` – Access by index (O(1))  
- **CONTAINS**: `connectedPlatforms.contains(platform)` – Validate connection  
- **REMOVE**: `connectedPlatforms.remove(platform)` – Disconnect  
- **SIZE**: `availableCategories.size()` – Get category count  

#### **Business Logic Operations:**
- **validateCategory(userInput)** – Check category validity  
- **getUserPlatforms()** – Return user’s connected platforms  
- **addUserPlatform(platform)** – Validate + add platform  
- **removeUserPlatform(platform)** – Remove user platform  
- **displayAvailableOptions()** – Print categories/platforms  

---

### **5. LinkedHashMap Operations (Results Display)**

#### **Core Operations:**
- **PUT**: `sortedResults.put(platform, cashbackAmount)` – Insert with order  
- **GET**: `sortedResults.get(platform)` – Get cashback amount  
- **ENTRY_SET**: `sortedResults.entrySet()` – Iterate in order  
- **KEY_SET**: `sortedResults.keySet()` – Ordered platform names  
- **VALUES**: `sortedResults.values()` – Ordered cashback values  

#### **Business Logic Operations:**
- **rankPlatformsByRate()** – Sort & insert into LinkedHashMap  
- **displayOptimizationResults()** – Iterate entries, format output  
- **calculateSavingsComparison()** – Compare best vs alternatives  
- **generateReport()** – Create formatted summary  
- **updateResults(platform, amount)** – Update result, preserve order  

---

### **Integration Operations Flow:**
```java
// Complete operation sequence
1. HashMap.containsKey() → validate category
2. HashMap.get() → retrieve all rates for category  
3. Graph.findOptimalPath() → determine best platform combination
4. PriorityQueue.peek() → check expiry urgency
5. LinkedHashMap.put() → store results in display order
6. ArrayList.contains() → verify user has recommended platform
