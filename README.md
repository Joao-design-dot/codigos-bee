<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>PontoEdu - Histórico de Registros</title>
    <link rel="stylesheet" href="style.css">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
</head>
<body>
    
    <header class="main-header">
        <div class="header-left">
            <div class="logoSRD">
                <strong>SRD</strong>
            </div>
            <nav class="nav-links">
            </nav>
        </div>
        <div class="header-right">
            

            <div class="user-profile">
                <i class="fas fa-user-circle"></i>
                <div>
                    <strong>Vinícius Brito</strong>
                    <small>docente</small>
                </div>
            </div>
            
     <div class="btn-header btn-filled"><a href="index.html">SAIR</a>
        </div>
    </header>

    <div class="img">
               <img src="IMAGES/Adobe Express - file (1).png" alt="">
    </div>

    <div class="dashboard-container">
        <aside class="sidebar">
            <div class="logo">
                <i class="far fa-clock"></i>
                <div>
                    <strong>Docente</strong>
                    <small>Registro de Professores</small>
                </div>
            </div>

            <nav class="navigation">
                <h4>NAVEGAÇÃO</h4>
                <ul>
                    <li class="ponto">
                        <i class="fas fa-th-large"></i>
                        <a href="tela.usuariodocente.html">Ponto </a>
                    </li>
                    <li class="active">
                        <i class="fas fa-history"></i>
                         <a href="histórico.html">Histórico</a>
                    </li>
                    <li class="senha">
                        <i class="fas fa-history"></i>
                         <a href="confirmacao_redefinir_senha.html">Senha</a>
                    </li>
                </ul>
            </nav>

    
        </aside>

        <main class="main-content">
            <div class="header-actions">
                <div>
                    <h1>Histórico de Registros</h1>
                    <p>Consulte todos os registros de ponto realizados</p>
                </div>
     

            <div class="container">
               <h2>Nova Senha</h2>
               <input type="text" placeholder="Login" >
  
  <!-- Ícones Font Awesome -->
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">

  <style>
    /* Reset e fonte padrão */
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    }

    body {
      background-color: #fff;
      padding: 40px;
      color: #333;
    }

    h3 {
      margin-bottom: 8px;
      color: #222;
    }

    .senha-container {
      position: relative;
      margin-bottom: 16px;
      max-width: 400px;
    }

    input[type="password"],
    input[type="text"] {
      width: 100%;
      padding: 12px 40px 12px 12px;
      font-size: 16px;
      border: 1px solid #ccc;
      border-radius: 6px;
      transition: border-color 0.2s;
    }

    input:focus {
      border-color: #0057d9;
      outline: none;
    }

    .senha-container i {
      position: absolute;
      right: 12px;
      top: 50%;
      transform: translateY(-50%);
      cursor: pointer;
      font-size: 18px;
      color: #666;
      user-select: none;
    }

    .validacao {
      margin: 10px 0 24px;
      max-width: 500px;
    }

    .validacao span {
      display: flex;
      align-items: center;
      font-size: 14px;
      margin: 4px 0;
      color: red;
      transition: color 0.3s;
    }

    .validacao span.verificado {
      color: green;
    }

    .validacao span::before {
      content: "✔";
      margin-right: 8px;
    }

    button {
      padding: 12px 24px;
      background-color: #0057d9;
      color: white;
      border: none;
      border-radius: 6px;
      font-size: 16px;
      cursor: pointer;
      transition: background-color 0.3s;
    }

    button:hover {
      background-color: #003eaa;
    }

    a {
      display: inline-block;
      margin-top: 20px;
      color: #0057d9;
      text-decoration: none;
      font-size: 14px;
    }

    a:hover {
      text-decoration: underline;
    }
  </style>
