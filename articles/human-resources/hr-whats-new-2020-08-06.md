---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources (06 sierpnia 2020 r.)
description: W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Human Resources w dniu 06 sierpnia 2020 roku.
author: andreabichsel
ms.date: 08/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-08-06
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: dbcf854330b7c5ba6ca812a5aed384584c05ce8d
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/31/2022
ms.locfileid: "8062193"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-august-06-2020"></a>Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources (06 sierpnia 2020 r.)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Dynamics 365 Human Resources. Zmiany dotyczą kompilacji o numerze 8.1.3444. Liczby w nawiasach w niektórych nagłówkach odnoszą się do numerów pomocy w LCS w charakterze informacyjnym.

## <a name="platform-update-1001236-is-now-available"></a>Aktualizacja platformy 10.0.12(36) jest teraz dostępna

Aby uzyskać więcej informacji, zobacz temat [Aktualizacje platformy dla wersji 10.0.12 aplikacji Finanse i Działania (sierpień 2020)](../fin-ops-core/dev-itpro/get-started/whats-new-platform-update-10-0-12.md).

## <a name="data-management-framework-dmf-entities-for-benefits-management"></a>Jednostki struktury zarządzania danymi (DMF) do zarządzania świadczeniami
 
Jednostki zarządzania świadczeniami są zwalniane. Jednostki DMF umożliwiają importowanie i eksportowanie danych w celu łatwego konfigurowania zarządzania korzyściami. Dostępny jest szablon zarządzanie świadczeniami, który umożliwia przenoszenie danych. Szablon jest eksportowany i importowany do danych w sposób sekwencyjny w celu uwzględnienia zależności danych. Aby uzyskać więcej informacji, zobacz:

- [Obsługa jednostki DMF](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/dmf-entity-support) w Dynamics 365 2020 1 plan wydania
- [Omówienie zarządzania danymi](../fin-ops-core/dev-itpro/data-entities/data-entities-data-packages.md)


## <a name="claire-creates-a-workflow-for-buying-and-selling-leave-requests-446557"></a>Claire tworzy przepływ pracy dla kupowanych i sprzedawanych wniosków urlopowych (446557)

Aby uzyskać więcej informacji, zobacz:

- [Pozwól pracownikom kupować i sprzedawać urlopy](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/allow-employees-buy-sell-leave) w 2 planie wydania rozwiązania Dynamics 365 2020
- [Zarządzaj zasadami Kupowania i Sprzedawania urlopu](./hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)
- [Kupuj i sprzedawaj urlop](./hr-employee-self-service-buy-sell-leave.md)


## <a name="worker-postal-addresses-v2-entity-has-access-across-legal-entities-with-restricted-access-459126"></a>Jednostka adresów pocztowych pracowników wersja 2 ma dostęp do wszystkich firm z ograniczonym dostępem (459126)

W przypadku tej zmiany **Adres pocztowy pracownika wer. 2** będzie ograniczać się na podstawie dostępu podmiotu prawnego dostarczonego użytkownikowi.

## <a name="workflow-email-hyperlink-fails-to-open-relevant-reviews-437398"></a>Hiperłącze do wiadomości e-mail przepływu pracy nie można otworzyć odpowiednich przeglądów (437398)

Gdy używasz symbolu zastępczego do otwierania recenzji wydajności w przepływie pracy recenzji, hiperłącze wygenerowane w wiadomości e-mail otwiera teraz wybrany rekord.

## <a name="new-entities-for-buying-and-selling-leave-473180"></a>Nowe jednostki do kupowania i sprzedawania urlopu (473180)

Jednostki struktury zarządzania danymi są teraz dostępne do kupowania i sprzedawania urlopu. Aby uzyskać więcej informacji, zapoznaj się z tematem [Zarządzanie danymi — omówienie](../fin-ops-core/dev-itpro/data-entities/data-entities-data-packages.md).

## <a name="when-viewing-record-information-and-using-advanced-filters-a-user-could-gain-access-to-other-employees-records-472490"></a>Podczas przeglądania informacji o rekordach i korzystaniu z filtrów zaawansowanych użytkownik może uzyskać dostęp do rekordów innych pracowników (472490)

W przypadku tej zmiany użytkownicy samoobsługi pracowników mogą uzyskać dostęp do własnych rekordów tylko podczas korzystania z funkcji samoobsługi pracownika etatowego. Przeglądanie informacji o rekordzie podczas zmiany opcji filtrowania nie są już ujawniane dodatkowe dane.

