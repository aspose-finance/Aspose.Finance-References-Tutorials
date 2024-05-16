---
title: Ajouter une référence de schéma au document XBRL
linktitle: Ajouter une référence de schéma au document XBRL
second_title: API Aspose.Finance .NET
description: Découvrez comment ajouter des références de schéma aux documents XBRL à l'aide d'Aspose.Finance pour .NET. Rationalisez le traitement de vos données financières dès aujourd’hui !
type: docs
weight: 15
url: /fr/net/xbrl-file-creation/add-schema-reference-to-xbrl-document/
---
## Présentation d'Aspose.Finance pour .NET
Aspose.Finance pour .NET est une bibliothèque puissante qui fournit des fonctionnalités complètes pour le traitement et la manipulation de documents et de données financiers au sein d'applications .NET. Que vous créiez un logiciel de comptabilité, des outils d'analyse financière ou toute autre application financière, Aspose.Finance pour .NET offre un large éventail de fonctionnalités pour rationaliser votre processus de développement.
## Conditions préalables
Avant de vous lancer dans l'utilisation d'Aspose.Finance pour .NET, assurez-vous d'avoir configuré les conditions préalables suivantes :
### 1. Installez Visual Studio
Assurez-vous que Visual Studio est installé sur votre système. Vous pouvez le télécharger et l'installer à partir du site officiel de Microsoft.
### 2. Obtenez une licence Aspose.Finance
Pour utiliser toutes les capacités d'Aspose.Finance pour .NET, vous devez acquérir une licence valide. Vous pouvez acheter une licence auprès de[ici](https://purchase.aspose.com/buy) ou optez pour une licence temporaire à des fins de test.
### 3. Téléchargez et référencez Aspose.Finance pour .NET
 Téléchargez la bibliothèque Aspose.Finance pour .NET à partir du[page des versions](https://releases.aspose.com/finance/net/) et référencez-le dans votre projet .NET.
### 4. Accéder à la documentation et au support
 Se référer au[Documentation API](https://reference.aspose.com/finance/net/) pour des informations détaillées sur l’utilisation d’Aspose.Finance pour .NET. De plus, vous pouvez demander de l'aide à la communauté Aspose.Finance sur le[forum d'entraide](https://forum.aspose.com/c/finance/43).
## Importation d'espaces de noms
Commençons par importer les espaces de noms nécessaires dans votre projet .NET :
## Étape 1 : Ajouter un espace de noms Aspose.Finance
```csharp
using Aspose.Finance.Xbrl;
using System;
```
Cet espace de noms contient des classes et des méthodes permettant d'utiliser des documents et des données XBRL.
Maintenant, décomposons l'exemple fourni en plusieurs étapes pour comprendre comment ajouter une référence de schéma à un document XBRL à l'aide d'Aspose.Finance pour .NET.
## Étape 1 : Définir les répertoires source et de sortie
```csharp
// Répertoire source
string sourceDir = "Your Source Directory";
// Répertoire de sortie
string outputDir = "Your Output Directory";
```
 Remplacer`"Your Source Directory"` et`"Your Output Directory"`avec les chemins réels vers vos répertoires source et de sortie respectivement.
## Étape 2 : Créer un document XBRL
```csharp
XbrlDocument document = new XbrlDocument();
```
Cela crée une nouvelle instance du document XBRL.
## Étape 3 : accéder aux instances XBRL
```csharp
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
Cela récupère la collection d'instances XBRL du document et y ajoute une nouvelle instance.
## Étape 4 : ajouter une référence de schéma
```csharp
SchemaRefCollection schemaRefs = xbrlInstance.SchemaRefs;
schemaRefs.Add(sourceDir + @"schema.xsd", "example", "http://exemple.com/xbrl/taxonomy");
```
 Cela ajoute une référence de schéma à l'instance XBRL. Remplacer`"schema.xsd"` avec le nom réel de votre fichier de schéma,`"example"` avec un préfixe approprié, et`"http://example.com/xbrl/taxonomy"` avec l’URI de l’espace de noms cible.
## Étape 5 : Enregistrez le document
```csharp
document.Save(outputDir + @"document2.xbrl");
```
Cela enregistre le document XBRL modifié dans le répertoire de sortie spécifié.
## Conclusion
En conclusion, Aspose.Finance for .NET offre une solution robuste pour gérer les documents et données financiers dans les applications .NET. En suivant les étapes décrites dans ce didacticiel, vous pouvez facilement intégrer Aspose.Finance dans vos projets et manipuler efficacement les documents XBRL.
## FAQ
 (Questions fréquemment posées)
### 1. Puis-je utiliser Aspose.Finance pour .NET sans licence ?
Non, vous avez besoin d'une licence valide pour utiliser toutes les fonctionnalités d'Aspose.Finance pour .NET. Cependant, vous pouvez obtenir une licence temporaire à des fins de test.
### 2. Aspose.Finance est-il adapté à la création de logiciels de comptabilité ?
Oui, Aspose.Finance fournit des fonctionnalités complètes pour le traitement des données financières, ce qui le rend idéal pour créer des logiciels de comptabilité et des applications associées.
### 3. Où puis-je trouver de l'aide pour Aspose.Finance ?
Vous pouvez demander de l'aide à la communauté Aspose.Finance sur le forum d'assistance officiel.
### 4. Puis-je personnaliser le préfixe de référence du schéma ?
Oui, vous pouvez choisir un préfixe approprié lors de l'ajout d'une référence de schéma à un document XBRL à l'aide d'Aspose.Finance pour .NET.
### 5. Aspose.Finance prend-il en charge d'autres formats financiers que XBRL ?
Oui, Aspose.Finance prend en charge divers formats et normes financières, permettant une intégration transparente dans diverses applications financières.