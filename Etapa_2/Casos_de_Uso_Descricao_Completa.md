# Casos de Uso – Descrição Completa

> Projeto: Sistema de Gestão para Clínica de Psicologia  
> Disciplina: Arquitetura e Desenho de Software (CIC1060) – PUC Goiás  

---
## Convenções
- **Atores primários**: iniciam o caso de uso e obtêm valor direto.  
- **Atores secundários**: sistemas/serviços externos ou papéis internos que dão suporte.  
- **Prioridade**: Alta (A), Média (M), Baixa (B).  
- **RF**: requisito funcional; **RNF**: requisito não-funcional.  
- **Pré-condições**: o que já deve ser verdade; **Pós-condições**: o que deve ser verdade ao concluir com êxito.

---
## UC-01 – Autenticar Usuário
**Atores**: Usuário Interno (Psicólogo, Auxiliar), Paciente.  
**Objetivo**: Permitir o acesso seguro às funcionalidades do sistema.  
**Prioridade**: A  
**RF**: RF-AUT-01, RF-SEG-01  
**RNF**: RNF-SEG-01, RNF-DISP-01

**Pré-condições**: Usuário cadastrado e ativo.  
**Pós-condições**: Sessão autenticada, permissões aplicadas e log registrado.

**Fluxo Principal**
1. Usuário informa credenciais.  
2. Sistema valida e verifica status.  
3. MFA é aplicado (opcional).  
4. Acesso liberado conforme perfil.

**Fluxos Alternativos**
- 1a. Esqueci minha senha → sistema envia link seguro.  
- 2a. Usuário bloqueado → exibe aviso e contato do suporte.

---
## UC-02 – Manter Cadastro de Paciente
**Atores**: Auxiliar Administrativo, Paciente.  
**Objetivo**: Cadastrar e manter informações do paciente.  
**Prioridade**: A  
**RF**: RF-CAD-01  
**RNF**: RNF-USAB-01, RNF-AUD-01

**Pré-condições**: Usuário autenticado com permissão.  
**Pós-condições**: Dados armazenados e auditáveis.

**Fluxo Principal**
1. Usuário inicia cadastro.  
2. Sistema solicita dados obrigatórios e consentimento.  
3. Verifica duplicidade (CPF/e-mail).  
4. Salva registro e confirma operação.

**Fluxos Alternativos**
- 2a. Consentimento pendente → status “restrito”.  
- 3a. Possível duplicidade → sistema alerta.

---
## UC-03 – Manter Cadastro de Profissional
**Atores**: Administrador, Auxiliar Administrativo.  
**Objetivo**: Cadastrar profissionais com CRP e horários.  
**Prioridade**: A  
**RF**: RF-CAD-02, RF-AGEN-01  
**RNF**: RNF-INT-01, RNF-AUD-01

**Pré-condições**: Permissão administrativa.  
**Pós-condições**: Profissional disponível para agendamento.

**Fluxo Principal**
1. Inserir dados do profissional.  
2. Validar CRP e especialidades.  
3. Configurar horários e valores.  
4. Salvar registro e publicar agenda.

**Fluxos Alternativos**
- 2a. CRP pendente → status “aguardando validação”.  
- 3a. Conflito de horários → sistema sugere correção.

---
## UC-04 – Configurar Agenda do Profissional
**Atores**: Psicólogo, Auxiliar Administrativo.  
**Objetivo**: Definir disponibilidade e bloqueios.  
**Prioridade**: A  
**RF**: RF-AGEN-02  
**RNF**: RNF-USAB-02, RNF-DESEMP-01

**Fluxo Principal**
1. Selecionar profissional e período.  
2. Definir horários, pausas e feriados.  
3. Sistema verifica conflitos e gera slots.  
4. Publica agenda.

**Fluxos Alternativos**
- 2a. Bloqueios pontuais → exceções adicionadas.  
- 3a. Capacidade excedida → sistema alerta.

---
## UC-05 – Agendar Consulta
**Atores**: Paciente, Auxiliar Administrativo.  
**Objetivo**: Permitir escolha de horário e confirmação.  
**Prioridade**: A  
**RF**: RF-AGEN-03, RF-COM-01  
**RNF**: RNF-INT-02, RNF-SEG-02

**Fluxo Principal**
1. Selecionar serviço e modalidade.  
2. Exibir horários disponíveis.  
3. Confirmar dados e registrar consulta.  
4. Enviar confirmação (e-mail/SMS/WhatsApp).

**Fluxos Alternativos**
- 2a. Sem disponibilidade → lista de espera.  
- 4a. Pagamento exigido → UC-09.

---
## UC-06 – Reagendar/Cancelar Consulta
**Atores**: Paciente, Psicólogo, Auxiliar Administrativo.  
**Objetivo**: Alterar ou cancelar consultas.  
**Prioridade**: A  
**RF**: RF-AGEN-04  
**RNF**: RNF-AUD-02

**Fluxo Principal**
1. Solicitar modificação.  
2. Sistema verifica políticas e janelas.  
3. Atualiza status e notifica partes.

**Fluxos Alternativos**
- 2a. Fora da janela → aplica penalidade.

