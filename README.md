# Forge — Apna AI Image & Video Studio

Ye ek complete web app hai jisme tum text likh ke image (Stability AI) aur video (Runway) generate kar sakte ho — apna branded interface ke sath.

## Setup (Local pe chalane ke liye)

### 1. Node.js install karo
Agar pehle se nahi hai to https://nodejs.org se LTS version install karo.

### 2. Dependencies install karo
Terminal/CMD mein is folder ke andar jao aur likho:
```
npm install
```

### 3. API keys set karo
- `.env.example` file ka naam copy karke `.env` bana lo
- Apni Stability AI key yahan se lo: https://platform.stability.ai/account/keys
- Apni Runway key yahan se lo: https://app.runwayml.com/settings/developer
- Dono keys `.env` file mein paste kar do

```
STABILITY_API_KEY=sk-xxxxxxxxxxxx
RUNWAY_API_KEY=key_xxxxxxxxxxxx
```

**IMPORTANT:** `.env` file kabhi kisi ke sath share mat karo, na hi GitHub pe upload karo — ye tumhari private keys hain. `.gitignore` file already isay protect karti hai.

### 4. Server start karo
```
npm start
```

Terminal mein likha aayega: `AI Studio running at http://localhost:3000`

### 5. Browser mein kholo
`http://localhost:3000` pe jao — tumhara tool ready hai.

---

## Ye tool kya karta hai

- **Text → Image**: Stability AI ka Stable Image Ultra model use karta hai. Aspect ratio aur style choose kar sakte ho.
- **Text → Video**: Runway ka Gen-4 Turbo model use karta hai. Agar starting image nahi diya to khud-ba-khud ek frame Stability se generate karke Runway ko de deta hai.

## Hosting (Internet pe live karne ke liye)

Jab local pe test ho jaye aur tum isay duniya ke liye live karna chaho, to ye options hain:
- **Railway.app** ya **Render.com** — dono free tier dete hain Node.js apps ke liye, aur `.env` variables ko unke dashboard mein securely daal sakte ho.
- Deploy karte waqt API keys ko hosting platform ke "Environment Variables" section mein daalna, code mein kabhi hardcode mat karna.

## Cost ka khayal rakho

- Stability AI aur Runway dono **paid APIs** hain — har image/video generate hone pe tumhare account se credits katenge.
- Pehle unke pricing pages check kar lo: 
  - https://platform.stability.ai/pricing
  - https://runwayml.com/pricing

## Aage kya customize kar sakte ho

- Apna logo/branding `public/index.html` mein tabdeel kar sakte ho
- User login/signup system add karke isay proper product bana sakte ho
- Payment gateway (Stripe) add karke users se paise le sakte ho generate karne ke liye
