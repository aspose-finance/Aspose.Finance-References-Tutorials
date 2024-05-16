---
title: Créer un fichier de demande de transaction bancaire OFX
linktitle: Créer un fichier de demande de transaction bancaire OFX
second_title: API Aspose.Finance .NET
description: Découvrez comment créer un fichier de demande de transaction bancaire OFX à l'aide d'Aspose.Finance pour .NET avec notre guide détaillé étape par étape. #Aspose #Finance
type: docs
weight: 12
url: /fr/net/ofx-file-manipulation/create-ofx-bank-transaction-request-file/
---
Créer un fichier de demande de transaction bancaire OFX peut sembler intimidant, mais avec les bons outils et conseils, cela peut être un processus simple. Dans ce didacticiel, nous vous guiderons à travers chaque étape de génération d'un fichier de demande de transaction bancaire OFX à l'aide d'Aspose.Finance pour .NET. Nous couvrirons les conditions préalables, les espaces de noms nécessaires et fournirons un guide détaillé, étape par étape, pour vous assurer que vous pouvez suivre facilement.
## Conditions préalables
Avant de plonger dans le didacticiel, vous devez mettre en place quelques éléments :
1.  Visual Studio : assurez-vous que Visual Studio est installé sur votre ordinateur. Vous pouvez le télécharger depuis le[site officiel](https://visualstudio.microsoft.com/).
2.  Aspose.Finance pour .NET : Vous avez besoin de la bibliothèque Aspose.Finance pour .NET. Vous pouvez le télécharger depuis[ici](https://releases.aspose.com/finance/net/).
3. Connaissances de base en C# : Comprendre les bases de la programmation C# vous aidera à suivre les exemples de code.
Une fois ces prérequis en place, vous êtes prêt à vous lancer !
## Importer des espaces de noms
Tout d’abord, importons les espaces de noms nécessaires. Ces espaces de noms sont cruciaux pour accéder aux classes et méthodes requises pour créer le fichier de demande de transaction bancaire OFX.
```csharp
using Aspose.Finance.Ofx;
using Aspose.Finance.Ofx.Bank;
using Aspose.Finance.Ofx.Signon;
using System;
```
## Étape 1 : configurer le répertoire de travail
Avant de commencer à créer le fichier de requête OFX, nous devons spécifier le répertoire de sortie dans lequel le fichier sera enregistré.
```csharp
string outputDir = "Your Output Directory";
```
 Remplacer`"Your Output Directory"` avec le chemin d'accès au répertoire dans lequel vous souhaitez enregistrer le fichier généré.
## Étape 2 : Créer le document de demande OFX
 Ensuite, nous devons créer une instance du`OfxRequestDocument` classe. Cette classe servira de conteneur pour notre requête OFX.
```csharp
OfxRequestDocument document = new OfxRequestDocument();
```
## Étape 3 : Configurer la demande de connexion
La demande de connexion est essentielle pour authentifier l'utilisateur et lancer la session OFX. Nous configurerons le message de demande de connexion et le remplirons avec les détails nécessaires tels que la date du client, l'ID utilisateur, le mot de passe et les informations sur l'institution financière.
```csharp
document.SignonRequestMessageSetV1 = new SignonRequestMessageSetV1();
SignonRequest signonRequest = new SignonRequest();
document.SignonRequestMessageSetV1.SignonRequest = signonRequest;
signonRequest.ClientDate = "20200611000000";
signonRequest.UserId = "aspose";
signonRequest.UserPassword = "password";
FinancialInstitution fi = new FinancialInstitution();
fi.Organization = "aspose";
fi.FinancialInstitutionId = "1";
signonRequest.FinancialInstitution = fi;
signonRequest.AppVersion = "1.0";
signonRequest.AppId = "Aspose.Finance";
signonRequest.ClientUserId = "aaaaaaa";
```
## Étape 4 : Configurer le message de demande bancaire
Maintenant que la demande de connexion est configurée, nous allons passer à la création du message de demande bancaire. Ce message contiendra les détails du compte bancaire et la demande de relevé de transaction.
```csharp
document.BankRequestMessageSetV1 = new BankRequestMessageSetV1();
StatementTransactionRequest stmtTransRequest = new StatementTransactionRequest();
document.BankRequestMessageSetV1.StatementTransactionRequests.Add(stmtTransRequest);
stmtTransRequest.TransactionUniqueId = "1111111";
stmtTransRequest.StatementRequest = new StatementRequest();
stmtTransRequest.StatementRequest.BankAccountFrom = new BankAccount();
stmtTransRequest.StatementRequest.BankAccountFrom.BankId = "sssss";
stmtTransRequest.StatementRequest.BankAccountFrom.AccountId = "sfsdfsfsdf";
stmtTransRequest.StatementRequest.BankAccountFrom.AccountType = AccountEnum.CHECKING;
```
## Étape 5 : Inclure les détails de la transaction
 Pour récupérer des transactions spécifiques, nous devons spécifier la plage de dates et s'il faut inclure les transactions dans la demande. Cela se fait en configurant le`IncTransaction` objet.
```csharp
stmtTransRequest.StatementRequest.IncTransaction = new IncTransaction();
stmtTransRequest.StatementRequest.IncTransaction.StartDate = "20200601000000";
stmtTransRequest.StatementRequest.IncTransaction.EndDate = "20200611000000";
stmtTransRequest.StatementRequest.IncTransaction.Include = true;
```
## Étape 6 : Enregistrez le document de demande OFX
Enfin, nous enregistrerons le document de requête OFX aux formats XML et SGML. Cela garantit la compatibilité avec différents systèmes pouvant utiliser l'un ou l'autre format.
```csharp
document.Save(outputDir + @"newOfxRequestBankStatement.xml", OfxVersionEnum.V2x);
document.Save(outputDir + @"newOfxRequestBankStatement.sgml", OfxVersionEnum.V1x);
```
## Étape 7 : Confirmer la réussite de l'exécution
Pour confirmer que le processus s'est exécuté avec succès, nous pouvons imprimer un message sur la console.
```csharp
Console.WriteLine("CreateOfxBankTransactionRequestFile executed successfully.");
```
## Conclusion
La création d'un fichier de demande de transaction bancaire OFX à l'aide d'Aspose.Finance pour .NET est un processus méthodique qui implique la configuration d'un document de demande, la configuration des messages d'ouverture de session et de demande bancaire, la spécification des détails de la transaction et l'enregistrement du document. En suivant ce guide étape par étape, vous pouvez générer efficacement des fichiers de requêtes OFX adaptés à vos besoins spécifiques.
## FAQ
### 1. Qu'est-ce qu'un fichier OFX ?
Un fichier OFX (Open Financial Exchange) est un format standard utilisé pour échanger des données financières entre institutions et utilisateurs. Il est largement utilisé pour les relevés bancaires, les transactions et autres activités financières.
### 2. Puis-je utiliser Aspose.Finance pour .NET avec d’autres langages de programmation ?
Aspose.Finance pour .NET est spécialement conçu pour être utilisé avec les langages .NET comme C#. Cependant, vous pouvez l'utiliser dans n'importe quel environnement pris en charge par .NET.
### 3. Existe-t-il un essai gratuit disponible pour Aspose.Finance pour .NET ?
Oui, vous pouvez télécharger un essai gratuit d'Aspose.Finance pour .NET à partir de[ici](https://releases.aspose.com/).
### 4. Comment puis-je obtenir de l'assistance pour Aspose.Finance pour .NET ?
 Vous pouvez bénéficier de l'assistance de la communauté Aspose et de l'équipe technique via leur[forum d'entraide](https://forum.aspose.com/c/finance/43).
### 5. Puis-je obtenir une licence temporaire pour Aspose.Finance pour .NET ?
 Oui, Aspose propose un[permis temporaire](https://purchase.aspose.com/temporary-license/) que vous pouvez utiliser pour évaluer le produit.