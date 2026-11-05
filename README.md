# Custom subscription page

This folder is a ready-to-use 3x-ui custom subscription theme. Point **Sub Theme Directory** at this folder on the server, or copy `index.html` into a theme folder on the server.

The template keeps the subscription page layout, announcement, usage display, apps, JSON subscription link, JSON QR code, configuration links, theme toggle, and support link. The Apps tab contains only Happ and Incy, with their icons. The subscription links area contains only the JSON URL and its QR code. The page offers English and Russian language selection and remembers the choice in the visitor's browser. The header logo and app icons are embedded in `index.html`, so no additional image files need to be served.

The QR generator, Three.js r134, and Vanta.js Globe 0.5.24 are embedded in `index.html`, so the theme does not depend on an external CDN. Their licenses are included in `QRCODE-LICENSE.txt`, `THREE-LICENSE.txt`, and `VANTA-LICENSE.txt`.
