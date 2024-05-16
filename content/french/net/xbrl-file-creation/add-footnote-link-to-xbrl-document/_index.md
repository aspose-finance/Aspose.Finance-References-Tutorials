---
title: Ajouter un lien de note de bas de page au document XBRL
linktitle: Ajouter un lien de note de bas de page au document XBRL
second_title: API Aspose.Finance .NET
description: Découvrez comment ajouter des liens de note de bas de page aux documents XBRL à l'aide d'Aspose.Finance pour .NET. Améliorez facilement les rapports financiers avec un contexte supplémentaire.
type: docs
weight: 12
url: /fr/net/xbrl-file-creation/add-footnote-link-to-xbrl-document/
---
L'ajout d'un lien de note de bas de page à un document XBRL est crucial pour fournir un contexte ou des explications supplémentaires pour des points de données spécifiques. Dans ce didacticiel, nous allons parcourir le processus étape par étape en utilisant Aspose.Finance pour .NET.
## Conditions préalables
Avant de commencer, assurez-vous que les conditions préalables suivantes sont remplies :
1.  Aspose.Finance pour .NET : assurez-vous d'avoir installé Aspose.Finance pour .NET sur votre système. Vous pouvez le télécharger depuis[ici](https://releases.aspose.com/finance/net/).
  
2. Environnement de développement : disposez d'un environnement de développement configuré avec un .NET Framework ou .NET Core.
## Importer des espaces de noms :
```csharp
using Aspose.Finance.Xbrl;
using System;
```
## Étape 1 : Définir les répertoires source et de sortie
Tout d'abord, spécifiez les répertoires des fichiers source et de sortie :
```csharp
// Répertoire source
string sourceDir = "Your Source Directory";
// Répertoire de sortie
string outputDir = "Your Output Directory";
```
## Étape 2 : Créer un document et une instance XBRL
Initialisez un document et une instance XBRL :
```csharp
XbrlDocument document = new XbrlDocument();
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
## Étape 3 : ajouter des références de schéma
Ajoutez des références de schéma à l'instance XBRL :
```csharp
SchemaRefCollection schemaRefs = xbrlInstance.SchemaRefs;
schemaRefs.Add(sourceDir + @"schema.xsd", "example", "http://exemple.com/xbrl/taxonomy");
SchemaRef schema = schemaRefs[0];
```
## Étape 4 : Définir le contexte
Définissez le contexte de l'instance XBRL :
```csharp
ContextPeriod contextPeriod = new ContextPeriod(DateTime.Parse("2020-01-01"), DateTime.Parse("2020-02-10"));
ContextEntity contextEntity = new ContextEntity("exampleIdentifierScheme", "exampleIdentifier");
Context context = new Context(contextPeriod, contextEntity);
context.Id = "cd1";
xbrlInstance.Contexts.Add(context);
```
## Étape 5 : Ajouter un lien de note de bas de page
Créez et ajoutez un lien de note de bas de page vers l'instance XBRL :
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
## Étape 6 : Enregistrez le document
Enregistrez le document XBRL modifié :
```csharp
document.Save(outputDir + @"document6.xbrl");
```

## Conclusion
L'ajout d'un lien de note de bas de page à un document XBRL est un processus simple avec Aspose.Finance pour .NET. En suivant les étapes décrites dans ce didacticiel, vous pouvez intégrer en toute transparence un contexte ou des explications supplémentaires dans vos rapports financiers.
## FAQ
### Puis-je ajouter plusieurs liens de notes de bas de page à un seul document XBRL ?
Oui, vous pouvez ajouter plusieurs liens de note de bas de page en répétant les étapes décrites dans ce didacticiel pour chaque lien supplémentaire.
### Aspose.Finance pour .NET est-il compatible avec .NET Framework et .NET Core ?
Oui, Aspose.Finance pour .NET prend en charge les environnements .NET Framework et .NET Core.
### Comment puis-je obtenir une licence temporaire pour Aspose.Finance pour .NET ?
 Vous pouvez obtenir une licence temporaire auprès de[ici](https://purchase.aspose.com/temporary-license/).
### Aspose.Finance for .NET prend-il en charge la validation XBRL ?
Oui, Aspose.Finance for .NET offre une prise en charge complète de la validation XBRL afin de garantir la conformité aux normes de l'industrie.
### Où puis-je trouver des ressources supplémentaires et une assistance pour Aspose.Finance pour .NET ?
 Vous pouvez visiter le[Forum Aspose.Finance pour .NET](https://forum.aspose.com/c/finance/43) pour obtenir de l'aide et accéder à la documentation[ici](https://reference.aspose.com/finance/net/).