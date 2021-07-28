---
title: Obciążenia pracą dotyczące zarządzania magazynem dla jednostek skalowania chmury i urządzenia brzegowego
description: Ten temat zawiera informacje o funkcji umożliwiającej skalowanie jednostek miar na uruchamianie wybranych procesów z poziomu obciążenia pracą w module Zarządzanie magazynem.
author: perlynne
ms.date: 04/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PurchTable, SysSecRolesEditUsers, SysWorkloadDuplicateRecord
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: SCM
ms.author: perlynne
ms.search.validFrom: 2020-10-06
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: dc065684952cbbe2a324b766dc8c465371cdb49d
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/06/2021
ms.locfileid: "6345507"
---
# <a name="warehouse-management-workloads-for-cloud-and-edge-scale-units"></a>Obciążenia pracą dotyczące zarządzania magazynem dla jednostek skalowania chmury i urządzenia brzegowego

[!include [banner](../includes/banner.md)]

> [!WARNING]
> Nie wszystkie funkcje zarządzania magazynem w firmie są w pełni obsługiwane w przypadku magazynów, w których jest uruchomione obciążenie pracą z jednostką skalowania. Należy pamiętać, aby użyć tylko tych procesów, które opisano w tym temacie jako obsługiwane.

## <a name="warehouse-execution-on-scale-units"></a>Wykonanie magazynowe w jednostkach skali

Ta funkcja umożliwia jednostkom miary skalowanie uruchamianie wybranych procesów z poziomu funkcji zarządzania magazynem.

W tym temacie wykonania zarządzania magazynem w magazynie zdefiniowanym jako jednostka skali określa się jako *system realizacji magazynu* (*Wes*).

## <a name="prerequisites"></a>Wymagania wstępne

Musi istnieć centrum i jednostka skali dla Dynamics 365 Supply Chain Management, która została wdrożona wraz z obciążeniem zarządzania magazynem. Aby uzyskać więcej informacji na temat architektury i procesu wdrożenia, zobacz [Użyj jednostek skalowania, aby zwiększyć odporność obciążeń związanych z zarządzaniem łańcuchem dostaw](cloud-edge-landing-page.md).

## <a name="how-the-wes-workload-works-on-scale-units"></a>Sposób działania obciążenia pracą WES na jednostkach skali

W przypadku procesów w ramach zadań zarządzania magazynem dane są synchronizowane między centrum a jednostkami miary skali.

Jednostka skali może obsługiwać tylko te dane, które są z nią właścicielem. Pojęcie własności danych dla jednostek skali ułatwia zapobieganie konfliktom z wieloma wzorcami. Dlatego ważne jest, aby zrozumieć, które procesy są własnością koncentratora i które są własnością jednostek skali.

Jednostki skali dzielą się na następujące dane:

- **Dane przetwarzania grupy wysyłek** — wybrane metody przetwarzania grupy czynności są obsługiwane jako część przetwarzania grupy czynności skali.
- **Dane przetwarzania pracy** — praca magazynowa utworzona na jednostkę skalowania będzie należeć do określonej jednostki skalowania. Obsługiwane są następujące typy przetwarzania zlecenia:

  - **Przesunięcia zapasów** (ręczne przenoszenie i przenoszenie według pracy według szablonu)
  - **Inwentaryzacja ciągła** oraz proces zatwierdzania/odrzucania w ramach operacji inwentaryzacji
  - **Zamówienia zakupu** (praca odłożenia za pośrednictwem zamówienia magazynowego, jeśli zamówienia zakupu nie są skojarzone z ładunkami)
  - **Zamówienia zakupu** (prosta praca pobierania i ładowania)
  - **Zamówienia przeniesienia** (tylko wychodzące z prostą pracą pobierania i ładowania)

