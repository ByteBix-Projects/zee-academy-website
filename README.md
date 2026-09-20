# Zee Academy

Responsive course website with a browser-only demo enrollment and payment flow.

## Preview

Run `python3 -m http.server 4173 --directory dist` and open http://localhost:4173.

## Content

- `dist/index.html`: homepage and metadata.
- `dist/app.js`: course catalog, additional sections, course details, demo enrollment, simulated payment states.
- `dist/style.css`: responsive theme, accessibility and reduced-motion support.
- `dist/assets/`: supplied faculty portraits and imagery from Zee Academy's existing website.

Course pricing uses the supplied flyer for Digital Marketing (₹34,999), AI Tools (₹24,999; 3 months), Podcast Production (₹49,999), and Media & Content Creation (₹34,999). Design courses use the supplied website screenshots. Contact details and internship terms use the flyer. Faculty photos follow the order provided: Shivani, Paritosh, Ratnesh. Unconfirmed faculty assignments are not invented.

## Enrollment and payments

Enrollment is deliberately a demo. Personal details are held only in page memory and are never sent or persisted. The flow includes native form validation, a course summary, learning mode, UPI/card/net-banking choices, a simulated decline/retry and a simulated success reference. There is no real transaction, admission record, notification, or email.

For production payments, add a server-side provider integration, create orders from authoritative course prices, verify signed callbacks/webhooks, and persist verified enrollment records. Do not trust a browser-generated success state for real admission.

## Verification

Checked the course category filters, course details, required-field validation, demo decline and retry, card payment simulation, and success confirmation in the browser. Checked mobile navigation and the 390px and 1440px layouts with no horizontal overflow; all images loaded and the browser reported no runtime errors.

The local preview is the current deliverable.

## Student LMS and admin demo

Open `/lms.html` from the **Student login** link on the website.

- Student: `student@gmail.com` / `123456`
- Admin: `admin@gmail.com` / `123456`
- There is no mentor/educator account.

The student workspace includes enrolled courses, activity progress, course curriculum, interactive sample playback, readings, assignments, projects, link-based submissions and admin feedback. Offline enrollments show classroom information and automatically hide every video lesson/player. Sample classroom schedules are explicitly marked.

The admin workspace includes course create/edit, draft/published visibility, reversible archiving, curriculum creation/edit/deletion/reordering, video/reading/assignment/project content, student enrollments and mode changes, and submission review with feedback and optional scores. Course edits are reflected on the website on reload. Videos can use direct HTTP(S) MP4/WebM links; blank URLs use an interactive sample preview. No Vimeo API or upload storage is connected.

`dist/data.js` is the shared demo data adapter. It seeds Digital Marketing online and Interior Designing offline. Completed mock checkout adds the course and chosen mode to the demo student. Data is saved only in this browser under `zee-academy-lms-v1`; login role lasts for the tab session. The portal is a frontend prototype, not secure authentication or authorization. Replace the adapter and role checks with authenticated APIs and server-enforced access before using real student data or payments. Course prices must remain server-authoritative in production.

Verified student/admin sign-in, sample playback, offline restrictions, progress, submissions, admin feedback, course creation, content publication, and public catalog integration using browser interactions.
