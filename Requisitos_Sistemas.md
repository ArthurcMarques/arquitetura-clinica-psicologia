# Levantamento de Requisitos - Sistemas Análogos

Este documento contém os requisitos levantados a partir da análise de sistemas existentes no mercado (PsicoManager, Sintropia) e de processos de negócio observados em clínicas de psicologia.

---

## Requisitos Funcionais (RF)

### Gestão de Pacientes e Cadastros
- **RF01**: O sistema deve permitir o cadastro completo dos pacientes, contendo dados pessoais e de contato.  
- **RF02**: O paciente deve poder visualizar e solicitar atualização de seus dados cadastrais (telefone, endereço) através de um portal.  

### Agendamento e Atendimento
- **RF03**: O sistema deve permitir agendar, reagendar e cancelar consultas, com visualização diária, semanal e mensal.  
- **RF04**: A agenda deve permitir a marcação de diferentes status para a consulta (confirmada, realizada, cancelada, falta).  
- **RF05**: A agenda deve permitir o agendamento de sessões recorrentes para um paciente por um período determinado.  
- **RF06**: O sistema deve possuir lista de espera para notificar pacientes quando um horário se torna vago.  
- **RF07**: O sistema deve permitir a visualização da agenda de múltiplos psicólogos e o agendamento de salas.  
- **RF08**: O profissional deve poder bloquear horários em sua agenda para compromissos pessoais.  

### Prontuários e Documentação Clínica
- **RF09**: O sistema deve permitir que o psicólogo crie documentos (declarações, atestados, encaminhamentos) associados ao prontuário.  
- **RF10**: O sistema deve permitir a criação de templates customizáveis para prontuários e sessões (ex.: anamnese, evolução).  
- **RF11**: O prontuário deve permitir o anexo de arquivos externos (PDF, imagens, etc.).  

### Controle Financeiro
- **RF12**: O sistema deve permitir o registro de pagamentos por sessão ou pacotes de sessões.  
- **RF13**: O sistema deve permitir a geração e envio de recibos de pagamento para os pacientes.  
- **RF14**: O sistema deve permitir a criação e venda de pacotes de sessões, com controle automático do uso.  
- **RF15**: O sistema deve permitir a emissão de recibos em lote para todos os atendimentos de um período.  
- **RF16**: O sistema deve prever integração futura com gateways de pagamento online.  

### Comunicação e Portal do Paciente
- **RF17**: O sistema deve enviar lembretes automáticos de consulta e solicitar confirmação (via e-mail ou WhatsApp).  
- **RF18**: O sistema deve permitir o envio de avisos para pacientes (ex.: pagamentos, férias).  
- **RF19**: O paciente deve poder solicitar novos agendamentos e cancelar consultas pelo portal.  

### Administração e Relatórios
- **RF20**: O sistema deve gerar relatórios financeiros (faturamento, pendências, fluxo de caixa).  
- **RF21**: O sistema deve gerar relatórios sobre a taxa de faltas por paciente ou por período.  

---

## Requisitos Não Funcionais (RNF)

### Usabilidade
- **RNF01**: A interface deve ser clara, intuitiva e de fácil utilização.  
- **RNF02**: O sistema deve otimizar tarefas administrativas, reduzindo retrabalho.  

### Portabilidade e Acessibilidade
- **RNF03**: O sistema deve ser acessível a partir dos principais navegadores web.  
- **RNF04**: A interface deve se adaptar a diferentes tamanhos de tela (desktop, tablet, celular).  

### Confiabilidade e Disponibilidade
- **RNF05**: O sistema deve ter alta disponibilidade, com mínimo tempo de inatividade.  
- **RNF06**: O sistema deve executar operações (consultas, registros, salvamentos) em tempo hábil.  
