---
title: Ajouter un élément au document XBRL
linktitle: Ajouter un élément au document XBRL
second_title: API Aspose.Finance .NET
description: Découvrez comment ajouter des éléments aux documents XBRL à l'aide d'Aspose.Finance pour .NET. Simplifiez les rapports financiers dans vos applications .NET. #Aspose #Finance
type: docs
weight: 13
url: /fr/net/xbrl-file-creation/add-item-to-xbrl-document/
---
Extensible Business Reporting Language (XBRL) est devenu un format standard pour les rapports financiers, permettant une communication efficace et précise des données financières. Aspose.Finance for .NET fournit des fonctionnalités robustes pour travailler avec des documents XBRL dans vos applications .NET. Dans ce didacticiel, nous passerons en revue les étapes permettant d'ajouter un élément à un document XBRL à l'aide d'Aspose.Finance pour .NET.
## Conditions préalables
Avant de commencer, assurez-vous de disposer des prérequis suivants :
### 1. Installez Aspose.Finance pour .NET
 Si vous ne l'avez pas déjà fait, téléchargez et installez Aspose.Finance for .NET à partir du[site officiel](https://releases.aspose.com/finance/net/). Suivez les instructions d'installation pour configurer la bibliothèque dans votre environnement .NET.
### 2. Configurez votre environnement de développement
Assurez-vous de disposer d'un environnement de développement fonctionnel pour le développement .NET. Vous aurez besoin d'un IDE compatible tel que Visual Studio, ainsi que du framework .NET installé sur votre système.
## Importer des espaces de noms
Tout d’abord, importez les espaces de noms nécessaires dans votre application .NET pour utiliser les fonctionnalités fournies par Aspose.Finance pour .NET.
```csharp
using Aspose.Finance.Xbrl;
using System;
```
#Maintenant, décomposons l'exemple de code en plusieurs étapes :
## Étape 1 : Définir les répertoires source et de sortie
```csharp
string sourceDir = "Your Source Directory";
string outputDir = "Your Output Directory";
```
 Remplacer`"Your Source Directory"` et`"Your Output Directory"` avec les chemins d'accès à vos répertoires source et de sortie, respectivement.
## Étape 2 : Créer un document et une instance XBRL
```csharp
XbrlDocument document = new XbrlDocument();
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
Initialisez un document et une instance XBRL avec lesquels travailler.
## Étape 3 : ajouter une référence de schéma
```csharp
SchemaRefCollection schemaRefs = xbrlInstance.SchemaRefs;
schemaRefs.Add(sourceDir + @"schema.xsd", "example", "http://exemple.com/xbrl/taxonomy");
```
Ajoutez une référence de schéma à l'instance XBRL, en fournissant le chemin d'accès au fichier de schéma et en spécifiant les détails de l'espace de noms.
## Étape 4 : Définir le contexte et l'entité
```csharp
ContextPeriod contextPeriod = new ContextPeriod(DateTime.Parse("2020-01-01"), DateTime.Parse("2020-02-10"));
ContextEntity contextEntity = new ContextEntity("exampleIdentifierScheme", "exampleIdentifier");
Context context = new Context(contextPeriod, contextEntity);
xbrlInstance.Contexts.Add(context);
```
Créez un contexte et une entité pour l'instance XBRL, en spécifiant les détails de la période et de l'entité.
## Étape 5 : Ajouter une unité
```csharp
Unit unit = new Unit(UnitType.Measure);
unit.MeasureQualifiedNames.Add(new QualifiedName("USD", "iso4217", "http://www.xbrl.org/2003/iso4217"));
xbrlInstance.Units.Add(unit);
```
Définissez une unité pour l'instance XBRL, en spécifiant les noms qualifiés des mesures.
## Étape 6 : Ajouter un article
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
Ajoutez un élément à l'instance XBRL, en spécifiant son concept, son contexte, son unité, sa précision et sa valeur.
## Étape 7 : Enregistrer le document
```csharp
document.Save(outputDir + @"document5.xbrl");
```
Enregistrez le document XBRL dans le répertoire de sortie.
## Conclusion
L'ajout d'éléments à un document XBRL est essentiel pour représenter avec précision les données financières. Aspose.Finance for .NET simplifie ce processus en fournissant une API complète pour travailler avec les documents XBRL dans les applications .NET.
## FAQ
### Puis-je utiliser Aspose.Finance pour .NET avec n’importe quelle application .NET ?
Oui, Aspose.Finance pour .NET est compatible avec n'importe quelle application .NET, y compris les applications ASP.NET, WinForms et Console.
### L’utilisation d’Aspose.Finance pour .NET est-elle gratuite ?
 Aspose.Finance pour .NET est une bibliothèque commerciale. Vous pouvez télécharger une version d'essai gratuite pour évaluer ses fonctionnalités, et les licences peuvent être achetées auprès de[ici](https://purchase.aspose.com/buy).
### Aspose.Finance pour .NET prend-il en charge d'autres formats de rapports financiers que XBRL ?
Aspose.Finance for .NET se concentre principalement sur les fonctionnalités liées à XBRL. Cependant, Aspose propose d'autres bibliothèques pour travailler avec différents formats financiers.
### Comment puis-je obtenir de l'aide pour Aspose.Finance pour .NET ?
 Vous pouvez obtenir une assistance pour Aspose.Finance pour .NET via le[forum officiel](https://forum.aspose.com/c/finance/43)où vous pouvez poser des questions et interagir avec d'autres utilisateurs et le personnel d'assistance.
### Puis-je obtenir une licence temporaire pour Aspose.Finance pour .NET ?
 Oui, des licences temporaires pour Aspose.Finance pour .NET sont disponibles à des fins de test. Vous pouvez en obtenir un[ici](https://purchase.aspose.com/temporary-license/).