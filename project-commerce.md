# CLAUDE.md (E-Commerce Project)

Real-world example for e-commerce/store projects.

---

## Project Context

**Name**: Store/Product Business  
**Key assets**: Product catalog, customer data, payment processing  
**Stakeholders**: Customers, ops team, finance, marketing  
**Revenue**: Direct product sales  

---

## Execution Rules

### Reversible (Autonomous)
- Product edits, inventory adjustments, customer communications
- Promotion scheduling, price testing, content updates
- Running reports, backups, test transactions

### Irreversible (Confirm First)
- **NEVER**: Delete customer data, completed orders, payment records
- **NEVER**: Change tax rates or shipping rules without approval
- **NEVER**: Modify payment processor settings
- **NEVER**: Publish pricing changes without review
- **ALWAYS CONFIRM**: Price discounts >10%, refunds, customer refunds, bulk inventory changes

---

## Critical Paths

| What | Path |
|------|------|
| Products | `data/products.json` or store API |
| Inventory | `data/inventory/` |
| Customers | Store DB (read-only unless escalated) |
| Orders | Store API + analytics |
| Payments | Stripe/Shopify (never edit directly) |
| Config | `config/store-config.json` |
| Templates | `templates/emails/`, `templates/pages/` |

---

## Common Tasks

### Add a product
```bash
POST /api/products with: name, description, price, sku, images
```

### Update inventory
```bash
PUT /api/inventory/{sku} with: quantity, location
```

### Send customer email
```bash
Use template from templates/emails/
Never hardcode customer addresses
```

### Process refund
```bash
1. Verify order exists
2. Check payment status
3. Confirm refund amount
4. Process via Stripe admin
5. Send confirmation email
6. Update order status
```

### Create promotion
```bash
1. Define discount code + terms
2. Set start/end dates
3. Test with test account
4. Schedule announcement
5. Monitor usage
```

---

## Data Security

- **Customer data**: PII protected, never log emails/addresses
- **Payment data**: Never touch raw card data; use Stripe tokens only
- **API keys**: Stored in `~/.claude/private/secrets/store-keys.md`
- **Audit trail**: All order changes logged with timestamp
- **Backup**: Daily backup of products, orders, customers

---

## Pricing & Revenue Rules

- **Price changes**: Require explicit approval, apply to NEW orders only
- **Discounts**: Document reason, set expiration, monitor usage
- **Refunds**: Only for legitimate issues (damaged goods, wrong item, return window)
- **Taxes**: Auto-calculated; never override without accounting review
- **Shipping**: Standard rates locked; overrides require approval

---

## Inventory Management

- **Low stock alerts**: Trigger if product <5 units
- **Out of stock**: Mark as unavailable; don't delete
- **Returns**: Update inventory, move to "returns pending" until inspected
- **Damage/loss**: Document and adjust inventory with notes
- **Reorder point**: [Set threshold for each product category]

---

## Customer Communication

- **Tone**: Helpful, professional, solution-focused
- **Response time**: <24h for urgent issues
- **Templates**: Use from `templates/emails/`; personalize only name/order#
- **Never**: Offer discounts/refunds without approval
- **Escalate**: Issues beyond standard policy to management

---

## Testing Before Live

- **Price changes**: Test with test account first
- **Promotions**: Verify discount code works, limits apply
- **Emails**: Send to internal test address, check rendering
- **Inventory**: Validate quantity updates in staging
- **Refunds**: Test refund flow in sandbox mode

---

## Gotchas & Constraints

1. **Stripe rate limits**: 100 req/s; batch operations carefully
2. **Tax jurisdiction**: Different rules per state/country
3. **Duplicate charges**: Check for double-payments before processing
4. **Email deliverability**: Monitor bounce rates; update suppression lists
5. **Inventory sync**: Manual updates can conflict; use API when possible

---

## Monitoring & Alerts

- **Daily**: Check for failed payments, unresolved orders
- **Weekly**: Inventory levels, customer complaints, refund requests
- **Monthly**: Revenue report, churn analysis, product performance

---

## Escalation

- **Policy questions**: Ask ops team
- **Refund disputes**: Finance approval required
- **Data issues**: IT/database team
- **Urgent customer issue**: Page on-call manager

---

## When Uncertain

1. Check existing order history for similar cases
2. Review customer communication templates
3. Test in staging before applying to live
4. Ask before refunding or changing pricing
5. Document all manual adjustments

---

_See global CLAUDE.md for core principles. This file handles store-specific execution._
