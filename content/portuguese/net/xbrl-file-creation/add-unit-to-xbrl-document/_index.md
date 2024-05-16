---
title: Adicionar unidade ao documento XBRL
linktitle: Adicionar unidade ao documento XBRL
second_title: API Aspose.Finance .NET
description: Aprenda como adicionar unidades a documentos XBRL sem esforço com Aspose.Finance for .NET. Aprimore seus recursos de processamento de dados financeiros hoje mesmo!
type: docs
weight: 16
url: /pt/net/xbrl-file-creation/add-unit-to-xbrl-document/
---
Bem-vindo ao mundo do Aspose.Finance for .NET - sua porta de entrada para a manipulação eficiente de documentos financeiros em aplicativos .NET. Esteja você criando software de contabilidade, ferramentas de análise financeira ou qualquer outro aplicativo financeiro, o Aspose.Finance for .NET fornece um conjunto abrangente de recursos para agilizar seu processo de desenvolvimento.
## Pré-requisitos
Antes de nos aprofundarmos no poder do Aspose.Finance for .NET, vamos garantir que temos os pré-requisitos necessários em vigor:
### 1. Instalação do Visual Studio
Certifique-se de ter o Visual Studio instalado em seu sistema. Caso contrário, você pode baixá-lo e instalá-lo no site oficial da Microsoft.
### 2. Obtenha uma licença
 Para desbloquear todo o potencial do Aspose.Finance for .NET, você precisa de uma licença válida. Você pode comprar uma licença de[aqui](https://purchase.aspose.com/buy) ou opte por uma licença temporária para fins de teste.
### 3. Baixe e consulte Aspose.Finance para .NET
 Baixe a biblioteca Aspose.Finance para .NET em[página de lançamentos](https://releases.aspose.com/finance/net/) e referencie-o em seu projeto .NET.
### 4. Acesse documentação e suporte
 Consulte o[documentação](https://reference.aspose.com/finance/net/)para obter informações detalhadas sobre a utilização do Aspose.Finance for .NET. Além disso, você pode procurar ajuda da comunidade Aspose.Finance no site[Fórum de suporte](https://forum.aspose.com/c/finance/43).
## Importando Namespaces
Agora, vamos importar os namespaces necessários para o seu projeto .NET:
## Etapa 1: adicionar namespace Aspose.Finance
```csharp
using Aspose.Finance.Xbrl;
using System;
```
Este namespace contém classes e métodos essenciais para trabalhar com documentos e dados XBRL.
Vamos dividir o exemplo fornecido em várias etapas para entender como adicionar uma unidade a um documento XBRL usando Aspose.Finance for .NET.
## Etapa 1: definir o diretório de saída
```csharp
// Diretório de saída
string outputDir = "Your Output Directory";
```
 Substituir`"Your Output Directory"` com o caminho real para o diretório de saída desejado.
## Etapa 2: crie um documento XBRL
```csharp
XbrlDocument document = new XbrlDocument();
```
Isso inicializa uma nova instância do documento XBRL.
## Etapa 3: acessar instâncias XBRL
```csharp
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
Isso recupera a coleção de instâncias XBRL do documento e adiciona uma nova instância a ele.
## Etapa 4: adicionar unidade
```csharp
Unit unit = new Unit(UnitType.Measure);
unit.MeasureQualifiedNames.Add(new QualifiedName("USD", "iso4217", "http://www.xbrl.org/2003/iso4217"));
xbrlInstance.Units.Add(unit);
```
Isso cria uma nova unidade de medida (neste caso, USD) e a adiciona à instância XBRL. Você pode ajustar o código da moeda e o URI do namespace conforme necessário.
## Etapa 5: salve o documento
```csharp
document.Save(outputDir + @"document4.xbrl");
```
Isso salva o documento XBRL modificado no diretório de saída especificado.
## Conclusão
Concluindo, Aspose.Finance for .NET capacita os desenvolvedores a manipular facilmente documentos e dados financeiros em seus aplicativos .NET. Seguindo as etapas descritas neste tutorial, você pode integrar perfeitamente o Aspose.Finance for .NET em seus projetos e aprimorar seus recursos de processamento financeiro.
## Perguntas frequentes
### 1. Posso usar Aspose.Finance for .NET sem licença?
Não, é necessária uma licença válida para desbloquear todos os recursos do Aspose.Finance for .NET. No entanto, licenças temporárias estão disponíveis para fins de teste.
### 2. O Aspose.Finance for .NET é adequado para construir software de contabilidade?
Sim, o Aspose.Finance for .NET fornece funcionalidades robustas personalizadas para a construção de software de contabilidade e aplicativos financeiros relacionados.
### 3. Onde posso encontrar suporte para Aspose.Finance for .NET?
Você pode buscar ajuda da comunidade Aspose.Finance no fórum de suporte.
### 4. Posso customizar a unidade de medida em um documento XBRL?
Sim, você pode criar e adicionar unidades de medida personalizadas a documentos XBRL usando Aspose.Finance for .NET.
### 5. O Aspose.Finance for .NET oferece suporte a várias moedas?
Sim, Aspose.Finance for .NET suporta múltiplas moedas, permitindo um processamento versátil de dados financeiros.