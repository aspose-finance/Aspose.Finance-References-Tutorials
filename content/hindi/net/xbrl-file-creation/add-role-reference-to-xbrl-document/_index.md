---
title: XBRL दस्तावेज़ में भूमिका संदर्भ जोड़ें
linktitle: XBRL दस्तावेज़ में भूमिका संदर्भ जोड़ें
second_title: Aspose.Finance .NET एपीआई
description: .NET के लिए Aspose.Finance का उपयोग करके XBRL दस्तावेज़ों में भूमिका संदर्भ जोड़ना सीखें। इस ट्यूटोरियल के साथ अपने .NET अनुप्रयोगों में वित्तीय रिपोर्टिंग को सरल बनाएँ।
type: docs
weight: 14
url: /hi/net/xbrl-file-creation/add-role-reference-to-xbrl-document/
---
XBRL (एक्सटेंसिबल बिजनेस रिपोर्टिंग लैंग्वेज) व्यावसायिक जानकारी के आदान-प्रदान के लिए एक मानक बन गया है, खासकर वित्तीय रिपोर्टिंग में। .NET के लिए Aspose.Finance .NET अनुप्रयोगों में XBRL दस्तावेज़ों के साथ काम करना आसान बनाता है। यह ट्यूटोरियल आपको .NET के लिए Aspose.Finance का उपयोग करके XBRL दस्तावेज़ में भूमिका संदर्भ जोड़ने की प्रक्रिया के माध्यम से मार्गदर्शन करेगा।
## आवश्यक शर्तें
आरंभ करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ हैं:
### 1. .NET के लिए Aspose.Finance स्थापित करें
सुनिश्चित करें कि आपके विकास परिवेश में Aspose.Finance for .NET स्थापित है। यदि आपने पहले से ऐसा नहीं किया है, तो इसे यहाँ से डाउनलोड करें।[विज्ञप्ति](https://releases.aspose.com/finance/net/) और स्थापना निर्देशों का पालन करें.
### 2. अपना विकास वातावरण स्थापित करें
सुनिश्चित करें कि आपके पास .NET विकास के लिए एक कार्यशील विकास वातावरण है। इसमें Visual Studio जैसे संगत IDE और आपके सिस्टम पर स्थापित .NET फ़्रेमवर्क शामिल है।
## नामस्थान आयात करें
.NET के लिए Aspose.Finance द्वारा प्रदान की गई कार्यक्षमता तक पहुँचने के लिए अपने .NET अनुप्रयोग में आवश्यक नामस्थानों को आयात करके आरंभ करें।
```csharp
using Aspose.Finance.Xbrl;
using System;
using Aspose
.Finance.Xbrl.Roles;
```
## चरण 1: स्रोत और आउटपुट निर्देशिकाएँ परिभाषित करें
```csharp
string sourceDir = "Your Source Directory";
string outputDir = "Your Output Directory";
```
 प्रतिस्थापित करें`"Your Source Directory"` और`"Your Output Directory"` क्रमशः आपके स्रोत और आउटपुट निर्देशिकाओं के पथ के साथ।
## चरण 2: एक XBRL दस्तावेज़ और इंस्टेंस बनाएँ
```csharp
XbrlDocument document = new XbrlDocument();
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
कार्य करने के लिए एक XBRL दस्तावेज़ और इंस्टैंस आरंभ करें.
## चरण 3: स्कीमा संदर्भ जोड़ें
```csharp
SchemaRefCollection schemaRefs = xbrlInstance.SchemaRefs;
schemaRefs.Add(sourceDir + @"schema.xsd", "example", "http://example.com/xbrl/taxonomy");
```
XBRL इंस्टैंस में स्कीमा संदर्भ जोड़ें, स्कीमा फ़ाइल का पथ प्रदान करें और नामस्थान विवरण निर्दिष्ट करें।
## चरण 4: भूमिका प्रकार प्राप्त करें और भूमिका संदर्भ जोड़ें
```csharp
SchemaRef schema = schemaRefs[0];
RoleType roleType = schema.GetRoleTypeByURI("http://abc.com/role/link1");
if (roleType != null)
{
    RoleReference roleReference = new RoleReference(roleType);
    xbrlInstance.RoleReferences.Add(roleReference);
}
```
URI का उपयोग करके भूमिका प्रकार को पुनः प्राप्त करें और XBRL इंस्टैंस में भूमिका संदर्भ जोड़ें।
## चरण 5: दस्तावेज़ सहेजें
```csharp
document.Save(outputDir + @"document7.xbrl");
```
XBRL दस्तावेज़ को आउटपुट निर्देशिका में सहेजें.
## निष्कर्ष
XBRL दस्तावेज़ों में भूमिका संदर्भ जोड़ना दस्तावेज़ के भीतर विभिन्न तत्वों की भूमिकाओं को परिभाषित करने के लिए महत्वपूर्ण है। Aspose.Finance for .NET इस कार्य को पूरा करने का एक सरल तरीका प्रदान करता है, जो डेवलपर्स को उनके .NET अनुप्रयोगों में XBRL दस्तावेज़ों के साथ कुशलतापूर्वक काम करने में सक्षम बनाता है।
## पूछे जाने वाले प्रश्न
### क्या मैं किसी भी .NET अनुप्रयोग के साथ Aspose.Finance for .NET का उपयोग कर सकता हूँ?
हां, Aspose.Finance for .NET किसी भी .NET अनुप्रयोग के साथ संगत है, जिसमें ASP.NET, WinForms और कंसोल अनुप्रयोग शामिल हैं।
### क्या .NET के लिए Aspose.Finance का उपयोग निःशुल्क है?
 Aspose.Finance for .NET एक व्यावसायिक लाइब्रेरी है। आप इसकी विशेषताओं का मूल्यांकन करने के लिए एक निःशुल्क परीक्षण संस्करण डाउनलोड कर सकते हैं, और लाइसेंस यहाँ से खरीदे जा सकते हैं[यहाँ](https://purchase.aspose.com/buy).
### क्या Aspose.Finance for .NET XBRL के अलावा अन्य वित्तीय रिपोर्टिंग प्रारूपों का समर्थन करता है?
.NET के लिए Aspose.Finance मुख्य रूप से XBRL-संबंधित कार्यक्षमता पर केंद्रित है। हालाँकि, Aspose विभिन्न वित्तीय प्रारूपों के साथ काम करने के लिए अन्य लाइब्रेरी प्रदान करता है।
### मैं .NET के लिए Aspose.Finance का समर्थन कैसे प्राप्त कर सकता हूं?
 आप .NET के लिए Aspose.Finance का समर्थन प्राप्त कर सकते हैं[मंच](https://forum.aspose.com/c/finance/43)जहां आप प्रश्न पूछ सकते हैं और अन्य उपयोगकर्ताओं और सहायता कर्मचारियों के साथ बातचीत कर सकते हैं।
### क्या मैं .NET के लिए Aspose.Finance का अस्थायी लाइसेंस प्राप्त कर सकता हूँ?
 हां, परीक्षण उद्देश्यों के लिए Aspose.Finance for .NET के लिए अस्थायी लाइसेंस उपलब्ध हैं। आप एक प्राप्त कर सकते हैं[यहाँ](https://purchase.aspose.com/temporary-license/).