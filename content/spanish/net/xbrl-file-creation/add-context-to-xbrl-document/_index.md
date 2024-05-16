---
title: Agregar contexto al documento XBRL
linktitle: Agregar contexto al documento XBRL
second_title: API de Aspose.Finance .NET
description: Aprenda a agregar contexto a documentos XBRL en .NET usando Aspose.Finance para optimizar los informes financieros. #Aspose #Finanzas #XBRL
type: docs
weight: 11
url: /es/net/xbrl-file-creation/add-context-to-xbrl-document/
---
## Introducción
En el ámbito de los informes financieros, XBRL (eXtensible Business Reporting Language) desempeña un papel fundamental en la estandarización del intercambio de información empresarial. Agregar contexto a los documentos XBRL es crucial para garantizar la integridad y relevancia de los datos que contienen. Con Aspose.Finance para .NET, este proceso se simplifica y es eficiente, lo que permite a los desarrolladores incorporar contexto sin problemas en sus documentos XBRL.
## Requisitos previos
Antes de sumergirse en el tutorial, asegúrese de tener los siguientes requisitos previos:
1. Biblioteca Aspose.Finance para .NET: descargue e instale la biblioteca Aspose.Finance para .NET desde[lanzamientos](https://releases.aspose.com/finance/net/).
2. Entorno de desarrollo .NET: asegúrese de tener un entorno de desarrollo .NET funcional configurado en su máquina.
3. Comprensión básica de C#: la familiaridad con el lenguaje de programación C# será útil para seguir los ejemplos.
## Importar espacios de nombres
En su proyecto C#, importe los espacios de nombres necesarios para acceder a la funcionalidad proporcionada por Aspose.Finance para .NET:
```csharp
using Aspose.Finance.Xbrl;
using System;
```
## Paso 1: configurar el directorio de salida
Antes de agregar contexto al documento XBRL, especifique el directorio de salida donde se guardará el documento modificado:
```csharp
string outputDir = "Your Output Directory";
```
 Reemplazar`"Your Output Directory"` con la ruta deseada en su sistema.
## Paso 2: crear documento XBRL
 Crear una instancia de`XbrlDocument` objeto para trabajar con documentos XBRL:
```csharp
XbrlDocument document = new XbrlDocument();
```
Este objeto representa el documento XBRL que será manipulado.
## Paso 3: agregar instancia XBRL
Agregue una instancia XBRL al documento. Cada instancia contiene los datos para un período de informe específico:
```csharp
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
Este paso inicializa una instancia XBRL dentro del documento.
## Paso 4: Definir el período y la entidad del contexto
Cree un período de contexto y una entidad para la instancia XBRL:
```csharp
ContextPeriod contextPeriod = new ContextPeriod(DateTime.Parse("2020-01-01"), DateTime.Parse("2020-02-10"));
ContextEntity contextEntity = new ContextEntity("exampleIdentifierScheme", "exampleIdentifier");
```
Especifique el período y los detalles de la entidad de acuerdo con sus requisitos de presentación de informes.
## Paso 5: crear contexto
Construya un contexto utilizando el período y la entidad definidos en el paso anterior:
```csharp
Context context = new Context(contextPeriod, contextEntity);
```
Este contexto encapsula la información temporal y relacionada con la entidad.
## Paso 6: agregar contexto a la instancia XBRL
Asocie el contexto creado en el paso anterior con la instancia XBRL:
```csharp
xbrlInstance.Contexts.Add(context);
```
Este paso vincula el contexto a la instancia XBRL, proporcionando información contextual relevante a los datos.
## Paso 7: guarde el documento
Guarde el documento XBRL modificado en el directorio de salida especificado:
```csharp
document.Save(outputDir + @"document3.xbrl");
```
Esto finaliza el proceso, guardando el documento XBRL con el contexto agregado.
## Conclusión
Si sigue estos pasos, puede agregar contexto de manera efectiva a documentos XBRL usando Aspose.Finance para .NET. Esto mejora la claridad y usabilidad de los datos financieros, facilitando análisis e informes precisos.
## Preguntas frecuentes
### ¿Puede Aspose.Finance para .NET manejar documentos XBRL de gran tamaño?
Aspose.Finance para .NET está optimizado para manejar documentos XBRL de distintos tamaños, incluidos grandes conjuntos de datos.
### ¿Existe una versión de prueba disponible de Aspose.Finance para .NET?
Sí, puede descargar una versión de prueba gratuita desde el sitio web oficial de Aspose.
### ¿Aspose.Finance para .NET admite otros estándares de informes financieros además de XBRL?
Aspose.Finance se centra principalmente en funcionalidades relacionadas con XBRL, pero también brinda soporte para otros formatos financieros.
### ¿Puedo personalizar la información de contexto según mis requisitos específicos?
Por supuesto, Aspose.Finance para .NET ofrece flexibilidad para personalizar la información de contexto según sus necesidades.
### ¿Dónde puedo encontrar soporte o recursos adicionales para Aspose.Finance para .NET?
Puede visitar el foro Aspose.Finance para obtener ayuda de la comunidad o explorar la documentación para obtener orientación completa.