## <a name="personnel-management-analytics-include-exited-worker-records-382893"></a>Analizy zarządzania personelem obejmują zamknięte rekordy pracowników (382893)

W tym wydaniu usługi zarządzania personelem teraz obejmują tylko aktywnych pracowników. 
 
## <a name="unable-to-process-a-merit-increase-for-an-employee-473125"></a>Nie można przetworzyć podwyżki merytorycznej dla pracownika (473125)

Ta zmiana umożliwia wprowadzenie wzrostu cen po zmianie daty obowiązywania nowego wzrostu.

## <a name="review-workflow-can-be-started-more-than-once-467541"></a>Przepływ pracy recenzji można uruchomić więcej niż raz (467541)

W przypadku tej zmiany przepływ pracy przegląd wydajności można uruchomić tylko raz. Stan menedżera nie powoduje już wyświetlenia opcji rozpoczęcia recenzji.

## <a name="leave-request-work-flow-ends-in-error-when-canceling-an-approved-leave-request-472063"></a>Przepływ pracy żądania urlopu kończy się błędem w przypadku anulowania zatwierdzonego wniosku urlopowego (472063)

W tej wersji, jeśli anulujesz zatwierdzone żądanie urlopu, stan żądania nie pozostanie zatwierdzony i przepływ pracy będzie kontynuowany.

## <a name="system-suggests-exited-workers-when-creating-a-new-review-form-the-template-460624"></a>System sugeruje zakończono pracę pracowników podczas tworzenia nowej recenzji z szablonu (460624)

Dzięki tej zmianie zwolnieni pracownicy są dłużej dostępni podczas tworzenia nowych recenzji na podstawie szablonu. Nie można tworzyć recenzji dla pracowników, którzy są poza datami zatrudnienia.

## <a name="position-hierarchy-circular-reference-detection-415879"></a>Wykrywanie odwołań cyklicznych w hierarchii stanowisk (415879)

W przypadku tej zmiany wykrywanie odwołań cyklicznych w hierarchii stanowisk jest ograniczone do jednego punktu w czasie. Można uruchomić Wykrywanie odwołań cyklicznych dla różnych dat w celu sprawdzenia, czy struktura raportowania nie zawiera odwołań cyklicznych.

## <a name="buy-and-sell-leave"></a>Kupuj i sprzedawaj urlop 

Niektóre organizacje pozwalają pracownikom kupować lub sprzedawać urlopy. Ten proces jest często zarządzany ręcznie. Ta funkcja automatyzuje Zarządzanie zasadami i wnioskami dotyczącymi działu kadr. Upraszcza proces zarządzania urlopami i pomaga wyeliminować błędy. Aby uzyskać więcej informacji, zobacz:

- [Pozwól pracownikom kupować i sprzedawać urlopy](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/allow-employees-buy-sell-leave) w 2 planie wydania rozwiązania Dynamics 365 2020
- [Zarządzaj zasadami Kupowania i Sprzedawania urlopu](./hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)
- [Kupuj i sprzedawaj urlop](./hr-employee-self-service-buy-sell-leave.md)

## <a name="leave-accrual-for-a-single-company-or-single-plan"></a>Pozostaw naliczenie dla jednej firmy lub pojedynczego planu

Odbiorcy mogą przetwarzać naliczenia dla jednej firmy lub jednego urlopu i planu nieobecności. Ta możliwość jest dostępna dla procesu naliczania dla odbiorców o różnych latach urlopowych lub zasadach naliczania urlopów. Aby uzyskać więcej informacji, zajrzyj do [Urlop naliczony według firmy lub planu urlopu](hr-leave-and-absence-accrue.md).

## <a name="add-attachments-to-time-off-requests"></a>Dodawanie załączników do żądań czasu wolnego

