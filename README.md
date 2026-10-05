# Budget Hardware website

Website for **Budget Hardware**, Mweiga Town, Nyeri, Kenya.
A single-page site: customers browse products, order on WhatsApp, and get directions in Google Maps.

## What's in the folder

| File | Purpose |
|------|---------|
| `index.html` | The whole website (HTML, CSS, JavaScript and the pictures, all in one file) |
| `images/` | Copies of the product photos, for reference. The site does not read from this folder. |
| `README.md` | This file |

## Features

- **Rotating logo opening screen.** A big spinning logo shows when the site loads, then the site opens after about 3 seconds. Tapping it opens the site sooner. Clicking the small logo in the header shows it again.
- **WhatsApp ordering.**
  - Every product has an "Ask about..." button that opens WhatsApp with a ready message.
  - A floating "Chat on WhatsApp" button follows the customer down the page.
  - The "Make an order" form turns ticked items, quantities and the customer's name into one WhatsApp message.
- **Directions.** "Get directions" opens Google Maps with driving directions from the customer's current location, from anywhere in the world. An embedded map is also on the page.
- **Admin panel.** Click **Admin** in the footer, enter the PIN, and replace any of the site's pictures.
- **Mobile friendly.** Works on phones, tablets and computers.

## Products shown

Roofing sheets, steel and rebar, water pipes and fittings, drainage and PVC, paint and finishes, fencing and mesh, nails/tools/fixings.

## Settings you should change

Open `index.html`, find the `Settings` comment near the top of the `<script>` section, and edit:

```js
var PHONE = "2547XXXXXXXX";     // WhatsApp number: country code first, no + or spaces
var PIN = "1234";             // Admin PIN. Change this before going live.
var DESTINATION = "Budget Hardware, Mweiga, Nyeri, Kenya";
```

- **PHONE:** Kenya numbers start with `254`, then the number without the leading 0. Example: `07XXXXXXXX` becomes `2547XXXXXXXX`. The number on the shop sign is partly hidden in the photo, so check it is the correct WhatsApp number.
- **PIN:** Only keeps casual visitors out. It is not strong security.
- **DESTINATION:** For an exact pin, open the shop in Google Maps, copy the coordinates (for example `-0.1234,36.5678`), and paste them in place of the text.

## Deploying on Vercel

1. Create a free account at vercel.com.
2. Create a new project and upload this folder (or push it to GitHub and import it).
3. Leave the framework as **Other** with no build command.
4. Deploy. Vercel gives you a link, for example `budget-hardware.vercel.app`.
5. Share the link. Customers who open it can message the shop on WhatsApp straight away.

## Using the admin panel

1. Scroll to the footer and click **Admin**.
2. Enter the PIN.
3. Choose a new photo for any slot. It is resized automatically.
4. Use **Reset to originals** to go back to the built-in pictures.

**Important:** Pictures changed in the admin panel are saved in that browser only. Customers will not see them. To change the pictures everyone sees, replace the pictures in the code and redeploy. Making admin changes show for every visitor needs a login and cloud storage (for example Vercel Blob). This can be added as a next step.

## Known limits

- The admin panel saves to the browser only (see above).
- The site has no prices because none were provided. Customers ask for prices on WhatsApp.
- Orders are sent as WhatsApp messages. There is no payment or order database.

## Next steps (optional)

- Add the correct WhatsApp number from the sign
- Set the exact map pin
- Add opening hours and a short "About us" line
- Admin panel that updates the live site for all customers
- Prices or a price list
