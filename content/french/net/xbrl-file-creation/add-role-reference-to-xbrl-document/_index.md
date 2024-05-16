---
title: Ajouter une référence de rôle au document XBRL
linktitle: Ajouter une référence de rôle au document XBRL
second_title: API Aspose.Finance .NET
description: Découvrez comment ajouter des références de rôle aux documents XBRL à l'aide d'Aspose.Finance pour .NET. Simplifiez les rapports financiers dans vos applications .NET avec ce didacticiel.
type: docs
weight: 14
url: /fr/net/xbrl-file-creation/add-role-reference-to-xbrl-document/
---
XBRL (eXtensible Business Reporting Language) est devenu un standard pour l'échange d'informations commerciales, notamment dans le domaine du reporting financier. Aspose.Finance pour .NET simplifie l'utilisation de documents XBRL dans les applications .NET. Ce didacticiel vous guidera tout au long du processus d'ajout d'une référence de rôle à un document XBRL à l'aide d'Aspose.Finance pour .NET.
## Conditions préalables
Avant de commencer, assurez-vous de disposer des prérequis suivants :
### 1. Installez Aspose.Finance pour .NET
Assurez-vous que Aspose.Finance pour .NET est installé dans votre environnement de développement. Si vous ne l'avez pas déjà fait, téléchargez-le depuis le[sorties](https://releases.aspose.com/finance/net/) et suivez les instructions d'installation.
### 2. Configurez votre environnement de développement
Assurez-vous de disposer d'un environnement de développement fonctionnel pour le développement .NET. Cela inclut un IDE compatible tel que Visual Studio et le framework .NET installé sur votre système.
## Importer des espaces de noms
Commencez par importer les espaces de noms nécessaires dans votre application .NET pour accéder aux fonctionnalités fournies par Aspose.Finance pour .NET.
```csharp
using Aspose.Finance.Xbrl;
using System;
using Aspose
.Finance.Xbrl.Roles;
```
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
## Étape 4 : Récupérer le type de rôle et ajouter une référence de rôle
```csharp
SchemaRef schema = schemaRefs[0];
RoleType roleType = schema.GetRoleTypeByURI("http://abc.com/role/link1");
if (roleType != null)
{
    RoleReference roleReference = new RoleReference(roleType);
    xbrlInstance.RoleReferences.Add(roleReference);
}
```
Récupérez le type de rôle à l’aide de son URI et ajoutez une référence de rôle à l’instance XBRL.
## Étape 5 : Enregistrer le document
```csharp
document.Save(outputDir + @"document7.xbrl");
```
Enregistrez le document XBRL dans le répertoire de sortie.
## Conclusion
L'ajout de références de rôle aux documents XBRL est crucial pour définir les rôles des différents éléments du document. Aspose.Finance for .NET fournit un moyen simple d'accomplir cette tâche, permettant aux développeurs de travailler efficacement avec des documents XBRL dans leurs applications .NET.
## FAQ
### Puis-je utiliser Aspose.Finance pour .NET avec n’importe quelle application .NET ?
Oui, Aspose.Finance pour .NET est compatible avec n'importe quelle application .NET, y compris les applications ASP.NET, WinForms et Console.
### L’utilisation d’Aspose.Finance pour .NET est-elle gratuite ?
 Aspose.Finance pour .NET est une bibliothèque commerciale. Vous pouvez télécharger une version d'essai gratuite pour évaluer ses fonctionnalités, et les licences peuvent être achetées auprès de[ici](https://purchase.aspose.com/buy).
### Aspose.Finance pour .NET prend-il en charge d'autres formats de rapports financiers que XBRL ?
Aspose.Finance for .NET se concentre principalement sur les fonctionnalités liées à XBRL. Cependant, Aspose propose d'autres bibliothèques pour travailler avec différents formats financiers.
### Comment puis-je obtenir de l'aide pour Aspose.Finance pour .NET ?
 Vous pouvez obtenir une assistance pour Aspose.Finance pour .NET via le[forum](https://forum.aspose.com/c/finance/43)où vous pouvez poser des questions et interagir avec d'autres utilisateurs et le personnel d'assistance.
### Puis-je obtenir une licence temporaire pour Aspose.Finance pour .NET ?
 Oui, des licences temporaires pour Aspose.Finance pour .NET sont disponibles à des fins de test. Vous pouvez en obtenir un[ici](https://purchase.aspose.com/temporary-license/).