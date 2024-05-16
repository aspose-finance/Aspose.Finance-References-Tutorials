---
title: Adicionar referência de esquema ao documento XBRL
linktitle: Adicionar referência de esquema ao documento XBRL
second_title: API Aspose.Finance .NET
description: Aprenda como adicionar referências de esquema a documentos XBRL usando Aspose.Finance for .NET. Simplifique seu processamento de dados financeiros hoje!
type: docs
weight: 15
url: /pt/net/xbrl-file-creation/add-schema-reference-to-xbrl-document/
---
## Apresentando Aspose.Finance para .NET
Aspose.Finance for .NET é uma biblioteca poderosa que fornece funcionalidades abrangentes para processamento e manipulação de documentos e dados financeiros em aplicativos .NET. Esteja você criando software de contabilidade, ferramentas de análise financeira ou qualquer outro aplicativo financeiro, o Aspose.Finance for .NET oferece uma ampla gama de recursos para agilizar seu processo de desenvolvimento.
## Pré-requisitos
Antes de começar a usar o Aspose.Finance for .NET, certifique-se de ter os seguintes pré-requisitos configurados:
### 1. Instale o Visual Studio
Certifique-se de ter o Visual Studio instalado em seu sistema. Você pode baixá-lo e instalá-lo no site oficial da Microsoft.
### 2. Obtenha uma licença Aspose.Finance
Para utilizar todos os recursos do Aspose.Finance for .NET, você precisa adquirir uma licença válida. Você pode comprar uma licença de[aqui](https://purchase.aspose.com/buy) ou opte por uma licença temporária para fins de teste.
### 3. Baixe e consulte Aspose.Finance para .NET
 Baixe a biblioteca Aspose.Finance para .NET em[página de lançamentos](https://releases.aspose.com/finance/net/) e referencie-o em seu projeto .NET.
### 4. Acesse documentação e suporte
 Consulte o[Documentação da API](https://reference.aspose.com/finance/net/) para obter informações detalhadas sobre como usar Aspose.Finance for .NET. Além disso, você pode procurar ajuda da comunidade Aspose.Finance no site[Fórum de suporte](https://forum.aspose.com/c/finance/43).
## Importando Namespaces
Vamos começar importando os namespaces necessários para o seu projeto .NET:
## Etapa 1: adicionar namespace Aspose.Finance
```csharp
using Aspose.Finance.Xbrl;
using System;
```
Este namespace contém classes e métodos para trabalhar com documentos e dados XBRL.
Agora, vamos dividir o exemplo fornecido em várias etapas para entender como adicionar uma referência de esquema a um documento XBRL usando Aspose.Finance for .NET.
## Etapa 1: definir diretórios de origem e saída
```csharp
// Diretório de origem
string sourceDir = "Your Source Directory";
// Diretório de saída
string outputDir = "Your Output Directory";
```
 Substituir`"Your Source Directory"` e`"Your Output Directory"`com os caminhos reais para seus diretórios de origem e saída, respectivamente.
## Etapa 2: crie um documento XBRL
```csharp
XbrlDocument document = new XbrlDocument();
```
Isso cria uma nova instância do documento XBRL.
## Etapa 3: acessar instâncias XBRL
```csharp
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
Isso recupera a coleção de instâncias XBRL do documento e adiciona uma nova instância a ele.
## Etapa 4: adicionar referência de esquema
```csharp
SchemaRefCollection schemaRefs = xbrlInstance.SchemaRefs;
schemaRefs.Add(sourceDir + @"schema.xsd", "example", "http://exemplo.com/xbrl/taxonomy");
```
 Isso adiciona uma referência de esquema à instância XBRL. Substituir`"schema.xsd"` com o nome real do seu arquivo de esquema,`"example"` com um prefixo adequado, e`"http://example.com/xbrl/taxonomy"` com o URI do namespace de destino.
## Etapa 5: salve o documento
```csharp
document.Save(outputDir + @"document2.xbrl");
```
Isso salva o documento XBRL modificado no diretório de saída especificado.
## Conclusão
Concluindo, Aspose.Finance for .NET oferece uma solução robusta para lidar com documentos e dados financeiros em aplicativos .NET. Seguindo as etapas descritas neste tutorial, você pode integrar facilmente o Aspose.Finance em seus projetos e manipular documentos XBRL com eficiência.
## Perguntas frequentes
 (Perguntas frequentes)
### 1. Posso usar Aspose.Finance for .NET sem licença?
Não, você precisa de uma licença válida para utilizar todos os recursos do Aspose.Finance for .NET. No entanto, você pode obter uma licença temporária para fins de teste.
### 2. O Aspose.Finance é adequado para construir software de contabilidade?
Sim, o Aspose.Finance oferece funcionalidades abrangentes para processamento de dados financeiros, tornando-o ideal para a construção de software de contabilidade e aplicativos relacionados.
### 3. Onde posso encontrar suporte para Aspose.Finance?
Você pode buscar ajuda da comunidade Aspose.Finance no fórum de suporte oficial.
### 4. Posso personalizar o prefixo de referência do esquema?
Sim, você pode escolher um prefixo adequado ao adicionar uma referência de esquema a um documento XBRL usando Aspose.Finance for .NET.
### 5. O Aspose.Finance oferece suporte a outros formatos financeiros além do XBRL?
Sim, Aspose.Finance oferece suporte a vários formatos e padrões financeiros, permitindo integração perfeita em diversas aplicações financeiras.