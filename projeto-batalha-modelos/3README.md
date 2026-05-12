# ⚔️ SM3 - Batalha de Modelos & Engenharia de Prompt (XML)

## 📝 Descrição do Projeto

Este projeto consistiu na criação de um **Prompt Estruturado em XML** para geração de uma página HTML Single Page com CSS integrado, testado simultaneamente em 7 ferramentas de IA diferentes: ChatGPT, Gemini, DeepSeek, Qwen, Grok, Maritaca e Claude.

Desenvolvido em grupo como parte da disciplina de **Engenharia de Prompt e Aplicações em IA (2026.1)**, o objetivo foi comparar a capacidade de compreensão, criatividade, precisão técnica e eficiência de cada modelo ao interpretar o mesmo prompt estruturado, gerando um quadro analítico comparativo completo.

**Integrantes:** Bryan Thomas Montalvo Ferreira, Welvis Ribeiro dos Santos, Naum Gonçalves Gomes.

## 🧪 O Prompt XML Utilizado

```xml
<tarefa>
  <objetivo>Criar uma página HTML5 única com CSS3 interno (single page).</objetivo>
  <tema>Receita de bolos</tema>
  <diretrizes_design>
    <layout>Responsivo e minimalista.</layout>
    <paleta_cores>Marrom e Bege</paleta_cores>
    <tipografia>Sans-serif para títulos, Serif para corpo.</tipografia>
  </diretrizes_design>
  <obrigatoriedades_tecnicas>
    <item>Menu de navegação funcional (âncoras).</item>
    <item>Seção de portfólio ou galeria.</item>
    <item>Rodapé com informações de contato simuladas.</item>
    <item>Bolo de chocolate</item>
  </obrigatoriedades_tecnicas>
  <metrica_obrigatoria>
    Ao final da resposta, informe uma estimativa de quantos tokens foram gerados.
  </metrica_obrigatoria>
</tarefa>
```

## 📊 Resultados Comparativos

| Critério | ChatGPT | Gemini | DeepSeek | Qwen | Grok | Maritaca | **Claude** |
|---|---|---|---|---|---|---|---|
| Precisão do Prompt | 7/10 | 9/10 | 7/10 | 7/10 | 8,5/10 | 7/10 | **10/10** |
| Precisão do HTML | 6,5/10 | 9/10 | 7/10 | 4/10 | 8/10 | Ok | **10/10** |
| Criatividade | 3/10 | 9/10 | 7/10 | 3/10 | 8/10 | Nenhuma | **10/10** |
| Bugs | 1 erro | 1 erro | 2 erros | 0 erros | 1 erro | 1 erro | **Nenhum** |
| Tokens Gastos | ~1000 | ~1450 | ~3000 | ~1450 | ~4820 | ~1300 | ~10500 |

## 🏆 Conclusões

* **Claude** demonstrou maior compreensão do prompt XML, entregando resultado com degradê, animações, destaque em palavras-chave e estrutura impecável — nota 10/10 em todos os critérios.
* Houve diferença significativa de verbosidade: o melhor resultado (Claude) utilizou ~10.500 tokens, enquanto os modelos básicos ficaram em média em ~4.000 tokens.
* **Para prototipagem rápida e código complexo:** Claude foi a escolha unânime do grupo.

## 🚀 Tecnologias Utilizadas

* **Linguagem do Prompt:** XML estruturado
* **Output gerado:** HTML5 + CSS3 (Single Page)
* **Ferramentas testadas:** Claude, ChatGPT, Gemini, DeepSeek, Qwen, Grok, Maritaca

---

[⬅ Voltar ao portfólio](https://github.com/bryanthomas-dev/portif-lio_Bryan_Thomas)
