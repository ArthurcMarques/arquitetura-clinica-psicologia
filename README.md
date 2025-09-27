# Requisitos Consolidados do Sistema – Clínica de Psicologia

---

## 🔹 Requisitos Funcionais

### RF01 - Cadastro de pacientes
O sistema deve permitir o cadastro completo dos pacientes, incluindo dados pessoais (nome, CPF, endereço, telefone, e-mail), informações clínicas relevantes, histórico de atendimentos e preferências de contato.  
**Origem:** Entrevista / PsicoManager

---

### RF02 - Cadastro de profissionais de psicologia
O sistema deve permitir que psicólogos e outros profissionais da clínica sejam cadastrados, com dados de identificação, especialidade, disponibilidade de agenda e documentação exigida pelo conselho de classe.  
**Origem:** Entrevista / PsicoManager

---

### RF03 - Agendamento de consultas
O sistema deve possibilitar agendar, remarcar e cancelar consultas, tanto pela clínica quanto pelos próprios pacientes, respeitando as disponibilidades de cada profissional.  
**Origem:** Entrevista / Sintropia / PsicoManager

---

### RF04 - Confirmação de consultas e envio de lembretes
O sistema deve enviar automaticamente confirmações e lembretes de consultas aos pacientes (via WhatsApp, e-mail ou SMS), de forma configurável.  
**Origem:** Entrevista / Sintropia

---

### RF05 - Sincronização com Google Agenda
O sistema deve integrar-se com o Google Agenda, permitindo que os compromissos registrados na clínica sejam automaticamente refletidos na agenda pessoal do profissional.  
**Origem:** Sintropia

---

### RF06 - Controle financeiro
O sistema deve gerenciar as finanças da clínica, incluindo:
- Registro de receitas e despesas  
- Emissão de relatórios mensais  
- Comparativos de crescimento e desempenho  

**Origem:** Entrevista / PsicoManager / Sintropia

---

### RF07 - Gestão de cobranças e emissão de notas fiscais/recibos
O sistema deve permitir o envio de cobranças automáticas e emissão de notas fiscais ou recibos digitais, enviados diretamente ao paciente.  
**Origem:** Entrevista / PsicoManager

---

### RF08 - Cobrança diferenciada
O sistema deve possibilitar a configuração de diferentes modalidades de cobrança: sessões avulsas, pacotes de atendimento, convênios e planos.  
**Origem:** PsicoManager

---

### RF09 - Prontuário eletrônico do paciente
O sistema deve permitir o registro eletrônico das sessões realizadas, contendo anotações, testes aplicados, evoluções e documentos relacionados ao paciente.  
**Origem:** Entrevista / Sintropia / PsicoManager

---

### RF10 - Geração automática de evoluções de prontuário com IA
O sistema deve auxiliar o psicólogo na elaboração do prontuário, utilizando inteligência artificial para sugerir resumos e evoluções clínicas das sessões.  
**Origem:** Sintropia

---

### RF11 - Histórico clínico consolidado
O sistema deve manter um histórico detalhado de cada paciente, incluindo todas as anotações, consultas passadas, documentos anexados e relatórios.  
**Origem:** Entrevista / PsicoManager

---

### RF12 - Anamnese estruturada
O sistema deve oferecer formulários de anamnese padronizados (primeira consulta, revisão semestral, revisão anual, encerramento) para facilitar a coleta sistemática de informações.  
**Origem:** Entrevista / PsicoManager

---

### RF13 - Planos de ação e escalas
O sistema deve permitir que o psicólogo elabore planos de ação e escalas de acompanhamento e os envie diretamente ao paciente para execução e acompanhamento.  
**Origem:** Sintropia

---

### RF14 - Registro de diário emocional / pensamentos pelo paciente
O sistema deve oferecer ao paciente a possibilidade de registrar diariamente pensamentos, emoções ou eventos relevantes, que serão armazenados em seu prontuário.  
**Origem:** Sintropia / PsicoManager

---

### RF15 - Aplicativo ou área do paciente
O sistema deve fornecer uma interface voltada ao paciente, onde ele poderá:
- Consultar suas próximas sessões  
- Reagendar ou cancelar consultas  
- Acompanhar pagamentos e recibos  
- Registrar seu humor ou pensamentos  

**Origem:** PsicoManager

---

