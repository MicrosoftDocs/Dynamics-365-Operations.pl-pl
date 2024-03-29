---
title: Stosowanie ustawień jednostki miary
description: W tym artykule opisano ustawienia jednostki miary oraz sposób ich stosowania w systemie Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 04/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.custom: ''
ms.assetid: ''
ms.search.industry: ''
ms.openlocfilehash: 7a7be6395a8bfce38e84f850bd792f358941c18a
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9275579"
---
# <a name="apply-unit-of-measure-settings"></a>Stosowanie ustawień jednostki miary

[!include [banner](includes/banner.md)]

W tym artykule opisano ustawienia jednostki miary oraz sposób ich stosowania w systemie Microsoft Dynamics 365 Commerce.

Produkt może być sprzedawany w różnych jednostkach, na przykład „sztuka”, „para” i „tuzin”. W centrali Commerce może być zdefiniowana jednostka miary sprzedaży dla produktu i pokazywana w witrynie handlu elektronicznego. Jeśli na przykład sprzedawca detaliczny sprzedaje produkt zarówno pojedynczo, jak i w tuzinach, dostępne jednostki miary mogą być pokazywane razem z innymi informacjami o produkcie.

W przykładzie na poniższej ilustracji jednostka miary sprzedaży **szt.** (sztuka) została skonfigurowana dla produktu w centrali Commerce.

![Przykład produktu ze skonfigurowaną jednostką miary w centrali Commerce.](./media/Productunit-headquarters.PNG)

> [!NOTE]
> Obsługa stosowania i pokazywania jednostki miary jest dostępna od wersji 10.0.19 systemu Commerce.

## <a name="unit-of-measure-settings"></a>Ustawienia jednostki miary

Ustawienia wyświetlania jednostki miary są definiowane w konstruktorze witryn Commerce, na ekranie **Ustawienia witryny \> Rozszerzenia \> Wyświetl jednostkę miary produktów**. Dostępne są trzy obsługiwane ustawienia:

- **Nie wyświetlaj** — po wybraniu tego ustawienia witryna handlu elektronicznego nie będzie wyświetlać jednostki miary produktu. To zachowanie jest zachowaniem domyślnym.
- **Wyświetl podczas kupowania produktu** — gdy to ustawienie jest zaznaczone, jednostka miary jest wyświetlana na stronach szczegółów produktu, koszyka, realizacji zamówienia, historii zamówień i szczegółów zamówienia.
- **Wyświetl podczas przeglądania i kupowania produktu** — gdy to ustawienie jest zaznaczone, jednostka miary jest wyświetlana podczas kupowania produktów, a także podczas przeglądania produktów. W ramach tego zachowania jednostki miary są pokazywane w wynikach wyszukiwania i modułach kolekcji produktów.

> [!IMPORTANT]
> Ustawienia wyświetlania jednostek miary są dostępne od wersji 10.0.19 systemu Commerce. W przypadku aktualizacji ze starszej wersji Commerce należy ręcznie zaktualizować plik appsettings.json. Aby uzyskać instrukcje, zobacz [Aktualizacje zestawu SDK i biblioteki modułów](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).

## <a name="modules-that-use-unit-of-measure-settings"></a>Moduły korzystające z ustawień jednostki miary

Moduły, w których są używane ustawienia jednostki miary, to między innymi pole zakupu, lista życzeń, ikona koszyka, ikona koszyka, kontener wyników wyszukiwania, kolekcja produktów, realizacja zamówienia i szczegóły zamówienia.

Na przykładzie na poniższej ilustracji na stronie szczegółów produktu (PDP) jest pokazana jednostka miary (**szt.**) produktu.

![Przykład PDP z jednostką miary.](./media/Productunit-PDP.png)

Na przykładzie na poniższej ilustracji w module kolekcji produktów jest pokazana jednostka miary (**szt.**) produktu.

![Przykład modułu kolekcji produktów z jednostką miary.](./media/Productunit-productcollection.png)

## <a name="additional-resources"></a>Dodatkowe zasoby

[Przegląd biblioteki modułów](starter-kit-overview.md)

[Moduł koszyka](add-cart-module.md)

[Moduł pola zakupu](add-buy-box.md)

[Strony i moduły zarządzania kontem](account-management.md)

[Aktualizacje zestawu SDK i biblioteki modułów](e-commerce-extensibility/sdk-updates.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
