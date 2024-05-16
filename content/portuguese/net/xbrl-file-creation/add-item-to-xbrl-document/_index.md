---
title: Adicionar item ao documento XBRL
linktitle: Adicionar item ao documento XBRL
second_title: API Aspose.Finance .NET
description: Aprenda como adicionar itens a documentos XBRL usando Aspose.Finance for .NET. Simplifique os relatórios financeiros em seus aplicativos .NET. #Aspose #Finanças
type: docs
weight: 13
url: /pt/net/xbrl-file-creation/add-item-to-xbrl-document/
---
Extensible Business Reporting Language (XBRL) tornou-se um formato padrão para relatórios financeiros, permitindo a comunicação eficiente e precisa de dados financeiros. Aspose.Finance for .NET fornece funcionalidade robusta para trabalhar com documentos XBRL em seus aplicativos .NET. Neste tutorial, percorreremos as etapas para adicionar um item a um documento XBRL usando Aspose.Finance for .NET.
## Pré-requisitos
Antes de começarmos, certifique-se de ter os seguintes pré-requisitos:
### 1. Instale Aspose.Finance para .NET
 Se ainda não o fez, baixe e instale Aspose.Finance for .NET do[website oficial](https://releases.aspose.com/finance/net/). Siga as instruções de instalação para configurar a biblioteca em seu ambiente .NET.
### 2. Configure seu ambiente de desenvolvimento
Certifique-se de ter um ambiente de desenvolvimento funcional para desenvolvimento .NET. Você precisará de um IDE compatível, como o Visual Studio, junto com o framework .NET instalado em seu sistema.
## Importar namespaces
Primeiro, importe os namespaces necessários para seu aplicativo .NET para utilizar a funcionalidade fornecida pelo Aspose.Finance for .NET.
```csharp
using Aspose.Finance.Xbrl;
using System;
```
#Agora vamos dividir o código de exemplo em várias etapas:
## Etapa 1: definir diretórios de origem e saída
```csharp
string sourceDir = "Your Source Directory";
string outputDir = "Your Output Directory";
```
 Substituir`"Your Source Directory"` e`"Your Output Directory"` com os caminhos para seus diretórios de origem e saída, respectivamente.
## Etapa 2: crie um documento e uma instância XBRL
```csharp
XbrlDocument document = new XbrlDocument();
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
Inicialize um documento XBRL e uma instância para trabalhar.
## Etapa 3: adicionar referência de esquema
```csharp
SchemaRefCollection schemaRefs = xbrlInstance.SchemaRefs;
schemaRefs.Add(sourceDir + @"schema.xsd", "example", "http://exemplo.com/xbrl/taxonomy");
```
Adicione uma referência de esquema à instância XBRL, fornecendo o caminho para o arquivo de esquema e especificando detalhes do namespace.
## Etapa 4: Definir Contexto e Entidade
```csharp
ContextPeriod contextPeriod = new ContextPeriod(DateTime.Parse("2020-01-01"), DateTime.Parse("2020-02-10"));
ContextEntity contextEntity = new ContextEntity("exampleIdentifierScheme", "exampleIdentifier");
Context context = new Context(contextPeriod, contextEntity);
xbrlInstance.Contexts.Add(context);
```
Crie um contexto e uma entidade para a instância XBRL, especificando o período e os detalhes da entidade.
## Etapa 5: adicionar unidade
```csharp
Unit unit = new Unit(UnitType.Measure);
unit.MeasureQualifiedNames.Add(new QualifiedName("USD", "iso4217", "http://www.xbrl.org/2003/iso4217"));
xbrlInstance.Units.Add(unit);
```
Defina uma unidade para a instância XBRL, especificando os nomes qualificados da medida.
## Etapa 6: adicionar item
```csharp
Concept fixedAssetsConcept = schema.GetConceptByName("fixedAssets");
if (fixedAssetsConcept != null)
{
    Item item = new Item(fixedAssetsConcept);
    item.ContextRef = context;
    item.UnitRef = unit;
    item.Precision = 4;
    item.Value = "1444";
    xbrlInstance.Facts.Add(item);
}
```
Adicione um item à instância XBRL, especificando seu conceito, contexto, unidade, precisão e valor.
## Etapa 7: Salvar documento
```csharp
document.Save(outputDir + @"document5.xbrl");
```
Salve o documento XBRL no diretório de saída.
## Conclusão
Adicionar itens a um documento XBRL é essencial para representar dados financeiros com precisão. Aspose.Finance for .NET simplifica esse processo, fornecendo uma API abrangente para trabalhar com documentos XBRL em aplicativos .NET.
## Perguntas frequentes
### Posso usar o Aspose.Finance for .NET com qualquer aplicativo .NET?
Sim, Aspose.Finance for .NET é compatível com qualquer aplicativo .NET, incluindo aplicativos ASP.NET, WinForms e Console.
### O uso do Aspose.Finance for .NET é gratuito?
 Aspose.Finance for .NET é uma biblioteca comercial. Você pode baixar uma versão de teste gratuita para avaliar seus recursos e as licenças podem ser adquiridas em[aqui](https://purchase.aspose.com/buy).
### O Aspose.Finance for .NET oferece suporte a outros formatos de relatórios financeiros além do XBRL?
Aspose.Finance for .NET concentra-se principalmente na funcionalidade relacionada ao XBRL. Porém, Aspose oferece outras bibliotecas para trabalhar com diversos formatos financeiros.
### Como posso obter suporte para Aspose.Finance for .NET?
 Você pode obter suporte para Aspose.Finance for .NET por meio do[fórum oficial](https://forum.aspose.com/c/finance/43)onde você pode fazer perguntas e interagir com outros usuários e equipe de suporte.
### Posso obter uma licença temporária para Aspose.Finance for .NET?
 Sim, licenças temporárias do Aspose.Finance for .NET estão disponíveis para fins de teste. Você pode obter um[aqui](https://purchase.aspose.com/temporary-license/).