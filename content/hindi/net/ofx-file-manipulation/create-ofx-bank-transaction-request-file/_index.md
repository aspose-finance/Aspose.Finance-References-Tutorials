---
title: OFX बैंक लेनदेन अनुरोध फ़ाइल बनाएँ
linktitle: OFX बैंक लेनदेन अनुरोध फ़ाइल बनाएँ
second_title: Aspose.Finance .NET एपीआई
description: हमारे विस्तृत, चरण-दर-चरण गाइड के साथ .NET के लिए Aspose.Finance का उपयोग करके OFX बैंक लेनदेन अनुरोध फ़ाइल बनाने का तरीका जानें। #Aspose #Finance
type: docs
weight: 12
url: /hi/net/ofx-file-manipulation/create-ofx-bank-transaction-request-file/
---
OFX बैंक ट्रांजेक्शन रिक्वेस्ट फ़ाइल बनाना मुश्किल लग सकता है, लेकिन सही टूल और मार्गदर्शन के साथ, यह एक सीधी प्रक्रिया हो सकती है। इस ट्यूटोरियल में, हम आपको .NET के लिए Aspose.Finance का उपयोग करके OFX बैंक ट्रांजेक्शन रिक्वेस्ट फ़ाइल बनाने के प्रत्येक चरण के बारे में बताएँगे। हम आवश्यक शर्तें, आवश्यक नामस्थानों को कवर करेंगे, और यह सुनिश्चित करने के लिए एक विस्तृत, चरण-दर-चरण मार्गदर्शिका प्रदान करेंगे कि आप आसानी से अनुसरण कर सकें।
## आवश्यक शर्तें
इससे पहले कि हम ट्यूटोरियल में आगे बढ़ें, कुछ चीजें हैं जिन्हें आपको तैयार रखना होगा:
1.  विज़ुअल स्टूडियो: सुनिश्चित करें कि आपके कंप्यूटर पर विज़ुअल स्टूडियो स्थापित है। आप इसे यहाँ से डाउनलोड कर सकते हैं[आधिकारिक वेबसाइट](https://visualstudio.microsoft.com/).
2.  Aspose.Finance for .NET: आपको Aspose.Finance for .NET लाइब्रेरी की आवश्यकता है। आप इसे यहाँ से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/finance/net/).
3. बुनियादी C# ज्ञान: C# प्रोग्रामिंग की मूल बातें समझने से आपको कोड उदाहरणों का अनुसरण करने में मदद मिलेगी।
एक बार जब आपके पास ये पूर्वापेक्षाएँ पूरी हो जाएँ, तो आप शुरू करने के लिए तैयार हैं!
## नामस्थान आयात करें
सबसे पहले, आइए आवश्यक नेमस्पेस को आयात करें। OFX बैंक ट्रांजेक्शन रिक्वेस्ट फ़ाइल बनाने के लिए आवश्यक क्लास और विधियों तक पहुँचने के लिए ये नेमस्पेस महत्वपूर्ण हैं।
```csharp
using Aspose.Finance.Ofx;
using Aspose.Finance.Ofx.Bank;
using Aspose.Finance.Ofx.Signon;
using System;
```
## चरण 1: कार्यशील निर्देशिका सेट करें
OFX अनुरोध फ़ाइल बनाना शुरू करने से पहले, हमें आउटपुट निर्देशिका निर्दिष्ट करने की आवश्यकता है जहां फ़ाइल सहेजी जाएगी।
```csharp
string outputDir = "Your Output Directory";
```
 प्रतिस्थापित करें`"Your Output Directory"` उस निर्देशिका का पथ जहाँ आप उत्पन्न फ़ाइल को सहेजना चाहते हैं।
## चरण 2: OFX अनुरोध दस्तावेज़ बनाएँ
 इसके बाद, हमें इसका एक उदाहरण बनाना होगा`OfxRequestDocument` क्लास। यह क्लास हमारे OFX अनुरोध के लिए कंटेनर के रूप में काम करेगा।
