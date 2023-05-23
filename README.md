# DesafioAluraCriptografia

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
