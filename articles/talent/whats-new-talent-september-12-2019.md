---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 for Talent (10 września 2019 r.)
description: W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 for Talent.
author: Darinkramer
manager: AnnBe
ms.date: 9/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-09-10
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 14e3482f366319851bed84b6cdd6135f0bcd1e80
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/06/2019
ms.locfileid: "2897343"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-september-10-2019"></a>Nowości i zmiany w rozwiązaniu Dynamics 365 for Talent (10 września 2019 r.)

W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Dynamics 365 for Talent.

## <a name="changes-in-attract"></a>Zmiany w Attract

### <a name="candidate-e-mail-login"></a>Kandydat — logowanie do wiadomości e-mail

Kandydaci mogą teraz użyć dowolnego adresu e-mail, aby utworzyć konto i zalogować się do witryny kariery w aplikacji Talent w celu ubiegania się o zadania i sprawdzanie stanu ich aplikacji. Jest to dodatkowa możliwość do opcji zalogowania się do witryny kariery w aplikacji Talent przy użyciu kont socjalnych lub poświadczeń organizacji.

### <a name="job-activation-and-posting"></a>Aktywacja i publikowanie zadania

Wprowadziliśmy kilka zmian w aktywacji i publikacji zadania. Musisz uaktywnić zadania przed ich publikacją w witrynie kariery w aplikacji Talent lub w zewnętrznych tablicach ofert pracy, w tym LinkedIn lub Broadbean.

## <a name="changes-in-onboard"></a>Zmiany w Onboard

Ta wersja zawiera drobne poprawki błędów dla rozwiązania Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Zmiany w Core HR

Zmiany opisane w tej części dotyczą kompilacji 8.1.2482. Liczby w nawiasach w niektórych nagłówkach odnoszą się do numerów pomocy w usługach Microsoft Dynamics Lifecycle Services (LCS).

### <a name="you-can-enable-preview-features-in-sandbox-and-trial-environments"></a>Funkcje podglądu można włączać w środowiskach piaskownicy i wersji próbnej

Podczas zastrzegania nowej instancji talentów można określić, czy typem wystąpienia jest Produkcja, czy Piaskownica - środowisko testowe. Wystąpienia typu Piaskownica umożliwiają wczesne testowanie nowych funkcji. Jeśli chcesz, aby jedno z istniejących wystąpień zostało zaktualizowane do typu wystąpienia Piaskownica, skontaktuj się z pomocą techniczną, aby zainicjować żądanie zmiany.

Aby uzyskać więcej informacji o publikowaniu zmian, zapoznaj się z tematem [Provision Talent](./provisioning-talent.md).

### <a name="platform-update-29"></a>Aktualizacja platformy Update 29

Aby uzyskać więcej informacji dotyczących 29. aktualizacji platformy, zobacz [Podgląd funkcji w aktualizacji platformy 29 Dynamics 365 for Finance and Operations (Październik 2019)](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-29).

### <a name="new-job-base-entity-available-in-data-management-framework-347202"></a>Nowa jednostka podstawowa zadania dostępna w narzędziu do zarządzania danymi (347202)

W tym wydaniu jest dostępna nowa podstawowa jednostka zadania służąca do importowania/eksportowania danych. 

### <a name="worker-advanced-security-policy-incorrectly-displays-positions-in-position-hierarchy-354868"></a>Zasady zabezpieczeń zaawansowanych pracownika niewłaściwie wyświetlają pozycje w hierarchii stanowisk (354868)

W tym wydaniu pozycje nie są już wyświetlane razem z „pustym” pracownikiem, gdy użytkownicy mają ograniczony dostęp.

### <a name="job-form-close-box-wont-close-form-in-certain-situations-342467"></a>Pole zamknięcia formularza zadania nie zostanie zamknięte w pewnych sytuacjach (342467)

Ta wersja zawiera zmianę pozwalającą na zamknięcie formularza zadania we wszystkich scenariuszach.

### <a name="new-case-on-employee-record-is-locked-for-human-resources-manager-role-337111"></a>Nowa sprawa w rekordzie pracownika jest zablokowana dla roli Kierownik ds. zasobów ludzkich (337111)

W przypadku zmiany formularz zarządzania sprawami nie jest już zablokowany podczas uzyskiwania dostępu do niego z formularza pracownika etatowego.

### <a name="employment-end-date-always-defaults-to-235959-351492"></a>Wartość końcowa daty zatrudnienia jest domyślnie równa 23:59:59 (351492)

Po wprowadzeniu tej zmiany datę zatrudnienia można zmienić na godzinę inną niż 23:59:59 podczas ręcznego zakończenia zatrudnienia.

### <a name="unable-to-set-up-expiration-date-on-an-earning-code-through-data-management-336604"></a>Nie można ustawić daty ważności dla kodu zarobków w obszarze Zarządzanie danymi (336604)

W tej wersji można skonfigurować kody zarobków, które wygasają przez jednostkę **PayrollWorkerPositionEarningCodeEntity**.

### <a name="employee-development-analytic-report-doesnt-display-data-348737"></a>Raport analityczny rozwoju pracownika etatowego nie wyświetla danych (348737)

W wydaniu z tego tygodnia zaktualizowano informacje o umiejętnościach pracownika, aby zapewnić dokładne raportowanie.

### <a name="terms-of-employment-datetime-dont-default-to-beginning-of-day-349101"></a>Data/godzina według warunków zatrudnienia nie zaczynają się domyślnie od początku dnia (349101)

Po wprowadzeniu tej zmiany data/godzina rozpoczęcia będzie domyślnie ustawiona na początek dnia, a data/godzina zakończenia jest domyślnie ustawiona jako koniec dnia.

### <a name="changing-the-employment-end-date-on-worker-action-form-displays-an-error-354092"></a>W przypadku zmiany daty zakończenia zatrudnienia w formularzu Akcji dotyczącej pracownika wyświetlany jest komunikat o błędzie (354092) 

Ta zmiana powoduje usunięcie błędu podczas modyfikowania daty zakończenia zatrudnienia w ramach akcji dotyczącej pracownika.

### <a name="applying-onboarding-checklists-across-companies-338433"></a>Stosowanie listy kontrolnej podczas wdrażania między firmami (338433)

Ta wersja zapewnia obecnie możliwość stosowania list kontrolnych pracowników zatrudnionych w firmach innych niż zalogowana firma.

## <a name="in-preview"></a>Wersja próbna

### <a name="streamlined-employee-entry-and-navigation"></a>Usprawnione wprowadzanie pracowników i nawigacja

Ta funkcja jest teraz dostępna w środowiskach piaskownicy. Aby włączyć tę funkcję, przejdź do **Administrowanie systemem > Łącza > Ustawienia > Parametry systemowe > Funkcje w wersji zapoznawczej**. Wybierz **Formularz i nawigację rozszerzonego pracownika**. Dzięki temu zmiany są włączone dla wszystkich użytkowników. Opcję tę można wyłączyć w dowolnym momencie.

Aby uzyskać więcej informacji, zajrzyj do [Usprawnione wprowadzanie pracowników i nawigacja](./streamlined-employee-entry.md).
