---
title: Obciążenia pracą dotyczące zarządzania magazynem dla jednostek skalowania chmury i urządzenia brzegowego
description: Ten temat zawiera informacje o funkcji umożliwiającej skalowanie jednostek miar na uruchamianie wybranych procesów z poziomu obciążenia pracą w module Zarządzanie magazynem.
author: perlynne
manager: tfeyr
ms.date: 10/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, SysSecRolesEditUsers
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: SCM
ms.author: perlynne
ms.search.validFrom: 2020-10-06
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 4ac76ad5cd88c35ac312b8e73d942a692f35c8aa
ms.sourcegitcommit: 8eefb4e14ae0ea27769ab2cecca747755560efa3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/13/2020
ms.locfileid: "4516854"
---
# <a name="warehouse-management-workloads-for-cloud-and-edge-scale-units"></a>Obciążenia pracą dotyczące zarządzania magazynem dla jednostek skalowania chmury i urządzenia brzegowego

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

> [!WARNING]
> Nie wszystkie funkcje biznesowe są w pełni obsługiwane w wersji zapoznawczej, gdy są używane jednostki skali obciążenia pracą. Należy pamiętać, aby użyć tylko tych procesów, które opisano w tym temacie jako obsługiwane.

## <a name="warehouse-execution-on-scale-units"></a>Wykonanie magazynowe w jednostkach skali

Ta funkcja umożliwia jednostkom miary skalowanie uruchamianie wybranych procesów z poziomu funkcji zarządzania magazynem. Jednostki skali chmury wykonują swoje obciążenie pracą w chmurze, korzystając z dedykowanych zdolności produkcyjnych w wybranym regionie Microsoft Azure. W przypadku jednostek skali krawędzi można uruchamiać pewne obciążenia niezależnie od pomieszczeń, nawet jeśli jednostki skalowania są tymczasowo odłączone od chmury.

W tym temacie wykonania zarządzania magazynem w magazynie zdefiniowanym jako jednostka skali określa się jako *system realizacji magazynu* (*Wes*).

## <a name="prerequisites"></a>Wymagania wstępne

Musi istnieć centrum i jednostka skali dla Dynamics 365 Supply Chain Management, która została wdrożona wraz z obciążeniem zarządzania magazynem. Aby uzyskać więcej informacji na temat architektury i procesu wdrożenia, zobacz [Zarządzanie jednostką skali chmurą i jej krawędzią przy produkcji i wykonywaniu zadań magazynowych](cloud-edge-landing-page.md).

## <a name="how-the-wes-workload-works-on-scale-units"></a>Sposób działania obciążenia pracą WES na jednostkach skali

W przypadku procesów w ramach zadań zarządzania magazynem dane są synchronizowane między centrum a jednostkami miary skali.

Jednostka skali może obsługiwać tylko te dane, które są z nią właścicielem. Pojęcie własności danych dla jednostek skali ułatwia zapobieganie konfliktom z wieloma wzorcami. Dlatego ważne jest, aby zrozumieć, które procesy są własnością koncentratora i które są własnością jednostek skali.

Jednostki skali dzielą się na następujące dane:

- **Dane przetwarzania grupy czynności** — wybrane metody przetwarzania grupy czynności są obsługiwane jako część przetwarzania grupy czynności skali.
- **Dane przetwarzania pracy** — obsługiwane są następujące typy przetwarzania zamówień pracy:

    - Przesunięcia zapasów (Ręczne przenoszenie i przenoszenie według pracy według szablonu)
    - Zamówienia zakupu (za pośrednictwem zamówienia magazynowego)
    - Tworzenie zlecenia pracy i pobierania zamówienia sprzedaży

- **Dane przyjęcia zamówienia magazynowego** — te dane są używane tylko dla zamówień zakupu, które są ręcznie zwalniane do magazynu.
- **Dane numeru identyfikacyjnego — numery identyfikacyjne** mogą być tworzone na koncentratorze i w jednostkach skali. Dostarczono dedykowaną obsługę konfliktów. Zauważ, że te dane nie są właściwe dla magazynu.

## <a name="outbound-process-flow"></a>Przepływ procesu wychodzącego

Piasta posiada następujące dane:

- Wszystkie dokumenty źródłowe, takie jak zamówienia sprzedaży i zamówienia przeniesienia
- Alokacja zamówienia i przetwarzanie ładunku wychodzącego
- Wydanie do magazynu, tworzenia wysyłek i procesów tworzenia grupy czynności

