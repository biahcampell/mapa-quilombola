# 📁 Entregas da Disciplina: Modelagem de Sistemas
*IFMA Campus Itapecuru-Mirim*

---

## 👁️ 1. Atividade: Roteiro e Plano de Coleta

### 📑 1. Objetivo da Coleta
O que exatamente o grupo precisa descobrir nesta fase? Defina o foco da investigação.

### 👥 2. Perfil do Stakeholder
Com quem vocês vão falar? Liste os perfis (ex: Morador, Gestor, Aluno) e por que eles são importantes.

### 📋 3. Roteiro de Perguntas
* Elabore de 8 a 10 perguntas abertas.
* Evite induzir respostas.
* Foque em Contexto, Processo e Problema.

### 📅 4. Plano de Ação
* Quem fará a entrevista/observação?
* Onde e quando ela ocorrerá?
* Como os dados serão registrados?

---

## 💻 2. Documento README.md (Template Sugerido)

### ❓ Perguntas Fundamentais Respondidas
1. **Qual problema o projeto resolve?**
   O sistema resolve a falta de automatização e o controle ineficiente de processos manuais (como o uso de planilhas de papel ou controles descentralizados). Ele centraliza as informações, otimiza o tempo de execução das tarefas e fornece relatórios claros para ajudar na tomada de decisões dos gestores no território.
2. **Como rodar a solução localmente?**
   * Clone o repositório (`git clone <url>`).
   * Acesse a pasta e instale as dependências (`npm install` ou equivalente).
   * Execute o comando de desenvolvimento (`npm run dev`).
3. **Onde estão os documentos e diagramas?**
   Toda a parte de engenharia e modelagem está concentrada na pasta `docs/diagramas/` e `docs/requisitos.md`.
4. **Quem são os autores e responsáveis?**
   Desenvolvido pela equipe do projeto na disciplina de Modelagem de Sistemas.

---

## 📑 3. Atividade: Primeira Lista Rastreável

### 📊 Template de Entrega

| ID | DESCRIÇÃO DO REQUISITO | TIPO | PRIOR. |
| :--- | :--- | :---: | :---: |
| **RF01** | O sistema deve permitir que os alunos realizem o upload do arquivo `README.md` diretamente no repositório do projeto. | RF | Alta |
| **RF02** | O sistema deve enviar uma notificação automática para o orientador quando um novo documento for postado. | RF | Média |
| **RNF01** | O sistema deve garantir que o tempo de carregamento de qualquer página de entrega não ultrapasse 3 segundos. | RNF | Alta |
| **RNF02** | O sistema deve ser responsivo, adaptando-se automaticamente a telas de smartphones e tablets. | RNF | Média |

### 🎫 Ticket de Saída

**Qual foi a maior dificuldade em transformar a "fala solta" do usuário em um requisito técnico estruturado?**

> **Resposta do Grupo:**
> A maior dificuldade foi remover a subjetividade e a ambiguidade da linguagem do usuário para traduzi-la em termos puramente técnicos, acionáveis e testáveis. Adaptar essa fala à estrutura rígida de *"O sistema deve [ação] [objeto]"* exige um grande esforço analítico para **[ação] separar** de forma clara **[objeto] as funcionalidades diretas do sistema (RF) das restrições ou regras de negócio externas (RNF)**.
> 