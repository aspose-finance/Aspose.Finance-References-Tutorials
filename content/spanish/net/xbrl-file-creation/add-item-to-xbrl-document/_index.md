---
title: Agregar elemento al documento XBRL
linktitle: Agregar elemento al documento XBRL
second_title: API de Aspose.Finance .NET
description: Aprenda a agregar elementos a documentos XBRL usando Aspose.Finance para .NET. Simplifique los informes financieros en sus aplicaciones .NET. #Aspose #Finanzas
type: docs
weight: 13
url: /es/net/xbrl-file-creation/add-item-to-xbrl-document/
---
El lenguaje extensible de informes comerciales (XBRL) se ha convertido en un formato estándar para los informes financieros, lo que permite una comunicación eficiente y precisa de datos financieros. Aspose.Finance para .NET proporciona una funcionalidad sólida para trabajar con documentos XBRL en sus aplicaciones .NET. En este tutorial, recorreremos los pasos para agregar un elemento a un documento XBRL usando Aspose.Finance para .NET.
## Requisitos previos
Antes de comenzar, asegúrese de tener los siguientes requisitos previos:
### 1. Instale Aspose.Finance para .NET
 Si aún no lo ha hecho, descargue e instale Aspose.Finance para .NET desde[página web oficial](https://releases.aspose.com/finance/net/). Siga las instrucciones de instalación para configurar la biblioteca en su entorno .NET.
### 2. Configure su entorno de desarrollo
Asegúrese de tener un entorno de desarrollo funcional para el desarrollo .NET. Necesitará un IDE compatible como Visual Studio, junto con el marco .NET instalado en su sistema.
## Importar espacios de nombres
Primero, importe los espacios de nombres necesarios a su aplicación .NET para utilizar la funcionalidad proporcionada por Aspose.Finance para .NET.
```csharp
using Aspose.Finance.Xbrl;
using System;
```
#Ahora dividamos el código de ejemplo en varios pasos:
## Paso 1: Definir directorios de origen y de salida
```csharp
string sourceDir = "Your Source Directory";
string outputDir = "Your Output Directory";
```
 Reemplazar`"Your Source Directory"` y`"Your Output Directory"` con las rutas a sus directorios de origen y de salida, respectivamente.
## Paso 2: crear un documento y una instancia XBRL
```csharp
XbrlDocument document = new XbrlDocument();
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
Inicialice un documento XBRL y una instancia con la que trabajar.
## Paso 3: agregar referencia de esquema
```csharp
SchemaRefCollection schemaRefs = xbrlInstance.SchemaRefs;
schemaRefs.Add(sourceDir + @"schema.xsd", "example", "http://ejemplo.com/xbrl/taxonomy");
```
Agregue una referencia de esquema a la instancia XBRL, proporcionando la ruta al archivo de esquema y especificando los detalles del espacio de nombres.
## Paso 4: definir el contexto y la entidad
```csharp
ContextPeriod contextPeriod = new ContextPeriod(DateTime.Parse("2020-01-01"), DateTime.Parse("2020-02-10"));
ContextEntity contextEntity = new ContextEntity("exampleIdentifierScheme", "exampleIdentifier");
Context context = new Context(contextPeriod, contextEntity);
xbrlInstance.Contexts.Add(context);
```
Cree un contexto y una entidad para la instancia XBRL, especificando el período y los detalles de la entidad.
## Paso 5: agregar unidad
```csharp
Unit unit = new Unit(UnitType.Measure);
unit.MeasureQualifiedNames.Add(new QualifiedName("USD", "iso4217", "http://www.xbrl.org/2003/iso4217"));
xbrlInstance.Units.Add(unit);
```
Defina una unidad para la instancia XBRL, especificando los nombres calificados de la medida.
## Paso 6: agregar artículo
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
Agregue un elemento a la instancia XBRL, especificando su concepto, contexto, unidad, precisión y valor.
## Paso 7: guardar el documento
```csharp
document.Save(outputDir + @"document5.xbrl");
```
Guarde el documento XBRL en el directorio de salida.
## Conclusión
Agregar elementos a un documento XBRL es esencial para representar con precisión los datos financieros. Aspose.Finance para .NET simplifica este proceso al proporcionar una API integral para trabajar con documentos XBRL en aplicaciones .NET.
## Preguntas frecuentes
### ¿Puedo usar Aspose.Finance para .NET con cualquier aplicación .NET?
Sí, Aspose.Finance para .NET es compatible con cualquier aplicación .NET, incluidas ASP.NET, WinForms y aplicaciones de consola.
### ¿Aspose.Finance para .NET es de uso gratuito?
 Aspose.Finance para .NET es una biblioteca comercial. Puede descargar una versión de prueba gratuita para evaluar sus funciones y se pueden comprar licencias en[aquí](https://purchase.aspose.com/buy).
### ¿Aspose.Finance para .NET admite otros formatos de informes financieros además de XBRL?
Aspose.Finance para .NET se centra principalmente en la funcionalidad relacionada con XBRL. Sin embargo, Aspose ofrece otras bibliotecas para trabajar con diferentes formatos financieros.
### ¿Cómo puedo obtener soporte para Aspose.Finance para .NET?
 Puede obtener soporte para Aspose.Finance para .NET a través de[foro oficial](https://forum.aspose.com/c/finance/43)donde puede hacer preguntas e interactuar con otros usuarios y personal de soporte.
### ¿Puedo obtener una licencia temporal de Aspose.Finance para .NET?
 Sí, las licencias temporales de Aspose.Finance para .NET están disponibles con fines de prueba. Puedes obtener uno[aquí](https://purchase.aspose.com/temporary-license/).