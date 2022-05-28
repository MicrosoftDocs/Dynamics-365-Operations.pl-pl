---
title: Integracja z często zadawanymi pytaniami Finance
description: W tym temacie wyjaśniono, jakie dane są synchronizowane w integracji programów Human Resources i Finance.
author: twheeloc
ms.date: 08/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 9b83250bdb54ea6e78709dd3a3ea434a994f6211
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2022
ms.locfileid: "8694012"
---
# <a name="integration-with-finance-faq"></a>Integracja z często zadawanymi pytaniami Finance


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



W tym temacie zawarto odpowiedzi na podstawowe pytania dotyczące sposobu synchronizowania danych po zintegrowaniu programu Dynamics 365 Human Resources z programem Dynamics 365 Finance.

## <a name="can-i-edit-the-dynamics-365-talent-application-user-in-power-apps"></a>Czy mogę modyfikować użytkownika aplikacji Dynamics 365 Talent w Power Apps?

Nie W przypadku modyfikacji użytkownika aplikacji Human Resources integracja między aplikacją Human Resources i Dataverse może zakończyć się niepowodzeniem. W poniższej tabeli przedstawiono ustawienia domyślne dla użytkownika aplikacji Talent.

| Imię i nazwisko | Identyfikator aplikacji | Identyfikator obiektu Azure AD | URI identyfikatora aplikacji |
| --- | --- | --- | --- |
| Dynamics365 for Talent | f9be0c49-aa22-4ec6-911a-c5da515226ff | 27fd8129-4b3c-43f7-b1bf-47495d3a049b | f9be0c49-aa22-4ec6-911a-c5da515226ff |

![Ustawienia domyślne dla użytkownika aplikacji Talent.](media/DynamicsApplicationUser.png)

## <a name="is-all-data-synchronized-or-just-some-data-entities"></a>Czy wszystkie dane są synchronizowane czy tylko niektóre jednostki danych?

Podzbiór danych został zsynchronizowany. Pełną listę wszystkich jednostek można znaleźć w temacie [Integracja z Dynamics 365 Finance](hr-admin-integration-finance.md).

## <a name="why-dont-i-see-any-data-synced-to-dataverse"></a>Dlaczego nie są wyświetlane żadne dane zsynchronizowane z Dataverse?

Domyślnie integracja Dataverse jest wyłączona w nowych środowiskach, w których nie uwzględniono dołączonych danych demonstracyjnych. Domyślnie jest ona włączana w nowych środowiskach, w których zawarto dane demonstracyjne, a synchronizacja danych rozpoczyna się w momencie zainicjowania obsługi środowiska. Po przygotowaniu środowiska do synchronizacji danych można włączyć integrację. Aby uzyskać więcej informacji, zobacz sekcję [Konfigurowanie narzędzia integracji Dataverse](hr-admin-integration-common-data-service.md).

## <a name="can-i-create-a-new-mapping-without-using-the-templates"></a>Czy mogę tworzyć nowe mapowania bez szablonów?

Szablony są punktem początkowym. Można utworzyć własny szablon, ale szablonu zawsze jest wymagany podczas tworzenia projektu integracji. Aby uzyskać więcej informacji o integratorze danych (DI), szablonach i projektach, zobacz [Integracja danych do Microsoft Dataverse](/powerapps/administrator/data-integrator).

## <a name="can-i-map-financial-dimensions-to-transfer-between-human-resources-and-finance"></a>Czy można mapować wymiary finansowe do przeniesienia między programami Human Resources i Finance?

Wymiary finansowe nie są obecnie w Dataverse i w związku z tym nie są częścią szablonu domyślnego. Ta jednostka jest planowana, ale aktualnie nie wiadomo, kiedy zostanie udostępniona.

Dla danych, które znajdują się w Finance, ale nie istnieje w Human Resources, należy połączyć dwa systemy ze sobą za pomocą opcji **Skonfiguruj łącza** w programie Human Resources.

![Mapowanie wymiarów finansowych.](media/MapFinancialDimensions.png)

## <a name="sometimes-when-i-import-employees-they-go-into-inactive-workers-in-finance-why"></a>Czasami po zaimportowaniu pracowników, przechodzą oni w stan nieaktywny w Finance. Dlaczego?

