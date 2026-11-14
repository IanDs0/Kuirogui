# Sistema de Gestão de Alunos — Escopo e Orçamento

Plataforma para gerenciamento de alunos, planos, mensalidades, promoções e controle de presença, com visão centralizada de quem está em dia, quem está atrasado e quem cancelou a matrícula.

O sistema **não processa pagamentos**: ele faz o controle administrativo, guarda o histórico financeiro informado pelo gestor e gera notificações de mensalidades pendentes.

---

## 1. Escopo do projeto

### 1.1. Incluído no sistema base

| Módulo | O que entrega |
|---|---|
| **Cadastro de alunos** | Cadastro, edição e consulta; campos configuráveis; situação cadastral (ativo, cancelado, suspenso); histórico individual completo. O cancelamento não apaga cadastro nem histórico. |
| **Planos** | Criação e gestão de planos (nome, valor, periodicidade, frequência permitida, situação); histórico de alterações de preço; troca de plano por aluno. Alterações de preço não afetam pagamentos já registrados. |
| **Promoções** | Desconto percentual ou fixo, período de validade, planos participantes, limite de utilizações; registro da promoção aplicada a cada aluno. |
| **Painel geral de alunos** | Listagem central com cores (verde: pago; vermelho: atrasado; cinza: cancelado), pesquisa por nome e CPF, filtros por plano, situação e período de matrícula. |
| **Controle de pagamentos** | Registro manual de pagamentos; histórico permanente; renovação lógica todo dia 1; exceção para matrículas feitas após o dia 1; notificações de inadimplência sem duplicidade. |
| **Presença** | Registro de entrada; consulta diária, semanal e mensal; percentual de frequência; relatórios de baixa frequência e horários de maior movimento. |
| **Usuários e permissões** | Autenticação; perfis Administrador, Gerente e Funcionário com permissões configuráveis; registro do usuário responsável por cada operação. |
| **Configurações gerais** | Dados do estabelecimento, vencimentos, notificações, usuários e permissões. |

### 1.2. Requisitos técnicos

- Interface responsiva para computador, tablet e celular.
- Datas e horários no padrão brasileiro (DD/MM/AAAA, HH:mm), fuso America/Sao_Paulo; armazenamento em UTC ou com timezone.
- Registro de auditoria das operações importantes.
- Rotina automática de atualização das competências mensais.
- Proteção de dados pessoais.
- Consistência entre cadastro, financeiro e frequência.

### 1.3. Fora do escopo

- Processamento de pagamentos, cobrança automática e emissão de boletos.
- Matrícula pública por link e cadastro por sistemas externos.
- API pública para terceiros.
- Aplicativo próprio para alunos.
- Integração com catracas e PIN de acesso: orçada à parte, depois de definido o equipamento, pois depende da API ou do protocolo do fabricante.

O painel do aluno não faz parte do sistema base e pode ser contratado como extra (fase 2), conforme a seção 3.

---

## 2. Modalidades de contratação

| | Compra | Assinatura |
|---|---|---|
| Código-fonte | Fica com o cliente, com direito de uso, modificação e revenda | Fica com o desenvolvedor; o cliente tem direito de uso enquanto pagar |
| Sistema base | R$ 4.500 – 9.000 (único) | Sem custo de entrada |
| Implantação | R$ 300 (único) | R$ 300 (único) |
| Mensalidade | Hospedagem + backup (R$ 200) e manutenção à escolha | R$ 400 – 600/mês, com hospedagem, backup na nuvem e manutenção Essencial |
| Contrato mínimo | — | 12 meses |
| No cancelamento | O cliente segue com o sistema | Acesso encerrado; o cliente recebe a exportação dos seus dados |

A implantação cobre instalação, configuração, carga inicial de dados e treinamento.

Em qualquer modalidade, os dados são do cliente.

### 2.1. Direitos do cliente na compra

Quem compra o sistema recebe o código-fonte completo e pode usá-lo como quiser:

- Usar no próprio estabelecimento, sem mensalidade de uso.
- Modificar o código por conta própria ou com outro desenvolvedor.
- Revender o sistema a terceiros e cobrar mensalidade de quem quiser usá-lo.

Junto com a implantação, o cliente recebe um tutorial de instalação e de uso, o que permite instalar o sistema em outros locais sem depender do desenvolvedor.

Depois da entrega, o único valor cobrado pelo desenvolvedor é a manutenção do código, que é opcional e segue os planos da seção 5. Cada plano de manutenção cobre uma instalação do sistema.

---

## 3. Extras de valor único

Valem para as duas modalidades.

| Item | Valor |
|---|---|
| Backup local (rotina diária automática e teste de restauração) | R$ 300 – 500 |
| Acesso remoto (configuração de domínio, DNS e HTTPS) | Domínio + R$ 150 |
| Design personalizado | R$ 100 – 150 por tela, com 2 rodadas de revisão incluídas |
| Alteração após a aprovação do design final | R$ 50 – 130 por alteração, conforme o tamanho |
| Painel do aluno (fase 2): login do aluno e consulta de mensalidades e presença | R$ 1.500 – 3.000 |

---

## 4. Custos recorrentes

| Item | Valor |
|---|---|
| Hospedagem + backup na nuvem (só na compra; na assinatura já está incluso) | R$ 200/mês |
| Domínio próprio | Cerca de R$ 40/ano (.com.br), repassado ao cliente |
| E-mail profissional | Domínio + valor por caixa de e-mail, conforme a quantidade |

---

## 5. Planos de manutenção

| Plano | O que inclui | Valor |
|---|---|---|
| **Essencial** | Correção de bugs e segurança, sem novas funcionalidades | R$ 150/mês (incluso na assinatura) |
| **Melhorias pequenas** | Essencial + até 3 h/mês de desenvolvimento | R$ 300/mês |
| **Melhorias médias** | Essencial + até 8 h/mês de desenvolvimento | R$ 600/mês |
| **Projeto grande** | Uma funcionalidade de grande porte; contrato mínimo de 6 meses | R$ 500 – 1.300/mês |
| **Completo** | Desenvolvimento de qualquer funcionalidade, até 30 h/mês; contrato mínimo de 6 meses | A partir de R$ 2.000/mês |
| **Hora excedente** | Horas acima do limite do plano | R$ 70 – 100/h |

Na assinatura, o upgrade de plano custa a diferença em relação ao Essencial (por exemplo, R$ 150 a mais para o plano de melhorias pequenas).

---

## 6. Condições gerais

- **Pagamento (compra):** 40% na assinatura do contrato, 30% na entrega da primeira versão e 30% na implantação.
- **Alterações de escopo:** qualquer funcionalidade não descrita na seção 1.1 é orçada à parte ou atendida pelas horas do plano de manutenção.
- **Faixas de valor:** o valor final dentro de cada faixa depende do detalhamento fechado com o cliente (campos, relatórios, número de telas e de usuários).
- **Custos de terceiros:** domínio e caixas de e-mail são cobrados pelos provedores e repassados sem acréscimo.
