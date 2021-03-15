---
title: Zmiana porządku sortowania dla podmiotów merchandisingowych
description: W tym temacie objaśniono koncepcje związane z kontrolowaniem kolejności wyświetlania dla różnych jednostek związanych z merchandisingiem w Dynamics 365 Commerce.
author: josaw1
manager: AnnBe
ms.date: 08/05/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: Category, Retail product hierarchy, Navigation hierarchy
audience: Application User, Merchandising manager, Catalog manager
ms.reviewer: josaw
ms.custom: 268444
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 694f95e274dc068cba02a2a519c1ce3ed186eaf0
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4976770"
---
# <a name="change-the-sort-order-for-merchandising-entities"></a>Zmiana porządku sortowania dla podmiotów merchandisingowych


[!include [banner](includes/banner.md)]

Detaliści uważają znajdowanie produktów za podstawowe narzędzie do wykrywania produktów na potrzeby interakcji z klientami we wszystkich kanałach. Klienci mogą łatwo odkrywać produkty, korzystając z różnych funkcji. Na przykład mogą przeglądać kategorie, wyszukiwać i filtrować.

W tym temacie objaśniono koncepcje związane z kontrolowaniem kolejności wyświetlania dla różnych jednostek związanych z merchandisingiem. Omówiono również sposób zmieniania kolejności sortowania.

## <a name="overview"></a>Przegląd

Obsługa sortowania różnych jednostek dotyczących merchandisingu została ulepszona. Ta obsługa jest teraz lepiej wyrównana z istniejącymi scenariuszami klientów, które wcześniej wymagały rozszerzeń od partnerów implementacji.

W wersjach Retail starszych niż wersja 10.0.5 kolejność sortowania kategorii w hierarchii nawigacji była alfabetyczna. Nowa funkcja niestandardowej kolejności sortowania umożliwia menedżerom ds. merchadisingu konfigurowanie kolejności sortowania różnych jednostek związanych z merchandisingiem dla wszystkich klientów końcowych. Do tych klientów należą: Centrala (HQ) i biura obsługi.

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

![Hierarchia produktów niestandardowo posortowana z wartościami ujemnymi](./media/RetailProductHierarchyCustomSortedWithNegativeValues.png)

![Zwolnione produkty według kategorii — sortowanie niestandardowe na podstawie hierarchii produktów](./media/ReleasedProductsByCategoryCustomSortedBasedOnRetailProductHierarchy.png)

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

![Niestandardowa hierarchia nawigacji kanału](./media/ChannelNavCustomSorted.png)

![Hierarchia nawigacji katalogu sortowanie niestandardowa na podstawie hierarchii nawigacji kanału](./media/CatalogNavHierarchyCustomSortedBasedOnChannelNav.png)

![Punkt sprzedaży z niestandardowymi kategoriami posortowanymi](./media/POSChannelCategoriesCustomSorted.png)

> [!NOTE]
> Domyślnie ta funkcja niestandardowego sortowania jest wyłączona. Aby dowiedzieć się, jak włączyć tę funkcję i inne funkcje, zobacz [Zarządzanie funkcjami](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/feature-management/feature-management-overview).


[!INCLUDE[footer-include](../includes/footer-banner.md)]