---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Talent (13 maja 2019 r.)
description: W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 05/13/2019
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
ms.search.validFrom: 2019-05-13
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 11c9f03f4b3915d81b624115a1d97a0c7bc31709
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/17/2020
ms.locfileid: "4529739"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-may-13-2019"></a>Nowości i zmiany w rozwiązaniu Dynamics 365 Talent (13 maja 2019 r.)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Dynamics 365 Talent.

## <a name="coming-soon-in-attract"></a>Wkrótce w aplikacji Attract

### <a name="job-approvals-on-home-page"></a>Zatwierdzenia zadań na stronie głównej

Zatwierdzenia są wyświetlane w sekcji **Zatwierdzenia** na pulpicie nawigacyjnym. Osoby zatwierdzające mogą przeglądać swoje zatwierdzenia w obszarze **Przypisane do Ciebie**, w którym jest wyświetlany identyfikator zadania, tytuł, inne osoby zatwierdzające i data przypisania. Użytkownicy, którzy przesyłają zadanie do zatwierdzenia, mogą przeglądać swoje zadania w obszarze **Żądane przez Ciebie**, w którym są wyświetlane osoby zatwierdzające, które muszą jeszcze zatwierdzić przesłane zadanie.

## <a name="changes-in-onboard"></a>Zmiany w Onboard

Ta wersja zawiera drobne poprawki błędów dla rozwiązania Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Zmiany w Core HR

Zmiany opisane w tej części dotyczą kompilacji 8.1.2297. Liczby w nawiasach w niektórych nagłówkach odnoszą się do numerów pomocy w usługach Microsoft Dynamics Lifecycle Services (LCS).

### <a name="indicate-instance-type-when-provisioning-talent"></a>Wskaż typ wystąpienia podczas inicjowania obsługi administracyjnej w aplikacji Talent

Podczas inicjowania obsługi nowego wystąpienia aplikacji Talent można wskazać, czy typ wystąpienia to **Produkcja** czy **Piaskownica**, co pozwala na wczesne testowanie nowych funkcji. Wszystkie istniejące wystąpienia aplikacji Talent zostaną zaktualizowane do typu wystąpienia **Produkcja**. Jeśli chcesz, aby jedno z istniejących wystąpień zostało zaktualizowane do typu wystąpienia **Piaskownica**, skontaktuj się z [pomocą techniczną](https://docs.microsoft.com/dynamics365/unified-operations/talent/talent-support), aby zainicjować żądanie zmiany.

### <a name="common-data-service-entity-support-for-custom-fields"></a>Obsługa jednostek w Common Data Service dla pól niestandardowych

W wydaniu z tego tygodnia następujące jednostki Common Data Service obsługują obecnie niestandardowe pola: zatrudnienie, częstotliwość obliczania świadczeń, stawka obliczania świadczeń, kalendarz pracy, dzień wolny i typy identyfikacji.

### <a name="common-data-service-integration-page"></a>Strona integracji Common Data Service

W tej wersji znajduje się nowa opcja na stronie **Administrowanie systemem > Łącza > Integracje > Konfiguracja Common Data Service**. Opcja **Konfiguracja Common Data Service** umożliwia administratorowi lub administratorowi zarządzania danymi pewną elastyczność i wgląd w działanie Common Data Service. Za pomocą tej opcji można włączyć lub wyłączyć integrację Common Data Service z wystąpieniem aplikacji Talent i wyświetlić szczegóły synchronizacji między wystąpieniem aplikacji Talent a Common Data Service.

### <a name="import-performance-data-with-final-employee-rating-316710"></a>Importowanie danych dotyczących wydajności z ostateczną oceną pracownika (316710)

W tej wersji można zaimportować historyczne dane dotyczące oceny pracownika. Pole **FinalEmployeeRatingId** ma teraz uprawnienia do zapisywania.

### <a name="cant-create-worker-address-in-common-data-service-and-sync-it-with-talent-317555"></a>Nie można utworzyć adresu pracownika w Common Data Service i zsynchronizować go z aplikacją Talent (317555)

Ta zmiana umożliwia synchronizowanie danych adresowych utworzonych w Common Data Service z aplikacją Talent.

## <a name="in-preview"></a>Wersja próbna

### <a name="new-page-to-validate-position-hierarchy-data"></a>Nowa strona do sprawdzania poprawności danych hierarchii stanowisk

Zasoby ludzkie (HR) i administratorzy mogą sprawdzać hierarchię kadry kierowniczej dla wszystkich odwołań cyklicznych, które mogły zostać przypadkowo zaimportowane. Dostęp do tej nowej strony można uzyskać z menu **Administracja organizacyjna > Łącza > Stanowiska > Sprawdzanie poprawności hierarchii stanowisk**.

### <a name="specify-reason-codes-on-leave-types"></a>Określ kody przyczyn dla typów urlopów

Organizacje mogą potrzebować dodatkowych informacji związanych z wnioskami o urlop. Można określić kody przyczyn skojarzonych z danym typem urlopu i wybrać kod przyczyny we wniosku o urlop.

### <a name="require-reason-codes-for-specific-leave-types-on-time-off-requests"></a>Wymaganie kodu przyczyny dla niektórych typów urlopów we wnioskach o czas wolny.

Organizacje mogą wymagać ustawienia kodów przyczyn dla określonych typów urlopu, kiedy pracownik składa wniosek urlopowy. To wymaganie może obowiązywać z powodu zasad dotyczących firmy lub przepisów prawa. Istnieje możliwość określenia typów urlopów wymagających podania kodu przyczyny i wymagania, aby pracownicy podawali powód dla typu urlopu we wniosku o urlop.

### <a name="provide-a-leave-and-absence-transaction-list-for-hr"></a>Podaj listę transakcji urlopów i nieobecności dla zasobów Ludzkich

Śledzenie czasu wolnego pracowników i monitorowanie, jak czas wolny jest obliczany nie tylko pomaga działowi HR w odpowiadaniu na pytania pracowników, ale także zapewnia odpowiednie wynagrodzenie za czas wolny. Zasoby ludzkie mają teraz nowy widok transakcji (dotacje, naliczenia, korekty i żądania) aby zobaczyć, co kryje się za saldami czasu wolnego.


[!INCLUDE[footer-include](../includes/footer-banner.md)]