---
date: "2022-06-05"
description: How to get in touch with me?
title: Contact me
---

<p><b>Email:</b> <a id="secret" href="javascript:void(0)" onclick="showSecret()">Click to reveal my e-mail (primitive crawler bot protection)</a></p>

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
    document.getElementById("secret").innerHTML = bin2String(theSecret);
}
</script>


<p><b>Telephone/Whatsapp/Messenger:</b> <span id="phone" href="javascript:void(0)">Enter my wife's first name in the box below and click reveal (more sophisticated spam bot protection, primary for friends & family)</span></p>

<div id="form">
  <input type="password" id="password" placeholder="My wife's name">
  <button onclick="showPhone()">Reveal phone number</button>
</div>

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
    // lowercased
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
    try {
        const decrypted = await crypto.subtle.decrypt(
            { name: "AES-GCM", iv: iv },
            key,
            encryptedData
        );
        const secret = decoder.decode(decrypted);
        document.getElementById("phone").innerHTML = secret;
        // hide the form
        document.getElementById("form").style.display = "none";
    } catch (e) {
        alert("Decryption failed");
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