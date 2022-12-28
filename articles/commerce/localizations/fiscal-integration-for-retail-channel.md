---
title: Omówienie integracji fiskalnej dla kanałów aplikacji Commerce
description: Ten artykuł zawiera omówienie funkcji integracji fiskalnej dostępnych w programie Dynamics 365 Commerce.
author: EvgenyPopovMBS
ms.date: 12/06/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: 3f1b555a016a56cc41ab397e3708f20482f25f09
ms.sourcegitcommit: 0c927fcb3afd34d870391f05b5393a4673d916e5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/08/2022
ms.locfileid: "9831867"
---
# <a name="fiscal-integration-overview-for-commerce-channels"></a>Omówienie integracji fiskalnej dla kanałów aplikacji Commerce

[!include [banner](../includes/banner.md)]

Ten artykuł zawiera omówienie funkcji integracji fiskalnej dostępnych w programie Dynamics 365 Commerce. 

Integracja fiskalna obejmuje integrację z różnymi urządzeniami i usługami fiskalnych umożliwiających rejestrację fiskalną sprzedaży zgodnie z lokalnymi przepisami podatkowymi, które mają na celu zapobieganie oszustwom podatkowym w sprzedaży detalicznej. Oto kilka typowych scenariuszy wykorzystania funkcji integracji fiskalnej:

- Rejestrowanie sprzedaży detalicznej na urządzeniu fiskalnym w punkcie sprzedaży (POS), np. na drukarce fiskalnej, i drukowanie paragonu fiskalnego dla klienta.
- Bezpieczne przesyłanie informacji związanych ze sprzedażą i zwrotami, które są wykonywane w programie Retail POS, do zewnętrznej usługi sieci web, która jest prowadzona przez urząd skarbowy.
- Pomoc w zapewnieniu niezmienności danych transakcji sprzedaży za pomocą podpisów cyfrowych.

