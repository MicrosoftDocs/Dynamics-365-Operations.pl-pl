---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources (14 maja 2020 r.)
description: W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Human Resources w dniu 14 maja 2020 roku.
author: Darinkramer
manager: AnnBe
ms.date: 05/14/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2020-05-14
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 76ca497cc7fabf737c8a0ee71363f22fd4201ea8
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/17/2020
ms.locfileid: "4528504"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-may-14-2020"></a>Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources (14 maja 2020 r.)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Dynamics 365 Human Resources. Zmiany dotyczą kompilacji o numerze 8.1.3244. Liczby w nawiasach w niektórych nagłówkach odnoszą się do numerów pomocy w usługach Lifecycle Services (LCS).

## <a name="platform-changes"></a>Zmiany w platformie

Zmiany w platformie są uwzględniane w wydaniu z danego tygodnia. Aby uzyskać więcej informacji, zobacz temat [Aktualizacje platformy dla wersji 10.0.10 aplikacji Finance and Operations (maj 2020)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-update-34). Ta wersja zawiera poprawki usterek i zmiany w zapisanych widokach.
 
## <a name="ensure-common-data-service-picklists-are-consistent-with-leave-enums-436343"></a>Upewnij się, że listy wyboru usługi Common Data Service są spójne z wyliczeniami nieobecności (436343)

Listy wyboru usługi Common Data Service są teraz spójne z wyliczeniami nieobecności.

## <a name="allow-users-to-configure-leave-request-workflow-based-on-the-request-amount-300044"></a>Umożliwienie użytkownikom konfigurowania przepływu pracy wniosku o urlop na podstawie ilości żądania (300044)

Użytkownicy mogą konfigurować przepływy pracy wniosku o urlop na podstawie ilości żądania.
 
## <a name="new-worker-form-exposes-data-through-the-view-menu-when-advanced-security-is-enabled-403185"></a>Nowy formularz pracownika ujawniane dane za pomocą menu widoku po włączeniu zabezpieczeń zaawansowanych (403185)

Ta wersja koryguje sposób, w jaki pracownicy w różnych firmach będą działać w przypadku, gdy jest włączony zaawansowany dostęp, a pracownicy w innych firmach są dostępni.

## <a name="allow-running-leave-accruals-for-a-single-plan-or-a-single-company-318844"></a>Zezwalanie na uruchamianie naliczania urlopu dla pojedynczego planu lub pojedynczej firmy (318844)

Dzięki tej zmianie można uruchamiać naliczenia dla firmy lub planu.
 
## <a name="show-the-positions-full-time-equivalent-fte-in-the-enrolled-workers-form-414658"></a>Wyświetlanie ekwiwalent pełnego wymiaru czasu pozycji (FTE) w formularzu zarejestrowanych pracowników (414658)

Wartość pełnego etatu pozycji pracownika określa stawkę naliczania dla pracownika, jeśli dla typu urlopu jest włączona opcja FTE. To pole jest teraz uwzględniane w formularzu **zarejestrowanych pracowników** i w oknie dialogowym **rejestracji grupowej**.

## <a name="add-leave-balance-expiration-batch-job-431266"></a>Dodawania zadania wsadowego wygasania sald urlopu (431266)

Jest teraz dostępne nowe zadanie wsadowe, które będzie uruchamiane codziennie. Pozostałe saldo urlopu jest zmniejszane, jeśli daty ważności stają się aktualne.

## <a name="exporting-personal-contacts-for-an-employee-using-the-worker-personal-contact-person-entity-doesnt-export-personal-contacts-with-the-parent-relationship-type-345893"></a>Eksportowanie osobistych osób kontaktowych pracownika za pomocą jednostki osobistej osoby kontaktowej pracownika nie powoduje eksportowania osobistych osób kontaktowych z nadrzędnym typem relacji (345893)

Jednostka danych **Osobista osoba kontaktowa pracownika** (**HcmPersonalContactPersonEntity** w DMF i **PersonalContactPerson** w OData) nie mogła wyeksportować osobistych osób kontaktowych, które mają typ relacji **Nadrzędna**. Ten problem został rozwiązany dla osobistych osób kontaktowych utworzonych po tej zmianie. Problem w przypadku osobistych osób kontaktowych typu **Nadrzędna** zostanie rozwiązany w późniejszej wersji.

## <a name="reason-codes-display-across-different-scenarios-when-theyre-marked-as-leave-and-absence-and-the-streamlined-employee-form-is-enabled-434163"></a>Kody przyczyn są wyświetlane w różnych scenariuszach, gdy są oznaczone jako Urlop i nieobecność, a udoskonalony formularz pracownika jest włączony (434163)

