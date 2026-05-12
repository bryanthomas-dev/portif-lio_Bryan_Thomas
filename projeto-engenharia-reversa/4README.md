# 🔍 SM4 - Engenharia Reversa

## 📝 Descrição do Projeto

Este projeto explorou o conceito de **Engenharia Reversa aplicada a prompts e interfaces de IA**, analisando como modelos de linguagem interpretam e reagem a diferentes instruções de persona, contexto e restrições. O objetivo foi compreender o comportamento "por baixo dos panos" das IAs ao receber comandos estruturados.

Desenvolvido como parte da disciplina de **Engenharia de Prompt e Aplicações em IA (2026.1)**, o experimento utilizou o modelo **Qwen3.5-Plus** para simular cenários criativos complexos — incluindo geração iterativa de imagens com múltiplos refinamentos de prompt e geração de textos com personas bem definidas — analisando como cada ajuste no prompt alterava o comportamento do modelo.

## 🧪 Experimentos Realizados

### 🎨 Experimento 1 — Geração Iterativa de Imagens
Partindo de um prompt inicial simples *("astronauta em Marte tocando violoncelo no estilo barroco")*, foram realizados refinamentos sucessivos:

- Iteração 1: Astronauta solo em Marte.
- Iteração 2: Adição de ETs na plateia.
- Iteração 3: Reposicionamento dos ETs na arquibancada.
- Iteração 4: Astronauta em palco com plateia de ETs.
- Iteração 5: Remoção da cortina e restauração do cenário marciano.

**Aprendizado:** Pequenas mudanças no prompt geram grandes diferenças no resultado visual. A IA mantém contexto entre iterações se bem orientada.

### ✍️ Experimento 2 — Persona e Tom de Texto
Foi solicitado ao modelo que escrevesse e-mails fictícios de um pirata para um rei, com variações progressivas de persona:

- E-mail formal de desculpas → resultado padrão.
- Adição de contexto (roubou as 7 esferas do dragão) → texto mais específico.
- Persona: pirata extremamente arrogante → tom completamente diferente.
- Instrução: pirata considera o rei um amador → provocação direta no texto.
- Restrição: manter o formato de pedido de desculpas com arrogância → resultado híbrido.

**Aprendizado:** A IA adapta completamente o tom e conteúdo conforme instruções de persona, demonstrando que o *contexto emocional* do prompt é tão importante quanto as instruções técnicas.

## 🚀 Tecnologias Utilizadas

* **Modelo de IA:** Qwen3.5-Plus
* **Plataforma:** chat.qwen.ai
* **Tipo de tarefa:** Geração de imagens + Geração de texto com persona

## 📊 Resultados e Aprendizados

* Compreensão aprofundada de como **contexto, persona e restrições** moldam as respostas de modelos de linguagem.
* Entendimento de que a IA não "entende" — ela **prevê** o próximo token com base no contexto fornecido.
* A **engenharia reversa** de prompts permite descobrir os limites e capacidades de cada modelo de forma prática.

---

[⬅ Voltar ao portfólio](https://github.com/bryanthomas-dev/portif-lio_Bryan_Thomas)