Ten błąd może występować, kiedy pracownicy nie mają aktywnego rekordu szczegółów zatrudnienia w programie Human Resources. Aby to rozwiązać, przejdź do **Zarządzanie personelem \> Pracownicy \> Historia zatrudnienia \> Menedżer dat** i sprawdź, czy jest aktywny rekord szczegółów zatrudnienia.

## <a name="if-i-select-to-map-only-a-subset-of-fields-will-changes-made-to-non-mapped-fields-trigger-a-sync"></a>Czy po wybraniu opcji mapowania tylko podzbioru pól zmiany niemapowanych pół będą wywoływały synchronizację?

Synchronizacja danych korzysta z harmonogramu wykonywania. Integracja pobierze rekord, jeśli dowolne pole w rekordzie zmieni się niezależnie od tego, czy pole jest częścią mapowania integracji.

## <a name="how-can-i-send-only-active-worker-changes-and-not-the-terminated-records"></a>Jak można wysłać tylko zmiany aktywnego pracownik, a nie rekordów zakończonych?

Za pomocą opcji „Zaawansowane zapytanie” można filtrować i przekształcać danych źródłowe przed przekazaniem ich do miejsca docelowego.

![Zaawansowane zapytanie o aktywnych pracowników.](media/MapOnlyActiveWorkersAdvancedQuery.png)

## <a name="can-i-specify-which-fields-to-send-to-finance-for-a-specific-entity"></a>Czy mogę określić, które pola należy wysłać do programu Finance w odniesieniu do określonej jednostki?

Pola można dodawać i usuwać z zadania integracji. Nie wszystkie pola danych, które istnieją w tabeli Dataverse, będą wypełnione dla Human Resources.
Dodatkowe dane mogą być wprowadzane prze Power Apps.

![Dodawanie lub usuwanie pól zadania integracji.](media/SpecifyFieldsIncludedInIntegration.png)

## <a name="i-set-up-integration-as-a-batch-job-but-human-resources-lost-connection-to-the-destination-system-how-can-i-send-the-same-set-of-changes-to-the-destination-system"></a>Konfiguruję integrację jako zadanie wsadowe, ale program Human Resources utracił połączenie z systemem docelowym. Jak mogę wysłać ten sam zestaw zmian do systemu docelowego?

Nie jest wymagana specjalna konfiguracja do obsługi wyjątków. Integrator danych automatycznie wyłowi i zgłosi błędy występujące w lokalizacjach źródłowej i docelowej i zezwoli na ręczne ponowienia. Nie zezwoli jednak na ręczne poprawianie danych. Jeśli wymagana jest aktualizacja danych, należy to zrobić w lokalizacji źródłowej lub docelowej.

## <a name="can-i-set-up-bi-directional-integration"></a>Czy mogę skonfigurować dwukierunkową integrację?

Nie. Integracja jest obecnie jednokierunkowa (z rozwiązania Human Resources do rozwiązania Finanse i Działania). Dostępny jest jednak domyślny szablon do wysyłania danych z rozwiązania Human Resources do rozwiązania Finance.

## <a name="can-i-allow-record-deletion-as-part-of-my-integration"></a>Czy można zezwolić na usunięcie rekordu w ramach integracji?

Nie. Integrator danych nie przechwyci usuniętych rekordów w kontekście przenoszenia danych. Obecnie dostępne są tylko funkcje tworzenia i aktualizacji danych (UPSERT).

## <a name="can-i-rerun-the-errored-execution-if-so-will-it-send-a-full-file-or-only-the-changes"></a>Czy mogę ponownie uruchomić błędne wykonanie? Jeśli tak, czy wysyłany jest pełny plik czy tylko zmiany?

Pierwsze uruchomienie Integratora danych jest zawsze pełnym uruchomieniem. Kolejne uruchomienia opierają się na śledzeniu zmian. W przypadku błędnego uruchomienia następuje wyodrębnienie rekordów w zakresie uruchomienia i wysłanie najnowszych zmian z Dataverse.

## <a name="when-i-save-the-project-i-get-the-error-project-has-mapping-errors-what-do-i-do"></a>Po zapisaniu projektu pojawia się błąd: „Projekt ma błędy mapowania”. Co należy zrobić?

