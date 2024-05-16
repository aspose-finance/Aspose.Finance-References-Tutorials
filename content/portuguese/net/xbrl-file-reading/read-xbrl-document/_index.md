---
title: Leia o documento XBRL
linktitle: Leia o documento XBRL
second_title: API Aspose.Finance .NET
description: Aprenda como ler documentos XBRL em .NET usando Aspose.Finance. Aprimore seus recursos de processamento de dados financeiros sem esforço. #Aspose #Finanças #XBRL
type: docs
weight: 11
url: /pt/net/xbrl-file-reading/read-xbrl-document/
---
## Introdução
Aspose.Finance for .NET é uma ferramenta robusta de desenvolvimento de software financeiro que capacita os desenvolvedores a gerenciar com eficiência dados financeiros em seus aplicativos .NET. Um de seus principais recursos é a capacidade de ler documentos XBRL (eXtensible Business Reporting Language) perfeitamente. Neste guia abrangente, percorreremos o processo de leitura de documentos XBRL usando Aspose.Finance for .NET. Ao final deste tutorial, você terá um conhecimento sólido de como aproveitar essa funcionalidade para aprimorar seus recursos de processamento de dados financeiros.
## Pré-requisitos
Antes de mergulharmos no tutorial, vamos garantir que você tenha tudo o que precisa:
### Ambiente de desenvolvimento .NET
Em primeiro lugar, certifique-se de ter um ambiente de desenvolvimento .NET configurado em sua máquina. Se ainda não o fez, você pode baixar e instalar a versão mais recente do .NET SDK no site oficial da Microsoft.
### Aspose.Finance para .NET
Para acompanhar este tutorial, você precisará ter o Aspose.Finance for .NET instalado em seu ambiente de desenvolvimento. Você pode baixar a biblioteca no link de download oficial fornecido abaixo:
[Baixe Aspose.Finance para .NET](https://releases.aspose.com/finance/net/)
### Documento XBRL
Prepare um documento XBRL que você pretende ler usando Aspose.Finance for .NET. Certifique-se de ter o caminho do arquivo pronto para referência em seu código.
## Importar namespaces
Vamos começar importando os namespaces necessários para o seu projeto .NET para acessar as funcionalidades do Aspose.Finance. Siga estas instruções passo a passo:
## Etapa 1: abra seu projeto .NET
Inicie seu projeto .NET em seu ambiente de desenvolvimento integrado (IDE) preferido, como o Visual Studio.
## Etapa 2: adicionar referência Aspose.Finance
Adicione uma referência ao Aspose.Finance for .NET em seu projeto. Você pode conseguir isso baixando a biblioteca e referenciando-a localmente ou usando o NuGet Package Manager para instalá-la diretamente em seu projeto.
## Etapa 3: importar namespaces
Agora, importe os namespaces necessários no início do seu arquivo de código. Esses namespaces fornecem acesso às classes e métodos necessários para trabalhar com documentos XBRL.
```csharp
using Aspose.Finance.Xbrl;
using System;
using System.Collections.Generic;
```
## Leia o documento XBRL
Agora que configuramos nosso ambiente e importamos os namespaces necessários, vamos mergulhar no processo de leitura de um documento XBRL usando Aspose.Finance for .NET. Siga estas instruções passo a passo:
## Etapa 1: definir o diretório de origem
 Comece definindo o caminho do diretório onde seu documento XBRL está localizado. Substituir`"Your Source Directory"` com o caminho real para o seu documento.
```csharp
string sourceDir = "Your Source Directory";
```
## Etapa 2: Criar objeto XbrlDocument
 A seguir, crie um`XbrlDocument` objeto fornecendo o caminho para seu documento XBRL.
```csharp
XbrlDocument document = new XbrlDocument(sourceDir + @"IdScopeContextPeriodStartAfterEnd.xml");
```
## Etapa 3: acessar instâncias XBRL
 Acesse as instâncias XBRL do documento usando o`XbrlInstances` propriedade.
```csharp
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[0];
```
## Etapa 4: extrair fatos, referências de esquema, contextos e unidades
Recupere fatos, referências de esquema, contextos e unidades da instância XBRL.
```csharp
List<Fact> facts = xbrlInstance.Facts;
SchemaRefCollection schemaRefs = xbrlInstance.SchemaRefs;
List<Context> contexts = xbrlInstance.Contexts;
List<Unit> units = xbrlInstance.Units;
```
## Etapa 5: exibir mensagem de sucesso
Informe ao usuário que o documento XBRL foi lido com sucesso.
```csharp
Console.WriteLine("ReadXbrlDocument executed successfully.");
```
Seguindo essas etapas, você leu com êxito um documento XBRL usando Aspose.Finance for .NET.
## Conclusão
Neste tutorial, cobrimos o processo de leitura de documentos XBRL usando Aspose.Finance for .NET. Aproveitando o guia passo a passo fornecido, você pode lidar com documentos XBRL com eficiência em seus aplicativos .NET, aprimorando seus recursos de processamento de dados financeiros.
## Perguntas frequentes
### O Aspose.Finance for .NET é compatível com todas as versões do .NET?
Sim, o Aspose.Finance for .NET foi projetado para ser compatível com todas as versões do .NET framework, garantindo integração perfeita em seus projetos.
### Posso usar Aspose.Finance para projetos comerciais?
Absolutamente! Aspose.Finance for .NET pode ser usado para projetos pessoais e comerciais. Basta adquirir uma licença para desbloquear todo o seu potencial.
### O Aspose.Finance oferece suporte a outros formatos de documento além do XBRL?
Sim, Aspose.Finance oferece suporte para diversos formatos de documentos financeiros, oferecendo flexibilidade e versatilidade no tratamento de dados financeiros.
### O suporte técnico está disponível para usuários do Aspose.Finance?
Certamente! Aspose oferece suporte técnico dedicado para seus produtos, incluindo Aspose.Finance. Você pode acessar o suporte através do fórum de suporte oficial.
### Posso experimentar o Aspose.Finance antes de fazer uma compra?
Claro! Aspose oferece uma versão de teste gratuita do Aspose.Finance, permitindo que você explore seus recursos e capacidades antes de assumir um compromisso.