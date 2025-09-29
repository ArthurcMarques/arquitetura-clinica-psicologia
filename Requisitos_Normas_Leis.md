# Levantamento de Requisitos - Normas e Leis

Este documento contém os requisitos levantados a partir da **LGPD**, **Resoluções do Conselho Federal de Psicologia (CFP)**, **ISO 25010** e **boas práticas de segurança** aplicáveis ao sistema de gestão para clínica de psicologia.

---

## Requisitos Funcionais (RF)

### Gestão de Pacientes e Cadastros
- **RF01**: O sistema deve registrar o consentimento explícito do paciente para o tratamento de seus dados, com data e versão dos termos.  
- **RF02**: O paciente deve poder visualizar e solicitar a atualização de seus dados cadastrais (telefone, endereço) através de um portal.  

### Prontuários e Documentação Clínica
- **RF03**: O sistema deve prover um módulo de prontuário eletrônico por paciente para registrar a evolução das sessões.  
- **RF04**: O prontuário deve conter identificação, demanda, objetivos e registros da evolução do atendimento.  
- **RF05**: O sistema deve permitir registrar se a sessão foi realizada presencialmente ou online.  

### Comunicação e Portal do Paciente
- **RF06**: O paciente deve poder visualizar seus próximos agendamentos e histórico de sessões.  
- **RF07**: O paciente deve poder visualizar seu histórico financeiro e baixar recibos de pagamento.  

### Administração e Relatórios
- **RF08**: O sistema deve permitir o cadastro de usuários com diferentes perfis (Administrador, Psicólogo, Secretário(a)).  
- **RF09**: O sistema deve gerar relatórios estatísticos e anonimizados sobre os pacientes (ex.: faixa etária).

### Conformidade com exigencias legais
- **RF10**: O sistema deve permitir anexar e armazenar documentos de registro da clínica/consultório, como CNPJ, alvarás, termo de responsabilidade técnica e certidões do CRP.
- **RF11**: O sistema deve permitir cadastrar a modalidade de atuação (Pessoa Jurídica ou Consultório Individual), vinculando a documentação obrigatória de cada caso.
- **RF12**: O sistema deve permitir o cadastro e a gestão da documentação do psicólogo atuante (registro no CRP, certidões de regularidade, termo de responsabilidade técnica, diploma).
- **RF13**: O sistema deve emitir alertas sobre vencimento ou renovação de documentos obrigatórios do profissional (ex.: anuidade do CRP, validade de alvará).
---

## Requisitos Não Funcionais (RNF)

### Segurança e Privacidade
- **RNF01**: Todos os dados sensíveis dos pacientes devem ser criptografados no banco de dados e durante a transmissão.  
- **RNF02**: O acesso às informações deve ser restrito por perfil; o prontuário só pode ser acessado pelo psicólogo responsável.  
- **RNF03**: O sistema deve registrar todas as ações de acesso e modificação em dados de pacientes (logs de auditoria).  
- **RNF04**: O sistema deve oferecer autenticação de dois fatores (2FA) para usuários.  
- **RNF05**: O sistema deve prover exportação segura de todos os dados de um paciente em formato legível.  
- **RNF06**: O sistema deve permitir configuração de políticas de arquivamento e exclusão de dados de pacientes inativos, conforme a LGPD.  

### Usabilidade
- **RNF07**: A interface deve ser clara, intuitiva e de fácil uso para todos os perfis de usuário.  

### Portabilidade e Acessibilidade
- **RNF08**: O sistema deve ser acessível via principais navegadores web.  
- **RNF09**: A interface deve se adaptar a diferentes dispositivos (desktop, tablet e celular).  

### Confiabilidade e Disponibilidade
- **RNF10**: O sistema deve possuir alta disponibilidade, com mínimo tempo de inatividade.  
- **RNF11**: O sistema deve executar consultas, registros e salvamentos em tempo hábil.  

### Conformidade Legal
- **RNF12**: O sistema deve garantir a guarda dos prontuários por um período mínimo de 5 anos.
- **RNF13**: O sistema deve contemplar a documentação exigida pelo CRP e órgãos municipais/estaduais para clínicas e consultórios de Psicologia.
- **RNF14**: O sistema deve garantir a confidencialidade e integridade da documentação profissional anexada, aplicando as mesmas normas de segurança dos dados clínicos. 
