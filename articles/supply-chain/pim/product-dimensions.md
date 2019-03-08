---
title: Wymiary produktu
description: Istnieją cztery wymiary produktu — Kolor, Konfiguracja, Rozmiar i Styl. Wymiary produktu łączy się w grupy wymiarów, a następnie przypisuje grupy wymiarów do produktów głównych. Kombinacje wymiarów produktu decydują o definicjach wariantów produktu.
author: cvocph
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDimension, EcoResProductDimensionGroup, EcoResProductMasterDimension, RetailEcoResColor, RetailEcoResSize, RetailEcoResStyle
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 19171
ms.assetid: 81fa3709-4ab8-4fbf-9806-359892a05985
ms.search.region: Global
ms.search.industry: Retail
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ccb9d47bf6f081dbcc9590bddd4516cf7385ec23
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "363299"
---
# <a name="product-dimensions"></a>Wymiary produktu

[!include [banner](../includes/banner.md)]

[!include [Retail name](../includes/retail-name.md)]

Istnieją cztery wymiary produktu — Kolor, Konfiguracja, Rozmiar i Styl. Wymiary produktu łączy się w grupy wymiarów, a następnie przypisuje grupy wymiarów do produktów głównych. Kombinacje wymiarów produktu decydują o definicjach wariantów produktu.

Wymiary produktu to cechy, które służą do określenia wariantu produktu. Kombinacje wymiarów produktu służą do definiowania wariantów produktu. Należy zdefiniować co najmniej jeden wymiar produktu dla produktu głównego w celu utworzenia wariantu produktu.
Warianty produktu
----------------

Warianty produktu są również określane jako elementy. Towar to produkt materialny, który nie jest usługą. Istnieje również możliwość zdefiniowania produktu głównego typu Usługa. Za pomocą typu Usługa można określić warianty produktu, które zawierają usługi. Na przykład można określić produkt główny dla pracy w zakresie doradztwa i warianty produktu dla pracy wykonywanej przez starszych konsultantów i młodszych konsultantów.

## <a name="product-dimensions"></a>Wymiary produktu
Dostępne są następujące wymiary produktu: Konfiguracja, Kolor, Rozmiar i Styl. Wariant produktu może być generowany na podstawie wartości w wymiarach produktu.

Wartości wymiarów produktu, takie jak Rozmiar, Kolor i Styl, można tworzyć na stronach **Rozmiar**, **Kolor** i **Styl**, które można otworzyć z następujących lokalizacji: **Zarządzanie informacjami o produktach** &gt; **Ustawienia** &gt; **Grupy wymiarów i wariantów** &gt; **Rozmiary/Kolory/Style**. Wartości wymiaru produktu dla wymiaru konfiguracji są zwykle tworzone za pomocą konfiguratora produktów lub konfiguratora opartego na wymiarach. Wymiary produktu mogą być również tworzone i obsługiwane na stronie **Wymiary produktu**, która jest dostępna z następujących miejsc:
-   Kliknij kolejno opcje **Zarządzanie informacjami o produktach** &gt; **Produkty** &gt; **Produkty główne**. W **okienku akcji** kliknij pozycję **Wymiary produktu**.
-   Kliknij kolejno opcje **Zarządzanie informacjami o produktach** &gt; **Produkty** &gt; **Wszystkie produkty i produkty główne**. Wybierz produkt główny. W **okienku akcji** kliknij pozycję **Wymiary produktu**.
-   Kliknij kolejno opcje **Zarządzanie informacjami o produktach** &gt; **Zwolnione produkty**. Wybierz produkt główny. W **okienku akcji** kliknij pozycję **Produkt**. W grupie **Produkt główny** kliknij **Wymiary produktu**.

Liczba wariantów, które można utworzyć dla towaru jest ograniczona przez liczbę kombinacji wymiarów produktu.

| **Wskazówka**                                                                                                                                              |
|------------------------------------------------------------------------------------------------------------------------------------------------------|
| Jeśli produkt jest używany, na przykład, w wierszu zamówienia, należy wybrać wymiary produktu do zdefiniowania wariantu produktu, który ma być używany. |

## <a name="example"></a>Przykład
Firma sprzedaje jeansy. Dla towaru — jeansów — istnieją wymiary Kolor i Rozmiar. Jeansy są sprzedawane w trzech różnych kolorach i sześciu rozmiarach. Kolory to niebieski, czarny, brązowy Rozmiary: XS, S, M, L, XL, XXL Nie wszystkie rozmiary są dostępne w trzech kolorach. Jeżeli wszystkie kombinacje byłyby dostępne, istniałoby 18 różnych typów jeansów. W tym przykładzie utworzono tylko dziewięć następujących kombinacji wariantu produktu.

| Kolor | Rozmiar |
|-------|------|
| Niebieski  | XS   |
| Niebieski  | S    |
| Niebieski  | P    |
| Czarny | P    |
| Czarny | L    |
| Czarny | XL   |
| Brązowy | W    |
| Brązowy | XL   |
| Brązowy | XXL  |





