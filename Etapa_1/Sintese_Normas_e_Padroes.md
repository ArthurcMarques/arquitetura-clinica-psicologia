# Síntese da Análise de Leis, Legislações, Regulamentações e Padrões

Esta síntese aborda os principais pontos levantados a partir da análise de documentos legais e normativos que impactam diretamente o desenvolvimento de um software para a área da psicologia no Brasil.

---

## 1. Lei Geral de Proteção de Dados (LGPD) - Lei nº 13.709/2018

A **LGPD** é o pilar central para o tratamento de dados pessoais no Brasil. Para um sistema de clínica psicológica, os prontuários e dados de pacientes são classificados como **dados pessoais sensíveis**, exigindo um nível de proteção ainda mais rigoroso.

### Princípios Fundamentais
O sistema deve ser projetado para garantir a aplicação dos princípios da LGPD, como:

- **Finalidade:** Os dados só podem ser coletados para propósitos legítimos, específicos, explícitos e informados ao titular (paciente).
- **Necessidade:** O sistema deve coletar o mínimo de dados necessários para a prestação do serviço.
- **Livre Acesso e Transparência:** O paciente deve ter um canal de fácil acesso para consultar, corrigir e solicitar a exclusão de seus dados.
- **Segurança e Prevenção:** O sistema deve empregar medidas técnicas e administrativas para proteger os dados contra acessos não autorizados, perda, alteração ou destruição.
- **Não Discriminação:** Os dados não podem ser utilizados para fins discriminatórios, ilícitos ou abusivos.

### Requisitos Derivados
- **Consentimento:** Mecanismo para registrar o consentimento explícito e inequívoco do paciente (ou responsável legal).
- **Controle de Acesso:** Perfis de acesso distintos (psicólogo, secretário(a), administrador). Apenas o psicólogo responsável deve ter acesso integral ao prontuário.
- **Criptografia:** Dados em repouso e em trânsito devem ser criptografados.
- **Logs de Acesso:** Registro de quem acessou, quando e o que fez nos dados (auditoria).
- **Portabilidade e Exclusão:** Funcionalidades para o paciente solicitar portabilidade ou exclusão de seus dados, respeitando as obrigações legais de guarda.

---

## 2. Resoluções do Conselho Federal de Psicologia (CFP)

O **CFP** estabelece normas para a prática profissional do psicólogo, incluindo elaboração e guarda de documentos.

### Resolução CFP nº 001/2009
Dispõe sobre a obrigatoriedade do registro documental decorrente da prestação de serviços psicológicos.

#### Requisitos Derivados
- **Prontuário Eletrônico:** Deve conter identificação do paciente, avaliação da demanda, definição dos objetivos, evolução do trabalho e procedimentos técnico-científicos adotados.
- **Guarda e Sigilo:** Acesso restrito ao psicólogo. Sigilo deve ser garantido contra acesso administrativo ou de terceiros sem consentimento.
- **Temporalidade:** Prontuários devem ser armazenados por, no mínimo, **5 anos** após o último atendimento.

### Resolução CFP nº 011/2018
Regulamenta a prestação de serviços psicológicos por meio de Tecnologias da Informação e Comunicação (TICs).

#### Requisitos Derivados
- **Segurança na Comunicação:** Qualquer funcionalidade de telepsicologia (avisos, lembretes) deve utilizar canais seguros.
- **Cadastro e-Psi:** Psicólogo deve ter cadastro ativo no **e-Psi** para atendimentos online. O sistema pode incluir campo para registrar este dado.

---

## 3. Norma ISO/IEC 25010 - Qualidade de Produto de Software

Define um modelo de qualidade de software dividido em **oito características principais**, que servem como guia para requisitos não-funcionais.

### Requisitos Não-Funcionais Derivados
- **Adequação Funcional:** O sistema deve prover todas as funcionalidades descritas no escopo.
- **Confiabilidade:** Alta disponibilidade, estabilidade e tolerância a falhas.
- **Usabilidade:** Interface intuitiva, acessível e de fácil aprendizado.
- **Eficiência de Desempenho:** Respostas rápidas em consultas, agendamentos e relatórios, mesmo com grande volume de dados.
- **Manutenibilidade:** Arquitetura modular, bem documentada, permitindo futuras atualizações e expansão (ex.: versão mobile).
- **Portabilidade:** Uso de tecnologias web padrão (HTML5, CSS3, JavaScript), garantindo compatibilidade entre navegadores e adaptação mobile (design responsivo).
- **Segurança:** Confidencialidade, integridade, autenticação forte e não-repúdio.
- **Compatibilidade:** Operação correta nos principais navegadores (Chrome, Firefox, Safari, Edge).

---