Jednostki te są zależne od rzeczywistego przetwarzania grupy czynności (np. przydziału pracy, pracy uzupełniania i tworzenia popytu) po wydaniu grupy czynności. W związku z tym pracownicy magazynu mogą przetwarzać pracę wychodzącą za pomocą aplikacji magazynowej połączonej z jednostką miary skali.

![Przetwarzanie przepływu grupy czynności](./media/wes_wave_processing_flow.png "Przetwarzanie przepływu grupy czynności")

## <a name="inbound-process-flow"></a>Przepływ procesu przychodzącego

Piasta posiada następujące dane:

- Wszystkie dokumenty źródłowe, takie jak zamówienia zakupu i zamówienia zwrotu
- Przetwarzanie ładowania przychodzącego

> [!NOTE]
> Przepływ przychodzącego zamówienia zakupu jest koncepcyjnie różny od przepływu wychodzącego, gdzie jednostka miary skali przetwarzania zależy od tego, czy zamówienie zostało zwolnione do magazynu.

Jeśli jest używana funkcja *zwalniania do magazynu*, tworzone są zamówienia magazynowe, a do jednostki skali jest przypisana własność powiązanego przepływu przyjęcia. Centrum nie będzie mogło zarejestrować przyjęcia przychodzącego.

Pracownicy magazynu mogą uruchomić proces odbioru za pomocą aplikacji magazynowej połączonej z jednostką miary skali. Dane są następnie rejestrowane przez jednostkę skali i podawane w odniesieniu do przychodzącego zamówienia magazynowego. Tworzenie i przetwarzanie kolejnych odłożeń będzie również obsługiwane przez jednostkę skali.

Jeśli nie są używane *procesy magazynowe*, a w związku z tym nie są używane *zamówienia magazynowe*, centrum może przetwarzać przyjęcie magazynowe i przetwarzanie pracy niezależnie od jednostek skalowania.

![Przepływ procesu przychodzącego](./media/wes_Inbound_flow.png "Przepływ procesu przychodzącego")

## <a name="supported-processes-and-roles"></a>Obsługiwane procesy i role

Nie wszystkie procesy zarządzania magazynem są obsługiwane w WES obciążeniu jednostki skali. Dlatego zaleca się przypisanie ról spełniających funkcje dostępne dla każdego użytkownika.

Aby ułatwić ten proces, do przykładowej roli o nazwie *Menedżer magazynu podczas obciążenia pracą* dołączono dane demonstracyjne w sekcji **Administrowanie systemem \> Zabezpieczenia \> Konfiguracja zabezpieczeń**. Celem tej roli jest umożliwienie menedżerom magazynu dostępu do WES na jednostce skali. Rola umożliwia dostęp do stron, które są istotne w kontekście obciążenia pracą obsługiwanego przez jednostkę skali.

Role użytkowników na jednostce skali są przypisywane jako część początkowej synchronizacji danych od centrum do jednostki skali.

Aby zmodyfikować role przypisane do użytkownika, przejdź do **Administracja systemu \> Zabezpieczenia \> Przypisz użytkowników do ról** na jednostce skali. Użytkownicy, którzy działają jako kierownicy magazynu tylko w jednostkach skali, powinni mieć przypisany tylko *Menedżer magazynu w* roli obciążenia. Takie podejście zapewni, że użytkownicy ci będą mieli dostęp tylko do obsługiwanych funkcji systemu. Umożliwia usunięcie wszelkich innych ról przypisanych do tych użytkowników.

Użytkownicy, którzy działają jako kierownicy magazynu tylko w jednostkach skali, powinni mieć przypisany tylko *Menedżer magazynu w* roli obciążenia. Należy pamiętać, że ta rola udziela pracownikom magazynowym dostępu do funkcji (takich jak przetwarzanie zamówień przeniesienia), które są wyświetlane w interfejsie użytkownika (UI), ale nie są obecnie obsługiwane w jednostkach skali.

## <a name="supported-wes-processes"></a>Obsługiwane procesy WES

Następujące procesy wykonania magazynu mogą być włączone dla WES obciążenia pracą jednostki skali:

- Wybrane metody grupy czynności dla zamówień sprzedaży i uzupełniania popytu
- Uruchamianie zleceń roboczych z zamówień sprzedaży i uzupełniania popytu przy użyciu aplikacji magazynu
- Badanie dostępnych zapasów przy użyciu aplikacji magazynowej
- Tworzenie i uruchamianie przesunięć magazynowych przy użyciu aplikacji magazynowej
- Rejestrowanie zamówień zakupu i wykonywanie odłożenia pracy przy użyciu aplikacji magazynowej

Następujące typy zleceń roboczych są obecnie obsługiwane w przypadku obciążeń WES w wdrożeniach jednostek skali:

- Zamówienia sprzedaży
- Uzupełnianie zapasów
- Przesunięcie magazynowe
- Zamówienia zakupu połączone z zamówieniami magazynowymi

Obecnie żadne inne przetwarzanie dokumentów źródłowych nie jest obsługiwane w jednostkach skali. Na przykład w przypadku WES obciążenia pracą jednostki skali nie można wykonywać następujących akcji:

- Zwalnianie zlecenia transferu.
- Przetwarzanie operacji pobierania i wysyłania dla magazynów wychodzących.

> [!IMPORTANT]
> W przypadku użycia obciążenia pracą na jednostkę skali nie można uruchamiać nieobsługiwanych procesów dla określonego magazynu w centrali.

Następująca funkcja zarządzania magazynem nie jest obecnie obsługiwana w jednostkach skali:

- Przetwarzanie przychodzące i wychodzące dla towarów, które mają dowolne aktywne wymiary śledzenia (takie jak wymiary partii lub numerów seryjnych)
- Przetwarzanie zmian stanu zapasów
- Przetwarzanie zapasów z wartością stanu blokowania
- Integracja z zarządzaniem jakością
- Integracja z produkcją
- Przetwarzanie towarów w ilości efektywnej
- Przetwarzanie nadwyżki i niedoboru w dostawie
- Przetwarzanie ujemnych dostępnych zapasów

### <a name="outbound-supported-only-for-sales-orders-and-demand-replenishment"></a>Wychodzące (obsługiwane tylko dla zamówień sprzedaży i uzupełniania popytu)

W poniższej tabeli pokazano, które funkcje wychodzące są obsługiwane i gdzie są obsługiwane, gdy obciążenie pracą w ramach zarządzania magazynem jest używane w jednostkach skali w chmurze i krawędziach.

> [!WARNING]
> Ponieważ obsługiwane jest tylko przetwarzanie zamówień sprzedaży, nie można używać przetwarzania wychodzącego zarządzania magazynem dla zamówień przeniesienia.
>
> Niektóre funkcje magazynowe nie będą dostępne w magazynach, w których są uruchomione obciążenia pracą zarządzania magazynem w jednostkach skali.

| Przetwarzaj                                                      | Piasta | WES obciążenie jednostki skali |
|--------------------------------------------------------------|-----|------------------------------|
| Przetwarzanie dokumentu źródłowego                                   | Tak | Nr |
| Zarządzanie procesem załadunku i transportu                | Tak | Nr |
| Zwolnij do magazynu                                         | Tak | Nr |
| Konsolidacja wysyłki                                       | Nr  | Nr |
| Przeładunek kompletacyjny (pobieranie)                                 | Nr  | Nr |
| Przetwarzanie grupy wysyłek                                     | Nie, ale stan grupy czynności jest obsługiwany w centrum |<p>Tak, ale nieobsługiwane są następujące możliwości:</p><ul><li>Tworzenie pracy równoległej</li><li>Kompilowanie i sortowanie ładunku</li><li>Konteneryzacja</li><li>Drukowanie etykiety grupy czynności</li></li></ul><p><b>Uwaga: </b>dostęp do centrum jest wymagany do sfinalizowania stanu grupy czynności w ramach przetwarzania grupy czynności.</p> |
| Przetwarzanie pracy magazynowej (z uwzględnieniem numeru identyfikacyjnego na płycie licencyjnej)     | Nr  | <p>Tak, ale tylko dla następujących możliwości:</p><ul><li>Pobieranie sprzedaży (bez użycia aktywnych wymiarów śledzenia)</li><li>Ładowanie sprzedaży (bez użycia aktywnych wymiarów śledzenia)</li></ul> |
| Wybór grupy                                              | Nr  | Nr |
| Przetwarzanie pakowania                                           | Nr  | Nr |
| Przetwarzanie sortowania wychodzących                                  | Nr  | Nr |
| Drukowanie dokumentów powiązanych z ładunkiem                           | Tak | Nr |
| List przewozowy i generowanie WPW                            | Tak | Nr |
| Potwierdzenie wysyłki i przetwarzanie dokumentu dostawy                | Tak | Nr |
| Krótkie pobieranie (zamówienia sprzedaży)                                 | Nr  | Nr |
| Anulowanie pracy                                            | Nr  | Nr |
| Zmiana lokalizacji pracy (zamówienia sprzedaży)                      | Nr  | Nr |
| Zakończ pracę (zamówienia sprzedaży)                                 | Nr  | Nr |
| Zablokuj i Odblokuj pracę                                       | Nr  | Nr |
| Zmień użytkownika                                                  | Nr  | Nr |
| Drukowanie raportu pracy                                            | Nr  | Nr |
| Etykieta grupy czynności                                                   | Nr  | Nr |
| Wycofaj pracę                                                 | Nr  | Nr |

