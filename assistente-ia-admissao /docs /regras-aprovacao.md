# Business Rules & Workflow Configuration
## 1. Campos Mandatórios (SharePoint List)
Para garantir a integridade do processo, a lista central deve conter:
- `Nome Completo` (Texto Único)
- `Status da Admissão` (Escolha: Pendente, Incompleto, Aprovado TI, Concluído)
- `Data de Início` (Data - Obrigatório)
- - `ID do Candidato/CPF` (Validação de 11 dígitos)
- `Link_Pasta_OneDrive` (Hyperlink gerado automaticamente)
  
## 2. Regras de Aprovação
O workflow de TI só será iniciado se, e somente se:
- O campo `Status da Admissão` for igual a **"Aprovado para Criação de Acessos"**.
- O anexo `RG/CPF` estiver presente na pasta vinculada.

## 3. Lógica do Workflow (Power Automate)
- **Verificação de Duplicidade:** O fluxo checa se o CPF já existe na base para evitar cadastros
- **Escalonamento:** Caso o status não seja alterado em 48h úteis após o envio dos documentos, o
- **Bloqueio de Registro:** Após o envio para o TI, a edição de campos sensíveis (Nome, CPF) é b