- **Dane przyjęcia zamówienia magazynowego** — te dane są używane tylko dla zamówień zakupu, które zostały zwolnione do magazynu.
- **Dane numeru identyfikacyjnego** — Tablice rejestracyjne można tworzyć zarówno na piaście, jak i na jednostkach wagi. Dostarczono dedykowaną obsługę konfliktów. 

    > [!IMPORTANT]
    > Dane tablicy rejestracyjnej nie są specyficzne dla magazynu. Jeśli ten sam numer rejestracyjny zostanie utworzony zarówno na koncentratorze, jak i jednostce wagi podczas tego samego cyklu synchronizacji, następna synchronizacja nie powiedzie się. W takim przypadku wybierz opcje **Administrowanie systemem > Informacje > Informacje obciążenia pracą > Zduplikowane rekordy**, w których można przeglądać i scalać dane.

## <a name="outbound-process-flow"></a>Przepływ procesu wychodzącego

Piasta posiada następujące dane:

- Wszystkie dokumenty źródłowe, takie jak zamówienia sprzedaży i zamówienia przeniesienia
- Alokacja zamówienia i przetwarzanie ładunku wychodzącego
- Wydanie do magazynu, tworzenie wysyłek, tworzenie grupy czynności i procesy finalizacji grupy czynności

Jednostki te są zależne od rzeczywistego przetwarzania grupy czynności (np. przydziału pracy, pracy uzupełniania i tworzenia popytu) po wydaniu grupy czynności. W związku z tym pracownicy magazynu mogą przetwarzać pracę wychodzącą za pomocą aplikacji Warehouse Management połączonej z jednostką miary skali.

![Przetwarzanie przepływu grupy czynności.](./media/wes-wave-processing-ga.png "Przetwarzanie przepływu grupy czynności")

### <a name="process-work-and-ship"></a>Przetwarzanie pracy i wysyłki

Gdy tylko ostateczny proces pracy odłoży zapasy w końcowej lokalizacji wysyłki (bramie dokowej), jednostka skalowania wysyła do centrum sygnał, aby zaktualizować transakcje magazynowe dokumentu źródłowego na stan *Pobrano*. Dopóki ten proces nie zostanie uruchomiony i nie zostanie zsynchronizowany ponownie, stan dostępnych zapasów dla obciążenia jednostki skalowania będzie fizycznie zarezerwowany na poziomie magazynu.

Gdy centrum zaktualizuje stan transakcji na *Pobrano*, może przetwarzać potwierdzenie wysyłki wychodzącej oraz skojarzony z nim dokument dostawy sprzedaży lub wysyłkę zamówienia przeniesienia dla obciążenia pracą.

![Przepływ przetwarzania wychodzącego.](./media/WES-outbound-processing-19.png "Przepływ przetwarzania wychodzącego")

## <a name="inbound-process-flow"></a>Przepływ procesu przychodzącego

Piasta posiada następujące dane:

- Wszystkie dokumenty źródłowe, takie jak zamówienia zakupu i zamówienia zwrotu
- Przetwarzanie ładowania przychodzącego
- Wszystkie aktualizacje fizyczne i finansowe

> [!NOTE]
> Przychodzący przepływ zamówienia zakupu różni się pod względem koncepcji od przepływu wychodzącego. Ten sam magazyn można obsługiwać w jednostce skalowania lub centrum w zależności od tego, czy zamówienie zakupu zostało zwolnione do magazynu, czy nie. Po zwolnieniu zamówienia do magazynu można pracować z tym zamówieniem wyłącznie po zalogowaniu się do jednostki skalowania.
>
> Jeśli jest używana funkcja *Zwalniania do magazynu*, tworzone są [*zamówienia magazynowe*](cloud-edge-warehouse-order.md), a do jednostki skali jest przypisana własność powiązanego przepływu przyjęcia. Centrum nie będzie mogło zarejestrować przyjęcia przychodzącego.

Należy się zalogować do centrum, aby zainicjować proces *zwalniania do magazynu*. Przejdź na jedną z następujących stron, aby go uruchomić lub zaplanować:

- **Zaopatrzenie i sourcing > Zamówienia zakupu > Wszystkie zamówienia zakupu > Magazyn > Akcje > Zwolnij do magazynu**
- **Zarządzanie magazynem > Zwolnij do magazynu > Automatyczne zwalnianie zamówień zakupu**

