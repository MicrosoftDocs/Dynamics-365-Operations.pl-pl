---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources (08 lipiec 2020)
description: W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Human Resources w dniu 8 lipca 2020 roku.
author: andreabichsel
ms.date: 07/08/2020
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
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 433eef4f11f385e85648d137521996a47a8ffd7f
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/18/2021
ms.locfileid: "6053930"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-july-8-2020"></a>Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources (8 lipiec 2020)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Dynamics 365 Human Resources. Zmiany dotyczą kompilacji o numerze 8.1.3382. Liczby w nawiasach w niektórych nagłówkach odnoszą się do numerów pomocy w LCS w charakterze informacyjnym.

## <a name="database-logging"></a>Logowanie do bazy danych

Rejestrowanie bazy danych umożliwia określenie, która tabele i pola mają być monitorowane. Umożliwia również określenie zdarzeń, które powinny uruchamiać śledzenie zmian. Korzystasz z możliwości rejestrowania bazy danych, aby zobaczyć te zmiany w czasie. Aby uzyskać więcej informacji, zajrzyj do [Konfigurowanie i zarządzanie rejestrowaniem bazy danych](hr-admin-database-logging.md).

## <a name="configure-the-name-of-employee-self-service"></a>Konfigurowanie nazwy Samoobsługi pracownika etatowego

W **parametrach Human Resources** można teraz zmienić nazwę obszaru roboczego **Samoobsługa pracownika etatowego** na **Samoobsługa**. Aby uzyskać więcej informacji, zajrzyj do [Zmień nazwę obszaru roboczego samoobsługi pracownika etatowego](hr-employee-self-service-workspace-name.md)

## <a name="benefits-management-open-enrollment-access-outside-of-period"></a>Zarządzanie świadczeniami umożliwia otwarcie dostępu do rejestracji poza okresem

Ta wersja rozwiązuje usterkę, na której pracownicy mogą uzyskać dostęp do świadczeń otwartych poza okresem rejestracji lub bez zdarzenia życiowego. W wyniku tego, jeśli zachodzi potrzeba pokazania rejestracji w module samoobsługi pracownika etatowego, należy skorygować otwarte daty rejestracji do dnia dzisiejszego (lub wcześniejszej), aby je udostępnić. To ustawienie można zmienić w obszarze **Zarządzanie świadczeniami > Reguły i okresy opcji**.

## <a name="email-employee-enrollment-confirmation"></a>Potwierdzenie rejestracji pracownika w wiadomości e-mail

Możesz teraz wysyłać wiadomości e-mail do pracowników, którzy ukończyli wybór świadczeń. Można albo wysłać wiadomość domyślną, albo skorzystać z szablonu wiadomości e-mail organizacji. Te ustawienia znajdują się w obszarze **Parametry zasobów ludzkich > Zarządzanie świadczeniami**.

## <a name="canceled-leave-still-appears-in-upcoming-time-off-on-people-workspace-441358"></a>Anulowane urlopy nadal są wyświetlane w obszarze roboczym Osoby (441358) w nadchodzącym czasie

Anulowany urlop nie jest już wyświetlany jako zbliżający się czas wolny na kartach urlopów w obszarze roboczym **Osoby**.

## <a name="unable-to-use-the-department-entity-property-in-the-positionv2-entity-456486"></a>Nie można skorzystać z właściwości jednostki dział w jednostce PositionV2 (456486)

Teraz można dodać dział bez tworzenia zduplikowanej relacji.

## <a name="payrollworkerenrolledbenefitdetailentity-should-only-use-calculated-field-for-retirement-plans-459779"></a>PayrollWorkerEnrolledBenefitDetailEntity powinny używać tylko pola obliczeniowego dla planów emerytalnych (459779)

