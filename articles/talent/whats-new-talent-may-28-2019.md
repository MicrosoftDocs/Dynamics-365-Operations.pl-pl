---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 for Talent (28 maja 2019 r.)
description: W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 for Talent.
author: Darinkramer
manager: AnnBe
ms.date: 05/28/2019
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
ms.search.validFrom: 2019-05-28
ms.dyn365.ops.version: Talent
ms.openlocfilehash: c99e0f3637a8d958e31a046eaad6faa57ce3e1e7
ms.sourcegitcommit: 1bf6a8b2f872394a4f242f9ff13c67e8e1ae8f65
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/03/2019
ms.locfileid: "1856288"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-may-28-2019"></a>Nowości i zmiany w rozwiązaniu Dynamics 365 for Talent (28 maja 2019 r.)

[!include [banner](includes/banner.md)]

W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Dynamics 365 for Talent.

## <a name="changes-in-attract"></a>Zmiany w Attract
Ta wersja zawiera poprawki błędów dla programu Dynamics 365 Talent: Attract.

## <a name="coming-soon-in-attract"></a>Wkrótce w aplikacji Attract

### <a name="job-approvals-on-home-page"></a>Zatwierdzenia zadań na stronie głównej

Zatwierdzenia są wyświetlane w sekcji **Zatwierdzenia** na pulpicie nawigacyjnym. Osoby zatwierdzające mogą przeglądać swoje zatwierdzenia w obszarze **Przypisane do Ciebie**, w którym jest wyświetlany identyfikator zadania, tytuł, inne osoby zatwierdzające i data przypisania. Użytkownicy, którzy przesyłają zadanie do zatwierdzenia, mogą przeglądać swoje zadania w obszarze **Żądane przez Ciebie**, w którym są wyświetlane osoby zatwierdzające, które muszą jeszcze zatwierdzić przesłane zadanie.

## <a name="changes-in-onboard"></a>Zmiany w Onboard
Ta wersja zawiera poprawki błędów dla programu Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Zmiany w Core HR
Zmiany opisane w tej części dotyczą kompilacji 8.1.2319.

### <a name="common-data-service-entity-support-for-custom-fields"></a>Obsługa jednostek w Common Data Service dla pól niestandardowych

W tej wersji następujące jednostki Common Data Service obsługują obecnie niestandardowe pola: szczegóły stawki obliczania świadczeń, kalendarz pracy, wiersz dnia wolnego i zatrudnienie.

### <a name="copy-position-now-includes-payroll-details"></a>Podczas kopiowania stanowiska są teraz uwzględniane szczegóły listy płac
W przypadku użycia funkcji **Kopiuj stanowisko** i wybrania wszystkich opcji informacje o szczegółach listy płac zostaną uwzględnione w kopii. 

## <a name="in-preview-in-core-hr"></a>W wersji zapoznawczej aplikacji Core HR

### <a name="restrict-the-leave-types-in-time-off-requests"></a>Ograniczanie typów urlopu we wnioskach o czas wolny

Organizacje mogą oferować pracownikom wiele różnych typów urlopów. Niektóre z tych typów urlopów mogą być nieodpowiednie dla pracowników, którzy przesyłają wniosek o czas wolny, i są zarządzane tylko przez dział zasobów ludzkich (HR). Za pomocą tej wersji można skonfigurować typy urlopów, na które pracownicy mogą zgłaszać wnioski o czas wolny. 

### <a name="new-page-to-validate-position-hierarchy-data"></a>Nowa strona do sprawdzania poprawności danych hierarchii stanowisk

Dział zasobów ludzkich i administratorzy mogą sprawdzać hierarchię kadry kierowniczej dla wszystkich odwołań cyklicznych, które mogły zostać przypadkowo zaimportowane. Dostęp do tej nowej strony można uzyskać z menu **Administracja organizacyjna > Łącza > Stanowiska > Sprawdzanie poprawności hierarchii stanowisk**.

### <a name="specify-reason-codes-on-leave-types"></a>Określ kody przyczyn dla typów urlopów

Organizacje mogą potrzebować dodatkowych informacji związanych z wnioskami o urlop. Można określić kody przyczyn skojarzonych z danym typem urlopu i wybrać kod przyczyny we wniosku o urlop.

### <a name="require-reason-codes-for-specific-leave-types-on-time-off-requests"></a>Wymaganie kodu przyczyny dla niektórych typów urlopów we wnioskach o czas wolny.

Organizacje mogą wymagać ustawienia kodów przyczyn dla określonych typów urlopu, kiedy pracownik składa wniosek urlopowy. To wymaganie może obowiązywać z powodu zasad dotyczących firmy lub przepisów prawa. Istnieje możliwość określenia typów urlopów wymagających podania kodu przyczyny i wymagania, aby pracownicy podawali powód dla typu urlopu we wniosku o urlop.

### <a name="provide-a-leave-and-absence-transaction-list-for-hr"></a>Podaj listę transakcji urlopów i nieobecności dla zasobów Ludzkich

Śledzenie czasu wolnego pracowników i monitorowanie, jak czas wolny jest obliczany nie tylko pomaga działowi HR w odpowiadaniu na pytania pracowników, ale także zapewnia odpowiednie wynagrodzenie za czas wolny. Zasoby ludzkie mają teraz nowy widok transakcji (dotacje, naliczenia, korekty i żądania) aby zobaczyć, co kryje się za saldami czasu wolnego.
