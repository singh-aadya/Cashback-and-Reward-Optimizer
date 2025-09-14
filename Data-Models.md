# 📖 Data Models Story: The Journey of Optimizing Cashback

## ⚙️ The Setup: Core DSA Structures
- **Hash Map Model** → Priya asks *“Best cashback for groceries?”* →  
  System instantly fetches:  
  `merchant_rates["grocery"]["paytm"] = 2%`  
  `merchant_rates["grocery"]["hdfc"] = 4%`  
  ✅ Lookup in under a millisecond.  

- **Min-Heap Model** → While Priya sleeps, the system tracks expiring rewards:  
  `RewardExpiry(500, "2025-09-15", "flipkart", "reward_123")`  
  ✅ Expiring cashback bubbles to the top automatically.  

- **Graph Model** → Priya wants to spend ₹10,000 across categories →  
  Graph traces optimal path:  
  `grocery_node → hdfc_card_edge(4%) → dining_node → dineout_edge(15%)`  
  ✅ Ensures maximum cumulative rewards.  

---

## 👤 The Characters: User Information
- **User Profile** → Priya’s preferences stored securely:  
  `{user_id: "priya123", preferences: "maximize_savings", notifications: "expiry_alerts_enabled"}`  

- **Connected Accounts** → Her financial life linked in one system:  
  `{"paytm": "priya@email.com", sync_status: "active", last_updated: "2025-09-14T10:50:00Z"}`  

- **Transaction History** → Every purchase becomes learning data:  
  `{₹1000_grocery, chosen_method: "hdfc_card", earned: ₹40, saved_vs_default: ₹20}`  

- **Optimization Analytics** → Priya’s success story through metrics:  
  `{monthly_savings: ₹2,847, favorite_optimization: "grocery_category", decision_acceptance_rate: 87%}`  

---

**Bottom Line**: The **DSA trio (Hash Map, Min-Heap, Graph)** + **personalized user data models** create a **living financial advisor** that not only answers Priya’s queries but learns and evolves with her spending patterns.
