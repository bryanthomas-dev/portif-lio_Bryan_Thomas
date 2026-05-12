# 🔬 SM2 - Laboratório de Classificação Visual

## 📝 Descrição do Projeto

Este projeto consiste na criação e treinamento de um modelo de classificação visual utilizando aprendizado de máquina, capaz de identificar características visuais em imagens a partir de amostras fornecidas pelo próprio usuário.

Desenvolvido como parte da disciplina de **Engenharia de Prompt e Aplicações em IA (2026.1)**, o laboratório utilizou a plataforma **Teachable Machine (Google)** para treinar um classificador de imagens com duas categorias personalizadas: **calvo** e **careca**. O modelo foi alimentado com 20 amostras de imagens por classe e testado em tempo real via câmera e upload de imagens.

## 🖼️ Demonstração

O modelo foi capaz de classificar corretamente rostos com diferentes características capilares, atingindo **100% de confiança** na categoria correta durante os testes realizados.

![Teste do modelo em tempo real](./demo_classificacao.png)
*Figura 1: Resultado do modelo classificando uma imagem com 100% de confiança na categoria "careca".*

![Interface de treinamento](./treinamento_modelo.png)
*Figura 2: Interface do Teachable Machine com as duas classes treinadas e amostras de imagens.*

## 🚀 Tecnologias Utilizadas

* **Plataforma:** Teachable Machine (Google)
* **Tipo de modelo:** Classificação de imagens (Image Project)
* **Amostras por classe:** 20 imagens
* **Teste:** Upload de imagem e câmera ao vivo

## 📊 Resultados e Aprendizados

* **100% de acurácia** nos testes com as imagens utilizadas.
* Compreensão prática de como modelos de Machine Learning aprendem a partir de exemplos visuais.
* Entendimento do conceito de **classes**, **amostras de treinamento** e **inferência** em modelos de visão computacional.
* Aprendizado sobre a importância da diversidade e qualidade das amostras para melhorar a performance do modelo.

## 🔧 Como Reproduzir

1. Acesse [Teachable Machine](https://teachablemachine.withgoogle.com/).
2. Crie um novo projeto do tipo **Image Project**.
3. Adicione suas classes e faça upload de no mínimo 20 imagens por categoria.
4. Clique em **Train Model** e aguarde o treinamento.
5. Teste o modelo com novas imagens via câmera ou upload.

---

[⬅ Voltar ao portfólio](https://github.com/bryanthomas-dev/portif-lio_Bryan_Thomas)