W przypadku korzystania z funkcji **Automatyczne zwalnianie zamówień zakupu** można wybierać określone wiersze zamówienia zakupu w oparciu o kwerendę. Typowym scenariuszem byłoby skonfigurowanie powtarzającego się zadania wsadowego, które zwalnia wszystkie potwierdzone wiersze zamówienia zakupu, które mają nadejść następnego dnia.

Pracownicy magazynu mogą uruchomić proces odbioru za pomocą aplikacji Warehouse Management połączonej z jednostką miary skali. Dane są następnie rejestrowane przez jednostkę skali i podawane w odniesieniu do przychodzącego zamówienia magazynowego. Tworzenie i przetwarzanie kolejnych odłożeń będzie również obsługiwane przez jednostkę skali.

Jeśli nie są używane *procesy magazynowe*, a w związku z tym nie są używane *zamówienia magazynowe*, centrum może przetwarzać przyjęcie magazynowe i przetwarzanie pracy niezależnie od jednostek skalowania.

![Przepływ procesu przychodzącego.](./media/wes-inbound-ga.png "Przepływ procesu przychodzącego")

Jeśli rejestrowanie przychodzące jest wykonywane w procesie przyjęcia przy użyciu aplikacji magazynowej w odniesieniu do zamówienia magazynowego jednostki skalowania, obciążenie jednostki skalowania będzie sygnalizować centrum, aby zaktualizować stan powiązanej transakcji wiersza zamówieni zakupu na *Zarejestrowane*. Po zakończeniu tego zadania będzie można uruchomić w centrum przyjęcie produktu zamówienia zakupu.

![Przepływ przetwarzania przychodzącego.](./media/WES-inbound-processing-19.png "Przepływ przetwarzania przychodzącego")

## <a name="supported-processes-and-roles"></a>Obsługiwane procesy i role

Nie wszystkie procesy zarządzania magazynem są obsługiwane w WES obciążeniu jednostki skali. Dlatego zaleca się przypisanie ról spełniających funkcje dostępne dla każdego użytkownika.

Aby ułatwić ten proces, do przykładowej roli o nazwie *Menedżer magazynu podczas obciążenia pracą* dołączono dane demonstracyjne w sekcji **Administrowanie systemem \> Zabezpieczenia \> Konfiguracja zabezpieczeń**. Celem tej roli jest umożliwienie menedżerom magazynu dostępu do WES na jednostce skali. Rola umożliwia dostęp do stron, które są istotne w kontekście obciążenia pracą obsługiwanego przez jednostkę skali.

Role użytkowników na jednostce skali są przypisywane jako część początkowej synchronizacji danych od centrum do jednostki skali.

Aby zmodyfikować role przypisane do użytkownika, przejdź do **Administracja systemu \> Zabezpieczenia \> Przypisz użytkowników do ról**. Użytkownicy, którzy działają jako kierownicy magazynu tylko w jednostkach skali, powinni mieć przypisany tylko *Menedżer magazynu w* roli obciążenia. Takie podejście zapewni, że użytkownicy ci będą mieli dostęp tylko do obsługiwanych funkcji systemu. Umożliwia usunięcie wszelkich innych ról przypisanych do tych użytkowników.

Użytkownicy, którzy działają jako kierownicy magazynu tylko w jednostkach skali, powinni mieć przypisany tylko *Menedżer magazynu w* roli obciążenia. Należy pamiętać, że ta rola udziela pracownikom magazynowym dostępu do funkcji (takich jak przetwarzanie odbioru zamówień przeniesienia), które są wyświetlane w interfejsie użytkownika (UI), ale nie są obecnie obsługiwane w jednostkach skali.

## <a name="supported-wes-processes"></a>Obsługiwane procesy WES

Następujące procesy wykonania magazynu mogą być włączone dla WES obciążenia pracą jednostki skali:

- Wybrane metody grupy czynności dla zamówień sprzedaży i przeniesienia (alokacja, uzupełnianie zapasów popytu, konteneryzacja, tworzenie pracy i drukowanie etykiet grupy czynności)

