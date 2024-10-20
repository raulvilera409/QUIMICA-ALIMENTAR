<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Atividade Avaliativa - Química Aplicada</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f0f0f0;
            color: #333;
        }
        .form-container {
            background-color: rgba(0, 0, 0, 0.85);
            margin: 20px auto;
            padding: 20px;
            border-radius: 10px;
            width: 90%;
            max-width: 1200px;
            color: white;
        }
        /* Cabeçalho da Escola */
        .header {
            margin-bottom: 20px;
        }
        .header h1 {
            font-size: 24px;
            text-align: left;
            margin: 0;
        }
        /* Conteúdo do Formulário */
        .form-content {
            margin-top: 20px;
        }
        .cabecalho {
            display: flex;
            justify-content: space-between;
            flex-wrap: wrap;
            margin-bottom: 20px;
        }
        .cabecalho div {
            width: 30%;
            min-width: 200px;
            margin-bottom: 10px;
        }
        .serie-dropdown {
            width: 25%;
            min-width: 150px;
            margin-bottom: 10px;
        }
        /* Estilo para Numeração das Questões */
        .numero-questao {
            color: red;
            font-weight: bold;
            margin-right: 10px;
        }
        /* Cronômetro */
        .relogio {
            width: 30px; /* Metade do tamanho original */
            height: 30px; /* Metade do tamanho original */
            border-radius: 50%;
            font-size: 12px; /* Ajustado para o novo tamanho */
            display: flex;
            align-items: center;
            justify-content: center;
            background-color: white;
            color: black;
            font-weight: bold;
            border: 2px solid transparent; /* Removido o border padrão */
            background-image: linear-gradient(white, white), linear-gradient(to bottom, blue, lime);
            background-origin: border-box;
            background-clip: content-box, border-box;
            position: absolute; /* Posicionado no canto superior esquerdo */
            top: 15px;
            left: 15px;
        }
        /* Questão */
        .questao {
            position: relative; /* Necessário para posicionar o cronômetro dentro da questão */
            margin-bottom: 30px;
            background-color: rgba(255, 255, 255, 0.1);
            padding: 20px 20px 20px 60px; /* Espaço à esquerda para o cronômetro */
            border-radius: 8px;
        }
        .questao p {
            margin-bottom: 15px;
            font-size: 16px;
        }
        /* Campo de Resposta */
        .resposta {
            width: 100%;
            height: 240px; /* Ajustado para pelo menos 8 pautas */
            padding: 10px;
            border-radius: 5px;
            border: 2px solid #cccccc; /* Borda para definir o campo */
            resize: vertical;
            line-height: 1.5;
            background-color: #ffffff; /* Fundo branco */
            background-image: repeating-linear-gradient(
                to bottom,
                #ffffff 0px,
                #ffffff 29px,
                #e0e0e0 29px,
                #e0e0e0 30px
            ); /* Linhas em cinza claro */
            background-size: 100% 30px;
            color: darkblue; /* Cor azul escura */
            font-size: 14px;
            font-weight: bold; /* Texto em negrito */
        }
        /* Estilização dos Campos de Seleção e Data */
        input[type="date"], select {
            width: 100%;
            padding: 10px;
            margin-top: 5px;
            border-radius: 5px;
            border: none;
            font-size: 14px;
            color: darkblue; /* Cor azul escura */
            font-weight: bold; /* Texto em negrito */
            background-color: white; /* Fundo branco para contraste */
        }
        /* Botão de Envio */
        button {
            display: block;
            margin: 30px auto;
            padding: 15px 30px;
            font-size: 16px;
            border: none;
            border-radius: 5px;
            background-color: #28a745;
            color: white;
            cursor: pointer;
            transition: background-color 0.3s;
        }
        button:hover {
            background-color: #218838;
        }
        /* Estilos para questões de múltipla escolha */
        .opcoes {
            margin-top: 10px;
        }
        .opcoes label {
            display: block;
            margin-bottom: 5px;
            cursor: pointer;
            font-weight: bold; /* Texto em negrito */
            color: white; /* Cor branca inicialmente */
        }
        /* Alterar a cor da alternativa selecionada para azul escura */
        .opcoes input[type="radio"]:checked + span {
            color: darkblue; /* Cor azul escura quando selecionada */
        }
        /* Adicionar estilo para os spans dentro das labels */
        .opcoes label span {
            color: white; /* Cor branca inicialmente */
            transition: color 0.3s;
        }
        /* Estilo para as linhas entre questões */
        .linha-questao {
            border-top: 2px solid #ffffff;
            margin: 30px 0;
        }
        /* Responsividade */
        @media (max-width: 768px) {
            .form-container {
                width: 95%;
            }
            .cabecalho {
                flex-direction: column;
            }
            .cabecalho div, .serie-dropdown {
                width: 100%;
            }
            .relogio {
                top: 10px;
                left: 10px;
            }
            .questao {
                padding: 15px 15px 15px 50px;
            }
            .linha-questao {
                margin: 20px 0;
            }
        }
    </style>
