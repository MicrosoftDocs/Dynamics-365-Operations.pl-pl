---
title: Omówienie integracji fiskalnej dla kanałów modułu Commerce
description: Ten temat zawiera omówienie funkcji integracji fiskalnej dostępnych w programie Dynamics 365 Commerce.
author: josaw
manager: annbe
ms.date: 02/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailFunctionalityProfile, RetailFormLayout, RetailParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: v-kikozl
ms.search.validFrom: 2019-1-16
ms.dyn365.ops.version: 10
ms.openlocfilehash: ff9d722640c86333cb1f9174c640adc2e76e9a5f
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/01/2020
ms.locfileid: "3023743"
---
# <a name="overview-of-fiscal-integration-for-commerce-channels"></a>Omówienie integracji fiskalnej dla kanałów modułu Commerce

[!include [banner](../includes/banner.md)]

## <a name="introduction"></a>Wprowadzenie

Ten temat zawiera omówienie funkcji integracji fiskalnej dostępnych w programie Dynamics 365 Commerce. Integracja fiskalna obejmuje integrację z różnymi urządzeniami i usługami fiskalnych umożliwiających rejestrację fiskalną sprzedaży zgodnie z lokalnymi przepisami podatkowymi, które mają na celu zapobieganie oszustwom podatkowym w sprzedaży detalicznej. Oto kilka typowych scenariuszy wykorzystania funkcji integracji fiskalnej:

- Rejestrowanie sprzedaży detalicznej na urządzeniu fiskalnym w punkcie sprzedaży (POS), np. na drukarce fiskalnej, i drukowanie paragonu fiskalnego dla klienta.
- Bezpieczne przesyłanie informacji związanych ze sprzedażą i zwrotami, które są wykonywane w programie Retail POS, do zewnętrznej usługi sieci web, która jest prowadzona przez urząd skarbowy.
- Pomoc w zapewnieniu niezmienności danych transakcji sprzedaży za pomocą podpisów cyfrowych.