- Przetwarzanie pracy magazynowej zamówień sprzedaży i przeniesienia przy użyciu aplikacji magazynu (łącznie z pracą uzupełniania zapasów)
- Badanie dostępnych zapasów przy użyciu aplikacji magazynowej
- Tworzenie i uruchamianie przesunięć magazynowych przy użyciu aplikacji magazynowej
- Tworzenie i przetwarzanie pracy inwentaryzacji ciągłej za pomocą aplikacji magazynowej
- Wykonywanie korekt zapasów przy użyciu aplikacji magazynowej
- Rejestrowanie zamówień zakupu i wykonywanie odłożenia pracy przy użyciu aplikacji magazynowej

Następujące typy zleceń roboczych są obecnie obsługiwane w przypadku obciążeń WES w wdrożeniach jednostek skali:

- Zamówienia sprzedaży
- Wydanie przeniesienia
- Uzupełnianie zapasów
- Przesunięcie magazynowe
- Inwentaryzacja ciągła
- Zamówienia zakupu (połączone z zamówieniami magazynowymi)

Obecnie żadne inne typy przetwarzania dokumentów źródłowych nie są obsługiwane w jednostkach skali. Na przykład w przypadku obciążenia pracą WES w jednostce skalowania nie można wykonać procesu przyjęcia zamówienia przeniesienia (przyjęcie przeniesienia) i musi ono zostać przetworzone przez wystąpienie centrum.

> [!NOTE]
> Elementy menu i przyciski menu urządzenia przenośnego dla nieobsługiwanych funkcji nie są pokazywane w _aplikacji Warehouse Management_, jeśli są połączone z wdrożeniem jednostki skalowania.

> [!WARNING]
> W przypadku uruchamiania obciążenia pracą na jednostkę skali nie można uruchamiać nieobsługiwanych procesów dla określonego magazynu w centrali. Tabele podane dalej w tym temacie zawierają opis obsługiwanych możliwości.
>
> Wybrane typy pracy magazynowej można tworzyć zarówno w centrum, jak i na jednostkach skalowania, ale mogą być dostępne tylko przez centrum lub jednostkę skalowania (wdrożenie, które utworzyło dane).
>
> Nawet jeśli określony proces jest obsługiwany przez jednostkę skalowania, należy pamiętać, że wszystkie potrzebne dane mogą nie zostać zsynchronizowane z centrum do jednostki skalowania lub z jednostki skalowania do centrum, co może doprowadzić do nieoczekiwanego przetworzenia systemu. Przykłady:
> 
> - Jeśli używasz zapytania dyrektywy lokalizacji, które łączy rekord tabeli danych, który istnieje tylko podczas wdrażania centrum.
> - W przypadku używania funkcji obciążenia wolumetrycznego dla lokalizacji i/lub stanu okalizacji. Te dane nie zostaną zsynchronizowane między wdrożeniami, dlatego będą działać tylko podczas aktualizowania dostępnych zapasów lokalizacji dla jednego z wdrożeń.

Następująca funkcja zarządzania magazynem nie jest obecnie obsługiwana w obciążeniach jednostkach skali:

- Przychodzące przetwarzanie wierszy zamówienia zakupu przypisanych do ładunku
- Przychodzące przetwarzanie zamówień zakupu dla projektu
- Przetwarzanie przychodzące i wychodzące dla towarów, które mają aktywne wymiary śledzenia **Właściciel** i/lub **Numer seryjny**
- Przetwarzanie zapasów z wartością stanu blokowania
- Zmiana stanu zapasów w trakcie dowolnego procesu przemieszczania pracy
- Elastyczne rezerwacja wymiarów na poziomie magazynu dla zamówienia
- Korzystanie z funkcji *stanu lokalizacji w magazynie* (dane nie są synchronizowane między wdrożeniami)
- Korzystanie z funkcji *pozycjonowania dla numeru identyfikacyjnego lokalizacji*
- Korzystanie z *filtrów produktów* i *grup filtrów produktów*, łącznie z ustawieniem **Liczba dni na mieszanie partii**
- Integracja z zarządzaniem jakością
- Przetwarzanie pozycji w ilości efektywnej
- Przetwarzanie z pozycjami włączonymi tylko dla zarządzania transportem (TMS)
- Przetwarzanie ujemnych dostępnych zapasów
- Przetwarzanie pracy magazynowej z niestandardowymi typami pracy
- Przetwarzanie pracy magazynowej z uwagami do wysyłki
- Przetwarzanie pracy magazynowej przy użyciu automatyzacji obsługi materiałów/magazynu
- Korzystanie z obrazu danych produktu głównego (na przykład w aplikacji Warehouse Management)