Ta zmiana ogranicza kody przyczyn tylko do kodów urlopów i nieobecności po włączeniu udoskonalonego wpisu pracownika.

## <a name="the-preview-feature-assign-a-leave-plan-to-employees-in-the-future-displays-error-433555"></a>Funkcja podglądu Przypisywanie plan urlopu do pracowników w przyszłości powoduje wyświetlanie błędu (433555)

Ta zmiana naprawia błąd występujący w przypadku, gdy do planu urlopu przypisano dwa typy urlopów i podjęto próbę przypisania pracownika.

## <a name="getting-started-banner-appears-for-all-users-441731"></a>Transparent wprowadzający jest widoczny dla wszystkich użytkowników (441731)

W przypadku tej zmiany transparent wprowadzający jest ukryty dla użytkowników, którzy nie są administratorami systemu ani administratorami zarządzania danymi. 

## <a name="the-common-data-service-worker-address-entity-works-differently-in-terms-of-date-time-effective-dates-in-human-resources-425071"></a>Jednostka adresu pracownika Common Data Service działa inaczej w zależności od daty i godziny dla czasu obowiązywania dat w aplikacji Human Resources (425071)

Ta zmiana powoduje, że informacje adresowe są wyrównywane w określonych scenariuszach na podstawie dat adresu.

## <a name="unable-to-add-an-attachment-to-an-approved-leave-request-425407"></a>Nie można dodać załącznika do zatwierdzonego wniosku o urlop (425407)

Od wersji z tego tygodnia można dodawać załączniki do zatwierdzonych wniosków o urlop bez zmiany wniosku o urlop.

## <a name="in-preview"></a>Wersja próbna

## <a name="leave-suspension"></a>Zawieszenie urlopu

Istnieje możliwość zawieszenia urlopu i nieobecności w Human Resources dla pracownika etatowego. Zawieszenie urlopu powoduje zatrzymanie naliczania dla wybranych typów urlopów. Jeśli zawieszenie następuje po zakończeniu procesu naliczania, wstrzymanie urlopu powoduje utworzenie skorygowanej korekty salda urlopu pracownika. Aby uzyskać więcej informacji, zobacz [Zawieś urlop](hr-leave-and-absence-suspend-leave.md).

## <a name="update-user-experience-to-indicate-that-accrual-is-suspended-429550"></a>Zaktualizowano środowisko użytkownika, aby umożliwić wskazanie, że naliczanie zostało zawieszone (429550)

Środowisko użytkownika wskazuje teraz, że naliczanie dla planu zostało zawieszone.

## <a name="suspend-leave-accrual-for-specified-leave-types-272447"></a>Wstrzymanie naliczania urlopu dla określonych typów urlopów (272447)

W tym wydaniu dział zasobów ludzkich może utworzyć regułę, aby wstrzymać naliczanie urlopów dla pracowników z wprowadzonymi wnioskami o urlop bezpłatny. Urlop bezpłatny może być typem, ale nie musi. Istnieje możliwość wstrzymania dowolnego urlopu na podstawie innego typu urlopu.

## <a name="dmf-entity-available-for-accrual-suspensions-429549"></a>Jednostka DMF dostępna dla wstrzymań naliczania (429549)

Jednostka DMF jest teraz dostępna dla wstrzymań naliczania.

## <a name="add-reason-code-to-accrual-suspensions-429547"></a>Dodano kod przyczyny do wstrzymań naliczania (429547)

Kody przyczyn zostały dodane do wstrzymania naliczania.

## <a name="begin-transitioning-from-human-resources-parameters-to-leave-and-absence-parameters"></a>Rozpoczęto przejście od parametrów zasobów ludzkich do parametrów urlopu i nieobecności

W tym wydaniu rozpoczęto łączenie parametrów zasobów ludzkich z parametrami urlopu i nieobecności.

## <a name="carry-forward-rules"></a>Zasady przenoszenia na następny okres

Można określić typ urlopu przeniesienia do przodu dla sald przeniesionych na następny okres, gdzie są przenoszone korekty do przodu. Jeśli na przykład pracownik przeniósł 10 dni do przodu, można wybrać inny typ urlopu dla tych 10 dni. Aby uzyskać więcej informacji, należy zapoznać się z tematem [Konfigurowanie typów urlopów i nieobecności](hr-leave-and-absence-types.md).

## <a name="see-also"></a>Informacje dodatkowe

[Nowości i zmiany w rozwiązaniu Human Resources](hr-admin-whats-new.md)</br>
[Omówienie rozwiązania Dynamics 365 Human Resources 2019, wydanie 2](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Aktualizowanie procesu](hr-admin-setup-update-process.md)</br>
[Zarządzanie funkcjami](hr-admin-manage-features.md)