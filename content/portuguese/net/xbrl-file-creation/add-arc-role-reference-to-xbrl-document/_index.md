---
title: Adicionar referência de função ARC ao documento XBRL
linktitle: Adicionar referência de função ARC ao documento XBRL
second_title: API Aspose.Finance .NET
description: Aprenda como manipular documentos XBRL com eficiência usando Aspose.Finance for .NET. Adicione referências de funções ARC sem esforço com orientação passo a passo.
type: docs
weight: 10
url: /pt/net/xbrl-file-creation/add-arc-role-reference-to-xbrl-document/
---
## Introdução
No mundo do gerenciamento e relatórios de dados financeiros, a eXtensible Business Reporting Language (XBRL) desempenha um papel crucial. Padroniza a forma como as informações financeiras são comunicadas e trocadas, garantindo consistência, precisão e eficiência. No entanto, a manipulação de documentos XBRL, especialmente quando incorporam funções e referências específicas, requer uma compreensão diferenciada dos mecanismos subjacentes. Este tutorial se concentra em uma dessas tarefas: adicionar uma referência de função ARC a um documento XBRL usando Aspose.Finance for .NET.
## Pré-requisitos
Antes de mergulhar no tutorial, certifique-se de ter os seguintes pré-requisitos:
### Configuração do ambiente
1.  Instale Aspose.Finance for .NET: Baixe e instale a biblioteca Aspose.Finance for .NET do[lançamentos](https://releases.aspose.com/finance/net/).
   
2. Ambiente de desenvolvimento: configure seu ambiente de desenvolvimento com Visual Studio ou qualquer outro IDE preferido.
## Importar namespaces
Certifique-se de importar os namespaces necessários em seu código C#:
```csharp
using Aspose.Finance.Xbrl;
using System;
```
## Etapa 1: definir diretórios de origem e saída
Antes de continuar, especifique os diretórios de origem e de saída onde seus arquivos XBRL serão localizados e salvos, respectivamente.
```csharp
// Diretório de origem
string sourceDir = "Your Source Directory";
// Diretório de saída
string outputDir = "Your Output Directory";
```
## Etapa 2: crie um documento XBRL
 Instanciar um`XbrlDocument` objeto para trabalhar com dados XBRL.
```csharp
XbrlDocument document = new XbrlDocument();
```
## Etapa 3: acessar a coleção XbrlInstance
Acesse a coleção de instâncias XBRL no documento.
```csharp
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
```
## Etapa 4: adicionar XbrlInstance
Adicione uma nova instância XBRL à coleção.
```csharp
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
## Etapa 5: adicionar referência de esquema
Inclua uma referência de esquema na instância XBRL, especificando o diretório de origem, o prefixo do namespace e o URI.
```csharp
SchemaRefCollection schemaRefs = xbrlInstance.SchemaRefs;
schemaRefs.Add(sourceDir + @"schema.xsd", "example", "http://exemplo.com/xbrl/taxonomy");
```
## Etapa 6: recuperar ArcroleType
 Recuperar o`ArcroleType` com base em um URI específico.
```csharp
SchemaRef schema = schemaRefs[0];
ArcroleType arcroleType = schema.GetArcroleTypeByURI("http://abc.com/arcrole/footnote-test");
```
## Etapa 7: adicionar ArcrolReference
 Se o`ArcroleType` for encontrado, crie um`ArcroleReference` e adicione-o às referências de arcole da instância XBRL.
```csharp
if (arcroleType != null)
{
    ArcroleReference arcroleReference = new ArcroleReference(arcroleType);
    xbrlInstance.ArcroleReferences.Add(arcroleReference);
}
```
## Etapa 8: salve o documento
Salve o documento XBRL modificado no diretório de saída especificado.
```csharp
document.Save(outputDir + @"document8.xbrl");
```
## Conclusão
Neste tutorial, exploramos como adicionar uma referência de função ARC a um documento XBRL usando Aspose.Finance for .NET. Seguindo estas instruções passo a passo e aproveitando os recursos do Aspose.Finance, você pode gerenciar e manipular dados XBRL com eficiência para atender aos seus requisitos específicos.
## Perguntas frequentes
### O que é XBRL?
XBRL significa eXtensible Business Reporting Language, uma linguagem padronizada para a comunicação eletrônica de dados comerciais e financeiros.
### Por que o XBRL é importante?
O XBRL garante consistência, precisão e eficiência na troca e análise de informações financeiras, beneficiando reguladores, analistas e empresas.
### O Aspose.Finance pode lidar com tarefas XBRL complexas?
Sim, Aspose.Finance oferece funcionalidade robusta para trabalhar com documentos XBRL, incluindo o tratamento de tarefas complexas, como referências de funções e gerenciamento de taxonomia.
### O Aspose.Finance é compatível com outras bibliotecas .NET?
Sim, o Aspose.Finance integra-se perfeitamente com outras bibliotecas .NET, fornecendo amplo suporte para manipulação e relatórios de dados financeiros.
### Onde posso encontrar suporte adicional para Aspose.Finance?
 Para suporte adicional, visite o[Página de suporte Aspose.Finance](https://forum.aspose.com/c/finance/43).