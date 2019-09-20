---
title: Integracja między programami Dynamics 365 for Talent a Dynamics 365 for Finance and Operations — FAQ
description: W tym temacie wyjaśniono, jakie dane są synchronizowane w integracji programów Talent i Finance and Operations.
author: andreabichsel
manager: AnnBe
ms.date: 01/09/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-12-31
ms.dyn365.ops.version: Talent
ms.openlocfilehash: cb9e01316f4b154a3e9a73042eaf0492f016c46c
ms.sourcegitcommit: 45f8cea6ac75bd2f4187380546a201c056072c59
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/12/2019
ms.locfileid: "1742726"
---
# <a name="dynamics-365-for-talent-to-dynamics-365-for-finance-and-operations-integration-faq"></a>Integracja między programami Dynamics 365 for Talent a Dynamics 365 for Finance and Operations — FAQ

[!include [banner](includes/banner.md)]

W tym temacie zawarto odpowiedzi na podstawowe pytania dotyczące sposobu synchronizowania danych po zintegrowaniu programu Dynamics 365 for Talent z programem Dynamics 365 for Finance and Operations.

## <a name="is-all-data-synchronized-or-just-some-data-entities"></a>Czy wszystkie dane są synchronizowane czy tylko niektóre jednostki danych?

W Core Human Resources (HR) synchronizowany jest tylko podzbiór danych. Pełną listę wszystkich jednostek można znaleźć w temacie [Integracja z programu Dynamics 365 for Talent do programu Dynamics 365 for Finance and Operations](talent-financeandoperations-integration.md).

W przypadku Attract i Onboard wszystkie dane są natywne dla Common Data Service.

## <a name="can-i-create-a-new-mapping-without-using-the-templates"></a>Czy mogę tworzyć nowe mapowania bez szablonów?