Sprawdź ustawienia kluczy integracji, wprowadź wymagane zmiany konfiguracji, a następnie odśwież jednostki w projekcie.

Kiedy używany jest domyślny szablon, klucze integracji zostaną automatycznie zaimportowane. Ten problem może wystąpić, gdy nowe zadania są dodawane do istniejącego szablonu.

## <a name="if-i-have-n-number-of-legal-entities-where-workers-have-employments-do-i-need-to-create-a-mapping-for-each-of-them"></a>Jeśli mam N firm, w których pracownicy mają zatrudnienie, czy muszę utworzyć mapowanie dla każdej z nich?

Tak, dla każdej firmy w Finance konieczne będzie utworzenie odrębnego projektu integracji w integracji danych.

## <a name="i-need-to-transfer-data-that-is-not-part-of-the-default-template-provided-by-microsoft-can-i-do-this"></a>Muszę przenieść dane, które nie są częścią domyślnego szablonu dostarczonego przez Microsoft. Czy jest to możliwe?

Tak, można dodawać i usuwać zawartość pól w istniejącym szablonie. Szablon można modyfikować, aby uwzględnić dodatkowe dane z tabel innych niż Dataverse. Jednostka musi być w Dataverse, aby mogła zostać uwzględniona w szablonie. 

## <a name="i-just-created-new-finance-and-human-resources-environments-and-im-getting-the-error-the-data-value-violates-integrity-constraints-why"></a>Po utworzeniu nowego środowiska rozwiązań Finance i Human Resources pojawia się błąd „Wartość danych narusza ograniczenie integralności”. Dlaczego?

Przyczyny tego błędu mogą być następujące:

- Przeniesienie danych spowodowało zduplikowanie wyodrębnienia rekordów w lokalizacji źródłowej (Dataverse).

- Przeniesienie danych zawiera wartości null dla pól, które są wymagane w Finanse i Działania. Sprawdź dane, które są w Dataverse i czy spełniają wymagania dotyczące Finanse i Działania.

## <a name="if-there-are-execution-errors-and-the-employee-id-didnt-sync-how-do-i-find-the-history-job-which-has-the-failed-employee-record"></a>Jeśli występują błędy wykonania i identyfikator pracownika nie został zsynchronizowany, jak znaleźć zadanie historii, które zawiera rekord pracownika, dla którego wystąpił błąd?

Integrator danych spowoduje utworzenie wielu projektów w Finance. Relacja między zadaniem Integratora danych a projektem Finance jest jeden do jednego.

Prześledź czas z historii wykonywania Integratora danych i poszukaj projektu z indeksem -1 w Finance. Jeśli zadania w Integratorze danych ma numer 9, jego indeks w Finance na nr 8.

1. Zapisz indeks zadania z Integratora danych (w tym przykładzie jest to 9)

    ![Zapisz indeks zadania z integratora danych.](media/CaptureTaskIndex.png)

2. Śledź czasu wykonania projektu.

    ![Śledź czasu wykonania projektu.](media/CaptureTimeOfExecution.png)

3. W Finance Zidentyfikuj indeks-1. W tym przykładzie projekt z sufiksem „8” i godzina wykonania projektu z indeksem „0” pasuje do czasu wykonania w kroku 2.

    ![Zidentyfikuj indeks.](media/IdentifyIndex.png)

## <a name="after-integrating-human-resources-and-finance-i-dont-see-my-human-resources-data-in-finance-what-do-i-do"></a>Po integracji Human Resources i Finance nie widzę danych Human Resources w Finance. Co należy zrobić?

Integracja do Finance jest procesem dwuetapowym. Najpierw sprawdź, czy dane Human Resources są zaktualizowane i dostępne w Dataverse. Ta synchronizacja odbywa się niemal w czasie rzeczywistym i można ją sprawdzić za pomocą Power Apps, sprawdzając dane w tabeli danych.

![Dane w Dataverse.](media/DataInCDS.png)

Jeśli dane nie są wyświetlane zgodnie z oczekiwaniami w Dataverse, sprawdź, czy jednostka jest obsługiwana w integracji. Aby uwzględnić dodatkowe dane w Dataverse, zmiana będzie wymagana w witrynie Microsoft.