</head>
<body>

  <h3>Nova senha</h3>
  <div class="senha-container">
    <input type="password" id="senha" placeholder="Digite sua senha" oninput="validarSenha()">
    <i class="fa-solid fa-eye" id="toggleSenha" onclick="alternarSenha('senha', this)"></i>
  </div>

  <div class="validacao" id="requisitos">
    <span id="minimo">A senha deve ter mínimo 8 e máximo 70 caracteres.</span>
    <span id="maiuscula">A senha deve ter pelo menos uma letra maiúscula.</span>
    <span id="minuscula">A senha deve ter pelo menos uma letra minúscula.</span>
    <span id="simbolo">A senha deve ter pelo menos um símbolo. Ex: '! # $ % & + - / : ; , ? @ \ |</span>
    <span id="numero">A senha deve ter pelo menos um número.</span>
  </div>

  <h3>Repita a senha</h3>
  <div class="senha-container">
    <input type="password" id="senhaRepetida" placeholder="Repita sua senha">
    <i class="fa-solid fa-eye" id="toggleSenhaRepetida" onclick="alternarSenha('senhaRepetida', this)"></i>
  </div>

  <button onclick="concluir()">Concluir</button>
  <a href="#">Voltar</a>

  <script>
    function validarSenha() {
      const senha = document.getElementById('senha').value;

      atualizarEstado('minimo', senha.length >= 8 && senha.length <= 70);
      atualizarEstado('maiuscula', /[A-Z]/.test(senha));
      atualizarEstado('minuscula', /[a-z]/.test(senha));
      atualizarEstado('numero', /[0-9]/.test(senha));
      atualizarEstado('simbolo', /[!@#\$%\^\&*\)\(+=._\-\/:;,?\\|]/.test(senha));
    }

    function atualizarEstado(id, condicao) {
      const item = document.getElementById(id);
      if (condicao) {
        item.classList.add('verificado');
      } else {
        item.classList.remove('verificado');
      }
    }

    function alternarSenha(idCampo, icone) {
      const campo = document.getElementById(idCampo);
      if (campo.type === 'password') {
        campo.type = 'text';
        icone.classList.remove('fa-eye');
        icone.classList.add('fa-eye-slash');
      } else {
        campo.type = 'password';
        icone.classList.remove('fa-eye-slash');
        icone.classList.add('fa-eye');
      }
    }

    function concluir() {
      const senha = document.getElementById('senha').value;
      const repetir = document.getElementById('senhaRepetida').value;

      if (senha !== repetir) {
        alert("As senhas não coincidem.");
        return;
      }

      alert("Senha definida com sucesso!");
    }
  </script>

</body>
</html>

          </div>
        </main>
    </div>
    <script src="script.js"></script>
</body>
</html>

<style>
    /* Variáveis de Cores (Baseadas no seu design) */
:root {
    --primary-bg: #ffffff; /* Fundo principal claro (parecido com o das imagens) */
    --sidebar-bg: #fff;  
    --card-bg: #fff;
    --text-dark: #1f2937; /* Tom escuro para títulos */
    --text-medium: #4b5563; /* Tom médio para textos */
    --highlight-orange: #ff7f50; /* Laranja da navegação ativa e botões */
    --highlight-blue: #0080ff; /* Azul para alguns ícones/detalhes */
    --badge-green: #45b38d; /* Verde para 'Entrada' */
    --badge-red: #ff6347; /* Vermelho para 'Saída' */
    --header-blue: #ff834a; /* Azul escuro do título principal */
}

* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: Arial, sans-serif;
}

body {
    background-color: var(--primary-bg);
    color: var(--text-medium);
    line-height: 1.6;
}

.active{
    box-shadow: none;
}


.logo {
    display: flex;
    align-items: center;
    gap: 10px;
    margin-bottom: 30px;
    color: var(--text-dark);
}


.sidebar ul {
    list-style: none;
}

.sidebar ul li {
    display: flex;
    align-items: center;
    gap: 10px;
    padding: 10px;
    margin: 5px 0;
    border-radius: 8px;
    cursor: pointer;
    transition: background-color 0.2s, color 0.2s;
    font-weight: 500;
}

.sidebar ul li:hover {
    background-color: #f0f0f0;
    color: white;
}


.sidebar ul li.active i {
    color: #fffafa;
    box-shadow: none;
}

.sidebar ul li.ponto i {
    color: #fffafa;
}

.sidebar ul li.senha i {
    color: #fffafa;
}

.sidebar ul li i {
    font-size: 1em;
    width: 20px;
    text-align: center;
    color: white;
}

.user-profile {
    color: #ffffff;
    display: flex;
    align-items: center;
    gap: 10px;
    padding-top: 20px;
    border-top: 1px solid #ffffff;
    
}

.user-profile i {
    font-size: 30px;
   color: #ffffff;
}

.user-profile strong {
    font-size: 1em;
    color: var(--text-dark);
}

.user-profile small {
    display: block;
    color: var(--text-medium);
    font-size: 0.8em;
}

/* 3. Main Content (Específico da Tela) */
.main-content {
    flex-grow: 1;
    padding: 30px;
}

.header-actions {
    display: flex;
    justify-content: space-between;
    align-items: flex-end;
    margin-bottom: 30px;
    color: #13093b;
}

.header-actions h1 {
    font-size: 2.2em;
    font-weight: bold;
    color: var(--header-blue);
    margin-bottom: 5px;
    color: #13093b;
}

.header-actions p {
    color: var(--text-medium);
    color: #13093b;
}


.filter-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 20px;
    border: #13093b;
}

