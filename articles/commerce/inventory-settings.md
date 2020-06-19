---
title: Zastosuj ustawienia zapasów
description: W tym temacie opisano ustawienia zapasów oraz sposób ich stosowania w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 06/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 7fc81c190806a0bdb50569f526589cfa1808ce0c
ms.sourcegitcommit: 2683aacb426bfb3b541637edf1f8ec2d6cb5a745
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/01/2020
ms.locfileid: "3417445"
---
# <a name="apply-inventory-settings"></a>Zastosuj ustawienia zapasów

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

W tym temacie opisano ustawienia zapasów oraz sposób ich stosowania w Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Omówienie

Ustawienia zapasów określają, czy zapasy powinny być sprawdzane przed dodaniem produktów do koszyka. Definiują również komunikaty promocyjne dotyczące zapasów, takie jak „w magazynie” i „zostało tylko parę sztuk”. Te ustawienia gwarantują, że produkt nie może zostać zakupiony, jeśli nie jest w stanie zapasów.

Dynamics 365 Commerce umożliwia oszacowanie dostępnych zapasów dla produktów. Aby uzyskać informacje dotyczące sposobu obliczania szacowanej dostępności zapasów, należy zapoznać się z tematem [Oblicz dostępność zapasów dla kanałów sieci sprzedaży](calculated-inventory-retail-channels.md).

W konstruktorze witryn Commerce można definiować progi i zakresy zapasów dla produktu lub kategorii. Określają one, czy zapasy mogą być klasyfikowane jako w magazynie, małe ilości czy wyprzedane. Aby uzyskać szczegółowe informacje, należy zapoznać się z tematem [Konfigurowanie buforów zapasów i poziomów zapasów](inventory-buffers-levels.md).

## <a name="inventory-settings"></a>Ustawienia zapasów

W module Commerce ustawienia zapasów są definiowane w **Ustawienia witryny \> Rozszerzenia \> Zarządzanie zapasami** w konstruktorze witryn. Istnieją cztery ustawienia zapasów, z których jedna jest przestarzała (przestarzałe):

- **Włączanie sprawdzania zapasów w aplikacji** — to ustawienie powoduje włączenie sprawdzania zapasów produktów. Pole zakupu, koszyk i pobieranie w modułach sklepów będą sprawdzać magazyn produktów i zezwalać na dodanie produktu do koszyka tylko wtedy, gdy zapasy są dostępne.
- **Poziom zapasów na podstawie** — to ustawienie określa sposób obliczania poziomów zapasów. Dostępne wartości to **Razem dostępne**, **Dostępne fizycznie** i **Próg wyprzedania**. W Commerce można zdefiniować próg i zakresy zapasów dla każdego produktu i kategorii. Interfejsy API magazynu zwracają informacje o zapasach produktów dla zarówno właściwości **Razem dostępne**, jak i właściwości **Fizycznie dostępne**. Detalista decyduje, czy wartość **Razem dostępne** lub **Fizycznie dostępne** powinna być używana do określenia licznika zapasów i odpowiednich zakresów w Stanach zapasów i poza magazynem.

    Wartość **Próg wyprzedania** ustawienia **Poziom zapasów na podstawie** jest starsza (przestarzała), nieaktualna. Po wybraniu tej opcji Inwentaryzacja jest określana na podstawie wyników wartości **Razem dostępne**, ale próg jest definiowany przez ustawienie wartości liczbowej **Próg wyprzedania**, które zostało opisane w dalszej części tego pola. To ustawienie progu ma zastosowanie w odniesieniu do wszystkich produktów w witrynie handlu elektronicznego. Jeśli zapasy są poniżej numeru progowego, produkt jest uważany za zapasy. W przeciwnym razie zostanie uznane za dostępne w magazynie. Możliwości wartości **Próg wyprzedania** są ograniczone i nie zaleca się używania jej w wersji 10.0.12 lub nowszej.

- **Zakresy zapasów** — to ustawienie definiuje zakresy zapasów, które są wyświetlane w wiadomościach w modułach witryny. Ma to zastosowanie tylko wtedy, gdy wybrano wartość **Razem Dostępne** lub **Dostępne Fizycznie** dla poziomu **Poziom zapasów w oparciu o ustawienie**. Dostępne wartości to **Wszystkie**, **Mała ilość i wyprzedane** oraz **Wyprzedane**.

    - Po wybraniu opcji **Wszystkie** zostaną wyświetlone komunikaty dotyczące wszystkich zakresów magazynowych (komunikat dostępny) do wykroczenia zapasów (komunikat „wyprzedane”).
    - Po wybraniu opcji **Mała ilość i wyprzedane** zostaną wyświetlone komunikaty dotyczące wszystkich zakresów magazynowych poza zakresem dostępnym (komunikat „Dostępny”).
    - W przypadku wybrania **Wyprzedane** będzie wyświetlany tylko komunikat „wyprzedane”.

- **Próg wyprzedania** — to stare ustawienie numeryczne zacznie obowiązywać tylko wtedy, gdy wartość **Próg wyprzedania** zostanie wybrana dla ustawienia **Poziom zapasów na podstawie**.

## <a name="modules-that-use-inventory-settings"></a>Moduły korzystające z ustawień zapasów

Pole Kup, Wishlist, selektor sklepu, koszyk i ikony koszyka Użyj ustawień zapasów, aby wyświetlić zakresy i komunikaty magazynowe.

Poniższy obraz przedstawia przykład strony ze szczegółowymi informacjami o produkcie (PDP), która pokazuje komunikat w magazynie („Dostępny”).

![Przykład modułu PDP, który ma komunikat w magazynie](./media/pdp-InStock.png)

Poniższy obraz pokazuje przykład PDP, który wyświetla komunikat „Wyprzedano”.

![Przykład modułu PDP, który ma komunikat o wyprzedaniu](./media/pdp-outofstock.png)

Poniższy obraz pokazuje przykład wózka z komunikatem o stanie magazynowym („Dostępne”).

![Przykład modułu koszyka, który ma komunikat w magazynie](./media/cart-instock.png)

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie zestawu początkowego](starter-kit-overview.md)

[Konfigurowanie buforów zapasów i poziomów zapasów](inventory-buffers-levels.md)

[Moduł koszyka](add-cart-module.md)

[Moduł pola zakupu](add-buy-box.md)

[Strony i moduły zarządzania kontem](account-management.md)

[Moduł wyboru sklepu](store-selector.md)