---
## UC-07 – Enviar Lembretes e Confirmações
**Atores**: Sistema, Paciente.  
**Objetivo**: Enviar notificações automáticas.  
**Prioridade**: A  
**RF**: RF-COM-02  
**RNF**: RNF-INT-02, RNF-CONF-01

**Fluxo Principal**
1. Sistema agenda lembretes (D-1, H-3).  
2. Envia mensagem e coleta confirmação.  
3. Atualiza status da consulta.

**Fluxos Alternativos**
- 2a. Canal falhou → fallback alternativo.

---
## UC-08 – Registrar Atendimento e Prontuário
**Atores**: Psicólogo.  
**Objetivo**: Registrar evolução clínica e anexos.  
**Prioridade**: A  
**RF**: RF-PRON-01, RF-SEG-02  
**RNF**: RNF-SEG-03, RNF-AUD-03

**Fluxo Principal**
1. Abrir ficha e criar evolução.  
2. Preencher campos (anamnese, SOAP, etc.).  
3. Anexar arquivos e salvar.  
4. Sistema gera versão imutável e loga acesso.

**Fluxos Alternativos**
- 3a. Arquivo inválido → rejeitar.  
- 4a. Assinatura digital opcional.

---
## UC-09 – Processar Pagamento e Emitir Recibo
**Atores**: Paciente, Auxiliar Financeiro.  
**Objetivo**: Registrar pagamento e emitir comprovante.  
**Prioridade**: A  
**RF**: RF-FIN-01, RF-FIN-03  
**RNF**: RNF-INT-03, RNF-COMP-01

**Fluxo Principal**
1. Escolher forma de pagamento.  
2. Integrar com gateway (ou manual).  
3. Confirmar transação e emitir recibo.  
4. Registrar repasse ao profissional.

**Fluxos Alternativos**
- 2a. Falha no gateway → retry.  
- 1a. Política de reembolso → UC-06.

---
## UC-10 – Mensagens de Acompanhamento ao Paciente
**Atores**: Psicólogo, Sistema.  
**Objetivo**: Enviar orientações pós-sessão.  
**Prioridade**: M  
**RF**: RF-COM-03  
**RNF**: RNF-CONF-02

**Fluxo Principal**
1. Psicólogo escolhe paciente e template.  
2. Sistema personaliza mensagem e envia.  
3. Registro auditável criado.

**Fluxos Alternativos**
- 2a. Canal não consentido → sugerir alternativo.

---
## UC-11 – Gerir Consentimentos e Preferências
**Atores**: Paciente, Auxiliar Administrativo.  
**Objetivo**: Controlar consentimentos LGPD.  
**Prioridade**: A  
**RF**: RF-LGPD-02, RF-LGPD-03  
**RNF**: RNF-SEG-04, RNF-AUD-04

**Fluxo Principal**
1. Paciente acessa centro de privacidade.  
2. Visualiza finalidades e aceita/revoga.  
3. Sistema aplica restrições conforme status.

**Fluxos Alternativos**
- 2a. Consentimento essencial ausente → bloqueia recurso.

---
## UC-12 – Acessar Prontuário (Consulta Segura)
**Atores**: Psicólogo, Paciente (limitado).  
**Objetivo**: Visualizar prontuários com controle de acesso.  
**Prioridade**: A  
**RF**: RF-PRON-02, RF-SEG-03  
**RNF**: RNF-SEG-05, RNF-AUD-03

**Fluxo Principal**
1. Buscar paciente e abrir registros.  
2. Aplicar filtros por papel.  
3. Exibir com marca d’água e opções de exportação.

**Fluxos Alternativos**
- 3a. Acesso negado → tentativa logada.

---
## UC-13 – Gerar Relatórios Financeiros
**Atores**: Auxiliar Financeiro, Administrador.  
**Objetivo**: Consultar faturamento e indicadores.  
**Prioridade**: M  
**RF**: RF-FIN-04  
**RNF**: RNF-DESEMP-02, RNF-SEC-06

**Fluxo Principal**
1. Selecionar período e filtros.  
2. Sistema calcula e exibe métricas.  
3. Exportar ou agendar relatório.

**Fluxos Alternativos**
- 2a. Dados incompletos → sinaliza pendências.

---
## UC-14 – Portal do Paciente: Gerenciar Conta e Agendamentos
**Atores**: Paciente.  
**Objetivo**: Permitir autoatendimento completo.  
**Prioridade**: A  
**RF**: RF-PORT-01, RF-COM-04  
**RNF**: RNF-USAB-04, RNF-SEG-07

**Fluxo Principal**
1. Acessar portal e atualizar dados.  
2. Visualizar histórico e preferências.  
3. Agendar, reagendar e acompanhar pagamentos.

**Fluxos Alternativos**
- 2a. Solicitar portabilidade → gerar pacote seguro.

---
## UC-15 – Gerenciar Convênios/Planos (Opcional)
**Atores**: Auxiliar Administrativo, Financeiro.  
**Objetivo**: Cadastrar convênios e regras.  
**Prioridade**: B  
**RF**: RF-FAT-01  
**RNF**: RNF-INT-04

**Fluxo Principal**
1. Registrar convênio e tabela.  
2. Vínculo paciente-convênio.  
3. Geração de guias e faturamento.

**Fluxos Alternativos**
- 2a. Elegibilidade negada → ofertar pagamento particular.