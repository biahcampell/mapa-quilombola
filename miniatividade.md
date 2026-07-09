# Miniatividade: Casos de Uso Detalhados
## Disciplina: Modelagem de Sistemas
### Instituto Federal do Maranhão (IFMA) - Campus Itapecuru-Mirim

---

## 👥 Identificação do Grupo
* **Componentes:**
  * [Nome do Aluno 1]
  * [Nome do Aluno 2]
  * [Nome do Aluno 3]
* **Tema do Sistema:** [Exemplo: Sistema de Gestão de Vendas e Clientes]

---

## 1. Requisito Funcional (RF) Selecionado
* **Código:** RF-001 (Exemplo)
* **Nome:** Efetuar Cadastro de Cliente
* **Descrição:** O sistema deve permitir o cadastro de novos clientes na plataforma, validando as informações obrigatórias e garantindo a unicidade do CPF.

---

## 2 & 3. Dicionário de Dados (v1)
Tabela contendo o mapeamento dos dados identificados e utilizados pelo requisito funcional selecionado.

| Nome do Campo | Tipo de Dado | Tamanho / Formato | Descrição | Obrigatoriedade |
| :--- | :--- | :--- | :--- | :--- |
| `id_cliente` | Inteiro | Auto-incremento | Identificador único do cliente no banco de dados. | Obrigatório |
| `nome_completo`| Texto | 100 caracteres | Nome completo do cliente. | Obrigatório |
| `cpf` | Texto | `000.000.000-00` | Cadastro de Pessoa Física (deve ser único). | Obrigatório |
| `email` | Texto | 80 caracteres | Endereço de e-mail para login e notificações. | Obrigatório |
| `telefone` | Texto | `(00) 00000-0000` | Número de telefone celular para contato. | Opcional |
| `data_cadastro`| Data/Hora | `DD/MM/AAAA HH:MM`| Registro automático do momento do cadastro. | Obrigatório |

---

## 4. Lista de Casos de Uso Candidatos
Com base no escopo e nos requisitos do módulo, foram mapeados 3 casos de uso candidatos:
1. **UC-001:** Cadastrar Cliente *(Selecionado para detalhamento)*
2. **UC-002:** Alterar Dados do Cliente
3. **UC-003:** Inativar Cadastro de Cliente

---

## 5. Detalhamento do Caso de Uso (UC-001)

| Campo | Detalhamento Técnico |
| :--- | :--- |
| **Caso de Uso** | UC-001: Cadastrar Cliente |
| **Ator Principal** | Atendente / Administrador |
| **Objetivo** | Permitir a inclusão de um novo cliente no banco de dados para habilitar vendas e emissão de ordens de serviço. |
| **RF Relacionado** | RF-001 |
| **Pré-condição** | O usuário deve estar autenticado no sistema com perfil autorizado (Atendente ou Admin). |
| **Pós-condição** | O registro do cliente é salvo na base de dados e uma mensagem de confirmação é exibida. |
| **Dados Usados** | `nome_completo`, `cpf`, `email`, `telefone`, `data_cadastro` (conforme Dicionário de Dados v1). |

### 🔄 Fluxo de Eventos

#### A. Fluxo Básico (Caminho Feliz)
1. O ator acessa o menu "Clientes" e clica no botão "Novo Cadastro".
2. O sistema exibe o formulário de cadastro em branco.
3. O ator preenche as informações obrigatórias (`nome_completo`, `cpf`, `email`).
4. O ator clica no botão "Salvar".
5. O sistema valida o preenchimento de todos os campos obrigatórios.
6. O sistema executa a validação matemática do dígito verificador do CPF.
7. O sistema consulta o banco de dados e verifica que o CPF informado não é duplicado.
8. O sistema persiste os dados na base de dados e gera automaticamente o `id_cliente` e a `data_cadastro`.
9. O sistema exibe a mensagem de sucesso: *"Cliente cadastrado com sucesso!"*.
10. O sistema limpa o formulário e encerra o caso de uso.

#### B. Fluxos Alternativos e de Exceção

##### FA01 - Campos Obrigatórios Não Preenchidos (No passo 5)
1. O sistema identifica que um ou mais campos obrigatórios estão vazios.
2. O sistema destaca em vermelho os campos não preenchidos.
3. O sistema exibe o alerta: *"Por favor, preencha todos os campos obrigatórios marcados com (*)."*
4. O sistema retorna ao passo 3 do Fluxo Básico.

##### FA02 - CPF Inválido (No passo 6)
1. O sistema identifica que a estrutura do CPF ou seus dígitos verificadores são matematicamente inválidos.
2. O sistema exibe a mensagem de erro: *"CPF informado é inválido. Por favor, verifique os dados."*
3. O sistema retorna ao passo 3 do Fluxo Básico com os campos preenchidos para correção.

##### FA03 - CPF Duplicado (No passo 7)
1. O sistema detecta que o CPF informado já está registrado em outra conta de cliente.
2. O sistema impede a gravação dos dados para evitar duplicidade.
3. O sistema exibe a mensagem de erro: *"Erro: Já existe um cliente cadastrado com este CPF."*
4. O sistema retorna ao passo 3 do Fluxo Básico.

### ⚠️ Regras de Negócio (RN)
* **RN01 - Unicidade de CPF:** É estritamente proibido haver mais de um registro ativo com o mesmo CPF na base de dados do sistema.
* **RN02 - Validação de E-mail:** O campo de e-mail deve obedecer obrigatoriamente à máscara padrão de mercado (`exemplo@dominio.com`).

### ✅ Critérios de Aceitação (CA)
* **CA01:** O formulário não deve permitir o envio (submissão) se houver algum campo obrigatório vazio.
* **CA02:** O tempo de resposta para a gravação dos dados no banco e exibição da mensagem de sucesso deve ser inferior a 2 segundos.

---

## 🤖 Log de Uso da IA
* **Ferramenta Utilizada:** Gemini (Google)
* **Prompts Enviados pelo Grupo:**
  1. *"Ajude-nos a estruturar a miniatividade de Casos de Uso Detalhados com base na imagem do slide da aula de Modelagem de Sistemas do IFMA."*
  2. *"Gere um template completo em formato Markdown contendo a estrutura da entrega: Dicionário de Dados v1, Lista de Casos de Uso Candidatos, Detalhamento de 1 Caso de Uso com Fluxos, Regras de Negócio, Critérios de Aceitação e o Log da IA."*
* **Análise de Contribuição:** A IA acelerou a criação do documento técnico gerando uma estrutura limpa e um cenário de exemplo realista (Cadastro de Clientes). Isso serviu como guia didático para o grupo compreender a amarração prática entre dicionário de dados, requisitos e fluxos textuais.