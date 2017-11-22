---
title: Essai JavaScript
permalink: /javascript/
---

# Un jour, ça va marcher !

## Stupidités

<div style="color:blue;">I'm blue ! DABADIDABADA !</div>

## Stupidités le retour
<p>
    <input id="field" type="text" />
</p>



<table>
    <tr>
        <td>keydown</td>
        <td id="down"></td>
    </tr>
    <tr>
        <td>keypress</td>
        <td id="press"></td>
    </tr>
    <tr>
        <td>keyup</td>
        <td id="up"></td>
    </tr>
</table>

<script>
    var field = document.getElementById('field'),
        down = document.getElementById('down'),
        press = document.getElementById('press'),
        up = document.getElementById('up');
    document.addEventListener('keydown', function(e) {
        down.innerHTML = e.keyCode;
    });

    document.addEventListener('keypress', function(e) {
        press.innerHTML = e.keyCode;
    });

    document.addEventListener('keyup', function(e) {
        up.innerHTML = e.keyCode;
    });
</script>

<p>
    <input id="cchhaammpp" type="text" />
</p>

## Essayons quelque chose d'intéressant

<p>
    <input id="cchhaammpp" type="text" maxlength="10"/>
</p>
