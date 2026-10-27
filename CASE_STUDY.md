# A connected ordering and restaurant workspace

Restaurant work crosses several screens. A customer chooses food, staff decide whether to accept the request, preparation moves forward, and someone must record the payment correctly. This project connects those tasks through a shared order record.

Screenshots use a fictional restaurant and demonstration data. Client identity and live systems are not shared.

## Customer journey

The implemented website supports category browsing and search, customization, quantities, notes and a cart. Delivery and pickup require a phone number. Table-specific ordering carries table context. Orders are priced and saved by the server before the customer sees a tracking page. Saved tracking links can be revisited on the same browser without creating a customer account.

A delivery request is not a confirmed delivery charge. Staff confirm the fee when accepting it. The location handoff can use an address, browser geolocation or a customer-initiated WhatsApp message. No location, messaging or phone integrations were invoked during showcase testing.

## From request to preparation

Guest requests enter a pending queue. Staff can accept or reject them; accepted orders move through preparing and ready, followed by the appropriate pickup, delivery or served state. Browser polling refreshes the shared view. The isolated test placed a customized pickup order through the customer interface, accepted it through the staff interface, and checked that preparing and ready appeared on customer tracking.

The native app has a Home screen, order queue and detail views, plus operational routes. Route navigation keeps the shared workspace alive so a screen change does not discard a ticket. This implementation was inspected and statically checked; no native device session is presented as evidence here.

## Counter, tables and cash

The POS supports product selection, editable quantities and options, held tickets, an online price quote and cash checkout. In the local browser test, a 20.00 demonstration ticket was paid with 25.00, returning 5.00 change and a receipt.

Table service groups orders into a visit and one combined bill. Pending requests must be resolved and active food served before checkout. Staff can add items and request the bill. Automated tests exercised table state changes, combined payment and rejection of stale visits. Split bills are outside the implemented scope.

An open drawer shift is required for drawer payments. Driver cash collection and drawer handover remain separate events: marking a delivery paid does not mean that cash has reached the drawer. Local automated tests exercised this separation and retry protections. No client financial records appear in this repository.

## Menu and owner tools

The catalog supports category and price editing, variants, modifiers, photos, availability and archive/restore. It does not deduct ingredient quantities or track stock counts. Owner tools include service pause/hours, account management, table administration and daily reports based on customer payment day. Reports were checked with synthetic automated fixtures; no sales dashboard is used as promotional proof of business results.

## Engineering contribution

Project work covers the customer experience, staff web and native workflows, API validation, database schema and transactional financial behavior. The implementation keeps historical item snapshots, computes prices on the server, preserves retry identities and checks stale state when recording money or changing shared records.

React/Vite provides the browser surfaces. Express and PostgreSQL own shared state. Shared JavaScript modules handle pricing and operational helpers. The native app uses Expo 57, React Native, TypeScript and Expo Router. Deployment configuration and private source are deliberately outside this case study.

## What the visuals mean

Ember & Oak Grill is fictional example content, not the software name. Its US menu and USD values are illustrative. Current application text, currency formatting and phone validation are market-specific. Browser-only translation and left-to-right formatting were used to make the implemented screens understandable to English-speaking readers. These are localization previews, not a shipped English edition or US compliance claim.

A scoped adaptation would externalize interface copy, translate validation/errors/receipts and native labels, replace hardcoded currency and cash presets, make phone rules market-aware, audit directional icons and layouts, and test the adapted customer and staff workflows end to end. Taxes, tipping, card processing and market-specific fiscal requirements need their own requirements and implementation review.

Native background push delivery, physical camera capture and printer hardware were not verified for this case study. Native previews do not establish thermal-printer support. Offline recovery is limited to local drafts, cached reference data and queued unpaid native counter orders; financial and fulfillment actions require a server connection. Refunds and broader localization remain unfinished.

[Discuss a similar custom project](CONTACT.md) · [Visual walkthrough](README.md) · [Verification](VERIFICATION.md)
