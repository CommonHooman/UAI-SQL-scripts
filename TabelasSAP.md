# Tabelas "Mestras" e Tabelas "Subordinadas"

No SAP, várias tabelas são consideradas "principais" e possuem outras tabelas "subordinadas". Isto é facilmente observado nas tabelas referentes a 
documentos de marketing (NF de entrada/saída, Pedido de Compra, Recebimento, Devolução, etc.)

Um bom exemplo disso é a tabela OINV, referente à tela de "Nota Fiscal de Saída", nessa tabela há campos como _DocNum_, _DocEntry_, _ObjType_, _DocDate_, _CardName_, etc.
Ou seja, campos gerais referentes à uma única nota fiscal (ou documento) inserida no SAP. Sendo assim, uma mesma nota fiscal pode ser referente à venda de 
vários produtos, cada um com seus próprios valores, impostos, grupos de itens, etc. Dessa forma, uma nota fiscal possui dados gerais relacionados ao documento como um
todo, assim como várias linha relacionadas à venda/compra de cada item englobado pela nota.

A tabela referente à tais "linhas de itens englobados pela nota" é considerada uma tabela "subordinada" da tabela principal relacionada à nota como um todo. No exemplo
dado previamente, a tabela "mestra" seria a OINV e sua tabela "subordinada" relacionada às linhas seria a INV1. Além disso, há várias outras tabelas subordinadas além
da tabela de "linhas do documento", como por exemplo as tabelas de:

- Dados do Parceiro de Negócio (cliente/fornecedor) referenciado pelo documento;
  - _Indicada pelo número '12' após o nome do documento_ (INV12, RIN12, PCH12, RPC12)

- Impostos sobre cada item (linha da tabela de linhas);
  - _Indicada pelo número '4' após o nome do documento_ (INV4, RIN4, PCH4, RPC4)

- Impostos retidos sobre cada item;
  - _Indicada pelo número '5' após o nome do documento_ (INV5, RIN5, PCH5, RPC5)

- Etc.

## Links Úteis

- Lista de várias tabelas com descrição, Primary Key e seu _ObjType_ -> https://blogs.sap.com/2017/04/27/list-of-object-types/

- Todas as tabelas do SAP B1, seus campos e um mapa de relação entre as tabelas -> https://biuan.com/

- Todas as tabelas separadas por módulos + campos, com a opção de produzir uma query com os campos escolhidos -> http://sapref.co.uk/?schema=BusinessOne9.3

# Algumas Tabelas e suas Descrições

|   Tabela 	| Descrição  	|
|-----------|-------------|
| OINV	    | NF de saída  	|
| INV1  	  | Linhas OINV  	|
| INV12  	  | Dados do cliente da NF (CPF, endereço)  	|
| ORIN      | Devolução de NF de saida  	|
| RIN1      | Linhas ORIN  	|
| RIN12     | Dados do cliente da NF devolvida 	|
| RIN21     | "referencia NF" na aba de Impostos (fazer dev. de NF manualmente fica aqui) 	|
| OPCH      | NF de entrada 	|
| ORPC      | Devolução NF de entrada 	|
| ODLN      | Entregas (no módulo de Vendas) 	|
| ORDN      | Devolução (no módulo de Vendas)	|
| OPDN      | Recebimento de Mercadoria 	|
| ORPD      | Devolução de Mercadoria 	|
| OCRD      | Cadastro de parceiro de negócios 	|
| OBPL      | Filiais 	|
