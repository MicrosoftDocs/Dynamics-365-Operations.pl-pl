---
title: Wpływ możliwości rozszerzania katalogów Commerce dla dostosowań B2B
description: Ten artykuł opisuje wpływ rozszerzalności katalogów Commerce na funkcjonalność B2B w Microsoft Dynamics 365 Commerce.
author: ashishmsft
ms.date: 07/11/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2022-02-28
ms.openlocfilehash: 06d304226270c9c63c6907190dc1038a38f70e44
ms.sourcegitcommit: d1491362421bf2fcf72a81dc2dc2d13d3b98122b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/11/2022
ms.locfileid: "9136808"
---
# <a name="extensibility-impact-of-commerce-catalogs-for-b2b-customizations"></a>Wpływ możliwości rozszerzania katalogów Commerce dla dostosowań B2B

[!include [banner](includes/banner.md)]

Ten artykuł opisuje wpływ rozszerzalności katalogów **Commerce na funkcjonalność B2B** w Microsoft Dynamics 365 Commerce.

Jeśli chcesz rozszerzyć kontekst katalogu na niestandardowe scenariusze, może być konieczna aktualizacja twoich dostosowań. Ta aktualizacja jest zgodna ze standardowym procesem, który muszą przejść klienci, ponieważ ich własne modyfikacje mogą nie obsługiwać automatycznie najnowszych funkcji po dokonaniu aktualizacji. Jeśli twoje modyfikacje zawierają jakieś nowe funkcje lub poprawki błędów w swoich doświadczeniach, zalecamy, abyś odpowiednio zaktualizował kod tych dostosowań. Ta aktualizacja przypomina zmiany, które Microsoft mógł wprowadzić w kodzie głównym.

Przejrzyj poniższe przypadki dostosowywania, aby określić, czy twoje dostosowania muszą zostać zaktualizowane.

> [!NOTE]
> - Wszystkie interfejsy programowania aplikacji merchandisingowych (API) powinny być świadome katalogów. Z tego względu bardzo ważne jest, aby przekazać parametr **CatalogID**.
> - Katalog domyślny (**CatalogID**=**0**) nie jest prawidłowym katalogiem dla zalogowanych użytkowników business-to-business (B2B). Dlatego wszystkie wywołania API, które podają wartość „0” lub używają wartości domyślnej, zakończą się niepowodzeniem, ponieważ użytkownicy witryny nie mają dostępu do katalogu 0. Aby uzyskać prawidłowe doświadczenie, należy zaktualizować wywołania API klienta tak, aby przekazywały ID katalogu, który został wybrany w selektorze katalogów. Jeśli używasz wartości domyślnej, a użytkownik przełącza katalogi, strona powinna dostarczyć dane dla wybranego katalogu. Dlatego, aby dopasować się do interfejsów API uruchamianych z kodu Core Commerce, dostosowane interfejsy API powinny przekazywać wybrany katalog.

Następujące przypadki dostosowywania wymagają aktualizacji oprogramowania:

- **Sprawa 1:** Klient wprowadza swoją własną [akcję danych](e-commerce-extensibility/data-actions.md), która wywołuje API lub akcję danych związaną z produktem. Wymagane jest wykonanie następujących kroków aktualizacji:

    1. Jeśli akcja danych korzysta z bezpośredniego wywołania API, zaktualizuj akcję danych tak, by przekazywała ID katalogu, jak pokazano na poniższym przykładzie.

        ![Zaktualizowana akcja danych, która przekazuje identyfikator katalogu.](./media/customization1_a.png)

    1. Jeśli akcja z danymi wywołuje wewnątrz dostosowania inną akcję z danymi dotyczącymi produktu, kod musi zostać zaktualizowany tak, aby przekazywał nowe parametry, takie jak **requestContext**. Parametr **requestContext** jest używany do pobierania bieżącego identyfikatora katalogu, jak pokazano na poniższej ilustracji.

        ![Zaktualizowana akcja danych, która przekazuje nowy parametr.](./media/customization1_b.png)

- **Przypadek 2:** Klient ma [nadpisaną akcję danych](e-commerce-extensibility/data-action-overrides.md). Konieczne jest wykonanie następującego kroku aktualizacji:

    - Zaktualizuj działanie danych tak, jak w przypadku 1.

- **Przypadek 3:** Klient ma rozszerzenie widoku, moduł wstrzykujący skrypt lub [sklonowany moduł](e-commerce-extensibility/modules-overview.md#clone-a-module-library-module), który zawiera wywołania do interfejsów API lub akcji danych. Konieczne jest wykonanie następującego kroku aktualizacji:

    - Zaktualizuj kod tak, jak w przypadku 1, jak pokazano na poniższej ilustracji.

       ![Zaktualizowany kod, która przekazuje nowy parametr.](./media/customization3.png)

- **Przypadek 4:** Klient używa wywołania API **getById**. Konieczne jest wykonanie następującego kroku aktualizacji:

    - Zamiast tego przełącz się na wywołanie API **getByIds**, ponieważ wywołanie APT **getById** ma pewne ograniczenia i nie obsługuje świadomości katalogów.

- **Przypadek 5:** Klient ma akcję danych, która pobiera informacje o wielu produktach, które mogą pochodzić z różnych katalogów. Konieczne jest wykonanie następującego kroku aktualizacji:

    - Podziel wywołania API według ID katalogu. Na przykład, w przypadku API koszyka, w koszyku mogą znajdować się produkty z różnych katalogów. Linie produktów powinny być pogrupowane według ID katalogu i powinny wywoływać API dla każdego katalogu osobno, jak pokazano na poniższej ilustracji.

        ![Zaktualizowana akcja danych, która grupuje linie produktów według ID katalogu.](./media/customization5.png)

## <a name="additional-resources"></a>Dodatkowe zasoby

[Tworzenie katalogów Commerce dla stron B2B](catalogs-b2b-sites.md)

[Katalogi Commerce dla B2B FAQ](catalogs-b2b-sites-FAQ.md)

[Moduł selektora katalogów](catalog-picker.md)
