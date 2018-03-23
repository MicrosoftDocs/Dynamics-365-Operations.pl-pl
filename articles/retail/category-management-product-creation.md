---
title: "Zarządzanie kategoriami produktów"
description: "W tym temacie opisano, jak kierownicy ds. merchadisingu mogą używać kategorii produktów sieci sprzedaży do zarządzania relacjami między hierarchiami produktów sieci sprzedaży a szczegółami zwolnionych produktów."
author: ashishmsft
manager: AnnBe
ms.date: 10/23/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 
ms.assetid: c7ed2ba5-87c6-4d99-9728-2a83e6d95ca9
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2017-09-01
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 25fa39dc81fc721d7593a25a102ce47041ebc5f0
ms.openlocfilehash: 4b7ef962b777a31e1da238a8ec1be9a42ec5bb5f
ms.contentlocale: pl-pl
ms.lasthandoff: 03/13/2018

---


# <a name="enhanced-product-and-category-management"></a>Ulepszone zarządzanie kategoriami i produktami

[!include[banner](./includes/banner.md)]

W tym temacie opisano poszerzony sposób zarządzania kategoriami produktów sieci sprzedaży i produktami w programie Dynamics 365 for Retail. Te ulepszenia umożliwiają menedżerom ds. merchadisingu wyświetlanie wspólnej struktury właściwości produktów między hierarchiami produktów detalicznych a informacjami o zwolnionych produktach.

Aby dowiedzieć się więcej o zarządzaniu kategoriami produktów sieci sprzedaży, w obszarze roboczym **Zarządzanie kategoriami i produktami** przejdź do sekcji **Hierarchia produktów sieci sprzedaży** i zwróć uwagę na ulepszoną strukturę znajdującą się na stronie **Kategoria produktów sieci sprzedaży**.

![Obszar roboczy Zarządzanie kategoriami i produktami](media/LaunchRetailProductHierarchy.png)

W poprzednich wersjach właściwości produktów były podzielone na **podstawowe właściwości produktów** i **właściwości produktów sieci sprzedaży** na podstawie zakresu ich zastosowania. **Właściwości produktów sieci sprzedaży** były *globalne* ze względu na zakres zastosowania, co oznacza, że dla danej **właściwości produktu sieci sprzedaży** ta sama wartość jest wspólna we wszystkich firmach. **Podstawowe właściwości produktów** były *specyficzne dla firmy*. Inaczej mówiąc, dana **podstawowa właściwość produktu** może mieć różne wartości dla różnych firm w zależności od wymagań biznesowych.

W ulepszonej strukturze kategorii produktów sieci sprzedaży właściwości produktów są logicznie rozdzielone na podstawie ich zastosowania w grupie, tak aby odzwierciedlić strukturę formularza szczegółów zwolnionych produktów.

![Grupowanie pól w oparciu o ich zakres stosowania](media/NoticeGroupingOfFieldsBasedOnTheirScope.PNG)

Można przełączyć się między zarządzaniem właściwościami specyficznymi dla firmy we wszystkich firmach i zarządzaniem nimi dla określonej firmy. W tym celu wybierz opcję **Wyświetl/edytuj dla wszystkich firm** lub **Wyświetl/edytuj dla określonej firmy**.

![Przełączanie widoku między jedną a wszystkimi firmami](media/ToggleBackToEditForSpecificLegalEntity.PNG)

![Przełączanie widoku między jedną a wszystkimi firmami](media/ToggleToEditForAllLegalEntities.PNG)  

W porównaniu z poprzednimi wersjami w nowej strukturze kategorii produktów sieci sprzedaży kierownik ds. merchadisingu może zdefiniować domyślne wartości dodatkowego zestawu właściwości produktów na poziomie indywidualnej kategorii. Podczas tworzenia produktu te domyślne właściwości produktu są dziedziczone przez produkt w oparciu o jego powiązanie z konkretną kategorią w hierarchii produktów sieci sprzedaży. Te dziedziczone właściwości produktów można również modyfikować dla każdego produktu, aby spełnić indywidualne wymagania biznesowe.

## <a name="select-properties-to-update-products-from-the-retail-product-category-form"></a>Wybieranie właściwości do aktualizacji produktu z formularza kategorii produktów sieci sprzedaży 
 
Tej nowej ulepszonej struktury można używać dla właściwości produktów w celu określania, które zaktualizowane właściwości produktów mają być rozpowszechniane do powiązanych produktów. 

![Nowy, ulepszony widok aktualizacji produktów](media/NewUpdateProductsEnhancedView.PNG) 

Menedżerowie ds. merchandisingu mogą zmodyfikować odziedziczone właściwości produktów dla każdego produktu, aby spełnić indywidualne wymagania biznesowe.


