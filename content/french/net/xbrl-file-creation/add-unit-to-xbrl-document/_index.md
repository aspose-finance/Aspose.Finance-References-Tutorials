---
title: Ajouter une unité au document XBRL
linktitle: Ajouter une unité au document XBRL
second_title: API Aspose.Finance .NET
description: Apprenez à ajouter des unités aux documents XBRL sans effort avec Aspose.Finance pour .NET. Améliorez vos capacités de traitement de données financières dès aujourd’hui !
type: docs
weight: 16
url: /fr/net/xbrl-file-creation/add-unit-to-xbrl-document/
---
Bienvenue dans le monde d'Aspose.Finance pour .NET - votre passerelle vers une manipulation efficace des documents financiers au sein des applications .NET. Que vous créiez un logiciel de comptabilité, des outils d'analyse financière ou toute autre application financière, Aspose.Finance pour .NET vous offre un ensemble complet de fonctionnalités pour rationaliser votre processus de développement.
## Conditions préalables
Avant de nous lancer dans l'exploitation de la puissance d'Aspose.Finance pour .NET, assurons-nous que les conditions préalables nécessaires sont en place :
### 1. Installation de Visual Studio
Assurez-vous que Visual Studio est installé sur votre système. Sinon, vous pouvez le télécharger et l'installer depuis le site officiel de Microsoft.
### 2. Obtenez une licence
 Pour libérer tout le potentiel d'Aspose.Finance pour .NET, vous avez besoin d'une licence valide. Vous pouvez acheter une licence auprès de[ici](https://purchase.aspose.com/buy) ou optez pour une licence temporaire à des fins de test.
### 3. Téléchargez et référencez Aspose.Finance pour .NET
 Téléchargez la bibliothèque Aspose.Finance pour .NET à partir du[page des versions](https://releases.aspose.com/finance/net/) et référencez-le dans votre projet .NET.
### 4. Accéder à la documentation et au support
 Se référer au[Documentation](https://reference.aspose.com/finance/net/)pour des informations détaillées sur l’utilisation d’Aspose.Finance pour .NET. De plus, vous pouvez demander de l'aide à la communauté Aspose.Finance sur le[forum d'entraide](https://forum.aspose.com/c/finance/43).
## Importation d'espaces de noms
Maintenant, importons les espaces de noms nécessaires dans votre projet .NET :
## Étape 1 : Ajouter un espace de noms Aspose.Finance
```csharp
using Aspose.Finance.Xbrl;
using System;
```
Cet espace de noms contient des classes et des méthodes essentielles pour travailler avec des documents et des données XBRL.
Décomposons l'exemple fourni en plusieurs étapes pour comprendre comment ajouter une unité à un document XBRL à l'aide d'Aspose.Finance pour .NET.
## Étape 1 : Définir le répertoire de sortie
```csharp
// Répertoire de sortie
string outputDir = "Your Output Directory";
```
 Remplacer`"Your Output Directory"` avec le chemin réel vers le répertoire de sortie souhaité.
## Étape 2 : Créer un document XBRL
```csharp
XbrlDocument document = new XbrlDocument();
```
Cela initialise une nouvelle instance du document XBRL.
## Étape 3 : accéder aux instances XBRL
```csharp
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
Cela récupère la collection d'instances XBRL du document et y ajoute une nouvelle instance.
## Étape 4 : Ajouter une unité
```csharp
Unit unit = new Unit(UnitType.Measure);
unit.MeasureQualifiedNames.Add(new QualifiedName("USD", "iso4217", "http://www.xbrl.org/2003/iso4217"));
xbrlInstance.Units.Add(unit);
```
Cela crée une nouvelle unité de mesure (dans ce cas, USD) et l'ajoute à l'instance XBRL. Vous pouvez ajuster le code de devise et l'URI de l'espace de noms selon vos besoins.
## Étape 5 : Enregistrez le document
```csharp
document.Save(outputDir + @"document4.xbrl");
```
Cela enregistre le document XBRL modifié dans le répertoire de sortie spécifié.
## Conclusion
En conclusion, Aspose.Finance pour .NET permet aux développeurs de manipuler sans effort des documents et des données financières au sein de leurs applications .NET. En suivant les étapes décrites dans ce didacticiel, vous pouvez intégrer de manière transparente Aspose.Finance for .NET dans vos projets et améliorer leurs capacités de traitement financier.
## FAQ
### 1. Puis-je utiliser Aspose.Finance pour .NET sans licence ?
Non, une licence valide est requise pour débloquer toutes les fonctionnalités d'Aspose.Finance pour .NET. Toutefois, des licences temporaires sont disponibles à des fins de test.
### 2. Aspose.Finance pour .NET est-il adapté à la création de logiciels de comptabilité ?
Oui, Aspose.Finance pour .NET fournit des fonctionnalités robustes adaptées à la création de logiciels de comptabilité et d'applications financières associées.
### 3. Où puis-je trouver de l'assistance pour Aspose.Finance pour .NET ?
Vous pouvez demander de l'aide à la communauté Aspose.Finance sur le forum d'assistance.
### 4. Puis-je personnaliser l'unité de mesure dans un document XBRL ?
Oui, vous pouvez créer et ajouter des unités de mesure personnalisées aux documents XBRL à l'aide d'Aspose.Finance pour .NET.
### 5. Aspose.Finance pour .NET prend-il en charge plusieurs devises ?
Oui, Aspose.Finance pour .NET prend en charge plusieurs devises, permettant un traitement polyvalent des données financières.