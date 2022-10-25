---
title: Obszar roboczy rozwiązania Invoice Capture
description: Ten artykuł zawiera informacje o obszarze roboczym rozwiązania Invoice Capture.
author: sunfzam
ms.date: 09/25/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: VendorInvoiceWorkspace, VendInvoiceInfoListPage
audience: Application User
ms.reviewer: twheeloc
ms.custom:
- "13971"
- intro-internal
ms.assetid: 0ec4dbc0-2eeb-423b-8592-4b5d37e559d3
ms.search.region: Global
ms.author: zezhangzhao
ms.search.validFrom: 2022-09-28
ms.dyn365.ops.version: ''
ms.openlocfilehash: 4f3af7abf94542437be6132344d6bb7ffaf33d07
ms.sourcegitcommit: 40c80a617b903c2b26e44b41147e0021c5cb680d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2022
ms.locfileid: "9691192"
---
# <a name="invoice-capture-solution-workspace"></a>Obszar roboczy rozwiązania Invoice Capture

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

## <a name="side-by-side-viewer-for-the-invoice-capture-solution"></a>Przeglądarka ze znajdującymi się obok siebie widokami rozwiązania Invoice Capture

Wprowadzanie faktur do systemu zwykle jest czasochłonnym procesem, który jest podatny na błędy, ponieważ aby zebrać poprawne informacje, trzeba nawigować po wielu plikach załączników i oknach. Przeglądarka dokumentów obok siebie ułatwia pracę nad fakturami, ułatwiając tym procesom bardziej efektywne i dokładniejsze działanie.

Przeglądarka dokumentów obok siebie umożliwia użytkownikom wyświetlanie w tym samym oknie obok siebie oryginalnego dokumentu i faktury. Strona faktury jest wypełniana informacjami z oryginalnego dokumentu faktury. Przeglądarka tworzy połączenie między polami strony faktury a oryginalnym dokumentem faktury. Przeglądarka pomaga również użytkownikom znajdować błędy na stronie faktury.

### <a name="open-the-side-by-side-viewer"></a>Otwieranie przeglądarki umożliwiającej wyświetlanie dokumentów obok siebie

W aplikacji Microsoft Dynamics 365 Finance możesz otworzyć przeglądarkę umożliwiającą wyświetlanie dokumentów obok siebie z listy na stronie podsumowania lub ze strony listy faktur. Można ją również otworzyć przez dwukrotne naciśnięcie (lub dwukrotne kliknięcie) rekordu lub wybranie numeru faktury.

### <a name="using-the-side-by-side-viewer"></a>Korzystanie z przeglądarki umożliwiającej wyświetlanie dokumentów obok siebie

#### <a name="manually-review-an-invoice"></a>Ręczne przeglądanie faktury

Zaimportowany dokument faktury może wymagać ręcznego sprawdzenia pod kątem błędów lub ostrzeżeń. W przeglądarce umożliwiającej wyświetlanie dokumentów obok siebie nagłówek dokumentu będzie pokazywał stan **Zaimportowano**, a bieżącą wersją będzie **Wersja oryginalna**.

Aby rozpocząć przeglądanie faktury, wybierz pozycję **Rozpocznij przegląd**. Wszystkie pola stają się edytowalne. Pole **Stan** zostanie zaktualizowane do stanu **W trakcie przeglądu**, a pole **Bieżąca wersja** zostanie zaktualizowane do wartości **Wersja zmodyfikowana**.

#### <a name="view-and-work-with-messages"></a>Przeglądanie komunikatów i praca z nimi

Użytkownicy powinni rozpocząć proces przeglądu z okienka komunikatów. Komunikaty o błędach są oznaczone czerwonym znakiem X, komunikaty ostrzegawcze są oznaczone trójkątem, a komunikaty informacyjne są oznaczone okręgiem. Komunikaty dotyczące współczynnika ufności mogą być klasyfikowane jako ostrzeżenia lub błędy, w zależności od progu ustawionego przez grupę konfiguracji. Aby uzyskać więcej informacji, zobacz temat [Grupy konfiguracji rozwiązania Invoice Capture](invoice-capture-config-group.md).

Komunikaty ostrzegawcze i komunikaty o błędach mogą być ignorowane w okienku komunikatów, w nagłówku faktury lub w wierszach faktury. Gdy komunikat zostanie zignorowany, nie będzie już wyświetlany jako błąd lub ostrzeżenie, a weryfikacja faktury nie powiedzie się.

- Aby zignorować komunikaty z okienka wiadomości, wybierz pozycję **Ignoruj**. Aby zresetować komunikat, który został zignorowany, wybierz ponownie pozycję **Ignoruj**. Następnie jego typ jest zmieniany z błędu lub ostrzeżenia na komunikat informacyjny.
- Aby zignorować komunikaty z nagłówka lub wiersza faktury, wybierz opcję **Ignoruj** w polu. Symbol komunikatu zniknie. Jeśli jednak komunikat zostanie zresetowany z okienka wiadomości, zostanie on ponownie wyświetlony.

W przypadku komunikatów związanych z polami nagłówka faktury po wybraniu komunikatu w okienku komunikatów kursor jest przenoszony do odpowiedniego pola w sekcji nagłówka.

#### <a name="proofread-and-edit-fields"></a>Korekta i edycja pól

Jeśli wartość pola jest odczytywana z oryginalnej faktury za pośrednictwem optycznego rozpoznawania znaków (OCR), na tym polu jest wyświetlany symbol. Po wybraniu symbolu widok przeglądarki dokumentów jest powiększany i jest wyróżniane miejsce, z poziomu którego jest odczytywana wartość pola, co pomaga w zweryfikowaniu danych faktury.

