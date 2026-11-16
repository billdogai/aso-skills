# BillDog

Paywalls, in-app subscriptions, analytics and messaging for mobile apps, on one customer record.

**Website:** [billdog.io](https://billdog.io)
**Docs:** [billdog.io/docs](https://billdog.io/docs)
**MCP server:** `https://api.billdog.io/mcp` (sign in with BillDog; [setup](https://billdog.io/docs/mcp-server))

## What It Provides

BillDog handles App Store, Google Play and Stripe subscriptions, renders paywalls natively on iOS and Android (SwiftUI / Jetpack Compose) and lets you change them without an App Store review.

### Key Features for ASO Skills

| Feature | Description | Skill Usage |
|---------|-------------|-------------|
| **Revenue metrics** | MRR, ARR, net revenue, active subscriptions, trials, churn, refunds, LTV | `monetization-strategy`, `app-analytics` |
| **Paywall A/B tests** | Test paywall design, price and trial offer per placement | `paywall-optimization`, `monetization-strategy` |
| **Product analytics** | Funnels, retention and cohorts on the same customer record as purchases | `retention-optimization`, `onboarding-optimization` |
| **Subscription lifecycle messaging** | Push and in-app messages triggered by subscription events such as a trial starting or a cancellation | `subscription-lifecycle`, `retention-optimization` |
| **AI paywall generator** | Reads an App Store or Google Play listing and designs three paywalls (free to try at [billdog.io/ai-paywall-generator](https://billdog.io/ai-paywall-generator)) | `paywall-optimization` |
| **Webhooks** | Real-time subscription events | `app-analytics` |

## Setup

```swift
// Swift Package Manager
// https://github.com/billdogai/billdog-ios-spm  (product: BillDogFull)

BillDog.shared.configure(
    config: BillDogConfig(apiKey: "bd_public_test_YOUR_KEY")
)
```

Android, React Native, Expo, Flutter and web SDKs: [billdog.io/docs](https://billdog.io/docs).

## Agent Access

Connect the MCP server in Claude Code, Cursor or another MCP client, then ask for revenue, trial and churn numbers or inspect paywalls, placements and experiments. Setup: [billdog.io/docs/mcp-server](https://billdog.io/docs/mcp-server).

## When to Use BillDog vs App Store Connect

| Need | BillDog | App Store Connect |
|------|---------|------------------|
| Real-time subscription events | ✓ | Delayed |
| Paywall A/B testing | ✓ | ✗ |
| Cross-platform (iOS + Android + web) | ✓ | iOS only |
| Revenue metrics (MRR, churn, LTV) | ✓ | Basic |
| Push and in-app messages on subscription events | ✓ | ✗ |
| Free tier | ✓ (under $3K MTR) | ✓ |

## Integration with ASO Skills

**`paywall-optimization`:** current paywall conversion by placement, and running the A/B test the skill recommends.
**`monetization-strategy`:** MRR trend, trial-to-paid conversion, churn by plan, LTV for CAC.
**`subscription-lifecycle` / `retention-optimization`:** churn and billing-issue cohorts, and the messages sent to them.
