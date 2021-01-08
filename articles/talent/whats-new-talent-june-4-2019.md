---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Talent (4 czerwiec 2019)
description: W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 06/04/2019
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
ms.search.validFrom: 2019-06-04
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 4a42a3b817024447e2ff26cfcb3cdd0df1351158
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/17/2020
ms.locfileid: "4528057"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-june-4-2019"></a>Nowości i zmiany w rozwiązaniu Dynamics 365 Talent (4 czerwiec 2019)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Zmiany w Attract

Ta wersja zawiera drobne poprawki błędów dla rozwiązania Dynamics 365 Talent: Attract.

## <a name="coming-soon-in-attract"></a>Wkrótce w aplikacji Attract

### <a name="job-approvals-on-the-home-page"></a>Zatwierdzenia zadań na stronie głównej

Zatwierdzenia są wyświetlane w sekcji **Zatwierdzenia** na pulpicie nawigacyjnym. Osoby zatwierdzające mogą przejrzeć swoje zatwierdzenia w obszarze **Przypisane do użytkownika** W tej sekcji jest wyświetlany identyfikator zadania, tytuł, inne osoby zatwierdzające oraz data przydzielenia zadania. Użytkownicy, którzy przesyłają zadanie do zatwierdzenia, mogą przeglądać swoje zadania zgodnie z **żądania użytkownika**. W tej sekcji są wyświetlane osoby zatwierdzające, które muszą nadal zatwierdzić przesłane zadanie.

## <a name="changes-in-onboard"></a>Zmiany w Onboard

Ta wersja zawiera drobne poprawki błędów dla rozwiązania Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Zmiany w Core HR

Zmiany opisane w tej części dotyczą kompilacji 8.1.2330.

### <a name="new-page-to-validate-position-hierarchy-data"></a>Nowa strona do sprawdzania poprawności danych hierarchii stanowisk

Pracownicy działu kadr i administratorzy mogą sprawdzać hierarchię kadry kierowniczej dla wszystkich odwołań cyklicznych, które zostały przypadkowo zaimportowane. Dostęp do tej nowej strony można uzyskać z menu **Administracja organizacyjna\>Łącza\>Stanowiska\>Sprawdzanie poprawności hierarchii stanowisk**.

### <a name="specify-reason-codes-on-leave-types"></a>Określ kody przyczyn dla typów urlopów

Organizacje mogą potrzebować dodatkowych informacji związanych z wnioskami o urlop. Można określić kody przyczyn skojarzonych z danym typem urlopu i wybrać kod przyczyny we wniosku o urlop.

### <a name="require-reason-codes-for-specific-leave-types-on-time-off-requests"></a>Wymaganie kodu przyczyny dla niektórych typów urlopów we wnioskach o czas wolny.

Organizacje mogą wymagać ustawienia kodów przyczyn dla określonych typów urlopu, kiedy pracownik składa wniosek urlopowy. To wymaganie może obowiązywać z powodu zasad dotyczących firmy lub przepisów prawa. Istnieje możliwość określenia typów urlopów wymagających podania kodu przyczyny i wymagania, aby pracownicy podawali powód dla typu urlopu we wniosku o urlop.

### <a name="provide-a-leave-and-absence-transaction-list-for-hr"></a>Podaj listę transakcji urlopów i nieobecności dla zasobów Ludzkich

Śledzenie czasu wolnego pracowników i monitorowanie, jak czas wolny jest obliczany nie tylko pomaga działowi HR w odpowiadaniu na pytania pracowników, ale także zapewnia odpowiednie wynagrodzenie za czas wolny. Zasoby ludzkie mają teraz nowy widok transakcji (dotacje, naliczenia, korekty i żądania) aby zobaczyć, co kryje się za saldami czasu wolnego.

### <a name="deleting-a-record-from-talent-doesnt-remove-the-record-from-common-data-service"></a>Usunięcie rekordu z talentów nie powoduje usunięcia rekordu z formularza Common Data Service

Wszystkie rekordy usunięte z Talent: Core HR teraz są również usuwane z systemu Common Data Service.

### <a name="variable-compensation-plan-valid-fromto-dates-arent-being-honored"></a>Okres ważności daty od/do w systemie wynagrodzeń o zmiennej wysokości nie jest uznawany

W tej wersji nie można zarejestrować pracownika w systemie wynagrodzeń o zmiennej wysokości, jeśli data początkowa jest wcześniejsza niż data rozpoczęcia lub data zakończenia, późniejsza niż data końcowa planu. 

### <a name="performance-review-comments-are-removed-when-users-select-cancel"></a>Komentarze do przeglądu wydajności są usuwane po wybraniu przez użytkownika przycisku Anuluj

W tym wydaniu występuje usunięcie błędu, gdzie komentarze są usuwane jeśli użytkownik zacznie zmieniać komentarz, a następnie wybiera opcję **Anuluj**. 

## <a name="in-preview"></a>Wersja próbna

### <a name="preview-features-are-enabled-only-in-sandbox-instances"></a>Funkcje podglądu są włączone tylko w środowisku testowym

Podczas zastrzegania nowej instancji talentów można określić, czy typem wystąpienia jest **Produkcja**, czy **Piaskownica - środowisko testowe**. Wystąpienia typu **Piaskownica** umożliwiają wczesne testowanie nowych funkcji. Wszystkie istniejące wystąpienia aplikacji Talent zostaną zaktualizowane do typu wystąpienia **Produkcja**. Jeśli chcesz, aby jedno z istniejących wystąpień zostało zaktualizowane do typu wystąpienia **Piaskownica**, skontaktuj się z [pomocą techniczną](https://docs.microsoft.com/dynamics365/unified-operations/talent/talent-support), aby zainicjować żądanie zmiany.

Aby uzyskać więcej informacji o publikowaniu zmian, zapoznaj się z tematem [Provision Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).

### <a name="restrict-leave-types-in-time-off-requests"></a>Ograniczanie typów urlopu we wnioskach o czas wolny

Organizacje mogą oferować pracownikom wiele różnych typów urlopów. Jednak może nie być właściwe, aby pracownicy składali wnioski o czas wolny na niektóre typy urlopów. Te typy urlopów mogą być zarządzane za pomocą polecenia HR. Za pomocą tej wersji można skonfigurować typy urlopów, na które pracownicy mogą zgłaszać wnioski o czas wolny. 

## <a name="coming-soon-in-core-hr"></a>Już wkrótce w Core HR

### <a name="view-extended-information-for-performance-in-manager-self-service"></a>Wyświetlanie rozszerzonych informacji o wydajności w module Self-Service Manager

Nowa opcja umożliwi menedżerom wyświetlanie wyników zarówno ich bezpośrednich raportów, jak i raportów rozszerzonych. Obecnie kierownicy wierszy mogą przypisywać i aktualizować cele wydajności oraz wydawać nowe recenzje, które są wspólnie zarządzane przez ich pracowników Ponadto menedżerowie etatowi i ich pracownicy mogą utrzymywać i aktualizować arkusze wydajności, aby zagwarantować płynność procesu oceny wydajności. Po zaimplementowaniu tej zmiany menedżerowie będą mogli wyświetlać i obsługiwać informacje związane z wydajnością raportów rozszerzonych, a także raporty bezpośrednie. 

### <a name="print-performance-reviews"></a>Drukowanie przeglądów wydajności

Pracownicy, menedżerowie i dział personalny będą mogli drukować przegląd wydajności pracownika.
