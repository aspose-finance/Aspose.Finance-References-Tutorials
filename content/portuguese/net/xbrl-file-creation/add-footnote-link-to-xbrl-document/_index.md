---
title: Adicionar link de nota de rodapé ao documento XBRL
linktitle: Adicionar link de nota de rodapé ao documento XBRL
second_title: API Aspose.Finance .NET
description: Aprenda como adicionar links de notas de rodapé a documentos XBRL usando Aspose.Finance for .NET. Aprimore relatórios financeiros com contexto adicional sem esforço.
type: docs
weight: 12
url: /pt/net/xbrl-file-creation/add-footnote-link-to-xbrl-document/
---
Adicionar um link de nota de rodapé a um documento XBRL é crucial para fornecer contexto adicional ou explicações para pontos de dados específicos. Neste tutorial, percorreremos o processo passo a passo usando Aspose.Finance for .NET.
## Pré-requisitos
Antes de começarmos, certifique-se de ter os seguintes pré-requisitos em vigor:
1.  Aspose.Finance for .NET: Certifique-se de ter instalado o Aspose.Finance for .NET em seu sistema. Você pode baixá-lo em[aqui](https://releases.aspose.com/finance/net/).
  
2. Ambiente de desenvolvimento: tenha um ambiente de desenvolvimento configurado com .NET Framework ou .NET Core.
## Importar namespaces:
```csharp
using Aspose.Finance.Xbrl;
using System;
```
## Etapa 1: definir diretórios de origem e saída
Primeiro, especifique os diretórios dos arquivos de origem e de saída:
```csharp
// Diretório de origem
string sourceDir = "Your Source Directory";
// Diretório de saída
string outputDir = "Your Output Directory";
```
## Etapa 2: crie um documento e uma instância XBRL
Inicialize um documento e uma instância XBRL:
```csharp
XbrlDocument document = new XbrlDocument();
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
## Etapa 3: adicionar referências de esquema
Adicione referências de esquema à instância XBRL:
```csharp
SchemaRefCollection schemaRefs = xbrlInstance.SchemaRefs;
schemaRefs.Add(sourceDir + @"schema.xsd", "example", "http://exemplo.com/xbrl/taxonomy");
SchemaRef schema = schemaRefs[0];
```
## Etapa 4: definir o contexto
Defina o contexto para a instância XBRL:
```csharp
ContextPeriod contextPeriod = new ContextPeriod(DateTime.Parse("2020-01-01"), DateTime.Parse("2020-02-10"));
ContextEntity contextEntity = new ContextEntity("exampleIdentifierScheme", "exampleIdentifier");
Context context = new Context(contextPeriod, contextEntity);
context.Id = "cd1";
xbrlInstance.Contexts.Add(context);
```
## Etapa 5: adicionar link de nota de rodapé
Crie e adicione um link de nota de rodapé à instância XBRL:
```csharp
FootnoteLink footnoteLink = new FootnoteLink();
Footnote footnote = new Footnote("footnote1");
footnote.Text = "Including the effects of the merger.";
Loc loc = new Loc("#cd1", "fact1");
FootnoteArc footnoteArc = new FootnoteArc(loc.Label, footnote.Label);
footnoteLink.Footnotes.Add(footnote);
footnoteLink.Locators.Add(loc);
footnoteLink.FootnoteArcs.Add(footnoteArc);
xbrlInstance.FootnoteLinks.Add(footnoteLink);
```
## Etapa 6: salve o documento
Salve o documento XBRL modificado:
```csharp
document.Save(outputDir + @"document6.xbrl");
```

## Conclusão
Adicionar um link de nota de rodapé a um documento XBRL é um processo simples com Aspose.Finance for .NET. Seguindo as etapas descritas neste tutorial, você pode incorporar facilmente contexto ou explicações adicionais em seus relatórios financeiros.
## Perguntas frequentes
### Posso adicionar vários links de notas de rodapé a um único documento XBRL?
Sim, você pode adicionar vários links de notas de rodapé repetindo as etapas descritas neste tutorial para cada link adicional.
### O Aspose.Finance for .NET é compatível com .NET Framework e .NET Core?
Sim, Aspose.Finance for .NET oferece suporte a ambientes .NET Framework e .NET Core.
### Como posso obter uma licença temporária do Aspose.Finance for .NET?
 Você pode obter uma licença temporária em[aqui](https://purchase.aspose.com/temporary-license/).
### O Aspose.Finance for .NET fornece suporte para validação XBRL?
Sim, o Aspose.Finance for .NET oferece suporte abrangente para validação XBRL para garantir a conformidade com os padrões do setor.
### Onde posso encontrar recursos adicionais e suporte para Aspose.Finance for .NET?
 Você pode visitar o[Fórum Aspose.Finance para .NET](https://forum.aspose.com/c/finance/43) para documentação de suporte e acesso[aqui](https://reference.aspose.com/finance/net/).