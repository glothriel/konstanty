---
date: "2022-06-05"
description: Konstanty Karagiorgis - Contact me
title: Contact me
---


<a id="secret" href="javascript:void(0)" onclick="showSecret()">
Click to reveal my e-mail (primitive spam bot protection): ***********
</a>

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

