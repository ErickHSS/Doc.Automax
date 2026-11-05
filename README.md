# Doc.Automax

Aplicação web estática para preencher formulários internos do Grupo Automax e gerar documentos em PDF diretamente no navegador.

## Formulários disponíveis

- Memorando financeiro para programação de pagamentos
- Autorização para entrega de veículo 0 km a terceiro
- Autorização de pagamento parcial a terceiro
- Checklist de autuações e pendências do veículo
- Contrato de varejo para veículos novos
- Contrato de vendas diretas
- Contrato de vendas e-commerce PSA
- Link externo para o portal de vendas corporativas

## Como executar

Não há etapa de compilação ou instalação de dependências. No Windows, execute `Abrir Doc.Automax.bat` para iniciar um servidor local e abrir o sistema no navegador. O script requer Python 3. Também é possível abrir `index.html` diretamente, mas o servidor local é mais confiável para recursos do navegador, como a consulta ao ViaCEP.

Para disponibilizar o sistema a uma equipe ou acessá-lo pelo celular, publique `index.html` e `logo.png` juntos em um servidor de arquivos estáticos ou servidor web interno e abra o endereço fornecido pelo servidor no navegador do computador ou do celular. O layout adapta menu, barra de ações, formulários e tabela financeira a telas pequenas.

É necessária conexão com a internet para carregar Tailwind CSS, `html2pdf.js` e para consultar o serviço ViaCEP durante o preenchimento do CEP. A geração dos PDFs e o preenchimento dos documentos acontecem no navegador.

## Como usar

1. Escolha um formulário no menu lateral.
2. Preencha os campos. Nos três contratos, os campos essenciais e o formato do e-mail são verificados antes de gerar o documento.
3. Use **Gerar Contrato** para revisar os contratos de varejo, vendas diretas e e-commerce.
4. Use **Editar Dados** para voltar ao preenchimento.
5. Use **Baixar PDF** para exportar o formulário/documento ativo ou **Limpar** para apagar os campos do formulário atual.

O CEP é consultado automaticamente ao sair do campo, quando contém oito dígitos. Se a busca não funcionar, preencha o endereço manualmente.

## Dados e privacidade

O projeto não tem servidor próprio, login ou banco de dados. Os dados preenchidos não são salvos pelo aplicativo e podem ser perdidos ao atualizar ou fechar a página. A consulta ao ViaCEP envia o CEP informado ao serviço externo. Os demais dados do formulário são processados no navegador para montar o documento e gerar o PDF.

## Arquivos do projeto

- `index.html`: interface, estilos e lógica dos formulários.
- `logo.png`: logotipo exibido na interface e nos documentos.
- `Abrir Doc.Automax.bat`: inicia o servidor local e abre o aplicativo no navegador do Windows.

## Manutenção

Os formulários e os contratos estão no `index.html`. A lista de modelos de veículos e as integrações com ViaCEP e geração de PDF também ficam nesse arquivo. Como os recursos de CSS e PDF são carregados por CDN, o sistema depende da disponibilidade desses serviços e de acesso à internet.