### <a name="inbound"></a>Przychodzące

W poniższej tabeli pokazano, które funkcje przychodzące są obsługiwane i gdzie są obsługiwane, gdy obciążenie pracą w ramach zarządzania magazynem jest używane w jednostkach skali w chmurze i krawędziach.

| Przetwarzaj                                                          | Piasta | WES obciążenie jednostki skali |
|------------------------------------------------------------------|-----|------------------------------|
| Przetwarzanie &nbsp;dokumentu&nbsp; źródłowego                                       | Tak | Nr |
| Zarządzanie procesem załadunku i transportu                    | Tak | Nr |
| Potwierdzenie wysyłki                                            | Tak | Nr |
| Zwolnienie zamówienia zakupu do magazynu (przetwarzanie zamówienia magazynowego) | Tak | Nr |
| Przyjęcie i odłożenie pozycji z zamówienia zakupu                        | <p>Tak, &nbsp;gdy &nbsp;nie ma&nbsp; zamówienia magazynowego</p><p>Nie, jeśli istnieje zamówienie magazynowe</p> | <p>Tak, jeśli istnieje zamówienie magazynowe, a zamówienie zakupu nie jest częścią <i>ładunku</i>. Jednak w celu przetworzenia odłożenia należy użyć dwóch elementów menu urządzeń przenośnych, jednego do przyjęcia (<i>przyjęcie zamówienia zakupu </i>) i drugiego, z włączoną opcją <b>używaj istniejącej opcji pracy</b>.</p><p>Nie, jeśli nie istnieje zamówienie magazynowe.</p> |
| Przyjęcie i odłożenie wiersza zamówienia zakupu                        | <p>Tak, jeśli nie istnieje zamówienie magazynowe</p><p>Nie, jeśli istnieje zamówienie magazynowe</p> | Nr |
| Zwróć odebrane zamówienie i odłóż                               | Tak | Nr |
| Przyjęcie i odłożenie mieszanego numeru identyfikacyjnego                        | <p>Tak, jeśli nie istnieje zamówienie magazynowe</p><p>Nie, jeśli istnieje zamówienie magazynowe</p> | Nr |
| Odbierana pozycja ładunku                                              | <p>Tak, jeśli nie istnieje zamówienie magazynowe</p><p>Nie, jeśli istnieje zamówienie magazynowe</p> | Nr |
| Odbieranie numeru identyfikacyjnego i odłożenie                              | <p>Tak, jeśli nie istnieje zamówienie magazynowe</p><p>Nie, jeśli istnieje zamówienie magazynowe</p> | Nr |
| Przyjmowanie i odkładanie pozycji z zamówienia przeniesienia                        | Tak | Nr |
| Przyjęcie i odłożenie wiersza zamówienia przeniesienia                        | Tak | Nr |
| Anulowanie pracy                                                | <p>Tak, jeśli nie istnieje zamówienie magazynowe</p><p>Nie, jeśli istnieje zamówienie magazynowe</p> | <p>Tak, ale opcja <b>Wyrejestrowywanie paragonu podczas anulowania pracy</b>(na <b>stronie parametry zarządzania magazynem </b>) nie jest obsługiwana.</p> |
| Zamówienie zakupu — przetwarzanie dokumentu przyjęcia produktów                        | Tak | Nr |
| Tworzenie pracy przeładunku kompletacyjnego jako część odbioru                 | <p>Tak, jeśli nie istnieje zamówienie magazynowe</p><p>Nie, jeśli istnieje zamówienie magazynowe</p> | Nr |

