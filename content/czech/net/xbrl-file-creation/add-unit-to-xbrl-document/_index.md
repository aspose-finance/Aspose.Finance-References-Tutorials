---
title: Přidat jednotku do dokumentu XBRL
linktitle: Přidat jednotku do dokumentu XBRL
second_title: Aspose.Finance .NET API
description: Naučte se, jak snadno přidávat jednotky do dokumentů XBRL s Aspose.Finance pro .NET. Vylepšete své možnosti zpracování finančních dat ještě dnes!
type: docs
weight: 16
url: /cs/net/xbrl-file-creation/add-unit-to-xbrl-document/
---
Vítejte ve světě Aspose.Finance for .NET – vaší brány k efektivní manipulaci s finančními dokumenty v rámci aplikací .NET. Ať už vytváříte účetní software, nástroje pro finanční analýzu nebo jakoukoli jinou finanční aplikaci, Aspose.Finance pro .NET vás vybaví komplexní sadou funkcí, které zefektivní váš vývojový proces.
## Předpoklady
Než se ponoříme do využití síly Aspose.Finance pro .NET, ujistěte se, že máme připraveny nezbytné předpoklady:
### 1. Instalace sady Visual Studio
Ujistěte se, že máte v systému nainstalované Visual Studio. Pokud ne, můžete si jej stáhnout a nainstalovat z oficiálních stránek společnosti Microsoft.
### 2. Získejte licenci
 Chcete-li odemknout plný potenciál Aspose.Finance pro .NET, potřebujete platnou licenci. Licenci si můžete zakoupit od[tady](https://purchase.aspose.com/buy) nebo se rozhodnout pro dočasnou licenci pro testovací účely.
### 3. Stáhněte si Aspose.Finance pro .NET a použijte odkaz
 Stáhněte si knihovnu Aspose.Finance for .NET z[stránka vydání](https://releases.aspose.com/finance/net/) a odkazujte na něj ve svém projektu .NET.
### 4. Přístup k dokumentaci a podpoře
 Odkazovat na[dokumentace](https://reference.aspose.com/finance/net/)pro podrobné informace o využití Aspose.Finance pro .NET. Kromě toho můžete požádat o pomoc komunitu Aspose.Finance na[Fórum podpory](https://forum.aspose.com/c/finance/43).
## Import jmenných prostorů
Nyní importujme potřebné jmenné prostory do vašeho projektu .NET:
## Krok 1: Přidejte jmenný prostor Aspose.Finance
```csharp
using Aspose.Finance.Xbrl;
using System;
```
Tento jmenný prostor obsahuje třídy a metody nezbytné pro práci s dokumenty a daty XBRL.
Pojďme si uvedený příklad rozdělit do několika kroků, abychom pochopili, jak přidat jednotku do dokumentu XBRL pomocí Aspose.Finance for .NET.
## Krok 1: Definujte výstupní adresář
```csharp
// Výstupní adresář
string outputDir = "Your Output Directory";
```
 Nahradit`"Your Output Directory"` se skutečnou cestou k požadovanému výstupnímu adresáři.
## Krok 2: Vytvořte dokument XBRL
```csharp
XbrlDocument document = new XbrlDocument();
```
Tím se inicializuje nová instance dokumentu XBRL.
## Krok 3: Přístup k instancím XBRL
```csharp
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
Tím se načte kolekce instancí XBRL z dokumentu a přidá se do ní nová instance.
## Krok 4: Přidejte jednotku
```csharp
Unit unit = new Unit(UnitType.Measure);
unit.MeasureQualifiedNames.Add(new QualifiedName("USD", "iso4217", "http://www.xbrl.org/2003/iso4217"));
xbrlInstance.Units.Add(unit);
```
Tím se vytvoří nová měrná jednotka (v tomto případě USD) a přidá se do instance XBRL. Kód měny a URI jmenného prostoru můžete upravit podle potřeby.
## Krok 5: Uložte dokument
```csharp
document.Save(outputDir + @"document4.xbrl");
```
Tím se upravený dokument XBRL uloží do zadaného výstupního adresáře.
## Závěr
Na závěr, Aspose.Finance for .NET umožňuje vývojářům snadno manipulovat s finančními dokumenty a daty v rámci jejich aplikací .NET. Podle kroků uvedených v tomto kurzu můžete bez problémů integrovat Aspose.Finance for .NET do svých projektů a vylepšit jejich možnosti zpracování financí.
## Nejčastější dotazy
### 1. Mohu používat Aspose.Finance pro .NET bez licence?
Ne, k odemknutí všech funkcí Aspose.Finance for .NET je nutná platná licence. Pro testovací účely jsou však k dispozici dočasné licence.
### 2. Je Aspose.Finance for .NET vhodný pro vytváření účetního softwaru?
Ano, Aspose.Finance for .NET poskytuje robustní funkce přizpůsobené pro vytváření účetního softwaru a souvisejících finančních aplikací.
### 3. Kde najdu podporu pro Aspose.Finance pro .NET?
Na fóru podpory můžete požádat o pomoc komunitu Aspose.Finance.
### 4. Mohu upravit měrnou jednotku v dokumentu XBRL?
Ano, pomocí Aspose.Finance for .NET můžete vytvářet a přidávat vlastní měrné jednotky do dokumentů XBRL.
### 5. Podporuje Aspose.Finance for .NET více měn?
Ano, Aspose.Finance for .NET podporuje více měn, což umožňuje všestranné zpracování finančních dat.