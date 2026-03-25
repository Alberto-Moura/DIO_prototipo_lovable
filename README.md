# DIO_prototipo_lovable
Site criado com auxilio de prompt gerado por ia e layout criado por Lovable

Prompt Original:
# PRD – Aplicativo de Finanças Pessoais por Conversa

## 1. Introdução e Objetivo

O **Objetivo** deste documento é detalhar o Product Requirements Document (PRD) para um aplicativo de organização de finanças pessoais baseado em conversas. A proposta é eliminar a complexidade das planilhas e formulários manuais, oferecendo uma experiência simples e natural, onde o usuário interage com um “Agente Financeiro” por meio de chat.

O foco é criar um **MVP (Produto Viável Mínimo)** que valide a hipótese principal: *pessoas que têm dificuldade em controlar gastos se engajam mais quando o processo é conversacional e as recomendações são automáticas.*

---

## 2. Problema e Solução

| Problema | Solução Proposta |
|----------|------------------|
| Aplicativos atuais exigem cadastro manual de cada gasto (formulários, categorias, datas). | Registro por linguagem natural: o usuário digita ou fala algo como “gastei R$ 50 no supermercado hoje” e o app interpreta e registra automaticamente. |
| Pouca personalização e ausência de insights práticos. | Agente Financeiro que aprende os hábitos do usuário e oferece dicas personalizadas de economia, além de sugerir metas realistas. |
| Desistência por falta de engajamento. | Experiência conversacional contínua, com lembretes inteligentes e relatórios simplificados gerados sob demanda. |

---

## 3. Público-Alvo e Personas

**Público primário:**  
- Jovens adultos (18–35 anos) que estão começando a organizar suas finanças.  
- Pessoas que não gostam de planilhas ou apps complexos, mas querem evitar dívidas e começar a poupar.  
- Usuários de bancos digitais que já têm familiaridade com experiências simplificadas.

**Persona exemplo:**  
**Ana, 26 anos, designer freelancer**  
- Ganha de forma irregular e quer controlar melhor os gastos.  
- Já tentou usar planilhas, mas abandonou por falta de tempo.  
- Usa WhatsApp diariamente e gosta de interações rápidas.  
- Precisa de dicas claras e um resumo simples de quanto pode gastar por semana.

---

## 4. Requisitos Funcionais

### 4.1 Registro de Gastos via Conversa
- O usuário deve poder informar despesas ou receitas em linguagem natural (texto ou voz).
- O sistema deve extrair automaticamente: valor, data (se não informada, assume a atual), descrição e categoria.
- Em caso de ambiguidade, o Agente pergunta de forma objetiva (“Esse valor é despesa ou receita?”).

### 4.2 Classificação Automática
- O app deve sugerir categorias baseadas no histórico e em palavras-chave (ex: “iFood” → Alimentação).
- O usuário pode confirmar ou ajustar a categoria, e o sistema aprende com a correção.

### 4.3 Metas Financeiras
- Permitir que o usuário defina metas (ex: “economizar R$ 500 em 3 meses”, “gastar no máximo R$ 200 com lazer por mês”).
- Acompanhar o progresso com mensagens de incentivo e alertas quando estiver próximo do limite.

### 4.4 Agente Financeiro (Dicas e Recomendações)
- O agente envia dicas proativas baseadas nos padrões de gasto (ex: “Você gastou 30% a mais com transporte neste mês. Que tal testar ir de bicicleta dois dias por semana?”).
- Sugere ajustes de meta e alerta sobre vencimentos de contas recorrentes.

### 4.5 Relatórios Simples e Personalizados
- Gerar relatórios sob demanda via comando: “me mostre quanto gastei com alimentação esse mês”.
- Visualizações básicas: gráfico de pizza por categoria, evolução de gastos no mês, comparativo com meses anteriores.
- Opção de exportar em texto ou imagem.

### 4.6 Lembretes e Periodicidade
- O usuário pode definir contas recorrentes (ex: “aluguel dia 5”) e receber lembretes para confirmar o pagamento.
- O app pode perguntar automaticamente sobre gastos recorrentes no final do mês.

---

## 5. Requisitos Não Funcionais

| Categoria | Descrição |
|-----------|-----------|
| **Usabilidade** | Interface conversacional limpa, sem jargões. O app deve guiar novos usuários com um tutorial interativo (primeiros passos). |
| **Desempenho** | Respostas rápidas (menos de 2s) para comandos comuns. Funcionalidade offline para consultas básicas (visualização de dados já sincronizados). |
| **Segurança e Privacidade** | Dados financeiros criptografados em trânsito e em repouso. Autenticação via biometria ou senha. Política de privacidade clara. |
| **Escalabilidade** | Arquitetura que permita adicionar futuramente integração com bancos (open finance) sem refatoração pesada. |
| **Plataformas** | MVP para iOS e Android (React Native ou Flutter). Backend com API RESTful. |
| **Design e Identidade Visual** | Layout universal (responsivo e adaptável a diferentes tamanhos de tela) com **detalhes de design futurista**: uso de gradientes suaves, tipografia moderna e limpa, animações sutis em microinterações, ícones com estilo neomórfico ou glassmorfismo, e paleta de cores que remeta a tecnologia e confiança (ex: tons escuros com acentos em azul ciano ou roxo neon). A experiência deve transmitir inovação sem sacrificar a clareza. |

