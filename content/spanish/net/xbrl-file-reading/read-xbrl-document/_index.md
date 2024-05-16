---
title: Leer documento XBRL
linktitle: Leer documento XBRL
second_title: API de Aspose.Finance .NET
description: Aprenda a leer documentos XBRL en .NET usando Aspose.Finance. Mejore sus capacidades de procesamiento de datos financieros sin esfuerzo. #Aspose #Finanzas #XBRL
type: docs
weight: 11
url: /es/net/xbrl-file-reading/read-xbrl-document/
---
## Introducción
Aspose.Finance para .NET es una sólida herramienta de desarrollo de software financiero que permite a los desarrolladores gestionar de manera eficiente los datos financieros dentro de sus aplicaciones .NET. Una de sus características clave es la capacidad de leer documentos XBRL (eXtensible Business Reporting Language) sin problemas. En esta guía completa, recorreremos el proceso de lectura de documentos XBRL utilizando Aspose.Finance para .NET. Al final de este tutorial, tendrá un conocimiento sólido de cómo aprovechar esta funcionalidad para mejorar sus capacidades de procesamiento de datos financieros.
## Requisitos previos
Antes de sumergirnos en el tutorial, asegurémonos de que tiene todo lo que necesita:
### Entorno de desarrollo .NET
En primer lugar, asegúrese de tener un entorno de desarrollo .NET configurado en su máquina. Si aún no lo ha hecho, puede descargar e instalar la última versión del SDK de .NET desde el sitio web oficial de Microsoft.
### Aspose.Finanzas para .NET
Para seguir este tutorial, necesitará tener Aspose.Finance para .NET instalado en su entorno de desarrollo. Puede descargar la biblioteca desde el enlace de descarga oficial que se proporciona a continuación:
[Descargar Aspose.Finance para .NET](https://releases.aspose.com/finance/net/)
### Documento XBRL
Prepare un documento XBRL que desee leer utilizando Aspose.Finance para .NET. Asegúrese de tener la ruta del archivo lista para hacer referencia en su código.
## Importar espacios de nombres
Comencemos importando los espacios de nombres necesarios a su proyecto .NET para acceder a las funcionalidades de Aspose.Finance. Siga estas instrucciones paso a paso:
## Paso 1: abra su proyecto .NET
Inicie su proyecto .NET en su entorno de desarrollo integrado (IDE) preferido, como Visual Studio.
## Paso 2: agregue la referencia de Aspose.Finance
Agregue una referencia a Aspose.Finance para .NET en su proyecto. Puede lograr esto descargando la biblioteca y haciendo referencia a ella localmente o usando NuGet Package Manager para instalarla directamente en su proyecto.
## Paso 3: importar espacios de nombres
Ahora, importe los espacios de nombres requeridos al comienzo de su archivo de código. Estos espacios de nombres brindan acceso a las clases y métodos necesarios para trabajar con documentos XBRL.
```csharp
using Aspose.Finance.Xbrl;
using System;
using System.Collections.Generic;
```
## Leer documento XBRL
Ahora que hemos configurado nuestro entorno e importado los espacios de nombres necesarios, profundicemos en el proceso de lectura de un documento XBRL usando Aspose.Finance para .NET. Siga estas instrucciones paso a paso:
## Paso 1: definir el directorio de origen
 Comience definiendo la ruta del directorio donde se encuentra su documento XBRL. Reemplazar`"Your Source Directory"` con la ruta real a su documento.
```csharp
string sourceDir = "Your Source Directory";
```
## Paso 2: crear el objeto XbrlDocument
 A continuación, cree un`XbrlDocument` objeto proporcionando la ruta a su documento XBRL.
```csharp
XbrlDocument document = new XbrlDocument(sourceDir + @"IdScopeContextPeriodStartAfterEnd.xml");
```
## Paso 3: acceder a instancias XBRL
 Acceda a las instancias XBRL desde el documento utilizando el`XbrlInstances` propiedad.
```csharp
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[0];
```
## Paso 4: extraer hechos, referencias de esquemas, contextos y unidades
Recupere hechos, referencias de esquemas, contextos y unidades de la instancia XBRL.
```csharp
List<Fact> facts = xbrlInstance.Facts;
SchemaRefCollection schemaRefs = xbrlInstance.SchemaRefs;
List<Context> contexts = xbrlInstance.Contexts;
List<Unit> units = xbrlInstance.Units;
```
## Paso 5: Mostrar mensaje de éxito
Informar al usuario que el documento XBRL ha sido leído exitosamente.
```csharp
Console.WriteLine("ReadXbrlDocument executed successfully.");
```
Si sigue estos pasos, habrá leído correctamente un documento XBRL utilizando Aspose.Finance para .NET.
## Conclusión
En este tutorial, cubrimos el proceso de lectura de documentos XBRL usando Aspose.Finance para .NET. Al aprovechar la guía paso a paso proporcionada, puede manejar eficientemente documentos XBRL dentro de sus aplicaciones .NET, mejorando sus capacidades de procesamiento de datos financieros.
## Preguntas frecuentes
### ¿Aspose.Finance para .NET es compatible con todas las versiones de .NET?
Sí, Aspose.Finance para .NET está diseñado para ser compatible con todas las versiones de .NET framework, lo que garantiza una integración perfecta en sus proyectos.
### ¿Puedo utilizar Aspose.Finance para proyectos comerciales?
¡Absolutamente! Aspose.Finance para .NET se puede utilizar tanto para proyectos personales como comerciales. Simplemente compre una licencia para desbloquear todo su potencial.
### ¿Aspose.Finance admite otros formatos de documentos además de XBRL?
Sí, Aspose.Finance brinda soporte para varios formatos de documentos financieros, ofreciendo flexibilidad y versatilidad en el manejo de datos financieros.
### ¿Hay soporte técnico disponible para los usuarios de Aspose.Finance?
¡Ciertamente! Aspose ofrece soporte técnico dedicado para sus productos, incluido Aspose.Finance. Puede acceder al soporte a través del foro de soporte oficial.
### ¿Puedo probar Aspose.Finance antes de realizar una compra?
¡Por supuesto! Aspose ofrece una versión de prueba gratuita de Aspose.Finance, que le permite explorar sus características y capacidades antes de comprometerse.