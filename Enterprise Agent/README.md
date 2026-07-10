# Autonomous Enterprise Agent
**The Problem:** Customer support bots often hallucinate policies or authorize refunds outside of company guidelines. 
**The Solution:** Engineered a master System Prompt for an e-commerce bot that strictly enforces a 30-day refund boundary.
**Techniques Used:**
* System Guardrails
* Invisible Chain-of-Thought (using <scratchpad> tags)
* Tone & Persona Constraints

**Lazy Prompt:** "You are a customer support agent for our company. Answer customer questions politely and helpfully. If they have a problem with their account or order, try to fix it for them. Be empathetic. If you don't know the answer, tell them to contact human support."
**Output:**: "I'm sorry to hear that your Item A was damaged during delivery.

Based on what you've shared, your order was placed on 4 May 2026, and today is 7 July 2026. Whether a full refund can be issued depends on the company's refund and returns policy, which I don't have access to.

If your policy covers items that arrive damaged, you're likely eligible for a resolution such as a full refund, replacement, or another remedy according to the policy.

To proceed, could you please provide your order number (and, if available, photos of the damaged item and packaging)? That will help us verify the order and process the appropriate resolution.

If I can't determine eligibility based on the available information or your request requires access to your account or order records, I'd recommend contacting our human support team so they can review your case and process the refund if applicable."

**Master System Prompt Output:** "I'm sorry that your Item A was broken during delivery.

Based on the information provided, the purchase was made on 4 May 2026, and the current date is 7 July 2026, which is more than 30 days after the purchase date. Under ShiftGear Electronics' stated policy, I'm unable to issue a full refund or a replacement for orders older than 30 days.

As an alternative, I'd be happy to offer you a 10% discount coupon for your next purchase:

Coupon Code: GEAR10

If your request is about a different order that was purchased within the last 30 days, please let me know the purchase date and I'll be happy to assist."