---

## 6. MVP – Escopo Inicial

O MVP terá o foco de validar a experiência conversacional e o engajamento com o Agente Financeiro. As funcionalidades serão entregues em fases, mas o lançamento inicial incluirá:

### 6.1 Telas Principais

1. **Tela de Conversa (Chat)**  
   - Campo de entrada de texto/microfone.  
   - Bolhas de mensagens: usuário à direita, Agente à esquerda.  
   - Botões de ação rápida (“Registrar gasto”, “Ver resumo”, “Ajuda”).

2. **Tela de Resumo Simplificado**  
   - Acessada via comando ou ícone.  
   - Mostra: saldo atual (se informado), total de despesas do mês, categoria com maior gasto, progresso da meta principal.

3. **Tela de Metas**  
   - Lista de metas ativas e concluídas.  
   - Barra de progresso e botão para criar nova meta com suporte a linguagem natural (ex: “quero juntar R$ 1000 até dezembro”).

4. **Tela de Relatórios**  
   - Visualização simples com gráficos interativos (tocar no gráfico para detalhes).  
   - Filtros rápidos por período (semana, mês) e categoria.

5. **Tela de Configurações**  
   - Categorias personalizáveis, notificações, vínculo de contas recorrentes, logout.

### 6.2 Recursos Necessários (Tecnologia)

- **Frontend Mobile:** React Native (para reaproveitamento em iOS/Android).  
- **Backend:** Node.js + Express ou Python (Django/FastAPI) para API.  
- **Banco de Dados:** PostgreSQL (estruturado) + MongoDB ou similar para logs de conversa não estruturados.  
- **Processamento de Linguagem Natural:** Inicialmente usar um modelo de classificação simples (ex: integração com API de NLP como Dialogflow ou uma solução própria com spaCy) para extrair valor, data, categoria.  
- **Machine Learning (para classificação e dicas):** Modelo inicial baseado em regras + aprendizado com feedback do usuário.  
- **Autenticação:** Firebase Auth ou Auth0.  
- **Armazenamento:** Supabase (para simplificar) ou AWS.  

### 6.3 Equipe Mínima Recomendada

- 1 Product Manager / UX Writer  
- 1 Designer de UI/UX  
- 2 Desenvolvedores mobile (React Native)  
- 2 Desenvolvedores backend  
- 1 Engenheiro de ML/Dados (pode ser consultor no início)

---

## 7. Validação Inicial

Antes de investir em desenvolvimento completo, recomenda-se um **teste de conceito** para mitigar riscos.

### 7.1 Protótipo Navegável
- Criar um protótipo interativo (Figma) do fluxo conversacional e testar com 10–15 pessoas da persona definida.  
- Coletar métricas de usabilidade: tempo para registrar um gasto, satisfação com a linguagem, clareza das recomendações.

### 7.2 MVP com Usuários Reais
- Lançar o MVP para um grupo fechado (50–100 usuários) via TestFlight/Play Store interna.  
- Duração: 4 semanas.  
- Métricas de validação:
  - **Engajamento:** número de transações registradas por usuário ativo semanal; percentual de usuários que retornam após 7 dias.
  - **Conversão:** quantos usuários definem pelo menos uma meta.
  - **NPS (Net Promoter Score)** após 2 semanas.
  - **Taxa de uso da conversa:** quantos comandos são feitos por chat vs. navegação manual.

### 7.3 Feedback Qualitativo
- Realizar entrevistas com usuários que abandonaram ou usaram pouco para entender barreiras.  
- Validar se a classificação automática reduziu o esforço de entrada.

---

## 8. Critérios de Sucesso do MVP

Para considerar o MVP bem-sucedido e partir para as próximas fases (integração com bancos, versão web, etc.), os seguintes critérios devem ser atingidos:

1. **Usabilidade:** 80% dos usuários conseguem registrar um gasto em menos de 30 segundos sem ajuda externa.  
2. **Retenção:** Taxa de retenção D7 (7 dias) ≥ 40% entre usuários ativos.  
3. **Classificação automática:** Pelo menos 70% das transações são categorizadas corretamente na primeira tentativa (com confirmação do usuário).  
4. **Satisfação:** NPS ≥ 50 entre os usuários do grupo piloto.  
5. **Comportamento desejado:** Pelo menos 30% dos usuários criam uma meta financeira no primeiro mês de uso.

---

## 9. Próximos Passos

Após a validação do MVP, recomenda-se:

- Evoluir o modelo de linguagem para entender melhor contextos e oferecer dicas mais assertivas.  
- Implementar integração com Open Finance (para importação automática de transações bancárias).  
- Criar versão web para acesso via navegador.  
- Adicionar suporte a múltiplos idiomas e exportação para Excel.

---

*Este PRD serve como guia para alinhamento da equipe e deve ser revisitado conforme aprendizados do MVP.*