### <a name="warehouse-operations-and-exception-handing"></a>Operacje magazynowe i przekazywanie wyjątków

W poniższej tabeli pokazano, które operacje magazynowe i obsługa wyjątków są obsługiwane i gdzie są obsługiwane, gdy obciążenie pracą w ramach zarządzania magazynem jest używane w jednostkach skali w chmurze i krawędziach.

| Przetwarzaj                                            | Piasta | WES obciążenie jednostki skali |
|----------------------------------------------------|-----|------------------------------|
| Zapytanie o numer identyfikacyjny                              | Tak | Tak                          |
| Zapytanie o pozycję                                       | Tak | Tak                          |
| Zapytanie o lokalizację                                   | Tak | Tak                          |
| Zmień magazyn                                   | Tak | Tak                          |
| Transakcje                                           | Nr  | Tak                          |
| Przeniesienie według szablonu                               | Nr  | Tak                          |
| Korekta (wejście/wyjście)                                | Tak | Nr                           |
| Przetwarzanie rozbieżności w inwentaryzacji ciągłej | Tak | Nr                           |
| Ponowny druk etykiety (drukowanie etykiet numeru identyfikacyjnego)             | Tak | Nr                           |
| Kompilacja numerów identyfikacyjnych                                | Tak | Nr                           |
| Przerwa dotycząca numeru identyfikacyjnego                                | Tak | Nr                           |
| Zaewidencjonowanie kierowcy                                    | Tak | Nr                           |
| Wyewidencjonowanie kierowcy                                   | Tak | Nr                           |
| Zmień kod dyspozycji partii                      | Tak | Nr                           |
| Wyświetl listę otwartych prac                             | Tak | Nr                           |
| Konsoliduj numery identyfikacyjne                         | Nr  | Nr                           |
| Usuń kontener z grupy                        | Nr  | Nr                           |
| Anuluj pracę                                        | Nr  | Nr                           |
| Proces uzupełnienia minimalnej i maksymalnej ilości zapasów                   | Nr  | Nr                           |
| Przetwarzanie uzupełnienia zapasów na przedziały                  | Nr  | Nr                           |

### <a name="production"></a>Produkcyjne

Integracja zarządzania magazynem dla scenariuszy produkcyjnych nie jest obecnie obsługiwana, co wskazano w poniższej tabeli.

| Przetwarzaj | Piasta | WES obciążenie jednostki skali |
|---------|-----|------------------------------|
| <p>Wszystkie procesy zarządzania magazynem, które są związane z produkcją. Oto kilka przykładów:</p><li>Zwolnij do magazynu</li><li>Przetwarzanie produkcji w ramach grupy czynności</li><li>Pobranie surowca</li><li>Ukończono odkładanie wyrobów</li><li>Odłożenie produktu ubocznego i produktu towarzyszącego</li><li>Kanban odłożone</li><li>Pobieranie Kanban</li><li>Rozpocznij zlecenie produkcyjne</li><li>Odpadki produkcji</li><li>Produkcja ostatniej palety</li><li>Rejestruj zużycie materiałów</li><li>Pusta karta Kanban</li></ul> | Nr | Nr |

## <a name="maintaining-scale-units-for-wes"></a>Obsługa jednostek skali dla WES

Kilka zadań wsadowych uruchamianych jest zarówno dla centrum, jak i jednostki skali.

W rozmieszczeniu centrum można ręcznie zarządzać zadaniami wsadowymi. Tymi trzema zadaniami można zarządzać w **Zarządzanie magazynem \> Zadania okresowe \> Zarządzanie obciążeniem backoffice**:

- Przetwarzanie zdarzeń aktualizacji stanu pracy
- Przetwarzanie zdarzeń przeniesienia kontroli wykonania grupy czynności
- Rejestruj przyjęcia zamówień źródłowych

W jednostkach obciążenia skalą, tymi dwoma zadaniami wsadowymi można zarządzać w **Zarządzanie magazynem \> Zadania okresowe \> Zarządzanie obciążeniem**:

- Przetwarzanie rekordów tabeli grupy czynności
- Przetwarzanie zdarzeń przeniesienia kontroli wykonania grupy czynności


[!INCLUDE[footer-include](../../includes/footer-banner.md)]