> [!WARNING]
> Niektóre funkcje magazynu nie będą dostępne dla magazynów, w których jest uruchomione obciążenie pracą zarządzania magazynem w jednostce skalowania, a ponadto nie są obsługiwane w centrum ani w obciążeniu jednostki skalowania.
> 
> Inne możliwości mogą zostać przetworzone dla obu tych obiektów, ale będą wymagać ostrożniej pracy w niektórych scenariuszach, na przykład w przypadku aktualizacji dostępnych zapasów dla tego samego magazynu zarówno w centrum, jak i jednostce skalowania z powodu asynchronicznej aktualizacji danych.
> 
> Określone funkcje (takie jak *praca z blokadą*) obsługiwane zarówno w jednostkach centrum, jak i skalowania będą obsługiwane tylko przez właściciela danych.

### <a name="outbound-supported-only-for-sales-and-transfer-orders"></a>Wychodzące (obsługiwane tylko dla zamówień sprzedaży i przeniesienia)

W poniższej tabeli pokazano, które funkcje wychodzące są obsługiwane i gdzie są obsługiwane, gdy obciążenie pracą w ramach zarządzania magazynem jest używane w jednostkach skali w chmurze i krawędziach.

| Przetwarzaj                                                      | Piasta | WES obciążenie jednostki skali |
|--------------------------------------------------------------|-----|------------------------------|
| Przetwarzanie dokumentu źródłowego                                   | Tak | Nr |
| Zarządzanie procesem załadunku i transportu                | Tak | Nr |
| Zwolnij do magazynu                                         | Tak | Nr |
| Planowany przeładunek kompletacyjny                                        | Nr  | Nr |
| Konsolidacja wysyłki                                       | Tak | Nr |
| Przetwarzanie grupy wysyłek                                     | Tak, ale tylko inicjowanie i finalizacja grupy czynności są obsługiwane w centrum. Oznacza to, że wychodzące przetwarzanie zamówień przeniesienia i zamówień sprzedaży może być obsługiwane tylko przez jednostkę skali.|<p>Nie, inicjowanie i finalizacja są obsługiwane przez centrum, a proces **tworzenia i sortowania ładunku** nie jest obsługiwany<p><b>Uwaga: </b>dostęp do centrum jest wymagany do sfinalizowania stanu grupy czynności w ramach przetwarzania grupy czynności.</p> |
| Obsługa wysyłek dla grupy czynności                                  | Tak | Nr |
| Przetwarzanie pracy magazynowej (z uwzględnieniem numeru identyfikacyjnego na płycie licencyjnej)        | Nr  | <p>Tak, ale tylko dla wyżej wymienionych obsługiwanych możliwości. |
| Wybór grupy                                              | Nr  | Tak|
| Ręczne przetwarzanie pakowania, w tym przetwarzanie pracy „Pobieranie zapakowanych kontenerów” | Nr <P>Niektóre operacje mogą być wykonywane po początkowym procesie pobierania obsługiwanym przez jednostkę skalowania, ale nie jest to zalecane z powodu następujących zablokowanych operacji.</p>  | Nr |
| Usuń kontener z grupy                                  | Nr  | Nr |
| Przetwarzanie sortowania wychodzących                                  | Nr  | Nr |
| Drukowanie dokumentów powiązanych z ładunkiem                           | Tak | Nr |
| List przewozowy i generowanie WPW                            | Tak | Nr |
| Potwierdzenie wysyłki                                             | Tak | Nr |
| Potwierdzenie wysyłki z „potwierdzeniem i przeniesieniem”            | Nr  | Nr |
| Przetwarzanie dokumentów dostawy i faktur                        | Tak | Nr |
| Szybkie pobranie (zamówienia sprzedaży i przeniesienia)                    | Nr  | Nr |
| Nadmiarowe pobranie (zamówienia sprzedaży i przeniesienia)                     | Nr  | Nr |
| Zmiana lokalizacji pracy (zamówienia sprzedaży i przeniesienia)         | Nr  | Tak|
| Zakończenie pracy (zamówienia sprzedaży i przeniesienia)                    | Nr  | Tak|
| Drukowanie raportu pracy                                            | Tak | Nr |
| Etykieta grupy czynności                                                   | Nr  | Tak|
| Podział pracy                                                   | Nr  | Tak|
| Przetwarzanie pracy — skierowane przez transport ładunku            | Nr  | Nr |
| Zmniejsz ilość pobraną                                       | Nr  | Nr |
| Wycofaj pracę                                                 | Nr  | Nr |
| Wycofaj potwierdzenie wysyłki                                | Tak | Nr |

