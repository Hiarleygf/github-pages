<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>para voce!!</title>
    <style>
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f0f2f5;
            transition: all 0.5s;
        }

        .container {
            max-width: 600px;
            margin: 30px auto;
            padding: 30px;
            background: white;
            border-radius: 15px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
            position: relative;
        }

        .overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0,0,0,0.85);
            display: none;
            justify-content: center;
            align-items: center;
            z-index: 100;
            animation: fadeIn 0.4s;
        }

        .overlay-content {
            background: white;
            padding: 30px;
            border-radius: 15px;
            text-align: center;
            max-width: 80%;
            animation: slideUp 0.5s forwards;
        }

        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        @keyframes slideUp {
            from { transform: translateY(20px); opacity: 0; }
            to { transform: translateY(0); opacity: 1; }
        }

        button {
            padding: 12px 30px;
            margin: 10px 5px;
            border: none;
            border-radius: 8px;
            font-size: 16px;
            cursor: pointer;
            transition: all 0.3s;
            font-weight: 600;
        }

        .btn-sim {
            background: #2ecc71;
            color: white;
        }

        .btn-nao {
            background: #e74c3c;
            color: white;
        }

        .btn-next {
            background: #3498db;
            color: white;
            margin-top: 20px;
        }

        .hidden {
            display: none;
        }

        .progress-bar {
            height: 5px;
            background: #ecf0f1;
            border-radius: 3px;
            margin-bottom: 20px;
        }

        .progress {
            height: 100%;
            background: #3498db;
            border-radius: 3px;
            width: 0%;
            transition: width 0.5s;
        }

        h2 {
            color: #2c3e50;
            margin-bottom: 20px;
        }

        img {
            max-width: 100%;
            border-radius: 10px;
            margin: 15px 0;
            box-shadow: 0 3px 10px rgba(0,0,0,0.1);
        }
    </style>
