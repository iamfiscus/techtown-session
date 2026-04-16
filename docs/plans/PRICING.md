# Pricing Structure

## Subscription Pricing

### Content Modules (Per Locality)

| Module         | Monthly | Annual  | Annual Savings |
| -------------- | ------- | ------- | -------------- |
| **Events**     | $29/mo  | $290/yr | ~17% ($58)     |
| **Businesses** | $29/mo  | $290/yr | ~17% ($58)     |
| **News**       | $29/mo  | $290/yr | ~17% ($58)     |

### Add-on Services

| Service           | Monthly | Annual  | Annual Savings |
| ----------------- | ------- | ------- | -------------- |
| **Ad Management** | $49/mo  | $490/yr | ~17% ($98)     |

## How It Works

### Module-Based Billing

- Each module (Events, Businesses, News) is a separate subscription item
- Modules are linked to localities via metadata: `{ localityId: "loc_123", moduleType: "events" }`
- Add/remove modules anytime through Stripe Customer Portal
- Prorated billing when adding/removing modules

### Example Scenarios

**Single Locality with All Modules:**

- Events: $29/mo
- Businesses: $29/mo
- News: $29/mo
- Ad Management: $49/mo
- **Total: $136/mo** or **$1,360/yr** (annual)

**Two Localities with Events Only:**

- Locality A Events: $29/mo
- Locality B Events: $29/mo
- **Total: $58/mo** or **$580/yr** (annual)

**Custom Mix:**

- Locality A: Events ($29) + Businesses ($29) = $58/mo
- Locality B: Events ($29) + News ($29) + Ad Mgmt ($49) = $107/mo
- **Total: $165/mo** or **$1,650/yr** (annual)

## Ad Revenue Sharing

### Platform Economics

- **Creator receives:** 85% of ad revenue
- **Platform fee:** 15% of ad revenue
- **Base subscription:** $49/mo for ad management tools

### Example Ad Revenue

**Scenario: $3,800 monthly ad revenue**

- Creator receives: $3,230 (85%)
- Platform fee: $570 (15%)
- Net to creator after subscription: $3,230 - $49 = **$3,181/mo**

**Scenario: $10,000 monthly ad revenue**

- Creator receives: $8,500 (85%)
- Platform fee: $1,500 (15%)
- Net to creator after subscription: $8,500 - $49 = **$8,451/mo**

## Stripe Product IDs

### Products

| Module        | Product ID            |
| ------------- | --------------------- |
| Events        | `prod_TBR8kMbCpljlWg` |
| Businesses    | `prod_TBR99aH1mP9llN` |
| News          | `prod_TBR9pYYUv1KVnU` |
| Ad Management | `prod_TBR9Z8EiMPEKpf` |

### Monthly Prices

| Module        | Price ID                         |
| ------------- | -------------------------------- |
| Events        | `price_1SF4IVB9cWICdIzHEymbRiKE` |
| Businesses    | `price_1SF4IdB9cWICdIzHYrX9h9EE` |
| News          | `price_1SF4IqB9cWICdIzHUzdkavRl` |
| Ad Management | `price_1SF4IrB9cWICdIzHILd01Lc1` |

### Annual Prices

| Module        | Price ID                         |
| ------------- | -------------------------------- |
| Events        | `price_1SF4IaB9cWICdIzHmZPm1LN5` |
| Businesses    | `price_1SF4IpB9cWICdIzHH04jDBW7` |
| News          | `price_1SF4IrB9cWICdIzHUyqyZfbo` |
| Ad Management | `price_1SF4IsB9cWICdIzHfTomRTI9` |

## Metadata Schema

### Subscription Item Metadata

```json
{
  "localityId": "locality_xyz123",
  "moduleType": "events|businesses|news|ad_management"
}
```

### Usage in Code

**TypeScript Constants (Backend):**

```typescript
// apps/functions/src/stripe/types.ts
export const STRIPE_PRODUCTS = {
  events: {
    productId: "prod_TBR8kMbCpljlWg",
    monthlyPriceId: "price_1SF4IVB9cWICdIzHEymbRiKE",
    annualPriceId: "price_1SF4IaB9cWICdIzHmZPm1LN5",
  },
  // ... other modules
};
```

**TypeScript Constants (Dashboard):**

```typescript
// apps/dashboard/src/lib/stripe/types.ts
export const STRIPE_PRODUCTS = {
  events: {
    monthlyPrice: 29,
    annualPrice: 290,
    // ... price IDs
  },
  // ... other modules
};
```

## Billing Intervals

- **Monthly:** Billed every month on subscription anniversary
- **Annual:** Billed once per year on subscription anniversary
- **Switching:** Users can switch between monthly/annual via Stripe Customer Portal
- **Proration:** When switching or adding modules, Stripe handles prorated billing automatically
