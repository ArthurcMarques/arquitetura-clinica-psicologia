# Documento Unificado de Requisitos – Sistema de Gestão para Clínica de Psicologia

## 1. Requisitos Funcionais (RF)

### 1.1 Gestão de Pacientes e Cadastros
- **RF01**: O sistema deve permitir o cadastro completo de pacientes (dados pessoais, contato).
- **RF02**: O sistema deve identificar e tratar adequadamente os casos de pacientes atendidos por planos de saúde. (retirei das entrevistas)
- **RF03**: O paciente deve poder visualizar e solicitar atualização de seus dados via portal.  
- **RF04**: O sistema deve registrar o consentimento explícito do paciente para tratamento de dados, com data e versão dos termos.  
- **RF05**: O sistema deve permitir anexar e armazenar documentos de registro da clínica (CNPJ, alvarás, CRP etc.).
- **RF06**: O sistema deve permitir cadastrar modalidade de atuação (PJ ou consultório individual) e documentação obrigatória.  
- **RF07**: O sistema deve permitir cadastro e gestão da documentação do psicólogo (CRP, certidões, diplomas).  
- **RF08**: O sistema deve emitir alertas sobre vencimento/renovação de documentos obrigatórios da clínica e do profissional.
- **RF09**: Toda alteração relevante de cadastro deve ser requerida/autorizada pelo detentor do cadastro e documentada automaticamente descrevendo o usuário que realizou a alteração.

### 1.2 Agendamento e Atendimento
- **RF10**: O sistema deve permitir agendar, reagendar e cancelar consultas (clínica ou paciente).  
- **RF11**: O sistema deve suportar agendamento rotineiro (recorrente semanal, quinzenal, etc.).  
- **RF12**: O sistema deve permitir visualização da agenda em múltiplas visões (dia, semana, mês, profissional designado, tipo de atendimento).  
- **RF13**: O sistema deve permitir integração da agenda pessoal do psicólogo com a clínica.  
- **RF14**: O sistema deve notificar pacientes sobre horários vagos (lista de espera).  
- **RF15**: O sistema deve enviar lembretes automáticos e solicitar confirmação de consultas (WhatsApp, e-mail, ligação).  
- **RF16**: O sistema deve permitir ao profissional registrar situações de urgência (ex.: ausência do profissional, falha técnica), notificando automaticamente os pacientes afetados e suspendendo agendamentos relacionados.

### 1.3 Prontuários e Documentação Clínica
- **RF17**: O sistema deve permitir criação, atualização e arquivamento de prontuários eletrônicos.  
- **RF18**: O sistema deve permitir registro documental da evolução das sessões.
- **RF19**: O sistema deve impedir a edição de registros clínicos anteriores, permitindo apenas acréscimos de complementos ou retificações devidamente documentadas.
- **RF20**: O prontuário deve permitir anexar arquivos (PDF, imagens, testes, exames), juntos ao prontuário ou avulsos.
- **RF21**: O sistema deve permitir utilização de templates padronizados (ex.: anamnese, acompanhamento semestral).  
- **RF22**: O sistema deve gerar automaticamente modelo com a estrutura do rascunho de prontuário, após consulta.  
- **RF23**: O sistema deve permitir que o Psicólogo(a) preencha a estrutura do pré-prontuário com as informações.  
- **RF24**: O sistema deve analisar o pré-prontuário preenchido e gerar, com auxílio de IA, um prontuário melhorado.  
- **RF25**: O sistema deve consultar se há algum encaminhamento; se sim, deve ser sinalizado e anexado o encaminhamento nesta parte, junto com a devida justificativa.  
- **RF26**: O sistema deve sugerir a inclusão de "Ocorrências" após o relatório, para colocar qualquer ocorrência que não se encaixe no padrão de prontuário, mas seja relevante (não obrigatória).  
- **RF27**: O sistema deve permitir ao Psicólogo(a) editar o rascunho de prontuário gerado por IA e deferi-lo ou indeferi-lo para arquivamento no sistema.  
- **RF28**: O sistema deve analisar evolução e gerar estatísticas de termos mais citados e impressões dos prontuários.  
- **RF29**: O sistema deve permitir diferenciar atendimento presencial e online.
- **RF30**: A IA não pode gerar conteúdo clínico novo.

