---
title: Wymiary produktu
description: "Istnieją cztery wymiary produktu — kolor, konfiguracja, rozmiar i styl. Wymiary produktu łączy się w grupy wymiarów, a następnie przypisuje grupy wymiarów do produktów głównych. Kombinacje wymiarów produktu decydują o definicjach wariantów produktu."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: EcoResProductDimension, EcoResProductDimensionGroup, EcoResProductMasterDimension, RetailEcoResColor, RetailEcoResSize, RetailEcoResStyle
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 19171
ms.assetid: 81fa3709-4ab8-4fbf-9806-359892a05985
ms.search.region: Global
ms.search.industry: Retail
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 8854ab94a71cc363bcd073d2df47bc01a243b6cd
ms.lasthandoff: 03/31/2017


---

# <a name="product-dimensions"></a>Wymiary produktu

Istnieją cztery wymiary produktu — kolor, konfiguracja, rozmiar i styl. Wymiary produktu łączy się w grupy wymiarów, a następnie przypisuje grupy wymiarów do produktów głównych. Kombinacje wymiarów produktu decydują o definicjach wariantów produktu.

Wymiary produktu to cechy, które służą do określenia wariantu produktu. Kombinacje wymiarów produktu służą do definiowania wariantów produktu. Należy zdefiniować co najmniej jeden wymiar produktu dla produktu głównego w celu utworzenia wariantu produktu.
Warianty produktu
----------------

Warianty produktu są również określane jako elementy. Towar to produkt materialny, który nie jest usługą. Jest również możliwe określenie produktu głównego z typem usługi. Za pomocą typu Usługa można określić warianty produktu, które zawierają usługi. Na przykład można określić produkt główny dla pracy w zakresie doradztwa i warianty produktu dla pracy wykonywanej przez starszych konsultantów i młodszych konsultantów.

## <a name="product-dimensions"></a>Wymiary produktu
Dostępne są następujące wymiary produktu: Konfiguracja, kolor, rozmiar i styl. Wariant produktu mogą być generowane na podstawie wartości wymiaru produktu.

Wymiary produktu wartości, takie jak rozmiar, kolor i styl mogą być tworzone na **rozmiar**, **kolor** i **styl** stron, które mogą być dostępne w następujących lokalizacjach: **zarządzanie informacjami o produktach**&gt;**instalacji**&gt;**wymiaru i wariantu grup**&gt;**rozmiary/kolory/style**. Wartości wymiaru produktu dla wymiaru konfiguracji są zwykle tworzone za pomocą konfiguratora produktów lub konfiguratora opartego na wymiarach. Wymiary produktu mogą być również tworzone i obsługiwane na stronie **Wymiary produktu**, która jest dostępna z następujących miejsc:
-   Kliknij **zarządzanie informacjami o produktach**&gt;**produkty**&gt;**produktów głównych**. Na **w okienku akcji**, kliknij przycisk **wymiary produktu**.
-   Kliknij **zarządzanie informacjami o produktach**&gt;**produkty**&gt;**wszystkie produkty i produkty główne**. Wybierz produkt główny. Na **w okienku akcji**, kliknij przycisk **wymiary produktu**.
-   Kliknij **zarządzanie informacjami o produktach**&gt;**zwolnionych produktów**. Wybierz produkt główny. Na **w okienku akcji**, kliknij przycisk **produktu**. W grupie **Produkt główny** kliknij **Wymiary produktu**.

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




