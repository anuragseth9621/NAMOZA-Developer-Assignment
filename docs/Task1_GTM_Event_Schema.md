# Task 01 – GTM Event Schema & GA4 Tracking Strategy

## Overview

## Overview

This document outlines the proposed Google Tag Manager (GTM) event tracking strategy for the OrthoNow website. The tracking plan focuses on measuring key user interactions throughout the appointment booking journey, helping the marketing team analyse user behaviour, identify drop-off points, and optimise campaign performance using Google Analytics 4 (GA4) and Google Ads.
---

# User Journey

```
Landing Page
      │
      ▼
Clinic Page
      │
      ▼
Booking Form
      │
      ▼
Step 1 – Clinic & Specialty
      │
      ▼
Step 2 – Name & Phone
      │
      ▼
Booking Confirmation
```

---

# GTM Event Schema

| Event Name | Trigger | Key Parameters | Purpose |
|------------|----------|---------------|---------|
| appointment_booking_start | User starts booking form | form_id, booking_session_id | Track booking intent |
| appointment_booking_step | User completes a booking step | step_number, step_name, clinic_location, specialty | Measure funnel progression |
| appointment_booking_complete | Successful booking | appointment_id, clinic_location, specialty | Primary conversion event |
| click_to_call | Phone link clicked | click_url, clinic_location | Track call enquiries |
| whatsapp_click | WhatsApp button clicked | click_url, page_location | Track WhatsApp enquiries |
| patient_guide_lead | Guide form submitted | guide_name, page_location | Track downloadable guide leads |
| file_download | PDF downloaded | file_name, file_extension | Track resource downloads |
| clinic_page_view | Clinic page visited | clinic_location, page_title | Measure clinic page traffic |
| blog_scroll | Scroll depth reached | article_title, scroll_threshold | Measure content engagement |
| blog_read_complete | Article completed | article_title, time_on_page | Measure full article reads |

---

# Example dataLayer Push

## Booking Started

```javascript
window.dataLayer.push({
  event: "appointment_booking_start",
  form_id: "appointment_booking",
  booking_session_id: "orthonow_987654321"
});
```

## Booking Step

```javascript
window.dataLayer.push({
  event: "appointment_booking_step",
  step_number: 2,
  step_name: "patient_details_entered",
  clinic_location: "Bengaluru",
  specialty: "Orthopedics",
  form_id: "appointment_booking",
  booking_session_id: "orthonow_987654321"
});
```

## Booking Completed

```javascript
window.dataLayer.push({
  event: "appointment_booking_complete",
  appointment_id: "APT-2026-00941",
  clinic_location: "Bengaluru",
  specialty: "Orthopedics",
  form_id: "appointment_booking",
  booking_session_id: "orthonow_987654321"
});
```

---

# GA4 Funnel

```
Booking Started
      │
      ▼
Step 1 Completed
      │
      ▼
Step 2 Completed
      │
      ▼
Booking Confirmed
```

This funnel helps identify where users leave the booking process so improvements can be made to increase conversions.

---

# Google Ads Conversion

The primary conversion imported into Google Ads is:

```
appointment_booking_complete
```

Using the final booking confirmation as the primary conversion helps optimize campaigns toward completed bookings instead of partial form interactions.

---

## Implementation Notes

- Events are pushed using `window.dataLayer.push()`.
- Google Tag Manager listens for these events and forwards them to GA4.
- The final booking completion event is configured as the primary Google Ads conversion.
- The event structure is designed to support future integrations with HubSpot CRM.

---

**Author:** Anurag Seth