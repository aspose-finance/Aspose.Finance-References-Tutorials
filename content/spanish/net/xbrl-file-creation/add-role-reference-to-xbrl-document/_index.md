---
title: Agregar referencia de rol al documento XBRL
linktitle: Agregar referencia de rol al documento XBRL
second_title: API de Aspose.Finance .NET
description: Aprenda a agregar referencias de roles a documentos XBRL usando Aspose.Finance para .NET. Simplifique los informes financieros en sus aplicaciones .NET con este tutorial.
type: docs
weight: 14
url: /es/net/xbrl-file-creation/add-role-reference-to-xbrl-document/
---
XBRL (eXtensible Business Reporting Language) se ha convertido en un estándar para el intercambio de información empresarial, particularmente en informes financieros. Aspose.Finance para .NET simplifica el trabajo con documentos XBRL en aplicaciones .NET. Este tutorial lo guiará a través del proceso de agregar una referencia de rol a un documento XBRL usando Aspose.Finance para .NET.
## Requisitos previos
Antes de comenzar, asegúrese de tener los siguientes requisitos previos:
### 1. Instale Aspose.Finance para .NET
Asegúrese de tener Aspose.Finance para .NET instalado en su entorno de desarrollo. Si aún no lo has hecho, descárgalo desde[lanzamientos](https://releases.aspose.com/finance/net/) y siga las instrucciones de instalación.
### 2. Configure su entorno de desarrollo
Asegúrese de tener un entorno de desarrollo funcional para el desarrollo .NET. Esto incluye un IDE compatible como Visual Studio y el marco .NET instalado en su sistema.
## Importar espacios de nombres
Comience importando los espacios de nombres necesarios en su aplicación .NET para acceder a la funcionalidad proporcionada por Aspose.Finance para .NET.
```csharp
using Aspose.Finance.Xbrl;
using System;
using Aspose
.Finance.Xbrl.Roles;
```
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
## Paso 4: recuperar el tipo de rol y agregar la referencia del rol
```csharp
SchemaRef schema = schemaRefs[0];
RoleType roleType = schema.GetRoleTypeByURI("http://abc.com/role/link1");
if (roleType != null)
{
    RoleReference roleReference = new RoleReference(roleType);
    xbrlInstance.RoleReferences.Add(roleReference);
}
```
Recupere el tipo de rol usando su URI y agregue una referencia de rol a la instancia XBRL.
## Paso 5: guardar el documento
```csharp
document.Save(outputDir + @"document7.xbrl");
```
Guarde el documento XBRL en el directorio de salida.
## Conclusión
Agregar referencias de roles a documentos XBRL es crucial para definir los roles de varios elementos dentro del documento. Aspose.Finance para .NET proporciona una forma sencilla de realizar esta tarea, permitiendo a los desarrolladores trabajar de manera eficiente con documentos XBRL en sus aplicaciones .NET.
## Preguntas frecuentes
### ¿Puedo usar Aspose.Finance para .NET con cualquier aplicación .NET?
Sí, Aspose.Finance para .NET es compatible con cualquier aplicación .NET, incluidas ASP.NET, WinForms y aplicaciones de consola.
### ¿Aspose.Finance para .NET es de uso gratuito?
 Aspose.Finance para .NET es una biblioteca comercial. Puede descargar una versión de prueba gratuita para evaluar sus funciones y se pueden comprar licencias en[aquí](https://purchase.aspose.com/buy).
### ¿Aspose.Finance para .NET admite otros formatos de informes financieros además de XBRL?
Aspose.Finance para .NET se centra principalmente en la funcionalidad relacionada con XBRL. Sin embargo, Aspose ofrece otras bibliotecas para trabajar con diferentes formatos financieros.
### ¿Cómo puedo obtener soporte para Aspose.Finance para .NET?
 Puede obtener soporte para Aspose.Finance para .NET a través de[foro](https://forum.aspose.com/c/finance/43)donde puede hacer preguntas e interactuar con otros usuarios y personal de soporte.
### ¿Puedo obtener una licencia temporal de Aspose.Finance para .NET?
 Sí, las licencias temporales de Aspose.Finance para .NET están disponibles con fines de prueba. Puedes obtener uno[aquí](https://purchase.aspose.com/temporary-license/).