```csharp
OfxRequestDocument document = new OfxRequestDocument();
```
## चरण 3: साइनऑन अनुरोध सेट करें
साइनऑन अनुरोध उपयोगकर्ता को प्रमाणित करने और OFX सत्र आरंभ करने के लिए आवश्यक है। हम साइनऑन अनुरोध संदेश सेट अप करेंगे और इसे क्लाइंट दिनांक, उपयोगकर्ता आईडी, पासवर्ड और वित्तीय संस्थान की जानकारी जैसे आवश्यक विवरणों से भर देंगे।
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
## चरण 4: बैंक अनुरोध संदेश सेट करें
अब जब साइनऑन अनुरोध सेट हो गया है, तो हम बैंक अनुरोध संदेश बनाने के लिए आगे बढ़ेंगे। इस संदेश में बैंक खाते और लेनदेन विवरण अनुरोध का विवरण होगा।
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
## चरण 5: लेनदेन विवरण शामिल करें
 विशिष्ट लेनदेन प्राप्त करने के लिए, हमें दिनांक सीमा निर्दिष्ट करने की आवश्यकता है और यह भी कि अनुरोध में लेनदेन शामिल करना है या नहीं। यह सेट अप करके किया जाता है`IncTransaction` वस्तु।
```csharp
stmtTransRequest.StatementRequest.IncTransaction = new IncTransaction();
stmtTransRequest.StatementRequest.IncTransaction.StartDate = "20200601000000";
stmtTransRequest.StatementRequest.IncTransaction.EndDate = "20200611000000";
stmtTransRequest.StatementRequest.IncTransaction.Include = true;
```
## चरण 6: OFX अनुरोध दस्तावेज़ सहेजें
अंत में, हम OFX अनुरोध दस्तावेज़ को XML और SGML दोनों प्रारूपों में सहेजेंगे। यह विभिन्न प्रणालियों के साथ संगतता सुनिश्चित करता है जो किसी भी प्रारूप का उपयोग कर सकते हैं।
```csharp
document.Save(outputDir + @"newOfxRequestBankStatement.xml", OfxVersionEnum.V2x);
document.Save(outputDir + @"newOfxRequestBankStatement.sgml", OfxVersionEnum.V1x);
```
## चरण 7: सफल निष्पादन की पुष्टि करें
यह पुष्टि करने के लिए कि प्रक्रिया सफलतापूर्वक निष्पादित हुई है, हम कंसोल पर एक संदेश प्रिंट कर सकते हैं।
```csharp
Console.WriteLine("CreateOfxBankTransactionRequestFile executed successfully.");
```
## निष्कर्ष
.NET के लिए Aspose.Finance का उपयोग करके OFX बैंक लेनदेन अनुरोध फ़ाइल बनाना एक व्यवस्थित प्रक्रिया है जिसमें अनुरोध दस्तावेज़ सेट करना, साइनऑन और बैंक अनुरोध संदेशों को कॉन्फ़िगर करना, लेनदेन विवरण निर्दिष्ट करना और दस्तावेज़ को सहेजना शामिल है। इस चरण-दर-चरण मार्गदर्शिका का पालन करके, आप अपनी विशिष्ट आवश्यकताओं के अनुरूप OFX अनुरोध फ़ाइलें कुशलतापूर्वक उत्पन्न कर सकते हैं।
## पूछे जाने वाले प्रश्न
### 1. OFX फ़ाइल क्या है?
OFX (ओपन फाइनेंशियल एक्सचेंज) फ़ाइल एक मानक प्रारूप है जिसका उपयोग संस्थाओं और उपयोगकर्ताओं के बीच वित्तीय डेटा के आदान-प्रदान के लिए किया जाता है। इसका व्यापक रूप से बैंक स्टेटमेंट, लेनदेन और अन्य वित्तीय गतिविधियों के लिए उपयोग किया जाता है।
### 2. क्या मैं अन्य प्रोग्रामिंग भाषाओं के साथ .NET के लिए Aspose.Finance का उपयोग कर सकता हूँ?
Aspose.Finance for .NET को खास तौर पर C# जैसी .NET भाषाओं के साथ इस्तेमाल के लिए डिज़ाइन किया गया है। हालाँकि, आप इसे किसी भी .NET-समर्थित वातावरण में इस्तेमाल कर सकते हैं।
### 3. क्या .NET के लिए Aspose.Finance का निःशुल्क परीक्षण उपलब्ध है?
हां, आप .NET के लिए Aspose.Finance का निःशुल्क परीक्षण डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/).
### 4. मैं .NET के लिए Aspose.Finance का समर्थन कैसे प्राप्त करूं?
 आप उनके माध्यम से Aspose समुदाय और तकनीकी टीम से समर्थन प्राप्त कर सकते हैं[सहयता मंच](https://forum.aspose.com/c/finance/43).
### 5. क्या मुझे .NET के लिए Aspose.Finance का अस्थायी लाइसेंस मिल सकता है?
 हाँ, Aspose एक प्रदान करता है[अस्थायी लाइसेंस](https://purchase.aspose.com/temporary-license/) जिसका उपयोग आप उत्पाद का मूल्यांकन करने के लिए कर सकते हैं।