Funkcji integracji fiskalnej w Retail jest podstawą zapewniającą wspólne rozwiązanie dla dalszego rozwoju i dostosowywania integracji między Retail POS a urządzeniami i usługami fiskalnymi. Funkcja obejmuje również przykładowe integracje fiskalne obsługujące podstawowe scenariusze dla określonych krajów lub regionów i współpracujące z określonymi urządzeniami lub usługami fiskalnymi. Przykładowa integracja fiskalna składa się z kilku rozszerzeń składników modułu Commerce i jest częścią zestawu SDK. Aby uzyskać więcej informacji o integracji próbek, zobacz [Omówienie integracji fiskalnej dla próbek w Commerce SDK](#fiscal-integration-samples-in-the-commerce-sdk). Aby uzyskać informacje dotyczące instalowania i używania zestawu SDK modułu Comerce, zobacz [Omówienie zestawu SDK (software development kit) modułu Retail](../dev-itpro/retail-sdk/retail-sdk-overview.md).

Do obsługi innych scenariusze, które nie są obsługiwane przez przykładową integrację fiskalną, do integracji programu Retail POS z innymi urządzeniami lub usługami fiskalnymi lub do spełnienia wymagań innych krajów lub regionów, należy albo rozszerzyć istniejącą przykładową integrację fiskalną lub utworzyć nową przykładową integrację na podstawie istniejącego przykładu.

## <a name="fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services"></a>Proces rejestracji fiskalnej i przykładowe integracje fiskalne dla urządzeń i usług fiskalnych

Proces rejestracji fiskalnej w programie Retail POS może obejmować jeden lub klika kroków. Każdy krok obejmuje rejestrację fiskalną konkretnych transakcji lub zdarzeń na jednym urządzeniu fiskalnym lub w jednej usłudze fiskalnej. Następujące składniki rozwiązania uczestniczą w rejestracji fiskalnej w urządzeniu fiskalnym lub usłudze:

- **Dostawca dokumentów fiskalnych** – ten składnik szereguje dane transakcji/zdarzeń w formacie, który służy również do interakcji z urządzeniem fiskalnym lub uslugą, analizuje odpowiedzi z urządzenia fiskalnego lub usługi i przechowywane odpowiedzi w bazie danych kanału. Rozszerzenia definiuje również określone transakcji i zdarzenia, które muszą zostać zarejestrowane.
- **Łącznik fiskalny** – ten składnik inicjuje komunikację z urządzeniem fiskalnym lub usługą, wysyła żądania i bezpośrednie polecenia dla urządzenia fiskalnego lub usługi na podstawie danych transakcji/zdarzenia sprzedaży detalicznej wyodrębnionych z dokumentu fiskalnego, i odbiera odpowiedzi z urządzenia fiskalnego lub usługi

Próbka integracji fiskalnej może zawierać Commerce runtime (CRT), stacji sprzętowej, oraz rozszerzenia POS dla dostawcy dokumentów fiskalnych i złącza fiskalnego. Zawiera również następujące konfiguracje komponentów:

- **Konfiguracja dostawcy dokumentu fiskalnego** – ta konfiguracja definiuje metodę wyjścia i format dokumentu fiskalnego. Zawiera także mapowania danych dla podatków i metod płatności, aby zapewnić zgodność danych z programu Retail POS z wartością, która jest wstępnie zdefiniowana w oprogramowaniu układowym urządzenia fiskalnego lub usługi.
- **Konfiguracja łącznika fiskalnego** — ta konfiguracja określa fizyczną komunikację z określonym urządzeniem fiskalnym lub usługą.

Proces rejestracji fiskalnej dla określonej rejestracji POS jest definiowany przez odpowiednie ustawienie w profilu funkcji POS. Aby uzyskać więcej szczegółów na temat sposobu konfigurowania procesu rejestracji fiskalnego, przesyłania konfiguracji dostawcy dokumentu fiskalnego i łącznika fiskalnego oraz zmieniania ich parametrów konfiguracji, zobacz [Konfigurowanie procesu rejestracji fiskalnej](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process).

> [!NOTE]
> Jeśli potrzebujesz urządzeń do operacji niefiskalnych, takich jak przeszukiwanie katalogu produktów, wyszukiwanie klientów lub tworzenie wersji roboczych transakcji, możesz wybrać je jako rejestry z ograniczeniami procesów fiskalnych. Aby uzyskać więcej informacji, zobacz temat [Konfigurowanie rejestrów z ograniczeniami rejestracji fiskalnej](setting-up-fiscal-integration-for-retail-channel.md#set-up-registers-with-fiscal-registration-restrictions).

Poniższy typowy przepływ rejestracji fiskalnej rozpoczyna się od zdarzenia w punkcie sprzedaży (np. finalizacja transakcji sprzedaży) i realizuje predefiniowaną sekwencję kroków, która angażuje inne komponenty Commerce (takie jak CRT i stacja sprzętowa).

1. POS żąda dokumentu fiskalnego z ram integracji fiskalnej (FIF).
1. FIF określa, czy bieżące zdarzenie wymaga rejestracji fiskalnej.
1. Na podstawie ustawień dla procesu rejestracji fiskalnej, FIF identyfikuje złącze fiskalne i odpowiedniego dostawcę dokumentów fiskalnych do użycia dla rejestracji fiskalnej.
1. FIF uruchamia dostawcę dokumentu fiskalnego, który generuje dokument fiskalny (na przykład dokument XML), reprezentujący transakcję lub zdarzenie sprzedaży detalicznej.
1. FIF zwraca wygenerowany dokument fiskalny do punktu sprzedaży.
1. POS żąda, aby FIF przekazał dokument fiskalny do urządzenia lub serwisu fiskalnego.
1. FIF uruchamia łącznik fiskalny, który przetwarza dokument fiskalny i przekazuje go do urządzenia lub serwisu fiskalnego.
1. FIF zwraca odpowiedź fiskalną (czyli odpowiedź urządzenia lub serwisu fiskalnego) do POS.
1. POS analizuje odpowiedź fiskalną, aby określić, czy rejestracja fiskalna zakończyła się sukcesem. Jeśli jest to wymagane, POS prosi FIF o zajęcie się wszelkimi błędami, które wystąpiły. 
1. Program POS żąda przetwarzania FIF i zapisywania odpowiedzi fiskalnej.
1. Dostawca dokumentu fiskalnego przetwarza odpowiedź fiskalną. W ramach tego przetwarzania dostawca dokumentów fiskalnych przetwarza odpowiedź i wyodrębnia z niej rozszerzone dane.
1. FIF zapisuje odpowiedź i rozszerzone dane do bazy danych kanału.
1. W razie potrzeby POS drukuje paragon za pomocą zwykłej drukarki paragonowej, która jest podłączona do stacji sprzętowej. Pokwitowanie może zawierać wymagane dane z odpowiedzi fiskalnej.
 
Poniższe przykłady pokazują przepływy realizacji rejestracji fiskalnej dla typowych urządzeń lub usług fiskalnych.
 
### <a name="fiscal-registration-is-done-via-a-device-connected-to-the-hardware-station"></a>Rejestracja fiskalna odbywa się za pomocą urządzenia podłączonego do stacji sprzętowej

Konfiguracja ta jest używana, gdy do stacji sprzętowej podłączone jest fizyczne urządzenie fiskalne, np. drukarka fiskalna. Dotyczy to również sytuacji, gdy komunikacja z urządzeniem fiskalnym lub serwisem odbywa się poprzez oprogramowanie zainstalowane na stacji sprzętowej. W tym przypadku dostawca dokumentów fiskalnych znajduje się na CRT, a złącze fiskalne na stacji sprzętowej.

![Rejestracja fiskalna odbywa się za pomocą urządzenia podłączonego do stacji sprzętowej.](media/FIF-CRT-HWS.png)

### <a name="fiscal-registration-is-done-via-an-external-service"></a>Rejestracja fiskalna jest wykonywana za pośrednictwem usługi zewnętrznej

Ta konfiguracja jest używana, gdy rejestracja fiskalna odbywa się poprzez zewnętrzny serwis, np. serwis internetowy, który jest obsługiwany przez urząd skarbowy. W tym przypadku zarówno dostawca dokumentów fiskalnych, jak i złącze fiskalne znajdują się na CRT.

![Rejestracja fiskalna jest wykonywana za pośrednictwem usługi zewnętrznej.](media/FIF-CRT-CRT.png)
 
### <a name="fiscal-registration-is-done-internally-in-the-crt"></a>Rejestracja fiskalna odbywa się wewnętrznie w CRT

Ta konfiguracja jest używana, gdy do rejestracji fiskalnej nie jest wymagane zewnętrzne urządzenie lub usługa fiskalna. Używa się go na przykład wtedy, gdy rejestracja fiskalna odbywa się poprzez cyfrowe podpisywanie transakcji sprzedaży. W tym przypadku zarówno dostawca dokumentów fiskalnych, jak i złącze fiskalne znajdują się na CRT.

![Rejestracja fiskalna odbywa się wewnętrznie w CRT.](media/FIF-CRT-CRT-SGN.png)

### <a name="fiscal-registration-is-done-via-a-device-or-service-in-the-local-network"></a>Rejestracja fiskalna odbywa się za pośrednictwem urządzenia lub usługi w sieci lokalnej

Konfiguracja ta jest stosowana, gdy w sieci lokalnej sklepu znajduje się fizyczne urządzenie fiskalne lub serwis fiskalny, które udostępnia interfejs programowania aplikacji (API) HTTPS. W tym przypadku dostawca dokumentów fiskalnych znajduje się na CRT, a złącze fiskalne na POS.

![Rejestracja fiskalna odbywa się za pośrednictwem urządzenia lub usługi w sieci lokalnej.](media/FIF-CRT-POS.png)

## <a name="error-handling"></a>Obsługa błędów

Schemat integracji fiskalnej zapewnia następujące opcje obsługi błędów podczas rejestracji fiskalnej:

- **Ponów próbę** — operator może użyć tej opcji do szybkiego naprawienia awarii i ponownego uruchomienia rejestracji fiskalnej. Na przykład ta opcja może być używana, kiedy urządzenie fiskalne nie jest podłączone, w drukarce fiskalnej nie ma papieru lub papier się w niej zakleszczy.
- **Anuluj** — ta opcja pozwala operatorowi odroczyć w czasie rejestrację fiskalną bieżącej transakcji lub zdarzenia w przypadku niepowodzenia. Po odroczeniu rejestracji operator może kontynuować pracę w POS i może zakończyć każdą inną operację, dla której rejestracja fiskalna nie jest wymagana. Gdy wystąpi dowolne zdarzeniem, które wymaga rejestracji fiskalnej w POS (np. otwarcie nowej transakcji), automatycznie wyświetli się okno dialogowe z informacją, że poprzednia transakcja nie została prawidłowo zarejestrowana, i dostępnymi opcjami obsługi błędu.
- **Pomiń** — operator może użyć tej opcji, jeśli nie jest możliwe zakończenie rejestracji podatkowej bieżącej transakcji lub zdarzenia, na przykład w przypadku awarii drukarki fiskalnej **oraz** rejestracja fiskalna może zostać pominięta w określonych warunkach. Na przykład ta opcja może zostać użyta gdy transakcja sprzedaży, dla której rejestracja fiskalna nie powiodła się, może zostać zarejestrowana w specjalnym arkuszu papierowym. Po pominięciu rejestracji fiskalnej można kontynuować zwykłe operacje w punkcie sprzedaży. 
- **Oznacz jako zarejestrowaną** — operator może użyć tej opcji, gdy bieżąca transakcja lub zdarzenie faktycznie zostały zarejestrowane za pomocą urządzenia fiskalnego, na przykład paragon fiskalny został wydrukowany, ale wystąpił błąd podczas zapisywania odpowiedzi fiskalnej w bazie danych kanału. Po oznaczeniu bieżącej transakcji lub zdarzenia jako zarejestrowanego w punkcie sprzedaży można kontynuować zwykłe operacje.
- **Odrocz** – operator może używać tej opcji w przypadku, gdy transakcja nie została zarejestrowana, ponieważ usługa lub urządzenie rejestracji jest niedostępne **oraz** ma zastosowanie jedna z poniższych opcji:
    - Istnieje opcja tworzenia kopii zapasowej rejestracji fiskalnej i można kontynuować proces rejestracji fiskalnej dla bieżącej transakcji. Na przykład lokalne [urządzenie fiskalne](./latam-bra-cf-e-sat.md#scenario-4-make-a-cash-and-carry-sale-of-goods-by-using-sat-as-contingency-mode) może być kopią zapasową usługi rejestracji podatkowej w trybie online, gdy ta usługa jest dostępna.
    - Rejestrację fiskalną można zakończyć później, ale nie za pomocą struktury integracji fiskalnej. Na przykład odroczone transakcje można później zarejestrować jako transakcje fiskalne w partii za pomocą [oddzielnej funkcji](./latam-bra-nfce.md#scenario-3-make-a-cash-and-carry-sale-of-goods-in-offline-contingency-mode).
    
    Po odroczeniu bieżącej transakcji lub zdarzenia w punkcie sprzedaży można kontynuować zwykłe operacje.

> [!WARNING]
> Opcje **Pomiń**, **Oznacz jako zarejestrowane** i **Odrocz** powinny być traktowane jako opcje alarmowe i używane tylko w przypadkach wyjątkowych. Przed włączeniem tej opcji należy omówić te opcje obsługi błędów z doradcą prawnym lub doradcą podatkowym i przed ich włączeniem kierować się zdrowym rozsądkiem. Opcje muszą być aktywowane w procesie rejestracji fiskalnej obrachunkowej, zanim zostaną użyte. Aby operatorzy nie mogli używać ich regularnie, trzeba przyznać im odpowiednie uprawnienia.

[Transakcja podatkowa](#storing-fiscal-response-in-fiscal-transaction) jest tworzona po wybraniu opcji **Pomiń**, **Oznacz jako zarejestrowane** lub **Odrocz**, ale transakcja podatkowa nie zawiera odpowiedzi fiskalnej. Umożliwi to zarejestrowanie zdarzenia awarii rejestracji fiskalnej. Te opcje pozwalają także na rejestrowanie określonych informacji przez kody informacyjne dotyczących awarii, np. przyczyny awarii lub uzasadnienia pominięcia rejestracji fiskalnej lub oznaczenia transakcji jako zarejestrowanej. Aby uzyskać więcej informacji o sposobie konfigurowania parametrów obsługi błędów, zobacz [Konfigurowanie obsługi błędów](setting-up-fiscal-integration-for-retail-channel.md#set-error-handling-settings).

### <a name="optional-fiscal-registration"></a>Opcjonalna rejestracja fiskalna

Rejestracja fiskalna może być obowiązkowa dla niektórych operacji i opcjonalna dla innych scenariuszy. Na przykład rejestracja fiskalna zwykłej sprzedaży i zwrotów może być obowiązkowa, ale rejestracja fiskalna operacji związanych z wpłatami odbiorcy może być opcjonalna. W tym przypadku brak rejestracji fiskalnej sprzedaży może blokować sprzedaż w przyszłości, ale niedokonanie rejestracji fiskalnej wpłat odbiorcy nie będzie blokowało sprzedaży w przyszłości. Aby odróżnić operacje obowiązkowe od opcjonalnych, zalecamy ich obsługę przez osobnych dostawców dokumentów oraz ustalenie osobnych kroków w rejestracji fiskalnej dla tych dostawców. Parametr **Kontynuuj przy błędzie** powinien być włączony dla wszystkich kroków związanych z opcjonalną rejestracją fiskalną. Aby uzyskać więcej informacji o sposobie konfigurowania parametrów obsługi błędów, zobacz [Konfigurowanie obsługi błędów](setting-up-fiscal-integration-for-retail-channel.md#set-error-handling-settings).

### <a name="manually-rerun-fiscal-registration"></a>Ręczne ponowne uruchomienie rejestracji fiskalnej

Jeśli rejestracja fiskalna transakcji lub zdarzenia zostały odroczone po awarii (np. operator wybrał opcję **Anuluj** w polu dialogowym obsługi błędu), można ręcznie ponownie uruchomić rejestrację fiskalną przez wywołanie odpowiedniej operacji. Aby dowiedzieć się więcej, zobacz [Włączanie ręcznego wykonywania odroczonej rejestracji fiskalnej](setting-up-fiscal-integration-for-retail-channel.md#enable-manual-execution-of-deferred-fiscal-registration).

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

Po pomyślnym zakończeniu rejestracji fiskalnej transakcji lub zdarzenia transakcja fiskalna jest tworzona w bazie danych kanału z łączem do oryginalnej transakcji lub oryginalnego zdarzenia. Podobnie w przypadku wybrania opcji **Pomiń**, **Oznacz jako zarejestrowane** lub **Odrocz** dla nieudanej rejestracji fiskalnej ta informacja jest zapisywana w transakcji fiskalnej. Transakcja fiskalna zawiera odpowiedź fiskalną z urządzenia fiskalnego lub usługi fiskalnej Jeśli proces rejestracji fiskalnej składa się z kilku kroków, transakcja fiskalna jest tworzona dla każdego kroku procesu, który spowodował powodzenie lub niepowodzenie rejestracji.

Transakcje fiskalne są przenoszone do Siedziby z pomocą zadania *P-job* wraz z transakcjami sieci sprzedaży. Na skróconej karcie **Transakcje fiskalne** na stronie **Transakcje sklepu** można wyświetlić transakcje fiskalne, które są połączone z transakcjami sieci sprzedaży.

Transakcja fiskalna przechowuje następujące informacje:

- Szczegóły procesu rejestracji fiskalnej (proces, grupa łącznika, łącznik itd.) Przechowywane są także numer seryjny urządzenia fiskalnego w polu **Numer rejestru**, jeśli te informacje są uwzględniane w odpowiedzi fiskalnej.
- Stan rejestracji fiskalnej: **Zakończona** dla pomyślnej rejestracji **Pominięty** jeśli operator wybrał opcję **Pomiń** dla rejestracji nieudanej lub **Oznaczona jako zarejestrowane**, jeśli operator wybrał opcję **Oznacz jako zarejestrowaną** lub **Odroczono**, jeśli operator wybrał opcję **Odrocz**.
- Transakcje kodu informacji powiązane z wybraną transakcją fiskalną. Aby wyświetlić transakcje kodu informacji na skróconej karcie **Transakcje fiskalne**, wybierz transakcję fiskalną ze stanem **Pominięta**, **Odroczone** lub **Oznaczona jako zarejestrowana**, a następnie wybierz **Transakcje kodu informacji**.

Po wybraniu opcji **Dane rozszerzone** można również wyświetlić niektóre właściwości transakcji fiskalnej. Lista właściwości, które można wyświetlić, jest specyficzna dla funkcji rejestracji podatkowej, która wygenerowała transakcję fiskalną. Na przykład można wyświetlić podpis cyfrowy, numer kolejny, odcisk palca certyfikatu, identyfikację algorytmu skrótu i inne właściwości transakcji fiskalnej dla funkcji podpisu cyfrowego we Francji.

## <a name="fiscal-texts-for-discounts"></a>Teksty fiskalne dla rabatów

Niektóre kraje i regiony mają specjalne wymagania dotyczące dodatkowych tekstów, które muszą być wydrukowane na paragonach fiskalnych przy stosowaniu różnych typów rabatów. Funkcja integracji fiskalnej umożliwia określanie specjalnego tekstu dla rabat, który zostanie wydrukowany po wierszu rabatu na paragonie fiskalnym. Dla rabatów ręcznych można skonfigurować tekst fiskalny dla kodu informacji, który został określony jako kod informacji **Rabatu produktu** w profilu funkcji POS. Aby uzyskać więcej informacji o sposobie konfigurowania rabatów fiskalnych, zobacz [Konfigurowanie tekstów fiskalnych dla rabatów](setting-up-fiscal-integration-for-retail-channel.md#set-up-fiscal-texts-for-discounts).

## <a name="printing-fiscal-x-and-fiscal-z-reports"></a>Drukowanie raportów fiskalnych X i końcowych raportów sprzedaży

Funkcja integracji fiskalnej obsługuje generowanie zestawień na koniec dnia, które są specyficzne dla zintegrowanego urządzenia fiskalnego lub usługi fiskalnej:

- Nowe przyciski uruchamiające odpowiednie operacje powinny zostać dodane do układu ekranu POS. Aby uzyskać więcej informacji, zobacz [Konfigurowanie raportów X / końcowych raportów sprzedaży w POS](setting-up-fiscal-integration-for-retail-channel.md#set-up-fiscal-xz-reports-from-the-pos).
- W przykładowej integracji fiskalnej te operacje powinny być dopasowane do odpowiednich operacji fiskalnych urządzenia fiskalnego.

## <a name="fiscal-integration-samples-in-the-commerce-sdk"></a>Przykładowa integracja fiskalna w zestawie SDK modułu Commerce

Następujące przykładowe integracje fiskalne są obecnie dostępne w zestawie SDK modułu Commerce:

- [Przykładowa integracja drukarki fiskalnej dla Włoch](./emea-ita-fpi-sample.md)
- [Przykładowa integracja drukarki fiskalnej (Polska)](./emea-pol-fpi-sample.md)
- [Przykład integracji usługi rejestracji fiskalnej (Austria)](./emea-aut-fi-sample.md)
- [Przykład integracji usługi rejestracji fiskalnej (Czechy)](./emea-cze-fi-sample.md)
- [Przykładowa integracja jednostki kontrolnej dla Szwecji](./emea-swe-fi-sample.md)
- [Przykład integracji usługi rejestracji fiskalnej (Niemcy)](./emea-deu-fi-sample.md)
- [Przykładowa integracja drukarki fiskalnej dla Rosji](./rus-fpi-sample.md)
- [Podpis cyfrowy dla Norwegii – próbka](./emea-nor-cash-registers.md)

Następujące funkcje integracji fiskalnej są także implementowane przy użyciu schematu integracji fiskalnej, ale nie są gotowe do użycia ani nie są zawarte w zestawie SDK Commerce:

- [Rejestracja fiskalna w Brazylii](./latam-bra-commerce-localization.md#fiscal-registration-for-brazil)
- [Podpis cyfrowy dla Francji](./emea-fra-cash-registers.md)

Następujące starsze funkcje integracji fiskalnej, które są dostępne w zestawie SDK modułu Commerce, nie używają platformy integracji fiskalnej i zostaną wycofane w późniejszych aktualizacjach:

- [Przykładowa integracja jednostki kontrolnej dla Szwecji (starsza wersja)](./retail-sdk-control-unit-sample.md)
- [Podpis cyfrowy we Francji (starego typu)](./emea-fra-deployment.md)
- [Podpis cyfrowy dla Norwegii – starsza wersja](./emea-nor-loc-deployment-guidelines.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
