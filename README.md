### 1. Core Concept & Gameplay Dynamics

The application serves two distinct user perspectives simultaneously:

* **For Young Indonesian Children:** Bright, visual-first cues with bold English text to spark recognition, curiosity, and early English vocabulary.
* **For English-Speaking Adults:** Clear Indonesian words paired with practical phonetic pronunciation guides (e.g., *Kucing* — *KOO-ching*), making it approachable and fun rather than intimidating.

To keep it engaging across ages, the app includes **three distinct game modes** powered by the same vocabulary dataset:

1. **Flash & Flip (Classic Teaching / Exploration):**
* A standard card that shows any combination of the 3 components (Picture, English, Indonesian).
* Tap to flip or reveal hidden pieces (e.g., show picture + Indonesian; tap to reveal English).
* Includes an easy phonetic guide and an optional browser speech synthesis button (Web Speech API) for pronunciation.


2. **"Tebak Cepat" / Match 3 (Multiple Choice Quiz):**
* Shows one prompt (e.g., the Picture or the Indonesian word) and presents 3 or 4 tap-friendly option tiles (English words or Pictures).
* Generates instant celebratory visual feedback (gentle confetti, green bounce) when correct.


3. **Turn-and-Pass (Two-Player Co-op / Challenge):**
* Designed for an adult and child sitting together holding the phone.
* Screen highlights who guesses: Child names it in English, Adult attempts the Indonesian pronunciation, then tap to check if both got it right!



### 2. Category & Vocabulary Structure (150–200 Words)

Organized into 6 easy-to-filter, child-friendly themes:

* **Hewan / Animals:** Kucing (Cat), Anjing (Dog), Burung (Bird), Ikan (Fish), Gajah (Elephant), Monyet (Monkey), Sapi (Cow), etc.
* **Rumah & Benda / Around the House:** Meja (Table), Kursi (Chair), Pintu (Door), Tempat Tidur (Bed), Sendok (Spoon), Garpu (Fork), Gelas (Cup/Glass), etc.
* **Mainan & Waktu Bermain / Toys & Play:** Bola (Ball), Boneka (Doll), Layang-layang (Kite), Sepeda (Bicycle), Balok (Blocks), Mobil-mobilan (Toy car), etc.
* **Sekolah & Belajar / School & Learning:** Buku (Book), Pensil (Pencil), Tas (Bag), Gunting (Scissors), Kertas (Paper), Penggaris (Ruler), etc.
* **Makanan & Minuman / Food & Drink:** Apel (Apple), Pisang (Banana), Nasi (Rice), Roti (Bread), Air (Water), Susu (Milk), Telur (Egg), etc.
* **Alam & Warna / Nature & Colors:** Matahari (Sun), Bulan (Moon), Pohon (Tree), Merah (Red), Biru (Blue), Hijau (Green), Kuning (Yellow), etc.

Each card entry contains:

* `id`, `category`
* `indonesian`: Word in Indonesian
* `pronunciation`: Simple English phonetic approximation (e.g., *Burung* -> *BOO-roong*)
* `english`: Word in English
* `icon` / `svg`: Inline clean vector SVG graphics or high-contrast, universally supported Twemoji/SVG symbols (ensuring instant, crisp offline rendering without heavy image downloads).


### 3. Visual Design & Creative Flair

* **Color Palette & Theme:** Warm tropical aesthetic—warm mango yellow, rich ocean teal, soft coral, and crisp cream backgrounds. High contrast for outdoor sunlight readability.
* **Card Styling:** Chunky, tactile cards with soft shadows, subtle 3D bevels, and rounded corners (`border-radius: 20px`) that feel like physical educational cards.
* **Micro-Animations:**
* Satisfying 3D card-flip rotation when tapping.
* Playful wiggle/bounce when a correct answer is chosen.
* Visual particle burst/sparkle without being overstimulating for young children.


* **Typography:** Friendly, rounded, highly legible sans-serif font (like *Fredoka* or *Quicksand* / system rounded fonts) that makes reading effortless for beginning readers.


### 4. Small Screen Mobile Ergonomics

* **Thumb-Zone Optimization:**
* Big touch targets (minimum 52px height) so small fingers and adult thumbs never mis-click.
* Mode switches, "Next / Shuffle" buttons, and answer tiles are anchored along the bottom half of the screen.


* **Viewport Safe Areas:** Generous top/bottom padding to respect notch cutouts and home gesture bars on modern mobile browsers.
* **No Pinch-Zoom Friction:** Configured viewport metadata (`user-scalable=no, viewport-fit=cover`) so fast tapping feels like a native app rather than a webpage.


### 5. 100% Offline & GitHub Pages Architecture

To ensure it works flawlessly in remote areas with zero cellular reception or Wi-Fi:

* **Zero Heavy External Dependencies:** Built as a self-contained Single-Page App (HTML5 + CSS3 + Vanilla JavaScript) or bundled with inline SVGs/data.
* **Progressive Web App (PWA) Ready:** Includes a lightweight `manifest.json` and a Service Worker (`sw.js`).
* *How this works on GitHub Pages:* The first time you visit the URL on Wi-Fi, the browser automatically caches every script, style, and icon.
* You can tap **"Add to Home Screen"** on iOS Safari or Android Chrome, and it launches full-screen like a regular mobile app even in Airplane Mode.


* **Device Text-to-Speech:** Uses the native browser `window.speechSynthesis` API (which runs locally on Android and iOS devices without sending data to cloud servers) with fallback to phonetic text cues.