.filter-group {
    display: flex;
    flex-direction: column;
    border: #13093b;
}

.filter-group label {
    font-size: 0.9em;
    font-weight: 500;
    color: var(--text-medium);
    margin-bottom: 5px;
    display: flex;
    align-items: center;
    gap: 5px;
    color: #2d093b;
}

.filter-group input {
    padding: 10px;
    border: 1px solid #4f008f;
    border-radius: 6px;
    font-size: 1em;
    transition: border-color 0.2s;
    color: #27093b;
}

.filter-group input:focus {
    outline: none;
    border-color: var(#2f093b);
    color: #2b093b;
}

/* 5. Tabela */
.table-card {
    padding: 0;
}

#registros-table {
    width: 100%;
    border-collapse: collapse;
}

#registros-table th, #registros-table td {
    padding: 15px 20px;
    text-align: left;
    border-bottom: 1px solid #eee;
}

#registros-table thead {
    background-color: #f9fafb;
}

#registros-table th {
    font-weight: 600;
    color: var(--text-dark);
    font-size: 0.9em;
}

#registros-table tbody tr:hover {
    background-color: #f5f5f5;
}

.badge {
    display: inline-flex;
    align-items: center;
    padding: 5px 10px;
    border-radius: 50px;
    font-size: 0.8em;
    font-weight: 600;
    color: white;
}

.badge i {
    font-size: 0.7em;
    margin-right: 5px;
}

.badge-green {
    background-color: var(--badge-green);
}

.badge-red {
    background-color: var(--badge-red);
}

.no-data-message {
    text-align: center;
    padding: 50px 20px;
    color: var(--text-medium);
}

/* Responsividade (Bônus) */
@media (max-width: 768px) {
    .dashboard-container {
        flex-direction: column;
    }

    .sidebar {
        width: 100%;
        height: auto;
        box-shadow: 0 2px 10px rgba(0, 0, 0, 0.05);
    }

    .sidebar .navigation, .sidebar .management {
        margin-bottom: 10px;
    }
    
    .sidebar ul {
        display: flex;
        flex-wrap: wrap;
        gap: 5px;
    }
    
    .sidebar ul li {
        flex-basis: auto;
    }

    .header-actions {
        flex-direction: column;
        align-items: flex-start;
        gap: 15px;
    }

    .filter-grid {
        grid-template-columns: 1fr;
    }
}

/* Estilo de Impressão */
@media print {
    .sidebar, .header-actions, .filters-card {
        display: none !important;
    }
    body {
        background-color: white;
    }
    .main-content {
        padding: 0;
    }
    .card {
        box-shadow: none;
        border: 1px solid #ffffff;
    }
}


a{
    text-decoration: none;
    color: #ffffff;
}    

