https://web-improve-23.preview.emergentagent.com/

<!DOCTYPE html>
<html>
<head>
<title>4:1 AI Multiplexer</title>
<style>
*{box-sizing:border-box}
body{
 margin:0;background:#070b12;color:#eee;
 font-family:Arial;padding:30px
}
.box{
 max-width:800px;margin:auto;
 background:#0e151f;padding:25px;
 border:1px solid #234;border-radius:18px
}
h1{font-size:45px}
p{color:#8291a5;line-height:1.6}
.mux{
 display:flex;align-items:center;
 justify-content:center;gap:40px;
 padding:50px 10px;
 background:#0a111a;
 border:1px solid #234;
 border-radius:15px
}
.inputs div{margin:18px 0}
.m{
 padding:60px 35px;
 border:2px solid #28dfff;
 border-radius:15px;
 text-align:center
}
button{
 padding:14px 25px;margin:5px;
 border:1px solid #456;
 border-radius:8px;
 background:#111c29;color:white;
 cursor:pointer
}
button:hover,.active{
 background:#063b48;
 border-color:#28dfff
}
table{
 width:100%;margin-top:20px;
 border-collapse:collapse
}
td,th{
 padding:14px;
 border-bottom:1px solid #234;
 text-align:center
}
.high{color:#28dfff}
.route{
 margin-top:20px;
 padding:15px;
 border-radius:10px;
 background:#17202c
}
@media(max-width:600px){
 .mux{gap:10px}
 h1{font-size:35px}
}
</style>
</head>

<body>

<div class="box">

<p>MUX / STUDIO · 4:1 AI MULTIPLEXER</p>

<h1>4:1 AI<br>Multiplexer</h1>

<p>
Route Vision, Voice, Search or Generate
through one shared output.
</p>

<div class="mux">

<div class="inputs">
<div>● I0 VISION</div>
<div>● I1 VOICE</div>
<div>● I2 SEARCH</div>
<div>● I3 GENERATE</div>
</div>

<div class="m">
4 : 1 MUX
<h1 id="out">Y1</h1>
<span id="name">SEARCH</span>
</div>

<div>🟡 Y</div>

</div>

<h2>Select Lines</h2>

<button onclick="select(0)">S1 = 0</button>
<button onclick="select(1)">S1 = 1</button>
<button onclick="select(2)">S0 = 0</button>
<button onclick="select(3)">S0 = 1</button>

<h2>Truth Table</h2>

<table>
<tr>
<th>S1</th>
<th>S0</th>
<th>Input</th>
<th>Output</th>
</tr>

<tr onclick="setRoute(0)">
<td>0</td><td>0</td><td>VISION</td><td>Y0</td>
</tr>

<tr onclick="setRoute(1)">
<td>0</td><td>1</td><td>VOICE</td><td>Y1</td>
</tr>

<tr onclick="setRoute(2)">
<td>1</td><td>0</td><td>SEARCH</td><td>Y2</td>
</tr>

<tr onclick="setRoute(3)">
<td>1</td><td>1</td><td>GENERATE</td><td>Y3</td>
</tr>

</table>

<h2>AI Inputs</h2>

<button onclick="toggle(0)">VISION</button>
<button onclick="toggle(1)">VOICE</button>
<button onclick="toggle(2)">SEARCH</button>
<button onclick="toggle(3)">GENERATE</button>

<div class="route" id="route">
Active Route: SEARCH → Y
</div>

</div>

<script>

let input=[0,0,1,0];
let route=2;

function setRoute(n){
 route=n;
 update();
}

function select(n){
 if(n==0) route=0;
 if(n==1) route=2;
 if(n==2) route=0;
 if(n==3) route=1;
 update();
}

function toggle(n){
 input[n]=input[n]?0:1;
 update();
}

function update(){

 let names=[
  "VISION",
  "VOICE",
  "SEARCH",
  "GENERATE"
 ];

 document.getElementById("out").innerHTML=
 "Y"+input[route];

 document.getElementById("name").innerHTML=
 names[route];

 document.getElementById("route").innerHTML=
 "Active Route: "+
 names[route]+
 " → Y"+input[route];
}

update();

</script>

</body>
</html>
