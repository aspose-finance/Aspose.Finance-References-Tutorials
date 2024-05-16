---
title: XBRL दस्तावेज़ में फ़ुटनोट लिंक जोड़ें
linktitle: XBRL दस्तावेज़ में फ़ुटनोट लिंक जोड़ें
second_title: Aspose.Finance .NET एपीआई
description: .NET के लिए Aspose.Finance का उपयोग करके XBRL दस्तावेज़ों में फ़ुटनोट लिंक जोड़ने का तरीका जानें। अतिरिक्त संदर्भ के साथ वित्तीय रिपोर्ट को आसानी से बेहतर बनाएँ।
type: docs
weight: 12
url: /hi/net/xbrl-file-creation/add-footnote-link-to-xbrl-document/
---
किसी XBRL दस्तावेज़ में फ़ुटनोट लिंक जोड़ना विशिष्ट डेटा बिंदुओं के लिए अतिरिक्त संदर्भ या स्पष्टीकरण प्रदान करने के लिए महत्वपूर्ण है। इस ट्यूटोरियल में, हम .NET के लिए Aspose.Finance का उपयोग करके चरण दर चरण प्रक्रिया से गुजरेंगे।
## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:
1.  Aspose.Finance for .NET: सुनिश्चित करें कि आपने अपने सिस्टम पर Aspose.Finance for .NET इंस्टॉल किया है। आप इसे यहाँ से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/finance/net/).
  
2. विकास परिवेश: .NET फ्रेमवर्क या .NET कोर के साथ एक विकास परिवेश स्थापित करें।
## नामस्थान आयात करें:
```csharp
using Aspose.Finance.Xbrl;
using System;
```
## चरण 1: स्रोत और आउटपुट निर्देशिकाएँ सेट करें
सबसे पहले, स्रोत और आउटपुट फ़ाइलों के लिए निर्देशिकाएँ निर्दिष्ट करें:
```csharp
// स्रोत निर्देशिका
string sourceDir = "Your Source Directory";
// उत्पादन निर्देशिका
string outputDir = "Your Output Directory";
```
## चरण 2: एक XBRL दस्तावेज़ और इंस्टेंस बनाएँ
XBRL दस्तावेज़ और इंस्टैंस आरंभ करें:
```csharp
XbrlDocument document = new XbrlDocument();
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
## चरण 3: स्कीमा संदर्भ जोड़ें
XBRL इंस्टैंस में स्कीमा संदर्भ जोड़ें:
```csharp
SchemaRefCollection schemaRefs = xbrlInstance.SchemaRefs;
schemaRefs.Add(sourceDir + @"schema.xsd", "example", "http://example.com/xbrl/taxonomy");
SchemaRef schema = schemaRefs[0];
```
## चरण 4: संदर्भ परिभाषित करें
XBRL इंस्टैंस के लिए संदर्भ परिभाषित करें:
```csharp
ContextPeriod contextPeriod = new ContextPeriod(DateTime.Parse("2020-01-01"), DateTime.Parse("2020-02-10"));
ContextEntity contextEntity = new ContextEntity("exampleIdentifierScheme", "exampleIdentifier");
Context context = new Context(contextPeriod, contextEntity);
context.Id = "cd1";
xbrlInstance.Contexts.Add(context);
```
## चरण 5: फ़ुटनोट लिंक जोड़ें
XBRL इंस्टैंस के लिए एक फ़ुटनोट लिंक बनाएं और जोड़ें:
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
## चरण 6: दस्तावेज़ सहेजें
संशोधित XBRL दस्तावेज़ सहेजें:
```csharp
document.Save(outputDir + @"document6.xbrl");
```

## निष्कर्ष
.NET के लिए Aspose.Finance के साथ XBRL दस्तावेज़ में फ़ुटनोट लिंक जोड़ना एक सीधी प्रक्रिया है। इस ट्यूटोरियल में बताए गए चरणों का पालन करके, आप अपनी वित्तीय रिपोर्ट में अतिरिक्त संदर्भ या स्पष्टीकरण को सहजता से शामिल कर सकते हैं।
## पूछे जाने वाले प्रश्न
### क्या मैं एक एकल XBRL दस्तावेज़ में एकाधिक फ़ुटनोट लिंक जोड़ सकता हूँ?
हां, आप प्रत्येक अतिरिक्त लिंक के लिए इस ट्यूटोरियल में बताए गए चरणों को दोहराकर कई फ़ुटनोट लिंक जोड़ सकते हैं।
### क्या Aspose.Finance for .NET .NET फ्रेमवर्क और .NET कोर दोनों के साथ संगत है?
हां, Aspose.Finance for .NET .NET फ्रेमवर्क और .NET कोर वातावरण दोनों का समर्थन करता है।
### मैं .NET के लिए Aspose.Finance का अस्थायी लाइसेंस कैसे प्राप्त कर सकता हूं?
 आप यहां से अस्थायी लाइसेंस प्राप्त कर सकते हैं[यहाँ](https://purchase.aspose.com/temporary-license/).
### क्या Aspose.Finance for .NET XBRL सत्यापन के लिए समर्थन प्रदान करता है?
हां, .NET के लिए Aspose.Finance उद्योग मानकों के अनुपालन को सुनिश्चित करने के लिए XBRL सत्यापन के लिए व्यापक समर्थन प्रदान करता है।
### मैं .NET के लिए Aspose.Finance हेतु अतिरिक्त संसाधन और समर्थन कहां पा सकता हूं?
 आप यहां जा सकते हैं[Aspose.Finance .NET फ़ोरम के लिए](https://forum.aspose.com/c/finance/43) सहायता और दस्तावेज़ तक पहुंच के लिए[यहाँ](https://reference.aspose.com/finance/net/).