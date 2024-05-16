---
title: Créer un fichier de réponse aux transactions bancaires OFX
linktitle: Créer un fichier de réponse aux transactions bancaires OFX
second_title: API Aspose.Finance .NET
description: Apprenez à créer sans effort des fichiers de réponses aux transactions bancaires OFX à l'aide d'Aspose.Finance pour .NET. Rationalisez l’échange de données financières dès aujourd’hui !
type: docs
weight: 13
url: /fr/net/ofx-file-manipulation/create-ofx-bank-transaction-response-file/
---
## Introduction
Dans le domaine du traitement des données financières, générer des fichiers de réponses aux transactions bancaires OFX (Open Financial Exchange) est une tâche cruciale. Ces fichiers encapsulent les informations transactionnelles dans un format standardisé, facilitant un échange transparent entre les institutions financières et les systèmes logiciels. Aspose.Finance pour .NET offre une solution robuste pour créer sans effort des fichiers de réponses aux transactions bancaires OFX dans le framework .NET.
## Conditions préalables
Avant de vous lancer dans la création de fichiers de réponses aux transactions bancaires OFX à l'aide d'Aspose.Finance pour .NET, assurez-vous que les conditions préalables suivantes sont remplies :
### 1. Obtenez Aspose.Finance pour .NET
 Tout d’abord, téléchargez et installez Aspose.Finance pour .NET à partir du site officiel[lien de téléchargement](https://releases.aspose.com/finance/net/).
### 2. Configurer l'environnement de développement
Assurez-vous qu'un environnement de développement approprié est configuré, y compris une version compatible de Visual Studio et du framework .NET.
### 3. Familiarité de base avec C#
Une compréhension fondamentale du langage de programmation C# est essentielle pour comprendre les concepts abordés dans ce didacticiel.
## Importer des espaces de noms
Pour commencer à créer des fichiers de réponses aux transactions bancaires OFX avec Aspose.Finance pour .NET, importez les espaces de noms nécessaires :
## 1. Importer les espaces de noms Aspose.Finance
```csharp
using Aspose.Finance.Ofx;
using Aspose.Finance.Ofx.Bank;
using Aspose.Finance.Ofx.Signon;
using System;
```
Maintenant, décomposons l'exemple fourni en plusieurs étapes pour vous guider tout au long du processus de création de fichiers de réponses aux transactions bancaires OFX à l'aide d'Aspose.Finance pour .NET.
## Étape 1 : Définir le répertoire de sortie
```csharp
string outputDir = "Your Output Directory";
```
Précisez le chemin du répertoire dans lequel vous souhaitez enregistrer les fichiers de réponses aux transactions bancaires OFX générés.
## Étape 2 : initialiser le document de réponse OFX
```csharp
OfxResponseDocument document = new OfxResponseDocument();
```
 Créez une nouvelle instance du`OfxResponseDocument` classe pour commencer à construire le document de réponse OFX.
## Étape 3 : Définir la réponse de connexion
```csharp
document.SignonResponseMessageSetV1 = new SignonResponseMessageSetV1();
```
 Instancier le`SignonResponseMessageSetV1` classe pour gérer les réponses de connexion dans le document OFX.
## Étape 4 : Définir les détails de la réponse de connexion
```csharp
SignonResponse signonResponse = new SignonResponse();
```
 Créer un nouveau`SignonResponse` objet pour encapsuler les détails de la réponse de connexion.
## Étape 5 : Définir l'état de la réponse de connexion
```csharp
signonResponse.Status = new Status();
signonResponse.Status.Code = "0";
signonResponse.Status.Severity = SeverityEnum.INFO;
signonResponse.Status.Message = "SUCCESS";
```
Configurez l'état de la réponse de connexion, en spécifiant le code, la gravité et le message.
## Étape 6 : Définir les détails de l'institution financière
```csharp
FinancialInstitution fi = new FinancialInstitution();
fi.Organization = "aspose";
fi.FinancialInstitutionId = "1";
```
Fournissez des informations sur l’institution financière impliquée dans la transaction.
## Étape 7 : Définir le cookie de session
```csharp
signonResponse.SessionCookie = "11111111111111111";
```
Attribuez un cookie de session à des fins d'authentification.
## Étape 8 : Ajouter un ensemble de messages de réponse bancaire
```csharp
document.BankResponseMessageSetV1 = new BankResponseMessageSetV1();
```
 Instancier le`BankResponseMessageSetV1` classe pour gérer les messages de réponse bancaire.
## Étape 9 : Ajouter une réponse à la transaction d'instruction
```csharp
StatementTransactionResponse stmtTransResponse = new StatementTransactionResponse();
document.BankResponseMessageSetV1.StatementTransactionResponses.Add(stmtTransResponse);
```
Créez un objet de réponse de transaction de relevé et ajoutez-le à l'ensemble de messages de réponse bancaire.
## Étape 10 : Définir les détails de la transaction
```csharp
stmtTransResponse.TransactionUniqueId = "829631324";
stmtTransResponse.Status = new Status();
stmtTransResponse.Status.Code = "0";
stmtTransResponse.Status.Severity = SeverityEnum.INFO;
```
Configurez les détails spécifiques à la transaction tels que l'identifiant unique et le statut.
## Étape 11 : Ajouter des informations sur le compte bancaire
```csharp
stmtTransResponse.StatementResponse.BankAccountFrom = new BankAccount();
stmtTransResponse.StatementResponse.BankAccountFrom.BankId = "1111111";
stmtTransResponse.StatementResponse.BankAccountFrom.AccountId = "1111111111111";
stmtTransResponse.StatementResponse.BankAccountFrom.AccountType = AccountEnum.CHECKING;
```
Fournissez des détails sur le compte bancaire impliqué dans la transaction.
## Étape 12 : Ajouter une liste de transactions bancaires
```csharp
stmtTransResponse.StatementResponse.BankTransactionList = new BankTransactionList();
stmtTransResponse.StatementResponse.BankTransactionList.StartDate = "20200601000000";
stmtTransResponse.StatementResponse.BankTransactionList.EndDate = "20200611000000";
```
Créez une liste de transactions bancaires et précisez les dates de début et de fin des transactions.
## Étape 13 : Ajouter des transactions de relevé
```csharp
StatementTransaction transaction1 = new StatementTransaction();
//Détails de la transaction pour la transaction1
StatementTransaction transaction2 = new StatementTransaction();
// Détails de la transaction pour la transaction2
stmtTransResponse.StatementResponse.BankTransactionList.StatementTransactions.Add(transaction1);
stmtTransResponse.StatementResponse.BankTransactionList.StatementTransactions.Add(transaction2);
```
Instanciez les transactions de relevé, remplissez-les avec des détails et ajoutez-les à la liste des transactions bancaires.
## Étape 14 : Définir le grand livre et les soldes disponibles
```csharp
stmtTransResponse.StatementResponse.LedgerBalance = new LedgerBalance();
stmtTransResponse.StatementResponse.LedgerBalance.BalanceAmount = "+2222.42";
stmtTransResponse.StatementResponse.LedgerBalance.DateAsOf = "20200611000000";
stmtTransResponse.StatementResponse.AvailableBalance = new AvailableBalance();
stmtTransResponse.StatementResponse.AvailableBalance.BalanceAmount = "+222222.42";
stmtTransResponse.StatementResponse.AvailableBalance.DateAsOf = "20200611000000";
```
Spécifiez le solde du grand livre et le solde disponible associés au compte bancaire.
## Étape 15 : Enregistrer les fichiers de réponse OFX
```csharp
document.Save(outputDir + @"newOfxResponseBankStatement.xml", OfxVersionEnum.V2x);
document.Save(outputDir + @"newOfxResponseBankStatement.sgml", OfxVersionEnum.V1x);
```
Enregistrez les fichiers de réponses OFX générés aux formats XML et SGML respectivement.
## Conclusion
La création de fichiers de réponses aux transactions bancaires OFX à l'aide d'Aspose.Finance pour .NET offre aux développeurs une approche rationalisée pour gérer l'échange de données financières. En suivant le guide étape par étape décrit dans cet article, vous pouvez générer efficacement des fichiers OFX adaptés aux besoins de votre application.
## FAQ
### 1. Puis-je intégrer Aspose.Finance pour .NET à d’autres logiciels financiers ?
Oui, Aspose.Finance pour .NET offre des capacités d'intégration transparentes avec diverses solutions logicielles financières, garantissant ainsi la compatibilité et l'interopérabilité.
### 2. Aspose.Finance pour .NET est-il adapté à une utilisation personnelle et professionnelle ?
Absolument! Que vous soyez un développeur individuel ou faisant partie d'une grande entreprise, Aspose.Finance pour .NET répond aux divers besoins des utilisateurs grâce à ses fonctionnalités flexibles et ses options de licence.
### 3. Existe-t-il des limites quant au nombre de transactions pouvant être traitées à l'aide d'Aspose.Finance pour .NET ?
Non, Aspose.Finance pour .NET est conçu pour gérer efficacement de gros volumes de transactions sans imposer de limitations arbitraires. Que vous traitiez quelques transactions ou gériez de nombreuses données financières, la bibliothèque garantit des performances et une évolutivité optimales.
### 4. Puis-je personnaliser le format et la structure des fichiers OFX générés par Aspose.Finance pour .NET ?
Certainement! Aspose.Finance pour .NET offre des options de personnalisation étendues, vous permettant d'adapter le format, la structure et le contenu des fichiers OFX en fonction de vos besoins spécifiques. Vous pouvez facilement ajuster divers paramètres pour répondre aux normes et préférences de votre application ou organisation.
### 5. Un support technique est-il disponible pour Aspose.Finance pour .NET ?
 Oui, un support technique complet est disponible pour Aspose.Finance pour les utilisateurs .NET. Vous pouvez accéder au[forum](https://forum.aspose.com/c/finance/43) pour demander de l'aide, signaler des problèmes ou interagir avec la communauté dynamique de développeurs et d'experts.