---
title: Zarządzanie jednostką miary
description: W tej procedurze pokazano sposób definiowania jednostki miary, wprowadzania tłumaczenia i opisu jednostki oraz określania reguł konwersji względem powiązanych jednostek.
author: sorenva
manager: tfehr
ms.date: 07/08/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductMaintainWorkspace, EcoResProductOpenCasesFormPart, UnitOfMeasure, UnitOfMeasureReportingTranslation, UnitOfMeasureTranslation, UnitOfMeasureConversion, UnitOfMeasureConversionEditOrCreate, UnitOfMeasureLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: abc02c73ae36975fa4872d638fe53cbf0379d15d
ms.sourcegitcommit: 8a2127c5af6cdbda30ccc1f9bef9bd4ab61e9e50
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/18/2020
ms.locfileid: "3383672"
---
# <a name="manage-unit-of-measure"></a>Zarządzanie jednostką miary

[!include [banner](../../includes/banner.md)]

W tej procedurze pokazano sposób definiowania jednostki miary, wprowadzania tłumaczenia i opisu jednostki oraz określania reguł konwersji względem powiązanych jednostek. Można przejść tę procedurę przy użyciu danych firmy demonstracyjnej lub własnych danych.

1. Otwórz **Okienko nawigacji > Moduły > Informacje o zarządzaniu produktem > Produkty > Obsługa zwolnionego produktu**.
2. Kliknij opcję **Jednostki**.

## <a name="create-a-unit-of-measure"></a>Tworzenie jednostki miary
1. Kliknij przycisk **Nowy**.
2. W polu **Jednostka** wpisz wartość. Wprowadź identyfikator lub symbol, który ma być używany przy odwoływaniu się do jednostki miary.  
3. W polu **Opis** wpisz wartość. Wprowadź opisową nazwę jednostki miary w wersji językowej systemu.  
4. W polu **Klasa jednostek** wybierz opcję. Klasa jednostki określa grupę logiczną, taką jak obszar, masa lub ilość, której jednostka miary jest częścią.  
5. W polu **Dokładność po przecinku** wpisz liczbę. Określ liczbę miejsc po przecinku, do jakiej musi zostać zaokrąglona przekonwertowana jednostka miary po wykonaniu na niej obliczeń.  
6. Kliknij przycisk **Zapisz**.

## <a name="define-unit-translations"></a>Definiowanie tłumaczeń jednostek
1. W **okienku akcji** kliknij pozycję **Teksty jednostek**.
2. Kliknij przycisk **Nowy**. Użyj opisu jednostki w celu utworzenia tłumaczenie identyfikatora lub symbolu reprezentującego jednostkę miary z przeznaczeniem do używania w dokumentach zewnętrznych w językach określonych odbiorców lub dostawców.  
3. W polu **Język** wprowadź lub wybierz wartość.
4. W polu **Tekst** wpisz wartość.
5. Kliknij przycisk **Zapisz**.
6. Zamknij stronę.
7. W **okienku akcji** kliknij pozycję **Przetłumaczone opisy jednostki**.
8. Kliknij przycisk **Nowy**. Utwórz opisy jednostki miary w różnych językach.  
9. W polu **Język** wprowadź lub wybierz wartość.
10. W polu **Opis** wpisz wartość.
11. Kliknij przycisk **Zapisz**.
12. Zamknij stronę.

## <a name="define-unit-conversion-rules"></a>Definiowanie reguł konwersji jednostek
1. W **okienku akcji** kliknij pozycję **Konwersje jednostek**. Zdefiniuj reguły konwersji jednostki miary na i z innych jednostek miary w wybranej klasie jednostek.  
2. Kliknij przycisk **Nowy** aby otworzyć rozwijane okno dialogowe.
3. W polu **Współczynnik** wpisz liczbę. Wskaźnik konwersji między jednostkami źródłową i docelową. Na przykład współczynnik konwersji centymetra na metr wynosi 100, ponieważ w jednym metrze jest 100 centymetrów.  
4. W polu **Do jednostki** wprowadź lub wybierz wartość.
5. W polu **Zaokrąglanie** wybierz opcję. Określ sposób zaokrąglania skonwertowanej wartości.  
6. Kliknij przycisk **OK**.
7. Zamknij stronę.

