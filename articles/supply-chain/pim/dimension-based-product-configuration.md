---
title: Konfiguracja produktu oparta na wymiarach
description: Konfiguracja produktu oparta na wymiarach to prosty sposób tworzenia wielu wariantów produktu z jednego produktu głównego i jego BOM.
author: cvocph
manager: AnnBe
ms.date: 11/03/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BOMConfigRule, BOMTable, ConfigChooseFromRoute, ConfigGroup, ConfigHierarchy, EcoResDimensionBasedConfiguration
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 19821
ms.assetid: 4db9890b-306b-4be7-ba98-3be2094d561f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: eb2690ec5296f65430268a211108551348a4a060
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "317023"
---
# <a name="dimension-based-product-configuration"></a>Konfiguracja produktu oparta na wymiarach

[!include [banner](../includes/banner.md)]

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
Naturalna sekwencja budowania modelu produktu dla produktu opartego na wymiarach rozpoczyna się od zdefiniowania konfiguracji odpowiednich grup. Należy upewnić się, że wszystkie produkty, które będą używane w BOM, zostały wydane firmie, dla której tworzony jest model produktu. Gdy te blok konstrukcyjne są na swoich miejscach, użytkownik może utworzyć BOM i przypisać grupy konfiguracji do wszystkich odpowiednich wierszy BOM. Kiedy BOM jest gotowy, można zdefiniować marszrutę konfiguracji dla uporządkowania grup konfiguracji we właściwej kolejności. [![Proces modelowania produktów opartych na wymiarach](./media/dimension-based-product-modeling-process-v1.png)](./media/dimension-based-product-modeling-process-v1.png) Jeżeli istnieją określone produkty z różnych grup konfiguracji, które muszą lub nie mogą być używane razem, można utworzyć reguły konfiguracji, które wymuszą relacje między tymi produktami. Po powiązaniu BOM z produktem głównym opartym na wymiarach za pomocą wersji BOM i po zatwierdzeniu oraz aktywowaniu jednego i drugiego, można utworzyć konfiguracje produktów i wprowadzić nazwę dla każdej konfiguracji. Konfiguracje mogą być definiowane zanim jakiekolwiek transakcje są generowane lub można to zrobić, gdy wystąpi potrzeba konkretnych konfiguracji.

### <a name="suggested-use"></a>Sugerowane zastosowanie

Technologia konfiguracji opartej na wymiarach najlepiej nadaje się do produktów ze ograniczoną zmiennością i kombinacją standardowych rozmiaru, koloru, stylu i konfiguracji wymiarów produktu, i jest ona nieodpowiednia do identyfikowania konkretnych wariantów produktów. Przykładem może być rower z konkretną wysokością ramy, średnicą koła i rytem hamulców oraz różnymi rodzajami przerzutek.

### <a name="next-step"></a>Następne kroki 

Poniżej znajduje się wykaz ośmiu przewodników po zadaniach w kolejności, w jakiej należy je ukończyć. 

1.  [Tworzenie produktu głównego opartego na wymiarach (przewodnik zadania)](tasks/create-dimension-based-product-master.md)
2.  [Zwolnienie produktu głównego opartego na wymiarach (przewodnik zadania)](tasks/release-dimension-based-product-master.md)
3.  [Wypełnianie podstawowych ustawień zrealizowanego produktu głównego (przewodnik zadania)](tasks/complete-basic-setup-released-product-master.md)
4.  [Definiowanie grupy konfiguracji (przewodnik zadania)](tasks/define-configuration-groups.md)
5.  [Tworzenie listy składowej (BOM) dla produktu głównego opartego na wymiarach (przewodnik zadania)](tasks/create-bill-materials-dimension-based-product-master.md)
6.  [Definiowanie marszrut konfiguracji (przewodnik zadania)](tasks/define-configuration-route.md)
7.  [Tworzenie reguł konfiguracji (przewodnik zadania)](tasks/create-configuration-rules.md)
8.  [Tworzenie konfiguracji opartych na wymiarach (przewodnik zadania)](tasks/create-dimension-based-configurations.md)

