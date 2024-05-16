---
title: XBRL दस्तावेज़ में ARC भूमिका संदर्भ जोड़ें
linktitle: XBRL दस्तावेज़ में ARC भूमिका संदर्भ जोड़ें
second_title: Aspose.Finance .NET एपीआई
description: .NET के लिए Aspose.Finance का उपयोग करके XBRL दस्तावेज़ों को कुशलतापूर्वक हेरफेर करना सीखें। चरण-दर-चरण मार्गदर्शन के साथ आसानी से ARC भूमिका संदर्भ जोड़ें।
type: docs
weight: 10
url: /hi/net/xbrl-file-creation/add-arc-role-reference-to-xbrl-document/
---
## परिचय
वित्तीय डेटा प्रबंधन और रिपोर्टिंग की दुनिया में, एक्सटेंसिबल बिजनेस रिपोर्टिंग लैंग्वेज (XBRL) एक महत्वपूर्ण भूमिका निभाती है। यह वित्तीय जानकारी के संचार और आदान-प्रदान के तरीके को मानकीकृत करता है, जिससे स्थिरता, सटीकता और दक्षता सुनिश्चित होती है। हालाँकि, XBRL दस्तावेज़ों में हेरफेर करना, विशेष रूप से विशिष्ट भूमिकाओं और संदर्भों को शामिल करते समय, अंतर्निहित तंत्र की सूक्ष्म समझ की आवश्यकता होती है। यह ट्यूटोरियल ऐसे ही एक कार्य पर केंद्रित है: .NET के लिए Aspose.Finance का उपयोग करके XBRL दस्तावेज़ में ARC भूमिका संदर्भ जोड़ना।
## आवश्यक शर्तें
ट्यूटोरियल में शामिल होने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ हैं:
### पर्यावरण सेटअप
1.  .NET के लिए Aspose.Finance स्थापित करें: यहां से Aspose.Finance for .NET लाइब्रेरी डाउनलोड करें और स्थापित करें।[विज्ञप्ति](https://releases.aspose.com/finance/net/).
   
2. विकास परिवेश: विजुअल स्टूडियो या किसी अन्य पसंदीदा IDE के साथ अपना विकास परिवेश सेट करें।
## नामस्थान आयात करें
अपने C# कोड में आवश्यक नामस्थानों को आयात करना सुनिश्चित करें:
```csharp
using Aspose.Finance.Xbrl;
using System;
```
## चरण 1: स्रोत और आउटपुट निर्देशिकाएँ परिभाषित करें
आगे बढ़ने से पहले, स्रोत और आउटपुट निर्देशिकाओं को निर्दिष्ट करें जहां आपकी XBRL फ़ाइलें क्रमशः स्थित और सहेजी जाएंगी।
```csharp
// स्रोत निर्देशिका
string sourceDir = "Your Source Directory";
// उत्पादन निर्देशिका
string outputDir = "Your Output Directory";
```
## चरण 2: एक XBRL दस्तावेज़ बनाएँ
 एक उदाहरण बनाना`XbrlDocument` XBRL डेटा के साथ काम करने के लिए ऑब्जेक्ट.
```csharp
XbrlDocument document = new XbrlDocument();
```
## चरण 3: XbrlInstance संग्रह तक पहुँचें
दस्तावेज़ के भीतर XBRL उदाहरणों के संग्रह तक पहुँचें.
```csharp
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
```
## चरण 4: XbrlInstance जोड़ें
संग्रह में एक नया XBRL उदाहरण जोड़ें.
```csharp
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
## चरण 5: स्कीमा संदर्भ जोड़ें
XBRL इंस्टैंस में स्कीमा संदर्भ शामिल करें, स्रोत निर्देशिका, नामस्थान उपसर्ग और URI निर्दिष्ट करें।
```csharp
SchemaRefCollection schemaRefs = xbrlInstance.SchemaRefs;
schemaRefs.Add(sourceDir + @"schema.xsd", "example", "http://example.com/xbrl/taxonomy");
```
## चरण 6: ArcroleType पुनर्प्राप्त करें
 पुनः प्राप्त करें`ArcroleType` एक विशिष्ट URI पर आधारित.
```csharp
SchemaRef schema = schemaRefs[0];
ArcroleType arcroleType = schema.GetArcroleTypeByURI("http://abc.com/arcrole/फुटनोट-टेस्ट");
```
## चरण 7: आर्क्रोलरेफरेंस जोड़ें
 यदि`ArcroleType` पाया जाता है, एक बनाएँ`ArcroleReference` और इसे XBRL इंस्टेंस के आर्करोल संदर्भों में जोड़ें।
```csharp
if (arcroleType != null)
{
    ArcroleReference arcroleReference = new ArcroleReference(arcroleType);
    xbrlInstance.ArcroleReferences.Add(arcroleReference);
}
```
## चरण 8: दस्तावेज़ सहेजें
संशोधित XBRL दस्तावेज़ को निर्दिष्ट आउटपुट निर्देशिका में सहेजें।
```csharp
document.Save(outputDir + @"document8.xbrl");
```
## निष्कर्ष
इस ट्यूटोरियल में, हमने .NET के लिए Aspose.Finance का उपयोग करके XBRL दस्तावेज़ में ARC रोल संदर्भ जोड़ने का तरीका खोजा है। इन चरण-दर-चरण निर्देशों का पालन करके और Aspose.Finance की क्षमताओं का लाभ उठाकर, आप अपनी विशिष्ट आवश्यकताओं को पूरा करने के लिए XBRL डेटा को कुशलतापूर्वक प्रबंधित और हेरफेर कर सकते हैं।
## पूछे जाने वाले प्रश्न
### एक्सबीआरएल क्या है?
एक्सबीआरएल का तात्पर्य एक्सटेंसिबल बिजनेस रिपोर्टिंग लैंग्वेज से है, जो व्यवसाय और वित्तीय डेटा के इलेक्ट्रॉनिक संचार के लिए एक मानकीकृत भाषा है।
### XBRL क्यों महत्वपूर्ण है?
एक्सबीआरएल वित्तीय जानकारी के आदान-प्रदान और विश्लेषण में स्थिरता, सटीकता और दक्षता सुनिश्चित करता है, जिससे नियामकों, विश्लेषकों और व्यवसायों को लाभ मिलता है।
### क्या Aspose.Finance जटिल XBRL कार्यों को संभाल सकता है?
हां, Aspose.Finance XBRL दस्तावेजों के साथ काम करने के लिए मजबूत कार्यक्षमता प्रदान करता है, जिसमें भूमिका संदर्भ और वर्गीकरण प्रबंधन जैसे जटिल कार्यों को संभालना भी शामिल है।
### क्या Aspose.Finance अन्य .NET लाइब्रेरीज़ के साथ संगत है?
हां, Aspose.Finance अन्य .NET लाइब्रेरीज़ के साथ सहजता से एकीकृत होता है, जो वित्तीय डेटा हेरफेर और रिपोर्टिंग के लिए व्यापक समर्थन प्रदान करता है।
### मैं Aspose.Finance के लिए अतिरिक्त सहायता कहां पा सकता हूं?
 अतिरिक्त सहायता के लिए यहां जाएं[Aspose.Finance सहायता पृष्ठ](https://forum.aspose.com/c/finance/43).