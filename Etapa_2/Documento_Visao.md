# 🧩 Documento de Visão  
## Sistema de Gestão para Clínica de Psicologia (PsicoManager)

---

## **1. Introdução**

### **1.1 Propósito**
Este documento tem como objetivo apresentar a visão geral do sistema *PsicoManager*, um sistema de gestão desenvolvido para clínicas de psicologia. Ele descreve os objetivos, escopo, público-alvo, principais funcionalidades, restrições e atributos de qualidade do produto.  
Serve como base de alinhamento entre a equipe de desenvolvimento, professores e demais stakeholders, sendo sustentado pelos artefatos da Etapa 1 (levantamento de requisitos) e Etapa 2 (modelagem de casos de uso).

---

### **1.2 Escopo do Produto**
O *PsicoManager* é um sistema web de gestão voltado a otimizar as rotinas de **atendimento, agendamento, controle financeiro, armazenamento de prontuários e comunicação** em clínicas de psicologia.  
O sistema busca garantir **segurança, confidencialidade e conformidade** com a **Lei Geral de Proteção de Dados (LGPD)** e as **Resoluções do Conselho Federal de Psicologia (CFP)**.

Principais funcionalidades previstas:
- Cadastro e gerenciamento de pacientes e profissionais;  
- Agendamento de consultas e notificações automáticas;  
- Registro e consulta de prontuários psicológicos;  
- Controle financeiro e geração de relatórios;  
- Controle de permissões e perfis de usuário;  
- Mecanismos de segurança e privacidade de dados.  

---

### **1.3 Definições, Acrônimos e Abreviações**

| Termo | Definição |
|-------|------------|
| **LGPD** | Lei Geral de Proteção de Dados Pessoais (Lei nº 13.709/2018) |
| **CFP** | Conselho Federal de Psicologia |
| **CRUD** | Create, Read, Update, Delete |
| **RF** | Requisito Funcional |
| **RNF** | Requisito Não Funcional |
| **MVP** | Produto Mínimo Viável |
| **PsicoManager** | Sistema de Gestão para Clínica de Psicologia |

---

### **1.4 Referências**
- Lei nº 13.709/2018 – LGPD  
- Resolução CFP nº 11/2018 – uso de sistemas informatizados para registro profissional  
- Resolução CFP nº 01/2009 – guarda e sigilo de documentos psicológicos  
- ISO/IEC 25010 – modelo de qualidade de software  
- IEEE 830 / IEEE 12207 – padrões de documentação e processo de software  
- Documentos da Etapa 1 e 2 do projeto *PsicoManager*

---

## **2. Posicionamento**

### **2.1 Oportunidade de Negócio**
A gestão manual de clínicas de psicologia gera ineficiência e risco de não conformidade.  
O *PsicoManager* visa centralizar e automatizar os processos administrativos e clínicos, reduzindo falhas, retrabalho e exposição indevida de informações sensíveis.

---

### **2.2 Declaração do Problema**
| Elemento | Descrição |
|-----------|------------|
| **O problema é** | A ausência de um sistema integrado que una agendamento, prontuário e controle financeiro. |
| **Que afeta** | Clínicas de psicologia, profissionais e pacientes. |
| **O impacto é** | Perda de produtividade, erros e risco jurídico. |
| **Uma solução de sucesso seria** | Um sistema web seguro e integrado que otimize processos e preserve a privacidade. |

---

### **2.3 Declaração da Solução**
O *PsicoManager* fornecerá:
- Uma interface web centralizada e intuitiva;  
- Controle de acessos e níveis de permissão;  
- Prontuário eletrônico conforme normas do CFP;  
- Lembretes automáticos de consultas e pagamentos;  
- Ferramentas administrativas e relatórios gerenciais.  

---

### **2.4 Público-Alvo e Usuários-Chave**
- **Psicólogos:** gestão de pacientes e prontuários;  
- **Pacientes:** agendamento e acompanhamento de consultas;  
- **Administradores:** controle financeiro, permissões e relatórios;  
- **Auxiliares administrativos:** suporte ao agendamento e comunicação.  

---

### **2.5 Posicionamento do Produto**
O *PsicoManager* diferencia-se por ser voltado exclusivamente à **realidade das clínicas psicológicas**, garantindo **aderência às normas do CFP** e **tratamento ético e seguro dos dados clínicos**.

---

