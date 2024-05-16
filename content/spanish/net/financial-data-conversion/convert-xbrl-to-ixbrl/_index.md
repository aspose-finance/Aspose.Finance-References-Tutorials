---
title: Convierta XBRL a iXBRL fácilmente
linktitle: Convertir XBRL a iXBRL
second_title: API de Aspose.Finance .NET
description: Convierta fácilmente XBRL a iXBRL con Aspose.Finance para .NET. Siga nuestra guía paso a paso para una transición perfecta. #Aspose #Finanzas
type: docs
weight: 10
url: /es/net/financial-data-conversion/convert-xbrl-to-ixbrl/
---
## Convierta XBRL a iXBRL usando Aspose.Finance para .NET
En el mundo actual basado en datos, los profesionales financieros a menudo necesitan convertir archivos XBRL (eXtensible Business Reporting Language) al formato iXBRL (Inline XBRL) para garantizar que los datos sean legibles tanto por máquinas como por humanos. Si está buscando una solución sólida para lograr esto, Aspose.Finance para .NET es una excelente opción. Esta guía lo guiará a través del proceso paso a paso, desde la configuración de su entorno hasta la conversión exitosa de sus archivos.
## Requisitos previos
Antes de sumergirnos en el proceso de conversión, repasemos lo que necesita:
1. Conocimientos básicos de .NET: la familiaridad con C# y el marco .NET es esencial.
2. Aspose.Finance para .NET: deberá descargar e instalar la biblioteca Aspose.Finance para .NET.
3. Archivos XBRL: asegúrese de tener los archivos XBRL que desea convertir.
4. Entorno de desarrollo: un entorno de desarrollo .NET como Visual Studio.
## Importar espacios de nombres
Para comenzar, necesita importar los espacios de nombres necesarios a su proyecto. Esto le permite acceder a las funcionalidades proporcionadas por Aspose.Finance.
```csharp
using Aspose.Finance.Xbrl;
using System;
using System.Collections.Generic;
```
## Paso 1: configurar directorios de trabajo
Primero, debe especificar los directorios para sus archivos XBRL de origen y los archivos iXBRL de salida.
```csharp
// Directorios de trabajo
string sourceDir = "Your Source Directory";
string outputDir = "Your Output Directory";
```
## Paso 2: cargar el documento XBRL
 A continuación, cargará su documento XBRL usando el`XbrlDocument` clase proporcionada por Aspose.Finance.
```csharp
XbrlDocument document = new XbrlDocument(sourceDir + @"IdScopeContextPeriodStartAfterEnd.xml");
```
 Esta línea de código inicializa una nueva instancia del`XbrlDocument` clase y carga el archivo XBRL especificado.
## Paso 3: configurar las opciones de guardar
Para convertir el documento a un formato diferente, debe configurar las opciones de guardar. Para este tutorial, guardaremos el archivo en formato iXBRL.
```csharp
SaveOptions saveOptions = new SaveOptions();
saveOptions.SaveFormat = SaveFormat.iXBRL;
```
 Aquí,`SaveOptions` se utiliza para especificar el formato en el que desea guardar el documento.
## Paso 4: guarde el archivo
Ahora que todo está configurado, puede guardar el documento XBRL como un archivo iXBRL.
```csharp
document.Save(outputDir + @"ConvertXbrlToiXbrl_out.ixbrl", saveOptions);
```
Este comando guarda el archivo convertido en el directorio de salida especificado.
## Paso 5: confirme la conversión
Finalmente, puede confirmar la conversión mostrando un mensaje de éxito.
```csharp
Console.WriteLine("ConvertXbrlToiXbrl executed successfully.");
```
## Conclusión
¡Felicidades! Ha convertido con éxito un archivo XBRL a iXBRL usando Aspose.Finance para .NET. Esta poderosa biblioteca simplifica el proceso de conversión, permitiendo transiciones fluidas entre diferentes formatos de informes financieros. Ya sea desarrollador o profesional financiero, dominar esta herramienta sin duda mejorará su productividad y eficiencia.
## Preguntas frecuentes
### 1. ¿Qué es Aspose.Finance para .NET?
Aspose.Finance para .NET es una biblioteca completa para administrar formatos financieros como XBRL, iXBRL y OFX. Permite a los desarrolladores crear, leer y manipular documentos financieros mediante programación.
### 2. ¿Puedo probar Aspose.Finance para .NET antes de comprarlo?
 Sí, puedes descargar una versión de prueba gratuita desde[Página de lanzamientos de Aspose](https://releases.aspose.com/finance/net/).
### 3. ¿Cómo obtengo soporte para Aspose.Finance para .NET?
 Puedes visitar el[Foro de soporte de Aspose.Finance](https://forum.aspose.com/c/finance/43) para obtener ayuda con cualquier problema que encuentre.
### 4. ¿Cuáles son las características principales de Aspose.Finance para .NET?
Aspose.Finance para .NET ofrece una amplia gama de funciones que incluyen la capacidad de crear, leer y convertir varios formatos financieros, amplias capacidades API y un sólido manejo de errores.
### 5. ¿Dónde puedo encontrar documentación detallada?
 La documentación detallada está disponible en el[Página de documentación de Aspose.Finance](https://reference.aspose.com/finance/net/).