.main-header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 16px 32px;
    background-color: var(--secondary-dark);
    border-bottom: 1px solid var(--border-color-dark);
    position: relative;
    z-index: 10;
    background-color: #230044;
}
        /* Variáveis de Cores */
:root {
    --primary-color: #ffffff; /* Fundo principal claro */
    --secondary-color: #fff;  /* Fundo da Sidebar e Cartões */
    --text-color: #333;
    --text-light-color: #666;
    --highlight-color: #2196F3; /* Cor principal de destaque (azul) */
    --orange-card: #ff7f50; /* Cor do card 1 */
    --blue-card: #1e90ff;   /* Cor do card 2 */
    --green-card: #45b38d;  /* Cor do card 3 */
    --red-card: #ff6347;    /* Cor do card 4 */
    --sidebar-bg: #fff;
    --sidebar-active-bg: #2196F3; /* Cor de fundo do item ativo na sidebar */
    --sidebar-active-text: #fff;  /* Cor do texto do item ativo na sidebar */
}

* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: Arial, sans-serif; /* Use a fonte da sua preferência */
}

body {
    background-color: var(--primary-color);
    color: var(--text-color);
    line-height: 1.6;
}

/* 1. Dashboard Container (Layout Principal) */
.dashboard-container {
    display: flex;
    min-height: 100vh;
}

/* 2. Sidebar (Barra Lateral) */
.sidebar {
    width: 250px;
    background-color: #230044;
    padding: 20px;
    box-shadow: 2px 0 5px rgba(0, 0, 0, 0.05);
    display: flex;
    flex-direction: column;
    justify-content: space-between; /* Para empurrar o perfil do usuário para o fundo */
}

.logo {
    display: flex;
    align-items: center;
    gap: 10px;
    margin-bottom: 30px;
    color: var(--text-color);

}

.logoSRD{
    font-size: 3.2em;
    font-weight: 600;
    color: #fff;
}

.logo i {
    font-size: 24px;
    color: var(--highlight-color);
    color:#ad81ff;
}

.logo strong {
    font-size: 1.2em;
    font-weight: 600;
    color: #fff;
}

.logo small {
    display: block;
    color: var(--text-light-color);
    font-size: 0.8em;
    color: #fff;
}

.navigation H4{
    color: #ffffff;
    margin-top: -840px;
}

.management {
    margin-bottom: 30px;
    color: #ffffff;
}

.sidebar h4 {
    color:#ffffff;
    font-size: 0.75em;
    font-weight: 500;
    margin-bottom: 10px;
    padding-left: 10px;
}

.sidebar ul {
    list-style: none;
}

.sidebar ul li {
    display: flex;
    align-items: center;
    gap: 10px;
    padding: 10px;
    margin: 5px 0;
    border-radius: 8px;
    cursor: pointer;
    transition: background-color 0.2s, color 0.2s;
    color: var(--text-light-color);
    font-weight: 500;
}

.sidebar ul li:hover {
    background-color: #5800bd75;
}

.sidebar ul li.senha {
        background-color:#ad81ff;
          color: #ffffff;
    box-shadow: 0 4px 8px rgb(120, 80, 173); /* Sombra para destaque */
}



.sidebar ul li.senhai {
    background-color:#ad81ff;
}

.sidebar ul li i {
    font-size: 1em;
    width: 20px;
    text-align: center;
    color: var(--text-light-color);
}

/* Perfil do Usuário */
.user-profile {
    display: flex;
    align-items: center;
    gap: 10px;
    padding-top: 20px;
    border-top: 1px solid #eee;
    margin-top: auto; /* Empurra para o final */
}

.user-profile i {
    font-size: 30px;
    color: var(--text-light-color);
}

.user-profile strong {
    font-size: 1em;
}

.user-profile small {
    display: block;
    color: var(--text-light-color);
    font-size: 0.8em;
}

/* 3. Main Content (Conteúdo Principal) */
.main-content {
    flex-grow: 1;
    padding: 30px;
    color: #230044;
}

header h1 {
    font-size: 2em;
    margin-bottom: 5px;
}

header p {
    color: var(--text-light-color);
    margin-bottom: 30px;
    color: #210638;
}