### 1.4 Teleatendimento
- **RF31**: O sistema deve permitir registro de atendimentos online (Google Meet, Zoom etc.).  
- **RF32**: O sistema deve registrar consentimento do paciente para atendimentos virtuais.
- **RF33**: O sistema deve armazenar logs dos atendimentos online (data, horário, link e duração), sem gravar conteúdo da sessão.

### 1.5 Controle Financeiro
- **RF34**: O sistema deve permitir registro de pagamentos por sessão ou pacotes.  
- **RF35**: O sistema deve permitir emissão e envio de recibos e notas fiscais.  
- **RF36**: O sistema deve permitir relatórios financeiros (faturamento, gastos, pendências).  
- **RF37**: O sistema deve permitir envio de links de cobrança.  
- **RF38**: O sistema deve permitir emissão de recibos em lote.  
- **RF39**: O sistema deve prever integração futura com gateways de pagamento online.  

### 1.6 Comunicação e Portal do Paciente
- **RF40**: O paciente deve poder solicitar agendamentos e cancelamentos online.  
- **RF41**: O paciente deve poder visualizar próximos agendamentos e histórico.  
- **RF42**: O paciente deve poder visualizar histórico financeiro e baixar recibos.  
- **RF43**: O sistema deve permitir envio de avisos gerais aos pacientes.
- **RF44**: O sistema deve dar opção ao adm de ativar mensagens (se tiver whatsapp API registrado), para encaminhar mensagens ao paciente.

### 1.7 Administração e Relatórios
- **RF45**: O sistema deve permitir que o administrador crie categorias de acesso às funcionalidades (para separar permitidos à administrativo, financeiro, estagiário, psicólogo, etc.).  
- **RF46**: O sistema deve gerar relatórios financeiros e de atendimento (faturamento, faltas, taxa de adesão).  
- **RF47**: O sistema deve gerar relatórios estatísticos anonimizados (ex.: faixa etária, recorrência de consultas).

### 1.8 Área de ajuda
- **RF48**: O sistema deve permitir que usuários relatem erros, solicitem auxílio técnico e reportem ocorrências graves(Fonte: Questionário)

---

## 2. Requisitos Não Funcionais (RNF)

### 2.1 Segurança e Privacidade
- **RNF01**: Todos os dados sensíveis devem ser criptografados, utilizando algoritmos criptográficos robustos, em banco e transmissão.  
- **RNF02**: Acesso deve ser restrito por perfil; prontuários só acessíveis pelo responsável.  
- **RNF03**: O sistema deve registrar logs de auditoria de acesso/modificação.  
- **RNF04**: O sistema deve ser acessível somente com autenticação de dois fatores (2FA).  
- **RNF05**: O sistema deve permitir exportação segura dos dados de pacientes.  
- **RNF06**: O sistema deve permitir políticas de arquivamento/exclusão conforme LGPD.  
- **RNF07**: O sistema deve garantir a guarda mínima de prontuários por 5 anos.  
- **RNF08**: O sistema deve garantir confidencialidade e integridade de documentos profissionais e informações financeiras.  

### 2.2 Usabilidade
- **RNF09**: A interface deve ser clara, intuitiva e de fácil uso para todos os perfis.  
- **RNF10**: O design deve ser clean, com cores aconchegantes e foco em funcionalidades principais.  
- **RNF11**: O sistema deve reduzir retrabalho em tarefas administrativas.
- **RNF12**: O sistema deve oferecer tutoriais ou onboarding interativo para novos usuários.

### 2.3 Portabilidade e Acessibilidade
- **RNF13**: O sistema deve ser acessível pelos principais navegadores.  
- **RNF14**: O sistema deve ser responsivo (desktop, tablet, celular).  
- **RNF15**: O sistema deve permitir integração futura com múltiplos dispositivos.
- **RNF16**: A interface deve seguir diretrizes de acessibilidade

### 2.4 Confiabilidade e Desempenho
- **RNF17**: O sistema deve ter alta disponibilidade (mínimo 99,5% de uptime mensal.).  
- **RNF18**: O sistema deve executar operações em tempo hábil (consultas, salvamentos).  
- **RNF19**: O sistema deve realizar análises automáticas em tempo real para feedback imediato.  
```