Podczas eksportowania jednostki **PayrollWorkerEnrolledBenefitDetailEntity** eksport określa, czy powinien on używać pola obliczeniowego na podstawie tabeli stawek, czy też należy używać pola **ContributionAmountCur** w tabeli zapasowej. Logika używana przez jednostkę danych używa tabeli stawek w sytuacjach, gdy aplikacja normalnie nie działa. Ta logika powoduje, że jednostka eksportuje w celu zwrócenia wartości zerowej dla tej kolumny, ponieważ nie istnieje tabela stawek obliczania, a produkt nie zezwala klientowi na określenie jednego z nich.
 
## <a name="confusing-translations-in-czech-language-in-personnel-management-and-employee-self-service-400276"></a>Pomyłkowe tłumaczenia w języku czeskim w Zarządzanie personelem i Samoobsługa pracownika etatowego (400276)

Ta wersja koryguje tłumaczenia **Katalogu firmy**, **Następny zarejestrowany kurs**, **Zadanie** i **Stanowiska**.
 
## <a name="the-workcalendaremployment-table-doesnt-have-the-created-and-modified-system-fields-enabled-460171"></a>W tabeli WorkCalendarEmployment nie są włączone utworzone i zmodyfikowane pola systemowe (460171)

Utworzone i zmodyfikowane pola systemowe są teraz włączane w tabeli **WorkCalendarEmployment** w Human Resources.
 
## <a name="null-reference-exception-for-hire-and-add-details-for-future-employee-455475"></a>Wyjątek odwołania zerowego dla zatrudnienia i dodaj szczegóły dla przyszłego pracownika (455475)

Ta wersja koryguje błąd (odwołanie o wartości null) w ulepszonym wpisie pracownika podczas zatrudniania pracownika przy użyciu opcji **Zatrudniania i dodawania szczegółów**.

## <a name="changes-made-in-the-dataverse-worker-entity-dont-reflect-in-human-resources-455652"></a>Zmiany wprowadzone w jednostce pracownika Dataverse nie są odzwierciedlane w Human Resources (455652)

Zmiany wprowadzone w poniższych polach w jednostce **Pracownik** w Dataverse z ostaną teraz wyświetlone w Human Resources:

- **Pracuje z domu**
- **Data stażu pracy**
- **Rocznica**
- **Pierwotna data zatrudnienia**

## <a name="correct-compensation-level-doesnt-default-based-on-the-job-assigned-to-the-position-394136"></a>Poprawny poziom wynagrodzeń nie jest domyślny na podstawie zadania przypisanego do stanowiska (394136)

W przypadku tej zmiany odpowiednie wartości domyślne poziomu wynagrodzeń są oparte na rekordach **Data wprowadzenia** dla **Szczegółów stanowiska** oraz w **Dacie początkowej** **Przypisania planu wynagrodzeń**.

## <a name="in-preview"></a>Wersja próbna

## <a name="mandatory-fields"></a>Pola obowiązkowe 

Można teraz wprowadzać wymagane pola, korzystając z możliwości personalizacji zasobów ludzkich. Ta funkcja wymaga **Zapisanych widoków**.

## <a name="human-resources-application-in-teams"></a>Aplikacja Human Resources w Teams

Pracownicy mogą wyświetlać i żądać czasu poza pracą w ramach Microsoft Teams. Mogą oni współpracować z botem, aby tworzyć żądania urlopu. Aby uzyskać więcej informacji, zajrzyj do [Aplikacja Human Resources w Teams](./hr-admin-teams-leave-app.md). 

## <a name="data-management-framework-dmf-entities-for-benefits-management"></a>Jednostki struktury zarządzania danymi (DMF) do zarządzania świadczeniami
 
Jednostki zarządzania świadczeniami są zwalniane. Jednostki DMF umożliwiają importowanie i eksportowanie danych w celu łatwego konfigurowania zarządzania korzyściami. Dostępny jest szablon zarządzanie świadczeniami, który umożliwia przenoszenie danych. Szablon jest eksportowany i importowany do danych w sposób sekwencyjny w celu uwzględnienia zależności danych.

