<!DOCTYPE html>
<html lang="pt">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Tinhico Microcrédito PRO</title>

<style>
body{font-family:Arial;margin:0;background:#f2f2f7;}
.hidden{display:none;}

nav{background:#1f1f1f;padding:15px;text-align:center;position:fixed;width:100%;top:0;}
nav a{color:white;margin:10px;text-decoration:none;font-weight:bold;}
nav a:hover{color:#ff9800;}

header{margin-top:70px;background:#ff9800;color:white;text-align:center;padding:60px;}

section{padding:30px;max-width:900px;margin:auto;background:white;margin-bottom:20px;opacity:0;transform:translateY(40px);transition:.6s;}
section.show{opacity:1;transform:translateY(0);}

button{padding:12px;background:#ff9800;border:none;color:white;border-radius:8px;cursor:pointer;}
button:hover{background:#e68900;}

input{width:100%;padding:10px;margin:10px 0;border-radius:8px;border:1px solid #ccc;}

.card{background:white;padding:15px;border-radius:10px;box-shadow:0 2px 10px rgba(0,0,0,.1);margin-bottom:10px;}

table{width:100%;border-collapse:collapse;}
th,td{border:1px solid #ddd;padding:8px;text-align:center;}
th{background:#ff9800;color:white;}

.bar-container{background:#eee;height:20px;border-radius:10px;}
.bar{height:100%;width:0;background:#ff9800;border-radius:10px;transition:1s;}

.whatsapp{position:fixed;bottom:20px;right:20px;background:#25D366;padding:15px;border-radius:50%;color:white;cursor:pointer;}
</style>
</head>

<body>

<!-- LOGIN -->
<div id="loginPage" style="max-width:400px;margin:120px auto;background:white;padding:30px;border-radius:10px;">
<h2>Login Administrador</h2>
<input id="user" placeholder="Usuário">
<input id="pass" type="password" placeholder="Senha">
<button onclick="login()">Entrar</button>
</div>

<div id="app" class="hidden">

<nav>
<a href="#sobre">Sobre</a>
<a href="#missao">Missão</a>
<a href="#credito">Crédito</a>
<a href="#requisitos">Requisitos</a>
<a href="#pagamento">Pagamento</a>
<a href="#simulador">Simulador</a>
<a href="#pedido">Pedido</a>
<a href="#contactos">Contactos</a>
<a href="#admin">Painel</a>
</nav>

<header>
<h1>Tinhico Microcrédito PRO</h1>
<p>Para Uma Vida Melhor</p>
</header>

<section id="sobre">
<h2>Sobre Nós</h2>
<p>A Tinhico Microcrédito é uma instituição financeira especializada em fornecer empréstimos rápidos, seguros e acessíveis.</p>
</section>

<section id="missao">
<h2>Missão</h2>
<p>Empoderar microempreendedores através de acesso rápido ao crédito.</p>
<h2>Visão</h2>
<p>Ser referência regional até 2035.</p>
<h2>Valores</h2>
<ul>
<li>Ética</li>
<li>Transparência</li>
<li>Sustentabilidade</li>
</ul>
</section>

<section id="credito">
<h2>Crédito Rápido & Seguro</h2>
<p>Empréstimos rápidos com taxa de 30% e duração de 30 dias.</p>
</section>

<section id="requisitos">
<h2>Requisitos</h2>
<ul>
<li>B.I</li>
<li>NUIT</li>
<li>Declaração</li>
<li>Extrato 3 meses</li>
<li>Garantia</li>
</ul>
</section>

<section id="pagamento">
<h2>Métodos de Pagamento</h2>
<ul>
<li>30 dias</li>
<li>Juros 30%</li>
<li>Diário / Semanal / Mensal</li>
</ul>
</section>

<section id="simulador">
<h2>Simulador Diário</h2>
<input id="valorD">
<button onclick="simularD()">Simular</button>
<div id="resD"></div>
<div class="bar-container"><div id="barD" class="bar"></div></div>

<h2>Simulador Semanal</h2>
<input id="valorS">
<button onclick="simularS()">Simular</button>
<div id="resS"></div>
<div class="bar-container"><div id="barS" class="bar"></div></div>

<h2>Simulador Mensal</h2>
<input id="valorM">
<button onclick="simularM()">Simular</button>
<div id="resM"></div>
</section>

<section id="pedido">
<h2>Pedido</h2>
<input id="nome" placeholder="Nome">
<input id="telefone" placeholder="Telefone">
<input id="valorPedido" placeholder="Valor">
<button onclick="whatsapp()">Enviar</button>
</section>

<section id="contactos">
<h2>Contactos</h2>

<div class="card">📞 853908255</div>
<div class="card">📧 tinhicomicrocredito@gmail.com</div>
<div class="card">
📍 Av. das Indústrias, Bairro da Liberdade<br>
Talhão 758/A da Parcela 707<br>
Cidade da Matola
</div>

</section>

<section id="admin">
<h2>Painel Financeiro</h2>

<div class="card">
Total Emprestado: <span id="te"></span><br>
Total Recebido: <span id="tr"></span><br>
Lucro: <span id="lucro"></span>
</div>

<h2>Clientes</h2>
<input id="cn" placeholder="Nome">
<input id="ct" placeholder="Telefone">
<input id="cv" placeholder="Valor">
<button onclick="add()">Registrar</button>

<table>
<tr><th>Nome</th><th>Valor</th><th>Total</th><th>Pago</th><th>Saldo</th><th>Status</th><th>Ação</th></tr>
<tbody id="lista"></tbody>
</table>

</section>

<footer>© 2026 Tinhico</footer>

</div>

<div class="whatsapp" onclick="window.open('https://wa.me/258853908255')">WA</div>

<script>
function login(){
if(user.value==='admin' && pass.value==='1234'){
loginPage.classList.add('hidden');
app.classList.remove('hidden');
load();
}else alert('Erro');
}

function simularD(){
let v=+valorD.value;
let total=v*1.3;
let d=total/30;
resD.innerHTML=${d.toFixed(2)} MZN/dia<br><button onclick="pedir(${v})">WhatsApp</button>;
barD.style.width='30%';
}

function simularS(){
let v=+valorS.value;
let total=v*1.3;
let s=total/4;
resS.innerHTML=${s.toFixed(2)} MZN/semana<br><button onclick="pedir(${v})">WhatsApp</button>;
barS.style.width='30%';
}

function simularM(){
let v=+valorM.value;
let total=v*1.3;
resM.innerHTML=${total.toFixed(2)} MZN total<br><button onclick="pedir(${v})">WhatsApp</button>;
}

function pedir(v){
window.open(https://wa.me/258853908255?text=Quero ${v} MZN);
}

function whatsapp(){
window.open(https://wa.me/258853908255?text=Pedido de empréstimo);
}

function add(){
let clientes=JSON.parse(localStorage.cl||"[]");
let v=+cv.value;
clientes.push({n:cn.value,t:ct.value,v:v,total:v*1.3,p:0});
localStorage.cl=JSON.stringify(clientes);
load();
}

function load(){
let c=JSON.parse(localStorage.cl||"[]");
let html='',te=0,tr=0;
c.forEach((x,i)=>{
let saldo=x.total-x.p;
let st=saldo<=0?'Pago':'Dívida';
te+=x.v; tr+=x.p;
html+=`<tr>
<td>${x.n}</td>
<td>${x.v}</td>
<td>${x.total.toFixed(2)}</td>
<td>${x.p}</td>
<td>${saldo.toFixed(2)}</td>
<td>${st}</td>
<td><button onclick="pagar(${i})">Pagar</button></td>
</tr>`;
});
lista.innerHTML=html;
teSpan=te.toFixed(2); trSpan=tr.toFixed(2);
document.getElementById('te').innerHTML=teSpan;
document.getElementById('tr').innerHTML=trSpan;
document.getElementById('lucro').innerHTML=(te*0.3).toFixed(2);
}

function pagar(i){
let c=JSON.parse(localStorage.cl);
let v=prompt("Valor pago");
c[i].p+=+v;
localStorage.cl=JSON.stringify(c);
load();
}

document.querySelectorAll('section').forEach(el=>{
window.addEventListener('scroll',()=>{
if(el.getBoundingClientRect().top<window.innerHeight-50){
el.classList.add('show');
}
});
});
</script>

</body>
</html>
