# Levantamento de Requisitos - Clínica de Psicologia

Este documento contém os requisitos levantados a partir da entrevista realizada com a psicóloga Adrillenne Pinheiro Silva Rezende.

---

## Requisitos Funcionais (RF)

### Agendamento e Atendimento
- **RF01**: O sistema deve permitir o cadastro de pacientes.  
- **RF02**: O sistema deve permitir o agendamento de consultas pela clínica.  
- **RF03**: O sistema deve permitir que o próprio paciente agende e remarque consultas online.  
- **RF04**: O sistema deve permitir a integração da agenda pessoal com a agenda da clínica.  
- **RF05**: O sistema deve enviar lembretes automáticos de consultas para pacientes (WhatsApp, e-mail ou ligação).  
- **RF06**: O sistema deve permitir que o paciente receba confirmações de consulta.  

### Prontuários e Documentação Clínica
- **RF07**: O sistema deve permitir a criação e atualização de prontuários de pacientes.  
- **RF08**: O sistema deve gerar automaticamente um prontuário após a sessão, com resumo breve.  
- **RF09**: O sistema deve permitir registro documental da evolução do paciente.  
- **RF10**: O sistema deve permitir a utilização de documentos/anamneses padronizadas (primeira consulta, 6 meses, 12 meses e encerramento).  
- **RF11**: O sistema deve permitir o armazenamento de anotações, testes psicológicos e outros documentos do paciente.  

### Controle Financeiro
- **RF12**: O sistema deve permitir o registro de pagamentos recebidos.  
- **RF13**: O sistema deve permitir geração de relatórios financeiros (lucros, gastos, crescimento mensal).  
- **RF14**: O sistema deve permitir o envio de links de cobrança ou documentos de pagamento (recibos, notas fiscais) para pacientes.  

### Teleatendimento
- **RF15**: O sistema deve permitir o registro de atendimentos online (ex.: via Google Meet ou Zoom).  
- **RF16**: O sistema deve registrar o consentimento do paciente para atendimentos virtuais.  

### Privacidade e LGPD
- **RF17**: O sistema deve armazenar os dados de pacientes por pelo menos 5 anos.  
- **RF18**: O sistema deve permitir armazenamento permanente de alguns documentos específicos.  
- **RF19**: O sistema deve garantir mecanismos para exportar os dados dos pacientes quando houver desligamento da clínica.  

### Gestão Clínica
- **RF20**: O sistema deve emitir lembretes para os profissionais da clínica sobre documentos de regularidade junto ao conselho.  

---

## Requisitos Não Funcionais (RNF)

### Usabilidade
- **RNF01**: O sistema deve ter interface intuitiva, simples e limpa (clean).  
- **RNF02**: O sistema deve utilizar cores aconchegantes e não sobrecarregar o usuário com excesso de informações.  
- **RNF03**: O sistema deve destacar as funcionalidades principais (agenda, prontuários, financeiro).  
- **RNF04**: O sistema deve ser fácil de usar tanto para profissionais quanto para pacientes.  

### Segurança e Privacidade
- **RNF05**: O sistema deve estar em conformidade com a LGPD e resoluções do Conselho de Psicologia.  
- **RNF06**: O sistema deve possuir criptografia forte para proteção de dados sensíveis.  
- **RNF07**: O sistema deve exigir autenticação para acesso de profissionais.  

### Acessibilidade e Portabilidade
- **RNF08**: O sistema deve ser acessível via dispositivos móveis (celulares, tablets) e computadores.  
- **RNF09**: O sistema deve permitir integração futura com múltiplos dispositivos.  

### Desempenho
- **RNF10**: O sistema deve gerar prontuários automaticamente em tempo real após as consultas.  

---
