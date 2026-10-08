# Puff Glyfada: 3D hookah lounge

An animated 3D web app of the Puff hookah lounge in Glyfada. It works the same way as the Manidu app in `../manidu`: guests walk through the lounge, build their own shisha mix, order to their table and reserve a seat. It is a single file, `index.html`, with no build step.

## What's inside

- **The lounge in 3D.** Based on the venue photos:
  - **Main hall:** rattan tub chairs at dark round tables, patio heaters, a black ceiling with white LED strips, big monstera plants and screens on the side wall.
  - **Glass lounge:** the glass partitions with slim rods sit under the backlit PUFF sign. The sign has its red neon dashes and diagonals, and the lounge's back wall carries "THINK OUTSIDE THE BOX" in red neon.
  - **Library wall:** walnut shelves with LED strips, books, the bubblegum bust and the white bear figure. Its door, marked "EVERY PUFF TELLS A STORY.", leads to the VIP room.
  - **VIP room:** green walls with basketballs and framed portraits, an L-shaped sofa, nesting wood tables and a curtain.
  - **Bar:** a lit front, a row of hookahs on the top shelf, the coal station and the gold hookah on the counter.
  - **Out front:** the round green and gold Puff badge over the glass front.
- **Intro, Mix Lab, menu, order tracker and reservations** behave as in Manidu, in Puff's green, gold and red. The zones are Hall, Lounge, VIP and Bar. The VIP room books as a single table for up to ten.

## Run it

```sh
cd puff && python3 -m http.server 8000
# then open http://localhost:8000
```

Three.js 0.160 and GSAP 3.12 load from the jsDelivr CDN. The Permanent Marker and Oswald fonts load from Google Fonts.

## Before going live

- **Orders and bookings are not sent anywhere yet.** They are stored in the guest's browser (`localStorage`), and availability is simulated. Connect `sendOrder()` and `confirmRes()` to a real backend, and replace `taken()` with real availability.
- **Prices, mixes and menu items are placeholders.** Edit `SIGNATURES`, `MENU`, `EXTRAS` and `BASE_PRICE` near the top of the script.
- **The portraits in the VIP room are generic silhouettes,** and the posters are abstract art. Swap in licensed images if you want the real ones.