</head>
<body>

    <div class="form-container">
        <!-- Cabeçalho da Escola -->
        <div class="header">
            <h1>E.E. MARIA LEONI</h1>
        </div>

        <!-- Conteúdo do Formulário -->
        <div class="form-content">
            <div class="cabecalho">
                <div>
                    <p>NOME: 
                        <select id="nome" name="nome" required>
                            <option value="" disabled selected>Selecione seu nome</option>
                            <option>ANA CLARA PETRONI DE SOUZA</option>
                            <option>ANTHONY LEONARDI DOS SANTOS</option>
                            <option>BEATRIZ BORTOLO CANDIDO</option>
                            <option>BEATRIZ CAMARGO</option>
                            <option>BEATRIZ DA SILVA VELOSO</option>
                            <option>DAVI CRUZ SIBINELLI</option>
                            <option>ERICK SALVADOR</option>
                            <option>FELIPE PEREIRA DA SILVA</option>
                            <option>GABRIEL ALVES DOS SANTOS SILVA</option>
                            <option>GABRIELA DOS ANJOS ALVES</option>
                            <option>GIOVANA CRISTINA ALVES DOMINGUES</option>
                            <option>GRAZIELLA DOS ANJOS MELO</option>
                            <option>GUSTAVO ALMEIDA DA SILVA</option>
                            <option>GUSTAVO RONDON</option>
                            <option>JESSYCA VITORIA COSTA VASCONCELOS</option>
                            <option>HELOISA ALVES DA SILVA</option>
                            <option>ISABELA FERREIRA CLEMENTE</option>
                            <option>ISABELLY MARTINS DE SIQUEIRA CORTEZ</option>
                            <option>JOAO VICTOR MONTEIRO DA SILVA</option>
                            <option>KAUA DE DEUS MESQUITA LEONARDO</option>
                            <option>KLEBER GABRIEL SAMPAIO VARELLA</option>
                            <option>MANUELLA QUEIROZ DOS SANTOS</option>
                            <option>MARIA CLARA DA SILVA BARBOSA SAMPAIO</option>
                            <option>MARIA EDUARDA LOPES DE OLIVEIRA</option>
                            <option>MATEUS VITOR PINHEIRO GONCALES</option>
                            <option>MATHEUS DOS SANTOS SOUSA</option>
                            <option>MATHEUS FERREIRA DE OLIVEIRA</option>
                            <option>NICOLAS FERNANDO SANTANA VIEIRA</option>
                            <option>SOPHIA ALVIN SILVA</option>
                            <option>THAISSA RAMOS DA SILVA</option>
                            <option>THAYNÁ VIEIRA SANTOS</option>
                        </select>
                    </p>
                </div>
                <div class="serie-dropdown">
                    <p>SÉRIE: 
                        <select id="serie" name="serie" required>
                            <option value="" disabled selected>Selecione a série</option>
                            <option value="3ª SÉRIE A">3ª SÉRIE A</option>
                            <option value="3ª SÉRIE B">3ª SÉRIE B</option>
                        </select>
                    </p>
                </div>
                <div class="serie-dropdown">
                    <p>DATA: <input type="date" id="data" name="data" required></p>
                </div>
            </div>

            <h2 style="text-align: center;">ATIVIDADE DE QUÍMICA APLICADA</h2>
            <p style="text-align: center;">TEMA: QUÍMICA ALIMENTAR</p>

            <div id="questoes-container"></div>

            <button onclick="enviarRespostas()">Enviar Respostas</button>
        </div>

    </div>

    <script>
        const questoes = [
            {
                tipo: 'aberta',
                texto: `A importância da conservação sustentável de alimentos em 2024:
A conservação dos alimentos é essencial para garantir segurança alimentar e reduzir desperdícios. No entanto, o impacto ambiental de métodos como refrigeração e embalagens plásticas tem sido amplamente debatido.
Questão: Como novas tecnologias, como embalagens biodegradáveis e sistemas modulares sem energia elétrica, podem minimizar os impactos ambientais da conservação de alimentos?`
            },
            {
                tipo: 'aberta',
                texto: `Internet das Coisas (IoT) na conservação e segurança alimentar:
Em 2024, a IoT é amplamente utilizada para monitorar a temperatura de armazenamento e prevenir a deterioração de alimentos.
Questão: Explique como o uso da IoT pode garantir a qualidade dos alimentos e evitar desperdícios, considerando tanto a indústria alimentícia quanto o consumo doméstico.`
            },
            {
                tipo: 'aberta',
                texto: `Aditivos alimentares e saúde pública:
A regulamentação sobre aditivos alimentares visa garantir a segurança do consumidor. No entanto, com o crescimento dos movimentos por alimentação saudável e natural, há maior pressão por alternativas naturais.
Questão: Como os avanços na química dos alimentos estão possibilitando a substituição de aditivos sintéticos por conservantes naturais? Discuta vantagens e desafios dessa transição.`
            },
            {
                tipo: 'aberta',
                texto: `Alimentos ultraprocessados e saúde pública em 2024:
A alta disponibilidade de alimentos ultraprocessados é um desafio global para a saúde pública, associado ao aumento de doenças crônicas.
Questão: Como as inovações na formulação de alimentos ultraprocessados podem mitigar seus efeitos negativos e promover um consumo mais saudável?`
            },
            {
                tipo: 'aberta',
                texto: `Legislação e segurança alimentar:
Em um cenário de comércio global, as regulamentações de segurança alimentar precisam ser atualizadas constantemente para lidar com novos desafios, como alimentos transgênicos e aditivos modernos.
Questão: Avalie como as normas estabelecidas por órgãos como a ANVISA e o Codex Alimentarius ajudam a garantir a segurança dos alimentos em 2024. Quais desafios permanecem?`
            },
            {
                tipo: 'aberta',
                texto: `Mudanças climáticas e conservação de alimentos:
O aumento das temperaturas e a instabilidade climática afetam diretamente a produção e conservação de alimentos.
Questão: Como tecnologias de conservação, como a liofilização e embalagens inteligentes, podem ajudar a mitigar os impactos das mudanças climáticas na segurança alimentar?`
            },
            {
                tipo: 'aberta',
                texto: `Composição nutricional e alimentação personalizada:
A demanda por alimentos personalizados, alinhados com necessidades individuais, como dietas para diabéticos ou intolerantes à lactose, tem crescido em 2024.
Questão: Como o conhecimento sobre a composição química dos alimentos e avanços em nutrição personalizada podem melhorar a saúde e o bem-estar da população?`
            },
            {
                tipo: 'aberta',
                texto: `Sustentabilidade e redução do desperdício de alimentos:
A produção alimentar sustentável é essencial para garantir o abastecimento global. Reduzir o desperdício e otimizar a conservação são passos importantes nesse processo.
Questão: Quais métodos inovadores de conservação podem contribuir para a redução do desperdício de alimentos, tanto em ambientes urbanos quanto rurais?`
            },
            {
                tipo: 'multipla-escolha',
                texto: `Embalagens inteligentes como solução para conservação eficiente:
As embalagens inteligentes são uma inovação que monitora a frescura dos alimentos, indicando a qualidade e a validade do produto.
Questão: Quais benefícios essas embalagens proporcionam à indústria e aos consumidores?`,
                opcoes: [
                    { letra: 'a', texto: 'Redução dos custos de produção e eliminação da necessidade de refrigeração' },
                    { letra: 'b', texto: 'Melhoria na segurança alimentar e redução do desperdício de alimentos' },
                    { letra: 'c', texto: 'Aumento da vida útil dos alimentos, mas com maior impacto ambiental' },
                    { letra: 'd', texto: 'Redução do consumo de aditivos alimentares, embora com alto custo para o consumidor' }
                ],
                respostaCorreta: 'b'
            },
            {
                tipo: 'multipla-escolha',
                texto: `Química dos alimentos e alimentos fortificados:
A química dos alimentos permite a criação de alimentos enriquecidos para combater deficiências nutricionais em populações vulneráveis.
Questão: Qual é um exemplo prático de alimentos fortificados disponíveis em 2024?`,
                opcoes: [
                    { letra: 'a', texto: 'Água mineral com corantes artificiais' },
                    { letra: 'b', texto: 'Pães enriquecidos com ferro e ácido fólico' },
                    { letra: 'c', texto: 'Lanches ultraprocessados com aumento de gorduras saturadas' },
                    { letra: 'd', texto: 'Alimentos orgânicos sem adição de micronutrientes' }
                ],
                respostaCorreta: 'b'
            }
        ];

        const cronometros = {}; // Objeto para armazenar os cronômetros de cada questão

        function iniciarCronometro(questaoId) {
            if (!cronometros[questaoId]) {
                let segundos = 0;
                const cronometro = document.getElementById(`cronometro-${questaoId}`);
                
                cronometros[questaoId] = setInterval(() => {
                    segundos++;
                    const minutos = Math.floor(segundos / 60);
                    const restoSegundos = segundos % 60;
                    cronometro.textContent = `${minutos.toString().padStart(2, '0')}:${restoSegundos.toString().padStart(2, '0')}`;
                }, 1000);
            }
        }

        function pararCronometro(questaoId) {
            if (cronometros[questaoId]) {
                clearInterval(cronometros[questaoId]);
                cronometros[questaoId] = null;
            }
        }

        function gerarQuestoes() {
            const container = document.getElementById('questoes-container');
            questoes.forEach((questao, index) => {
                const questaoId = index + 1;

                const questaoDiv = document.createElement('div');
                questaoDiv.classList.add('questao');

                // Cronômetro
                const cronometroDiv = document.createElement('div');
                cronometroDiv.classList.add('relogio');
                cronometroDiv.id = `cronometro-${questaoId}`;
                cronometroDiv.textContent = "00:00";
                questaoDiv.appendChild(cronometroDiv);

                // Pergunta com Numeração
                const pergunta = document.createElement('p');

                // Criar elemento para número da questão
                const numeroSpan = document.createElement('span');
                numeroSpan.classList.add('numero-questao');
                numeroSpan.textContent = `${questaoId}. `;

                // Adicionar número e texto da questão
                pergunta.appendChild(numeroSpan);
                pergunta.appendChild(document.createTextNode(questao.texto));
                questaoDiv.appendChild(pergunta);

                // Resposta
                if (questao.tipo === 'aberta') {
                    const resposta = document.createElement('textarea');
                    resposta.id = `resposta-${questaoId}`;
                    resposta.name = `resposta-${questaoId}`;
                    resposta.placeholder = "Digite sua resposta aqui...";
                    resposta.classList.add('resposta');
                    resposta.addEventListener('focus', () => iniciarCronometro(questaoId));
                    resposta.addEventListener('blur', () => pararCronometro(questaoId));
                    questaoDiv.appendChild(resposta);
                } else if (questao.tipo === 'multipla-escolha') {
                    const opcoesDiv = document.createElement('div');
                    opcoesDiv.classList.add('opcoes');

                    questao.opcoes.forEach(opcao => {
                        const label = document.createElement('label');
                        const input = document.createElement('input');
                        input.type = 'radio';
                        input.name = `resposta-${questaoId}`;
                        input.value = opcao.letra;
                        input.required = true;

                        // Criar um span para o texto da opção
                        const span = document.createElement('span');
                        span.textContent = ` ${opcao.letra}) ${opcao.texto}`;

                        label.appendChild(input);
                        label.appendChild(span);
                        opcoesDiv.appendChild(label);
                    });

                    // Adicionar evento para iniciar/parar cronômetro quando uma opção é selecionada/desselecionada
                    opcoesDiv.querySelectorAll('input[type="radio"]').forEach(radio => {
                        radio.addEventListener('change', () => {
                            if (radio.checked) {
                                iniciarCronometro(questaoId);
                            }
                        });
                        radio.addEventListener('blur', () => {
                            pararCronometro(questaoId);
                        });
                    });

                    questaoDiv.appendChild(opcoesDiv);
                }

                // Adicionar linha separadora entre questões, exceto após a última
                if (questaoId < questoes.length) {
                    const linha = document.createElement('hr');
                    linha.classList.add('linha-questao');
                    questaoDiv.appendChild(linha);
                }

                container.appendChild(questaoDiv);
            });
        }

        async function enviarRespostas() {
            const nome = document.getElementById('nome').value;
            const serie = document.getElementById('serie').value;
            const data = document.getElementById('data').value;

            if (!nome || !serie || !data) {
                alert("Por favor, preencha todos os campos antes de enviar.");
                return;
            }

            let respostas = {};
            respostas['nome'] = nome;
            respostas['serie'] = serie;
            respostas['data'] = data;

            const totalQuestoes = questoes.length; // Número total de questões
            for (let i = 1; i <= totalQuestoes; i++) {
                if (questoes[i - 1].tipo === 'aberta') {
                    const resposta = document.getElementById(`resposta-${i}`).value;
                    respostas[`resposta-${i}`] = resposta;
                } else if (questoes[i - 1].tipo === 'multipla-escolha') {
                    const respostaSelecionada = document.querySelector(`input[name="resposta-${i}"]:checked`);
                    respostas[`resposta-${i}`] = respostaSelecionada ? respostaSelecionada.value : '';
                }
            }

            // Parar todos os cronômetros antes de enviar
            for (let i = 1; i <= totalQuestoes; i++) {
                pararCronometro(i);
            }

            try {
                const response = await fetch('https://script.google.com/macros/s/AKfycbx5iMaz8Hepg47TXIgD9eF7gsr2slPP191_7g6o7BwUEhNM2a4cdUA38crFOLYI73o8/exec', { // Substitua por seu URL do Web App
                    method: 'POST',
                    mode: 'no-cors', // Necessário para evitar problemas de CORS
                    headers: {
                        'Content-Type': 'application/x-www-form-urlencoded',
                    },
                    body: new URLSearchParams(respostas)
                });

                // Limpar o formulário após o envio
                document.getElementById('nome').value = "";
                document.getElementById('serie').value = "";
                document.getElementById('data').value = "";
                for (let i = 1; i <= totalQuestoes; i++) {
                    if (questoes[i - 1].tipo === 'aberta') {
                        document.getElementById(`resposta-${i}`).value = "";
                    } else if (questoes[i - 1].tipo === 'multipla-escolha') {
                        const radios = document.getElementsByName(`resposta-${i}`);
                        radios.forEach(radio => radio.checked = false);
                    }
                    document.getElementById(`cronometro-${i}`).textContent = "00:00";
                }

                alert("Respostas enviadas com sucesso!");
            } catch (error) {
                console.error('Erro ao enviar respostas:', error);
                alert("Ocorreu um erro ao enviar as respostas. Por favor, tente novamente.");
            }
        }

        // Inicializa as questões ao carregar a página
        window.onload = gerarQuestoes;
    </script>

</body>
</html>
