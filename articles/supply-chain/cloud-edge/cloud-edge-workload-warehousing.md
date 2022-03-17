---
title: Obciążenia pracą dotyczące zarządzania magazynem dla jednostek skalowania chmury i urządzenia brzegowego
description: Ten temat zawiera informacje o funkcji umożliwiającej skalowanie jednostek miar na uruchamianie wybranych procesów z poziomu obciążenia pracą w module Zarządzanie magazynem.
author: perlynne
ms.date: 09/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PurchTable, InventTransferOrders, SalesTable, SysSecRolesEditUsers, SysWorkloadDuplicateRecord
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: SCM
ms.author: perlynne
ms.search.validFrom: 2020-10-06
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 67f78441b0914d18c2a7853bab54c6b8817be3ac
ms.sourcegitcommit: 2e554371f5005ef26f8131ac27eb171f0bb57b4e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/04/2022
ms.locfileid: "8384493"
---
# <a name="warehouse-management-workloads-for-cloud-and-edge-scale-units"></a>Obciążenia pracą dotyczące zarządzania magazynem dla jednostek skalowania chmury i urządzenia brzegowego

[!include [banner](../includes/banner.md)]

> [!WARNING]
> Nie wszystkie funkcje zarządzania magazynem w firmie są w pełni obsługiwane w przypadku magazynów, w których jest uruchomione obciążenie pracą z jednostką skalowania. Należy pamiętać, aby użyć tylko tych procesów, które opisano w tym temacie jako obsługiwane.

## <a name="warehouse-execution-on-scale-units"></a>Wykonanie magazynowe w jednostkach skali

Obciążenia pracą dotyczące zarządzania magazynem umożliwiają jednostkom skalowania chmury i krawędzi uruchamianie wybranych procesów z poziomu możliwości zarządzania magazynem.

## <a name="prerequisites"></a>Wymagania wstępne

Zanim zaczniesz pracować z obciążeniem pracą związanym z zarządzaniem magazynem, twój system musi być przygotowany w sposób opisany w tej sekcji.

### <a name="deploy-a-scale-unit-with-the-warehouse-management-workload"></a>Rozmieść jednostkę wagi z obciążeniem pracy związanym z zarządzaniem magazynem

Musi istnieć centrum i jednostka skali dla Dynamics 365 Supply Chain Management, która została wdrożona wraz z obciążeniem zarządzania magazynem. Aby uzyskać więcej informacji na temat architektury i procesu wdrażania, zobacz [Jednostki skalowania w rozproszonej topologii hybrydowej](cloud-edge-landing-page.md).

### <a name="turn-on-required-features-in-feature-management"></a>Włącz wymagane funkcje w zarządzaniu cechami

W obszarze roboczym [Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) włącz obie funkcje. (Obie funkcje są wymienione pod *Zarządzania magazynem*.)

- Odłączanie pracy odłożonej od powiadomień WPW
- (Wersja zapoznawcza) Obsługa jednostki skalowania dla przychodzących i wychodzących zamówień magazynu

## <a name="how-the-warehouse-execution-workload-works-on-scale-units"></a>Sposób obciążenia pracą dotyczącą wykonania w magazynie na jednostkach skali

W przypadku procesów w ramach zadań zarządzania magazynem dane są synchronizowane między centrum a jednostkami miary skali.

Jednostka skali może obsługiwać tylko te dane, które są z nią właścicielem. Pojęcie własności danych dla jednostek skali ułatwia zapobieganie konfliktom z wieloma wzorcami. Dlatego ważne jest, aby zrozumieć, które dane procesu są własnością centrum, a które są własnością jednostek skali.

W zależności od procesów biznesowych ten sam rekord danych może zmienić prawa własności między centrum a jednostkami skali. Przykład tego scenariusza przedstawiono w poniższej sekcji.

> [!IMPORTANT]
> Niektóre dane można tworzyć zarówno dla centrum, jak i dla jednostki skalowania. Przykłady: **Numery identyfikacyjne** i **Numery partii**. Obsługa konfliktów jest dedykowana w przypadku scenariusza, w którym podczas tego samego cyklu synchronizacji ten sam unikatowy rekord jest tworzony zarówno w centrum, jak i jednostce skalowania. Jeśli się tak zdarzy, następna synchronizacja nie powiedzie się i będzie trzeba przejść do folderu **Administrowanie systemem > Zapytania > Zapytania dotyczące obciążenia pracą > Zduplikowane rekordy**, w których można wyświetlać i scalać dane.

## <a name="outbound-process-flow"></a>Przepływ procesu wychodzącego

