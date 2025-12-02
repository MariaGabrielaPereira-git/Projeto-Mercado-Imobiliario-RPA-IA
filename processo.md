#  Processo: Comparacao_Minuta_vs_Dados

## Visão Geral do Processo
Este processo tem como objetivo realizar a comparação entre dados capturados em fontes oficiais internas e informações disponíveis em documentos auxiliares e minutas de contrato.  
O fluxo automatizado identifica itens aptos para processamento, extrai informações de múltiplas origens, preenche documentos, gera arquivos complementares e consolida tudo para posterior aprovação e assinatura.

---

##  Objetivo da Automação
- Garantir consistência entre minuta e dados cadastrais.
- Preencher automaticamente documentos complementares (ex.: declarações e guias).
- Consolidar arquivos finais em um único documento para assinatura digital.
- Reduzir o tempo de preparação da documentação.
- Diminuir erros operacionais e divergências em campos sensíveis.

---

##  Escopo da Automação
### **Dentro do Escopo**
- Identificação dos itens a processar.
- Captura de dados cadastrais e financeiros.
- Preenchimento de planilhas auxiliares.
- Abertura e edição de documentos base.
- Geração de arquivos complementares.
- Consolidação final do pacote documental.
- Preparação do fluxo de assinatura.
- Emissão de relatório analítico e sintético.

###  Fora do Escopo
- Alteração de layout de documentos base.
- Alteração manual de dados fornecidos por áreas externas.
- Edição avançada não prevista para modelos auxiliares.
- Validação jurídica ou revisão de conteúdo textual.
- Tratativa de documentos fora do padrão definido.

---

#  Fluxo TO BE (Detalhado)

### **1. Identificação dos Itens**
- Ler os itens marcados como aptos.
- Construir fila de execução.
- Registrar início do processamento.

### **2. Captura de Dados**
- Extrair dados cadastrais do comprador.
- Capturar informações do empreendimento.
- Obter valores financeiros e condições do repasse.
- Registrar múltiplos compradores, quando houver.

### **3. Preenchimento da Planilha Auxiliar**
- Preencher campos da planilha "Contrato".
- Registrar datas, empreendimento, torre, unidade, valores financeiros e status.

### **4. Identificação da Minuta**
- Localizar documentos do comprador.
- Abrir arquivos auxiliares do empreendimento.
- Capturar fração, matrícula individualizada e demais textos necessários.

### **5. Extração de Campos para Montagem da Minuta**
- Capturar parágrafos e blocos textuais para substituição:
- Qualificação das partes
- Informações de unidade
- Construção
- Cláusulas adicionais
- Textos específicos (Hipoteca, Em Tempo, Futura Unidade etc.)

### **6. Edição da Minuta**
- Substituir trechos conforme regras predefinidas.
- Ajustar campos de acordo com modalidade (planta ou construído).
- Inserir ou remover parágrafos conforme disponibilidade.
- Ajustar campos de assinatura.
- Preencher informações adicionais/ressalvas.

### **7. Geração de Documentos Complementares**
- Avaliar necessidade de gerar o documento ITBI.
- Gerar:
- Ficha complementar
- Guia de pagamento
- Declaração de Isenção (quando aplicável)
- Documento de 1ª Aquisição (quando aplicável)

### **8. Consolidação Final**
- Juntar minuta + declarações + documentos emitidos em um único arquivo PDF.
- Nomear estruturadamente conforme padrão:
- **DDMMYY_Comprador_CPF_Bloco_Unidade**

### **9. Preparação para Assinatura**
- Ler fila de aprovadores na planilha de apoio.
- Preencher ordem de ações, nomes, CPFs e e-mails.
- Inserir “Procurador” como última assinatura.

### **10. Relatórios**
- Preencher relatório analítico:
- Resultados por etapa
- Divergências
- Documentos preenchidos
- Preencher relatório sintético:
- Tempo total
- Quantidade processada
- Itens com sucesso ou exceção

---

# 🚀 Melhorias Implementadas no Processo
- Redução de retrabalho com preenchimento 100% automático.
- Padronização da minuta via substituição controlada por regras.
- Eliminação de divergências entre documentos auxiliares.
- Criação de fluxo único consolidado para assinatura digital.
- Geração automática de declarações e guias.
- Centralização da lógica de validação em um único fluxo.
- Monitoramento padronizado por relatório analítico e sintético.

---

# ⚠️ Pontos de Atenção / Exceções
- Documentos fora do padrão devem ser interrompidos e registrados.
- Ausência de parágrafos esperados gera log de exceção.
- Campos com divergências financeiras invalidam o fluxo da minuta.
- Falta de arquivos auxiliares impede continuidade.
- Dados incompletos em planilhas bloqueiam a geração dos documentos.
- Falta de dados estruturais (cartório, matrícula, fração) impede emissão do ITBI.

---

# 📊 KPI – Indicadores Sugeridos
| Indicador | Descrição | Fórmula | Meta |
|----------|-----------|---------|-------|
| **Taxa de Sucesso** | Execuções concluídas sem erro | Sucesso / Total | ≥ 95% |
| **Tempo Médio de Execução** | Duração média por item processado | Soma tempos / Qtde itens | ≤ 8 min por item |
| **Taxa de Divergência** | Itens com inconsistências | Divergências / Total | ≤ 5% |
| **Documentos Gerados** | Quantidade de documentos criados por ciclo | Contagem por execução | N/A |
| **Tempo de Preparação para Assinatura** | Tempo até finalização do pacote | Tempo total assinatura | ≤ 2 min |

---

# 📝 Observações
- Todo conteúdo textual substituível deve estar padronizado nos documentos auxiliares.
- Erros de captura devem ser registrados com print e mensagem amigável.
- O fluxo aceita múltiplos compradores.
- Qualquer alteração de layout deve ser previamente comunicada.


---

  🚨 Aviso Importante: Todas as informações contidas nos projetos deste repositório são fictícias e foram criadas exclusivamente para fins de demonstração ou simulação. Nenhuma das empresas, organizações, pessoas ou eventos mencionados nos arquivos deste projeto são reais ou exigem dados autênticos. Quaisquer semelhanças com nomes, lugares ou entidades existentes são puramente coincidentes.

Este repositório foi desenvolvido com o objetivo de demonstrar habilidades técnicas, práticas de projetos e experiência em desenvolvimento e mapeamento de sistemas. Todas as referências a empresas, produtos, serviços ou indivíduos são meramente fictícias e não devem ser interpretadas como representações precisas da realidade.

Fique à vontade para explorar os projetos disponíveis aqui, mas lembre-se sempre de que todas as informações são fictícias e não devem ser utilizadas para qualquer fim além de fins educacionais, de demonstração ou simulação.

