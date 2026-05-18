# 📱 ConectaFácil - Videochamada Simplificada para Idosos

**Plataforma:** Android (API 24+) | **Linguagem:** Kotlin Nativo | **Arquitetura:** MVVM | **Engine:** Jitsi Meet SDK

---

## 📝 Descrição do Projeto

O **ConectaFácil** é um aplicativo Android nativo de videoconferência desenvolvido com foco em acessibilidade extrema para idosos. A aplicação integra o SDK do Jitsi Meet para instanciar chamadas de vídeo imediatas com apenas um toque, eliminando fluxos de autenticação complexos, links voláteis e painéis poluídos de aplicativos tradicionais.

O projeto mitiga a barreira da exclusão digital na terceira idade, readequando a interface humano-computador através de componentes visuais hiper-dimensionados e um fluxo linear previsível de navegação.

---

## 🏗 Mockups e Interface do Usuário (Mídias do App em Execução)

Para garantir a total validação visual e demonstrar a topologia ergonômica planejada para o público idoso, os mockups abaixo representam as telas estruturais do sistema:

<p align="center">
  <img src="https://images.placeholders.dev/?width=300&height=550&text=Tela+Principal+-+Botao+Grande+Acessivel&theme=dark" alt="Mockup da Tela Principal do ConectaFácil" width="280"/>
  &nbsp;&nbsp;&nbsp;&nbsp;
  <img src="https://images.placeholders.dev/?width=300&height=550&text=Chamada+Ativa+-+Foco+Total+No+Video&theme=dark" alt="Mockup da Chamada Ativa" width="280"/>
</p>

---

## 🏛 Decisões Arquiteturais Mobile

O ecossistema técnico do **ConectaFácil** foi estruturado com foco em desacoplamento de código, manutenibilidade e gerenciamento reativo de ciclo de vida.

* **Model-View-ViewModel (MVVM):** Separação estrita da lógica de apresentação das regras de interface. A View observa reativamente as mudanças expostas pelo ViewModel, blindando o estado da aplicação contra perdas induzidas por rotações de tela ou mudanças de configuração do sistema.
* **Componentes de Acessibilidade:** Utilização de `View Binding` estruturado com suporte nativo a contrastes elevados e escalonamento dinâmico de fontes (SP), respeitando as diretrizes do Material Design v3.
* **StateFlow & Coroutines:** Os estados da tela (Carregando, Sucesso, Erro) são gerenciados via fluxos de dados unidirecionais seguros, assegurando que o clique único do usuário não trave a thread principal de renderização (UI Thread).
* **Jitsi Meet SDK Wrapper:** Encapsulamento da API nativa do Jitsi sobre uma camada de repositório abstrata. Isso permite injetar configurações globais pré-definidas (como desativar chat de texto, silenciar microfone ao entrar e ocultar botões de convite) de maneira invisível ao usuário final.

---

## 📊 Fluxo de Interação Técnica

Comportamento reativo da aplicação e o desacoplamento de responsabilidades entre as camadas:

```mermaid
graph TD
    A[Tela do Idoso / View] -->|Digita Nome + Clique Único| B(Botão Grande: Entrar)
    B -->|Dispara Evento| C[ViewModel]
    C -->|StateFlow: Altera Estado| A
    C -->|Configura Parâmetros| D[Jitsi Meet SDK Wrapper]
    D -->|Conexão Automática| E[Sala Fixa: familia-conecta]
````
## 🏛 Decisões Arquiteturais Mobile

O ecossistema técnico do **ConectaFácil** foi estruturado com foco em desacoplamento de código, manutenibilidade imediata e ciclo de vida robusto.

### Padrão de Arquitetura e UI
* **Model-View-ViewModel (MVVM):** Garante a separação estrita da lógica de apresentação das regras de interface. A camada de View observa reativamente as mudanças expostas pelo ViewModel, blindando o estado da aplicação contra perdas induzidas por rotações de tela ou mudanças de configuração do Android.
* **Componentes de Acessibilidade:** Utilização de `View Binding` estruturado com suporte nativo a contrastes elevados e escalonamento dinâmico de fontes (SP).

### Gerenciamento de Estado e Reatividade
* **StateFlow & Coroutines:** Os estados da tela (Carregando, Sucesso, Erro de Conexão, Sessão Ativa) são gerenciados via fluxos de dados unidirecionais seguros contra vazamento de memória. Isso assegura que o clique do idoso resulte em uma ação determinística sem travamento de UI Thread.

### Integração de APIs e Terceiros
* **Jitsi Meet SDK Wrapper:** Encapsulamento da API nativa do Jitsi sobre uma camada de repositório abstrata. Isso permite injetar configurações globais pré-definidas de chamada (como desativar chat de texto opcional, silenciar microfone por padrão, ocultar botões redundantes de convite) de maneira invisível ao usuário final.

---
## 🔗 Preview do Aplicativo

👉 https://manus.im/app-preview/3xTmBGWafsjHRpUjc5Ngvn?sessionId=LWAM8kRYRyoZfnbqaCvFOo  

---

## 📷 QR Code para Instalação

![QR Code](./qrcode.png)

---

## 🛠 Tecnologias Utilizadas

- **Linguagem:** Kotlin (Nativo)
- **Plataforma Alvo:** Android (SDK Mínima: API 24+ / Android 7.0)
- **Engine de Vídeo:** Jitsi Meet Android SDK (v3.10.2+)
- **Assincronismo:** Kotlin Coroutines
- **Ferramental Adicional:** Manus AI (Orquestração de UI)

---

## 🚀 Guia de Execução & Reprodutibilidade

Siga rigorosamente os pré-requisitos e comandos sequenciais abaixo para clonar, compilar e rodar o projeto localmente.

### Pré-requisitos de Ambiente
1. **Java Development Kit:** JDK 17 configurado nas variáveis de ambiente.
2. **Android Studio:** Versão Ladybug (2024.2.1) ou superior instalada.
3. **Android SDK:** Instalar via SDK Manager o Android 14.0 (API 34).
4. **Dispositivo Físico ou Emulador:** Dispositivo com câmera e microfone funcionais (API 24+).

### Comandos de Terminal para Build

```bash
# 1. Clonar o repositório
git clone [https://github.com/bryanthomas-dev/portfolio-bryan-thomas-montalvo-ferreira.git](https://github.com/bryanthomas-dev/portfolio-bryan-thomas-montalvo-ferreira.git)

# 2. Navegar até o diretório correspondente ao projeto mobile
cd portfolio-bryan-thomas-montalvo-ferreira/projeto-composicao-musical

# 3. Limpar builds residuais e validar dependências do Gradle
./gradlew clean

# 4. Compilar o projeto em modo de depuração (Debug)
./gradlew assembleDebug

# 5. Instalar o APK gerado diretamente no dispositivo ou emulador conectado
./gradlew installDebug
```
<p align="right"><a href="https://github.com/bryanthomas-dev/portfolio-bryan-thomas-montalvo-ferreira">⬅️ Voltar ao início</a></p>
