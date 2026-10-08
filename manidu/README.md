# Manidu Lounge: 3D shisha bar

An animated 3D web app of the Manidu shisha lounge. Guests can walk through the bar, build their own shisha mix, order to their table and reserve a seat. It is a single file, `index.html`, with no build step.

## What's inside

- **The lounge in 3D.** This is based on the venue photos: the glass terrace with its burnt-pine slatted pergola, hanging greenery with warm neon loops, grey velvet sofas and dark wingback chairs, the pallet wall with match screens, the backlit bar with the "uuuu" neon wave, lit stairs, the street outside and the MANIDU sign with the bowl in place of the I. Hookahs on the tables smoke, candles flicker, the TVs show a live match and cars pass outside.
- **Intro.** The sign flickers on, the neon switches on zone by zone, and the camera flies from the street through the glass into the terrace.
- **Lounge.** Drag to look around and pinch or scroll to zoom. Glowing pins jump to the terrace, the match screens, the bar, the velvet lounge and the street, and a tour button plays these as a cinematic loop.
- **Mix Lab.** The camera flies to the hookah on the bar and the lid lifts. Guests pick up to three of 26 flavours and drag sliders to set the split. Each flavour drops into the bowl as coloured particles, and the wedges in the bowl, the smoke colour, a donut chart and a taste radar update live. Guests also choose the strength, the bowl (clay, silicone, or a grapefruit or pineapple head), the base (water, ice water, milk or juice) and extras such as an ice hose. All of these change the 3D hookah, and the price updates as they change.
- **Menu.** Signature mixes (with a "Remix" button that opens them in the Mix Lab), drinks, coffee and bites.
- **Order.** The cart shows quantities and the delivery table. When a guest sends an order, a tracker runs through Received → Packing → Coals → On its way. A glowing ember then flies from the bar to the table, and the shisha appears there smoking in the mix's colours.
- **Reserve.** The roof and the building lift off to reveal the floor plan. Guests pick a day, a time and the number of guests. Tables glow as free, taken or too small, and can be tapped in 3D or in the list. Booking produces a ticket with a booking code. Guests can see and cancel their bookings, and the cart preselects today's booked table.

## Run it

Open `index.html` in a browser served over HTTP:

```sh
cd manidu && python3 -m http.server 8000
# then open http://localhost:8000
```

Three.js 0.160 and GSAP 3.12 load from the jsDelivr CDN, so the page needs an internet connection.

## Before going live

- **Orders and bookings are not sent anywhere yet.** They are stored in the guest's own browser (`localStorage`), and table availability is simulated. To make them real, connect `sendOrder()` and `confirmRes()` to a backend (a booking system, a POS, or a simple API plus a staff screen), and replace `taken()` with real availability.
- **Prices and the menu are placeholders.** Edit `FLAVORS`, `SIGNATURES`, `MENU`, `BOWLS`, `BASES`, `EXTRAS` and `BASE_PRICE` near the top of the script.
- **Tables** are defined in `TABLES`: id, zone, seats and position on the floor plan in metres.
