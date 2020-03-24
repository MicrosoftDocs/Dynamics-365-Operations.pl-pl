---
title: Kontrola kondycji urządzeń peryferyjnych i usług punktu sprzedaży
description: Ten temat stanowi przegląd operacji sprawdzania kondycji w punkcie sprzedaży (POS).
author: rubendel
manager: AnnBe
ms.date: 03/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.custom: 141393
ms.assetid: e23e944c-15de-459d-bcc5-ea03615ebf4c
ms.search.region: Global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2019-03-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 1a4ecdbd64bdb0ae3eee9d82bd9ef2cbfcab7567
ms.sourcegitcommit: 48c39c0c0949fe48b3536d9d2d0e451d561ff5c6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2020
ms.locfileid: "3112373"
---
# <a name="health-check-for-pos-peripherals-and-services"></a>Kontrola kondycji urządzeń peryferyjnych i usług punktu sprzedaży

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Ten temat opisuje przegląd operacji sprawdzania kondycji w punkcie sprzedaży (POS).

## <a name="overview"></a>Omówienie

Sklepy detaliczne mogą być skomplikowanymi środowiskami, w których używane są różne aplikacje i urządzenia. W miarę wzrostu operacji może się okazać trudne zapewnienie, że operacje są zawsze wykonywane bezproblemowo z powodu zależności na przykład dla urządzeń peryferyjnych, które mogą zostać zerwane lub przypadkowo odłączone w ciągu dnia. Rozwiązywanie problemów związanych z urządzeniami i usługami może być kosztowne dla większych handlowców i w równym stopniu frustrujące dla mniejszych operacji.

W wersji Microsoft Dynamics 365 Commerce 10.0.10 i nowszych uwzględniono operację sprawdzania kondycji, która pomaga zapobiegać niektórym kosztom i frustracji. Ta operacja udostępnia metodę testowania urządzeń bezpośrednio z punktu sprzedaży poza normalnymi operacjami. Dzięki temu Detaliści mogą wykryć problemy przed ich wystąpieniem.

## <a name="key-terms"></a>Kluczowe terminy

| Okres | opis |
|---|---|
| Urządzenie peryferyjne | Dowolne urządzenie używane przez aplikację punktu sprzedaży w celu ułatwienia transakcji i innych operacji w sklepie. Przykładami mogą być szuflady środków pieniężnych, skanery kodów kreskowych i terminale płatności. |
| Serwis | W tym temacie Usługa jest aplikacją pomocniczą, na której opiera się aplikacja punktu sprzedaży, aby wykonywać transakcje i codzienne operacje. Przykładem mogą być aplikacje, które pomagają w obliczeniach podatków lub kosztów wysyłki. |

## <a name="health-check-operation"></a>Operacja sprawdzania kondycji

Operacja sprawdzania kondycji jest operacją 717 na stronie **operacje punktu sprzedaży** w programie Commerce Headquarters. Można go użyć, gdy punkt sprzedaży jest w trybie bez szuflady. Jednak Stacja sprzętowa musi być aktywna.

Domyślnie testy kondycji są sprawdzane tylko w przypadku urządzeń skonfigurowanych w profilu sprzętu dla stacji sprzętowej, która jest aktualnie aktywna dla kasy. Jeśli rejestr używa wielu stacji sprzętowych w ciągu dnia, w celu sprawdzenia kondycji wszystkich tych urządzeń musi połączyć się każdorazowo z jedną stacją sprzętową. Nie ma sprawdzania kondycji na poziomie sklepu. Jednak sprawdzanie tego typu może być możliwe za pośrednictwem rozszerzalności serwera Commerce Server.

### <a name="out-of-box-health-checks"></a>Gotowe kontrole kondycji