## **3. Descrição do Produto**

### **3.1 Perspectiva do Produto**
O *PsicoManager* será uma **plataforma web modular e escalável**, composta por módulos independentes para gestão clínica, financeira e administrativa.  
A **arquitetura do sistema ainda está em fase de definição**, devendo ser detalhada na próxima entrega (Documento de Arquitetura de Software).

---

### **3.2 Funções Principais do Sistema**
- Gerenciar cadastro de pacientes e profissionais (RF-CAD-01);  
- Registrar e consultar prontuários (RF-PRO-02);  
- Agendar, reagendar e cancelar consultas (RF-AGEN-03);  
- Emitir lembretes automáticos (RF-COM-01);  
- Controlar pagamentos e registros financeiros (RF-FIN-01);  
- Gerar relatórios administrativos (RF-ADM-02);  
- Garantir controle de acesso seguro (RF-SEG-01).  

---

### **3.3 Características dos Usuários**
Com base nas entrevistas e questionários:
- Usuários possuem **nível técnico intermediário**;  
- Exigem **interface simples e responsiva**;  
- Necessitam **acesso remoto e multiplataforma**;  
- Psicólogos demandam **máximo sigilo e confiabilidade**.  

---

### **3.4 Restrições Gerais**
- Cumprimento obrigatório da LGPD e resoluções do CFP;  
- Sistema deve ser acessível via navegador moderno;  
- Armazenamento seguro de dados sensíveis;  
- Cronograma e escopo definidos pelas etapas da disciplina;  
- Arquitetura técnica **ainda em definição**.  

---

## **4. Requisitos e Atributos de Qualidade**

### **4.1 Requisitos Funcionais (Resumo)**
| Código | Descrição |
|--------|------------|
| RF-CAD-01 | Cadastro e manutenção de pacientes e profissionais |
| RF-AGEN-03 | Agendamento e cancelamento de consultas |
| RF-COM-01 | Envio de notificações automáticas |
| RF-FIN-01 | Controle financeiro e emissão de recibos |
| RF-PRO-02 | Registro e consulta de prontuários |
| RF-ADM-02 | Geração de relatórios administrativos |
| RF-SEG-01 | Autenticação e controle de acesso |

---

### **4.2 Requisitos Não Funcionais (Resumo)**
| Categoria | Descrição |
|------------|------------|
| **Segurança** | Proteção de dados, controle de acessos e auditoria. |
| **Usabilidade** | Interface intuitiva e adaptável. |
| **Desempenho** | Respostas rápidas em operações rotineiras. |
| **Disponibilidade** | Acesso contínuo ao sistema. |
| **Conformidade** | Aderência às normas LGPD e CFP. |
| **Manutenibilidade** | Estrutura modular e documentação versionada. |

---

## **5. Ambiente do Produto**

### **5.1 Interfaces Externas**
- Interface de uso via navegador web;  
- Possível integração futura com APIs de notificação e pagamento.  

### **5.2 Plataformas e Tecnologias**
A definição de tecnologias, frameworks e padrões arquiteturais **será realizada em fase posterior** (Documento de Arquitetura de Software).  
O sistema deverá ser compatível com navegadores modernos e dispositivos móveis.

---

## **6. Critérios de Sucesso**

### **6.1 Indicadores**
- Adoção integral pela clínica piloto;  
- Redução do tempo de agendamento e registro de consultas;  
- Eliminação de registros manuais;  
- Nenhum incidente de vazamento de dados.  

### **6.2 Critérios de Aceitação**
- Implementação completa dos requisitos de prioridade alta;  
- Satisfação dos usuários em testes de usabilidade;  
- Conformidade com a LGPD e resoluções do CFP;  
- Disponibilização do sistema funcional e documentado.  

---

## **7. Riscos e Dependências**
| Tipo | Descrição |
|------|------------|
| **Legal** | Falha em atender exigências da LGPD ou CFP. |
| **Técnico** | Dependência de definições arquiteturais futuras. |
| **Operacional** | Dificuldade de adaptação por parte dos usuários. |
| **Cronograma** | Atrasos nas etapas subsequentes do projeto. |
| **Segurança** | Exposição indevida de dados confidenciais. |

---

📎 **Anexos**  
- Etapa 1 – Levantamento de Requisitos  
- Etapa 2 – Descrição de Casos de Uso  
- Matriz de Rastreabilidade  

---
