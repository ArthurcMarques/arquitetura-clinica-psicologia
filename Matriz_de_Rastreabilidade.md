# Matriz de Rastreabilidade de Requisitos

| ID      | Descrição resumida                                                     | Origem                  | Categoria |
|---------|------------------------------------------------------------------------|-------------------------|-----------|
| RF01    | Cadastro completo de pacientes                                         | Entrevista, Sistemas    | Evidente  |
| RF02    | Paciente atualiza dados via portal                                     | Sistemas, Normas        | Evidente  |
| RF03    | Registro de consentimento para tratamento de dados                     | Normas, Entrevista      | Evidente  |
| RF04    | Anexar documentos da clínica (CNPJ, alvarás, CRP)                      | Normas                  | Evidente  |
| RF05    | Cadastro de modalidade de atuação (PJ/Individual)                      | Normas                  | Evidente  |
| RF06    | Gestão da documentação do psicólogo (CRP, diplomas)                    | Normas                  | Evidente  |
| RF07    | Alertas de vencimento de documentos                                    | Normas, Entrevista      | Evidente  |
| RF08    | Agendar/reagendar/cancelar consultas                                   | Sistemas, Entrevista    | Evidente  |
| RF09    | Agendamento recorrente                                                 | Sistemas                | Evidente  |
| RF10    | Visualização da agenda (dia, semana, mês)                              | Sistemas                | Evidente  |
| RF11    | Integração agenda pessoal do psicólogo                                 | Entrevista              | Oculta    |
| RF12    | Lista de espera / notificação de horários vagos                        | Sistemas                | Evidente  |
| RF13    | Bloqueio de horários pelo profissional                                 | Sistemas                | Evidente  |
| RF14    | Lembretes automáticos e confirmações (WhatsApp, e-mail, ligação)       | Sistemas, Entrevista    | Evidente  |
| RF15    | Criação/atualização de prontuários                                     | Entrevista, Normas      | Evidente  |
| RF16    | Registro de evolução das sessões                                       | Normas, Entrevista      | Evidente  |
| RF17    | Anexar arquivos externos ao prontuário                                 | Sistemas, Entrevista    | Evidente  |
| RF18    | Uso de templates padronizados (anamnese etc.)                          | Sistemas, Entrevista    | Evidente  |
| RF19    | Geração de prontuário com dados do Psicólogo e geração automática      | Entrevista              | Evidente  |
| RF20    | Análise automática de termos mais citados                              | Entrevista              | Evidente  |
| RF21    | Diferenciar atendimento presencial e online                            | Normas, Entrevista      | Evidente  |
| RF22    | Registro de atendimentos online (Meet, Zoom)                           | Entrevista              | Evidente  |
| RF23    | Consentimento para atendimentos virtuais                               | Entrevista, Normas      | Evidente  |
| RF24    | Registro de pagamentos                                                 | Sistemas, Entrevista    | Evidente  |
| RF25    | Emissão e envio de recibos/notas fiscais                               | Sistemas, Entrevista    | Evidente  |
| RF26    | Relatórios financeiros (faturamento, gastos, pendências)               | Sistemas, Entrevista    | Evidente  |
| RF27    | Envio de links de cobrança                                             | Entrevista              | Evidente  |
| RF28    | Emissão de recibos em lote                                             | Sistemas                | Evidente  |
| RF29    | Integração futura com gateways de pagamento                            | Sistemas                | Oculta    |
| RF30    | Paciente solicita agendamento/cancelamento online                      | Sistemas, Entrevista    | Evidente  |
| RF31    | Paciente visualiza próximos agendamentos e histórico                   | Normas, Entrevista      | Evidente  |
| RF32    | Paciente visualiza histórico financeiro e baixa recibos                | Normas, Entrevista      | Evidente  |
| RF33    | Envio de avisos gerais para pacientes                                  | Sistemas                | Evidente  |
| RF34    | Perfis de usuário distintos (Adm, Psicólogo, Secretário)               | Normas                  | Evidente  |
| RF35    | Relatórios de atendimento (faturamento, faltas, taxa de adesão)        | Sistemas, Entrevista    | Evidente  |
| RF36    | Relatórios estatísticos anonimizados                                   | Normas                  | Oculta    |
| RNF01   | Criptografia de dados sensíveis                                        | Normas, Entrevista      |           |
| RNF02   | Controle de acesso por perfil                                          | Normas                  |           |
| RNF03   | Logs de auditoria                                                      | Normas                  |           |
| RNF04   | Autenticação de dois fatores (2FA)                                     | Normas                  |           |
| RNF05   | Exportação segura de dados                                             | Normas, Entrevista      |           |
| RNF06   | Políticas de arquivamento/exclusão LGPD                                | Normas, Entrevista      |           |
| RNF07   | Guarda mínima de prontuários por 5 anos                                | Normas, Entrevista      |           |
| RNF08   | Confidencialidade de documentos profissionais                          | Normas                  |           |
| RNF09   | Interface clara e intuitiva                                            | Normas, Entrevista      |           |
| RNF10   | Design clean, cores aconchegantes                                      | Entrevista              |           |
| RNF11   | Redução de retrabalho administrativo                                   | Sistemas                |           |
| RNF12   | Acessível em navegadores                                               | Normas, Sistemas        |           |
| RNF13   | Responsivo (desktop, tablet, celular)                                  | Normas, Sistemas        |           |
| RNF14   | Integração futura com múltiplos dispositivos                           | Entrevista              |           |
| RNF15   | Alta disponibilidade (mínimo downtime)                                 | Normas, Sistemas        |           |
| RNF16   | Operações em tempo hábil                                               | Normas, Sistemas        |           |
| RNF17   | Análises automáticas em tempo real                                     | Entrevista              |           |

---

### Legenda das Origens
- **Sistemas** → Requisitos derivados da análise de sistemas análogos (PsicoManager, Sintropia).  
- **Normas** → Requisitos derivados de LGPD, CFP e ISO 25010.  
- **Entrevista** → Requisitos levantados em entrevistas com profissionais da área.  
