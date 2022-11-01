---
title: Użycie tokenu płatności limitu
description: W tym artykule opisano funkcję, która ogranicza sposób, w jaki tokeny płatności są używane w programie Microsoft Dynamics 365 Commerce.
author: BrianShook
ms.date: 10/20/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2022-09-20
ms.openlocfilehash: 8092ab0724f33f21759aa84d25e0bdcb5b2ad5dd
ms.sourcegitcommit: 6bd8822f7aa781d596b70956bead834117cf302c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/20/2022
ms.locfileid: "9709660"
---
# <a name="limit-payment-token-usage"></a>Użycie tokenu płatności limitu

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

W tym artykule opisano funkcję, która ogranicza sposób, w jaki tokeny płatności są używane w programie Microsoft Dynamics 365 Commerce. Użycie tokenu jest ograniczone do zakresu zamówienia sprzedaży lub, jeśli zgoda odbiorcy jest udzielona, jest przechowywane jako karta w pliku.

## <a name="key-terms"></a>Kluczowe terminy

| Okres | Opis |
|---|---|
| Token | Obiekt blob XML w usłudze Dynamics 365, do którego istnieje odwołanie, który przechowuje odwołania do płatności do celów transakcyjnych. |
| Karta w pliku | Zapisany token odwołania do karty, który został uzgodniony do przyszłego użycia w systemie Dynamics 365 lub w bramy płatności, i który jest określony dla konta odbiorcy. |

Limity użycia tokenu płatności dotyczą dowolnego środowiska, w którym jest używana usługa bramy płatności, w których są używane tokeny cykliczne. Gotowy łącznik [Dynamics 365 Payment Connector dla Adyen](adyen-connector.md) używa cyklicznych tokenów płatności do wykonywania kolejnych akcji zamówień, takich jak korekty autoryzacji i ponowne autoryzacje.

Aby ułatwić kontrolowanie sposobu używania tych tokenów płatności cyklicznych w systemie, funkcja **Ogranicz użycie tokenu płatności do kontekstu zamówienia** ogranicza użycie tokenu cyklicznego w zakresie zamówienia sprzedaży w systemie. Gdy jest włączony, funkcja modyfikuje interfejs użytkownika (UI) programu Commerce headquarters, aktualizując strony wejściowe płatności i ograniczając możliwość wybierania odwołań do płatności byłego klienta do użycia w nowych wystąpieniach transakcji.

