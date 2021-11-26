---
title: Konfiguruj kartę zadań dla urządzeń
description: W tym temacie opisano różne opcje konfigurowania urządzenia karty zadań.
author: johanhoffmann
ms.date: 05/29/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: JmgRegistrationSetupTouch, JmgRegistrationTouchUserConfiguration
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-05-29
ms.dyn365.ops.version: 10.0.12
ms.openlocfilehash: 0382e34664f20389c43e8dec4437f0078fa1f60a
ms.sourcegitcommit: 8cb031501a2b2505443599aabffcfece50e01263
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/09/2021
ms.locfileid: "7777747"
---
# <a name="configure-job-card-for-devices"></a>Konfiguruj kartę zadań dla urządzeń

[!include [banner](../includes/banner.md)]

Urządzenie karty zadań jest używane przez pracowników warsztatowych do rejestrowania pracy codziennej, na przykład w przypadku rozpoczęcia zadań, raportowania informacji zwrotnych o zadaniach, rejestrowania działań pośrednich i raportowania nieobecności. Te rejestracje stanowią podstawę śledzenia postępu i kosztu zleceń produkcyjnych oraz obliczania podstawy wypłat dla pracowników. W tym temacie opisano różne opcje konfigurowania urządzeń karty zadań.

## <a name="enable-new-features-in-feature-management"></a>Włącz nowe funkcje w zarządzaniu funkcjami

Niektóre z ustawień opisanych w tym temacie muszą być włączone w systemie, zanim będą dostępne dla użytkownika. Strona [Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) umożliwia włączenie w razie potrzeby wszelkich lub wszystkich wymienionych poniżej funkcji.

### <a name="generate-license-plate"></a>Generuj numer identyfikacyjny

Aby ta funkcja była dostępna, włącz następujące funkcje w module [Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) (w kolejności):

1. Numer identyfikacyjny do zgłoszenia jako gotowy dodany do urządzenia karty zadań (na podstawie wersji 10.0.21 Supply Chain Management, ta funkcja jest domyślnie włączona)
1. Włącz automatyczną generację numeru identyfikacyjnego podczas zgłaszania wyrobów gotowych w urządzeniu karty zadań

### <a name="print-label"></a>Drukuj etykietę

Aby ta funkcja była dostępna, włącz następujące funkcje w module [Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) (w kolejności):

1. Numer identyfikacyjny do zgłoszenia jako gotowy dodany do urządzenia karty zadań (na podstawie wersji 10.0.21 Supply Chain Management, ta funkcja jest domyślnie włączona)
1. Drukowanie etykiety z menu Urządzenie karty zadań

### <a name="allow-locking-of-touch-screen"></a>Zezwalaj na blokowanie ekranu dotykowego

Od wersji 10.0.21 Supply Chain Management version ta funkcja jest domyślnie włączona. Jeśli chcesz z niego skorzystać, upewnij się, że poniższa funkcja jest włączona w [Zarządzaniu funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md):

- Funkcja umożliwiająca blokowanie urządzenie karty zadań i terminalu karty zadań w celu ich wyczyszczenia

## <a name="manage-your-device-configurations"></a>Zarządzaj konfiguracjami urządzeń

Aby skonfigurować urządzenie wybierz kolejno opcje **Kontrola produkcji > Ustawienia > Wykonywanie produkcji > Konfiguruj kartę zadań dla urządzeń**. Zostanie wyświetlona strona **Konfigurowanie karty zadań dla urządzeń**, która pokazuje listę istniejących konfiguracji. Następnie tę operację można wykonać następująco: 

- Wybierz dowolną konfigurację urządzenia znajdującą się w lewej kolumnie, aby ją wyświetlić i edytować.
- Wybierz opcję **Nowy** w okienku akcji, aby dodać nową konfigurację urządzenia do listy. Następnie wprowadź nazwę w polu **Konfiguracja**, aby zidentyfikować nową konfigurację. Wprowadzona tutaj wartość musi być unikatowa wśród wszystkich konfiguracji urządzeń i nie będzie można jej później edytować.

Poniższe sekcje zawierają szczegółowe informacje na temat ustawień konfigurowania urządzeń z kartami zadań.

## <a name="general-settings"></a>Ustawienia ogólne

Skrócona karta **Ogólne** umożliwia skonfigurowanie każdej z różnych opcji dostępnych dla wybranej konfiguracji urządzenia. Dostępne są następujące ustawienia:

- **Zgłoś ilość przy wyjściu** — wartość **Tak** powoduje, że pracownicy będą monitowani o raportowanie informacji zwrotnych dotyczących zadań w toku podczas wyrejestrowywania. Jeśli ustawiono wartość **Nie**, pracownik nie będzie monitowany.
- **Zablokuj pracownika** — Jeśli ta opcja ma wartość **Nie**, każdy pracownik zostanie wylogowany natychmiast po dokonaniu rejestracji (na przykład w nowym zadaniu), a następnie urządzenie wróci do strony logowania. Jeśli ta opcja jest ustawiona na wartość **Tak**, każdy pracownik pozostanie zalogowany na urządzeniu z kartami zadań. Jednak pracownik nadal będzie mógł się wylogować ręcznie, aby umożliwić innemu pracownikowi zalogowanie się, gdy urządzenie karty zadań pozostanie uruchomione na tym samym koncie użytkownika systemu. Aby uzyskać więcej informacji o tych typach kont, zobacz, zobacz temat [Przypisani użytkownicy](#assigned-users).
- **Skaner kodów kreskowych** — ustawienie na **Tak**, aby udostępnić opcję na urządzeniu karty zadań, które umożliwia pracownikom rejestrowanie rozpoczęcia nowego zadania przez skanowanie kodu kreskowego.
- **Użyj faktycznego czasu rejestracji** - Ustaw to na **Tak**, aby ustawić czas każdej nowej rejestracji na równy dokładnemu czasowi, w którym rejestracja została złożona przez pracownika. Ustawienie wartości **Nie** powoduje, że zamiast niej będzie używana godzina logowania. Zazwyczaj ustawienie to jest ustawione na **Tak**, jeśli włączono opcję **Zablokuj pracownika** i/lub **Jeden pracownik**, gdzie pracownik często pozostaje zalogowany przez dłuższy okres czasu.
- **Jeden pracownik** — Ustawienie tej opcji na wartość **Tak**, jeśli tylko jeden pracownik korzysta z każdego urządzenia karty zadań, w którym ta konfiguracja jest aktywna. Po wybraniu tej opcji opcja **Blokowanie pracownika** jest automatycznie ustawiana na wartość **Tak**. Ponadto ta opcja usuwa zapotrzebowanie (i zdolność) pracownika, który ma być zalogowany przy użyciu identyfikatora karty identyfikacyjnej (lub czegoś podobnego). Zamiast tego pracownik loguje się do Supply Chain Management, używając konta użytkownika systemowego powiązanego z *pracownik zarejestrowany w czasie* (z tabeli *pracownicy*) i jednocześnie loguje się do urządzenia karty pracy jako ten pracownik.  Aby uzyskać więcej informacji o tych typach kont, zobacz, zobacz temat [Przypisani użytkownicy](#assigned-users).
- **Zezwalaj pracownikom na konfigurowanie filtrów osobistych** - ustawienie tej opcji na wartość **Tak**, aby umożliwić pracownikom filtrowanie zadań widocznych dla nich na urządzeniu. Pracownik może modyfikować wartości dowolnych trzech kryteriów filtrowania: **Jednostka produkcyjna**, **Grupa zasobów** i **Zasób**. Na urządzeniu zostaną wyświetlone tylko zadania zaplanowane na zasobach spełniających wybrane kryteria filtrowania. Można również przypisywać wartości domyślne dla dowolnego lub wszystkich tych kryteriów, które będą stosowane nawet w przypadku, gdy ta opcja nie zostanie wybrana.
- **Zezwalaj na blokowanie ekranu dotykowego** — tę opcję należy wybrać **Tak**, aby umożliwić pracownikom zablokowanie ekranu dotykowego urządzenia karty zadań w celu ich usunięcia. Po włączeniu do strony logowania do urządzenia dodawany jest przycisk **Blokowanie ekranu ze względu na dezynfekcję**. Po wybraniu tego przycisku przez pracownika ekran dotykowy jest tymczasowo blokowany, aby zapobiec niezamierzonemu wprowadzaniu i pokazywany jest czasomierz odliczania. Pracownik może teraz bezpiecznie oczyścić urządzenie i ekran. Po zakończeniu odliczania ekran dotykowy automatycznie odblokowuje ponownie system.
- **Czas trwania blokady ekranu** — gdy jest włączona opcja **Zezwalaj na blokowanie ekranu dotykowego**, ta opcja służy do określenia liczby sekund, kiedy ekran dotykowy powinien być zablokowany do oczyszczania. Czas trwania musi być liczbą od 5 do 120 sekund.
- **Jednostka produkcyjna** — umożliwia wybór jednostki produkcyjnej, która ma zostać zastosowana jako domyślne kryterium filtru dla listy zadań wyświetlanych dla każdego pracownika. Tylko zadania zaplanowane na zasobach pogrupowanych w wybranej jednostce produkcyjnej będą początkowo wyświetlane przez urządzenie. Jeśli opcja **Zezwalaj pracownikom na konfigurowanie filtrów osobistych** jest włączona, pracownicy będą mogli edytować tę wartość. w przeciwnym razie ten filtr będzie stosowany zawsze, gdy ta konfiguracja urządzenia jest aktywna.
- **Grupa zasobów** — umożliwia wybór grupy zasobów, która ma zostać zastosowana jako domyślne kryterium filtru dla listy zadań wyświetlanych dla każdego pracownika. Tylko zadania zaplanowane na zasobach pogrupowanych w wybranej grupy zasobów będą początkowo wyświetlane przez urządzenie. Jeśli opcja **Zezwalaj pracownikom na konfigurowanie filtrów osobistych** jest włączona, pracownicy będą mogli edytować tę wartość. w przeciwnym razie ten filtr będzie stosowany zawsze, gdy ta konfiguracja urządzenia jest aktywna.
- **Zasoby** — umożliwia wybór zasobów, które mają zostać zastosowane jako domyślne kryterium filtru dla listy zadań wyświetlanych dla każdego pracownika. Tylko zadania zaplanowane na wybranym zasobie będą początkowo wyświetlane przez urządzenie. Jeśli opcja **Zezwalaj pracownikom na konfigurowanie filtrów osobistych** jest włączona, pracownicy będą mogli edytować tę wartość. w przeciwnym razie ten filtr będzie stosowany zawsze, gdy ta konfiguracja urządzenia jest aktywna.
- **Generowanie numeru identyfikacyjnego** — ustawienie tej opcji na wartość **Tak** powoduje generowanie nowego numeru identyfikacyjnego za każdym razem, gdy pracownik używa urządzenia karty zadań do zgłaszania wyrobów gotowych. Numer identyfikacyjny jest generowany na podstawie sekwencji numerów ustawionej na stronie **Parametry zarządzania magazynem**. Po ustawieniu wartości **Nie** pracownicy muszą określić istniejący numer identyfikacyjny podczas zgłaszania wyrobów gotowych.
- **Drukuj etykietę** — ustawienie tej opcji na wartość **Tak** powoduje Drukowanie etykiety numeru identyfikacyjnego, gdy pracownik korzysta z urządzenia karty zadań w celu zgłoszenia jako gotowej. Konfiguracja etykiety jest ustawiana w obszarze marszruta dokumentów, zgodnie z opisem w [Układ rozsyłania dokumentów dla etykiet numerów identyfikacyjnych](../warehousing/document-routing-layout-for-license-plates.md).

<a name="assigned-users"></a>

## <a name="assigned-users"></a>Przypisani użytkownicy

Użyj skróconej karty **Przypisanych użytkowników**, aby powiązać jednego lub więcej użytkowników systemu z bieżącą konfiguracją urządzenia. Każdemu użytkownikowi systemu może być przypisana tylko jedna konfiguracja urządzenia zadania.

Podczas konfigurowania urządzenia pracownik IT zazwyczaj loguje się do Supply Chain Management przy użyciu konta użytkownika systemu. Następnie konfiguracja urządzenia zadania skojarzona z tym użytkownikiem systemu będzie stosowana tak długo, jak długo użytkownik systemu pozostanie zalogowany. Te konta użytkowników systemu są zwykle ograniczone, aby umożliwić dostęp tylko do strony urządzenia karty zadań i nie ma innej części Supply Chain Management.

Po zalogowaniu użytkownika systemu i załadowaniu konfiguracji urządzenia, pracownicy mogą następnie zalogować się do urządzenia z karty zadań, używając swojego konta *pracownika zarejestrowanego w czasie* (np. przez skanowanie kodu kreskowego na ich znaczku), aby mogli rozpocząć nowe zadania i dokonać rejestracji innych typów. Wielu pracowników może logować się i wyszukiwać w ciągu dnia, podczas gdy ta sama konfiguracja urządzenia pozostaje w mocy na tym komputerze, ponieważ użytkownik systemu pozostanie zalogowany do Supply Chain Management w danym dniu.

Jednak jak wspomniano wcześniej, w przypadku korzystania z konfiguracji urządzeń z **Pojedynczym pracownikiem**, pracownicy zwykle logują się do Supply Chain Management przy użyciu użytkownika systemu połączonego z własnym kontem *pracownika zarejestrowanego w czasie*, dzięki czemu załadują one konfigurację urządzenia i logują się jako pracownik na urządzeniu obsługującym kartę czasu pracy.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Zgłaszanie jako gotowych z urządzenia karty zadania.](report-finished-job-device.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]