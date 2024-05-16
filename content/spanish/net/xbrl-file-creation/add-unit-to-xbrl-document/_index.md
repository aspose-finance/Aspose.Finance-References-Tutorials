---
title: Agregar unidad al documento XBRL
linktitle: Agregar unidad al documento XBRL
second_title: API de Aspose.Finance .NET
description: Aprenda a agregar unidades a documentos XBRL sin esfuerzo con Aspose.Finance para .NET. ¡Mejore sus capacidades de procesamiento de datos financieros hoy!
type: docs
weight: 16
url: /es/net/xbrl-file-creation/add-unit-to-xbrl-document/
---
Bienvenido al mundo de Aspose.Finance para .NET: su puerta de entrada a la manipulación eficiente de documentos financieros dentro de aplicaciones .NET. Ya sea que esté creando software de contabilidad, herramientas de análisis financiero o cualquier otra aplicación financiera, Aspose.Finance para .NET le proporciona un conjunto completo de funciones para agilizar su proceso de desarrollo.
## Requisitos previos
Antes de profundizar en cómo aprovechar el poder de Aspose.Finance para .NET, asegurémonos de contar con los requisitos previos necesarios:
### 1. Instalación de Visual Studio
Asegúrese de tener Visual Studio instalado en su sistema. De lo contrario, puede descargarlo e instalarlo desde el sitio web oficial de Microsoft.
### 2. Obtener una licencia
 Para desbloquear todo el potencial de Aspose.Finance para .NET, necesita una licencia válida. Puede adquirir una licencia en[aquí](https://purchase.aspose.com/buy) u optar por una licencia temporal con fines de prueba.
### 3. Descargue y haga referencia a Aspose.Finance para .NET
 Descargue la biblioteca Aspose.Finance para .NET desde[página de lanzamientos](https://releases.aspose.com/finance/net/) y haga referencia a él en su proyecto .NET.
### 4. Acceda a la documentación y al soporte
 Referirse a[documentación](https://reference.aspose.com/finance/net/)para obtener información detallada sobre cómo utilizar Aspose.Finance para .NET. Además, puede buscar ayuda de la comunidad Aspose.Finance en el[Foro de soporte](https://forum.aspose.com/c/finance/43).
## Importando espacios de nombres
Ahora, importemos los espacios de nombres necesarios a su proyecto .NET:
## Paso 1: agregar el espacio de nombres Aspose.Finance
```csharp
using Aspose.Finance.Xbrl;
using System;
```
Este espacio de nombres contiene clases y métodos esenciales para trabajar con documentos y datos XBRL.
Dividamos el ejemplo proporcionado en varios pasos para comprender cómo agregar una unidad a un documento XBRL usando Aspose.Finance para .NET.
## Paso 1: definir el directorio de salida
```csharp
// Directorio de salida
string outputDir = "Your Output Directory";
```
 Reemplazar`"Your Output Directory"` con la ruta real al directorio de salida deseado.
## Paso 2: crear un documento XBRL
```csharp
XbrlDocument document = new XbrlDocument();
```
Esto inicializa una nueva instancia del documento XBRL.
## Paso 3: acceder a instancias XBRL
```csharp
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
Esto recupera la colección de instancias XBRL del documento y le agrega una nueva instancia.
## Paso 4: agregar unidad
```csharp
Unit unit = new Unit(UnitType.Measure);
unit.MeasureQualifiedNames.Add(new QualifiedName("USD", "iso4217", "http://www.xbrl.org/2003/iso4217"));
xbrlInstance.Units.Add(unit);
```
Esto crea una nueva unidad de medida (en este caso, USD) y la agrega a la instancia XBRL. Puede ajustar el código de moneda y el URI del espacio de nombres según sea necesario.
## Paso 5: guarde el documento
```csharp
document.Save(outputDir + @"document4.xbrl");
```
Esto guarda el documento XBRL modificado en el directorio de salida especificado.
## Conclusión
En conclusión, Aspose.Finance para .NET permite a los desarrolladores manipular sin esfuerzo documentos y datos financieros dentro de sus aplicaciones .NET. Si sigue los pasos descritos en este tutorial, podrá integrar perfectamente Aspose.Finance para .NET en sus proyectos y mejorar sus capacidades de procesamiento financiero.
## Preguntas frecuentes
### 1. ¿Puedo utilizar Aspose.Finance para .NET sin licencia?
No, se requiere una licencia válida para desbloquear todas las funciones de Aspose.Finance para .NET. Sin embargo, hay licencias temporales disponibles para fines de prueba.
### 2. ¿Es Aspose.Finance para .NET adecuado para crear software de contabilidad?
Sí, Aspose.Finance para .NET proporciona funcionalidades sólidas diseñadas para crear software de contabilidad y aplicaciones financieras relacionadas.
### 3. ¿Dónde puedo encontrar soporte para Aspose.Finance para .NET?
Puede buscar ayuda de la comunidad Aspose.Finance en el foro de soporte.
### 4. ¿Puedo personalizar la unidad de medida en un documento XBRL?
Sí, puede crear y agregar unidades de medida personalizadas a documentos XBRL utilizando Aspose.Finance para .NET.
### 5. ¿Aspose.Finance para .NET admite varias monedas?
Sí, Aspose.Finance para .NET admite múltiples monedas, lo que permite un procesamiento versátil de datos financieros.