Funkcji integracji fiskalnej w Retail jest podstawą zapewniającą wspólne rozwiązanie dla dalszego rozwoju i dostosowywania integracji między Retail POS a urządzeniami i usługami fiskalnymi. Funkcje obejmuje również przykładowe integracje fiskalne obsługujące podstawowe scenariusze sieci sprzedaży dla określonych krajów lub regionów i współpracujące z określonymi urządzeniami lub usługami fiskalnymi. Przykładowa integracja fiskalna składa się z kilku rozszerzeń składników modułu Commerce i jest częścią zestawu SDK. Aby uzyskać więcej informacji o integracji próbek, zobacz [Omówienie integracji fiskalnej dla próbek w Retail SDK](#fiscal-integration-samples-in-the-retail-sdk). Aby uzyskać informacje dotyczące instalowania i używania zestawu SDK modułu Retail, zobacz [Omówienie zestawu SDK (software development kit) modułu Retail](../dev-itpro/retail-sdk/retail-sdk-overview.md).

Do obsługi innych scenariusze, które nie są obsługiwane przez przykładową integrację fiskalną, do integracji programu Retail POS z innymi urządzeniami lub usługami fiskalnymi lub do spełnienia wymagań innych krajów lub regionów, należy albo rozszerzyć istniejącą przykładową integrację fiskalną lub utworzyć nową przykładową integrację na podstawie istniejącego przykładu.

## <a name="fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices"></a>Proces rejestracji fiskalnej i przykładowe integracje fiskalne dla urządzeń fiskalnych

Proces rejestracji fiskalnej w programie Retail POS może obejmować jeden lub klika kroków. Każdy krok obejmuje rejestrację fiskalną konkretnych transakcji lub zdarzeń na jednym urządzeniu fiskalnym lub w jednej usłudze fiskalnej. Następujące składniki rozwiązania uczestniczą w rejestracji fiskalnej w urządzeniu fiskalnym, które jest podłączone do aplikacji Hardware Station:

- **Rozszerzenie środowiska uruchomieniowego Commerce Runtime (CRT)** — ten składnik szereguje dane transakcji/zdarzeń w formacie, który służy również do interakcji z urządzeniem fiskalnym, analizuje odpowiedzi z urządzenia fiskalnego i przechowywane odpowiedzi w bazie danych kanału. Rozszerzenia definiuje również określone transakcji i zdarzenia, które muszą zostać zarejestrowane. Ten składnik jest często nazywany *dostawcą dokumentu fiskalnego*.
- **Rozszerzenie aplikacji Hardware Station** — ten składnik inicjuje komunikację z urządzeniem fiskalnym, wysyła żądania i bezpośrednie polecenia dla urządzenia fiskalnego na podstawie danych transakcji/zdarzenia sprzedaży detalicznej wyodrębnionych z dokumentu fiskalnego, i odbiera odpowiedzi z urządzenia fiskalnego. Ten składnik jest często nazywany *łącznikiem fiskalnym*.

Przykładowa integracji fiskalna dla urządzenia fiskalnego zawiera rozszerzenia CRT i Hardware Station odpowiednio dla dostawcy dokumentu fiskalnego i łącznika fiskalnego. Zawiera również następujące konfiguracje komponentów:

- **Konfiguracja dostawcy dokumentu fiskalnego** – ta konfiguracja definiuje metodę wyjścia i format dokumentu fiskalnego. Zawiera także mapowania danych dla podatków i metod płatności, aby zapewnić zgodność danych z programu Retail POS z wartością, która jest wstępnie zdefiniowana w oprogramowaniu układowym urządzenia fiskalnego.
- **Konfiguracja łącznika fiskalnego** — ta konfiguracja określa fizyczną komunikację z określonym urządzeniem fiskalnym.

Proces rejestracji fiskalnej dla określonej rejestracji POS jest definiowany przez odpowiednie ustawienie w profilu funkcji POS. Aby uzyskać więcej szczegółów na temat sposobu konfigurowania procesu rejestracji fiskalnego, przesyłania konfiguracji dostawcy dokumentu fiskalnego i łącznika fiskalnego oraz zmieniania ich parametrów, zobacz [Konfigurowanie procesu rejestracji fiskalnej](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process).

Poniższy przykład pokazuje przepływ realizacji typowej rejestracji fiskalnej dla urządzenia fiskalnego. Przepływ rozpoczyna się od zdarzenia w POS (np. finalizacji transakcji sprzedaży) i implementuje następującą sekwencję kroków:

1. POS żąda dokumentu fiskalnego z CRT.
2. CRT określa, czy bieżące zdarzenie wymaga rejestracji fiskalnej.
3. Na podstawie konfiguracji procesu rejestracji fiskalnej CRT identyfikuje łącznik fiskalny i odpowiedniego dostawcę dokumentu fiskalnego używanego do użycia w rejestracji fiskalnej.
4. CRT uruchamia dostawcę dokumentu fiskalnego, który generuje dokument fiskalny (na przykład dokument XML), reprezentujący transakcję lub zdarzenie.
5. POS wysyła dokument fiskalny przygotowywany przez CRT do Hardware Station.
6. Hardware Station uruchamia łącznik fiskalny, który przetwarza dokument fiskalny i przesyła go do urządzenia fiskalnego lub usługi fiskalnej.
7. POS analizuje odpowiedź z urządzenia fiskalnego lub usługi fiskalnego w celu określenia, czy rejestracja fiskalna zakończyła się pomyślnie.
8. CRT zapisuje odpowiedź w bazie danych kanału.

![Schemat rozwiązania](media/emea-fiscal-integration-solution.png "Schemat rozwiązania")

## <a name="error-handling"></a>Obsługa błędów

Schemat integracji fiskalnej zapewnia następujące opcje obsługi błędów podczas rejestracji fiskalnej:

- **Ponów próbę** — operator może użyć tej opcji do szybkiego naprawienia awarii i ponownego uruchomienia rejestracji fiskalnej. Na przykład ta opcja może być używana, kiedy urządzenie fiskalne nie jest podłączone, w drukarce fiskalnej nie ma papieru lub papier się w niej zakleszczy.
- **Anuluj** — ta opcja pozwala operatorowi odłożyć w czasie rejestrację fiskalną bieżącej transakcji lub zdarzenia w przypadku niepowodzenia. Po odroczeniu rejestracji operator może kontynuować pracę w POS i może zakończyć każdą inną operację, dla której rejestracja fiskalna nie jest wymagana. Gdy wystąpi dowolne zdarzeniem, które wymaga rejestracji fiskalnej w POS (np. otwarcie nowej transakcji), automatycznie wyświetli się okno dialogowe z informacją, że poprzednia transakcja nie została prawidłowo zarejestrowana, i dostępnymi opcjami obsługi błędu.
- **Pomiń** — operator może użyć tej opcji, gdy rejestrację fiskalną można pominąć w określonych warunkach i można kontynuować wykonywanie zwykłych operacji w POS. Na przykład ta opcja może zostać użyta gdy transakcja sprzedaży, dla której rejestracja fiskalna nie powiodła się, może zostać zarejestrowana w specjalnym arkuszu papierowym.
- **Oznacz jako zarejestrowaną** — operator może użyć tej opcji, gdy transakcja faktycznie została zarejestrowana za pomocą urządzenia fiskalnego (na przykład paragon fiskalny został wydrukowany), ale wystąpił błąd podczas zapisywania odpowiedzi fiskalnej w bazie danych kanału.

> [!NOTE]
> Opcje **Pomiń** i **Oznacz jako zarejestrowaną** muszą być aktywowane w procesie rejestracji fiskalnej obrachunkowej, zanim zostaną użyte. Ponadto operatorzy muszą mieć odpowiednie uprawnienia.

Opcje **Pomiń** i **Oznacz jako zarejestrowaną** pozwalają na rejestrowanie określonych informacji przez kody informacyjne dotyczących awarii, np. przyczyny awarii lub uzasadnienia pominięcia rejestracji fiskalnej lub oznaczenia transakcji jako zarejestrowanej. Aby uzyskać więcej informacji o sposobie konfigurowania parametrów obsługi błędów, zobacz [Konfigurowanie obsługi błędów](setting-up-fiscal-integration-for-retail-channel.md#set-error-handling-settings).

### <a name="optional-fiscal-registration"></a>Opcjonalna rejestracja fiskalna

Rejestracja fiskalna może być obowiązkowa dla niektórych operacji i opcjonalna dla innych scenariuszy. Na przykład rejestracja fiskalna zwykłej sprzedaży i zwrotów może być obowiązkowa, ale rejestracja fiskalna operacji związanych z wpłatami odbiorcy może być opcjonalna. W tym przypadku brak rejestracji fiskalnej sprzedaży może blokować sprzedaż w przyszłości, ale niedokonanie rejestracji fiskalnej wpłat odbiorcy nie będzie blokowało sprzedaży w przyszłości. Aby odróżnić operacje obowiązkowe od opcjonalnych, zalecamy ich obsługę przez osobnych dostawców dokumentów oraz ustalenie osobnych kroków w rejestracji fiskalnej dla tych dostawców. Parametr **Kontynuuj przy błędzie** powinien być włączony dla wszystkich kroków związanych z opcjonalną rejestracją fiskalną. Aby uzyskać więcej informacji o sposobie konfigurowania parametrów obsługi błędów, zobacz [Konfigurowanie obsługi błędów](setting-up-fiscal-integration-for-retail-channel.md#set-error-handling-settings).

### <a name="manually-running-fiscal-registration"></a>Ręczne uruchomienie rejestracji fiskalnej

Jeśli rejestracja fiskalna transakcji lub zdarzenia zostały odroczone po awarii (np. operator wybrał opcję **Anuluj** w polu dialogowym obsługi błędu), można ręcznie ponownie uruchomić rejestrację fiskalną przez wywołanie odpowiedniej operacji. Aby dowiedzieć się więcej, zobacz [Włączanie ręcznego wykonywania odroczonej rejestracji fiskalnej](setting-up-fiscal-integration-for-retail-channel.md#enable-manual-execution-of-postponed-fiscal-registration).

### <a name="fiscal-registration-health-check"></a>Sprawdzanie kondycji rejestracji fiskalnej

Procedury sprawdzania kondycji rejestracji fiskalnej weryfikują dostępność urządzenia fiskalnego lub usługi po wystąpieniu określonego zdarzenia. Jeśli nie można obecnie dokończyć rejestracji fiskalnej, operator zostanie powiadomiony z wyprzedzeniem.

Punkty sprzedaży uruchamiają procedurę sprawdzania kondycji, gdy wystąpią następujące zdarzenia:

- Nowa transakcja jest otwarta.
- Wstrzymana transakcja została wznowiona.
- Transakcja sprzedaży lub zwrotu jest zakończona.

Jeśli sprawdzanie kondycji nie powiedzie się, przy punkcie sprzedaży zostanie wyświetlone okno dialogowe sprawdzania kondycji. To okno dialogowe zawiera następujące przyciski:

- **OK** — kliknięcie tego przycisku umożliwia operatorowi zignorowanie błędu sprawdzania kondycji i kontynuowanie przetwarzania operacji. Operator może nacisnąć ten przycisk tylko wtedy, gdy ma włączone uprawnienie **Zezwalaj na pominięcie błędu sprawdzania kondycji**.
- **Anuluj** — Jeśli operator wybierze ten przycisk, punkt sprzedaży anuluje ostatnią akcję (na przykład towar nie zostanie dodany do nowej transakcji).

> [!NOTE]
> Sprawdzanie kondycji jest uruchamiane tylko wtedy, gdy bieżąca operacja wymaga rejestracji fiskalnej, a parametr **Kontynuuj przy błędzie** jest wyłączony dla bieżącego etapu procesu rejestracji fiskalnej. Aby uzyskać więcej informacji, zobacz [Określanie ustawienia ustawień obsługi błędów](setting-up-fiscal-integration-for-retail-channel.md#set-error-handling-settings).

## <a name="storing-fiscal-response-in-fiscal-transaction"></a>Zapisywanie odpowiedzi fiskalnej w transakcji fiskalnej

Po pomyślnym zakończeniu rejestracji fiskalnej transakcji lub zdarzenia transakcja fiskalna jest tworzona w bazie danych kanału z łączem do oryginalnej transakcji lub oryginalnego zdarzenia. Podobnie w przypadku wybrania opcji **Pomiń** lub **Oznaczanie jako zarejestrowaną** dla nieudanej rejestracji fiskalnej ta informacja jest zapisywana w transakcji fiskalnej. Transakcja fiskalna zawiera odpowiedź fiskalną z urządzenia fiskalnego lub usługi fiskalnej Jeśli proces rejestracji fiskalnej składa się z kilku kroków, transakcja fiskalna jest tworzona dla każdego kroku procesu, który spowodował powodzenie lub niepowodzenie rejestracji.

Transakcje fiskalne są przenoszone do Siedziby z pomocą zadania *P-job* wraz z transakcjami sieci sprzedaży. Na skróconej karcie **Transakcje fiskalne** na stronie **Transakcje sklepu** można wyświetlić transakcje fiskalne, które są połączone z transakcjami sieci sprzedaży.

Transakcja fiskalna przechowuje następujące informacje:

- Szczegóły procesu rejestracji fiskalnej (proces, grupa łącznika, łącznik itd.) Przechowywane są także numer seryjny urządzenia fiskalnego w polu **Numer rejestru**, jeśli te informacje są uwzględniane w odpowiedzi fiskalnej.
- Stan rejestracji fiskalnej: **Zakończona** dla pomyślnej rejestracji **Pominięty** jeśli operator wybrał opcję **Pomiń** dla rejestracji nieudanej lub **Oznaczona jako zarejestrowane**, jeśli operator wybrał opcję **Oznacz jako zarejestrowaną**.
- Transakcje kodu informacji powiązane z wybraną transakcją fiskalną. Aby wyświetlić transakcje kodu informacji na skróconej karcie **Transakcje fiskalne**, wybierz transakcję fiskalną ze stanem **Pominięta** lub **Oznaczona jako zarejestrowana**, a następnie wybierz **Transakcje kodu informacji**.

## <a name="fiscal-texts-for-discounts"></a>Teksty fiskalne dla rabatów

Niektóre kraje i regiony mają specjalne wymagania dotyczące dodatkowych tekstów, które muszą być wydrukowane na paragonach fiskalnych przy stosowaniu różnych typów rabatów. Funkcja integracji fiskalnej umożliwia określanie specjalnego tekstu dla rabat, który zostanie wydrukowany po wierszu rabatu na paragonie fiskalnym. Dla rabatów ręcznych można skonfigurować tekst fiskalny dla kodu informacji, który został określony jako kod informacji **Rabatu produktu** w profilu funkcji POS. Aby uzyskać więcej informacji o sposobie konfigurowania rabatów fiskalnych, zobacz [Konfigurowanie tekstów fiskalnych dla rabatów](setting-up-fiscal-integration-for-retail-channel.md#set-up-fiscal-texts-for-discounts).

## <a name="printing-fiscal-x-and-fiscal-z-reports"></a>Drukowanie raportów fiskalnych X i końcowych raportów sprzedaży

Funkcja integracji fiskalnej obsługuje generowanie zestawień na koniec dnia, które są specyficzne dla zintegrowanego urządzenia fiskalnego lub usługi fiskalnej:

- Nowe przyciski uruchamiające odpowiednie operacje powinny zostać dodane do układu ekranu POS. Aby uzyskać więcej informacji, zobacz [Konfigurowanie raportów X / końcowych raportów sprzedaży w POS](setting-up-fiscal-integration-for-retail-channel.md#set-up-fiscal-xz-reports-from-the-pos).
- W przykładowej integracji fiskalnej te operacje powinny być dopasowane do odpowiednich operacji fiskalnych urządzenia fiskalnego.

## <a name="fiscal-integration-samples-in-the-retail-sdk"></a>Przykładowa integracja fiskalna w zestawie SDK modułu Retail

Następujące przykładowe integracje fiskalne są obecnie dostępne w zestawie SDK modułu Retail:

- [Przykładowa integracja drukarki fiskalnej dla Włoch](emea-ita-fpi-sample.md)
- [Przykładowa integracja drukarki fiskalnej (Polska)](emea-pol-fpi-sample.md)
- [Przykład integracji usługi rejestracji fiskalnej (Austria)](emea-aut-fi-sample.md)
- [Przykład integracji usługi rejestracji fiskalnej (Czechy)](emea-cze-fi-sample.md)
- [Przykładowa integracja jednostki kontrolnej dla Szwecji](./emea-swe-fi-sample.md)

Następujące funkcje integracji fiskalnej są także dostępne w zestawie SDK modułu Retail, ale obecnie nie używają schematu integracji fiskalnej. Migracja tej funkcji do schematu integracji fiskalnej jest planowana w późniejszych aktualizacjach.


- [Podpis cyfrowy dla Francji](emea-fra-cash-registers.md)
- [Podpis cyfrowy dla Norwegii](emea-nor-cash-registers.md)

Następujące starsze funkcje integracji fiskalnej, które są dostępne w zestawie Retail SDK, nie używają platformy integracji fiskalnej i zostaną wycofane w późniejszych aktualizacjach:

- [Przykładowa integracja jednostki kontrolnej dla Szwecji (starsza wersja)](./retail-sdk-control-unit-sample.md)
