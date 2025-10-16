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
- **include** = comportamento **obrigatório e reutilizável** (o caso base sempre executa o incluído).
- **extend** = comportamento **opcional/condicional** que adiciona passos ao caso base em um ponto de extensão.
- **Nota** = relacionamento de disparo/associação (quando não é propriamente include/extend).

---
## Sumário dos Casos de Uso

- **UC-01** Autenticar Usuário  
- **UC-02** Manter Cadastro de Paciente  
- **UC-03** Manter Cadastro de Profissional  
- **UC-04** Configurar Agenda do Profissional  
  - *extend* → **UC-16** Sincronizar Calendário Externo  
- **UC-05** Agendar Consulta  
  - *extend* → **UC-05a** Gerir Lista de Espera  
  - *extend* → **UC-09** Processar Pagamento e Emitir Recibo *(quando política exigir pré‑pagamento)*  
- **UC-05a** Gerir Lista de Espera *(novo)*  
- **UC-05b** Confirmar Presença *(novo)*  
- **UC-06** Reagendar/Cancelar Consulta  
  - *extend* → **UC-07** Enviar Comunicações Transacionais *(notificações de reagendamento/cancelamento)*  
  - **Nota:** Pode **disparar** regras para **UC-18** Processar Reembolso (quando aplicável)  
- **UC-07** Enviar Comunicações Transacionais (Lembretes, Confirmações, Mensagens) **[escopo ampliado]**  
  - **Nota:** Pode **iniciar** **UC-05b** Confirmar Presença via link/token seguro  
- **UC-08** Registrar Atendimento e Prontuário  
  - *extend* → **UC-17** Assinar Digitalmente Documento Clínico  
- **UC-09** Processar Pagamento e Emitir Recibo  
  - *extend* → **UC-18** Processar Reembolso *(quando aplicável por política)*  
- **UC-10** Mensagens de Acompanhamento ao Paciente (pós-consulta)  
  - *extend* → **UC-07** Enviar Comunicações Transacionais *(agendar/envio de acompanhamento)*  
- **UC-11** Gerir Consentimentos e Preferências (LGPD)  
  - **Nota:** Na ausência de consentimento essencial, casos que exigem o dado podem ser **bloqueados** (fluxo alternativo interno)  
- **UC-12** Acessar Prontuário (Consulta Segura)  
  - *extend* → **UC-13** Gerar Relatórios *(exportar/baixar)*  
- **UC-13** Gerar Relatórios (Operacionais/Financeiros/Clínicos)  
  - *extend* → **UC-07** Enviar Comunicações Transacionais *(agendar e enviar relatório)*  
- **UC-14** Portal do Paciente  
  - *extend* → **UC-11** Solicitar Portabilidade/Relatório de Dados Pessoais  
- **UC-15** Gerenciar Convênios/Planos  
  - *extend* → **UC-09** Processar Pagamento Particular *(quando elegibilidade for negada e paciente optar por particular)*  
- **UC-16** Sincronizar Calendário Externo *(novo)*  
- **UC-17** Assinar Digitalmente Documento Clínico *(novo)*  
- **UC-18** Processar Reembolso *(novo)*

---

## UC-01 – Autenticar Usuário
**Atores:** Usuário (Paciente/Profissional/Admin)  
**Objetivo:** Acessar o sistema com credenciais válidas / SSO.  
**Prioridade:** A  
**RF:** RF-AUT-01, RF-SEG-01  
**RNF:** RNF-SEG-02, RNF-INT-01

**Fluxo Principal**  
1. Informar credenciais ou usar SSO.  
2. Validar autenticidade e permissões.  
3. Conceder acesso.

**Alternativos**  
- 1a. **Esqueci minha senha** → *extend* (UC de Recuperar Senha — fora de escopo aqui ou a definir).  
- 2a. Falha de autenticação → mensagem e registro de tentativa.

---

## UC-02 – Manter Cadastro de Paciente
**Atores:** Auxiliar Administrativo, Paciente  
**Objetivo:** Criar/atualizar cadastro de paciente.  
**Prioridade:** A  
**RF:** RF-CAD-01, RF-CAD-02, RF-LGPD-01  
**RNF:** RNF-SEG-02, RNF-AUD-01