## <a name="buy-and-sell-leave"></a>Kupuj i sprzedawaj urlop 

Niektóre organizacje pozwalają pracownikom kupować lub sprzedawać urlopy. Ten proces jest często zarządzany ręcznie. Ta funkcja automatyzuje Zarządzanie zasadami i wnioskami dotyczącymi działu kadr. Upraszcza proces zarządzania urlopami i pomaga wyeliminować błędy. Aby uzyskać więcej informacji, zobacz:

- [Zarządzaj zasadami Kupowania i Sprzedawania urlopu](hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)
- [Kupuj i sprzedawaj urlop](hr-employee-self-service-buy-sell-leave.md)

## <a name="leave-accrual-for-a-single-company-or-single-plan"></a>Pozostaw naliczenie dla jednej firmy lub pojedynczego planu

Odbiorcy mogą przetwarzać naliczenia dla jednej firmy lub jednego urlopu i planu nieobecności. Ta możliwość jest dostępna dla procesu naliczania dla odbiorców o różnych latach urlopowych lub zasadach naliczania urlopu. Aby uzyskać więcej informacji, zajrzyj do [Urlop naliczony według firmy lub planu urlopu](hr-leave-and-absence-accrue.md).

## <a name="add-attachments-to-time-off-requests"></a>Dodawanie załączników do żądań czasu wolnego

Możliwość dodawania załączników do zatwierdzonych żądań urlopów jest krytyczna w bieżącym środowisku COVID-19. Pracownicy mogą teraz dodawać te załączniki. Ponadto mają więcej informacji na temat sposobu dokonywania aktualizacji żądań urlopów. Aby uzyskać więcej informacji, odwiedź sekcję [Dodawanie załącznika do istniejącego żądania](hr-employee-self-service-request-time-off.md#add-an-attachment-to-an-existing-request).

## <a name="add-reason-code-to-accrual-suspensions"></a>Dodano kod przyczyny do wstrzymań naliczania 

Kody przyczyn zostały dodane do wstrzymania naliczania.

## <a name="carry-forward-rules"></a>Zasady przenoszenia na następny okres 

Można określić typ urlopu przeniesienia do przodu dla sald przeniesionych na następny okres, gdzie są przenoszone korekty do przodu. Jeśli na przykład pracownik przeniósł 10 dni do przodu, można wybrać inny typ urlopu dla tych 10 dni. Aby uzyskać więcej informacji, należy zapoznać się z tematem [Konfigurowanie typów urlopów i nieobecności](hr-leave-and-absence-types.md).

## <a name="suspend-leave-accrual-for-specified-leave-types"></a>Wstrzymanie naliczania urlopu dla określonych typów urlopów

Można utworzyć regułę, aby wstrzymać naliczanie urlopów dla pracowników z wprowadzonymi wnioskami o urlop bezpłatny. Urlop bezpłatny może być typem, ale nie musi. Istnieje możliwość wstrzymania dowolnego urlopu na podstawie innego typu urlopu.

## <a name="dmf-entity-available-for-accrual-suspensions"></a>Jednostka DMF dostępna dla wstrzymań naliczania 

Jednostka DMF jest teraz dostępna dla wstrzymań naliczania.

## <a name="coming-soon"></a>Wkrótce

## <a name="checklist-entities-included-in-dataverse"></a>Jednostki listy kontrolnej uwzględnione w Dataverse

Jednostki listy kontrolnej dotyczące procesów wdrażania, odłączania, przenoszenia i obsługi procesów biznesowych będą wkrótce dostępne w Dataverse.

## <a name="see-also"></a>Informacje dodatkowe

[Nowości i zmiany w rozwiązaniu Human Resources](hr-admin-whats-new.md)</br>
[Omówienie rozwiązania Dynamics 365 Human Resources 2019, wydanie 2](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Aktualizowanie procesu](hr-admin-setup-update-process.md)</br>
[Zarządzanie funkcjami](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]