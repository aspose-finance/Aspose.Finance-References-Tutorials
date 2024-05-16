---
title: Agregar referencia de esquema al documento XBRL
linktitle: Agregar referencia de esquema al documento XBRL
second_title: API de Aspose.Finance .NET
description: Aprenda a agregar referencias de esquema a documentos XBRL usando Aspose.Finance para .NET. ¡Agilice su procesamiento de datos financieros hoy!
type: docs
weight: 15
url: /es/net/xbrl-file-creation/add-schema-reference-to-xbrl-document/
---
## Presentamos Aspose.Finance para .NET
Aspose.Finance para .NET es una poderosa biblioteca que proporciona funcionalidades integrales para procesar y manipular documentos y datos financieros dentro de aplicaciones .NET. Ya sea que esté creando software de contabilidad, herramientas de análisis financiero o cualquier otra aplicación financiera, Aspose.Finance para .NET ofrece una amplia gama de funciones para agilizar su proceso de desarrollo.
## Requisitos previos
Antes de sumergirse en el uso de Aspose.Finance para .NET, asegúrese de tener configurados los siguientes requisitos previos:
### 1. Instale Visual Studio
Asegúrese de tener Visual Studio instalado en su sistema. Puede descargarlo e instalarlo desde el sitio web oficial de Microsoft.
### 2. Obtenga una licencia de Aspose.Finance
Para utilizar todas las capacidades de Aspose.Finance para .NET, debe adquirir una licencia válida. Puede adquirir una licencia en[aquí](https://purchase.aspose.com/buy) u optar por una licencia temporal con fines de prueba.
### 3. Descargue y haga referencia a Aspose.Finance para .NET
 Descargue la biblioteca Aspose.Finance para .NET desde[página de lanzamientos](https://releases.aspose.com/finance/net/) y haga referencia a él en su proyecto .NET.
### 4. Acceda a la documentación y al soporte
 Referirse a[Documentación API](https://reference.aspose.com/finance/net/) para obtener información detallada sobre el uso de Aspose.Finance para .NET. Además, puede buscar ayuda de la comunidad Aspose.Finance en el[Foro de soporte](https://forum.aspose.com/c/finance/43).
## Importando espacios de nombres
Comencemos importando los espacios de nombres necesarios a su proyecto .NET:
## Paso 1: agregar el espacio de nombres Aspose.Finance
```csharp
using Aspose.Finance.Xbrl;
using System;
```
Este espacio de nombres contiene clases y métodos para trabajar con documentos y datos XBRL.
Ahora, dividamos el ejemplo proporcionado en varios pasos para comprender cómo agregar una referencia de esquema a un documento XBRL usando Aspose.Finance para .NET.
## Paso 1: Definir directorios de origen y de salida
```csharp
// Directorio fuente
string sourceDir = "Your Source Directory";
// Directorio de salida
string outputDir = "Your Output Directory";
```
 Reemplazar`"Your Source Directory"` y`"Your Output Directory"`con las rutas reales a sus directorios de origen y de salida respectivamente.
## Paso 2: crear un documento XBRL
```csharp
XbrlDocument document = new XbrlDocument();
```
Esto crea una nueva instancia del documento XBRL.
## Paso 3: acceder a instancias XBRL
```csharp
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
Esto recupera la colección de instancias XBRL del documento y le agrega una nueva instancia.
## Paso 4: agregar referencia de esquema
```csharp
SchemaRefCollection schemaRefs = xbrlInstance.SchemaRefs;
schemaRefs.Add(sourceDir + @"schema.xsd", "example", "http://ejemplo.com/xbrl/taxonomy");
```
 Esto agrega una referencia de esquema a la instancia XBRL. Reemplazar`"schema.xsd"` con el nombre real de su archivo de esquema,`"example"` con un prefijo adecuado, y`"http://example.com/xbrl/taxonomy"` con el URI del espacio de nombres de destino.
## Paso 5: guarde el documento
```csharp
document.Save(outputDir + @"document2.xbrl");
```
Esto guarda el documento XBRL modificado en el directorio de salida especificado.
## Conclusión
En conclusión, Aspose.Finance para .NET ofrece una solución sólida para manejar documentos y datos financieros en aplicaciones .NET. Si sigue los pasos descritos en este tutorial, puede integrar fácilmente Aspose.Finance en sus proyectos y manipular documentos XBRL de manera eficiente.
## Preguntas frecuentes
 (Preguntas frecuentes)
### 1. ¿Puedo utilizar Aspose.Finance para .NET sin licencia?
No, necesita una licencia válida para utilizar todas las funciones de Aspose.Finance para .NET. Sin embargo, puede obtener una licencia temporal para realizar pruebas.
### 2. ¿Es Aspose.Finance adecuado para crear software de contabilidad?
Sí, Aspose.Finance proporciona funcionalidades integrales para procesar datos financieros, lo que lo hace ideal para crear software de contabilidad y aplicaciones relacionadas.
### 3. ¿Dónde puedo encontrar soporte para Aspose.Finance?
Puede buscar ayuda de la comunidad Aspose.Finance en el foro de soporte oficial.
### 4. ¿Puedo personalizar el prefijo de referencia del esquema?
Sí, puede elegir un prefijo adecuado al agregar una referencia de esquema a un documento XBRL usando Aspose.Finance para .NET.
### 5. ¿Aspose.Finance admite otros formatos financieros además de XBRL?
Sí, Aspose.Finance admite varios formatos y estándares financieros, lo que permite una integración perfecta en diversas aplicaciones financieras.