**Relações:**  
- *extend* → **UC-07** Enviar Comunicações Transacionais *(mensagem de boas‑vindas/ confirmação de cadastro, quando aplicável)*

**Fluxo Principal**  
1. Inserir/editar dados pessoais e de contato.  
2. Validar consentimentos (LGPD) e salvar.  
3. Disponibilizar confirmação do cadastro.

**Alternativos**  
- 2a. Consentimento essencial ausente → bloquear coleta do dado e orientar (ver UC-11).

---

## UC-03 – Manter Cadastro de Profissional
**Atores:** Administrador, Profissional  
**Objetivo:** Cadastrar/atualizar dados e status do psicólogo.  
**Prioridade:** A  
**RF:** RF-CAD-03, RF-CAD-04  
**Relações:**  
- *extend* → **UC-07** Enviar Comunicações Transacionais *(notificar ativação/alteração de perfil)*

**Fluxo Principal**  
1. Cadastrar dados profissionais, especialidades, CRP.  
2. Definir status (ativo/inativo) e disponibilidade geral.  
3. Salvar e disponibilizar no diretório.

---

## UC-04 – Configurar Agenda do Profissional
**Atores:** Profissional, Auxiliar Administrativo  
**Objetivo:** Configurar faixas de horário, intervalos, capacidade e políticas.  
**Prioridade:** A  
**RF:** RF-AGEN-01, RF-AGEN-02

**Relações:**  
- *extend* → **UC-16** Sincronizar Calendário Externo *(opcional; Google/Outlook, etc.)*

**Fluxo Principal**  
1. Definir disponibilidade por dia/semana, duração de sessões.  
2. Parametrizar políticas (pré‑pagamento, tolerância de atraso, janelas).  
3. Salvar e publicar slots disponíveis.

---

## UC-05 – Agendar Consulta
**Atores:** Paciente, Auxiliar Administrativo  
**Objetivo:** Selecionar serviço/profissional, escolher horário e confirmar.  
**Prioridade:** A  
**RF:** RF-AGEN-03, RF-COM-01  
**RNF:** RNF-INT-02, RNF-SEG-02

**Relações:**  
- *extend* → **UC-05a** Gerir Lista de Espera *(quando não houver disponibilidade)*  
- *extend* → **UC-09** Processar Pagamento e Emitir Recibo *(quando política de pré‑pagamento exigir)*

**Fluxo Principal**  
1. Selecionar serviço/modalidade e (opcional) profissional.  
2. Exibir horários disponíveis conforme regras.  
3. Capturar dados de confirmação.  
4. Registrar consulta e exibir confirmação.  
5. *extend point:* **Pré‑pagamento exigido** → acionar **UC-09**.

**Alternativos**  
- 2a. **Sem disponibilidade** → *extend* **UC-05a**.  
- 4a. Falha na reserva (condição corrida) → tentar outro slot.

---

## **UC-05a – Gerir Lista de Espera** *(novo)*
**Atores:** Paciente, Auxiliar Administrativo  
**Objetivo:** Cadastrar preferências e posição em fila; notificar e reservar janela quando surgir vaga.  
**Prioridade:** B  
**RF:** RF-AGEN-10 (fila), RF-COM-04 (notificação)

**Fluxo Principal**  
1. Oferecer entrada na fila com preferências (profissional/horário).  
2. Registrar posição e regras de prioridade.  
3. Detectar vaga compatível; reservar por janela limitada.  
4. Notificar paciente.  
5. Paciente confirma → criar consulta (retorna ao UC-05 passo de confirmação).

**Alternativos**  
- 3a. Janela expira → notificar próximo da fila.  
- 5a. Recusa → manter posição ou ajustar preferências.

---

## **UC-05b – Confirmar Presença** *(novo)*
**Atores:** Paciente  
**Objetivo:** Confirmar/declinar presença da consulta previamente agendada.  
**Prioridade:** B  
**RF:** RF-AGEN-11

**Relações:**  
- **Nota:** **UC-07** pode **iniciar** este UC via link/token seguro enviado ao paciente.

**Fluxo Principal**  
1. Acessar link autenticado/assinado.  
2. Visualizar detalhes da sessão e política de no‑show.  
3. Confirmar presença → status “confirmada”.