Ta funkcja pomaga spełnić reguły użycia dla niektórych wystawców płatności, takich jak Visa. W [podstawowych zasadach dotyczących karty Visa oraz zasadach dotyczących produktów i usług Visa](https://usa.visa.com/content/dam/VCOM/download/about-visa/visa-rules-public.pdf) Visa określa, że korzystanie z tokenów płatności powinno być ograniczone do zakresu transakcji, o ile posiadacz karty nie uzgodni inaczej.

Funkcja **Ogranicz użycie tokenu płatności do kontekstu zamówienia** jest dostępna tylko w przypadku korzystania z usługi bramy płatności, która korzysta z odwołań do cyklicznych tokenów płatności.

## <a name="enable-the-feature"></a>Włączanie funkcji

Aby włączyć funkcję **Ogranicz użycie tokenu płatności do kontekstu zamówienia**, w programie Commerce headquarters w swoim środowisku przejdź do obszaru **Obszary robocze \> Zarządzanie funkcjami**, znajdź i wybierz **Ogranicz użycie tokenu płatności do kontekstu zamówienia** z listy, a następnie wybierz **Włącz teraz**.

## <a name="limit-payment-token-usage"></a>Użycie tokenu płatności limitu

Gdy ta funkcja jest włączona, strony programu Commerce headquarters używane do przechwytywania form płatności zaktualizują sposób, w jaki odwołują się do form płatności odbiorcy, które są zarejestrowane dla tego odbiorcy. Ta aktualizacja będzie mieć głównie wpływ na dwa obszary operacji:

- Sposób w jaki karta odbiorcy jest wprowadzana w pliku w imieniu odbiorcy
- Sposób przechowywania informacji o płatności dla odbiorcy dla przyszłych wpisów płatności zamówień sprzedaży

Gdy odbiorca przeprowadza transakcje w kanałach Commerce, szczegóły płatności są przechowywane z kontekstem zamówienia sprzedaży. Kontekst zamówienia sprzedaży ogranicza token płatności, przez co nie będzie używany jako odwołanie do płatności dla rekordu odbiorcy na stronach płatności dla nowych lub edytowanych płatności zamówień sprzedaży w programie Commerce headquarters.

### <a name="payment-form-changes"></a>Zmiany formularza płatności

Gdy użytkownik z centrum obsługi lub centrali Commerce headquarters przyjmuje płatność dla odbiorcy za zamówienie sprzedaży, na stronie płatności są obecne szczegóły wyboru formy płatności. Gdy jest włączona funkcja **Ogranicz użycie tokenu płatności do kontekstu zamówienia**, to jeśli użytkownik wybierze znak plus (**+**) na stronie płatności, zostaną wyświetlone tylko zapisane rekordy „karta w pliku”. Zmiany wymagają, aby użytkownik działu obsługi lub centrali Commerce headquarters wprowadzał pełne szczegóły płatności podane przez klienta, gdy wypełniał stronę **Wprowadzanie informacji o płatności odbiorcy** dla nowej transakcji zamówienia sprzedaży.

Lista wartości pola **Numer** zawiera tylko odwołania do kart skojarzone z klientem, który ma kartę w pliku. Odfiltrowuje wszelkie odwołania do minionych płatności, których zakres nie jest ograniczony do zamówienia sprzedaży.

Znak plus (**+**) w polu **Numer** pozostaje dostępny i może służyć do wprowadzania informacji o płatności podanych przez klienta dla transakcji skojarzonej z przetwarzanym zamówieniem sprzedaży.

### <a name="how-cards-on-file-work"></a>Jak działają karty w pliku

Gdy jest włączona funkcja **Ogranicz użycie tokenu płatności do kontekstu zamówienia**, karta w pliku jest cyklicznym tokenem płatności zapisywany w rekordzie odbiorcy i nie jest ograniczona do zakresu zamówienia sprzedaży. Karta w pliku umożliwia szybkie odwołanie użytkowników programu Commerce headquarters po wypełnieniu strony płatności dotyczącej nowej płatności za zamówienie sprzedaży. To odwołanie do tokenu ma zastosowanie tylko do środowiska systemu Dynamics 365. W przypadku kanałów online korzystających z usługi bramy płatności, która umożliwia użytkownikom zapisanie metody płatności do przyszłego użycia w module płatności iFrame, brama płatności przechowuje te odwołania jako oddzielne odwołanie do karty w pliku Dynamics 365.

Jeśli na przykład Dynamics 365 Commerce Payment Connector dla Adyen jest używany w kanale online, klienci, którzy w module płatności iFrame podają informacje o karcie kredytowej, zobaczą tylko odwołania do kart zapisane przez usługę bramy do ich następnego uwierzytelnienia zakupu w trybie online. W pliku nie widać karty przechowywanej dla środowiska systemu Dynamics 365 jako opcji w module płatności iFrame. Podobnie, gdy osoby robiące zakupy umieszczają zamówienie za pośrednictwem biura obsługi klienta, ich zapisane w trybie online odwołania do kart nie są prezentowane użytkownikowi biura obsługi jako opcje. Użytkownik biura obsługi widzi tylko poprzednią kartę w odwołaniach do plików z systemu Dynamics 365 (zgodnie z uzgodnieniami klienta), aby zapisać dla przyszłych zamówień.

Użytkownicy programu Commerce headquarters mogą zapisywać w pliku kartę dla odbiorcy, przechodząc do **Retail i Commerce \> Klienci** i wybierając rekord konta użytkownika. W sekcji **Klient \> Konfiguracja** użytkownicy, którzy mają uprawnienia do przetwarzania stron płatności, mogą użyć strony wprowadzania **Kart kredytowych** w celu wprowadzenia karty płatniczej, która będzie przechowywana w pliku dla przyszłych transakcji. Ta operacja pomaga zaoszczędzić czas podczas przetwarzania przyszłych płatności zamówień sprzedaży dla odbiorcy. Użytkownicy centrum obsługi i centrali Commerce headquarters powinni wprowadzać dane karty tylko wtedy, gdy odbiorca zgadza się używać odwołania do karty w przyszłych transakcjach.

Pole wyboru **Zapisz do przyszłego użycia** u dołu stron płatności programu Commerce headquarters umożliwia użytkownikom zapisanie karty do przyszłego użycia. To pole wyboru powinno być używane tylko wtedy, gdy klient zgadza się używać karty w pliku do przyszłych transakcji. Pole wyboru **Zapisz na potrzeby przyszłego użycia** można wyświetlić lub ograniczyć, używając opcji **Zezwalaj na kartę odbiorcy w pliku** na karcie **Płatność** na stronie **Parametry centrum obsługi** w programie Commerce headquarters. Gdy jest ustawiona wartość **Tak**, użytkownicy programu Commerce Headquarters, którzy mają uprawnienia do przetwarzania stron płatności, mogą zapisać kartę w pliku, używając pola wyboru **Zapisz do przyszłego użycia**. Gdy jest ustawiona wartość **Nie**, to pole wyboru nie jest dostępne dla użytkowników centrali Commerce headquarters, którzy mają uprawnienia do przetwarzania stron płatności. Opcji **Zezwalaj na użycie karty odbiorcy w pliku** można użyć, jeśli firma chce ograniczyć korzystanie z tokenów cyklicznych w programie Commerce headquarters, ale nie chce jeszcze zezwalać na zapisanie karty w pliku bez procedury zapewniającej wyrażenie zgody odbiorcy.

### <a name="commerce-headquarters-pages-where-the-recurring-token-restrictions-are-enforced"></a>Strony centrali Commerce headquarters, na których wymuszane są ograniczenia tokenu cyklicznego

Gdy ta funkcja jest włączona, ograniczenie tokenu wpływa na następujące obszary w programie Commerce headquarters:

- Informacje o płatności odbiorcy w **Zamówienie sprzedaży \> Płatności \> Wprowadź płatność odbiorcy**
- Zamówienia ciągłe
- Płatności rat
- Płatności karty kredytowej rozrachunków z odbiorcami

### <a name="manage-payment-tokens-archiving-or-removal"></a>Zarządzanie tokenami płatności (archiwizacja lub usuwanie)

Tokeny płatności utworzone przed włączoną flagą funkcji **Ogranicz użycie tokenu płatności do kontekstu zamówienia** (lub gdy ta funkcja była wyłączona) pozostaną w systemie „poza zakresem” i można do nich odwoływać się na listach wyboru na stronie płatności centrali Commerce headquarters. Tokeny te można usuwać regularnie na dwa sposoby w programie Commerce headquarters:

- Strona **Archiwizuj dane transakcji karty kredytowej** do konfiguracji zadania, które regularnie przeczyszcza lub archiwizuje tokeny płatności. Jeśli w opcji **Usuń dane bezarchiwizacji** ustawisz wartość **Tak**, tokeny spełniające ustawienie **Minimalny czas transakcji (w dniach)** zostaną usunięte. Aby uzyskać więcej informacji, zobacz [Archiwizuj dane transakcji karty kredytowej](archive-cc-data.md).
- Użyj nowej strony **Wyczyść tokeny karty kredytowej** (**Rozrachunki z odbiorcami \>Informacje i raporty Oczyszczanie \> Czyszczenie \> Wyczyść tokeny karty kredytowej**), która umożliwia uruchomienie lub skonfigurowanie zadania wsadowego, które usuwa tokeny płatności. Ustaw następujące parametry:

    - Wartość **Minimalnego wieku tokenu w dniach** musi być co najmniej 90 dni.
    - Ustawienia **Uruchom w tle** mogą służyć do definiowania ustawień **Cyklu** lub **Alertów**.
    - Grupę zadań wsadowych można przypisać do uruchamiania zadania w określonej grupie.
    - Jeśli w opcji **Prywatny** jest ustawiona wartość **Tak**, może je uruchomić tylko użytkownik, który je tworzy.
    - Ustawienie **Tak** w przypadku opcji **Zadanie krytyczne** zapewnia, że system aktywnie śledzi stan zadania.

Nie można pobrać usuniętych tokenów. Ustaw w polu **Minimalny czas tokenu** wartość na zakres, który odpowiada najdłużej działającemu środowisku transakcyjnemu (od autoryzacji do przechwytywania lub zwrotu).

## <a name="additional-resources"></a>Dodatkowe zasoby

[Płatności — często zadawane pytania](payments-retail.md)

[Moduł realizacji transakcji](../add-checkout-module.md)

[Moduł płatności](../payment-module.md)
