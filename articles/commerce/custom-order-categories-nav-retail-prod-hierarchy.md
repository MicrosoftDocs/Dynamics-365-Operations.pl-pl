---
title: Zmiana porządku sortowania dla podmiotów merchandisingowych
description: W tym artykule objaśniono koncepcje związane z kontrolowaniem kolejności wyświetlania dla różnych jednostek związanych z merchandisingiem w Dynamics 365 Commerce.
author: josaw1
ms.date: 08/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: Category, Retail product hierarchy, Navigation hierarchy
audience: Application User, Merchandising manager, Catalog manager
ms.reviewer: josaw
ms.custom: 268444
ms.search.region: global
ms.search.industry: Retail
ms.author: brshoo
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 80586597f4f60476b341e4cf1cfd90f3681e15c0
ms.sourcegitcommit: 52e31b1ef2b3ed8675de931d06090cd57e057fc2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9265844"
---
# <a name="change-the-sort-order-for-merchandising-entities"></a>Zmiana porządku sortowania dla podmiotów merchandisingowych


[!Include [banner](includes/banner.md)]

Detaliści uważają znajdowanie produktów za podstawowe narzędzie do wykrywania produktów na potrzeby interakcji z klientami we wszystkich kanałach. Istnieje kilka funkcji, które mogą ułatwić klientom znajdowanie produktów. Na przykład klienci mogą przeglądać kategorie, wyszukiwać i filtrować.

W tym artykule objaśniono koncepcje związane z kontrolowaniem kolejności wyświetlania dla różnych jednostek związanych z merchandisingiem. Omówiono również sposób zmieniania kolejności sortowania.

## <a name="overview"></a>Omówienie

W handlu sortowanie różnych jednostek związanych z merchadisingiem jest zgodne z istniejącymi scenariuszami klientów i nie wymaga już rozszerzeń ze strony partnerów wdrożeniowych.

W wersji Commerce 10.0.5 i wcześniejszych kolejność sortowania kategorii w hierarchii nawigacji była alfabetyczna. Obecna funkcja niestandardowego porządku sortowania umożliwia menedżerom ds. sprzedaży konfigurowanie kolejności sortowania dla różnych jednostek związanych z merchandisingiem we wszystkich klientach końcowych. Do tych klientów należą: Centrala (HQ) i biura obsługi.

## <a name="configure-the-display-order-for-categories-in-the-product-hierarchy"></a>Skonfiguruj kolejność wyświetlania dla kategorii w hierarchii produktów

Aby można było wykonać tę procedurę, w środowisku muszą być zainstalowane dane pokazowe.

1. Wybierz kolejno opcje **Retail i Commerce \> Produkty i kategorie \> Hierarchia produktów Commerce**.
2. Kliknij opcję **Edytuj hierarchię kategorii**.
3. Kliknij przycisk **Edytuj**.
4. W drzewie rozwiń **WSZYSTKO \> Sporty akcji**.
5. W drzewie rozwiń **WSZYSTKO \> Sporty drużynowe**.
6. W polu **Kolejność wyświetlania** wpisz liczbę. (Liczba może być ujemna.)
7. Powtórz kroki od 4 do 6 dla wszystkich dodatkowych kategorii, których kolejność chcesz zmienić.

Kolejność wyświetlania dla hierarchii nawigacji kanału zostanie odzwierciedlona w HQ dla hierarchii produktów handlu i zwolnionych produktów według kategorii.

![Hierarchia produktów niestandardowo posortowana z wartościami ujemnymi.](./media/RetailProductHierarchyCustomSortedWithNegativeValues.png)

![Zwolnione produkty według kategorii — sortowanie niestandardowe na podstawie hierarchii produktów.](./media/ReleasedProductsByCategoryCustomSortedBasedOnRetailProductHierarchy.png)

## <a name="configure-the-display-order-for-categories-in-the-channel-navigation-hierarchy"></a>Skonfiguruj kolejność wyświetlania dla kategorii w hierarchii kategorii nawigacji

Aby można było wykonać tę procedurę, w środowisku muszą być zainstalowane dane pokazowe.

1. Przejdź do **Retail i Commerce \> Produkty i kategorie \> Kategorie nawigacji kanału**.
2. Z listy wybierz hierarchię **nawigacji Moda**.
3. Kliknij opcję **Edytuj hierarchię kategorii**.
4. Kliknij przycisk **Edytuj**.
5. W drzewie wybierz **Moda \> Moda damska \> Buty damskie**.
6. W polu **Kolejność wyświetlania** wpisz liczbę.
7. W drzewie wybierz **Moda \> Moda damska \> Bluzki**.

Analogicznie, można określić kolejność sortowania dla podkategorii.

8. W drzewie wybierz **Moda \> Moda męska \> Koszule codzienne**.
9. W polu **Kolejność wyświetlania** wpisz liczbę.
10. W drzewie wybierz **Moda \> Moda męska \> Płaszcze i kurtki**.
11. W polu **Kolejność wyświetlania** wpisz liczbę.
12. Powtórz dla wszystkich dodatkowych kategorii, których kolejność chcesz zmienić.

Kolejność wyświetlania dla hierarchii nawigacji kanału jest odzwierciedlona w HQ, katalogu i kanałach.

![Niestandardowa hierarchia nawigacji kanału.](./media/ChannelNavCustomSorted.png)

![Hierarchia nawigacji katalogu sortowanie niestandardowa na podstawie hierarchii nawigacji kanału.](./media/CatalogNavHierarchyCustomSortedBasedOnChannelNav.png)

![Punkt sprzedaży z niestandardowymi kategoriami posortowanymi.](./media/POSChannelCategoriesCustomSorted.png)

> [!NOTE]
> Domyślnie funkcja **Włącz kolejność wyświetlania jednostek merchandisingowych** jest wyłączona. Użyj [funkcji zarządzania,](../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) aby włączyć tę funkcję. Po włączeniu funkcji uruchom zadanie CDX **Konfiguracja globalna -1110** z harmonogramu dystrybucji.
> Jeśli kolejność kategorii w punkcie sprzedaży nie została zaktualizowana, ponownie aktywuj urządzenie. Informacje o kategorii są pobierane po aktywacji urządzenia, więc może być konieczne ponowne pobranie informacji o kategorii ze zaktualizowanymi kolejnościami wyświetlania. 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