/* 4. Status Cards (Cartões de Métricas) */
.status-cards {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 20px;
    margin-bottom: 30px;
}

.card {
    background-color: var(--secondary-color);
    padding: 20px;
    border-radius: 10px;
    box-shadow: 0 2px 4px rgb(51, 8, 92);
    display: flex;
    align-items: center;
    gap: 15px;
}

.icon-container {
    width: 50px;
    height: 50px;
    border-radius: 50%;
    display: flex;
    justify-content: center;
    align-items: center;
}

.icon-container i {
    color: var(--secondary-color);
    font-size: 20px;
}


.card .info {
    display: flex;
    flex-direction: column;
    color: #000000;
}

.card .info strong {
    font-size: 0.9em;
    color: var(--text-light-color);
    font-weight: 500;
    color: #210057;
}

.card .info .value {
    font-size: 1.8em;
    font-weight: 700;
    line-height: 1.2;
}

.card .info small {
    font-size: 0.7em;
    color: var(--text-light-color);
    color: #210057;
}

/* 5. Seções Inferiores */
.live-section, .registered-section {
    background-color: var(--secondary-color);
    padding: 20px;
    border-radius: 10px;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.05);
    margin-bottom: 20px;
}

.section-header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding-bottom: 15px;
    margin-bottom: 15px;
    border-bottom: 1px solid #ffffff;
}

.section-header h2 {
    font-size: 1.1em;
    font-weight: 600;
    color: var(--text-color);
}

.section-header h2 i {
    color: var(--green-card); /* Ícone de check verde */
    margin-right: 5px;
}

.status-tag {
    font-size: 0.8em;
    padding: 5px 10px;
    border-radius: 20px;
    font-weight: 600;
    color: var(--secondary-color);
}

.status-tag.present {
    background-color: var(--green-card);
}

.status-tag.active-teachers {
    background-color: var(--orange-card);
}

/* Mensagem de Sem Dados */
.no-data-message {
    text-align: center;
    padding: 50px 0;
    color: var(--text-light-color);
}

.no-data-message i {
    font-size: 40px;
    color: #ffffff;
    margin-bottom: 10px;
}

.no-data-message p {
    font-size: 1em;
    margin-bottom: 5px;
}

.no-data-message small {
    font-size: 0.8em;
    display: block;
}

/* Ajuste para a segunda seção */
.registered-section .section-header h2 i {
    color: var(--orange-card); /* Ícone de professores laranja */
}

</style>
</style>
























 
 
<style>
 
body {
 font-family: Arial, sans-serif;
 background-color: #180438;
 padding: 20px;
 margin: 0;
}
 
.container {
 background-color: rgb(255, 255, 255);
 max-width: 1000px;
 margin: auto;
 padding: 40px;
 border-radius: 20px;
 box-shadow: 0 0 40px #949494;
 margin-top: 200px;
}
 
h2, h3, h4 {
 text-align: center;
 color: #2f0861;
}
 
img {
 display: block;
 margin: 10px auto;
 border-radius: 50%;
}
 
input[type="text"],
input[type="password"],
input[type="search"] {
 width: 30%;
 padding: 10px;
 margin: 8px 0;
 border: 1px solid #7c7c7c;
 border-radius: 5px;
}
 
button {
 padding: 10px;
 margin: 10px 5px 0 0;
 border: none;
 border-radius: 5px;
 cursor: pointer;
}
 
.confirm {
 background-color: #4d0f80;
 color: white;
 margin-left: 250px;
}
 
ul, .faq, .uploads {
 padding: 0;
 margin: 10px 0;
 list-style: none;
}
 
li, .faq p, .toggle {
 padding: 10px;
 margin-bottom: 6px;
 border-radius: 5px;
}
 
.toggle {
 display: flex;
 justify-content: space-between;
 align-items: center;
}

.img{
     margin-top: -350px;
     margin-left: 1200px;
     position: fixed;
}
img{
     width: 890px;
     margin-left: -1100px;
     margin-top: 457px;

}

</style>
