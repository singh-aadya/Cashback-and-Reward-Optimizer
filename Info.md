
## **All Libraries, Frameworks, Methods & Classes Used in DSA Cashback Optimizer** 📚

---

### **1. Java Core Libraries**

#### **java.util Package**
- **HashMap**: `Map<String, Map<String, Double>>` – Core data structure for rate storage  
- **PriorityQueue**: `PriorityQueue<RewardExpiry>` – Min-heap for expiry management  
- **ArrayList**: `List<String>` – Dynamic arrays for categories & platforms  
- **LinkedHashMap**: `LinkedHashMap<String, Double>` – Ordered results display  
- **Arrays**: `Arrays.asList()` – Convert arrays to lists  
- **Collections**: `Collections.sort()` – Sorting operations  
- **Set**: `Set<String>` – For keySet ops from HashMap  
- **List**: `List<Edge>` – Adjacency list for graph representation  

#### **java.time Package**
- **LocalDate**: `LocalDate.now()` – Current date for expiry comparisons  
- **LocalDateTime**: `LocalDateTime.parse()` – Parsing expiry timestamps  
- **DateTimeFormatter**: `DateTimeFormatter.ISO_LOCAL_DATE` – Date formatting  

#### **java.io Package**
- **InputStream**: `getClass().getResourceAsStream()` – Read JSON files from resources  
- **InputStreamReader** – Convert byte streams to char streams  
- **BufferedReader** – Efficient file reading  

---

### **2. Jackson Library (JSON Processing)**

#### **Core Classes**
- **ObjectMapper**: `new ObjectMapper()` – Main JSON processor  
- **JsonNode**: `JsonNode node = mapper.readTree()` – JSON tree representation  
- **TypeReference**: `new TypeReference<Map<String, Object>>() {}` – Generic type handling  

#### **Methods Used**
- `objectMapper.readValue(inputStream, TypeReference)` – Deserialize JSON → Java  
- `objectMapper.writeValueAsString(object)` – Serialize Java → JSON  
- `jsonNode.get("fieldName")` – Extract JSON fields  
- `jsonNode.asText()` – Convert to String  
- `jsonNode.asDouble()` – Convert to Double  

---

### **3. JUnit 5 Testing Framework**

#### **Core Annotations**
- **@Test** – Define test cases  
- **@BeforeEach** – Run setup before each test  
- **@AfterEach** – Run cleanup after each test  
- **@DisplayName** – Custom test names  
- **@ParameterizedTest** – Run with multiple params  

#### **Assertion Methods**
- `Assertions.assertEquals(expected, actual)`  
- `Assertions.assertTrue(condition)`  
- `Assertions.assertNotNull(object)`  
- `Assertions.assertThrows(Exception.class, () -> method())`  

---

### **4. Java Standard I/O**

#### **Console Operations**
- **System.out.println()** – Console output  
- **System.err.println()** – Error output  
- **Scanner**: `new Scanner(System.in)` – User input  

---

### **5. Custom Classes Created**

#### **Model Classes**
```java
public class PaymentMethod {
    private String platformName;
    private String type;
    private double defaultRate;
    // Getters, setters, constructors
}

public class MerchantRate {
    private String category;
    private String platform;
    private double cashbackRate;
    // Getters, setters, constructors
}

public class RewardExpiry {
    private String platform;
    private double amount;
    private LocalDate expiryDate;
    // Getters, setters, constructors, Comparable implementation
}

public class OptimizationResult {
    private String bestPlatform;
    private double maxCashback;
    private Map<String, Double> alternatives;
    // Getters, setters, constructors
}
````

#### **Service Classes**

```java
public class RateService {
    private Map<String, Map<String, Double>> cashbackRates;
    private List<String> availableCategories;
    
    public Double getBestRate(String category)
    public Map<String, Double> getAllRates(String category)
    public boolean isValidCategory(String category)
}

public class ExpiryService {
    private PriorityQueue<RewardExpiry> expiryQueue;
    
    public void addReward(RewardExpiry reward)
    public RewardExpiry getNextExpiry()
    public List<RewardExpiry> getUpcomingExpiries(int days)
}

public class OptimizationService {
    private Map<String, List<Edge>> adjacencyList;
    
    public OptimizationResult findOptimalPayment(String category, double amount)
    public void buildGraph()
    public String findBestPlatform(String category)
}
```

---

### **6. Exception Handling Classes**

#### **Built-in Exceptions**

* **IOException** – File read failures
* **JsonProcessingException** – JSON parse errors
* **IllegalArgumentException** – Invalid input
* **NullPointerException** – Null handling

#### **Custom Exception**

```java
public class OptimizationException extends Exception {
    public OptimizationException(String message)
    public OptimizationException(String message, Throwable cause)
}
```

---

### **7. Maven Dependencies (pom.xml)**

```xml
<dependency>
    <groupId>com.fasterxml.jackson.core</groupId>
    <artifactId>jackson-databind</artifactId>
    <version>2.15.2</version>
</dependency>

<dependency>
    <groupId>org.junit.jupiter</groupId>
    <artifactId>junit-jupiter</artifactId>
    <version>5.9.3</version>
    <scope>test</scope>
</dependency>
```

---

### **8. Key Methods by Data Structure**

#### **HashMap**

* `put(key, value)`, `get(key)`, `containsKey(key)`, `keySet()`, `values()`, `entrySet()`

#### **PriorityQueue**

* `offer(element)`, `poll()`, `peek()`, `size()`, `isEmpty()`, `clear()`

#### **ArrayList**

* `add(element)`, `get(index)`, `contains(object)`, `remove(object)`, `size()`

#### **LinkedHashMap**

* `put(key, value)`, `get(key)`, `entrySet()`, `keySet()`, `values()`

---

**👉 Total:** *50+ library methods* and *15+ custom classes* working together in the **DSA-based optimization system! 🎯**

```

---

Would you like me to also add a **visual dependency map (tree/diagram)** showing *Core Java → Jackson → JUnit → Custom Classes → CLI*, so reviewers instantly see how everything connects?
```
