---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 for Talent (16 kwietnia 2019)
description: W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 for Talent.
author: Darinkramer
manager: AnnBe
ms.date: 04/16/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-04-16
ms.dyn365.ops.version: Talent
ms.openlocfilehash: adf8f470b00a565c62a27f857d490c6c000b21d8
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/07/2019
ms.locfileid: "1518815"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-april-16-2019"></a>Nowości i zmiany w rozwiązaniu Dynamics 365 for Talent (16 kwietnia 2019)

[!include [banner](includes/banner.md)]

W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Dynamics 365 for Talent.

## <a name="changes-in-attract"></a>Zmiany w Attract

### <a name="process-auditing"></a>Inspekcja procesu

Teraz można śledzić zmiany wprowadzone w danych kandydatów, wakatach i podaniach o pracę. Aby uzyskać więcej informacji, zobacz [Śledzenie zmian w danych rekrutacji](process-auditing.md).

## <a name="changes-in-onboard"></a>Zmiany w Onboard

Ta wersja zawiera poprawki błędów dla programu Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Zmiany w Core HR

Zmiany opisane w tej części dotyczą kompilacji 8.1.2239. Liczby w nawiasach odnoszą się do numerów pomocy w usługach Lifecycle Services (LCS).

### <a name="compensation-region-compensation-level-benefit-option-and-skill-type-entities-in-common-data-service-updated-to-include-customer-field-support"></a>Region wynagrodzeń, poziom wynagrodzeń, opcja świadczeń i jednostki typu kwalifikacji w Common Data Service zostały zaktualizowane w celu uwzględnienia obsługi pola odbiorcy

W tym wydaniu te jednostki Common Data Service zostały zaktualizowane w celu dodania możliwości uwzględnienia niestandardowego pola dodanego za pośrednictwem aplikacji Talent (Core HR).

### <a name="new-common-data-service-entity-support-for-compensation-vesting-rules-compensation-variable-plan-variable-compensation"></a>Obsługa nowej jednostki Common Data Service dla: reguły wypłat wynagrodzenia, planu wynagrodzeń o zmiennej wysokości, wynagrodzeń o zmiennej wysokości

W tym wydaniu w Common Data Service zostały dodane reguły wypłat wynagrodzenia, plan wynagrodzeń o zmiennej wysokości oraz wynagrodzenie o zmiennej wysokości. Te jednostki obsługują również niestandardowe pola dodane za pośrednictwem aplikacji Talent (Core HR).

### <a name="powerbi-refresh-issues-314342"></a>Problemy z odświeżaniem usługi PowerBI (314342)

Ta zmiana dotyczy rozwiązania problemów z raportami usługi PowerBI, tak aby były poprawnie odświeżane.

### <a name="unable-to-click-directly-through-on-transition-tasks-in-employee-self-service-303309"></a>Nie można kliknąć bezpośrednio na zadania przejścia w portalu pracowników etatowych (303309)

Ta zmiana umożliwia użytkownikom z rolą pracownika wybieranie i aktualizowanie zadań przejścia z listy do zrobienia w aplikacji Talent.

### <a name="performance-feedback-email-message-updated-309615"></a>Zaktualizowano wiadomość e-mail z informacją o wydajności (309615)

Dzięki tej zmianie po pomyślnym przesłaniu opinii zostanie wyświetlona wiadomość z potwierdzeniem.

### <a name="missing-tables-in-word-template-308048"></a>Brak tabel w szablonie programu Word (308048)

Dzięki tej zmianie podczas tworzenia szablonu programu Word zawierającego informacje o pracowniku i umiejętnościach, w dokumencie programu Word pojawią się tylko kwalifikacje wybranego pracownika.

### <a name="when-applying-an-offboarding-checklist-an-error-is-displayed-299877"></a>Po zastosowaniu listy kontrolnej odłączania wyświetlany jest komunikat o błędzie. (299877)

Ta zmiana powoduje usunięcie błędu podczas stosowania listy kontrolnej odłączania bezpośrednio z formularza pracownika.

## <a name="in-preview"></a>Wersja próbna

### <a name="allow-reason-codes-to-be-specified-on-leave-types"></a>Zezwalaj na określanie kodów przyczyn dla typów urlopu

Organizacje mogą potrzebować dodatkowych informacji związanych z wnioskami o urlop. Można określić kody przyczyn skojarzonych z danym typem urlopu i wybrać kod przyczyny we wniosku o urlop.

### <a name="require-reason-codes-for-certain-leave-types-on-time-off-requests"></a>Wymaganie kodu przyczyny dla niektórych typów urlopów we wnioskach o czas wolny.

Organizacje mogą wymagać ustawienia kodów przyczyn dla określonych typów urlopu, kiedy pracownik składa wniosek urlopowy. Może to być spowodowane wymaganiami prawnymi lub polityką firmy. Teraz można określić typy urlopów wymagające podania kodu przyczyny i można wymagać, aby pracownicy podawali powód dla typu urlopu we wniosku.

### <a name="provide-leave-and-absence-transaction-list-for-hr"></a>Podaj listę transakcji urlopów i nieobecności dla zasobów Ludzkich

Śledzenie czasu wolnego pracowników i monitorowanie, jak czas wolny jest obliczany nie tylko pomaga działowi HR w odpowiadaniu na pytania pracowników, ale także zapewnia odpowiednie wynagrodzenie za czas wolny. Zasoby ludzkie mają teraz nowy widok transakcji (dotacje, naliczenia, korekty i żądania) aby zobaczyć, co kryje się za saldem.

## <a name="coming-soon"></a>Wkrótce

### <a name="improvements-to-the-user-interface-for-duplicate-employee-check"></a>Ulepszona funkcja interfejsu użytkownika do sprawdzania zduplikowanych pracowników

Ta zmiana powoduje, że zduplikowane pozycje są wykrywane po wypełnieniu pól nazwisk, a stan pokazuje liczbę zduplikowanych pozycji. Można wybrać podane łącze, aby otworzyć nową stronę w celu dokonania oceny, czy ma być używane wykryte dopasowanie. Aby uniknąć zakłóceń we wprowadzaniu danych, formularz zduplikowanych pozycji nie jest automatycznie otwierany.

### <a name="email-support-for-alerts"></a>Pomoc techniczna e-mail dla alertów

Aktualizacja platformy 25 pozwala użytkownikom tworzyć reguły alertów, które automatycznie wysyłają powiadomienia do kontaktów w wyniku wyzwolenia przez zdarzenie.


