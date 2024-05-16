---
title: Ajouter une référence de rôle ARC au document XBRL
linktitle: Ajouter une référence de rôle ARC au document XBRL
second_title: API Aspose.Finance .NET
description: Apprenez à manipuler efficacement des documents XBRL à l'aide d'Aspose.Finance pour .NET. Ajoutez facilement des références de rôle ARC grâce à des conseils étape par étape.
type: docs
weight: 10
url: /fr/net/xbrl-file-creation/add-arc-role-reference-to-xbrl-document/
---
## Introduction
Dans le monde de la gestion et du reporting des données financières, le langage XBRL (eXtensible Business Reporting Language) joue un rôle crucial. Il normalise la manière dont les informations financières sont communiquées et échangées, garantissant ainsi la cohérence, l’exactitude et l’efficacité. Cependant, la manipulation de documents XBRL, notamment lorsqu’ils incorporent des rôles et des références spécifiques, nécessite une compréhension nuancée des mécanismes sous-jacents. Ce didacticiel se concentre sur l'une de ces tâches : ajouter une référence de rôle ARC à un document XBRL à l'aide d'Aspose.Finance pour .NET.
## Conditions préalables
Avant de plonger dans le didacticiel, assurez-vous d'avoir les prérequis suivants :
### Configuration de l'environnement
1.  Installez Aspose.Finance pour .NET : Téléchargez et installez la bibliothèque Aspose.Finance pour .NET à partir du[sorties](https://releases.aspose.com/finance/net/).
   
2. Environnement de développement : configurez votre environnement de développement avec Visual Studio ou tout autre IDE préféré.
## Importer des espaces de noms
Assurez-vous d'importer les espaces de noms nécessaires dans votre code C# :
```csharp
using Aspose.Finance.Xbrl;
using System;
```
## Étape 1 : Définir les répertoires source et de sortie
Avant de continuer, spécifiez les répertoires source et de sortie dans lesquels vos fichiers XBRL seront respectivement situés et enregistrés.
```csharp
// Répertoire source
string sourceDir = "Your Source Directory";
// Répertoire de sortie
string outputDir = "Your Output Directory";
```
## Étape 2 : Créer un document XBRL
 Instancier un`XbrlDocument` objet de travailler avec des données XBRL.
```csharp
XbrlDocument document = new XbrlDocument();
```
## Étape 3 : accéder à la collection XbrlInstance
Accédez à la collection d’instances XBRL dans le document.
```csharp
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
```
## Étape 4 : ajouter XbrlInstance
Ajoutez une nouvelle instance XBRL à la collection.
```csharp
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
## Étape 5 : ajouter une référence de schéma
Incluez une référence de schéma dans l'instance XBRL, en spécifiant le répertoire source, le préfixe d'espace de noms et l'URI.
```csharp
SchemaRefCollection schemaRefs = xbrlInstance.SchemaRefs;
schemaRefs.Add(sourceDir + @"schema.xsd", "example", "http://exemple.com/xbrl/taxonomy");
```
## Étape 6 : Récupérer ArcroleType
 Récupérer le`ArcroleType` basé sur un URI spécifique.
```csharp
SchemaRef schema = schemaRefs[0];
ArcroleType arcroleType = schema.GetArcroleTypeByURI("http://abc.com/arcrole/footnote-test");
```
## Étape 7 : ajouter une référence Arcrole
 Si la`ArcroleType` est trouvé, créez un`ArcroleReference` et ajoutez-le aux références arcrole de l'instance XBRL.
```csharp
if (arcroleType != null)
{
    ArcroleReference arcroleReference = new ArcroleReference(arcroleType);
    xbrlInstance.ArcroleReferences.Add(arcroleReference);
}
```
## Étape 8 : Enregistrez le document
Enregistrez le document XBRL modifié dans le répertoire de sortie spécifié.
```csharp
document.Save(outputDir + @"document8.xbrl");
```
## Conclusion
Dans ce didacticiel, nous avons expliqué comment ajouter une référence de rôle ARC à un document XBRL à l'aide d'Aspose.Finance pour .NET. En suivant ces instructions étape par étape et en tirant parti des capacités d'Aspose.Finance, vous pouvez gérer et manipuler efficacement les données XBRL pour répondre à vos besoins spécifiques.
## FAQ
### Qu’est-ce que XBRL ?
XBRL signifie eXtensible Business Reporting Language, un langage standardisé pour la communication électronique de données commerciales et financières.
### Pourquoi XBRL est-il important ?
XBRL garantit la cohérence, l'exactitude et l'efficacité de l'échange et de l'analyse des informations financières, au profit des régulateurs, des analystes et des entreprises.
### Aspose.Finance peut-il gérer des tâches XBRL complexes ?
Oui, Aspose.Finance offre des fonctionnalités robustes pour travailler avec des documents XBRL, notamment la gestion de tâches complexes telles que les références de rôles et la gestion de la taxonomie.
### Aspose.Finance est-il compatible avec d'autres bibliothèques .NET ?
Oui, Aspose.Finance s'intègre de manière transparente à d'autres bibliothèques .NET, offrant une prise en charge étendue pour la manipulation et le reporting des données financières.
### Où puis-je trouver une assistance supplémentaire pour Aspose.Finance ?
 Pour une assistance supplémentaire, visitez le[Page d'assistance Aspose.Finance](https://forum.aspose.com/c/finance/43).