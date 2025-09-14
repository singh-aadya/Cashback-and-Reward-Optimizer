
## **Input Data and Output Examples for DSA Cashback Optimizer** 📊

---

### **1. Input Data Sources**

#### **JSON Configuration Files**

**cashback-rates.json**
```json
{
  "grocery": {
    "hdfc_credit": 4.0,
    "paytm": 2.0,
    "google_pay": 1.5,
    "amazon_pay": 2.5
  },
  "fuel": {
    "hdfc_credit": 5.0,
    "sbi_credit": 4.0,
    "paytm": 1.0,
    "google_pay": 0.5
  },
  "dining": {
    "dineout": 15.0,
    "zomato_pro": 10.0,
    "swiggy_one": 8.0,
    "hdfc_credit": 3.0
  }
}
````

**reward-expiry.json**

```json
[
  {
    "platform": "hdfc_credit",
    "amount": 150.0,
    "expiryDate": "2025-09-20"
  },
  {
    "platform": "paytm",
    "amount": 75.0,
    "expiryDate": "2025-09-18"
  },
  {
    "platform": "dineout",
    "amount": 300.0,
    "expiryDate": "2025-09-25"
  }
]
```

#### **User CLI Commands (Input)**

```bash
# Optimization command
java -jar cashback-optimizer.jar optimize grocery 1000

# Rate lookup command  
java -jar cashback-optimizer.jar rates dining

# Expiry check command
java -jar cashback-optimizer.jar expiring

# Add reward command
java -jar cashback-optimizer.jar add-reward hdfc_credit 200 2025-10-15
```

---

### **2. Generated Output Examples**

#### **Optimization Command Output**

```
🚀 DSA Cashback Optimizer v1.0

🔍 Processing: optimize grocery ₹1000

💡 HashMap Lookup Results:
   ✓ Found 4 platforms for 'grocery' category

📊 Rate Comparison (LinkedHashMap ordered results):
   🥇 HDFC Credit Card: 4.0% = ₹40.00
   🥈 Amazon Pay: 2.5% = ₹25.00  
   🥉 Paytm: 2.0% = ₹20.00
   4️⃣ Google Pay: 1.5% = ₹15.00

⏰ PriorityQueue Expiry Check:
   ⚠️  HDFC Credit has ₹150 expiring on 2025-09-20 (6 days left)

🎯 RECOMMENDATION:
╔══════════════════════════════════════╗
║ Best Option: HDFC Credit Card        ║
║ Cashback: ₹40.00 (4.0%)              ║
║ Bonus: Use expiring ₹150 reward!     ║
║ Net Benefit: ₹190.00 total           ║
╚══════════════════════════════════════╝

💰 Savings Analysis:
   vs Amazon Pay: +₹15.00 (60% more cashback)
   vs Paytm: +₹20.00 (100% more cashback)  
   vs Google Pay: +₹25.00 (167% more cashback)

⚡ DSA Performance: Processed in 12ms using HashMap O(1) + Graph O(V+E)
```

---

#### **Rate Lookup Command Output**

```
🔍 Cashback Rates for 'dining' category:

📊 All Available Platforms (HashMap.values() operation):
╔══════════════════════════════════════╗
║ Platform          │ Rate    │ ₹1000  ║
╠══════════════════════════════════════╣
║ Dineout           │ 15.0%   │ ₹150   ║
║ Zomato Pro        │ 10.0%   │ ₹100   ║  
║ Swiggy One        │ 8.0%    │ ₹80    ║
║ HDFC Credit       │ 3.0%    │ ₹30    ║
╚══════════════════════════════════════╝

🏆 Best Option: Dineout with 15.0% cashback
📈 Graph Analysis: Direct connection, no routing needed
🎯 ArrayList Validation: All platforms verified
```

---

#### **Expiry Check Command Output**

```
⏰ Reward Expiry Status (PriorityQueue Min-Heap Results):

🚨 URGENT (Next 7 days):
╔══════════════════════════════════════╗
║ Platform    │ Amount │ Days Left     ║
╠══════════════════════════════════════╣
║ Paytm       │ ₹75    │ 4 days  🔥    ║
║ HDFC Credit │ ₹150   │ 6 days  ⚠️    ║
╚══════════════════════════════════════╝

📅 Upcoming (Next 30 days):
╔══════════════════════════════════════╗
║ Dineout    │ ₹300   │ 11 days        ║
╚══════════════════════════════════════╝

💰 Total Expiring: ₹525
🎯 Action Required: Use Paytm reward within 4 days!

⚡ PriorityQueue Operations: peek() = O(1), 3 rewards processed
```

---

#### **Add Reward Command Output**

```
➕ Adding New Reward:

📝 Input Data:
   Platform: hdfc_credit
   Amount: ₹200
   Expiry: 2025-10-15

✅ PriorityQueue Operations:
   • Validation: Platform exists in HashMap
   • Insertion: offer() operation completed in O(log n)
   • Heap Property: Maintained automatically

📊 Updated Expiry Queue:
   1️⃣ Paytm: ₹75 (4 days) - MIN_HEAP_TOP
   2️⃣ HDFC Credit: ₹150 (6 days)  
   3️⃣ Dineout: ₹300 (11 days)
   4️⃣ HDFC Credit: ₹200 (31 days) - NEW

🎯 Success: Reward added to min-heap with automatic ordering
```

---

#### **Error Handling Output**

```
❌ Error: Invalid category 'electronics'

📋 Available Categories (ArrayList data):
   ✓ grocery
   ✓ fuel  
   ✓ dining
   ✓ online_shopping

💡 Try: java -jar cashback-optimizer.jar optimize grocery 1000

🔧 ArrayList.contains() operation returned false in O(1) time
```

---

### **3. Data Structure Performance Metrics**

```
📈 DSA Performance Report:
╔══════════════════════════════════════╗
║ Operation        │ Time     │ Space  ║
╠══════════════════════════════════════╣
║ HashMap Lookup   │ O(1)     │ O(n×m) ║
║ PriorityQueue    │ O(log k) │ O(k)   ║
║ Graph Traversal  │ O(V+E)   │ O(V+E) ║
║ ArrayList Check  │ O(n)     │ O(n)   ║
║ LinkedHashMap    │ O(1)     │ O(p)   ║
╚══════════════════════════════════════╝

Where: n = categories, m = platforms, k = rewards, V = vertices, E = edges, p = results
```

---

**Real-world data processing with clear, formatted output showcasing all DSA operations in action! 🎯**

```

---

Do you want me to also create a **compact demo script** (step-by-step commands + sample outputs) so someone can copy-paste and see the optimizer working end-to-end?
```
