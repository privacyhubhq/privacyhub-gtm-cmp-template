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

## Google Consent Mode Signals

This template manages the following consent signals:

- ad_storage
- ad_user_data
- ad_personalization
- analytics_storage
- functionality_storage
- personalization_storage
- security_storage

Default state is set to **denied**, and updated based on user consent.

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

- Before consent:
  - Google tags (GA4, Ads, Floodlight) do NOT fire
  - No `collect` or `g/collect` requests are sent
- Accept all:
  - All consent signals set to granted
  - Tags are released
- Reject all:
  - Consent remains denied
  - Tags remain blocked
- Preferences:
  - Tags load based on selected categories

---

## Compliance Behavior

This template enforces Google Consent Mode v2 by:

- Setting default consent state to denied before user interaction
- Updating consent state after user action via CMP
- Preventing Google tags from firing before consent
- Enabling tags only after valid consent is received

---

## External Script

This template loads the PrivacyHub CMP script from:

https://api.privacyhub.ai/functions/v1/ph

This script is responsible for:
- Displaying consent banner
- Managing consent state
- Controlling script execution

---

## Support

https://www.privacyhub.ai  
support@privacyhub.ai
