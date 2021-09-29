---
title: Kody przyczyn zliczania zapasów
description: W tym temacie opisano sposób konfigurowania i stosowania kodów przyczyn dla zadań inwentaryzacji.
author: perlynne
ms.date: 08/02/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventCountingReasonCodePolicy, InventCountingReasonCode
audience: Application User
ms.reviewer: kamaybac
ms.custom: 1705903
ms.assetid: 427e01b3-4968-4cff-9b85-1717530f72e4
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 4c178ddf342b13a0ef8fee8b8b958554a9a31069
ms.sourcegitcommit: ecd4c148287892dcd45656f273401315adb2805e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/18/2021
ms.locfileid: "7500607"
---
# <a name="reason-codes-for-inventory-counting"></a>Kody przyczyn zliczania zapasów

[!include [banner](../includes/banner.md)]

Kody przyczyn umożliwiają analizowanie wyników procesu inwentaryzacji (zliczania) i wszelkich rozbieżności pojawiających się w trakcie tego procesu. Można określić przyczynę wykonywania inwentaryzacji, taką jak uszkodzenie palety lub korekta zapasów oparta na próbkach zapasów. Jednocześnie można użyć funkcji korekty, aby zaksięgować wartość dostępnych korekt zapasów na odpowiednim koncie przeciwstawnym, na podstawie przyczyny każdej korekty zapasów.

## <a name="recommendation"></a>Propozycja płacowa

Przed skonfigurowaniem systemu zalecamy zdefiniowanie strategii pracy z kodami przyczyn. Na przykład spróbuj odpowiedzieć na następujące pytania:

- Czy kody przyczyn powinny być wymagane w magazynach?
- Czy kody przyczyn powinny być obowiązkowe, czy też dla niektórych towarów opcjonalne?
- Ile kodów przyczyn potrzeba?
- Czy musisz wstępnie wybrać ograniczoną listę kodów przyczyn dla korekt?
- Jak kody przyczyny powinny być wykorzystywane użytkowników skanerów kodów kreskowych? Czy kody przyczyn powinny być wstępnie wybierane, obowiązkowe i nieedytowalne?
- Czy pracownicy magazynu potrzebują innego zachowania kodów przyczyn w przenośnych skanerach? Jeśli odpowiedź brzmi „tak”, można utworzyć więcej elementów menu i przypisać je do różnych osób.
- Czy kody przyczyn powinny prowadzić do księgowania na finansowym konta przeciwstawnym?

## <a name="turn-on-reason-code-features-in-your-system"></a>Włączanie funkcji kodów przyczyn w systemie

