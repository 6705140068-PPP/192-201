# Assignment 03 — CHANGES

**Name:** Pyae Pyae Phyo  **Student ID:** 6705140068

This is the written part of your submission. Explain **what you changed and why**, then record your **prompt log**. Keep before/after snippets to a line or two.

---

## 1 · What I changed

One row per change. Name the OOP concept and say how you checked the behaviour was unchanged.

| # | Code smell in the original | What I changed it to | OOP concept applied | How I verified behaviour was unchanged |
|---|---|---|---|---|
| 1 |The products were stored in tuples, so I had to use indexes to get the product name, price and category. | I created a Product class to store the name, price and category of each product. I also added the tax calculation inside the product class.| Classes / Encapsulation | Ran `python Assignment_03.py` result PASS |
| 2 | The orders and items were stored using nested tuples and lists, which made the code harder to read. | I created Order and OrderItem classes. Each order has a customer and a list of items, and each item has a product and quantity. |Composition| I ran the program after changing the structure and checked that the output was still the same. |
| 3 | The original program used many if/elif statements to check the customer tier for discounts and points. |I created Customer, SilverCustomer, GoldCustomer and PlatinumCustomer classes. Each type of customer has its own discount rates and points multiplier. | Inheritance / Polymorphism | I checked that there were no more if tier == ... chains in the refactored calculation and ran the self-test again. It passed. |
| 4 | The original calc() function did the calculations and printing together. |I separated them into methods such as subtotal(), discount(), tax(), total() and points(). I used receipt() separately for formatting the receipt.  | Separation of concerns / Pure methods | I checked that the calculation methods return values instead of printing them. The final output still passed the self-test. |
| 5 |There were magic numbers in the code, a global variable, and there was no validation when creating objects.  |I created named constants such as TAX_RATE, BULK_DISCOUNT_RATE and POINTS_DIVISOR. I also added validation for product prices, quantities and other object data.  | Encapsulation / Clean code |I ran the whole program again and received PASS, so the behaviour was unchanged.  |

## 2 · Short reflection (4–6 sentences)

Which change improved the code the most, and why? Where did keeping the behaviour identical force you to be careful?

> _your reflection..._

I think the biggest improvement was changing the customer tier logic into different customer classes. The original code had several if/elif statements, but using subclasses made the discount and points rules easier for me to understand. Creating Product, OrderItem and Order objects also made the program clearer because I did not need to depend on tuple indexes everywhere. I had to be careful with the tax, discount and points calculations because the assignment required the output to stay exactly the same. I also had to keep the receipt formatting unchanged. After finishing the refactoring, I ran the provided self-test and got PASS.

## 3 · Prompt log (Level 2 — required)

Record **every** prompt where AI helped. If you wrote a part yourself, say so in one row. AI-shaped code with an empty log does **not** meet the Level-2 policy.

| # | My prompt to the AI | What it suggested (summary) | Accept / reject / edited | How I checked it |
|---|---|---|---|---|
| 1 | *"Refactor this tier discount if/elif into subclasses"* | *Base `Customer` + 4 subclasses* | Edited (renamed methods) | Self-test PASS; read every line |
| 2 | "Refactor these product tuples into a Product class" |Product class with name, price and category  | Accepted |Self-test PASS; checked output  |
| 3 | "Change the order items into objects using composition" |OrderItem class with product and quantity  |Edited  | Self-test PASS; checked calculations |
| 4 | "Separate the calculations from the printing" | Separate calculation methods and receipt output | Accepted |Self-test PASS; checked methods |

**Ownership statement.** *By submitting, I confirm I understand and can explain every line of code I submitted, and that this prompt log reflects my actual AI use.*

---

## 4 · Before-you-submit checklist

- [ ] `python Assignment_03.py` prints **PASS**.
- [ ] No tuples / parallel lists left — products, orders, and items are objects.
- [ ] No `if tier == ...` chains — tiers are a class family.
- [ ] Calculation methods **return** values and do not `print`; printing is separate.
- [ ] Constructors validate state; no leftover `global`; magic numbers are named.
- [ ] The change table and reflection above are filled in.
- [ ] The prompt log is complete and the ownership statement is signed.
