# PrivacyHub CMP (Official) – GTM Template

PrivacyHub CMP enables Google Consent Mode v2 compliance with automatic consent handling for analytics and advertising tags.

## Features

- Google Consent Mode v2 compliant
- Blocks GA4, Ads, Floodlight before consent
- Supports:
  - GA4
  - Google Ads
  - Floodlight
  - IAB TCF v2.2
  - IAB GPP (US Privacy)
  - Global Privacy Control (GPC)

---

## Setup

### Step 1 — Add Template

Import **PrivacyHub CMP (Official)** in GTM Templates.

---

### Step 2 — Create ONE Tag

| Setting | Value |
|--------|------|
| Tag Type | PrivacyHub CMP (Official) |
| Website ID | Your PrivacyHub Website ID |
| Script URL | https://api.privacyhub.ai/functions/v1/ph |

---

### Step 3 — Add Triggers

- Consent Initialization – All Pages  
- Custom Event: `ph_consent_updated`

---

### Step 4 — GA4 Setup

Create GA4 tag with trigger: privacyhub_google_tag_init_after_consent

---

## Behavior

- Before consent → all tracking blocked  
- Accept all → tracking enabled  
- Reject all → tracking blocked  
- Preferences → conditional loading  

---

## Compliance Behavior

This template enforces Google Consent Mode v2 by:

- Setting default consent state to denied before user interaction
- Updating consent state after user action via CMP
- Preventing Google tags from firing before consent
- Enabling tags only after valid consent is received

---

## Support

https://www.privacyhub.ai  
support@privacyhub.ai