**Alternativos**  
- 3a. Declinar → aplicar política (ex.: liberar vaga/espera, eventual penalidade).

---

## UC-06 – Reagendar/Cancelar Consulta
**Atores:** Paciente, Auxiliar Administrativo  
**Objetivo:** Alterar ou cancelar sessão futura conforme regras.  
**Prioridade:** A  
**RF:** RF-AGEN-05, RF-AGEN-06

**Relações:**  
- *extend* → **UC-07** Enviar Comunicações Transacionais *(enviar confirmação de reagendamento/cancelamento)*  
- **Nota:** Política pode **disparar** **UC-18** Processar Reembolso (quando elegível).

**Fluxo Principal**  
1. Selecionar consulta e ação (reagendar/cancelar).  
2. Aplicar regras (janelas/limites).  
3. Concluir alteração/cancelamento.

---

## UC-07 – Enviar Comunicações Transacionais (**escopo ampliado**)
**Atores:** Sistema (job), Auxiliar Administrativo  
**Objetivo:** Enviar lembretes, confirmações, mensagens de boas‑vindas e comunicações operacionais (e‑mail/SMS/WhatsApp).  
**Prioridade:** A  
**RF:** RF-COM-01, RF-COM-02, RF-COM-03

**Relações:**  
- **Nota:** Pode **iniciar** **UC-05b** Confirmar Presença (link seguro).  
- *extend* por: **UC-02**, **UC-03**, **UC-06**, **UC-10**, **UC-13** (quando precisam enviar mensagens).

**Fluxo Principal**  
1. Agendar/gerar conteúdo transacional.  
2. Enfileirar e enviar por canal preferido.  
3. Registrar logs e status.

---

## UC-08 – Registrar Atendimento e Prontuário
**Atores:** Profissional  
**Objetivo:** Registrar evolução clínica, anexos e observações de sessão.  
**Prioridade:** A  
**RF:** RF-PRON-01, RF-PRON-02; RF-LGPD-02

**Relações:**  
- *extend* → **UC-17** Assinar Digitalmente Documento Clínico *(quando necessário)*

**Fluxo Principal**  
1. Selecionar paciente e sessão.  
2. Registrar anotações e anexos.  
3. Salvar versão auditável.  
4. *extend point:* **Assinatura exigida** → **UC-17**.

---

## UC-09 – Processar Pagamento e Emitir Recibo
**Atores:** Paciente, Auxiliar Administrativo, Gateway de Pagamento  
**Objetivo:** Cobrar e emitir recibo NF/recibo interno.  
**Prioridade:** A  
**RF:** RF-PAG-01, RF-PAG-02

**Relações:**  
- *extend* → **UC-18** Processar Reembolso *(política/solicitação)*

**Fluxo Principal**  
1. Selecionar modalidade (cartão, pix, convênio/complemento).  
2. Processar transação.  
3. Emitir recibo e registrar contábil.

**Alternativos**  
- 2a. Falha de pagamento → orientar novo meio.

---

## UC-10 – Mensagens de Acompanhamento ao Paciente (pós-consulta)
**Atores:** Profissional, Auxiliar Administrativo  
**Objetivo:** Enviar orientações e follow‑up após atendimento.  
**Prioridade:** B  
**RF:** RF-COM-03

**Relações:**  
- *extend* → **UC-07** *(agendar/envio do acompanhamento)*

**Fluxo Principal**  
1. Selecionar paciente(s) e conteúdo de acompanhamento.  
2. Definir agendamento.  
3. Disparar envio (via UC-07).

---

## UC-11 – Gerir Consentimentos e Preferências (LGPD)
**Atores:** Paciente, Auxiliar Administrativo  
**Objetivo:** Registrar, atualizar e auditar consentimentos/preferências.  
**Prioridade:** A  
**RF:** RF-LGPD-01, RF-LGPD-03

**Fluxo Principal**  
1. Exibir termos e finalidades.  
2. Capturar aceites/negações por finalidade.  
3. Persistir e versionar registros.

**Alternativos**  
- 2a. Consentimento essencial negado → bloquear a funcionalidade dependente (fluxo interno do caso que requer o dado).

