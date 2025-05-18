# ⚽ Vai Passar Onde? 📺

## ✨ Sobre o Projeto

"Vai Passar Onde?" é uma aplicação inteligente desenvolvida em Python que utiliza um sistema de múltiplos agentes para fornecer a você o guia mais rápido e prático dos jogos de futebol e seus canais de transmissão no Brasil. Cansado de procurar onde assistir o jogo do seu time ou os principais confrontos do dia? Este projeto resolve isso para você!

## 💡 Como Funciona

O projeto opera com uma arquitetura modular baseada em Agentes (utilizando a Google AI Client Library), onde cada agente tem uma responsabilidade específica:

1.  **🕵️‍♂️ Agente Coletor de Jogos:** Este agente é o "pesquisador". Ele utiliza a ferramenta de busca (Google Search) para vasculhar a web em sites confiáveis de esporte e guias de programação, coletando informações brutas sobre os jogos agendados e suas transmissões no Brasil. Ele foca nas principais competições e times, priorizando ligas masculinas e times brasileiros.
2.  **🧠 Agente Processador de Dados:** O "organizador" e "identificador". Ele recebe os dados brutos do Coletor, estrutura as informações de forma consistente e, crucialmente, identifica se algum jogo envolve o seu "time do coração", marcando-o com uma flag especial (`is_favorite_game`).
3.  **✍️ Agente Gerador de Texto:** O "comunicador". Este agente pega os dados processados e formatados e transforma-os em um texto simples e direto, no estilo "WhatsApp", pronto para ser lido ou compartilhado.

A lógica principal em Python orquestra esses agentes: primeiro busca a próxima partida do time favorito, exibe-a, depois busca os jogos de hoje (filtrando e removendo duplicatas caso o jogo do favorito seja hoje) e, por fim, exibe a lista dos jogos de hoje.

## 🚀 Features

* **Busca do Time do Coração:** Encontra a próxima partida agendada especificamente para o time que você indicar.
* **Agenda do Dia:** Lista os principais jogos de futebol que acontecem hoje, focando em competições relevantes.
* **Informações de Transmissão:** Detalha em quais canais de TV ou plataformas de streaming o jogo será exibido no Brasil.
* **Sistema Multi-Agente:** Arquitetura modular e expansível baseada em agentes dedicados.
* **Foco em Relevância:** Prioriza as ligas e times mais populares, filtrando competições menos relevantes (séries inferiores, ligas femininas/de base - configurável).
* **Formato Amigável:** Apresenta as informações de forma clara e formatada para fácil leitura.

## 🛠️ Tecnologias Utilizadas

* **Python 3**
* **Google AI Client Library** (para criar e gerenciar os Agentes)
* **Google Search Tool** (como ferramenta para o Agente Coletor)
* **Google Colab** (ambiente recomendado para execução inicial)

## 🚦 Configuração e Como Executar

Este projeto foi desenvolvido e testado no ambiente Google Colab, que facilita a configuração e execução, especialmente com as chaves de API.

1.  **Obtenha uma Google API Key:**
    * Acesse o [Google AI Studio](https://aistudio.google.com/) ou o [Google Cloud Console (Vertex AI)](https://console.cloud.google.com/vertex-ai).
    * Crie ou selecione um projeto.
    * Gere uma API Key que tenha permissão para usar o modelo Gemini e ferramentas (como Google Search).

2.  **Configure a API Key no Google Colab:**
    * Abra seu notebook no Google Colab.
    * No menu lateral esquerdo, clique no ícone de uma "chave" (Secrets / Segredos).
    * Clique em "Adicionar novo segredo".
    * No campo "Nome", digite `GOOGLE_API_KEY` (é essencial que seja exatamente este nome).
    * No campo "Valor", cole a API Key que você obteve.
    * Certifique-se que a opção "Notebook access" (Acesso do notebook) esteja ativa para o seu notebook.

3.  **Copie o Código:**
    * Copie todo o código Python (`.py` ou o conteúdo do seu notebook Colab) para uma célula no seu notebook Colab.

4.  **Execute o Notebook:**
    * Execute a célula que contém o código.
    * O script pedirá que você digite o nome do seu time do coração no campo de entrada.
    * Acompanhe a execução das etapas de coleta, processamento e geração do texto.
    * Os resultados (próxima partida do favorito e jogos de hoje) serão exibidos no output do notebook.

## ☁️ Próximos Passos e Possíveis Melhorias

* **Interface Web Completa:** Desenvolver um frontend (como a simulação em HTML/CSS/JS fornecida, mas funcional) e um backend (Python Flask/Django) para transformar a aplicação em um serviço web acessível via navegador.
* **Notificações:** Implementar um sistema de notificação (por email, push, etc.) para avisar sobre a próxima partida do time favorito.
* **Personalização:** Permitir que o usuário configure suas ligas e times favoritos de forma persistente.
* **Mais Esportes:** Expandir a busca para outros esportes além do futebol.
* **Dockerização:** Empacotar a aplicação em um container Docker para facilitar a implantação.

## 📄 Licença

Este projeto está sob a licença.

## ✍️ Autor

Carlos Augusto Costa Bastos (https://github.com/caugustocbastos)
