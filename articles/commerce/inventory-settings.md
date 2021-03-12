---
title: Zastosuj ustawienia zapasów
description: W tym temacie opisano ustawienia zapasów oraz sposób ich stosowania w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 77a3bde12fd047e15d7730903416cdb5263a8cd9
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4972816"
---
# <a name="apply-inventory-settings"></a>Zastosuj ustawienia zapasów

[!include [banner](includes/banner.md)]

W tym temacie opisano ustawienia zapasów oraz sposób ich stosowania w Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Omówienie

Ustawienia zapasów określają, czy zapasy powinny być sprawdzane przed dodaniem produktów do koszyka. Definiują również komunikaty promocyjne dotyczące zapasów, takie jak „w magazynie” i „zostało tylko parę sztuk”. Te ustawienia gwarantują, że produkt nie może zostać zakupiony, jeśli nie jest w stanie zapasów.

Dynamics 365 Commerce umożliwia oszacowanie dostępnych zapasów dla produktów. Aby uzyskać informacje dotyczące sposobu obliczania szacowanej dostępności zapasów, należy zapoznać się z tematem [Oblicz dostępność zapasów dla kanałów sieci sprzedaży](calculated-inventory-retail-channels.md).

W konstruktorze witryn Commerce można definiować progi i zakresy zapasów dla produktu lub kategorii. Określają one, czy zapasy mogą być klasyfikowane jako w magazynie, małe ilości czy wyprzedane. Aby uzyskać szczegółowe informacje, należy zapoznać się z tematem [Konfigurowanie buforów zapasów i poziomów zapasów](inventory-buffers-levels.md).

> [!NOTE]
> Obsługa progów i zakresów zapasów jest dostępna w wersji Dynamics 365 Commerce 10.0.12.

## <a name="inventory-settings"></a>Ustawienia zapasów

W module Commerce ustawienia zapasów są definiowane w **Ustawienia witryny \> Rozszerzenia \> Zarządzanie zapasami** w konstruktorze witryn. Istnieją cztery ustawienia zapasów, z których jedna jest przestarzała (przestarzałe):

- **Włącz sprawdzanie zapasów w aplikacji** — to ustawienie powoduje włączenie sprawdzania zapasów produktów. Pole zakupu, koszyk i pobieranie w modułach sklepów będą sprawdzać magazyn produktów i zezwalać na dodanie produktu do koszyka tylko wtedy, gdy zapasy są dostępne.
- **Poziom zapasów na podstawie** — to ustawienie określa sposób obliczania poziomów zapasów. Dostępne wartości to **Razem dostępne**, **Dostępne fizycznie** i **Próg wyprzedania**. W Commerce można zdefiniować próg i zakresy zapasów dla każdego produktu i kategorii. Interfejsy API magazynu zwracają informacje o zapasach produktów dla zarówno właściwości **Razem dostępne**, jak i właściwości **Fizycznie dostępne**. Detalista decyduje, czy wartość **Razem dostępne** lub **Fizycznie dostępne** powinna być używana do określenia licznika zapasów i odpowiednich zakresów w Stanach zapasów i poza magazynem.

    Wartość **Próg wyprzedania** ustawienia **Poziom zapasów na podstawie** jest starsza (przestarzała), nieaktualna. Po wybraniu tej opcji Inwentaryzacja jest określana na podstawie wyników wartości **Razem dostępne**, ale próg jest definiowany przez ustawienie wartości liczbowej **Próg wyprzedania**, które zostało opisane w dalszej części tego pola. To ustawienie wartości progowej ma zastosowanie w odniesieniu do wszystkich produktów w witrynie handlu elektronicznego. Jeśli zapasy są poniżej numeru progowego, produkt jest uważany za zapasy. W przeciwnym razie zostanie uznane za dostępne w magazynie. Możliwości wartości **Próg wyprzedania** są ograniczone i nie zaleca się używania jej w wersji 10.0.12 lub nowszej.

- **Zakresy zapasów** — to ustawienie definiuje zakresy zapasów, które są wyświetlane w wiadomościach w modułach witryny. Ma to zastosowanie tylko wtedy, gdy wybrano wartość **Razem Dostępne** lub **Dostępne Fizycznie** dla poziomu **Poziom zapasów w oparciu o ustawienie**. Dostępne wartości to **Wszystkie**, **Mała ilość i wyprzedane** oraz **Wyprzedane**.

    - Po wybraniu opcji **Wszystkie** zostaną wyświetlone komunikaty dotyczące wszystkich zakresów magazynowych (komunikat dostępny) do wykroczenia zapasów (komunikat „wyprzedane”).
    - Po wybraniu opcji **Mała ilość i wyprzedane** zostaną wyświetlone komunikaty dotyczące wszystkich zakresów magazynowych poza zakresem dostępnym (komunikat „Dostępny”).
    - W przypadku wybrania **Wyprzedane** będzie wyświetlany tylko komunikat „wyprzedane”.

- **Próg wyprzedania** — to stare ustawienie numeryczne zacznie obowiązywać tylko wtedy, gdy wartość **Próg wyprzedania** zostanie wybrana dla ustawienia **Poziom zapasów na podstawie**.

> [!IMPORTANT] 
> Te ustawienia są dostępne w wydaniu Dynamics 365 Commerce 10.0.12. W przypadku aktualizacji ze starszej wersji Dynamics 365 Commerce należy ręcznie zaktualizować plik appsettings.json. Aby uzyskać instrukcje dotyczące aktualizowania pliku appsettings.json, zajrzyj do [Aktualizacje zestawu SDK i biblioteki modułów](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).

## <a name="modules-that-use-inventory-settings"></a>Moduły korzystające z ustawień zapasów

Pole Kup, Wishlist, selektor sklepu, koszyk i ikony koszyka Użyj ustawień zapasów, aby wyświetlić zakresy i komunikaty magazynowe.

Poniższy obraz przedstawia przykład strony ze szczegółowymi informacjami o produkcie (PDP), która pokazuje komunikat w magazynie („Dostępny”).

![Przykład modułu PDP, który ma komunikat w magazynie](./media/pdp-InStock.png)

Poniższy obraz pokazuje przykład PDP, który wyświetla komunikat „Wyprzedano”.

![Przykład modułu PDP, który ma komunikat o wyprzedaniu](./media/pdp-outofstock.png)

Poniższy obraz pokazuje przykład wózka z komunikatem o stanie magazynowym („Dostępne”).

![Przykład modułu koszyka, który ma komunikat w magazynie](./media/cart-instock.png)

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie biblioteki modułów](starter-kit-overview.md)

[Konfigurowanie buforów zapasów i poziomów zapasów](inventory-buffers-levels.md)

[Moduł koszyka](add-cart-module.md)

[Moduł pola zakupu](add-buy-box.md)

[Strony i moduły zarządzania kontem](account-management.md)

[Moduł wyboru sklepu](store-selector.md)

[Aktualizacje zestawu SDK i biblioteki modułów](e-commerce-extensibility/sdk-updates.md)
