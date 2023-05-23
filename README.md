<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter&family=Roboto&display=swap" rel="stylesheet"> 

    <link rel="stylesheet" href="style.css">
    <title>Encriptador</title>
</head>
<body>
    <header>
        <img src="Imagens/logoAlura.png" alt="logo da Alura">
    </header>  
    <main>
    
        <section>
            <textarea class="text-area" cols="41" rows="4" placeholder="Digite seu texto"></textarea>

            <div class="informacao">
                <h6>Apenas letras minúsculas e sem acento</h6>
            </div>

            <div class="botoes">
                <button class="btn-encriptar" onclick="btnEncriptar()">Criptografar</button>
                <button class="btn-desencriptar" onclick="btnDesencriptar()" >Descriptografar</button>
            </div>
        </section>

        <section>
            <textarea class="mensagem" cols="20" rows="10"></textarea> 
            <button class="btn-copiar">Copiar</button>
        </section>

    </main>
    <script src="script.js"></script>
</body>
</html>


* {
    background-color: #FFFFFF;
    font-family: 'Inter', sans-serif;
    font-weight: 400;
    font-size:25px;
    line-height: 150%;
}


.logoAlura {
    margin-left: 10px;
    padding-top: 10px;
    width: 2%;
}

main {
    display: flex;
    margin-bottom: 50px;
    margin-left: 80px;
}

.text-area {
    border-width: 25px;
    border: #343A40;
    color: #343A40;
    margin-top: 90px;
    text-transform: lowercase;
}

::placeholder { color: #343A40}
    .text-area:focus; {
        outline: none;
    }

.mensagem {
    background: #FF6347;
    background-image: url(/Imagens/boneco.png);
    background-repeat: no-repeat;
    border: none;
    border-radius: 24px;
    color: #008B8B;
    margin-left: 98px;
    margin-top: 20px;
    padding-left: 20px;
    position: fixed;
}
.mensagem:focus {
    outline: none;
}

.botoes {
    display: flex;
    margin-top: 18px;
}

.btn-desencriptar {
    background: #FF6347;
    border: 1px solid #FF6347;
    border-radius: 24px;
    color: #343A40;
    cursor: pointer;
    height: 67px;
    margin-left: 30px;
    width: 328px;
}

.btn-encriptar {
    background: #FF6347;
    border: 1px solid #FF6347;
    border-radius: 24px;
    color: #343A40;
    cursor: pointer;
    height: 67px;
    margin-left: 30px;
    width: 328px;
}

.btn-copiar {
    background: #FF6347;
    border: 1px solid #FF6347;
    border-radius: 24px;
    color: #343A40;
    cursor: pointer;
    height: 67px;
    margin-left: 108px;
    margin-top: 402px;
    position: absolute;
    width: 336px;
}

.informacao {
    color: #343A40;
    font-size: 18px;
}

const textArea= document.querySelector(".text-area");
const mensagem = document.querySelector(".mensagem");

// A letra "e" é convertida para "enter"
// A letra "i" é convertida para "imes"
// A letra "a" é convertida para "ai"
// A letra "o" é convertida para "ober"
// A letra "u" é convertida para "ufat"

function btnEncriptar() {
    const textoEncriptado = encriptar(textArea.value);
    mensagem.value = textoEncriptado;
    textArea.value = "";
}

function encriptar(stringEncriptada) {

    let matrizCodigo = [["e", "enter"] , ["i","imes"],["a","ai"], ["o", "ober"],["u", "ufat"]];
    stringEncriptada = stringEncriptada.toLowerCase();

    for(let i =0; i < matrizCodigo.length; i++) {
        if(stringEncriptada.includes(matrizCodigo[i][0])) {
            stringEncriptada = stringEncriptada.replaceAll(matrizCodigo[i][0], matrizCodigo[i][1]);

        }
    }

    return stringEncriptada;
}



function btnDesencriptar() {
    const textoDesencriptado = Desencriptar(textArea.value);
    mensagem.value = textoDesencriptado;
    textArea.value = "";
}

function desencriptar(stringDesencriptada) {

    let matrizCodigo = [["e", "enter"] , ["i","imes"],["a","ai"], ["o", "ober"],["u", "ufat"]];
    stringDesencriptada = stringDsencriptada.toLowerCase();

    for(let i =0; i < matrizCodigo.length; i++) {
        if(stringDesencriptada.includes(matrizCodigo[i][1])) {
            stringDesencriptada = stringDesencriptada.replaceAll(matrizCodigo[i][1], matrizCodigo[i][0]);

        }
    }

    return stringDesencriptada;
}

