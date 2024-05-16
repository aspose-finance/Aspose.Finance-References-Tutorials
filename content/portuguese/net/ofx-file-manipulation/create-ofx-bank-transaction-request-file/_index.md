---
title: Criar arquivo de solicitação de transação bancária OFX
linktitle: Criar arquivo de solicitação de transação bancária OFX
second_title: API Aspose.Finance .NET
description: Aprenda como criar um arquivo de solicitação de transação bancária OFX usando Aspose.Finance for .NET com nosso guia passo a passo detalhado. #Aspose #Finanças
type: docs
weight: 12
url: /pt/net/ofx-file-manipulation/create-ofx-bank-transaction-request-file/
---
Criar um arquivo de solicitação de transação bancária OFX pode parecer assustador, mas com as ferramentas e orientações certas, pode ser um processo simples. Neste tutorial, orientaremos você em cada etapa da geração de um arquivo de solicitação de transação bancária OFX usando Aspose.Finance for .NET. Abordaremos os pré-requisitos, os namespaces necessários e forneceremos um guia passo a passo detalhado para garantir que você possa acompanhar facilmente.
## Pré-requisitos
Antes de mergulharmos no tutorial, há algumas coisas que você precisa ter em mente:
1.  Visual Studio: certifique-se de ter o Visual Studio instalado em seu computador. Você pode baixá-lo no[website oficial](https://visualstudio.microsoft.com/).
2.  Aspose.Finance for .NET: Você precisa da biblioteca Aspose.Finance for .NET. Você pode baixá-lo em[aqui](https://releases.aspose.com/finance/net/).
3. Conhecimento básico de C#: Compreender os fundamentos da programação C# o ajudará a acompanhar os exemplos de código.
Depois de definir esses pré-requisitos, você estará pronto para começar!
## Importar namespaces
Primeiro, vamos importar os namespaces necessários. Esses namespaces são cruciais para acessar as classes e métodos necessários para criar o arquivo de solicitação de transação bancária OFX.
```csharp
using Aspose.Finance.Ofx;
using Aspose.Finance.Ofx.Bank;
using Aspose.Finance.Ofx.Signon;
using System;
```
## Etapa 1: configurar o diretório de trabalho
Antes de começarmos a criar o arquivo de solicitação OFX, precisamos especificar o diretório de saída onde o arquivo será salvo.
```csharp
string outputDir = "Your Output Directory";
```
 Substituir`"Your Output Directory"` com o caminho para o diretório onde deseja salvar o arquivo gerado.
## Etapa 2: Crie o documento de solicitação OFX
 Em seguida, precisamos criar uma instância do`OfxRequestDocument` aula. Esta classe servirá como contêiner para nossa solicitação OFX.
```csharp
OfxRequestDocument document = new OfxRequestDocument();
```
## Etapa 3: configurar a solicitação de logon
solicitação de signon é essencial para autenticar o usuário e iniciar a sessão OFX. Configuraremos a mensagem de solicitação de login e a preencheremos com os detalhes necessários, como data do cliente, ID do usuário, senha e informações da instituição financeira.
```csharp
document.SignonRequestMessageSetV1 = new SignonRequestMessageSetV1();
SignonRequest signonRequest = new SignonRequest();
document.SignonRequestMessageSetV1.SignonRequest = signonRequest;
signonRequest.ClientDate = "20200611000000";
signonRequest.UserId = "aspose";
signonRequest.UserPassword = "password";
FinancialInstitution fi = new FinancialInstitution();
fi.Organization = "aspose";
fi.FinancialInstitutionId = "1";
signonRequest.FinancialInstitution = fi;
signonRequest.AppVersion = "1.0";
signonRequest.AppId = "Aspose.Finance";
signonRequest.ClientUserId = "aaaaaaa";
```
## Etapa 4: configurar a mensagem de solicitação bancária
Agora que a solicitação de login está configurada, passaremos para a criação da mensagem de solicitação bancária. Esta mensagem conterá os dados da conta bancária e a solicitação do extrato da transação.
```csharp
document.BankRequestMessageSetV1 = new BankRequestMessageSetV1();
StatementTransactionRequest stmtTransRequest = new StatementTransactionRequest();
document.BankRequestMessageSetV1.StatementTransactionRequests.Add(stmtTransRequest);
stmtTransRequest.TransactionUniqueId = "1111111";
stmtTransRequest.StatementRequest = new StatementRequest();
stmtTransRequest.StatementRequest.BankAccountFrom = new BankAccount();
stmtTransRequest.StatementRequest.BankAccountFrom.BankId = "sssss";
stmtTransRequest.StatementRequest.BankAccountFrom.AccountId = "sfsdfsfsdf";
stmtTransRequest.StatementRequest.BankAccountFrom.AccountType = AccountEnum.CHECKING;
```
## Etapa 5: incluir detalhes da transação
 Para recuperar transações específicas, precisamos especificar o intervalo de datas e se devemos incluir transações na solicitação. Isto é feito configurando o`IncTransaction` objeto.
```csharp
stmtTransRequest.StatementRequest.IncTransaction = new IncTransaction();
stmtTransRequest.StatementRequest.IncTransaction.StartDate = "20200601000000";
stmtTransRequest.StatementRequest.IncTransaction.EndDate = "20200611000000";
stmtTransRequest.StatementRequest.IncTransaction.Include = true;
```
## Etapa 6: salve o documento de solicitação OFX
Por fim, salvaremos o documento de solicitação OFX nos formatos XML e SGML. Isso garante compatibilidade com diferentes sistemas que podem usar qualquer um dos formatos.
```csharp
document.Save(outputDir + @"newOfxRequestBankStatement.xml", OfxVersionEnum.V2x);
document.Save(outputDir + @"newOfxRequestBankStatement.sgml", OfxVersionEnum.V1x);
```
## Etapa 7: confirme a execução bem-sucedida
Para confirmar que o processo foi executado com sucesso, podemos imprimir uma mensagem no console.
```csharp
Console.WriteLine("CreateOfxBankTransactionRequestFile executed successfully.");
```
## Conclusão
A criação de um arquivo de solicitação de transação bancária OFX usando Aspose.Finance for .NET é um processo metódico que envolve a configuração de um documento de solicitação, configuração de mensagens de conexão e solicitação bancária, especificação de detalhes da transação e salvamento do documento. Seguindo este guia passo a passo, você pode gerar com eficiência arquivos de solicitação OFX adaptados às suas necessidades específicas.
## Perguntas frequentes
### 1. O que é um arquivo OFX?
Um arquivo OFX (Open Financial Exchange) é um formato padrão usado para troca de dados financeiros entre instituições e usuários. É amplamente utilizado para extratos bancários, transações e outras atividades financeiras.
### 2. Posso usar Aspose.Finance for .NET com outras linguagens de programação?
Aspose.Finance for .NET foi projetado especificamente para uso com linguagens .NET como C#. No entanto, você pode usá-lo em qualquer ambiente compatível com .NET.
### 3. Existe uma avaliação gratuita disponível para Aspose.Finance for .NET?
Sim, você pode baixar uma avaliação gratuita do Aspose.Finance for .NET em[aqui](https://releases.aspose.com/).
### 4. Como obtenho suporte para Aspose.Finance for .NET?
 Você pode obter suporte da comunidade Aspose e da equipe técnica por meio de seus[Fórum de suporte](https://forum.aspose.com/c/finance/43).
### 5. Posso obter uma licença temporária do Aspose.Finance for .NET?
 Sim, Aspose oferece um[licença temporária](https://purchase.aspose.com/temporary-license/) que você pode usar para avaliar o produto.