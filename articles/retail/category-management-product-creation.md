---
title: Zarządzanie kategoriami produktów i produktami sieci sprzedaży
description: W tym temacie opisano, jak kierownicy ds. merchadisingu mogą używać kategorii produktów sieci sprzedaży do zarządzania relacjami między hierarchiami produktów sieci sprzedaży a szczegółami zwolnionych produktów.
author: ashishmsft
manager: AnnBe
ms.date: 10/23/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: ''
ms.assetid: c7ed2ba5-87c6-4d99-9728-2a83e6d95ca9
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2017-09-01
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 0bcc5989edd9913fce414c0c24068f111d8c1aeb
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "344692"
---
# <a name="manage-retail-product-categories-and-products"></a>Zarządzanie kategoriami produktów i produktami sieci sprzedaży

[!include [banner](./includes/banner.md)]

W tym temacie opisano poszerzony sposób zarządzania kategoriami produktów sieci sprzedaży i produktami w programie Microsoft Dynamics 365 for Retail. Ulepszenia umożliwiają menedżerom ds. merchadisingu wyświetlanie struktury właściwości produktów, która jest wspólna dla hierarchii produktów sieci sprzedaży i informacji o zwolnionych produktach.

Aby dowiedzieć się więcej o zarządzaniu kategoriami produktów sieci sprzedaży, w obszarze roboczym **Zarządzanie kategoriami i produktami** wybierz kafelek **Hierarchia produktów sieci sprzedaży**.

Zwróć uwagę na ulepszoną strukturę na stronie **Hierarchia produktów sieci sprzedaży**. W poprzednich wersjach aplikacji Retail właściwości produktów były podzielone na *podstawowe właściwości produktów* i *właściwości produktów sieci sprzedaży* na podstawie zakresu ich zastosowania. Właściwości produktów sieci sprzedaży są *globalne* pod względem zakresu ich zastosowania. Inaczej mówiąc, dla danej właściwości produktu sieci sprzedaży ta sama wartość jest współdzielona we wszystkich firmach. Z kolei podstawowe właściwości produktów są *specyficzne dla firmy*. Inaczej mówiąc, dana podstawowa właściwość produktu może mieć różne wartości dla różnych firm, w zależności od wymagań biznesowych konkretnej firmy.

W ulepszonej strukturze kategorii produktów sieci sprzedaży właściwości produktów są logicznie rozdzielone na podstawie ich zastosowania w grupie, tak aby odzwierciedlić strukturę formularza szczegółów zwolnionych produktów.

![Pola pogrupowane w oparciu o zakres stosowania właściwości](media/NoticeGroupingOfFieldsBasedOnTheirScope.PNG)

Można przełączyć się między zarządzaniem właściwościami specyficznymi dla firmy we wszystkich firmach a zarządzaniem nimi dla określonej firmy.

Aby zarządzać właściwościami we wszystkich firmach, wybierz opcję **Wyświetl dla wszystkich firm** (lub **Edytuj dla wszystkich firm**).

![Wyświetl/edytuj dla wszystkich firm](media/ToggleBackToEditForSpecificLegalEntity.PNG)

Aby zarządzać właściwościami określonej firmy, wybierz opcję **Wyświetl dla określonej firmy** (lub **Edytuj dla określonej firmy**).

![Wyświetl/edytuj dla określonej firmy](media/ToggleToEditForAllLegalEntities.PNG)

Ponadto w ulepszonej strukturze kategorii produktów sieci sprzedaży kierownik ds. merchadisingu może zdefiniować domyślne wartości dodatkowego zestawu właściwości produktów na poziomie indywidualnej kategorii. Wtedy podczas tworzenia produktów będą one dziedziczyły domyślne wartości w oparciu o ich powiązanie z konkretną kategorią w hierarchii produktów sieci sprzedaży. Te dziedziczone właściwości produktów można również modyfikować dla każdego produktu, aby spełnić indywidualne wymagania biznesowe.

## <a name="selecting-properties-to-update-products-on-the-retail-product-hierarchy-page"></a>Wybieranie właściwości w celu aktualizowania produktów na stronie hierarchii produktów sieci sprzedaży

Nowej ulepszonej struktury można używać dla właściwości produktów w celu określania, które zaktualizowane właściwości produktów mają być rozpowszechniane do powiązanych produktów. Na stronie **Hierarchia produktów sieci sprzedaży** w okienku akcji wybierz opcję **Kategoria**, a następnie wybierz opcję **Aktualizuj produkty**, aby otworzyć okno dialogowe **Aktualizuj produkty**.

![Okno dialogowe Aktualizuj produkty](media/NewUpdateProductsEnhancedView.PNG)
