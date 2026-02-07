<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<title>Negão xiter - Key System</title>

<style>

body{
    margin:0;
    background:linear-gradient(135deg,#05050a,#120015);
    font-family:Arial;
    height:100vh;
    color:white;
}

/* Caixa Key */
#keyBox{
    position:fixed;
    top:50%;
    left:50%;
    transform:translate(-50%,-50%);
    width:280px;
    background:#0e0e16;
    border:2px solid #ff0077;
    border-radius:15px;
    padding:20px;
    box-shadow:0 0 25px #ff0077;
    text-align:center;
}

input{
    width:100%;
    padding:8px;
    background:#1c1c25;
    border:none;
    color:white;
    border-radius:6px;
    margin:10px 0;
}

button{
    width:100%;
    padding:10px;
    background:#ff0077;
    border:none;
    color:white;
    border-radius:8px;
    cursor:pointer;
    margin-top:8px;
}

button:hover{
    box-shadow:0 0 15px #ff0077;
}

/* Painel */
#panel{
    position:fixed;
    top:50%;
    left:50%;
    transform:translate(-50%,-50%);
    width:320px;
    background:#0e0e16;
    border-radius:18px;
    border:2px solid #ff0077;
    box-shadow:0 0 30px #ff0077;
    display:none;
    padding:15px;
}

#header{
    text-align:center;
    color:#ff0077;
    font-size:22px;
    margin-bottom:10px;
}

.option{
    background:#161621;
    padding:10px;
    margin:7px 0;
    border-radius:8px;
    display:flex;
    justify-content:space-between;
    align-items:center;
}

/* Switch */
.switch{
    width:45px;
    height:22px;
    background:#333;
    border-radius:20px;
    position:relative;
    cursor:pointer;
}

.switch::before{
    content:"";
    width:18px;
    height:18px;
    background:white;
    border-radius:50%;
    position:absolute;
    top:2px;
    left:2px;
    transition:0.3s;
}

.switch.active{
    background:#ff0077;
}

.switch.active::before{
    left:25px;
}

/* Slider */
.slider{
    width:100%;
}

#fovBox{
    margin-top:8px;
    background:#161621;
    padding:8px;
    border-radius:8px;
}

#footer{
    text-align:center;
    font-size:12px;
    color:#777;
    margin-top:10px;
}

#msg{
    font-size:14px;
}

</style>
</head>

<body>

<!-- KEY -->
<div id="keyBox">

<h2 style="color:#ff0077;">Negão xiter</h2>

<p>Digite sua Key</p>

<input id="keyInput" placeholder="NX-XXXXX-XXX">

<button onclick="checkKey()">Acessar</button>

<p id="msg"></p>

</div>


<!-- PAINEL -->
<div id="panel">

<div id="header">Negão xiter</div>

<div class="option">
<span>Aimbot</span>
<div class="switch"></div>
</div>

<div class="option">
<span>Aimlet</span>
<div class="switch"></div>
</div>

<div class="option">
<span>FPS 120</span>
<div class="switch"></div>
</div>

<div class="option">
<span>Black Jack</span>
<div class="switch"></div>
</div>


<!-- FOV -->
<div id="fovBox">

<div class="option">
<span>FOV</span>
<span id="fovVal">90</span>
</div>

<input type="range"
       min="0"
       max="180"
       value="90"
       class="slider"
       id="fov">

</div>

<!-- BOTÃO ABRIR FREE FIRE -->
<button onclick="abrirFreeFire()">
🎮 Abrir Free Fire
</button>


<div id="footer">
Sistema por Key • v1.2
</div>

</div>


<script>

/* Validar Key */
function checkKey(){

    let key = document.getElementById("keyInput").value.trim();

    let regex = /^NX-[A-Z0-9]{5}-[A-Z0-9]{3}$/;

    if(regex.test(key)){

        document.getElementById("keyBox").style.display="none";
        document.getElementById("panel").style.display="block";

        alert("Acesso liberado!");

    }else{

        document.getElementById("msg").innerText = "Key inválida!";
        document.getElementById("msg").style.color="red";

    }
}

/* Switch */
document.querySelectorAll(".switch").forEach(sw=>{
    sw.onclick = ()=>{
        sw.classList.toggle("active");
    };
});

/* FOV */
let fov = document.getElementById("fov");
let fovVal = document.getElementById("fovVal");

fov.oninput = ()=>{
    fovVal.innerText = fov.value;
};

/* Abrir Free Fire */
function abrirFreeFire(){

    window.location.href =
    "intent://com.dts.freefireth/#Intent;scheme=package;package=com.dts.freefireth;end";

}

</script>

</body>
</html>