</head>
<body>
    <!-- Tela Principal - Pergunta 1 -->
    <div class="container" id="pergunta1">
        <div class="progress-bar">
            <div class="progress" id="progresso"></div>
        </div>
        <h2>Você tem um mapa?</h2>
        <img src="https://i.postimg.cc/2SSkYjgC/images-1.jpg" alt="Programação">
        
        <div>
            <button class="btn-sim" onclick="responder(true, 1)">nao porque</button>
            <button class="btn-nao" onclick="responder(false, 1)">clica no verde</button>
        </div>
    </div>

    <!-- Tela Principal - Pergunta 2 (oculta inicialmente) -->
    <div class="container hidden" id="pergunta2">
        <div class="progress-bar">
            <div class="progress" style="width: 50%"></div>
        </div>
        <h2>seu nome e tamara?</h2>
        <img src="https://i.postimg.cc/dtt3s9yM/download-4.jpg" alt="Projeto">
        
        <div>
            <button class="btn-sim" onclick="responder(true, 2)">nao porque</button>
            <button class="btn-nao" onclick="responder(false, 2)">encima</button>
        </div>
    </div>

    <!-- Tela Principal - Pergunta 3 (oculta inicialmente) -->
    <div class="container hidden" id="pergunta3">
        <div class="progress-bar">
            <div class="progress" style="width: 100%"></div>
        </div>
        <h2>me perdi dentro de mim mesmo</h2>
        <img src="https://i.postimg.cc/FKKw17xH/download-5.jpg" alt="Dicas">
        
        <div>
            <button class="btn-sim" onclick="responder(true, 3)">oque?</button>
            <button class="btn-nao" onclick="responder(false, 3)">encima</button>
        </div>
    </div>

    <!-- Overlay de Respostas -->
    <div class="overlay" id="overlay-resposta">
        <div class="overlay-content">
            <h2 id="resposta-titulo"></h2>
            <p id="resposta-texto"></p>
            <img id="resposta-imagem" style="max-height: 150px; display: none;">
            <button class="btn-next" onclick="proximaPergunta()">Continuar</button>
        </div>
    </div>

    <!-- Overlay Final -->
    <div class="overlay" id="overlay-final">
        <div class="overlay-content">
            <h2 style="color:#9b59b6">🎉 terminou gatinha!</h2>
            <p id="resultado-final"></p>
            <img src="https://source.unsplash.com/random/300x150/?celebration" style="max-height: 120px; margin: 15px 0;">
            <button class="btn-next" onclick="reiniciar()">quer repetir?</button>
        </div>
    </div>

    <script>
        // Configuração das perguntas e respostas
        const perguntas = [
            {
                pergunta: "Você tem um mapa?",
                respostas: {
                    sim: {
                        titulo: "humm!",
                        texto: "e porque eu me perdi no brilho do seu sorriso!",
                        imagem: "https://i.postimg.cc/VvWb5pJc/984f7c044cb0eb4e691acdb5a39c8038.jpg"
                    },
                    nao: {
                        titulo: "yess",
                        texto: "o brilho do seu olhar realmente me fez perder o rumo!",
                        imagem: "https://i.postimg.cc/sX0YstGH/download-1.jpg"
                    }
                }
            },
            {
                pergunta: "Você já criou algum projeto pessoal?",
                respostas: {
                    sim: {
                        titulo: "linda!",
                        texto: "Porque voce TAMARAvilhosa!",
                        imagem: "https://i.postimg.cc/yYb70KwY/download-2.jpg"
                    },
                    nao: {
                        titulo: "humm!",
                        texto: "a resposta certa era em cima!",
                        imagem: "https://i.postimg.cc/sX0YstGH/download-1.jpg"
                    }
                }
            },
            {
                pergunta: "Você gostaria de receber dicas de programação?",
                respostas: {
                    sim: {
                        titulo: "foi dificil fazer isso mais valeu apena!",
                        texto: "e quando me encontrei foi com saldades de voce!",
                        imagem: "https://i.postimg.cc/1tb7HWcT/download-3.jpg"
                    },
                    nao: {
                        titulo: "humm so queria te dizer!",
                        texto: "Que adoro conversar com voce!",
                        imagem: "https://i.postimg.cc/1tb7HWcT/download-3.jpg"
                    }
                }
            }
        ];

        let perguntaAtual = 1;
        const respostasUsuario = [];

        function responder(resposta, numeroPergunta) {
            // Armazena a resposta
            respostasUsuario[numeroPergunta-1] = resposta;
            
            // Configura o overlay com a resposta adequada
            const tipoResposta = resposta ? 'sim' : 'nao';
            const respostaData = perguntas[numeroPergunta-1].respostas[tipoResposta];
            
            document.getElementById('resposta-titulo').textContent = respostaData.titulo;
            document.getElementById('resposta-texto').textContent = respostaData.texto;
            
            const imgElement = document.getElementById('resposta-imagem');
            imgElement.src = respostaData.imagem;
            imgElement.style.display = 'block';
            
            // Mostra o overlay
            document.getElementById('overlay-resposta').style.display = 'flex';
        }

        function proximaPergunta() {
            // Esconde o overlay
            document.getElementById('overlay-resposta').style.display = 'none';
            
            // Esconde a pergunta atual
            document.getElementById(`pergunta${perguntaAtual}`).classList.add('hidden');
            
            // Avança para a próxima pergunta ou mostra resultados finais
            perguntaAtual++;
            
            if (perguntaAtual <= 3) {
                document.getElementById(`pergunta${perguntaAtual}`).classList.remove('hidden');
            } else {
                mostrarResultadoFinal();
            }
        }

        function mostrarResultadoFinal() {
            // Conta respostas positivas
            const positivas = respostasUsuario.filter(r => r).length;
            let mensagem = "";
            
            if (positivas === 3) {
                mensagem = "isso demorou demais mais vale apena ja que e para voce!";
            } else if (positivas >= 1) {
                mensagem = "Voce realmente repetiu em fiz isso com cuidado!";
            } else {
                mensagem = "voce e importante para mim";
            }
            
            document.getElementById('resultado-final').textContent = mensagem;
            document.getElementById('overlay-final').style.display = 'flex';
        }

        function reiniciar() {
            // Reseta tudo
            perguntaAtual = 1;
            respostasUsuario.length = 0;
            
            // Esconde overlays
            document.getElementById('overlay-final').style.display = 'none';
            document.getElementById('overlay-resposta').style.display = 'none';
            
            // Mostra primeira pergunta
            document.querySelectorAll('.container').forEach(el => el.classList.add('hidden'));
            document.getElementById('pergunta1').classList.remove('hidden');
        }
    </script>
</body>
</html>