Przed wdrożeniem obciążenia pracą zarządzania magazynem w jednostce skalowania chmury lub krawędzi należy upewnić się, że w centrum przedsiębiorstwa jest włączona funkcja *Obsługa jednostki skalowania do zwalniania do magazynu zamówień wychodzących*. Administratorzy mogą skorzystać z ustawień [zarządzania funkcją](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby sprawdzić stan funkcji i włączyć ją, jeśli istnieje taka potrzeba. W obszarze roboczym **Zarządzanie funkcjami** ta funkcja widnieje jako:

- **Moduł:** *Zarządzanie magazynem*
- **Nazwa funkcji:** *Obsługa jednostki skalowania do zwalniania do magazynu zamówień wychodzących*

Proces wychodzących praw własności danych zależy od tego, czy jest używany proces planowania wysyłki ładunku. We wszystkich przypadkach centrum jest właścicielem *dokumentów źródłowych*, takich jak zamówienia sprzedaży i zamówienia przeniesienia, a także procesu alokacji zamówień i powiązanych danych transakcji zamówień. Jednak w przypadku korzystania z procesu planowania wysyłki ładunku obciążenia pracą zostaną utworzone w centrum i dlatego początkowo należą do centrum. W ramach procesu *zwalniania do magazynu* własność danych ładunku jest przenoszona do dedykowanego wdrożenia jednostki skalowania, które stanie się właścicielem kolejnego *przetwarzania grupy czynności wysyłki* (takich jak alokacja pracy, praca uzupełniania zapasów i tworzenie pracy popytu). Dlatego pracownicy magazynu mogą przetwarzać wyłącznie pracę zamówień sprzedaży wychodzącej i zamówienia przeniesienia za pomocą aplikacji mobilnej Warehouse Management, która jest połączona z wdrożeniem, w którym jest uruchomione określone obciążenie pracą jednostki skalowania.

Gdy tylko ostateczny proces pracy odłoży zapasy w końcowej lokalizacji wysyłki (bramie dokowej), jednostka skalowania wysyła do centrum sygnał, aby zaktualizować transakcje magazynowe dokumentu źródłowego na stan *Pobrano*. Dopóki ten proces nie zostanie uruchomiony i nie zostanie zsynchronizowany ponownie, dostępne zapasy dla obciążenia jednostki skalowania zostaną fizycznie zarezerwowane na poziomie magazynu i będzie można natychmiast przetworzyć potwierdzenie wysyłki wychodzącej bez oczekiwania na zakończenie tej synchronizacji. Kolejny dokument dostawy sprzedaży oraz wysyłka zafakturowana lub z zamówienia przeniesienia dla ładunku zostaną obsłużone w centrum.

Na poniższym schemacie przedstawiono przepływ wychodzący oraz przedstawiono miejsce wykonania miejsce poszczególnych procesów biznesowych. (Zaznacz diagram, aby go powiększyć).

[![Przepływ przetwarzania wychodzącego.](media/wes_outbound_warehouse_processes-small.png "Przepływ przetwarzania wychodzącego")](media/wes_outbound_warehouse_processes.png)

### <a name="outbound-processing-with-load-planning"></a>Przetwarzanie wychodzące z planowaniem wysyłki ładunku

W przypadku korzystania z procesu planowania wysyłki ładunku w centrum są tworzone ładunki i wysyłki, a prawa własności do danych są przenoszone na jednostki skalowania w ramach procesu *zwalniania do magazynu*, co przedstawiono na poniższej ilustracji.

![Przetwarzanie wychodzące z planowaniem wysyłki ładunku.](./media/wes_outbound_processing_with_load_planning.png "Przetwarzanie wychodzące z planowaniem wysyłki ładunku")

### <a name="outbound-processing-without-load-planning"></a>Przetwarzanie wychodzące bez planowania wysyłki ładunku

Jeśli nie używasz procesu planowania wysyłki ładunku, wysyłki są tworzone w ramach jednostek skalowania. Ładunki są także tworzone na jednostkach skalowania w ramach procesu obsługi grupy czynności.

![Przetwarzanie wychodzące bez planowania wysyłki ładunku.](./media/wes_outbound_processing_without_load_planning.png "Przetwarzanie wychodzące bez planowania wysyłki ładunku")

## <a name="inbound-process-flow"></a>Przepływ procesu przychodzącego

Piasta posiada następujące dane:

- Wszystkie dokumenty źródłowe, takie jak zamówienia zakupu i zlecenia produkcyjne
- Przetwarzanie ładowania przychodzącego
- Wszystkie aktualizacje fizyczne i finansowe

> [!NOTE]
> Przychodzący przepływ zamówienia zakupu różni się pod względem koncepcji od przepływu wychodzącego. Ten sam magazyn można obsługiwać w jednostce skalowania lub centrum w zależności od tego, czy zamówienie zakupu zostało zwolnione do magazynu. Po zwolnieniu zamówienia do magazynu można pracować z tym zamówieniem wyłącznie po zalogowaniu się do jednostki skalowania.
>
> Jeśli jest używana funkcja *Zwalniania do magazynu*, tworzone są [*zamówienia magazynowe*](cloud-edge-warehouse-order.md), a do jednostki skali jest przypisana własność powiązanego przepływu przyjęcia. Centrum nie będzie mogło zarejestrować przyjęcia przychodzącego.

Należy się zalogować do centrum, aby zainicjować proces *zwalniania do magazynu*. W celu przetwarzania zamówienia zakupu przejdź na jedną z następujących stron, aby je uruchomić lub zaplanować:

- **Zaopatrzenie i sourcing > Zamówienia zakupu > Wszystkie zamówienia zakupu > Magazyn > Akcje > Zwolnij do magazynu**
- **Zarządzanie magazynem > Zwolnij do magazynu > Automatyczne zwalnianie zamówień zakupu**

W przypadku korzystania z funkcji **Automatyczne zwalnianie zamówień zakupu** można wybierać określone wiersze zamówienia zakupu w oparciu o kwerendę. Typowym scenariuszem byłoby skonfigurowanie powtarzającego się zadania wsadowego, które zwalnia wszystkie potwierdzone wiersze zamówienia zakupu, które mają nadejść następnego dnia.

Pracownicy magazynu mogą uruchomić proces odbioru za pomocą aplikacji Warehouse Management połączonej z jednostką miary skali. Dane są następnie rejestrowane przez jednostkę skali i podawane w odniesieniu do przychodzącego zamówienia magazynowego. Tworzenie i przetwarzanie kolejnych odłożeń będzie również obsługiwane przez jednostkę skali.

Jeśli nie są używane *procesy magazynowe*, a w związku z tym nie są używane *zamówienia magazynowe*, centrum może przetwarzać przyjęcie magazynowe i przetwarzanie pracy niezależnie od jednostek skalowania.

![Przepływ procesu przychodzącego.](./media/wes-inbound-ga.png "Przepływ procesu przychodzącego")

Gdy pracownik rejestruje dane przychodzące za pomocą procesu przyjęcia w aplikacji mobilnej Warehouse Management dla jednostki skalowania, przyjęcie jest rejestrowane w odniesieniu do powiązanego zamówienia magazynowego przechowywanego w ramach jednostki skalowania. Obciążenie pracą jednostki skalowania będzie wtedy sygnalizować centrum aktualizację transakcji związanych z wierszem zamówienia zakupu na *Zarejestrowane*. Po zakończeniu tego zadania będzie można uruchomić w centrum przyjęcie produktu zamówienia zakupu.

Na poniższym schemacie przedstawiono przepływ przychodzący oraz przedstawiono miejsce wykonania miejsce poszczególnych procesów biznesowych. (Zaznacz diagram, aby go powiększyć).

[![Przepływ przetwarzania przychodzącego](media/wes_inbound_warehouse_processes-small.png "Przepływ przetwarzania przychodzącego")](media/wes_inbound_warehouse_processes.png)

## <a name="production-control"></a>Kontrola produkcji

Narzędzie do zarządzania magazynem obsługuje następujące trzy przepływy produkcyjne w aplikacji Warehouse Management:

- Zgłoszenie i odłożenie wyrobów gotowych
- Rozpocznij zlecenie produkcyjne
- Rejestruj zużycie materiałów

### <a name="report-as-finished-and-put-away"></a>Zgłoszenie i odłożenie wyrobów gotowych

Pracownicy mogą użyć przepływu **Zgłoś jako zakończone i odłóż** w aplikacji Warehouse Management, aby zgłosić zlecenie produkcyjne lub wsadowe jako zakończone. Mogą także zgłaszać produkty uboczne i współprodukty w zleceniu na partię jako gotowe. Kiedy zadanie jest zgłaszane jako zakończone, system zazwyczaj generuje pracę odłożenia w magazynie na jednostce skalowania. Jeśli nie potrzebujesz odkładania pracy na później, możesz tak skonfigurować swoją politykę pracy, by ją pomijać.

### <a name="start-production-order"></a>Rozpocznij zlecenie produkcyjne

Pracownicy mogą użyć przepływu **Rozpocznij zlecenie produkcyjne** w aplikacji Warehouse Management, aby zarejestrować rozpoczęcie zlecenia produkcyjnego lub seryjnego.

### <a name="register-material-consumption"></a>Rejestruj zużycie materiałów

Pracownicy mogą użyć przepływu **Rejestruj zużycie materiału** w aplikacji Warehouse Management, aby zgłosić zużycie materiału dla zlecenia produkcyjnego lub seryjnego. Następnie tworzony jest dziennik listy pobrań dla materiału zgłoszonego w zleceniu produkcyjnym lub seryjnym na jednostce wagi. W wierszach dziennika dokonuje się fizycznego zastrzeżenia zużytych zapasów. Gdy dane są synchronizowane między jednostką wagi a hubem, generowany jest dziennik pobrań, który jest umieszczany na instancji centrum.

## <a name="supported-processes-and-roles"></a>Obsługiwane procesy i role

Nie wszystkie procesy zarządzania magazynem są obsługiwane w obciążeniu pracy dla wykonania w magazynie w ramach jednostki skalowania. Dlatego zaleca się przypisanie ról spełniających funkcje dostępne dla każdego użytkownika.

Aby ułatwić ten proces, do przykładowej roli o nazwie *Menedżer magazynu podczas obciążenia pracą* dołączono dane demonstracyjne w sekcji **Administrowanie systemem \> Zabezpieczenia \> Konfiguracja zabezpieczeń**. Celem tej roli jest umożliwienie menedżerom magazynu dostępu do obciążenia dla wykonania w magazynie w ramach jednostki skalowania. Rola umożliwia dostęp do stron, które są istotne w kontekście obciążenia pracą obsługiwanego przez jednostkę skali.

Role użytkowników na jednostce skali są przypisywane jako część początkowej synchronizacji danych od centrum do jednostki skali.

Aby zmodyfikować role przypisane do użytkownika, przejdź do **Administracja systemu \> Zabezpieczenia \> Przypisz użytkowników do ról**. Użytkownicy, którzy działają jako kierownicy magazynu tylko w jednostkach skali, powinni mieć przypisany tylko *Menedżer magazynu w* roli obciążenia. Takie podejście zapewni, że użytkownicy ci będą mieli dostęp tylko do obsługiwanych funkcji systemu. Umożliwia usunięcie wszelkich innych ról przypisanych do tych użytkowników.

Użytkownicy, którzy działają jako kierownicy magazynu tylko w jednostkach skali, powinni mieć przypisany tylko *Menedżer magazynu w* roli obciążenia. Należy pamiętać, że ta rola udziela pracownikom magazynowym dostępu do funkcji (takich jak przetwarzanie odbioru zamówień przeniesienia), które są wyświetlane w interfejsie użytkownika (UI), ale nie są obecnie obsługiwane w jednostkach skali.

### <a name="supported-warehouse-execution-processes"></a>Obsługiwane procesy wykonania w magazynie

Następujące procesy wykonania w magazynie mogą być włączone dla obciążenia wykonania w magazynie w ramach jednostki skalowania:

- Wybrane metody grupy czynności dla zamówień sprzedaży i przeniesienia (walidacja, tworzenia obciążenia pracą, alokacja, uzupełnianie zapasów popytu, konteneryzacja, tworzenie pracy i drukowanie etykiet grupy czynności)

- Przetwarzanie pracy magazynowej zamówień sprzedaży i przeniesienia przy użyciu aplikacji magazynu (łącznie z pracą uzupełniania zapasów)
- Badanie dostępnych zapasów przy użyciu aplikacji magazynowej
- Tworzenie i uruchamianie przesunięć magazynowych przy użyciu aplikacji magazynowej
- Tworzenie i przetwarzanie pracy inwentaryzacji ciągłej za pomocą aplikacji magazynowej
- Wykonywanie korekt zapasów przy użyciu aplikacji magazynowej
- Rejestrowanie zamówień zakupu i wykonywanie odłożenia pracy przy użyciu aplikacji magazynowej

W ramach jednostki skalowania można tworzyć następujące typy pracy, które mogą być przetwarzane w ramach obciążenia pracą dla zarządzania magazynem:

- **Przesunięcia zapasów**— ręczne przenoszenie i przenoszenie według pracy z szablonu.
- **Inwentaryzacja ciągła** — obejmuje proces zatwierdzania/odrzucania rozbieżności w ramach operacji inwentaryzacji.
- **Zamówienia zakupu** — praca odłożenia za pośrednictwem zamówienia magazynowego, jeśli zamówienia zakupu nie są skojarzone z ładunkami.
- **Zamówienia zakupu** — proste pobieranie i ładowanie.
- **Przeniesienie przyjęcia** – za pośrednictwem przetwarzania przyjęcia przez numer identyfikacyjny.
- **Wydanie przeniesienia** — proste pobieranie i ładowanie.
- **Uzupełnianie zapasów** — z wyłączeniem surowców do produkcji.
- **Ukończono odkładanie wyrobów** — proces przeprowadzany po zgłoszeniu produkcji jako zakończonej.
- **Odłożenie produktu ubocznego i produktu towarzyszącego** — proces przeprowadzany po zgłoszeniu produkcji jako zakończonej.
<!-- - **Packed container picking** - After manual packing station processing. -->

Obecnie żadne inne typy przetwarzania dokumentów źródłowych nie są obsługiwane w jednostkach skalowania. Na przykład, kiedy pracujesz z obciążeniem wykonawczym magazynu na jednostce wagi, nie możesz użyć procesu przyjmowania zamówień zwrotnych do przetwarzania zamówień zwrotnych. Zamiast tego to przetwarzanie musi być wykonane przez instancję centrum.

> [!NOTE]
> Elementy menu i przyciski menu urządzenia przenośnego dla nieobsługiwanych funkcji nie są pokazywane w _aplikacji Warehouse Management_, jeśli są połączone z wdrożeniem jednostki skalowania.
>
> Aby skonfigurować aplikację mobilną Warehouse Management do pracy z chmurą lub jednostką brzegową, należy wykonać kilka dodatkowych kroków. - Aby uzyskać więcej informacji, zobacz [Skonfiguruj aplikację mobilną Warehouse Management dla jednostek działających w chmurze i na brzegu](cloud-edge-workload-setup-warehouse-app.md).
>
> W przypadku uruchamiania obciążenia pracą na jednostkę skali nie można uruchamiać nieobsługiwanych procesów dla określonego magazynu w centrali. Tabele podane dalej w tym temacie zawierają opis obsługiwanych możliwości.
>
> Wybrane typy pracy magazynowej można tworzyć zarówno w centrum, jak i na jednostkach skalowania, ale mogą być dostępne tylko przez centrum lub jednostkę skalowania (wdrożenie, które utworzyło dane).
>
> Nawet jeśli określony proces jest obsługiwany przez jednostkę skalowania, należy pamiętać, że wszystkie potrzebne dane mogą nie zostać zsynchronizowane z centrum do jednostki skalowania lub z jednostki skalowania do centrum, co może doprowadzić do nieoczekiwanego przetworzenia systemu. Przykłady tego scenariusza obejmują następujące sytuacje:
>
> - Jeśli używasz zapytania dyrektywy lokalizacji, które łączy rekord tabeli danych, który istnieje tylko podczas wdrażania centrum.
> - W przypadku używania funkcji obciążenia wolumetrycznego dla lokalizacji i/lub stanu okalizacji. Te dane nie zostaną zsynchronizowane między wdrożeniami, dlatego będą działać tylko podczas aktualizowania dostępnych zapasów lokalizacji dla jednego z wdrożeń.

Następująca funkcja zarządzania magazynem nie jest obecnie obsługiwana w obciążeniach jednostkach skali:

- Przychodzące przetwarzanie wierszy zamówienia zakupu przypisanych do ładunku.
- Przychodzące przetwarzanie zamówień zakupu dla projektu.
- Zarządzanie kosztami z wyładunkiem, korzystanie z podróży i śledzenie zmian towarów w drodze.
- Przetwarzanie przychodzące i wychodzące dla towarów, które mają aktywne wymiary śledzenia **Właściciel** i/lub **Numer seryjny**.
- Przetwarzanie zapasów z wartością stanu blokowania.
- Zmiana stanu zapasów w trakcie dowolnego procesu przemieszczania pracy.
- Elastyczne rezerwacja wymiarów na poziomie magazynu dla zamówienia.
- Korzystanie z funkcji *stanu lokalizacji w magazynie* (dane nie są synchronizowane między wdrożeniami).
- Korzystanie z funkcji *pozycjonowania dla numeru identyfikacyjnego lokalizacji*.
- Korzystanie z *filtrów produktów* i *grup filtrów produktów*, łącznie z ustawieniem **Liczba dni na mieszanie partii**.
- Integracja z zarządzaniem jakością.
- Przetwarzanie pozycji w ilości efektywnej.
- Przetwarzanie z pozycjami włączonymi tylko dla zarządzania transportem (TMS).
- Przetwarzanie ujemnych dostępnych zapasów.
- Udostępnianie danych między firmami dla produktów. <!-- Planned -->
- Przetwarzanie prac magazynowych z notatkami wysyłkowymi (na przykład notatkami pakowania na stacji pakowania).
- Obrazy danych produktu głównego (na przykład w aplikacji Warehouse Management).
- Przetwarzanie pracy magazynowej przy użyciu automatyzacji obsługi materiałów/magazynu.

> [!WARNING]
> Niektóre funkcje magazynu nie będą dostępne dla magazynów, w których jest uruchomione obciążenie pracą zarządzania magazynem w jednostce skalowania, a ponadto nie są obsługiwane w centrum ani w obciążeniu jednostki skalowania.
>
> Inne możliwości mogą zostać przetworzone dla obu tych obiektów, ale będą wymagać ostrożniej pracy w niektórych scenariuszach, na przykład w przypadku aktualizacji dostępnych zapasów dla tego samego magazynu zarówno w centrum, jak i jednostce skalowania z powodu asynchronicznej aktualizacji danych.
>
> Określone funkcje (takie jak *praca z blokadą*) obsługiwane zarówno w jednostkach centrum, jak i skalowania będą obsługiwane tylko przez właściciela danych.

### <a name="outbound-supported-only-for-sales-and-transfer-orders"></a>Wychodzące (obsługiwane tylko dla zamówień sprzedaży i przeniesienia)

W poniższej tabeli pokazano, które funkcje wychodzące są obsługiwane i gdzie są obsługiwane, gdy obciążenie pracą w ramach zarządzania magazynem jest używane w jednostkach skali w chmurze i krawędziach.

| Przetwarzaj                                                      | Piasta | Obciążenie pracą dla wykonania w magazynie w ramach jednostki skalowania |
|--------------------------------------------------------------|-----|------------------------------|
| Przetwarzanie dokumentu źródłowego                                   | Tak | Nie |
| Zarządzanie procesem załadunku i transportu                | Tak, ale tylko procesy planowania wysyłki ładunku. Przetwarzanie zarządzania transportem nie jest obsługiwane  | Nie |
| Zwolnij do magazynu                                         | Tak | Nie |
| Planowany przeładunek kompletacyjny                                        | Nie  | Nie |
| Konsolidacja wysyłki                                       | Tak, w przypadku planowania wysyłki ładunku | Tak |
| Przetwarzanie grupy wysyłek                                     | Nie  |Tak, z wyjątkiem funkcji **Tworzenie i sortowanie ładunku** |
| Obsługa wysyłek dla grupy czynności                                  | Nie  | Tak|
| Przetwarzanie pracy magazynowej (z uwzględnieniem numeru identyfikacyjnego na płycie licencyjnej)        | Nie  | Tak, ale tylko dla wymienionych wcześniej obsługiwanych możliwości |
| Wybór grupy                                              | Nie  | Tak|
| Ręczne przetwarzanie stacji pakowania  | Nie  | Nie |
| Przetwarzanie sortowania wychodzących                                  | Nie  | Nie |
| Drukowanie dokumentów powiązanych z ładunkiem                           | Tak | Tak|
| List przewozowy i generowanie WPW                            | Nie  | Tak|
| Potwierdzenie wysyłki                                             | Nie  | Tak|
| Potwierdzenie wysyłki z „potwierdzeniem i przeniesieniem”            | Nie  | Tak|
| Przetwarzanie dokumentów dostawy i faktur                        | Tak | Nie |
| Szybkie pobranie (zamówienia sprzedaży i przeniesienia)                    | Nie  | Tak, bez usuwania rezerwacji dla dokumentów źródłowych|
| Nadmiarowe pobranie (zamówienia sprzedaży i przeniesienia)                     | Nie  | Tak|
| Konsoliduj numery identyfikacyjne                                   | Nie  | Tak|
| Zmiana lokalizacji pracy (zamówienia sprzedaży i przeniesienia)         | Nie  | Tak|
| Zakończenie pracy (zamówienia sprzedaży i przeniesienia)                    | Nie  | Tak|
| Drukowanie raportu pracy                                            | Tak | Tak|
| Etykieta grupy czynności                                                   | Nie  | Tak|
| Podział pracy                                                   | Nie  | Tak|
| Przetwarzanie pracy — skierowane przez transport ładunku            | Nie  | Nie |
| Zmniejsz ilość pobraną                                       | Nie  | Tak|
| Wycofaj pracę                                                 | Nie  | Tak|
| Wycofaj potwierdzenie wysyłki                                | Nie  | Tak|
| Prośba o anulowanie wierszy zamówień magazynowych                      | Tak | Nie, ale wniosek zostanie zatwierdzony lub odrzucony |
| <p>Zwolnij zamówienie przeniesienia do odbioru</p><p>Ten proces będzie automatycznie występować w procesie wysyłki zamówienia przeniesienia. Można go jednak użyć ręcznie, aby umożliwić odbiór tablic rejestracyjnych w jednostce wagi, jeśli linie zamówień przychodzących do magazynu zostały anulowane lub jako część procesu wdrażania nowego obciążenia.</p> | Tak | Nie|
<!--| Ręczne przetwarzanie na stanowisku pakowania, w tym praca „Pobieranie zapakowanych kontenerów”  | Nie  | Tak, ale bez manifestacji przesyłki TMS i publikowania listów przewozowych sprzedaży oraz bez notatek dotyczących pakowania i zdjęć produktów |-->

### <a name="inbound"></a>Przychodzące

W poniższej tabeli pokazano, które funkcje przychodzące są obsługiwane i gdzie są obsługiwane, gdy obciążenie pracą w ramach zarządzania magazynem jest używane w jednostkach skali w chmurze i krawędziach.

| Przetwarzaj                                                          | Piasta | Obciążenie pracą dla wykonania w magazynie w ramach jednostki skalowania<BR>*(Pozycje oznaczone jako „Tak” dotyczą tylko zamówień magazynowych)* |
|------------------------------------------------------------------|-----|----------------------------------------------------------------------------------|
| Przetwarzanie &nbsp;dokumentu&nbsp; źródłowego                             | Tak | Nie |
| Zarządzanie procesem załadunku i transportu                    | Tak | Nie |
| Koszt z wyładunkiem i odbiór towaru w drodze                       | Tak | Nie |
| Potwierdzenie wysyłki wychodzącej                                    | Tak | Nie |
| Zwolnienie zamówienia zakupu do magazynu (przetwarzanie zamówienia magazynowego) | Tak | Nie |
| Prośba o anulowanie wierszy zamówień magazynowych                            | Tak | Nie, ale wniosek zostanie zatwierdzony lub odrzucony |
| Przetwarzanie dokumentu źródłowego zamówienia zakupu na odbiór produktu                        | Tak | Nie |
| Przyjęcie i odłożenie pozycji z zamówienia zakupu                       | <p>Tak, &nbsp;gdy &nbsp;nie ma&nbsp; zamówienia magazynowego</p><p>Nie, jeśli istnieje zamówienie magazynowe</p> | <p>Tak, jeśli zamówienie zakupu nie jest częścią <i>ładunku</i></p> |
| Przyjęcie i odłożenie wiersza zamówienia zakupu                       | <p>Tak, jeśli nie istnieje zamówienie magazynowe</p><p>Nie, jeśli istnieje zamówienie magazynowe</p> | <p>Tak, jeśli zamówienie zakupu nie jest częścią <i>ładunku</i></p></p> |
| Zwróć odebrane zamówienie i odłóż                              | Tak | Nie |
| Przyjęcie i odłożenie mieszanego numeru identyfikacyjnego                       | <p>Tak, jeśli nie istnieje zamówienie magazynowe</p><p>Nie, jeśli istnieje zamówienie magazynowe</p> | Tak |
| Odbierana pozycja ładunku                                              | <p>Tak, jeśli nie istnieje zamówienie magazynowe</p><p>Nie, jeśli istnieje zamówienie magazynowe</p> | Nie |
| Zamówienie Numeru identyfikacyjnego Odbiór i odłożenie              | <p>Tak, jeśli nie istnieje zamówienie magazynowe</p><p>Nie, jeśli istnieje zamówienie magazynowe</p> | Nie |
| Transfer Numeru identyfikacyjnego Odbiór i odłożenie             | Nie | Tak |
| Przyjmowanie i odkładanie pozycji z zamówienia przeniesienia                       | Tak | Nie |
| Przyjęcie i odłożenie wiersza zamówienia przeniesienia                       | Tak | Nie |
| Przyjęcie zamówienia zakupu z dostawą z niedoborem                      | <p>Tak, jeśli nie istnieje zamówienie magazynowe</p><p>Nie, jeśli istnieje zamówienie magazynowe</p> | Tak, ale tylko przez zgłoszenie wniosku o anulowanie z centrum |
| Przyjęcie zamówienia zakupu z dostawą z nadmiarem                       | <p>Tak, jeśli nie istnieje zamówienie magazynowe</p><p>Nie, jeśli istnieje zamówienie magazynowe</p> | Tak  |
| Przyjęcie z utworzeniem pracy *przeładunku kompletacyjnego*                 | <p>Tak, jeśli nie istnieje zamówienie magazynowe</p><p>Nie, jeśli istnieje zamówienie magazynowe</p> | Nie |
| Przyjęcie z utworzeniem pracy *zlecenia kontroli jakości*                  | <p>Tak, jeśli nie istnieje zamówienie magazynowe</p><p>Nie, jeśli istnieje zamówienie magazynowe</p> | Nie |
| Przyjęcie z utworzeniem pracy *zlecenia wyrywkowej kontroli jakości*          | <p>Tak, jeśli nie istnieje zamówienie magazynowe</p><p>Nie, jeśli istnieje zamówienie magazynowe</p> | Nie |
| Przyjęcie z utworzeniem pracy *jakości w kontroli jakości*       | <p>Tak, jeśli nie istnieje zamówienie magazynowe</p><p>Nie, jeśli istnieje zamówienie magazynowe</p> | Nie |
| Przyjęcie z utworzeniem zlecenia kontroli jakości                            | <p>Tak, jeśli nie istnieje zamówienie magazynowe</p><p>Nie, jeśli istnieje zamówienie magazynowe</p> | Nie |
| Przetwarzanie pracy — skierowane przez *odłożenie klastra*                 | Tak | Nie |
| Przetwarzanie pracy z *szybkim pobraniem*                               | Tak | Nie |
| Anuluj pracę (przychodzące)                                            | <p>Tak, jeśli nie istnieje zamówienie magazynowe</p><p>Nie, jeśli istnieje zamówienie magazynowe</p> | <p>Tak, ale tylko gdy zaznaczenie opcji <b>Wyrejestrowywanie paragonu podczas anulowania pracy</b> (na stronie <b>parametrów zarządzania magazynem</b>) zostanie usunięte</p> |
| Ładowanie numeru identyfikacyjnego                                           | Tak | Tak |

### <a name="warehouse-operations-and-exception-handing"></a>Operacje magazynowe i przekazywanie wyjątków

W poniższej tabeli pokazano, które operacje magazynowe i obsługa wyjątków są obsługiwane i gdzie są obsługiwane, gdy obciążenie pracą w ramach zarządzania magazynem jest używane w jednostkach skali w chmurze i krawędziach.

| Przetwarzaj                                            | Piasta | Obciążenie pracą dla wykonania w magazynie w ramach jednostki skalowania |
|----------------------------------------------------|-----|------------------------------|
| Zapytanie o numer identyfikacyjny                              | Tak | Tak                          |
| Zapytanie o pozycję                                       | Tak | Tak                          |
| Zapytanie o lokalizację                                   | Tak | Tak                          |
| Zmień magazyn                                   | Tak | Tak                          |
| Transakcje                                           | Tak | Tak                          |
| Przeniesienie według szablonu                               | Tak | Tak                          |
| Przeniesienie magazynu                                 | Tak | Nie                           |
| Tworzenie zamówienia przeniesienia z aplikacji magazynu           | Tak | Nie                           |
| Korekta (wejście/wyjście)                                | Tak | Tak, ale nie dla skorygowanego scenariusza, w którym rezerwacja zapasów musi zostać usunięta przy użyciu ustawienia **Usuń rezerwacje** w typach korekt zapasów</p>                           |
| Zmiana stanu zapasów                            | Tak | Nie                           |
| Przetwarzanie rozbieżności w inwentaryzacji ciągłej | Tak | Tak                           |
| Ponowny druk etykiety (drukowanie etykiet numeru identyfikacyjnego)             | Tak | Tak                          |
| Kompilacja numerów identyfikacyjnych                                | Tak | Nie                           |
| Przerwa dotycząca numeru identyfikacyjnego                                | Tak | Nie                           |
| Spakuj do zagnieżdżonych numerów identyfikacyjnych                      | Tak | Nie                           |
| Zaewidencjonowanie kierowcy                                    | Tak | Nie                           |
| Wyewidencjonowanie kierowcy                                   | Tak | Nie                           |
| Zmień kod dyspozycji partii                      | Tak | Tak                          |
| Wyświetl listę otwartych prac                             | Tak | Tak                          |
| Przetwarzanie uzupełniania zapasów — minimum/maksimum i próg strefy| Tak <p>Rekomendacje nie powinny uwzględniać tych samych lokalizacji jako części zapytań</p>| Tak                          |
| Przetwarzanie uzupełnienia zapasów na przedziały                  | Tak  | Tak<p>Należy pamiętać, że ustawienia muszą zostać wykonane dla jednostki skali</p>                           |
| Zablokuj i Odblokuj pracę                             | Tak | Tak                          |
| Zmień użytkownika                                        | Tak | Tak                          |
| Zmień pulę pracy w pracy                           | Tak | Tak                          |
| Anuluj pracę                                        | Tak | Tak                          |

### <a name="production"></a>Produkcyjne

W poniższej tabeli podsumowano, które scenariusze produkcyjne zarządzania magazynem są obecnie obsługiwane w przypadku obciążeń jednostek skalowania.

| Przetwarzaj | Piasta | Obciążenie pracą dla wykonania w magazynie w ramach jednostki skalowania |
|---------|-----|----------------------------------------------|
| Przetwarzanie dokumentów źródłowych zleceń produkcyjnych    | Tak | Nie |
| Zwolnij do magazynu                           | Tak | Nie |
| Rozpocznij zlecenie produkcyjne                         | Tak | Tak|
| Tworzenie zamówień magazynowych                        | Tak | Nie |
| Prośba o anulowanie wierszy zamówień magazynowych        | Tak | Nie, ale wniosek zostanie zatwierdzony lub odrzucony |
| Raportowanie jako wyroby gotowe i wyroby gotowe odłożone | <p>Tak, jeśli nie istnieje zamówienie magazynowe</p><p>Nie, jeśli istnieje zamówienie magazynowe</p> | Tak|
| Odłożenie produktu ubocznego i produktu towarzyszącego             | <p>Tak, jeśli nie istnieje zamówienie magazynowe</p><p>Nie, jeśli istnieje zamówienie magazynowe</p> | Tak|
| Rejestruj zużycie materiałów                  | Tak | Tak|
| Przetwarzanie produkcji w ramach grupy czynności                     | Tak | Nie |
| Pobranie surowca                           | Tak | Nie |
| Kanban odłożone                                | Tak | Nie |
| Pobieranie Kanban                                 | Tak | Nie |
| Pusta karta Kanban                                   | Tak | Nie |
| Odpadki produkcji                               | Tak | Nie |
| Produkcja ostatniej palety                         | Tak | Nie |
| Uzupełnianie zapasów surowców                     | Nie  | Nie |

## <a name="maintaining-scale-units-for-warehouse-execution"></a>Zarządzenie jednostkami skalowania na potrzeby wykonania w magazynie

Kilka zadań wsadowych uruchamianych jest zarówno dla centrum, jak i jednostki skali.

W rozmieszczeniu centrum można ręcznie zarządzać następującymi zadaniami wsadowymi:

- Zadaniami wsadowymi można zarządzać w obszarze **Zarządzanie magazynem \> Zadania okresowe \> Zarządzanie obciążeniem backoffice**:

    - Procesor komunikatów jednostki skalowania do piasty
    - Rejestruj przyjęcia zamówień źródłowych
    - Zakończ zamówienia magazynowe
    - Generuj brakujące wychodzące zamówienia magazynu

- Zadaniami wsadowymi można zarządzać w obszarze **Zarządzanie magazynem \> Zadania okresowe \> Zarządzanie obciążeniem**:

    - Procesor komunikatów piasty magazynu do jednostki skalowania
    - Przetwarzanie przyjęć wierszy zamówienia magazynowego dla księgowania przyjęć magazynowych

Na wdrożeniach jednostek skalowania możesz zarządzać tymi zadaniami wsadowymi można zarządzać w obszarze **Zarządzanie magazynem \> Zadania okresowe \> Zarządzanie obciążeniem**:

- Przetwórz rekordy tabeli grupy czynności
- Procesor komunikatów piasty magazynu do jednostki skalowania
- Przetwarzanie przyjęć wierszy zamówienia magazynowego dla księgowania przyjęć magazynowych

[!INCLUDE [cloud-edge-privacy-notice](../../includes/cloud-edge-privacy-notice.md)]

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
