# Verification and scope

Review date: 27 October 2026. These checks establish local behavior and source evidence. They do not verify a client's deployment or prove general production readiness.

## Isolation

A disposable application copy and freshly initialized, dedicated local PostgreSQL cluster were used. No existing database records or backups were imported. The original application's working tree, Git history, remotes, deployment and configuration were left unchanged.

The demo settings, product catalog, user and order records were created specifically for this review. Push delivery was disabled. Browser capture allowed loopback requests only; no external browser requests were observed during the successful capture run. No phone, map, messaging, geolocation, email, payment-provider, notification, print or webhook action was invoked. No operational demo is hosted or linked here.

## Evidence

| Area | Evidence gathered for this case study |
| --- | --- |
| Customer order | Browser selected an extra, submitted a pickup request and reached the pending tracking screen |
| Staff preparation | The same order was accepted through the staff browser UI; customer tracking then displayed preparing and ready |
| POS | Browser built a three-item ticket, entered cash, confirmed the sale and opened its receipt; expected change was checked |
| Table service | Synthetic staff order created through the local API and displayed in the table bill; automated tests covered service states and combined payment |
| Menu management | Catalog and availability screen rendered in the browser; automated tests exercised editing, availability, archive/restore and stale-edit guards |
| Cash and delivery | Automated tests exercised drawer shifts, atomic POS payment, driver custody, selected handover and replay safeguards |
| Owner tools | Source reviewed; automated tests covered service controls, permissions and report accounting |
| Responsive web | Desktop views at 1440 × 1000 and customer and staff browser at 390 × 844; phone-width horizontal overflow assertions passed |
| Native staff app | Home, queue, routes and recovery implementation inspected; TypeScript typecheck and Expo lint passed; no authenticated physical-device runtime check performed |

Seventeen targeted automated tests passed across pricing, kitchen snapshots, customer history, POS/catalog/cash operations, tables, delivery, driver access and owner behavior. They ran against isolated schemas in the disposable local cluster. The successful browser capture run recorded no JavaScript page errors.

## Visual evidence and English adaptation

The eight images in `assets/screenshots/` are **English localization previews**, not screenshots of a shipping English edition. They start from the actual application rendered with a synthetic menu and records. Browser text nodes and placeholders were translated, the document was presented left-to-right, prices were formatted illustratively in USD, and synthetic phone strings were displayed using reserved US example numbers. The underlying Moroccan phone validation was retained and exercised with synthetic format-compatible test strings. Application workflows, components, order states and financial calculations were preserved.

Each exported preview contains a visible disclosure bar. Original Arabic captures and disposable preparation scripts are excluded from publication. The generated promotional cover uses these previews as references and is illustrative artwork, not additional feature evidence.

The fictional US setting does not establish US readiness. A real adaptation still needs complete localization of web/native text, errors and receipts; configurable currency, cash presets and phone rules; directional layout review; and end-to-end market testing. Fiscal, tax, gratuity and card requirements would need a separate scope.

## Known limits

- No quantity or ingredient stock ledger, split bills or demonstrated card-payment integration.
- Refunds and complete English localization remain unfinished.
- Offline recovery is bounded; payments and fulfillment require connectivity.
- Native camera capture, background push delivery and hardware printing were not exercised here. The native implementation does not establish direct thermal printing support.
- Management and report implementation does not prove client adoption of every module.
- No timing, conversion, sales, revenue or customer-count claims are made.
- No workflow recording is included. The customer-to-staff flow was verified through the running local application; the published English material consists of clearly labeled still previews.

## Publication review

Only the files in [PUBLICATION_FILES.txt](PUBLICATION_FILES.txt) are proposed for publication. They contain showcase text, media, provenance, rights notices and repository configuration. No application source, build, credentials, environment data, logs, database exports, private documents or inherited Git history are included.

Text, filenames, rendered previews and metadata were checked for client identity and operational addresses. All eight previews were checked for untranslated Arabic, currency consistency and synthetic content. No screenshot contains a table QR code. The cover and previews were visually reviewed; QR decoding and metadata checks are recorded in the final local review. Contact links use only the portfolio, business email and LinkedIn profile supplied for this case study.