### <a name="inbound"></a>Przychodzące

W poniższej tabeli pokazano, które funkcje przychodzące są obsługiwane i gdzie są obsługiwane, gdy obciążenie pracą w ramach zarządzania magazynem jest używane w jednostkach skali w chmurze i krawędziach.

| Przetwarzaj                                                          | Piasta | WES obciążenie jednostki skali<BR>*(Pozycje oznaczone jako „Tak” dotyczą tylko zamówień magazynowych)*</p> |
|------------------------------------------------------------------|-----|----------------------------------------------------------------------------------|
| Przetwarzanie &nbsp;dokumentu&nbsp; źródłowego                             | Tak | Nr |
| Zarządzanie procesem załadunku i transportu                    | Tak | Nr |
| Potwierdzenie wysyłki wychodzącej                                    | Tak | Nr |
| Zwolnienie zamówienia zakupu do magazynu (przetwarzanie zamówienia magazynowego) | Tak | Nr |
| Anulowanie wierszy zamówienia magazynowego<p>Należy zauważyć, że jest to obsługiwane tylko wtedy, gdy nie utworzono żadnej rezerwacji dla wiersza</p> | Tak | Nr |
| Przyjęcie i odłożenie pozycji z zamówienia zakupu                       | <p>Tak, &nbsp;gdy &nbsp;nie ma&nbsp; zamówienia magazynowego</p><p>Nie, jeśli istnieje zamówienie magazynowe</p> | <p>Tak, jeśli zamówienie zakupu nie jest częścią <i>ładunku</i></p> |
| Przyjęcie i odłożenie wiersza zamówienia zakupu                       | <p>Tak, jeśli nie istnieje zamówienie magazynowe</p><p>Nie, jeśli istnieje zamówienie magazynowe</p> | <p>Tak, jeśli zamówienie zakupu nie jest częścią <i>ładunku</i></p></p> |
| Zwróć odebrane zamówienie i odłóż                              | Tak | Nr |
| Przyjęcie i odłożenie mieszanego numeru identyfikacyjnego                       | <p>Tak, jeśli nie istnieje zamówienie magazynowe</p><p>Nie, jeśli istnieje zamówienie magazynowe</p> | Nr |
| Odbierana pozycja ładunku                                              | <p>Tak, jeśli nie istnieje zamówienie magazynowe</p><p>Nie, jeśli istnieje zamówienie magazynowe</p> | Nr |
| Odbieranie numeru identyfikacyjnego i odłożenie                             | <p>Tak, jeśli nie istnieje zamówienie magazynowe</p><p>Nie, jeśli istnieje zamówienie magazynowe</p> | Nr |
| Przyjmowanie i odkładanie pozycji z zamówienia przeniesienia                       | Tak | Nr |
| Przyjęcie i odłożenie wiersza zamówienia przeniesienia                       | Tak | Nr |
| Anuluj pracę (przychodzące)                                            | <p>Tak, jeśli nie istnieje zamówienie magazynowe</p><p>Nie, jeśli istnieje zamówienie magazynowe</p> | <p>Tak, ale tylko gdy zaznaczenie opcji <b>Wyrejestrowywanie paragonu podczas anulowania pracy</b> (na stronie <b>parametrów zarządzania magazynem</b>) zostanie usunięte</p> |
| Zamówienie zakupu — przetwarzanie dokumentu przyjęcia produktów                        | Tak | Nr |
| Przyjęcie zamówienia zakupu z dostawą z niedoborem                      | <p>Tak, jeśli nie istnieje zamówienie magazynowe</p><p>Nie, jeśli istnieje zamówienie magazynowe</p> | Tak, ale tylko przez zgłoszenie wniosku o anulowanie z centrum |
| Przyjęcie zamówienia zakupu z dostawą z nadmiarem                       | <p>Tak, jeśli nie istnieje zamówienie magazynowe</p><p>Nie, jeśli istnieje zamówienie magazynowe</p> | Tak  |
| Przyjęcie z utworzeniem pracy *przeładunku kompletacyjnego*                 | <p>Tak, jeśli nie istnieje zamówienie magazynowe</p><p>Nie, jeśli istnieje zamówienie magazynowe</p> | Nr |
| Przyjęcie z utworzeniem pracy *zlecenia kontroli jakości*                  | <p>Tak, jeśli nie istnieje zamówienie magazynowe</p><p>Nie, jeśli istnieje zamówienie magazynowe</p> | Nr |
| Przyjęcie z utworzeniem pracy *zlecenia wyrywkowej kontroli jakości*          | <p>Tak, jeśli nie istnieje zamówienie magazynowe</p><p>Nie, jeśli istnieje zamówienie magazynowe</p> | Nr |
| Przyjęcie z utworzeniem pracy *jakości w kontroli jakości*       | <p>Tak, jeśli nie istnieje zamówienie magazynowe</p><p>Nie, jeśli istnieje zamówienie magazynowe</p> | Nr |
| Przyjęcie z utworzeniem zlecenia kontroli jakości                            | <p>Tak, jeśli nie istnieje zamówienie magazynowe</p><p>Nie, jeśli istnieje zamówienie magazynowe</p> | Nr |
| Przetwarzanie pracy — skierowane przez *odłożenie klastra*                 | Tak | Nr |
| Przetwarzanie pracy z *szybkim pobraniem*                               | Tak | Nr |
| Ładowanie numeru identyfikacyjnego                                           | Tak | Tak |

