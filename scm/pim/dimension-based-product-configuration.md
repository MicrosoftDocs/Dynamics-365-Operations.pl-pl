---
title: Konfiguracja produktu oparta na wymiarach
description: "Konfiguracja produktu oparta na wymiarach to prosty sposób tworzenia wielu wariantów produktu z jednego produktu głównego i jego BOM."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BOMConfigRule, BOMTable, ConfigChooseFromRoute, ConfigGroup, ConfigHierarchy, EcoResDimensionBasedConfiguration
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 19821
ms.assetid: 4db9890b-306b-4be7-ba98-3be2094d561f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: d13fc55342030d96d38f264f6bff9586832b4ab5
ms.contentlocale: pl-pl
ms.lasthandoff: 05/25/2017


---

# <a name="dimension-based-product-configuration"></a>Konfiguracja produktu oparta na wymiarach

[!include[banner](../includes/banner.md)]


Konfiguracja produktu oparta na wymiarach to prosty sposób tworzenia wielu wariantów produktu z jednego produktu głównego i jego BOM.

Konfiguracja produktów oparta na wymiarach jest jedną z trzech wbudowanych technologii konfiguracji produktów. Dwie pozostałe konfiguracje to wstępnie zdefiniowane warianty i konfiguracja oparta na ograniczeniach. Wszystkie trzy technologie używają produktu głównego jako punktu wyjścia i umożliwiają użytkownikowi tworzenie wielu wariantów dla jednego produktu głównego.

## <a name="key-concepts"></a>Podstawowe pojęcia
Podstawą konfiguracji opartej na wymiarach są następujące pojęcia:

-   Produkty główne
-   Konfiguracja wymiarów produktu
-   Grupy konfiguracji
-   Lista składowa (BOM)
-   Marszruta konfiguracji
-   Reguły konfiguracji

### <a name="product-masters"></a>Produkty główne

Produkt główny jest punktem wyjścia dla każdego procesu konfiguracji produktów. Konfiguracja produktu oparta na wymiarach wymaga produktu głównego z konkretną technologią konfiguracji i grupy wymiaru produktu zawierającej wymiar produktu konfigurowanego.

### <a name="configuration-product-dimension"></a>Konfiguracja wymiarów produktu

Wymiar konfiguracji produktu jest używany do identyfikacji wariantów produktów dla produktu głównego z technologią konfiguracji opartą na wymiarach. Wartość wymiaru konfiguracji jest określona przez użytkownika i powinna pomagać w identyfikowaniu poszczególnych kombinacji.

### <a name="configuration-groups"></a>Grupy konfiguracji

Grupy konfiguracji są określane w centralnym repozytorium i mogą być używane dla wszystkich modeli konfiguracji produktu opartych na wymiarach. Grupy konfiguracji są skojarzone z poszczególnymi wierszami BOM i spajają grupę wierszy, które wzajemnie się wykluczają. Oznacza to, że dla jednego wariantu produktu można wybrać tylko jeden wiersz w grupie.

### <a name="bill-of-materials-bom"></a>Lista składowa (BOM)

BOM odpowiada blokom konstrukcyjnym dla konfiguracji produktu opartej na wymiarach. Musi zawierać wszystkie różne produkty, które mogą być używane w dowolnym wariancie produktu. Każdy wiersz w BOM może się odwoływać do grupy konfiguracji. Jeśli wiersz nie odwołuje się do grupy konfiguracji, będzie on uwzględniony we wszystkich wariantach produktu.

### <a name="configuration-route"></a>Marszruta konfiguracji

Marszruta konfiguracji określa kolejność grup konfiguracji, w jakiej będą one wyświetlane użytkownikowi w procesie konfiguracji produktu.

### <a name="configuration-rules"></a>Reguły konfiguracji

Reguły konfiguracji stanowią mechanizm zapewniający, że produkt wchodzący w skład jednej grupy konfiguracji w BOM wymusza włączenia lub wyłączenia produktu w innej grupie konfiguracji w tym samym BOM.

## <a name="product-modeling-process"></a>Proces modelowania produktu
Naturalna sekwencja budowania modelu produktu dla produktu opartego na wymiarach rozpoczyna się od zdefiniowania konfiguracji odpowiednich grup. Należy upewnić się, że zostały zwolnione wszystkie produktów, które będą używane w BOM, do firmy, dla której tworzony jest model produktu. Gdy te blok konstrukcyjne są na swoich miejscach, użytkownik może utworzyć BOM i przypisać grupy konfiguracji do wszystkich odpowiednich wierszy BOM. Kiedy BOM jest gotowy, można zdefiniować marszrutę konfiguracji dla uporządkowania grup konfiguracji we właściwej kolejności. \[caption id="attachment\_282671" align="alignnone" width="1187"\][![Proces modelowania produktów opartych na wymiarach](./media/dimension-based-product-modeling-process-v1.png)](./media/dimension-based-product-modeling-process-v1.png) Proces modelowania produktów opartych na wymiarach\[/caption\] Jeśli istnieją pewne produkty z różnych grup konfiguracji, które muszą lub nie mogą być używane razem, można utworzyć reguły konfiguracji, które będą wymuszać relacje tych produktów. Po powiązaniu BOM z produktem głównym opartym na wymiarach za pomocą wersji BOM i po zatwierdzeniu oraz aktywowaniu jednego i drugiego, można utworzyć konfiguracje produktów i wprowadzić nazwę dla każdej konfiguracji. Konfiguracje mogą być definiowane zanim jakiekolwiek transakcje są generowane lub można to zrobić, gdy wystąpi potrzeba konkretnych konfiguracji.

### <a name="suggested-use"></a>Sugerowane zastosowanie

Technologia konfiguracji opartej na wymiarach najlepiej nadaje się do produktów ze ograniczoną zmiennością i kombinacją standardowych rozmiaru, koloru, stylu i konfiguracji wymiarów produktu, i jest ona nieodpowiednia do identyfikowania konkretnych wariantów produktów. Przykładem może być rower z konkretną wysokością ramy, średnicą koła i rytem hamulców oraz różnymi rodzajami przerzutek.




