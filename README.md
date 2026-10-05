<!-- revenuedot:readme:start -->
<p align="center"><a href="https://revenuedot.app"><picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/revenuedot/revenuedot/main/brand/kit/wordmark/revenuedot-lockup-white.svg">
  <img alt="RevenueDot" src="https://raw.githubusercontent.com/revenuedot/revenuedot/main/brand/kit/wordmark/revenuedot-lockup-black.svg" height="40">
</picture></a></p>

# RevenueDot Android SDK

This is RevenueDot's MIT fork of RevenueCat's `purchases-android`: the same classes and method names, pointed at a RevenueDot server ([RevenueDot Cloud](https://app.revenuedot.app/signup) at `https://api.revenuedot.app`, or one you host) with RevenueDot's response-signing key built in, and kept in sync with upstream.

[![License: MIT](https://img.shields.io/badge/license-MIT-blue)](LICENSE) [![Maven Central](https://img.shields.io/maven-central/v/app.revenuedot.purchases/purchases?label=Maven%20Central)](https://central.sonatype.com/artifact/app.revenuedot.purchases/purchases) [![Upstream](https://img.shields.io/badge/upstream-RevenueCat%2Fpurchases--android_10.24.0--SNAPSHOT-lightgrey)](https://github.com/RevenueCat/purchases-android)

## Install

```kotlin
// build.gradle.kts
implementation("app.revenuedot.purchases:purchases:10.23.3")
implementation("app.revenuedot.purchases:purchases-ui:10.23.3")   // only if you use RevenueCat UI
```
Kotlin packages stay `com.revenuecat.purchases.*`, so imports do not change.

## Configure

```kotlin
import com.revenuecat.purchases.Purchases
import com.revenuecat.purchases.PurchasesConfiguration
import java.net.URL

// Self-hosted server only: RevenueDot Cloud (https://api.revenuedot.app) is the default.
Purchases.proxyURL = URL("https://revenuedot.example.com")
Purchases.configure(PurchasesConfiguration.Builder(this, "goog_...").build())   // the app's public key from the RevenueDot dashboard
```

The fork already trusts RevenueDot's signing key, so no signature or verification setting is needed. This fork also sends diagnostics, paywall events and ad events to `proxyURL`. Full guide: https://revenuedot.app/docs/sdks/android.

## What RevenueDot adds

- **Start free on [RevenueDot Cloud](https://app.revenuedot.app/signup)**: free up to $10,000 a month of tracked revenue, then 0.5%, never more than $999 a month ([pricing](https://revenuedot.app/pricing)).
- **The same REST API and webhook payloads** as RevenueCat, so your backend and integrations keep working ([API reference](https://revenuedot.app/docs/api)).
- **Paywalls, experiments and the Customer Center** built in the RevenueDot dashboard and rendered by this SDK ([guides](https://revenuedot.app/docs/guides)).
- **A one-line migration:** point the stock SDK at RevenueDot with `setProxyURL`, or install this fork and drop the line ([migration guide](https://revenuedot.app/docs/migrate)).

## Use with your coding agent

Coding agents can read this repository's docs and code on demand, so they use the right package and imports:

- **Context7:** https://context7.com/revenuedot/purchases-android
- **DeepWiki:** https://deepwiki.com/revenuedot/purchases-android
- **GitMCP:** https://gitmcp.io/revenuedot/purchases-android

## Links

- **Docs for this SDK:** https://revenuedot.app/docs/sdks/android
- **Example app:** https://github.com/revenuedot/examples/tree/main/mobile/android-compose
- **Releases and changelog:** https://github.com/revenuedot/purchases-android/releases (tags `<upstream version>-revenuedot`; upstream's changes are in `CHANGELOG.md`)
- **RevenueDot server and dashboard:** https://github.com/revenuedot/revenuedot
- **Fork pipeline (what we change and how upstream is merged):** https://github.com/revenuedot/revenuedot/tree/main/scripts/forks

RevenueDot is not affiliated with RevenueCat, Inc. RevenueCat's copyright notice stays in `LICENSE`; RevenueDot's changes are MIT too.

---

## Upstream README (RevenueCat's, unchanged)
<!-- revenuedot:readme:end -->

<h3 align="center">😻 In-App Subscriptions Made Easy 😻</h3>

[![License](https://img.shields.io/github/license/RevenueCat/purchases-android.svg?style=flat)](https://github.com/RevenueCat/purchases-android/blob/main/LICENSE)
[![Release](https://img.shields.io/github/release/RevenueCat/purchases-android.svg?style=flat)](https://github.com/RevenueCat/purchases-android/releases)

RevenueCat is a powerful, reliable, and free to use in-app purchase server with cross-platform support. Our open-source framework provides a backend and a wrapper around StoreKit and Google Play Billing to make implementing in-app purchases and subscriptions easy. 

Whether you are building a new app or already have millions of customers, you can use RevenueCat to:

  * Fetch products, make purchases, and check subscription status with our [native SDKs](https://docs.revenuecat.com/docs/installation). 
  * Host and [configure products](https://docs.revenuecat.com/docs/entitlements) remotely from our dashboard. 
  * Analyze the most important metrics for your app business [in one place](https://docs.revenuecat.com/docs/charts).
  * See customer transaction histories, chart lifetime value, and [grant promotional subscriptions](https://docs.revenuecat.com/docs/customers).
  * Get notified of real-time events through [webhooks](https://docs.revenuecat.com/docs/webhooks).
  * Send enriched purchase events to analytics and attribution tools with our easy integrations.

Sign up to [get started for free](https://app.revenuecat.com/signup).

## Purchases

*Purchases* is the client for the [RevenueCat](https://www.revenuecat.com/) subscription and purchase tracking system. It is an open source framework that provides a wrapper around `BillingClient` and the RevenueCat backend to make implementing in-app subscriptions in `Android` easy - receipt validation and status tracking included!

## Migration Guides
| Description | Link |
| --- | --- |
| Migrating from v4.x.x to v5.x.x | [V5 API Migration Guide](./migrations/v5-MIGRATION.md) |
| Migrating from v5.x.x to v6.x.x | [V6 API Migration Guide](./migrations/v6-MIGRATION.md) |



## RevenueCat SDK Features
|   | RevenueCat |
| --- | --- |
✅ | Server-side receipt validation
➡️ | [Webhooks](https://docs.revenuecat.com/docs/webhooks) - enhanced server-to-server communication with events for purchases, renewals, cancellations, and more  
🎯 | Subscription status tracking - know whether a user is subscribed whether they're on iOS, Android or web  
📊 | Analytics - automatic calculation of metrics like conversion, mrr, and churn  
📝 | [Online documentation](https://docs.revenuecat.com/docs) up to date  
🔀 | [Integrations](https://www.revenuecat.com/integrations) - over a dozen integrations to easily send purchase data where you need it  
💯 | Well maintained - [frequent releases](https://github.com/RevenueCat/purchases-android/releases)  
📮 | Great support - [Help Center](https://revenuecat.zendesk.com) 

## Getting Started
For more detailed information, you can view our complete documentation at [docs.revenuecat.com](https://docs.revenuecat.com/docs).

Please follow the [Quickstart Guide](https://docs.revenuecat.com/docs/) for more information on how to install the SDK.

Or view / build our Android sample app:
- [MagicWeather](examples/MagicWeather) (open it on a different Android Studio window)

## Codelab

1. [RevenueCat Google Play Integration](https://revenuecat.github.io/codelabs/google-play.html#0): In this codelab, you'll learn how to:

   - Properly configure products on Google Play.
   - Set up the RevenueCat dashboard and connect it to your Google Play products.
   - Understanding Product, Offering, Package, and Entitlement.
   - Create paywalls using the [Paywall Editor](https://www.revenuecat.com/docs/tools/paywalls/creating-paywalls#using-the-editor).

2. [Android In-App Purchases & Paywalls](https://revenuecat.github.io/codelabs/android.html#0): In this codelab, you will:

   - Integrate the Android RevenueCat SDK into your project
   - Implement in-app purchases in your Android application
   - Learn how to distinguish between paying and non-paying users
   - Build a paywall screen, which is based on server-driven UI approach

## Requirements
- Java 8+
- Kotlin 1.8.0+
- Minimum target: Android 6.0+ (API level 23+)
    - Paywalls and Customer Center minimum target: Android 7.0+ (API level 24+)

## SDK Reference
Our full SDK reference [can be found here](https://sdk.revenuecat.com/android/index.html).

## Contributing
Contributions are always welcome! To learn how you can contribute, please see the [Contributing Guide](./CONTRIBUTING.md).