### <a name="warehouse-operations-and-exception-handing"></a>Operacje magazynowe i przekazywanie wyjątków

W poniższej tabeli pokazano, które operacje magazynowe i obsługa wyjątków są obsługiwane i gdzie są obsługiwane, gdy obciążenie pracą w ramach zarządzania magazynem jest używane w jednostkach skali w chmurze i krawędziach.

| Przetwarzaj                                            | Piasta | WES obciążenie jednostki skali |
|----------------------------------------------------|-----|------------------------------|
| Zapytanie o numer identyfikacyjny                              | Tak | Tak                          |
| Zapytanie o pozycję                                       | Tak | Tak                          |
| Zapytanie o lokalizację                                   | Tak | Tak                          |
| Zmień magazyn                                   | Tak | Tak                          |
| Transakcje                                           | Tak | Tak                          |
| Przeniesienie według szablonu                               | Tak | Tak                          |
| Przeniesienie magazynu                                 | Tak | Nr                           |
| Tworzenie zamówienia przeniesienia z aplikacji magazynu           | Tak | Nr                           |
| Korekta (wejście/wyjście)                                | Tak | Tak, ale nie dla skorygowanego scenariusza, w którym rezerwacja zapasów musi zostać usunięta przy użyciu ustawienia **Usuń rezerwacje** w typach korekt zapasów.</p>                           |
| Zmiana stanu zapasów                            | Tak | Nr                           |
| Przetwarzanie rozbieżności w inwentaryzacji ciągłej | Tak | Tak                           |
| Ponowny druk etykiety (drukowanie etykiet numeru identyfikacyjnego)             | Tak | Tak                          |
| Kompilacja numerów identyfikacyjnych                                | Tak | Nr                           |
| Przerwa dotycząca numeru identyfikacyjnego                                | Tak | Nr                           |
| Spakuj do zagnieżdżonych numerów identyfikacyjnych                                | Tak | Nr                           |
| Zaewidencjonowanie kierowcy                                    | Tak | Nr                           |
| Wyewidencjonowanie kierowcy                                   | Tak | Nr                           |
| Zmień kod dyspozycji partii                      | Tak | Tak                          |
| Wyświetl listę otwartych prac                             | Tak | Tak                          |
| Konsoliduj numery identyfikacyjne                         | Tak | Nr                           |
| Przetwarzanie uzupełniania zapasów — minimum/maksimum i próg strefy| Tak <p>Rekomendacje nie powinny uwzględniać tych samych lokalizacji jako części zapytań</p>| Tak                          |
| Przetwarzanie uzupełnienia zapasów na przedziały                  | Tak  | Tak<p>Należy pamiętać, że ustawienia muszą zostać wykonane dla jednostki skali</p>                           |
| Zablokuj i Odblokuj pracę                             | Tak | Tak                          |
| Zmień użytkownika                                        | Tak | Tak                          |
| Zmień pulę pracy w pracy                           | Tak | Tak                          |
| Anuluj pracę                                        | Tak | Tak                          |