Szablony są punktem początkowym. Można utworzyć własny szablon, ale szablonu zawsze jest wymagany podczas tworzenia projektu integracji. Aby uzyskać więcej informacji o integratorze danych (DI), szablonach i projektach, zobacz [Integracja danych do Common Data Service](https://docs.microsoft.com/powerapps/administrator/data-integrator).

## <a name="can-i-map-financial-dimensions-to-transfer-between-talent-and-finance-and-operations"></a>Czy można mapować wymiary finansowe do przeniesienia między programami Talent i Finance and Operations?

Wymiary finansowe nie są obecnie w Common Data Service i w związku z tym nie są częścią szablonu domyślnego. Ta jednostka jest planowana, ale aktualnie nie wiadomo, kiedy zostanie udostępniona.

Dla danych, które znajdują się w Finance and Operations, ale nie istnieje w Talent, należy połączyć dwa systemy ze sobą za pomocą opcji **Skonfiguruj łącza** w programie Talent. Aby uzyskać więcej informacji dotyczących sposobu konfigurowania powiązań między programami Talent i Finance and Operations, zobacz [Nowości i zmiany w rozwiązaniu w Dynamics 365 for Talent Core HR (31 października 2018)](whats-new-talent-october-31.md).

![Mapowanie wymiarów finansowych](media/MapFinancialDimensions.png)

## <a name="sometimes-when-i-import-employees-they-go-into-inactive-workers-in-finance-and-operations-why"></a>Czasami po zaimportowaniu pracowników, przechodzą oni w stan nieaktywny w Finance and Operations. Dlaczego?

Ten błąd może występować, kiedy pracownicy nie mają aktywnego rekordu szczegółów zatrudnienia w programie Talent. Aby to rozwiązać, przejdź do **Zarządzanie personelem \> Pracownicy \> Historia zatrudnienia \> Menedżer dat** i sprawdź, czy jest aktywny rekord szczegółów zatrudnienia.

## <a name="if-i-select-to-map-only-a-subset-of-fields-will-changes-made-to-non-mapped-fields-trigger-a-sync"></a>Czy po wybraniu opcji mapowania tylko podzbioru pól zmiany niemapowanych pół będą wywoływały synchronizację?

Synchronizacja danych korzysta z harmonogramu wykonywania. Integracja pobierze rekord, jeśli dowolne pole w rekordzie zmieni się niezależnie od tego, czy pole jest częścią mapowania integracji.

## <a name="how-can-i-send-only-active-worker-changes-and-not-the-terminated-records"></a>Jak można wysłać tylko zmiany aktywnego pracownik, a nie rekordów zakończonych?

Za pomocą opcji „Zaawansowane zapytanie” można filtrować i przekształcać danych źródłowe przed przekazaniem ich do miejsca docelowego.

![Zaawansowane zapytanie o aktywnych pracowników](media/MapOnlyActiveWorkersAdvancedQuery.png)

## <a name="can-i-specify-which-fields-to-send-to-finance-and-operations-for-a-specific-entity"></a>Czy mogę określić, które pola należy wysłać do programu Finance and Operations w odniesieniu do określonej jednostki?

Pola można dodawać i usuwać z zadania integracji. Nie wszystkie pola danych, które istnieją w jednostce Common Data Service, będą wypełnione dla Core HR.
Dodatkowe dane mogą być wprowadzane prze PowerApps.

![Dodawanie lub usuwanie pól zadania integracji](media/SpecifyFieldsIncludedInIntegration.png)

## <a name="i-set-up-integration-as-a-batch-job-but-talent-lost-connection-to-the-destination-system-how-can-i-send-the-same-set-of-changes-to-the-destination-system"></a>Konfiguruję integrację jako zadanie wsadowe, ale program Talent utracił połączenie z systemem docelowym. Jak mogę wysłać ten sam zestaw zmian do systemu docelowego?

Nie jest wymagana specjalna konfiguracja do obsługi wyjątków. Integrator danych automatycznie wyłowi i zgłosi błędy występujące w lokalizacjach źródłowej i docelowej i zezwoli na ręczne ponowienia. Nie zezwoli jednak na ręczne poprawianie danych. Jeśli wymagana jest aktualizacja danych, należy to zrobić w lokalizacji źródłowej lub docelowej.

## <a name="can-i-set-up-bi-directional-integration"></a>Czy mogę skonfigurować dwukierunkową integrację?

Nie. Integracja jest obecnie jednokierunkowa (z rozwiązania Talent do rozwiązania Finance and Operations). Dostępny jest jednak domyślny szablon do wysyłania danych z rozwiązania Talent do rozwiązania Finance and Operations.

## <a name="can-i-allow-record-deletion-as-part-of-my-integration"></a>Czy można zezwolić na usunięcie rekordu w ramach integracji?

Nie. Integrator danych nie przechwyci usuniętych rekordów w kontekście przenoszenia danych. Obecnie dostępne są tylko funkcje tworzenia i aktualizacji danych (UPSERT).

## <a name="can-i-rerun-the-errored-execution-if-so-will-it-send-a-full-file-or-only-the-changes"></a>Czy mogę ponownie uruchomić błędne wykonanie? Jeśli tak, czy wysyłany jest pełny plik czy tylko zmiany?

Pierwsze uruchomienie Integratora danych jest zawsze pełnym uruchomieniem. Kolejne uruchomienia opierają się na śledzeniu zmian. W przypadku błędnego uruchomienia następuje wyodrębnienie rekordów w zakresie uruchomienia i wysłanie najnowszych zmian z Common Data Service.

## <a name="when-i-save-the-project-i-get-the-error-project-has-mapping-errors-what-do-i-do"></a>Po zapisaniu projektu pojawia się błąd: „Projekt ma błędy mapowania”. Co należy zrobić?

Sprawdź ustawienia kluczy integracji, wprowadź wymagane zmiany konfiguracji, a następnie odśwież jednostki w projekcie.

Kiedy używany jest domyślny szablon, klucze integracji zostaną automatycznie zaimportowane. Ten problem może wystąpić, gdy nowe zadania są dodawane do istniejącego szablonu.

## <a name="if-i-have-n-number-of-legal-entities-where-workers-have-employments-do-i-need-to-create-a-mapping-for-each-of-them"></a>Jeśli mam N firm, w których pracownicy mają zatrudnienie, czy muszę utworzyć mapowanie dla każdej z nich?

Tak, dla każdej firmy w Finance and Operations konieczne będzie utworzenie odrębnego projektu integracji w integracji danych.

## <a name="i-need-to-transfer-data-that-is-not-part-of-the-default-template-provided-by-microsoft-can-i-do-this"></a>Muszę przenieść dane, które nie są częścią domyślnego szablonu dostarczonego przez Microsoft. Czy jest to możliwe?

Tak, można dodawać i usuwać zawartość pól w istniejącym szablonie. Szablon można modyfikować, aby uwzględnić dodatkowe dane z jednostek innych niż Common Data Service. Jednostka musi być w Common Data Service, aby mogła zostać uwzględniona w szablonie. 

## <a name="i-just-created-new-finance-and-operations-and-talent-environments-and-im-getting-the-error-the-data-value-violates-integrity-constraints-why"></a>Po utworzeniu nowego środowiska rozwiązań Finance and Operations i Talent pojawia się błąd „Wartość danych narusza ograniczenie integralności”. Dlaczego?

Przyczyny tego błędu mogą być następujące:

- Przeniesienie danych spowodowało zduplikowanie wyodrębnienia rekordów w lokalizacji źródłowej (Common Data Service).

- Przeniesienie danych zawiera wartości null dla pól, które są wymagane w Finance and Operations. Sprawdź dane, które są w Common Data Service i czy spełniają wymagania dotyczące Finance and Operations.

## <a name="if-there-are-execution-errors-and-the-employee-id-didnt-sync-how-do-i-find-the-history-job-which-has-the-failed-employee-record"></a>Jeśli występują błędy wykonania i identyfikator pracownika nie został zsynchronizowany, jak znaleźć zadanie historii, które zawiera rekord pracownika, dla którego wystąpił błąd?

Integrator danych spowoduje utworzenie wielu projektów w Finance and Operations. Relacja między zadaniem Integratora danych a projektem Finance and Operations jest jeden do jednego.

Prześledź czas z historii wykonywania Integratora danych i poszukaj projektu z indeksem -1 w Finance and Operations. Jeśli zadania w Integratorze danych ma numer 9, jego indeks w Finance and Operations na nr 8.

1. Zapisz indeks zadania z Integratora danych (w tym przykładzie jest to 9)

![Zapisz indeks zadania z integratora danych](media/CaptureTaskIndex.png)

2. Śledź czasu wykonania projektu.

![Śledź czasu wykonania projektu.](media/CaptureTimeOfExecution.png)

3. W Finance and Operations zidentyfikuj indeks -1 W tym przykładzie projekt z sufiksem „8” i godzina wykonania projektu z indeksem „0” pasuje do czasu wykonania w kroku 2.

![Zidentyfikuj indeks](media/IdentifyIndex.png)

## <a name="after-integrating-talent-and-finance-and-operations-i-dont-see-my-talent-data-in-finance-and-operations-what-do-i-do"></a>Po integracji Talent i Finance and Operations nie widzę danych Talent w Finance and Operations. Co należy zrobić?

Integracja do Finance and Operations jest procesem dwuetapowym. Najpierw sprawdź, czy dane Talent są zaktualizowane i dostępne w Common Data Service. Ta synchronizacja odbywa się niemal w czasie rzeczywistym i można ją sprawdzić za pomocą PowerApps, sprawdzając dane w jednostce danych.

![Dane w Common Data Service](media/DataInCDS.png)

Jeśli dane nie są wyświetlane zgodnie z oczekiwaniami w Common Data Service, sprawdź, czy jednostka jest obsługiwana w integracji. Aby uwzględnić dodatkowe dane w Common Data Service, zmiana będzie wymagana w witrynie Microsoft.

Jeśli jednostka jest obsługiwana, a dane są dostępne w Common Data Service, sprawdź, czy mapowanie jest prawidłowe w Integratorze danych. Jeśli mapowanie integratora jest poprawne, następnie sprawdź czy zadania zarządzania danymi zostały pomyślnie uruchomione. Błędy mogą wystąpić podczas wykonywania zadań wsadowych. Aby uzyskać więcej informacji o zarządzaniu danymi, zobacz [Zarządzanie danymi](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/data-entities-data-packages?toc=/fin-and-ops/toc.json).

## <a name="the-addresses-for-my-employees-are-incorrect-after-i-import-them-into-finance-and-operations-what-should-i-do"></a>Po zaimportowaniu adresów pracowników do Finance and Operations są one nieprawidłowe. Co należy zrobić?

Sekwencja numerów dla **Identyfikatora lokalizacji** korzysta z takiego samego wzorca zarówno w Talent jaki i w Finance and Operations. Sekwencja numerów musi być unikatowa po obu stronach, żeby nie było żadnych konfliktów adresów podczas integrowania danych z Common Data Service do Finance and Operations.

Podczas wprowadzania środowiska Talent należy sprawdzić, czy sekwencja numerów nie jest taka sama w Talent i Finance and Operations. Sprawdź, czy wszystkie sekwencje numerów nie są identyczne tam gdzie dane mogą być obsługiwane przez oba systemy.

## <a name="when-creating-my-connection-set-i-am-unable-to-see-the-connection-in-the-connection-drop-down-list-what-do-i-do"></a>Po utworzeniu moje zestawu połączeń nie widać połączenia na liście rozwijanej Połączenie. Co należy zrobić?

Upewnij się, że podczas tworzenia połączenia została wybrana opcja Dynamics 365 for Finance and Operations (aktualnie w wersji próbnej) i Common Data Service.

## <a name="when-syncing-employments-i-get-the-errors-companyinfo_fk-doesnt-exist-or-the-value-12312154-115959-pm-in-field-employment-end-date-is-not-found-in-the-related-table-employment-what-should-i-do"></a>Podczas synchronizowania zatrudnienia pojawiają się błędy „CompanyInfo_FK nie istnieje.” lub „Wartość '12/31/2154 11:59:59 pm' w polu 'Data zakończenia zatrudnienia' nie występuje w odpowiedniej tabeli 'Zatrudnienie'”. Co należy zrobić?

Upewnij się, że mapujesz prawidłowe firmy. Synchronizowanie firmy nie jest częścią szablonu domyślnego, więc oczekuje się, że każda firma, która znajduje się w Talent i Common Data Service, znajduje się również w Finance and Operations.
Upewnij się również, że wybierasz prawidłowe firmy dla skojarzonego zestawu połączeń.

## <a name="after-setting-up-my-project-the-field-mapping-for-finance-and-operations-appears-to-be-empty-what-should-i-do"></a>Po skonfigurowaniu projektu mapowanie pól dla Finance and Operations wydaje się puste. Co należy zrobić?

Odśwież jednostki danych w Finance and Operations, przechodząc do **Zarządzanie danymi \> Parametry struktury \> Ustawienia jednostki \> Odśwież listę jednostek.** Może to potrwać kilka minut, a następnie powinny zostać wyświetlone te mapowania. Ten problem występuje podczas tworzenia nowych projektów.

![Brak mapowania pól](media/MissingFieldMapping.png)

## <a name="additional-resources"></a>Dodatkowe zasoby

- Integrator danych (DI): 

  - [Integracja danych w Common Data Service](https://docs.microsoft.com/powerapps/administrator/data-integrator)

  - [Zarządzanie błędami integratora danych i rozwiązywanie problemów](https://docs.microsoft.com/powerapps/administrator/data-integrator-error-management)

  - [Odpowiadanie na żądania DSR dla dzienników generowanych przez system w PowerApps, Microsoft Flow i Common Data Service](https://docs.microsoft.com/powerapps/administrator/powerapps-gdpr-dsr-guide-systemlogs)

- Zarządzanie danymi:

  - [Zarządzanie danymi](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/data-entities-data-packages?toc=/fin-and-ops/toc.json)
