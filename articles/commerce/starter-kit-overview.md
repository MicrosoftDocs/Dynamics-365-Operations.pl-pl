---
title: Przegląd biblioteki modułów
description: W tym temacie omówiono bibliotekę modułów Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 09/15/2020
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 94ff18fc34fbfbaee434db12f0d0bc8bb7042c2f
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2022
ms.locfileid: "7985766"
---
# <a name="module-library-overview"></a>Przegląd biblioteki modułów

[!include [banner](includes/banner.md)]

W tym temacie omówiono bibliotekę modułów Microsoft Dynamics 365 Commerce.

Biblioteka modułów Dynamics 365 Commerce to zbiór modułów, za pomocą których można utworzyć witrynę sieci Web e-Commerce. Moduły mają aspekty interfejsu użytkownika (UI) i aspekty zachowania funkcjonalnego.

Motywy mogą być stosowane do modułów w bibliotece modułów, aby zmieniać ich wygląd i działanie. W motywach używane są kaskadowe arkusze stylów (CSS). Motyw fikcyjnej witryny e-Commerce o nazwie „Fabrikam” jest dostarczany jako część biblioteki modułów i może być używany jako odwołanie.

## <a name="module-library-modules"></a>Moduły biblioteki modułów

W bibliotece modułów są dostępne następujące typy modułów:

- **Moduł kontenerów** — moduł kontenerowy jest prostym modułem działającym jako host dla innych modułów. Steruje on układem modułów znajdujących się wewnątrz tego modułu.
- **Moduły marketingowe** — moduły marketingowe: blok zawartości, blok tekstowy, odtwarzacz wideo i moduły karuzeli. Wszystkie te moduły mogą być używane do poprezentacji zawartości. Można je umieścić na dowolnej stronie i są sterowane danymi z systemu zarządzania treścią (CMS).
- **Moduły nagłówka i stopki** — moduły nagłówka i stopki są wyświetlane w nagłówku i stopce wszystkich stron witryny. Moduły te można skonfigurować zgodnie z wymaganiami właściwości.
- **Moduły wyszukiwania** — produkty można wykrywać za pomocą modułu wyszukiwania w nagłówku. Wyniki wyszukiwania zostaną wyświetlone na stronie wyników wyszukiwania. Produkty można również wykryty na stronach kategorii, które są dedykowanymi stronami dla każdej kategorii obsługiwanej w hierarchii nawigacji kanału. Ponadto moduły elementów uściślających mogą służyć do dalszego filtrowania wyników wyszukiwania i stron kategorii.
- **Moduły strony Szczegóły produktu** — strony z informacjami o produktach używają kilku modułów do wyświetlania informacji o produktach. Odbiorca modułu pola zakupu dla odbiorców umożliwia wyświetlenie produktów i dodanie ich do koszyka. Inne moduły, takie jak moduł specyfikacji technicznej, zawierają szczegóły dotyczące produktu. Moduł oceny i recenzje może służyć do wyświetlania i udostępniania recenzji.
- **Kupowanie w trybie online w module sklep** — funkcja kupowania w trybie online w module sklep jest zintegrowana z mapami Bing. Może służyć do wyszukiwania pobliskich sklepów, w których klienci mogą odbierać produkty nabyte przez nich.
- **Moduły zakupu** — moduły zakupów zawierają moduł koszyka, który może być używany do dodawania towarów do koszyka. Moduł realizacji transakcji zawiera adres wysyłkowy, opcje dostarczania oraz informacje o kartach upominkowych, programie lojalnościowym i karcie kredytowej, dzięki czemu można je przetwarzać. Po złożeniu zamówienia moduł potwierdzający zamówienie może być używany do wyświetlania szczegółów potwierdzenia.
- **Moduły zarządzania kontami** — odbiorcy mogą zalogować się do istniejącego konta, a moduł zapisywania się pozwala im utworzyć nowe konto. Po utworzeniu konta można użyć modułu historii zamówień w celu wyświetlenia ostatnich zamówień, a moduł szczegóły zamówienia może służyć do wyświetlania szczegółów zamówienia.
- **Moduł rekomendacji** — rekomendacje są wyświetlane za pomocą modułu umieszczanie produktu. Moduł ten obsługuje listy algorytmowe i redakcyjne, które można prezentować na dowolnej stronie.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Moduł kontenera](add-container-module.md)

[Moduł pola zakupu](add-buy-box.md)

[Moduł koszyka](add-cart-module.md)

[Moduł realizacji transakcji](add-checkout-module.md)

[Moduł potwierdzenia zamówienia](order-confirmation-module.md)

[Moduł nagłówka](author-header-module.md)

[Moduł stopki](author-footer-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]