Aby zresetować przeglądarkę dokumentów do oryginalnego powiększenia, należy wykonać jeden z poniższych kroków:

- Wybierz ten sam symbol co poprzednio.
- Kliknij przycisk w prawym górnym rogu przeglądarki dokumentów.

Edytuj pola stosownie do potrzeb. Edycje są zapisywane automatycznie, gdy kursor opuszcza pole. Symbol z prawej strony pola wskazuje, że pole zostało zaktualizowane ręcznie. Po odświeżeniu strony symbol zostanie usunięty.

#### <a name="check-an-invoice-to-get-up-to-date-messages"></a>Sprawdzanie faktury w celu wyświetlenia aktualnych komunikatów

Podczas edytowania pola wartość tego pola jest aktualizowana, ale nowe komunikaty dotyczące walidacji nie są generowane. Aby wyświetlić aktualne komunikatów dotyczące walidacji, wybierz pozycję **Sprawdź**. Komunikaty w okienku komunikatów, w nagłówku faktury i w wierszach faktury są aktualizowane.

#### <a name="complete-the-review"></a>Kończenie przeglądu

Aby zakończyć przegląd, wybierz pozycję **Ukończ przegląd**. Faktury są weryfikowane. Jeśli zostaną znalezione błędy, dokument będzie nadal w stanie **W trakcie przeglądu** i pojawi się pasek komunikatów. Wszystkie komunikaty w okienku komunikatów oraz w nagłówku i wierszach faktury są automatycznie aktualizowane, aby uzyskać informacje o przyczynach błędu walidacji.

Po usunięciu wszystkich błędów powodujących blokowanie można zakończyć przegląd. Stan dokumentu jest aktualizowany do stanu **Przejrzano** i pól nie można już edytować. Możesz ponownie uruchomić przegląd, jeszcze raz wybierając pozycję **Uruchom przegląd**.

#### <a name="generate-a-pending-vendor-invoice-in-finance"></a>Generowanie oczekującej faktury od dostawcy w aplikacji Finance

Aby wysłać dokument faktury do połączonego środowiska aplikacji Finance, wybierz pozycję **Generuj**. Jeśli generowanie faktury nie powiedzie się, na pasku komunikatów pojawi się komunikat o błędzie.

#### <a name="void-an-invoice"></a>Unieważnianie faktury

Aby unieważnić fakturę, wybierz pozycję **Unieważnij**. Nie można przeglądać unieważnianych faktur i nie są one wyświetlane na liście **Faktury wymagają ręcznego przeglądu**.

### <a name="validation-logic"></a>Logika walidacji

Niektóre pola klucza w przeglądarce dokumentów obok siebie nie istnieją w danych tymczasowych faktur, ale są wymagane do generowania faktur oczekujących w aplikacji Finance. Te pola pochodzą z kombinacji bieżących danych tymczasowych faktur i danych głównych z aplikacji Finance.

Wymagane pola pochodne to **Osoba prawna**, **Konto dostawcy** i **Identyfikator pozycji**. Muszą one być pobierane w następującej kolejności. Jeśli określanie pole pochodnego nie powiedzie się, proces zostanie zatrzymany.

1. **Osoba prawna** — osoba prawna jest pobierana jako pierwsza. Jeśli dla osoby prawnej zostanie znaleziona aktywna reguła mapowania, osoba prawna będzie pochodną nazwy firmy i adresu firmy.
2. **Konto dostawcy** — następnie konto dostawcy jest pobierane na podstawie aktywnej reguły mapowania oraz kombinacji pochodnej osoby prawnej, nazwy dostawcy i adresu dostawcy.
3. **Identyfikator pozycji** — na koniec nazwa pozycji jest pobierana z etapu tymczasowego na podstawie następujących trzech typów informacji:

    - Skonfigurowana reguła mapowania
    - Pochodna osoba prawna
    - Pochodne konto dostawcy

Aby uruchomić walidację, wybierz opcję **Sprawdź** w przeglądarce dokumentów obok siebie. Obecnie walidacja wykonuje następujące testy:

- **Kontrola obowiązkowa** — ten test polega na weryfikacji obowiązkowych pól w przeglądarce dokumentów obok siebie. Użytkownicy mogą wybrać pola obowiązkowe na stronie **Ustawienie konfiguracji**.
- **Współczynnik ufności** — użytkownicy mogą ustawiać próg ostrzeżenia i próg błędu dla współczynnika ufności. Ten test koncentruje się na współczynniku ufności z OCR, który znajduje się poniżej tych progów. Na podstawie wyników walidacji będą wyświetlane komunikaty o błędach lub komunikaty ostrzegawcze.
- **Osoba prawna** — ten test weryfikuje osobę prawną w aplikacji Finance. Jeśli osoba prawna nie istnieje w środowisku aplikacji Finance, walidacja nie powiedzie się.

Gdy przeglądarka dokumentów obok siebie jest używana po raz pierwszy, a użytkownik wybierze pozycję **Sprawdź**, zostaną uruchomione procesy określania pochodnych i walidacji. Jeśli faktury są dokładne, proces walidacji jest uruchamiany, gdy użytkownik wybierze opcję **Ukończ przegląd**. Jest on również uruchamiany, gdy użytkownik wybierze opcję **Generuj fakturę od dostawcy**.

Proces określania pochodnych występuje przed procesem walidacji i wszystkie ostrzeżenia lub błędy pochodzą z tego procesu. Ostrzeżenia i błędy zostaną zarejestrowane w aplikacji Finance.
