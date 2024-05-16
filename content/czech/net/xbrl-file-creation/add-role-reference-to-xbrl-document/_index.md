---
title: Přidejte odkaz na roli do dokumentu XBRL
linktitle: Přidejte odkaz na roli do dokumentu XBRL
second_title: Aspose.Finance .NET API
description: Naučte se přidávat odkazy na role do dokumentů XBRL pomocí Aspose.Finance for .NET. Zjednodušte finanční výkaznictví ve svých aplikacích .NET pomocí tohoto kurzu.
type: docs
weight: 14
url: /cs/net/xbrl-file-creation/add-role-reference-to-xbrl-document/
---
XBRL (eXtensible Business Reporting Language) se stal standardem pro výměnu obchodních informací, zejména ve finančním výkaznictví. Aspose.Finance for .NET zjednodušuje práci s dokumenty XBRL v aplikacích .NET. Tento tutoriál vás provede procesem přidání odkazu na roli do dokumentu XBRL pomocí Aspose.Finance for .NET.
## Předpoklady
Než začneme, ujistěte se, že máte následující předpoklady:
### 1. Nainstalujte Aspose.Finance pro .NET
Ujistěte se, že máte ve svém vývojovém prostředí nainstalovaný Aspose.Finance for .NET. Pokud jste tak ještě neučinili, stáhněte si jej z[vydání](https://releases.aspose.com/finance/net/) a postupujte podle pokynů k instalaci.
### 2. Nastavte své vývojové prostředí
Ujistěte se, že máte funkční vývojové prostředí pro vývoj .NET. To zahrnuje kompatibilní IDE, jako je Visual Studio a framework .NET nainstalovaný ve vašem systému.
## Import jmenných prostorů
Začněte importem potřebných jmenných prostorů do vaší aplikace .NET, abyste získali přístup k funkcím, které poskytuje Aspose.Finance pro .NET.
```csharp
using Aspose.Finance.Xbrl;
using System;
using Aspose
.Finance.Xbrl.Roles;
```
## Krok 1: Definujte zdrojové a výstupní adresáře
```csharp
string sourceDir = "Your Source Directory";
string outputDir = "Your Output Directory";
```
 Nahradit`"Your Source Directory"` a`"Your Output Directory"` s cestami ke zdrojovým a výstupním adresářům.
## Krok 2: Vytvořte dokument a instanci XBRL
```csharp
XbrlDocument document = new XbrlDocument();
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
Inicializujte dokument XBRL a instanci, se kterou chcete pracovat.
## Krok 3: Přidejte odkaz na schéma
```csharp
SchemaRefCollection schemaRefs = xbrlInstance.SchemaRefs;
schemaRefs.Add(sourceDir + @"schema.xsd", "example", "http://example.com/xbrl/taxonomy");
```
Přidejte odkaz na schéma k instanci XBRL, uveďte cestu k souboru schématu a určete podrobnosti o jmenném prostoru.
## Krok 4: Načtěte typ role a přidejte odkaz na roli
```csharp
SchemaRef schema = schemaRefs[0];
RoleType roleType = schema.GetRoleTypeByURI("http://abc.com/role/link1");
if (roleType != null)
{
    RoleReference roleReference = new RoleReference(roleType);
    xbrlInstance.RoleReferences.Add(roleReference);
}
```
Načtěte typ role pomocí jeho URI a přidejte odkaz na roli do instance XBRL.
## Krok 5: Uložte dokument
```csharp
document.Save(outputDir + @"document7.xbrl");
```
Uložte dokument XBRL do výstupního adresáře.
## Závěr
Přidání odkazů na role do dokumentů XBRL je klíčové pro definování rolí různých prvků v dokumentu. Aspose.Finance for .NET poskytuje přímý způsob, jak tento úkol splnit, a umožňuje vývojářům efektivně pracovat s dokumenty XBRL v jejich aplikacích .NET.
## Nejčastější dotazy
### Mohu používat Aspose.Finance pro .NET s jakoukoli aplikací .NET?
Ano, Aspose.Finance for .NET je kompatibilní s jakoukoli aplikací .NET, včetně aplikací ASP.NET, WinForms a Console.
### Je Aspose.Finance for .NET k použití zdarma?
 Aspose.Finance for .NET je komerční knihovna. Můžete si stáhnout bezplatnou zkušební verzi, abyste mohli vyhodnotit její funkce, a licence lze zakoupit od[tady](https://purchase.aspose.com/buy).
### Podporuje Aspose.Finance for .NET jiné formáty finančního výkaznictví kromě XBRL?
Aspose.Finance for .NET se primárně zaměřuje na funkce související s XBRL. Aspose však nabízí další knihovny pro práci s různými finančními formáty.
### Jak mohu získat podporu pro Aspose.Finance pro .NET?
 Podporu pro Aspose.Finance pro .NET můžete získat prostřednictvím[Fórum](https://forum.aspose.com/c/finance/43)kde můžete klást otázky a komunikovat s ostatními uživateli a pracovníky podpory.
### Mohu získat dočasnou licenci pro Aspose.Finance pro .NET?
 Ano, dočasné licence pro Aspose.Finance pro .NET jsou k dispozici pro testovací účely. Můžete získat jeden[tady](https://purchase.aspose.com/temporary-license/).