Jeśli jednostka jest obsługiwana, a dane są dostępne w Dataverse, sprawdź, czy mapowanie jest prawidłowe w Integratorze danych. Jeśli mapowanie integratora jest poprawne, następnie sprawdź czy zadania zarządzania danymi zostały pomyślnie uruchomione. Błędy mogą wystąpić podczas wykonywania zadań wsadowych. Aby uzyskać więcej informacji o zarządzaniu danymi, zobacz [Zarządzanie danymi](/dynamics365/unified-operations/dev-itpro/data-entities/data-entities-data-packages?toc=%2ffin-and-ops%2ftoc.json).

## <a name="the-addresses-for-my-employees-are-incorrect-after-i-import-them-into-finance-what-should-i-do"></a>Po zaimportowaniu adresów pracowników do Finance są one nieprawidłowe. Co należy zrobić?

Sekwencja numerów dla **Identyfikatora lokalizacji** korzysta z takiego samego wzorca zarówno w Human Resources jaki i w Finance. Sekwencja numerów musi być unikatowa po obu stronach, żeby nie było żadnych konfliktów adresów podczas integrowania danych z Dataverse do Finanse i Działania.

Podczas wprowadzania środowiska Human Resources należy sprawdzić, czy sekwencja numerów nie jest taka sama w Human Resources i Finanse i Działania. Sprawdź, czy wszystkie sekwencje numerów nie są identyczne tam gdzie dane mogą być obsługiwane przez oba systemy.

## <a name="when-creating-my-connection-set-i-am-unable-to-see-the-connection-in-the-connection-drop-down-list-what-do-i-do"></a>Po utworzeniu moje zestawu połączeń nie widać połączenia na liście rozwijanej Połączenie. Co należy zrobić?

Upewnij się, że podczas tworzenia połączenia została wybrana opcja Dynamics 365 Finance i Dataverse.

## <a name="when-syncing-employments-i-get-the-errors-companyinfo_fk-doesnt-exist-or-the-value-12312154-115959-pm-in-field-employment-end-date-is-not-found-in-the-related-table-employment-what-should-i-do"></a>Podczas synchronizowania zatrudnienia pojawiają się błędy „CompanyInfo_FK nie istnieje.” lub „Wartość '12/31/2154 11:59:59 pm' w polu 'Data zakończenia zatrudnienia' nie występuje w odpowiedniej tabeli 'Zatrudnienie'”. Co należy zrobić?

Upewnij się, że mapujesz prawidłowe firmy. Synchronizowanie firmy nie jest częścią szablonu domyślnego, więc oczekuje się, że każda firma, która znajduje się w Human Resources i Dataverse, znajduje się również w Finance. Upewnij się również, że wybierasz prawidłowe firmy dla skojarzonego zestawu połączeń.

## <a name="after-setting-up-my-project-the-field-mapping-for-finance-appears-to-be-empty-what-should-i-do"></a>Po skonfigurowaniu projektu mapowanie pól dla Finance wydaje się puste. Co należy zrobić?

Odśwież jednostki danych w Finance, przechodząc do **Zarządzanie danymi \> Parametry struktury \> Ustawienia jednostki \> Odśwież listę jednostek.** Może to potrwać kilka minut, a następnie powinny zostać wyświetlone te mapowania. Ten problem występuje podczas tworzenia nowych projektów.

![Brak mapowania pól.](media/MissingFieldMapping.png)

## <a name="additional-resources"></a>Dodatkowe zasoby

- Integrator danych (DI): 

  - [Integracja danych w Microsoft Dataverse](/powerapps/administrator/data-integrator)

  - [Zarządzanie błędami integratora danych i rozwiązywanie problemów](/powerapps/administrator/data-integrator-error-management)

  - [Odpowiadanie na żądania DSR dla dzienników generowanych przez system w Power Apps, Microsoft Power Automate i Dataverse](/powerapps/administrator/powerapps-gdpr-dsr-guide-systemlogs)

- Zarządzanie danymi:

  - [Zarządzanie danymi](/dynamics365/unified-operations/dev-itpro/data-entities/data-entities-data-packages?toc=%2ffin-and-ops%2ftoc.json)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
