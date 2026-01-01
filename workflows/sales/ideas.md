1. **[User Input]**

   ↓

2. **[Intent Classifier]**

   - Product Info Query  
   - Pricing Query  
   - Promotion/Marketing Query  
   - Availability/Inventory Query  
   - Multi-intent (triggers parallel branches)

   ↓

3. **[Parallel Tool Nodes - dummy APIs for now]**

   - Product Database Lookup (flavor specs, ingredients, case sizes)  
   - Pricing Engine (region-based, volume discounts)  
   - Inventory Check (distribution center stock levels)  
   - Marketing Calendar (active/upcoming promotions)

   ↓

4. **[Context Aggregation]**

   ↓

5. **[Qwen Synthesis with Sales-Optimized Prompt]**

   ↓

6. **[Response Formatting]**

   - Key facts highlighted  
   - Follow-up suggestions  
   - Related products to upsell

7. **Question Classifier**

   - Product Info → Knowledge Base retrieval (vectorized product specs, marketing materials, training docs)  
   - Pricing → HTTP Request to Oracle DB (live pricing data)  
   - Inventory → HTTP Request to Oracle DB (real-time stock levels)  
   - Promotions → Knowledge Base retrieval (current promo materials)  
   - Processes → Knowledge Base retrieval (SOPs, training materials from that UPC project)

8. Static/slow-changing data (product descriptions, allergens, processes) → Vector DB, fast retrieval, no API calls  
   Dynamic data (pricing, inventory) → Live Oracle queries, always current  
   Segmented knowledge bases mean better retrieval accuracy - sales KB doesn't pollute with HR policies, etc.