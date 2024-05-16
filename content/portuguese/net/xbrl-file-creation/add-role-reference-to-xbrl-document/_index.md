---
title: Adicionar referência de função ao documento XBRL
linktitle: Adicionar referência de função ao documento XBRL
second_title: API Aspose.Finance .NET
description: Aprenda como adicionar referências de função a documentos XBRL usando Aspose.Finance for .NET. Simplifique os relatórios financeiros em seus aplicativos .NET com este tutorial.
type: docs
weight: 14
url: /pt/net/xbrl-file-creation/add-role-reference-to-xbrl-document/
---
XBRL (eXtensible Business Reporting Language) tornou-se um padrão para troca de informações comerciais, especialmente em relatórios financeiros. Aspose.Finance for .NET simplifica o trabalho com documentos XBRL em aplicativos .NET. Este tutorial irá guiá-lo através do processo de adição de uma referência de função a um documento XBRL usando Aspose.Finance for .NET.
## Pré-requisitos
Antes de começarmos, certifique-se de ter os seguintes pré-requisitos:
### 1. Instale Aspose.Finance para .NET
Certifique-se de ter o Aspose.Finance for .NET instalado em seu ambiente de desenvolvimento. Se ainda não o fez, baixe-o no[lançamentos](https://releases.aspose.com/finance/net/) e siga as instruções de instalação.
### 2. Configure seu ambiente de desenvolvimento
Certifique-se de ter um ambiente de desenvolvimento funcional para desenvolvimento .NET. Isso inclui um IDE compatível, como o Visual Studio e o .NET framework instalado em seu sistema.
## Importar namespaces
Comece importando os namespaces necessários para seu aplicativo .NET para acessar a funcionalidade fornecida pelo Aspose.Finance for .NET.
```csharp
using Aspose.Finance.Xbrl;
using System;
using Aspose
.Finance.Xbrl.Roles;
```
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
## Etapa 4: recuperar o tipo de função e adicionar referência de função
```csharp
SchemaRef schema = schemaRefs[0];
RoleType roleType = schema.GetRoleTypeByURI("http://abc.com/role/link1");
if (roleType != null)
{
    RoleReference roleReference = new RoleReference(roleType);
    xbrlInstance.RoleReferences.Add(roleReference);
}
```
Recupere o tipo de função usando seu URI e adicione uma referência de função à instância XBRL.
## Etapa 5: Salvar documento
```csharp
document.Save(outputDir + @"document7.xbrl");
```
Salve o documento XBRL no diretório de saída.
## Conclusão
Adicionar referências de funções a documentos XBRL é crucial para definir as funções de vários elementos no documento. Aspose.Finance for .NET fornece uma maneira direta de realizar essa tarefa, capacitando os desenvolvedores a trabalhar de forma eficiente com documentos XBRL em seus aplicativos .NET.
## Perguntas frequentes
### Posso usar o Aspose.Finance for .NET com qualquer aplicativo .NET?
Sim, Aspose.Finance for .NET é compatível com qualquer aplicativo .NET, incluindo aplicativos ASP.NET, WinForms e Console.
### O uso do Aspose.Finance for .NET é gratuito?
 Aspose.Finance for .NET é uma biblioteca comercial. Você pode baixar uma versão de teste gratuita para avaliar seus recursos e as licenças podem ser adquiridas em[aqui](https://purchase.aspose.com/buy).
### O Aspose.Finance for .NET oferece suporte a outros formatos de relatórios financeiros além do XBRL?
Aspose.Finance for .NET concentra-se principalmente na funcionalidade relacionada ao XBRL. Porém, Aspose oferece outras bibliotecas para trabalhar com diversos formatos financeiros.
### Como posso obter suporte para Aspose.Finance for .NET?
 Você pode obter suporte para Aspose.Finance for .NET por meio do[fórum](https://forum.aspose.com/c/finance/43)onde você pode fazer perguntas e interagir com outros usuários e equipe de suporte.
### Posso obter uma licença temporária para Aspose.Finance for .NET?
 Sim, licenças temporárias do Aspose.Finance for .NET estão disponíveis para fins de teste. Você pode obter um[aqui](https://purchase.aspose.com/temporary-license/).