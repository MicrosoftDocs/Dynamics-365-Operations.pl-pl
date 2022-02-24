---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Talent (25 czerwiec 2019)
description: W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 06/25/2019
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
ms.search.validFrom: 2019-06-25
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 98ac7df9fa33635814b390427fd3292bdc1175ed
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/17/2020
ms.locfileid: "4528652"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-june-25-2019"></a>Nowości i zmiany w rozwiązaniu Dynamics 365 Talent (25 czerwiec 2019)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Zmiany w Attract

Ta wersja zawiera drobne poprawki błędów dla rozwiązania Dynamics 365 Talent: Attract.

## <a name="coming-soon-in-attract"></a>Wkrótce w aplikacji Attract

### <a name="job-approvals-appear-on-the-home-page"></a>Zatwierdzenia zadań pojawiają się na stronie głównej

Zatwierdzenia są wyświetlane w sekcji **Zatwierdzenia** na pulpicie nawigacyjnym. Osoby zatwierdzające mogą przeglądać swoje zatwierdzenia w obszarze **Przypisane do Ciebie**, w którym jest wyświetlany identyfikator zadania, tytuł, inne osoby zatwierdzające i data przypisania zadania. Użytkownicy, którzy przesyłają zadanie do zatwierdzenia, mogą przeglądać swoje zadania w obszarze **Żądane przez Ciebie**, w którym są wyświetlane osoby zatwierdzające, które muszą jeszcze zatwierdzić przesłane zadanie.

## <a name="changes-in-onboard"></a>Zmiany w Onboard
Ta wersja zawiera drobne poprawki błędów dla rozwiązania Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Zmiany w Core HR

Zmiany opisane w tej części dotyczą kompilacji 8.1.2357.

### <a name="incorrect-value-displayed-for-primary-position-314266"></a>Wyświetlana jest niepoprawna wartość stanowiska podstawowego (314266)

Te zmiany będą stale wyświetlać ustawienie **Pozycja główna** na wszystkich stronach.

### <a name="cant-edit-after-recalling-the-workflow-in-review-318180"></a>Nie można edytować po odwołaniu przepływu pracy w przeglądzie (318180)

Można teraz edytować recenzje, które zostały odwołane za pośrednictwem przepływu pracy.

### <a name="final-comments-field-in-reviews-isnt-translated-325921"></a>Pole komentarzy ostatecznych w recenzjach nie jest tłumaczone (325921)

Etykieta **Ostatecznego komentarza** zostanie przetłumaczona w Talencie.

### <a name="preview-features-will-be-enabled-only-in-sandbox-environments"></a>Funkcje wersji Preview będą włączone tylko w środowiskach piaskownicy

Podczas zastrzegania nowej instancji talentów można wskazać, czy typem wystąpienia jest **Produkcja** czy **Piaskownica** (środowisko testowe). Typ instancji **Piaskownica** umożliwia wczesne testowanie nowych funkcji. Wszystkie istniejące wystąpienia aplikacji Talent zostaną zaktualizowane do typu wystąpienia **Produkcja**. Jeśli chcesz, aby jedno z istniejących wystąpień zostało zaktualizowane do typu wystąpienia **Piaskownica**, skontaktuj się z [pomocą techniczną](https://docs.microsoft.com/dynamics365/unified-operations/talent/talent-support), aby zainicjować żądanie zmiany.

Aby uzyskać więcej informacji o publikowaniu zmian, zapoznaj się z tematem [Provision Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).

## <a name="in-preview"></a>Wersja próbna

### <a name="restrict-the-leave-types-in-time-off-requests"></a>Ograniczanie typów urlopu we wnioskach o czas wolny

Organizacje mogą oferować pracownikom wiele różnych typów urlopów. Jednak może nie być właściwe, aby pracownicy składali wnioski o czas wolny na niektóre typy urlopów. Te typy urlopów mogą być zarządzane za pomocą polecenia HR. Za pomocą tej wersji można skonfigurować typy urlopów, na które pracownicy mogą zgłaszać wnioski o czas wolny. 

## <a name="coming-soon-in-core-hr"></a>Już wkrótce w Core HR

### <a name="feature-management-area-in-talent"></a>Obszar zarządzania funkcjami w Talencie

**Zarządzanie funkcji** zostanie usunięte z **Administracja systemu** z powodu problemów z tą funkcją. Firma Microsoft ponownie wprowadzi **Zarządzanie funkcji** w przyszłym wydaniu systemu. 

### <a name="common-data-service-entity-support-for-custom-fields"></a>Obsługa jednostek w Common Data Service dla pól niestandardowych

Poniższe jednostki umożliwiają obsługę pól niestandardowych: **Kod zarobków dla listy płac**, **Zdarzenie stałego wynagrodzenia**, **Siatka wynagrodzeń**, **Okres płac** oraz **Punkt odniesienia wynagrodzeń**. 

### <a name="new-common-data-service-entities"></a>Nowe Common Data Service jednostki

Jednostka **Kody przyczyn** zostanie dodana do Common Data Service.

### <a name="view-performance-information-for-direct-and-extended-reports-in-manager-self-service"></a>Wyświetlanie informacji o wydajności dla bezpośrednich i rozszerzonych raportów w module Self-Service Manager

Nowa opcja umożliwi menedżerom wyświetlanie wyników zarówno ich bezpośrednich raportów, jak i raportów rozszerzonych. Obecnie menedżerowie liniowi mogą przypisywać i aktualizować cele wydajności oraz wystawiać nowe recenzje. Ponadto bezpośredni menedżerowie i ich pracownicy mogą utrzymywać i aktualizować dzienniki wydajności, aby zapewnić sprawny przebieg procesu przeglądu wydajności. Po zaimplementowaniu tej zmiany menedżerowie będą mogli wyświetlać i obsługiwać informacje związane z wydajnością raportów rozszerzonych, a także raporty bezpośrednie.

### <a name="print-performance-reviews"></a>Drukowanie przeglądów wydajności

Pracownicy, menedżerowie i dział personalny będą mogli drukować przegląd wydajności pracownika.
