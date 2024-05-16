---
title: Ajouter du contexte au document XBRL
linktitle: Ajouter du contexte au document XBRL
second_title: API Aspose.Finance .NET
description: Découvrez comment ajouter du contexte aux documents XBRL dans .NET à l'aide d'Aspose.Finance pour des rapports financiers rationalisés. #Aspose #Finance #XBRL
type: docs
weight: 11
url: /fr/net/xbrl-file-creation/add-context-to-xbrl-document/
---
## Introduction
Dans le domaine de l'information financière, XBRL (eXtensible Business Reporting Language) joue un rôle central dans la normalisation de l'échange d'informations commerciales. L'ajout de contexte aux documents XBRL est crucial pour garantir l'intégrité et la pertinence des données qu'ils contiennent. Avec Aspose.Finance pour .NET, ce processus devient rationalisé et efficace, permettant aux développeurs d'intégrer de manière transparente le contexte dans leurs documents XBRL.
## Conditions préalables
Avant de plonger dans le didacticiel, assurez-vous de disposer des prérequis suivants :
1. Bibliothèque Aspose.Finance pour .NET : téléchargez et installez la bibliothèque Aspose.Finance pour .NET à partir du[sorties](https://releases.aspose.com/finance/net/).
2. Environnement de développement .NET : assurez-vous que vous disposez d'un environnement de développement .NET fonctionnel configuré sur votre ordinateur.
3. Compréhension de base de C# : La connaissance du langage de programmation C# sera utile pour suivre les exemples.
## Importer des espaces de noms
Dans votre projet C#, importez les espaces de noms nécessaires pour accéder aux fonctionnalités fournies par Aspose.Finance pour .NET :
```csharp
using Aspose.Finance.Xbrl;
using System;
```
## Étape 1 : définir le répertoire de sortie
Avant d'ajouter du contexte au document XBRL, spécifiez le répertoire de sortie dans lequel le document modifié sera enregistré :
```csharp
string outputDir = "Your Output Directory";
```
 Remplacer`"Your Output Directory"` avec le chemin souhaité sur votre système.
## Étape 2 : Créer un document XBRL
 Instancier un`XbrlDocument` s'opposer à travailler avec des documents XBRL :
```csharp
XbrlDocument document = new XbrlDocument();
```
Cet objet représente le document XBRL qui sera manipulé.
## Étape 3 : Ajouter une instance XBRL
Ajoutez une instance XBRL au document. Chaque instance contient les données pour une période de reporting spécifique :
```csharp
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
Cette étape initialise une instance XBRL dans le document.
## Étape 4 : Définir la période et l'entité du contexte
Créez une période de contexte et une entité pour l'instance XBRL :
```csharp
ContextPeriod contextPeriod = new ContextPeriod(DateTime.Parse("2020-01-01"), DateTime.Parse("2020-02-10"));
ContextEntity contextEntity = new ContextEntity("exampleIdentifierScheme", "exampleIdentifier");
```
Spécifiez les détails de la période et de l'entité en fonction de vos exigences de reporting.
## Étape 5 : Créer un contexte
Construisez un contexte en utilisant la période et l'entité définies à l'étape précédente :
```csharp
Context context = new Context(contextPeriod, contextEntity);
```
Ce contexte encapsule les informations temporelles et liées à l'entité.
## Étape 6 : ajouter du contexte à l'instance XBRL
Associez le contexte créé à l'étape précédente à l'instance XBRL :
```csharp
xbrlInstance.Contexts.Add(context);
```
Cette étape relie le contexte à l'instance XBRL, fournissant des informations contextuelles pertinentes aux données.
## Étape 7 : Enregistrez le document
Enregistrez le document XBRL modifié dans le répertoire de sortie spécifié :
```csharp
document.Save(outputDir + @"document3.xbrl");
```
Ceci finalise le processus, en enregistrant le document XBRL avec le contexte ajouté.
## Conclusion
En suivant ces étapes, vous pouvez ajouter efficacement du contexte aux documents XBRL à l'aide d'Aspose.Finance pour .NET. Cela améliore la clarté et la convivialité des données financières, facilitant ainsi une analyse et un reporting précis.
## FAQ
### Aspose.Finance for .NET peut-il gérer des documents XBRL volumineux ?
Aspose.Finance pour .NET est optimisé pour gérer des documents XBRL de différentes tailles, y compris de grands ensembles de données.
### Existe-t-il une version d'essai disponible pour Aspose.Finance pour .NET ?
Oui, vous pouvez télécharger une version d'essai gratuite sur le site officiel d'Aspose.
### Aspose.Finance pour .NET prend-il en charge d'autres normes d'information financière que XBRL ?
Aspose.Finance se concentre principalement sur les fonctionnalités liées à XBRL mais prend également en charge d'autres formats financiers.
### Puis-je personnaliser les informations contextuelles en fonction de mes besoins spécifiques ?
Absolument, Aspose.Finance pour .NET offre une flexibilité pour personnaliser les informations contextuelles en fonction de vos besoins.
### Où puis-je trouver une assistance ou des ressources supplémentaires pour Aspose.Finance pour .NET ?
Vous pouvez visiter le forum Aspose.Finance pour obtenir l'aide de la communauté ou explorer la documentation pour obtenir des conseils complets.