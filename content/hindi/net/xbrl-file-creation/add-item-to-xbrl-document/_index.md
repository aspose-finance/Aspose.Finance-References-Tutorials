---
title: XBRL दस्तावेज़ में आइटम जोड़ें
linktitle: XBRL दस्तावेज़ में आइटम जोड़ें
second_title: Aspose.Finance .NET एपीआई
description: .NET के लिए Aspose.Finance का उपयोग करके XBRL दस्तावेज़ों में आइटम जोड़ने का तरीका जानें। अपने .NET अनुप्रयोगों में वित्तीय रिपोर्टिंग को सरल बनाएँ। #Aspose #Finance
type: docs
weight: 13
url: /hi/net/xbrl-file-creation/add-item-to-xbrl-document/
---
एक्सटेंसिबल बिजनेस रिपोर्टिंग लैंग्वेज (XBRL) वित्तीय रिपोर्टिंग के लिए एक मानक प्रारूप बन गया है, जो वित्तीय डेटा के कुशल और सटीक संचार को सक्षम बनाता है। Aspose.Finance for .NET आपके .NET अनुप्रयोगों में XBRL दस्तावेज़ों के साथ काम करने के लिए मजबूत कार्यक्षमता प्रदान करता है। इस ट्यूटोरियल में, हम Aspose.Finance for .NET का उपयोग करके XBRL दस्तावेज़ में कोई आइटम जोड़ने के चरणों के माध्यम से चलेंगे।
## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ हैं:
### 1. .NET के लिए Aspose.Finance स्थापित करें
 यदि आपने पहले से ऐसा नहीं किया है, तो .NET के लिए Aspose.Finance को डाउनलोड और इंस्टॉल करें[आधिकारिक वेबसाइट](https://releases.aspose.com/finance/net/)अपने .NET वातावरण में लाइब्रेरी स्थापित करने के लिए स्थापना निर्देशों का पालन करें।
### 2. अपना विकास वातावरण स्थापित करें
सुनिश्चित करें कि आपके पास .NET विकास के लिए एक कार्यशील विकास वातावरण है। आपको अपने सिस्टम पर इंस्टॉल किए गए .NET फ्रेमवर्क के साथ-साथ Visual Studio जैसे संगत IDE की आवश्यकता होगी।
## नामस्थान आयात करें
सबसे पहले, .NET के लिए Aspose.Finance द्वारा प्रदान की गई कार्यक्षमता का उपयोग करने के लिए अपने .NET अनुप्रयोग में आवश्यक नामस्थान आयात करें।
```csharp
using Aspose.Finance.Xbrl;
using System;
```
#अब आइए उदाहरण कोड को कई चरणों में विभाजित करें:
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
## चरण 4: संदर्भ और इकाई को परिभाषित करें
```csharp
ContextPeriod contextPeriod = new ContextPeriod(DateTime.Parse("2020-01-01"), DateTime.Parse("2020-02-10"));
ContextEntity contextEntity = new ContextEntity("exampleIdentifierScheme", "exampleIdentifier");
Context context = new Context(contextPeriod, contextEntity);
xbrlInstance.Contexts.Add(context);
```
XBRL इंस्टैंस के लिए संदर्भ और इकाई बनाएं, अवधि और इकाई विवरण निर्दिष्ट करें।
## चरण 5: इकाई जोड़ें
```csharp
Unit unit = new Unit(UnitType.Measure);
unit.MeasureQualifiedNames.Add(new QualifiedName("USD", "iso4217", "http://www.xbrl.org/2003/iso4217"));
xbrlInstance.Units.Add(unit);
```
माप योग्य नामों को निर्दिष्ट करते हुए XBRL इंस्टेंस के लिए एक इकाई परिभाषित करें।
## चरण 6: आइटम जोड़ें
```csharp
Concept fixedAssetsConcept = schema.GetConceptByName("fixedAssets");
if (fixedAssetsConcept != null)
{
    Item item = new Item(fixedAssetsConcept);
    item.ContextRef = context;
    item.UnitRef = unit;
    item.Precision = 4;
    item.Value = "1444";
    xbrlInstance.Facts.Add(item);
}
```
XBRL इंस्टैंस में एक आइटम जोड़ें, इसकी अवधारणा, संदर्भ, इकाई, परिशुद्धता और मान निर्दिष्ट करें।
## चरण 7: दस्तावेज़ सहेजें
```csharp
document.Save(outputDir + @"document5.xbrl");
```
XBRL दस्तावेज़ को आउटपुट निर्देशिका में सहेजें.
## निष्कर्ष
वित्तीय डेटा को सटीक रूप से प्रस्तुत करने के लिए XBRL दस्तावेज़ में आइटम जोड़ना आवश्यक है। .NET के लिए Aspose.Finance .NET अनुप्रयोगों में XBRL दस्तावेज़ों के साथ काम करने के लिए एक व्यापक API प्रदान करके इस प्रक्रिया को सरल बनाता है।
## पूछे जाने वाले प्रश्न
### क्या मैं किसी भी .NET अनुप्रयोग के साथ Aspose.Finance for .NET का उपयोग कर सकता हूँ?
हां, Aspose.Finance for .NET किसी भी .NET अनुप्रयोग के साथ संगत है, जिसमें ASP.NET, WinForms और कंसोल अनुप्रयोग शामिल हैं।
### क्या .NET के लिए Aspose.Finance का उपयोग निःशुल्क है?
 Aspose.Finance for .NET एक व्यावसायिक लाइब्रेरी है। आप इसकी विशेषताओं का मूल्यांकन करने के लिए एक निःशुल्क परीक्षण संस्करण डाउनलोड कर सकते हैं, और लाइसेंस यहाँ से खरीदे जा सकते हैं[यहाँ](https://purchase.aspose.com/buy).
### क्या Aspose.Finance for .NET XBRL के अलावा अन्य वित्तीय रिपोर्टिंग प्रारूपों का समर्थन करता है?
.NET के लिए Aspose.Finance मुख्य रूप से XBRL-संबंधित कार्यक्षमता पर केंद्रित है। हालाँकि, Aspose विभिन्न वित्तीय प्रारूपों के साथ काम करने के लिए अन्य लाइब्रेरी प्रदान करता है।
### मैं .NET के लिए Aspose.Finance का समर्थन कैसे प्राप्त कर सकता हूं?
 आप .NET के लिए Aspose.Finance का समर्थन प्राप्त कर सकते हैं[आधिकारिक मंच](https://forum.aspose.com/c/finance/43)जहां आप प्रश्न पूछ सकते हैं और अन्य उपयोगकर्ताओं और सहायता कर्मचारियों के साथ बातचीत कर सकते हैं।
### क्या मैं .NET के लिए Aspose.Finance का अस्थायी लाइसेंस प्राप्त कर सकता हूँ?
 हां, परीक्षण उद्देश्यों के लिए Aspose.Finance for .NET के लिए अस्थायी लाइसेंस उपलब्ध हैं। आप एक प्राप्त कर सकते हैं[यहाँ](https://purchase.aspose.com/temporary-license/).