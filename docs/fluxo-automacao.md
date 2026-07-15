# Desenho da Solução: Processo AS-IS vs TO-BE
## 1. Fluxo Atual (AS-IS)
1. Gestor envia requisição (E-mail).
2. RH solicita documentos ao candidato (WhatsApp/E-mail).
3. Candidato envia docs (Vários formatos).
4. RH valida e cadastra no ERP (Manual).
5. RH solicita acessos ao TI (Ticker/E-mail).
6. TI libera acessos e avisa o RH.
   
## 2. Fluxo Automatizado Proposto (TO-BE)
A solução utiliza **Microsoft Forms, SharePoint e Power Automate** para orquestrar o processo.
1. **Entrada Estruturada:** Candidato preenche MS Forms com validações de campo obrigatório.
2. **Processamento Cloud:** Power Automate captura a resposta, cria pasta no SharePoint e movime
3. **Triagem RH:** RH valida a documentação via Checklist no SharePoint.
4. **Trigger de Provisionamento:** Ao alterar o status para "Aprovado", o fluxo aciona o TI via
5. **Encerramento Automático:** A confirmação do TI dispara e-mails de boas-vindas e credenciais

## 3. Etapas da Automação
- **Gatilho:** Recebimento de resposta no Microsoft Forms.
- **Orquestração:** Power Automate (Workflows condicionais).
- **Repositório:** SharePoint Lists e OneDrive for Business.
- **Interface:** Cartões Adaptativos no Microsoft Teams.
