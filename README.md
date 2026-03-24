<!DOCTYPE html>
<html lang="pt">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Tinhico Microcrédito E.I</title>

<style>
body{font-family:Arial,sans-serif;margin:0;background:#f2f2f7;}
nav{background:#1f1f1f;padding:15px;text-align:center;position:fixed;width:100%;top:0;z-index:1000;box-shadow:0 4px 20px rgba(0,0,0,0.3);border-bottom-left-radius:15px;border-bottom-right-radius:15px;}
nav a{color:white;margin:10px;text-decoration:none;font-weight:bold;}
nav a:hover{color:#ff9800;}

header{margin-top:70px;background:#ff9800;color:white;text-align:center;padding:60px;border-radius:0 0 30px 30px;}
header button{margin-top:15px;}

section{padding:40px;max-width:900px;margin:auto;opacity:0;transform:translateY(50px);transition:1s;border-radius:15px;background:white;margin-bottom:20px;}
section.show{opacity:1;transform:translateY(0);}

h2{color:#ff9800;}
ul{line-height:1.8;}

input{width:100%;padding:14px;margin:10px 0;border-radius:10px;border:1px solid #ccc;font-size:16px;}
button{padding:14px;background:#ff9800;border:none;color:white;border-radius:10px;cursor:pointer;font-weight:bold;font-size:16px;}
button:hover{background:#e68900;transform:scale(1.05);}

footer{background:#222;color:white;text-align:center;padding:20px;border-top-left-radius:20px;border-top-right-radius:20px;}

.card{background:white;padding:20px;border-radius:15px;margin-bottom:15px;box-shadow:0 2px 10px rgba(0,0,0,0.1);}

.whatsapp{position:fixed;bottom:20px;right:20px;background:#25D366;color:white;padding:18px;border-radius:50%;cursor:pointer;font-weight:bold;font-size:16px;}
</style>
</head>

<body>

<nav>
<a href="#sobre">Sobre</a>
<a href="#missao">Missão</a>
<a href="#credito">Crédito</a>
<a href="#requisitos">Requisitos</a>
<a href="#pagamento">Pagamento</a>
<a href="#simulador">Simulador</a>
<a href="#pedido">Pedido</a>
<a href="#contactos">Contactos</a>
</nav>

<header>
<h1>Tinhico Microcrédito E.I</h1>
<p>Para Uma Vida Melhor</p>
<button onclick="ligarAgora()">📞 Falar Agora</button>
</header>

<section id="sobre">
<h2>Sobre Nós</h2>
<p>A Tinhico Microcrédito E.I é uma instituição financeira especializada em fornecer empréstimos rápidos, seguros e acessíveis para indivíduos e pequenas empresas.</p>
</section>

<section id="missao">
<h2>Missão</h2>
<p>Empoderar microempreendedores através de acesso rápido ao crédito.</p>
<h2>Visão</h2>
<p>Ser referência em microfinanças até 2035.</p>
<h2>Valores</h2>
<ul>
<li>Ética</li>
<li>Transparência</li>
<li>Sustentabilidade</li>
</ul>
</section>

<section id="credito">
<h2>Crédito Rápido & Seguro</h2>
<p>Oferecemos empréstimos rápidos com aprovação simples, taxa transparente e pagamento flexível.</p>
</section>

<section id="requisitos">
<h2>Requisitos para Empréstimo</h2>
<ul>
<li>B.I</li>
<li>NUIT</li>
<li>Declaração do bairro</li>
<li>Extracto bancário dos últimos 3 meses</li>
<li>Garantia ou avalista</li>
</ul>
</section>

<section id="pagamento">
<h2>Métodos de Pagamento</h2>
<ul>
<li>Duração do empréstimo: 30 dias</li>
<li>Taxa única de juros: 30%</li>
<li>Pagamento diário</li>
<li>Pagamento semanal</li>
<li>Pagamento mensal</li>
</ul>
</section>

<section id="simulador">
<h2>Simulador de Pagamento Diário</h2>
<input type="number" id="valorD" placeholder="Valor do empréstimo">
<button onclick="simularDiario()">Simular</button>
<div id="resD" style="font-weight:bold;margin-top:10px;"></div>

<hr>

<h2>Simulador de Pagamento Semanal</h2>
<input type="number" id="valorS" placeholder="Valor do empréstimo">
<button onclick="simularSemanal()">Simular</button>
<div id="resS" style="font-weight:bold;margin-top:10px;"></div>

<hr>

<h2>Simulador de Pagamento Mensal</h2>
<input type="number" id="valorM" placeholder="Valor do empréstimo">
<button onclick="simularMensal()">Simular</button>
<div id="resM" style="font-weight:bold;margin-top:10px;"></div>
</section>

<section id="pedido">
<h2>Pedido de Empréstimo</h2>
<input id="nome" placeholder="Nome">
<input id="telefone" placeholder="Telefone">
<input id="valorPedido" placeholder="Valor desejado">
<button onclick="whatsapp()">Enviar Pedido</button>
</section>

<section id="contactos">
<h2>Contactos</h2>

<div class="card">
<p><strong>📞 Telefone:</strong> 853908255</p>
<button style="width:100%;margin-top:10px;" onclick="ligarAgora()">📞 Ligar Agora</button>
</div>

<div class="card">
<p><strong>📧 Email:</strong> tinhicomicrocredito@gmail.com</p>
</div>

<div class="card">
<p><strong>📍 Endereço:</strong><br>
Av. das Indústrias, Bairro da Liberdade<br>
Talhão 758/A da Parcela 707, Andar R/C<br>
Cidade da Matola
</p>
</div>

</section>

<footer>
© 2026 Tinhico Microcrédito E.I
</footer>

<div class="whatsapp" onclick="window.open('https://wa.me/258853908255')">WA</div>

<script>
function ligarAgora(){
  window.location.href="tel:+258853908255";
}

function simularDiario(){
  let v=parseFloat(document.getElementById("valorD").value);
  if(isNaN(v)||v<=0){ alert("Insira um valor válido"); return; }
  let total=v*1.30;
  let diario=total/30;
  document.getElementById("resD").innerHTML=`Para ${v.toFixed(2)} MZN, paga ${diario.toFixed(2)} MZN/dia. Total: ${total.toFixed(2)} MZN.`;
}

function simularSemanal(){
  let v=parseFloat(document.getElementById("valorS").value);
  if(isNaN(v)||v<=0){ alert("Insira um valor válido"); return; }
  let total=v*1.30;
  let semanal=total/4;
  document.getElementById("resS").innerHTML=`Para ${v.toFixed(2)} MZN, paga ${semanal.toFixed(2)} MZN/semana. Total: ${total.toFixed(2)} MZN.`;
}

function simularMensal(){
  let v=parseFloat(document.getElementById("valorM").value);
  if(isNaN(v)||v<=0){ alert("Insira um valor válido"); return; }
  let total=v*1.30;
  document.getElementById("resM").innerHTML=`Para ${v.toFixed(2)} MZN, paga ${total.toFixed(2)} MZN após 30 dias.`;
}

function whatsapp(){
  let nome=document.getElementById("nome").value;
  let tel=document.getElementById("telefone").value;
  let valor=document.getElementById("valorPedido").value;
  if(!nome||!tel||!valor){ alert("Preencha todos os campos"); return; }
  let msg=`Olá, sou ${nome}, telefone ${tel} e quero um empréstimo de ${valor} MZN`;
  window.open("https://wa.me/258853908255?text="+encodeURIComponent(msg));
}

// Animação ao scroll
const faders=document.querySelectorAll('section');
window.addEventListener('scroll',()=>{
  faders.forEach(el=>{
    const pos=el.getBoundingClientRect().top;
    if(pos<window.innerHeight-100){
      el.classList.add('show');
    }
  });
});
</script>

</body>
</html
