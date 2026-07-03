# NAMOZA Developer Assignment

## Task 02 – OrthoNow Landing Page

This repository contains my solution for **Task 02** of the NAMOZA Developer Assignment.

The objective was to build a responsive landing page for the campaign:

> **"Get an expert orthopaedic opinion – Book your consultation at OrthoNow."**

The landing page is built using **HTML, CSS, and Vanilla JavaScript** as required in the assignment. It is designed for working professionals in Bengaluru experiencing knee or back pain and focuses on providing a simple and smooth consultation booking experience.

---

## Live Demo

https://namoza-developer-assignment-1grj.onrender.com

---

## Loom Walkthrough

https://www.loom.com/share/03c407eed8ef42a48b5291a7549f2d04

---

## GitHub Repository

https://github.com/anuragseth9621/NAMOZA-Developer-Assignment

---


## Technologies Used

- HTML5
- CSS3
- Vanilla JavaScript

---

## Features

- Responsive landing page
- Mobile-first layout
- Consultation form with Name and Phone fields
- Client-side form validation
- GTM `window.dataLayer.push()` event on successful form submission
- Thank-you message without page reload
- Trust section with key highlights
- Benefits section
- Patient testimonials
- Sticky Call-to-Action button for mobile devices
- Basic SEO meta tags
- Accessible form elements

---

## GTM Event

After a successful form submission, the following event is pushed to the Google Tag Manager Data Layer:

```javascript
window.dataLayer.push({
  event: "consultation_form_submitted",
  name: enteredName,
  phone_length: enteredPhone.length,
  page: "orthonow_consultation",
  timestamp: new Date().toISOString()
});
```

This event can be used for conversion tracking through Google Tag Manager.

---

## Performance

The landing page was optimized for fast loading and good Core Web Vitals performance.

**Google PageSpeed Insights**

| Metric | Score |
|---------|------:|
| Mobile Performance | 100 |
| Desktop Performance | 100 |

Performance screenshots are available in the `screenshots` folder.

---

## Project Structure

```text
NAMOZA-Developer-Assignment/
│
├── docs/
├── screenshots/
│   ├── landing-page-preview.png
│   ├── pagespeed-mobile.png
│   ├── pagespeed-desktop.png
│   └── console-datalayer.png (optional)
│
├── index.html
└── README.md
```

---

## How to Run

### Run Locally

1. Clone or download this repository.
2. Open `index.html` in any modern web browser.

### Live Version

https://namoza-developer-assignment-1grj.onrender.com

---

## Assignment Deliverables

- **Task 01:** GTM Event Schema *(docs folder)*
- **Task 02:** Landing Page *(index.html)*
- **Task 03:** CRM Integration Write-up *(docs folder)*

---

## Author

**Anurag Seth**

B.Tech – Information Technology  
Noida Institute of Engineering and Technology (NIET)