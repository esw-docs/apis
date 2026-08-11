# Quick Start Guide

Welcome to ESW!&#x20;

Expand your Shopify store globally with ESW. From multi-currency payments to duties, taxes, and international shipping, ESW simplifies global commerce so you can sell anywhere - all while staying compliant, all from one platform.&#x20;

Important note: to use the ESW Shopify integration, you must download and enable both International and Payment Apps. They are designed to work together and cannot be used separately.&#x20;

Once you have downloaded these two apps, please contact the ESW Onboarding team. They will complete the provisioning for your account, so the apps can be activated and ready to use.

Let’s get started.&#x20;

{% hint style="danger" icon="light-emergency-on" %}

#### Before you Begin

* The integration of the ESW Shopify Apps requires that you install, enable, and configure *both*, the International App and the Payments App for the solution to be functional.
* Note that these applications are interdependent.
* These Apps cannot be implemented or used separately.
  {% endhint %}

<div data-with-frame="true"><img src="/files/5eb733b326ed21d4c9b8fd0a61dae93c97f2bde4" alt=""></div>

### Managed Process

* After the apps are installed, your account must be provisioned by the ESW Onboarding Team.
* Contact our team and provide your shop domain to notify them of your installation. The onboarding team will complete the provisioning for you.
* Once provisioning is complete, the app will become available for activation in your Shopify admin.
* Activation is the final, simple step that enables ESW apps.

#### Order of Action

{% stepper %}
{% step %}

### Install the International App

Install the ESW Shopify [International App](/shopify/shopify-native/quick-start-guide/install-esw-shopify-apps.md#international-app-1).
{% endstep %}

{% step %}

### Install the Payments App

Install the ESW Shopify [Payments App](/shopify/shopify-native/quick-start-guide/install-esw-shopify-apps.md#payments-app-1).
{% endstep %}

{% step %}

### Create a Market

[Create and configure a m**a**rket](/shopify/shopify-native/configuration/create-a-new-market.md) for your target region(s).
{% endstep %}

{% step %}

### Add Legal Messaging

Add the [ESW Privacy Notice](/shopify/shopify-native/configuration/add-legal-messaging.md) to your Shopify checkout page.
{% endstep %}

{% step %}

### Testing Period

{% hint style="info" icon="flask-vial" %}
Conduct testing to validate:

* App integrations
* Payment workflows
* Market settings and configurations
  {% endhint %}
  {% endstep %}

{% step %}

### Go-Live

Once testing is successful, proceed with **go-live** on the agreed date.

{% hint style="warning" icon="rectangle-beta" %}
Testing before go-live ensures smooth functionality and reduces potential issues in production.
{% endhint %}

{% code expandable="true" %}

```mermaid
%%{init: {
  "theme": "base",
  "themeVariables": {
    "fontFamily": "Arial, sans-serif",
    "primaryColor": "#007A4E",
    "primaryTextColor": "#1E2221",
    "primaryBorderColor": "#007A4E",

    "lineColor": "#1E2221",
    "signalColor": "#1E2221",
    "signalTextColor": "#1E2221",

    "actorBkg": "#CFF3E4",
    "actorTextColor": "#1E2221",

    "labelBoxBkgColor": "#DEEBE5",
    "labelTextColor": "#1E2221",

    "noteBkgColor": "#DEEBE5",
    "noteTextColor": "#1E2221",

    "sequenceNumberColor": "#FFD138",
    "activationBorderColor": "#007A4E",
    "activationBkgColor": "#80E8BF"
  }
}}%%
sequenceDiagram
    autonumber
    participant U as User
    participant SA as Shopify Admin
    participant TP as Testing Period
    participant GL as Go-Live

    Note over U,SA: Shopify setup
    U->>SA: Install the International App
    U->>SA: Install the Payments App
    U->>SA: Add a Market

    Note over SA,TP: Validation phase
    SA->>TP: Conduct testing to validate functionality

    Note over TP,GL: Launch phase
    TP->>GL: Proceed with go-live on agreed date
```

{% endcode %}
{% endstep %}
{% endstepper %}

***
