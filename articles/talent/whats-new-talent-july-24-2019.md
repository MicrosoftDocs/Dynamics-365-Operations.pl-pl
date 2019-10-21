---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Talent (23 lipiec 2019)
description: W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 07/23/2019
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
ms.search.validFrom: 2019-07-23
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 428e862b84a17f0d50edf034b4cc836e5ae7710d
ms.sourcegitcommit: 434dd21450bddcd891aba0555b9853d9ba0afb6f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2019
ms.locfileid: "2010275"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-july-23-2019"></a>Nowości i zmiany w rozwiązaniu Dynamics 365 Talent (23 lipiec 2019)

[!include [banner](includes/banner.md)]

W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Zmiany w Attract

### <a name="pdf-renderer-for-candidate-documents"></a>Renderowanie dokumentów PDF dla kandydatów

Attract dla użytkowników może teraz wyświetlać załączniki PDF dla kandydatów w przeglądarce dokumentów zamiast pobierać załączniki.

### <a name="signing-up-for-attract-user-research-group"></a>Zapisywanie się do grupy badawczej użytkownika Attract 

Obecnie planuje się nowe możliwości produktów lub funkcje wersji, dlatego szukamy naszych użytkowników, którzy poinforumują nas, czy zmierzamy w dobrym kierunku. Zainteresowani użytkownicy mogą teraz zarejestrować się jako część naszej grupy badawczej użytkownika, korzystając z łącza zapisywania w naszej aplikacji.

### <a name="job-approvals-appear-on-the-home-page"></a>Zatwierdzenia zadań pojawiają się na stronie głównej

Zatwierdzenia są wyświetlane w sekcji **Zatwierdzenia** na pulpicie nawigacyjnym. Osoby zatwierdzające mogą przeglądać swoje zatwierdzenia w obszarze **Przypisane do Ciebie**, w którym jest wyświetlany identyfikator zadania, tytuł, inne osoby zatwierdzające i data przypisania zadania. Użytkownicy, którzy przesyłają zadanie do zatwierdzenia, mogą przeglądać swoje zadania w obszarze **Żądane przez Ciebie**, w którym są wyświetlane osoby zatwierdzające, które muszą jeszcze zatwierdzić przesłane zadanie.

## <a name="changes-in-onboard"></a>Zmiany w Onboard
Ta wersja zawiera drobne poprawki błędów dla rozwiązania Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Zmiany w Core HR
Zmiany opisane w tej części dotyczą kompilacji 8.1.2394.

### <a name="entity-support-for-custom-fields-in-common-data-service"></a>Obsługa firm w Common Data Service dla pól niestandardowych 

W tym wydaniu **Kalendarz roboczy** i **Dzień kalendarzowy** obsługują teraz pola niestandardowe w Common Data Service.

### <a name="restrict-leave-types-in-time-off-requests"></a>Ograniczanie typów urlopu we wnioskach o czas wolny

Organizacje mogą oferować pracownikom wiele różnych typów urlopów. Jednak może nie być właściwe, aby pracownicy składali wnioski o czas wolny na niektóre typy urlopów. Te typy urlopów mogą być zarządzane za pomocą polecenia HR. Za pomocą tej wersji można skonfigurować typy urlopów, na które pracownicy mogą zgłaszać wnioski o czas wolny. 

## <a name="in-preview"></a>Wersja próbna

### <a name="preview-features-are-enabled-only-in-sandbox-instances"></a>Funkcje podglądu są włączone tylko w środowisku testowym

Podczas zastrzegania nowej instancji talentów można określić, czy typem wystąpienia jest **Produkcja**, czy **Piaskownica - środowisko testowe**. Wystąpienia typu **Piaskownica** umożliwiają wczesne testowanie nowych funkcji. Wszystkie istniejące wystąpienia aplikacji Talent zostaną zaktualizowane do typu wystąpienia **Produkcja**. Jeśli chcesz, aby jedno z istniejących wystąpień zostało zaktualizowane do typu wystąpienia **Piaskownica**, skontaktuj się z [pomocą techniczną](https://docs.microsoft.com/dynamics365/unified-operations/talent/talent-support), aby zainicjować żądanie zmiany.

Aby uzyskać więcej informacji o publikowaniu zmian, zapoznaj się z tematem [Provision Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).

### <a name="view-extended-information-for-performance-in-manager-self-service"></a>Wyświetlanie rozszerzonych informacji o wydajności w module Self-Service Manager

Nowa opcja umożliwi menedżerom wyświetlanie wyników zarówno ich bezpośrednich raportów, jak i raportów rozszerzonych. Obecnie kierownicy wierszy mogą przypisywać i aktualizować cele wydajności oraz wydawać nowe recenzje, które są wspólnie zarządzane przez ich pracowników Ponadto bezpośredni menedżerowie i ich pracownicy mogą utrzymywać i aktualizować dzienniki wydajności, aby zapewnić sprawny przebieg procesu przeglądu wydajności. Po zaimplementowaniu tej zmiany menedżerowie będą mogli wyświetlać i obsługiwać informacje związane z wydajnością raportów rozszerzonych, a także raporty bezpośrednie. 

## <a name="coming-soon"></a>Wkrótce

### <a name="region-support-for-canada-and-southeast-asia"></a>Obsługa regionu Kanada i Południowo-Wschodnia Azja

Mamy przyjemność poinformować o tym, że rozwiązania Talent od 1 sierpnia 2019 r. będą dostępne w regionach Kanada i Azja Południowo-Wschodnia. Dzięki tej zmianie można tworzyć środowiska w regionach Kanada i Azja, a wszystkie dane Talent będą obsługiwane wyłącznie w tych lokalizacjach. Środowisko w tych nowych regionach można utworzyć, wybierając lokalizację w oknie dialogowym Nowe środowisko i używając tego środowiska do inicjowania obsługi Talent w LCS, zgodnie z opisem [Inicjowanie obsługi rozwiązania Talent](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/provisioning-talent).

Migracja danych istniejących projektów z innych regionów do Kanady i Azji nie jest obsługiwana. Tylko nowe projekty mogą zostać zainicjowane do tych nowych obsługiwanych regionów.
