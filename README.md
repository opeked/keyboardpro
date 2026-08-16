# ⌨ KeyboardPRO

**Curso de datilografia futurista** — exercícios progressivos, testes cronometrados, provas com nota, desafios diários, ranking real e login (incluindo Google).

Arquivo principal: `KeyboardPRO.html` (tudo em um único HTML, sem servidor obrigatório).

---

## Funcionalidades

| Recurso | Descrição |
|--------|-----------|
| **Exercícios** | Níveis Iniciante, Intermediário e Profissional |
| **Teste rápido** | 1, 3 ou 5 minutos com PPM, precisão e erros em tempo real |
| **Provas** | Provas oficiais com nota (A–F) e histórico |
| **Gráficos** | Chart.js após cada teste + histórico no painel |
| **Desafios diários** | 3 desafios novos por dia |
| **Ranking** | Apenas usuários reais que já fizeram pelo menos 1 teste |
| **Login local** | Registro e entrada com usuário/senha (dados no navegador) |
| **Login Google** | Botão “Continuar com Google” (modo demo ou Client ID real) |
| **Visual** | Tema neon, partículas animadas, interface responsiva |

---

## Como usar

1. Baixe ou abra o arquivo **`KeyboardPRO.html`** no navegador (Chrome, Firefox, Edge…).
2. Clique em **Começar Agora** ou **Entrar**.
3. Crie uma conta (usuário + senha) **ou** use **Continuar com Google**.
4. Treine nos **Exercícios**, faça **Teste Rápido**, **Provas** e **Desafios**.
5. Acompanhe evolução no **Painel** e compare no **Ranking**.

> **Dica:** quanto mais testes você fizer, mais estável fica seu PPM médio no ranking.

---

## Login com Google

### Modo demonstração (já funciona)

Sem configurar nada: ao clicar em **Continuar com Google**, o site pede um nome e cria uma conta local associada ao “Google” (útil para testar).

### Login Google real

1. Acesse [Google Cloud Console](https://console.cloud.google.com/).
2. Crie um projeto (ou use um existente).
3. Vá em **APIs e serviços → Credenciais → Criar credenciais → ID do cliente OAuth**.
4. Tipo: **Aplicativo da Web**.
5. Em **Origens JavaScript autorizadas**, adicione a URL de onde o site será servido  
   (ex.: `http://localhost:5500` ou `https://seudominio.com`).
6. Copie o **Client ID**.
7. Abra `KeyboardPRO.html` e localize:

```js
const GOOGLE_CLIENT_ID = '';
```

8. Cole o Client ID entre as aspas, por exemplo:

```js
const GOOGLE_CLIENT_ID = '123456789-abcdefg.apps.googleusercontent.com';
```

9. Salve e recarregue a página. O popup oficial do Google passará a funcionar.

---

## Dados e privacidade

- Contas, histórico de PPM, provas e desafios são salvos no **navegador** (`localStorage`), quando disponível.
- Em ambientes muito restritos (alguns sandboxes/iframes), o site usa memória da sessão (dados somem ao recarregar).
- Não há servidor próprio: nada é enviado a um backend do KeyboardPRO.
- Contas Google reais usam o fluxo oficial do Google; o site só recebe nome, e-mail e foto do perfil para identificar o usuário localmente.

---

## Estrutura do projeto

```
artifacts/
├── KeyboardPRO.html   # Site completo (HTML + CSS + JS)
└── README.md          # Este arquivo
```

Dependências via CDN (internet necessária na primeira carga):

- [Chart.js](https://www.chartjs.org/) — gráficos
- [Google Identity Services](https://developers.google.com/identity/gsi/web) — login Google

---

## Níveis de exercício

- **Iniciante** — home row, letras básicas, frases curtas  
- **Intermediário** — textos completos, foco em velocidade e precisão  
- **Profissional** — pontuação, símbolos e textos longos  

---

## Ranking

- Só entram usuários **reais** (registrados) que já completaram **pelo menos 1 teste**.
- Ordenação: **PPM médio** (desempate por precisão).
- Não há ranks fictícios ou aleatórios.

---

## Atalhos / fluxo sugerido

1. Registrar ou entrar com Google  
2. Fazer 2–3 exercícios do nível atual  
3. Rodar um **Teste Rápido** de 1 minuto  
4. Completar um **Desafio diário**  
5. Quando se sentir confiante, fazer uma **Prova** do nível  

---

## Requisitos

- Navegador moderno com JavaScript ativado  
- Conexão à internet (CDN do Chart.js e, se usar, script do Google)  
- Para Google real: Client ID OAuth e origem autorizada  

---

## Licença / uso

Projeto demonstrativo para prática de datilografia. Você pode usar, copiar e adaptar livremente.

**KeyboardPRO** — treine rápido, digite certo.
