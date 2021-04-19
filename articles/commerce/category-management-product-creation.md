---
title: Zarządzanie kategoriami produktów i produktami
description: W tym temacie opisano, jak kierownicy ds. merchadisingu mogą używać kategorii produktów do zarządzania relacjami między hierarchiami produktów Commerce a szczegółami zwolnionych produktów.
author: ashishmsft
ms.date: 10/23/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResCategorySearchList, EcoResAttribute, COODualUseCategories, EcoResProductCategory, EcoResCategoryAddProduct, EcoResAttributeValue
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: c7ed2ba5-87c6-4d99-9728-2a83e6d95ca9
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2017-09-01
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 678561856fbb5514ff954363a767091edac6dee2
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5794380"
---
# <a name="manage-product-categories-and-products"></a>Zarządzanie kategoriami produktów i produktami

[!include [banner](./includes/banner.md)]

W tym temacie opisano poszerzony sposób zarządzania kategoriami produktów sieci sprzedaży i produktami w usłudze Dynamics 365 Commerce. Ulepszenia umożliwiają menedżerom ds. merchadisingu wyświetlanie struktury właściwości produktów, która jest wspólna dla hierarchii produktów i informacji o zwolnionych produktach.

Aby dowiedzieć się więcej o zarządzaniu kategoriami produktów, w obszarze roboczym **Zarządzanie kategoriami i produktami** wybierz kafelek **Hierarchia produktów Commerce**.

Zwróć uwagę na ulepszoną strukturę na stronie **Hierarchia produktów Commerce**. W poprzednich wersjach aplikacji właściwości produktów były podzielone na *podstawowe właściwości produktów* i *właściwości produktów sieci sprzedaży* na podstawie zakresu ich zastosowania. Właściwości produktów sieci sprzedaży są *globalne* pod względem zakresu ich zastosowania. Inaczej mówiąc, dla właściwości danego produktu ta sama wartość jest współdzielona we wszystkich firmach. Z kolei podstawowe właściwości produktów są *specyficzne dla firmy*. Inaczej mówiąc, dana podstawowa właściwość produktu może mieć różne wartości dla różnych firm, w zależności od wymagań biznesowych konkretnej firmy.

W ulepszonej strukturze kategorii produktów właściwości produktów są logicznie rozdzielone na podstawie ich zastosowania w grupie, tak aby odzwierciedlić strukturę formularza szczegółów zwolnionych produktów.

![Pola pogrupowane w oparciu o zakres stosowania właściwości](media/NoticeGroupingOfFieldsBasedOnTheirScope.PNG)

Można przełączyć się między zarządzaniem właściwościami specyficznymi dla firmy we wszystkich firmach a zarządzaniem nimi dla określonej firmy.

Aby zarządzać właściwościami we wszystkich firmach, wybierz opcję **Wyświetl dla wszystkich firm** (lub **Edytuj dla wszystkich firm**).

![Wyświetl/edytuj dla wszystkich firm](media/ToggleBackToEditForSpecificLegalEntity.PNG)

Aby zarządzać właściwościami określonej firmy, wybierz opcję **Wyświetl dla określonej firmy** (lub **Edytuj dla określonej firmy**).

![Wyświetl/edytuj dla określonej firmy](media/ToggleToEditForAllLegalEntities.PNG)

Ponadto w ulepszonej strukturze kategorii produktów kierownik ds. merchadisingu może zdefiniować domyślne wartości dodatkowego zestawu właściwości produktów na poziomie indywidualnej kategorii. Wtedy podczas tworzenia produktów będą one dziedziczyły domyślne wartości w oparciu o ich powiązanie z konkretną kategorią w hierarchii produktów. Te dziedziczone właściwości produktów można również modyfikować dla każdego produktu, aby spełnić indywidualne wymagania biznesowe.

## <a name="selecting-properties-to-update-products-on-the-commerce-product-hierarchy-page"></a>Wybieranie właściwości w celu aktualizowania produktów na stronie hierarchii produktów Commerce

Nowej ulepszonej struktury można używać dla właściwości produktów w celu określania, które zaktualizowane właściwości produktów mają być rozpowszechniane do powiązanych produktów. Na stronie **Hierarchia produktów Commerce** w okienku akcji wybierz opcję **Kategoria**, a następnie wybierz opcję **Aktualizuj produkty**, aby otworzyć okno dialogowe **Aktualizuj produkty**.

![Okno dialogowe Aktualizuj produkty](media/NewUpdateProductsEnhancedView.PNG)


[!INCLUDE[footer-include](../includes/footer-banner.md)]