Jeśli nie widzisz wszystkich funkcji opisanych w tym temacie w systemie, prawdopodobnie musisz włączyć funkcję *Księgowanie korekt dostępnych zapasów za pomocą konfigurowalnych kodów przyczyn połączonych z kontami przeciwstawnymi*. Administratorzy mogą skorzystać z ustawień [zarządzania funkcją](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby sprawdzić stan funkcji i włączyć ją, jeśli istnieje taka potrzeba. W obszarze roboczym **Zarządzanie funkcjami** ta funkcja widnieje jako:

- **Moduł:** *Zarządzanie magazynem*
- **Nazwa funkcji:** *Księgowanie korekt dostępnych zapasów za pomocą konfigurowalnych kodów przyczyn połączonych z kontami przeciwstawnymi*

## <a name="set-up-reason-codes"></a>Ustaw kody przyczyn

### <a name="set-up-reason-code-policies"></a>Konfigurowanie zasad kodów przyczyn zliczania

Można utworzyć wiele zasad kodów przyczyn, aby kontrolować, kiedy i jak kody przyczyn inwentaryzacji są stosowane. Każda zasada kodu przyczyny może mieć jeden z dwóch typów kodów przyczyn inwentaryzacji (*Opcjonalna* lub *Obowiązkowa*). Zasady kodów przyczyn inwentaryzacji mogą być używane na poziomie magazynu lub pozycji.

Aby utworzyć zasady kodu przyczyny, wykonaj następujące kroki.

1. Przejdź do pozycji **Zarządzanie zapasami** \> **Konfiguracja** \> **Zapasy** \> **Zasady kodów przyczyn inwentaryzacji**.
1. W okienku akcji wybierz opcję **Nowy**, aby dodać zasady do siatki.
1. Ustaw pole **Nazwa** dla nowych zasad.
1. W polu **Typ kodu przyczyny inwentaryzacji** wybierz opcję *Obowiązkowe* lub *Opcjonalne*, aby określić, czy wybór kodu przyczyny powinien być działaniem obowiązkowym czy opcjonalnym w jednym z procesów korekty zapasów:

    - Inwentaryzacja ciągła (za pomocą urządzenia przenośnego)
    - Inwentaryzacja punktowa (za pomocą urządzenia przenośnego)
    - Inwentaryzacja progowa (za pomocą urządzenia przenośnego)
    - Korekta wewnętrzna (za pomocą urządzenia przenośnego)
    - Korekta zewnętrzna (za pomocą urządzenia przenośnego)
    - Arkusz inwentaryzacyjny (za pomocą pełnego klienta)
    - Korekta ilości/Inwentaryzacja online (klient zaawansowany)

Można również skonfigurować zasady kodów przyczyn dla poszczególnych magazynów i produktów. Konfiguracja kodu przyczyny dla produktu może unieważnić konfigurację magazynu produktu.

> [!NOTE]
> W przypadku magazynów i pozycji, dla których ustawiono pole **Zasady kodu przyczyny inwentaryzacji** na *Obowiązkowe*, arkusz inwentaryzacyjny można sfinalizować i zamknąć dopiero po podaniu kodu przyczyny. Aby uzyskać więcej informacji, zapoznaj się z następną sekcją.

### <a name="assign-counting-reason-code-policies-to-warehouses"></a>Przypisywanie zasad kodów przyczyny inwentaryzacji do magazynów

Aby przypisać zasady kodu przyczyny inwentaryzacji do magazynu, wykonaj następujące kroki.

1. Przejdź do pozycji **Zarządzanie zapasami** \> **Konfiguracja** \> **Podział magazynu** \> **Magazyny**.
1. Wybierz magazyn w okienku listy.
1. W okienku akcji na karcie **Magazyn** w grupie **Konfiguracja** wybierz pozycję **Zasady kodów przyczyn inwentaryzacji**. Następnie w oknie dialogowym z listą rozwijaną **Przypisywanie zasad kodów przyczyny inwentaryzacji** wykonaj jedną z następujących czynności:

    - Aby użyć konfiguracji zasad dla każdej pozycji w celu określenia, czy arkusze inwentaryzacji są dla niej obowiązkowe, nie wprowadzaj wartości (lub usuń istniejącą wartość).
    - Aby wymagać kodu przyczyny inwentaryzacji arkuszy dla magazynu, wybierz zasady przyczyny, w których pole **Typ kodu przyczyny inwentaryzacji** jest ustawione na *Obowiązkowe*.
    - Jeśli kod przyczyny jest opcjonalny w arkuszach inwentaryzacji dla magazynu, wybierz zasady przyczyny, w których pole **Typ kodu przyczyny inwentaryzacji** jest ustawione na *Opcjonalne*.

### <a name="assign-counting-reason-code-policies-to-products"></a>Przypisywanie zasad kodów przyczyny inwentaryzacji do produktów

Aby przypisać zasady kodu przyczyny inwentaryzacji do produktu, wykonaj następujące kroki.

1. Przejdź do **Zarządzanie informacjami o produktach** \> **Produkty** \> **Zwolnione produkty**.
1. Wybierz produkt w siatce.
1. W okienku akcji na karcie **Produkt** w grupie **Konfiguracja** wybierz pozycję **Zasady kodów przyczyn inwentaryzacji**. Następnie w oknie dialogowym z listą rozwijaną **Przypisywanie zasad kodów przyczyny inwentaryzacji** wykonaj jedną z następujących czynności:

    - Aby użyć konfiguracji zasad dla magazynu w celu określenia, czy arkusze inwentaryzacji są obowiązkowe dla produktu, nie wprowadzaj wartości (lub usuń istniejącą wartość).
    - Aby wymagać kodu przyczyny inwentaryzacji arkuszy dla produktu, wybierz zasady przyczyny, w których pole **Typ kodu przyczyny inwentaryzacji** jest ustawione na *Obowiązkowe*. To ustawienie zastępuje wszelkie ustawienia kodów przyczyn na poziomie magazynu.
    - Jeśli kod przyczyny jest opcjonalny w arkuszach inwentaryzacji dla produktu, wybierz zasady przyczyny, w których pole **Typ kodu przyczyny inwentaryzacji** jest ustawione na *Opcjonalne*. To ustawienie zastępuje wszelkie ustawienia kodów przyczyn na poziomie magazynu.

### <a name="set-up-counting-reason-codes"></a>Konfigurowanie kodów przyczyn inwentaryzacji

Aby skonfigurować kody przyczyn inwentaryzacji, wykonaj następujące kroki.

1. Przejdź do pozycji **Zarządzanie zapasami** \> **Konfiguracja** \> **Zapasy** \> **Kody przyczyn inwentaryzacji**.
1. W okienku akcji wybierz opcję **Nowy**, aby dodać nowy wiersz do siatki.
1. Ustaw pola **Kod przyczyny inwentaryzacji** i **Opis** dla nowego wiersza.
1. Aby przypisać konto przeciwstawne, wprowadź lub wybierz wartość w polu **Konto przeciwstawne**.

    > [!NOTE]
    > Jeśli konto przeciwstawne jest przypisane do kodu przyczyny inwentaryzacji, podczas księgowania arkusza inwentaryzacji z kodem przyczyny inwentaryzacji, wartość jest księgowana na przypisanym koncie przeciwstawnym zamiast domyślnego konta profilu księgowania zapasów.

### <a name="set-up-counting-reason-code-groups"></a><a name="reason-groups"></a>Konfigurowanie grup kodów przyczyn inwentaryzacji

*Grupy kodów przyczyn inwentaryzacji* mogą być używane jako część elementów menu *Korekta wewnętrzna* i *Korekta zewnętrzna* w aplikacji mobilnej Warehouse Management w celu ograniczenia listy kodów przyczyn inwentaryzacji. (Aby uzyskać więcej informacji na temat grup kodów przyczyn inwentaryzacji, zobacz sekcję [Konfigurowanie elementów menu na urządzeniu przenośnym dla korekty wewnętrznej i zewnętrznej](#setup-adjustment-in-out) w dalszej części tego tematu).

1. Przejdź do pozycji **Zarządzanie zapasami** \> **Konfiguracja** \> **Zapasy** \> **Grupy kodów przyczyn inwentaryzacji**.
1. W okienku akcji wybierz opcję **Nowy**, aby dodać grupę.
1. Ustaw pola **Grupa przyczyny inwentaryzacji** i **Opis grupy** dla nowej grupy.
1. Na okienku akcji wybierz opcję **Zapisz**.
1. W sekcji **Szczegóły** i wybierz pozycję **Nowy** na pasku narzędzi, aby dodać wiersz do siatki. Następnie ustaw pole **Kod przyczyny inwentaryzacji** dla nowego wiersza. 
1. Powtórz poprzedni krok, aby przypisać więcej kodów zgodnie z wymaganiami. Jeśli musisz usunąć kod z grupy, zaznacz go, a następnie wybierz pozycję **Usuń** na pasku narzędzi.

### <a name="set-up-reason-codes-for-mobile-device-menu-items"></a>Konfigurowanie kodów przyczyn dla elementów menu na urządzeniu przenośnym

Kody przyczyn można skonfigurować dla następujących typów korekt dostępnych zapasów:

- Inwentaryzacja ciągła
- Inwentaryzacja punktowa
- Inwentaryzacja progowa
- Korekta wewnętrzna
- Korekta zewnętrzna

W większości przypadków można zdefiniować następujące informacje dla każdego odpowiedniego elementu menu urządzenia przenośnego:

- Czy kod przyczyny jest widoczny dla pracownika korzystającego z urządzenia przenośnego podczas inwentaryzacji.
- Domyślny kod przyczyny wyświetlany w elemencie menu na urządzeniu przenośnym.
- Czy użytkownik może edytować kod przyczyny.

#### <a name="set-up-mobile-device-menu-items-for-a-counting-process"></a>Konfigurowanie elementów menu na urządzeniu przenośnym na potrzeby procesu inwentaryzacji

Aby skonfigurować element menu urządzenia przenośnego dla procesu inwentaryzacji, wykonaj następujące kroki.

1. Przejdź do pozycji **Zarządzanie magazynem** \> **Konfiguracja** \> **Urządzenie przenośne** \> **Elementy menu urządzenia przenośnego**.
1. Zaznacz odpowiedni element menu w okienku listy lub utwórz nowy element menu.
1. W okienku akcji wybierz pozycję **Inwentaryzacja ciągła**.
1. W polu **Domyślny kod przyczyny inwentaryzacji** ustaw domyślny kod przyczyny, który ma być rejestrowany podczas inwentaryzacji za pomocą elementu menu na urządzeniu przenośnym.
1. W polu **Wyświetl kod przyczyny inwentaryzacji** wybierz jedną z następujących wartości:

    - *Wiersz* — pokaż kod przyczyny po zarejestrowaniu każdego odchylenia.
    - *Ukryj* — nie pokazuj kodu przyczyny.

1. Ustaw pole **Edytuj kod przyczyny inwentaryzacji** na *Tak*, aby zezwolić pracownikowi na edytowanie kodu przyczyny wyświetlanego na urządzeniu przenośnym podczas inwentaryzacji. Ustaw je na *Nie*, aby uniemożliwić pracownikowi edycję kodu.

> [!NOTE]
> Przycisk **Inwentaryzacja ciągła** można włączyć dla każdego elementu menu na urządzeniu przenośnym służącym do wykonywania inwentaryzacji. Przykładami są elementy menu dla inwentaryzacji punktowych, pracy sterowanej przez użytkownika i pracy sterowanej przez system.

#### <a name="set-up-mobile-device-menu-items-for-adjustment-in-and-adjustment-out"></a><a name="setup-adjustment-in-out"></a>Konfigurowanie elementów menu na urządzeniu przenośnym dla korekty wewnętrznej i zewnętrznej

Aby skonfigurować element menu urządzenia przenośnego dla korekty wewnętrznej lub zewnętrznej, wykonaj następujące kroki.

1. Przejdź do pozycji **Zarządzanie magazynem** \> **Konfiguracja** \> **Urządzenie przenośne** \> **Elementy menu urządzenia przenośnego**.
1. W okienku akcji wybierz opcję **Nowe**, aby utworzyć element menu.
1. Ustaw pola **Nazwa elementu na urządzeniu przenośnym** i **Tytuł** dla nowego elementu menu.
1. Ustaw pole **Tryb** na *Praca*.
1. W opcji **Użyj istniejącej pracy** ustaw wartość *Nie*.
1. W polu **Proces tworzenia pracy** wybierz pozycję *Korekta wewnętrzna* lub *Korekta zewnętrzna*.
1. Na skróconej karcie **Ogólne** ustaw następujące pola. (Wszystkie te pola są dodawane po wybraniu wartości *Korekta wewnętrzna* lub *Korekta zewnętrzna* w polu **Proces tworzenia pracy**).

    - **Użyj przewodnika po procesach** — jeśli tworzysz proces *korekty zewnętrznej*, należy ustawić tę opcję na *Tak*. Jeśli tworzysz proces *korekty zewnętrznej*, ta opcja jest zawsze ustawiona na *Tak*.
    - **Domyślny kod przyczyny inwentaryzacji** — ustaw domyślny kod przyczyny, który ma być rejestrowany podczas inwentaryzacji za pomocą elementu menu na urządzeniu przenośnym.
    - **Wyświetl kod przyczyny inwentaryzacji** — wybierz jedną z następujących wartości:

        - *Wiersz* — pokaż kod przyczyny po zarejestrowaniu każdego odchylenia.
        - *Ukryj* — nie pokazuj kodu przyczyny.

    - **Edytuj kod przyczyny inwentaryzacji** — ustaw tę opcję na *Tak*, aby zezwolić pracownikowi na edytowanie kodu przyczyny wyświetlanego na urządzeniu przenośnym podczas inwentaryzacji. Ustaw je na *Nie*, aby uniemożliwić pracownikowi edycję kodu.
    - **Grupa kodów przyczyn zliczania** — wybierz grupę kodów przyczyn, jeśli chcesz ograniczyć listę opcji, które są prezentowane pracownikom. Aby uzyskać informacje dotyczące konfigurowania grup kodów przyczyn, zobacz sekcję [Konfigurowanie grup kodów przyczyn inwentaryzacji](#reason-groups) wcześniej w tym temacie. 

> [!NOTE]
> Po przypisaniu grupy kodu przyczyny inwentaryzacji do elementów menu *Korekta wewnętrzna* i *Korekta zewnętrzna*, gdy opcja **Użyj przewodnika po procesach** jest ustawiona na *Tak*, można uzyskać ograniczoną listę kodów przyczyn inwentaryzacji w ramach przetwarzania w aplikacji mobilnej Warehouse Management.
>
> Opcja **Użyj przewodnika po procesach** może również pomóc zapobiegać pomyłkowemu przetwarzaniu dużych ilości w ramach korekty. (Na przykład pracownik może przypadkowo zeskanować kod kreskowy numeru pozycji zamiast wartości ilościowej). Aby skonfigurować tę funkcję, należy ustawić opcję **Użyj przewodnika po procesach** na *Tak* dla każdego odpowiedniego elementu menu. Następnie przejdź do pozycji **Zarządzanie magazynem \> Konfiguracja \> Pracownik** i ustaw pole **Limit ilości korekty** dla każdego odpowiedniego pracownika magazynu, aby określić maksymalną ilość korekty, jaką pracownik może zarejestrować.

## <a name="processing-that-uses-counting-reason-codes"></a>Przetwarzanie, które używa kodów przyczyn inwentaryzacji

Gdy pracownicy korzystają z aplikacji mobilnej Warehouse Management, kody przyczyn są rejestrowane. O ile nie zdefiniowano procesu zatwierdzania inwentaryzacji, zarejestrowane kody przyczyn są natychmiast używane jako część stosowanego następnie arkusza inwentaryzacji.

### <a name="cycle-count-approvals"></a>Zatwierdzenia inwentaryzacji ciągłej

Przed zatwierdzeniem inwentaryzacji pracownik może zmienić kod przyczyny skojarzony z inwentaryzacją. Po zatwierdzeniu inwentaryzacji kod przyczyny jest wprowadzany w wierszach arkusza inwentaryzacyjnego.

#### <a name="modify-reason-codes-for-cycle-count-approvals"></a>Modyfikowanie kodów przyczyn dla zatwierdzeń inwentaryzacji ciągłej

Aby zmodyfikować zatwierdzenie inwentaryzacji ciągłej, wykonaj następujące kroki.

1. Przejdź do pozycji **Zarządzanie magazynem** \> **Inwentaryzacja ciągła** \> **Praca inwentaryzacji ciągłej oczekuje na przegląd**.
1. Wybierz inwentaryzację ciągłą w siatce.
1. W okienku akcji na karcie **Praca** wybierz opcję **Inwentaryzacja ciągła**. Następnie w polu **Kod przyczyny** wybierz nowy kod przyczyny.

Kody przyczyn są dodawane do wierszy arkusza w arkuszach inwentaryzacyjnych typu *Arkusz zliczania*.

1. Wybierz kolejno opcje **Zarządzanie zapasami** \> **Wpisy w arkuszu** \> **Zliczanie towarów** \> **Inwentaryzacja**.
2. W szczegółach wiersza arkusza inwentaryzacji w polu **Kod przyczyny inwentaryzacji** wybierz kod przyczyny odpowiadający bieżącej sytuacji.

### <a name="view-the-reason-codes-recorded-in-the-counting-history"></a>Wyświetlanie kodów przyczyn zarejestrowanych w historii inwentaryzacji

Aby wyświetlić kody przyczyn, które zostały zarejestrowane w historii inwentaryzacji, wykonaj następujące kroki.

1. Wybierz kolejno opcje **Zarządzanie zapasami** \> **Zapytania i raporty** \> **Historia inwentaryzacji**.
1. Wybierz rekord liczby elementów w okienku listy.
1. W polu **Kod przyczyny inwentaryzacji** wyświetl historię inwentaryzacji, która została zarejestrowana za pomocą kodu przyczyny.

### <a name="use-reason-codes-for-quantity-adjustment-or-online-counting"></a>Używanie kodów przyczyn do korekty ilości lub inwentaryzacji online

Aby użyć kodu przyczyny do korekty ilości lub inwentaryzacji online, wykonaj następujące kroki.

1. Wybierz kolejno opcje **Zarządzanie zapasami \> Zapytania i raporty \> Dostępne zapasy**.
1. W okienku akcji kliknij pozycję **Korekta ilości**.
1. Wybierz opcję **Korekta ilości**, a następnie w polu **Kod przyczyny inwentaryzacji** wybierz kod przyczyny.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