### <a name="production"></a>Produkcyjne

W poniższej tabeli podsumowano, które scenariusze produkcyjne zarządzania magazynem są (i nie są) obecnie obsługiwane w przypadku obciążeń jednostek skalowalnych.

| Przetwarzaj | Piasta | WES obciążenie jednostki skali |
|---------|-----|------------------------------|
| Raportowanie jako wyroby gotowe i wyroby gotowe odłożone | Tak | Tak |
| Odłożenie produktu ubocznego i produktu towarzyszącego | Tak | Tak |
| <p>Wszystkie inne procesy zarządzania magazynem, które są związane z produkcją, w tym:</p><li>Zwolnij do magazynu</li><li>Przetwarzanie produkcji w ramach grupy czynności</li><li>Pobranie surowca</li><li>Kanban odłożone</li><li>Pobieranie Kanban</li><li>Rozpocznij zlecenie produkcyjne</li><li>Odpadki produkcji</li><li>Produkcja ostatniej palety</li><li>Rejestruj zużycie materiałów</li><li>Pusta karta Kanban</li></ul> | Tak | Nr |

## <a name="maintaining-scale-units-for-wes"></a>Obsługa jednostek skali dla WES

Kilka zadań wsadowych uruchamianych jest zarówno dla centrum, jak i jednostki skali.

W rozmieszczeniu centrum można ręcznie zarządzać zadaniami wsadowymi. Zadaniami wsadowymi można zarządzać w obszarze **Zarządzanie magazynem \> Zadania okresowe \> Zarządzanie obciążeniem backoffice**:

- Procesor komunikatów jednostki skalowania do piasty
- Rejestruj przyjęcia zamówień źródłowych
- Zakończ zamówienia magazynowe

W obciążeniu w jednostce skali tymi zadaniami wsadowymi można zarządzać w obszarze **Zarządzanie magazynem \> Zadania okresowe \> Zarządzanie obciążeniem**:

- Przetwarzanie rekordów tabeli grupy czynności
- Procesor komunikatów piasty magazynu do jednostki skalowania
- Przetwórz żądania aktualizacji ilości dla wierszy zamówienia magazynowego

[!INCLUDE [cloud-edge-privacy-notice](../../includes/cloud-edge-privacy-notice.md)]

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
