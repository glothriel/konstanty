---
date: "2022-06-05"
description: How to get in touch with me?
title: Contact me
---

<p class="contact-intro">Email is the easiest way to reach me. My phone number is here for friends and family too.</p>

<div class="contact-grid">
<section class="contact-card" aria-labelledby="email-heading">
<h2 id="email-heading">Email & LinkedIn</h2>
<button class="contact-action" id="email-reveal" type="button" onclick="showSecret()">Reveal email address</button>
<p class="contact-result" aria-live="polite"><a id="secret"></a></p>
<a class="contact-action" href="https://www.linkedin.com/in/konstanty-karagiorgis-46264a185/">Find me on LinkedIn</a>
</section>

<script>
// My email as As ASCII arr
var theSecret = [
    107, 111, 110, 115, 116, 97, 110, 116, 121, 64, 107
].concat([97, 114, 97, 103, 105, 111, 114, 103, 105, 115, 46, 112, 108])

function bin2String(array) {
  var result = "";
  for (var i = 0; i < array.length; i++) {
    result += String.fromCharCode(array[i]);
  }
  return result;
}
function showSecret(){
    const email = bin2String(theSecret);
    const link = document.getElementById("secret");
    link.textContent = email;
    link.href = "mailto:" + email;
    document.getElementById("email-reveal").hidden = true;
}
</script>


<section class="contact-card" aria-labelledby="phone-heading">
<h2 id="phone-heading">Phone &amp; messaging</h2>
<p>Telephone, WhatsApp or Signal. A small challenge: enter my wife's first name.</p>
<form class="contact-form" id="form" onsubmit="event.preventDefault(); showPhone();">
  <label for="password">My wife's first name</label>
  <input type="password" id="password" autocomplete="off" required aria-describedby="phone-feedback">
  <button class="contact-action" id="phone-reveal" type="submit">Reveal phone number</button>
  <p class="contact-feedback" id="phone-feedback" role="status"></p>
</form>
<p class="contact-result" id="phone" aria-live="polite"></p>
</section>
</div>

<noscript><p>Please enable JavaScript to reveal my contact details.</p></noscript>

<script>
const encryptedSecret = {
  "iv": [
    21,
    140,
    187,
    116,
    87,
    20,
    80,
    21,
    122,
    146,
    16,
    146
  ],
  "secret": [
    116,
    197,
    181,
    44,
    188,
    76,
    62,
    98,
    26,
    129,
    17,
    137,
    247,
    72,
    217,
    0,
    48,
    172,
    2,
    20,
    13,
    252,
    229,
    244,
    0,
    73,
    38
  ]
};

async function showPhone() {
    const button = document.getElementById("phone-reveal");
    const feedback = document.getElementById("phone-feedback");
    button.disabled = true;
    feedback.textContent = "Checking…";
    try {
        const password = document.getElementById("password").value.toLowerCase();
        const decoder = new TextDecoder();
        const keyMaterial = await crypto.subtle.importKey(
            "raw",
            new TextEncoder().encode(password),
            { name: "PBKDF2" },
            false,
            ["deriveKey"]
        );
        const key = await crypto.subtle.deriveKey(
            {
                name: "PBKDF2",
                salt: new TextEncoder().encode("some_salt"),
                iterations: 100000,
                hash: "SHA-256"
            },
            keyMaterial,
            { name: "AES-GCM", length: 256 },
            false,
            ["decrypt"]
        );
        const iv = new Uint8Array(encryptedSecret.iv);
        const encryptedData = new Uint8Array(encryptedSecret.secret);
        const decrypted = await crypto.subtle.decrypt(
            { name: "AES-GCM", iv: iv },
            key,
            encryptedData
        );
        const secret = decoder.decode(decrypted);
        document.getElementById("phone").textContent = secret;
        // hide the form
        document.getElementById("form").style.display = "none";
    } catch (e) {
        feedback.textContent = "Couldn't unlock the number. Check the name and try again.";
    } finally {
        button.disabled = false;
    }
}

async function generateEncryptedSecret(secret, password) {
    const encoder = new TextEncoder();
    const data = encoder.encode(secret);
    const keyMaterial = await crypto.subtle.importKey(
        "raw",
        encoder.encode(password),
        { name: "PBKDF2" },
        false,
        ["deriveKey"]
    );
    const key = await crypto.subtle.deriveKey(
        {
            name: "PBKDF2",
            salt: encoder.encode("some_salt"), // Use a proper salt in production
            iterations: 100000,
            hash: "SHA-256"
        },
        keyMaterial,
        { name: "AES-GCM", length: 256 },
        false,
        ["encrypt"]
    );
    const iv = crypto.getRandomValues(new Uint8Array(12));
    const encrypted = await crypto.subtle.encrypt(
        { name: "AES-GCM", iv: iv },
        key,
        data
    );
    return {
        iv: Array.from(iv),
        secret: Array.from(new Uint8Array(encrypted))
    };
}
</script>