| Typ | Połączenie | Szczegóły |
|---|---|---|
| Drukarka | OPOS | Ten test testuje podstawowe łączenie i osadzanie obiektów dla funkcji punktu sprzedaży (OPOS). Oto kilka przykładów:<ul><li>Otwórz: **Otwórz** &gt; **ClaimDevice** &gt; **DeviceEnabled = True**</li><li>Zamknij: **DeviceEnabled=False** &gt; **ReleaseDevice** &gt; **Zamknij**</li></ul> |
| Wyświetlacz wierszowy | OPOS | Ten test sprawdza podstawowe funkcje OPOS. Oto kilka przykładów:<ul><li>Otwórz: **Otwórz** &gt; **ClaimDevice** &gt; **DeviceEnabled = True**</li><li>Zamknij: **DeviceEnabled=False** &gt; **ReleaseDevice** &gt; **Zamknij**</li></ul> |
| Dwa wyświetlacze | Windows | Ten test gwarantuje, że system operacyjny wykryje drugi ekran systemu Windows. | 
| MSR | OPOS | Ten test sprawdza podstawowe funkcje OPOS. Oto kilka przykładów:<ul><li>Otwórz: **Otwórz** &gt; **ClaimDevice** &gt; **DeviceEnabled = True**</li><li>Zamknij: **DeviceEnabled=False** &gt; **ReleaseDevice** &gt; **Zamknij**</li></ul> |
| Szuflada | OPOS | Ten test sprawdza podstawowe funkcje OPOS. Oto kilka przykładów:<ul><li>Otwórz: **Otwórz** &gt; **ClaimDevice** &gt; **DeviceEnabled = True**</li><li>Zamknij: **DeviceEnabled=False** &gt; **ReleaseDevice** &gt; **Zamknij**</li></ul> | 
| Skaner | OPOS | Ten test sprawdza podstawowe funkcje OPOS. Oto kilka przykładów:<ul><li>Otwórz: **Otwórz** &gt; **ClaimDevice** &gt; **DeviceEnabled = True**</li><li>Zamknij: **DeviceEnabled=False** &gt; **ReleaseDevice** &gt; **Zamknij**</li></ul> | 
| Waga | OPOS | Ten test sprawdza podstawowe funkcje OPOS. Oto kilka przykładów:<ul><li>Otwórz: **Otwórz** &gt; **ClaimDevice** &gt; **DeviceEnabled = True**</li><li>Zamknij: **DeviceEnabled=False** &gt; **ReleaseDevice** &gt; **Zamknij**</li></ul> |
| Konsola PIN | OPOS | Ten test sprawdza podstawowe funkcje OPOS. Oto kilka przykładów:<ul><li>Otwórz: **Otwórz** &gt; **ClaimDevice** &gt; **DeviceEnabled = True**</li><li>Zamknij: **DeviceEnabled=False** &gt; **ReleaseDevice** &gt; **Zamknij**</li></ul> |
| Terminal płatniczy | SDK Płatności | Ten test testuje podstawowe funkcje terminalu, dostarczane przez zestaw SDK Płatności. <ul><li>Zablokuj</li><li>BeginTransaction</li><li>EndTransaction</li><li>ReleaseDevice</li><li>Zamknięcie</li></ul> |

### <a name="using-the-health-check-operation-in-the-pos"></a>Korzystanie z operacji sprawdzania kondycji w punkcie sprzedaży

Gdy w punkcie sprzedaży zainicjowano operację sprawdzania kondycji, w okienku po prawej stronie znajduje się lista skonfigurowanych urządzeń i jest wyświetlany stan każdego urządzenia. Aby sprawdzić kondycję dla jednego urządzenia, wybierz urządzenie, a następnie wybierz opcję **Testuj wybrane**. Aby sprawdzić kondycję wszystkich urządzeń, wybierz opcję **Testuj wszystkie**. Funkcja **Testuj wszystkie** sprawdza wszystkie urządzenia, pojedynczo i aktualizuje stan każdego urządzenia w kolumnie **Stan**.

Kolumna **Ostatnie sprawdzanie kondycji** jest wyświetlana po ostatnim zakończeniu sprawdzania kondycji dla każdego urządzenia.

Jeśli sprawdzanie kondycji urządzenia zostało zakończone bez problemów (to znaczy, jeśli nie wystąpiły żadne błędy), stan urządzenia będzie mieć wartość **OK**. Jeśli sprawdzanie kondycji nie powiedzie się, stan będzie wskazywał, że wystąpił błąd. W tym przypadku okienko po prawej stronie zawiera szczegóły związane z tym błędem lub informuje użytkownika o konieczności skontaktowania się z administratorem systemu.

Niektóre urządzenia, takie jak blokada klucza OPOS, nie mają gotowych testów sprawdzających kondycję. Jeśli test sprawdzania kondycji nie zostanie wykryty dla żadnego używanego urządzenia, stan będzie **Nieobsługiwany**.

### <a name="extending-health-checks"></a>Rozszerzanie kontroli kondycji

Gotowe testy sprawdzające kondycję są skonfigurowane w taki sposób, aby w przypadku typowych błędów były przedstawiane przyjazne dla użytkownika komunikaty. Jednak nie wszystkie scenariusze są tym objęte. Dzięki rozszerzalności sprzedawcy mogą mapować przyjazne dla użytkownika wiadomości na błędy, które mogą być charakterystyczne dla środowiska.

Niestandardowe testy kondycji można również tworzyć w przypadku urządzeń, które nie są domyślnie obsługiwane, ani do testowania usług, na których bazuje się punkt sprzedaży.

## <a name="related-articles"></a>Powiązane artykuły

[Możliwości rozszerzania wyzwalacza aplikacji Modern POS (MPOS) i Cloud POS](https://docs.microsoft.com/dynamics365/commerce/dev-itpro/modern-pos-trigger-extensibility)