---

## UC-12 – Acessar Prontuário (Consulta Segura)
**Atores:** Profissional (autorizado)  
**Objetivo:** Visualizar registros clínicos com controle de acesso.  
**Prioridade:** A  
**RF:** RF-PRON-03

**Relações:**  
- *extend* → **UC-13** Gerar Relatórios *(exportar/compartilhar versões permitidas)*

**Fluxo Principal**  
1. Selecionar paciente; validar permissão.  
2. Consultar evoluções, anexos, histórico.  
3. (Opcional) Exportar/gerar relatório → *extend* UC-13.

---

## UC-13 – Gerar Relatórios (Operacionais/Financeiros/Clínicos)
**Atores:** Admin, Gestor, Profissional  
**Objetivo:** Produzir relatórios e visões analíticas.  
**Prioridade:** B  
**RF:** RF-REL-01, RF-REL-02

**Relações:**  
- *extend* → **UC-07** *(agendar/envio automático)*

**Fluxo Principal**  
1. Selecionar fonte/período/filtros.  
2. Gerar relatório.  
3. (Opcional) Programar envio (via UC-07).

---

## UC-14 – Portal do Paciente
**Atores:** Paciente  
**Objetivo:** Autoatendimento (agendamentos, histórico, preferências, dados pessoais).  
**Prioridade:** A  
**RF:** RF-PORT-01, RF-PORT-02

**Relações:**  
- *extend* → **UC-11** Solicitar Portabilidade/Relatório de Dados Pessoais

---

## UC-15 – Gerenciar Convênios/Planos
**Atores:** Auxiliar Administrativo  
**Objetivo:** Manter convênios, tabelas e verificar elegibilidade.  
**Prioridade:** A  
**RF:** RF-CONV-01, RF-CONV-02

**Relações:**  
- *extend* → **UC-09** Processar Pagamento Particular *(quando elegibilidade negada e paciente optar por particular)*

**Fluxo Principal**  
1. Verificar elegibilidade/guia.  
2. Calcular coparticipação/diferença.  
3. Concluir autorização.

**Alternativos**  
- 1a. Elegibilidade negada → oferecer pagamento particular → *extend* UC-09.

---

## **UC-16 – Sincronizar Calendário Externo** *(novo)*
**Atores:** Profissional, Sistema  
**Objetivo:** Integrar agenda com Google/Outlook/CalDAV.  
**Prioridade:** B  
**RF:** RF-AGEN-07

**Fluxo Principal**  
1. Conectar conta externa e consentir escopos.  
2. Configurar mapeamentos (serviços/calendários).  
3. Sincronizar eventos (pull/push) e resolver conflitos.

---

## **UC-17 – Assinar Digitalmente Documento Clínico** *(novo)*
**Atores:** Profissional  
**Objetivo:** Assinar evoluções/relatórios conforme política e requisitos legais.  
**Prioridade:** B  
**RF:** RF-ASS-01

**Fluxo Principal**  
1. Selecionar documento elegível.  
2. Validar identidade (MFA/certificado).  
3. Aplicar assinatura e carimbo do tempo.  
4. Arquivar versão assinada.

---

## **UC-18 – Processar Reembolso** *(novo)*
**Atores:** Paciente, Financeiro, Gateway  
**Objetivo:** Reembolsar valores conforme política (cancelamento, no‑show, erro).  
**Prioridade:** B  
**RF:** RF-REB-01

**Fluxo Principal**  
1. Identificar elegibilidade e origem (UC-06 cancelamento, erro de cobrança, etc.).  
2. Selecionar meio de estorno (cartão/pix).  
3. Executar reembolso e emitir comprovante.

---

## Observações de Modelagem

- **UC-07** teve escopo ampliado para cobrir **boas‑vindas**, **lembretes**, **confirmações** e **envios programados** solicitados por outros casos.  
- Evitamos *include/extend* quando a relação é apenas **disparo/associação** (ex.: UC-07 → link que inicia UC-05b).  
- **Pagamento em Agendamento (UC-05)** foi modelado como **extend para UC-09** (pois é condicional por política). Caso sua política torne **sempre obrigatório** para certos serviços, crie uma **variante** do UC-05 que **include** o UC-09.

---