### RF16 - Relatórios e estatísticas
O sistema deve gerar relatórios de desempenho clínico e financeiro, incluindo: número de atendimentos por período, evolução de pacientes, comparativos financeiros e indicadores de crescimento.  
**Origem:** Entrevista / PsicoManager

---

### RF17 - Gestão multiusuário
O sistema deve permitir diferentes perfis de acesso (psicólogo, administrador da clínica, recepcionista), cada um com permissões específicas para uso da plataforma.  
**Origem:** PsicoManager

---

### RF18 - Ferramentas de marketing e divulgação
O sistema deve incluir funcionalidades de apoio à divulgação de serviços da clínica em redes sociais e outros canais digitais, de forma integrada.  
**Origem:** Sintropia

---

## 🔹 Requisitos Não Funcionais

### RNF01 - Segurança e privacidade de dados
O sistema deve estar em conformidade com a LGPD, garantindo confidencialidade, criptografia dos dados sensíveis e consentimento explícito do paciente para uso das informações.  
**Origem:** Entrevista / Sintropia / PsicoManager

---

### RNF02 - Usabilidade e interface intuitiva
O sistema deve apresentar uma interface simples, clara, aconchegante e intuitiva, tanto para profissionais quanto para pacientes.  
**Origem:** Entrevista / Sintropia / PsicoManager

---

### RNF03 - Performance e rapidez
Operações críticas, como geração de prontuário e carregamento de agendas, devem ocorrer em poucos segundos, sem causar lentidão ao usuário.  
**Origem:** Sintropia

---

### RNF04 - Disponibilidade e confiabilidade
O sistema deve ser hospedado em nuvem, com alta disponibilidade e backup contínuo, garantindo acesso seguro e sem interrupções aos profissionais.  
**Origem:** PsicoManager

---

### RNF05 - Acesso multiplataforma
O sistema deve poder ser acessado de navegadores em computadores, tablets e celulares, com possibilidade de aplicativos móveis nativos.  
**Origem:** Entrevista / Sintropia / PsicoManager

---

### RNF06 - Flexibilidade e parametrização
O sistema deve permitir a configuração de políticas financeiras (tipos de cobrança, convênios, pacotes) e personalização de formulários clínicos de acordo com a necessidade do profissional.  
**Origem:** PsicoManager

---

### RNF07 - Suporte técnico e treinamento
O sistema deve oferecer suporte ao usuário, com canais de atendimento e materiais de treinamento para auxiliar a clínica no uso inicial e no dia a dia.  
**Origem:** PsicoManager

---

## 📊 Matriz de Rastreabilidade 

| ID    | Requisito                                                         | Tipo | Origem                             |
|-------|-------------------------------------------------------------------|------|------------------------------------|
| RF01  | Cadastro de pacientes                                             | RF   | Entrevista / PsicoManager          |
| RF02  | Cadastro de profissionais de psicologia                           | RF   | Entrevista / PsicoManager          |
| RF03  | Agendamento de consultas (agendar, remarcar, cancelar)            | RF   | Entrevista / Sintropia / PsicoManager |
| RF04  | Confirmação e envio automático de lembretes                       | RF   | Entrevista / Sintropia             |
| RF05  | Integração com Google Agenda                                      | RF   | Sintropia                          |
| RF06  | Controle financeiro (receitas, despesas, relatórios)              | RF   | Entrevista / Sintropia / PsicoManager |
| RF07  | Gestão de cobranças, emissão de notas fiscais/recibos             | RF   | Entrevista / PsicoManager          |
| RF08  | Cobrança diferenciada (avulsas, pacotes, convênios, planos)       | RF   | PsicoManager                       |
| RF09  | Prontuário eletrônico do paciente                                 | RF   | Entrevista / Sintropia / PsicoManager |
| RF10  | Geração automática de evoluções de prontuário com IA              | RF   | Sintropia                          |
| RF11  | Histórico clínico consolidado                                     | RF   | Entrevista / PsicoManager          |
| RF12  | Anamnese estruturada (primeira consulta, revisões, encerramento)  | RF   | Entrevista / PsicoManager          |
| RF13  | Planos de ação e escalas de acompanhamento                        | RF   | Sintropia                          |
| RF14  | Registro de diário emocional /
# arquitetura-clinica-psicologia
Documentação do projeto da disciplina Arquitetura e Desenho de Software