Możliwość dodawania załączników do zatwierdzonych żądań urlopów jest krytyczna w bieżącym środowisku COVID-19. Pracownicy mogą teraz dodawać te załączniki. Ponadto mają więcej informacji na temat sposobu dokonywania aktualizacji żądań urlopów. Aby uzyskać więcej informacji, odwiedź sekcję [Dodawanie załącznika do istniejącego żądania](hr-employee-self-service-request-time-off.md#add-an-attachment-to-an-existing-request).

## <a name="add-reason-code-to-accrual-suspensions"></a>Dodano kod przyczyny do wstrzymań naliczania 

Kody przyczyn zostały dodane do wstrzymania naliczania.

## <a name="carry-forward-rules"></a>Zasady przenoszenia na następny okres 

Można określić typ urlopu przeniesienia do przodu dla sald przeniesionych na następny okres, gdzie są przenoszone korekty do przodu. Jeśli na przykład pracownik przeniósł 10 dni do przodu, można wybrać inny typ urlopu dla tych 10 dni. Aby uzyskać więcej informacji, należy zapoznać się z tematem [Konfigurowanie typów urlopów i nieobecności](hr-leave-and-absence-types.md).

## <a name="suspend-leave-accrual-for-specified-leave-types"></a>Wstrzymanie naliczania urlopu dla określonych typów urlopów

Można utworzyć regułę, aby wstrzymać naliczanie urlopów dla pracowników z wprowadzonymi wnioskami o urlop bezpłatny. Urlop bezpłatny może być typem, ale nie musi. Istnieje możliwość wstrzymania dowolnego urlopu na podstawie innego typu urlopu.

## <a name="in-preview"></a>Wersja próbna

### <a name="mandatory-fields"></a>Pola obowiązkowe

Można wprowadzać wymagane pola, korzystając z możliwości personalizacji zasobów ludzkich. Ta funkcja wymaga **Zapisanych widoków**. Aby uzyskać więcej informacji na temat zapisanych widoków, zobacz:

- [Zapisane widoki — ogólna dostępność](/dynamics365-release-plan/2020wave2/finance-operations/finance-operations-crossapp-capabilities/saved-views--general-availability) w planie wydania Dynamics 365 2020 aktualizacja 2
- [Tworzenie formularzy, które w pełni wykorzystują zapisane widoki](../fin-ops-core/dev-itpro/user-interface/understanding-saved-views.md)

### <a name="human-resources-application-in-teams"></a>Aplikacja Human Resources w Teams

Pracownicy mogą wyświetlać i żądać czasu poza pracą w ramach Microsoft Teams. Mogą oni współpracować z botem, aby tworzyć żądania urlopu. Aby uzyskać więcej informacji, zobacz:

- [Urlop i nieobecność pracowników w Microsoft Teams](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) w planie rozwiązania Dynamics 365 2020 aktualizacja 1
- [Aplikacja Human Resources w Teams](./hr-admin-teams-leave-app.md)

### <a name="dmf-entity-available-for-accrual-suspensions"></a>Jednostka DMF dostępna dla wstrzymań naliczania

Jednostka DMF jest teraz dostępna dla wstrzymań naliczania.

## <a name="coming-soon"></a>Wkrótce

## <a name="checklist-entities-included-in-dataverse"></a>Jednostki listy kontrolnej uwzględnione w Dataverse

Jednostki listy kontrolnej dotyczące procesów wdrażania, odłączania, przenoszenia i obsługi procesów biznesowych będą wkrótce dostępne w Dataverse.

## <a name="known-issues"></a>Znane problemy

W obszarze roboczym **Zarządzanie funkcjami** mogą być wyświetlane funkcje, które są wyłączone w postaci funkcji podglądu, gdy są one zazwyczaj dostępne. Poniżej znajduje się lista ogólnie dostępnych funkcji, które pokazują nieprawidłowy stan. 

1.  Zarządzanie świadczeniami
2.  Zarządzanie sprawami
3.  Rejestrowanie z bazie danych (inspekcja)
4.  Naliczanie urlopów dla jednej firmy lub pojedynczego planu
5.  Zawieszenie naliczania urlopów i nieobecności
6.  Kod przyczyny korekty salda i komentarz
7.  Kupuj i sprzedawaj urlop
8.  Kalendarz urlopów i nieobecności
9.  Reguły przeniesienia na następny okres urlopu
10. Inspekcja naliczania urlopów
11. Usunięcie naliczenia urlopów
12. Zaokrąglanie naliczania urlopów
13. Konfiguruj wiele typów urlopów w jednym planie urlopów
14. Aktualizuj udoskonalenia czasu wolnego
15. Użyj równoważnika pełnego etatu pracownika etatowego do naliczeń
16. Widok wynagrodzeń między firmami
17. Drukowanie przeglądów wydajności
18. Korekty naliczonych urlopów świątecznych

## <a name="see-also"></a>Informacje dodatkowe

[Nowości i zmiany w rozwiązaniu Human Resources](hr-admin-whats-new.md)</br>
[Omówienie rozwiązania Dynamics 365 Human Resources 2019, wydanie 2](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Aktualizowanie procesu](hr-admin-setup-update-process.md)</br>
[Zarządzanie funkcjami](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]