---
title: Agregar referencia de rol ARC al documento XBRL
linktitle: Agregar referencia de rol ARC al documento XBRL
second_title: API de Aspose.Finance .NET
description: Aprenda a manipular eficientemente documentos XBRL utilizando Aspose.Finance para .NET. Agregue referencias de roles ARC sin esfuerzo con una guía paso a paso.
type: docs
weight: 10
url: /es/net/xbrl-file-creation/add-arc-role-reference-to-xbrl-document/
---
## Introducción
En el mundo de la gestión y la presentación de informes de datos financieros, el lenguaje eXtensible Business Reporting Language (XBRL) desempeña un papel crucial. Estandariza la forma en que se comunica e intercambia la información financiera, garantizando coherencia, precisión y eficiencia. Sin embargo, manipular documentos XBRL, especialmente cuando incorporan roles y referencias específicas, requiere una comprensión matizada de los mecanismos subyacentes. Este tutorial se centra en una de esas tareas: agregar una referencia de función ARC a un documento XBRL usando Aspose.Finance para .NET.
## Requisitos previos
Antes de sumergirse en el tutorial, asegúrese de tener los siguientes requisitos previos:
### Configuración del entorno
1.  Instale Aspose.Finance para .NET: descargue e instale la biblioteca Aspose.Finance para .NET desde[lanzamientos](https://releases.aspose.com/finance/net/).
   
2. Entorno de desarrollo: configure su entorno de desarrollo con Visual Studio o cualquier otro IDE preferido.
## Importar espacios de nombres
Asegúrese de importar los espacios de nombres necesarios en su código C#:
```csharp
using Aspose.Finance.Xbrl;
using System;
```
## Paso 1: Definir directorios de origen y de salida
Antes de continuar, especifique los directorios de origen y de salida donde se ubicarán y guardarán sus archivos XBRL, respectivamente.
```csharp
// Directorio fuente
string sourceDir = "Your Source Directory";
// Directorio de salida
string outputDir = "Your Output Directory";
```
## Paso 2: crear un documento XBRL
 Crear una instancia de`XbrlDocument` objeto para trabajar con datos XBRL.
```csharp
XbrlDocument document = new XbrlDocument();
```
## Paso 3: Acceda a la colección XbrlInstance
Acceda a la colección de instancias XBRL dentro del documento.
```csharp
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
```
## Paso 4: agregar XbrlInstance
Agregue una nueva instancia XBRL a la colección.
```csharp
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
## Paso 5: agregar referencia de esquema
Incluya una referencia de esquema en la instancia XBRL, especificando el directorio de origen, el prefijo del espacio de nombres y el URI.
```csharp
SchemaRefCollection schemaRefs = xbrlInstance.SchemaRefs;
schemaRefs.Add(sourceDir + @"schema.xsd", "example", "http://ejemplo.com/xbrl/taxonomy");
```
## Paso 6: recuperar ArcroleType
 recuperar el`ArcroleType` basado en un URI específico.
```csharp
SchemaRef schema = schemaRefs[0];
ArcroleType arcroleType = schema.GetArcroleTypeByURI("http://abc.com/arcrole/footnote-test");
```
## Paso 7: agregar ArcroleReference
 Si el`ArcroleType` se encuentra, cree un`ArcroleReference` y agréguelo a las referencias de arcroles de la instancia XBRL.
```csharp
if (arcroleType != null)
{
    ArcroleReference arcroleReference = new ArcroleReference(arcroleType);
    xbrlInstance.ArcroleReferences.Add(arcroleReference);
}
```
## Paso 8: guarde el documento
Guarde el documento XBRL modificado en el directorio de salida especificado.
```csharp
document.Save(outputDir + @"document8.xbrl");
```
## Conclusión
En este tutorial, exploramos cómo agregar una referencia de función ARC a un documento XBRL usando Aspose.Finance para .NET. Si sigue estas instrucciones paso a paso y aprovecha las capacidades de Aspose.Finance, podrá administrar y manipular de manera eficiente los datos XBRL para cumplir con sus requisitos específicos.
## Preguntas frecuentes
### ¿Qué es XBRL?
XBRL significa eXtensible Business Reporting Language, un lenguaje estandarizado para la comunicación electrónica de datos comerciales y financieros.
### ¿Por qué es importante XBRL?
XBRL garantiza coherencia, precisión y eficiencia en el intercambio y análisis de información financiera, beneficiando a reguladores, analistas y empresas.
### ¿Puede Aspose.Finance manejar tareas XBRL complejas?
Sí, Aspose.Finance ofrece una funcionalidad sólida para trabajar con documentos XBRL, incluido el manejo de tareas complejas como referencias de roles y gestión de taxonomía.
### ¿Aspose.Finance es compatible con otras bibliotecas .NET?
Sí, Aspose.Finance se integra perfectamente con otras bibliotecas .NET, brindando un amplio soporte para la manipulación y la generación de informes de datos financieros.
### ¿Dónde puedo encontrar soporte adicional para Aspose.Finance?
 Para soporte adicional visite el[Página de soporte de Aspose.Finance](https://forum.aspose.com/c/finance/43).