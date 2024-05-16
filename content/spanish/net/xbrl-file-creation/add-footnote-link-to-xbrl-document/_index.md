---
title: Agregar enlace de nota al pie al documento XBRL
linktitle: Agregar enlace de nota al pie al documento XBRL
second_title: API de Aspose.Finance .NET
description: Aprenda a agregar enlaces de notas al pie a documentos XBRL usando Aspose.Finance para .NET. Mejore los informes financieros con contexto adicional sin esfuerzo.
type: docs
weight: 12
url: /es/net/xbrl-file-creation/add-footnote-link-to-xbrl-document/
---
Agregar un enlace de nota al pie a un documento XBRL es crucial para proporcionar contexto adicional o explicaciones para puntos de datos específicos. En este tutorial, recorreremos el proceso paso a paso utilizando Aspose.Finance para .NET.
## Requisitos previos
Antes de comenzar, asegúrese de tener implementados los siguientes requisitos previos:
1.  Aspose.Finance para .NET: asegúrese de haber instalado Aspose.Finance para .NET en su sistema. Puedes descargarlo desde[aquí](https://releases.aspose.com/finance/net/).
  
2. Entorno de desarrollo: tenga un entorno de desarrollo configurado con .NET Framework o .NET Core.
## Importar espacios de nombres:
```csharp
using Aspose.Finance.Xbrl;
using System;
```
## Paso 1: configurar los directorios de origen y de salida
Primero, especifique los directorios para los archivos fuente y de salida:
```csharp
// Directorio fuente
string sourceDir = "Your Source Directory";
// Directorio de salida
string outputDir = "Your Output Directory";
```
## Paso 2: crear un documento y una instancia XBRL
Inicialice un documento XBRL y una instancia:
```csharp
XbrlDocument document = new XbrlDocument();
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
## Paso 3: agregar referencias de esquema
Agregue referencias de esquema a la instancia XBRL:
```csharp
SchemaRefCollection schemaRefs = xbrlInstance.SchemaRefs;
schemaRefs.Add(sourceDir + @"schema.xsd", "example", "http://ejemplo.com/xbrl/taxonomy");
SchemaRef schema = schemaRefs[0];
```
## Paso 4: definir el contexto
Defina el contexto para la instancia XBRL:
```csharp
ContextPeriod contextPeriod = new ContextPeriod(DateTime.Parse("2020-01-01"), DateTime.Parse("2020-02-10"));
ContextEntity contextEntity = new ContextEntity("exampleIdentifierScheme", "exampleIdentifier");
Context context = new Context(contextPeriod, contextEntity);
context.Id = "cd1";
xbrlInstance.Contexts.Add(context);
```
## Paso 5: agregar un enlace a la nota al pie
Cree y agregue un enlace de nota al pie a la instancia XBRL:
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
## Paso 6: guarde el documento
Guarde el documento XBRL modificado:
```csharp
document.Save(outputDir + @"document6.xbrl");
```

## Conclusión
Agregar un enlace de nota al pie a un documento XBRL es un proceso sencillo con Aspose.Finance para .NET. Si sigue los pasos descritos en este tutorial, podrá incorporar sin problemas contexto o explicaciones adicionales en sus informes financieros.
## Preguntas frecuentes
### ¿Puedo agregar varios enlaces de notas al pie a un único documento XBRL?
Sí, puede agregar varios enlaces de notas al pie repitiendo los pasos descritos en este tutorial para cada enlace adicional.
### ¿Aspose.Finance para .NET es compatible tanto con .NET Framework como con .NET Core?
Sí, Aspose.Finance para .NET admite entornos .NET Framework y .NET Core.
### ¿Cómo puedo obtener una licencia temporal de Aspose.Finance para .NET?
 Puede obtener una licencia temporal de[aquí](https://purchase.aspose.com/temporary-license/).
### ¿Aspose.Finance para .NET proporciona soporte para la validación XBRL?
Sí, Aspose.Finance para .NET ofrece soporte integral para la validación XBRL para garantizar el cumplimiento de los estándares de la industria.
### ¿Dónde puedo encontrar recursos adicionales y soporte para Aspose.Finance para .NET?
 Puedes visitar el[Foro Aspose.Finance para .NET](https://forum.aspose.com/c/finance/43) para soporte y documentación de acceso[aquí](https://reference.aspose.com/finance/net/).