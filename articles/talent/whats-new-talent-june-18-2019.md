---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 for Talent (18 czerwiec 2019)
description: W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 for Talent.
author: Darinkramer
manager: AnnBe
ms.date: 06/18/2019
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
ms.search.validFrom: 2019-06-18
ms.dyn365.ops.version: Talent
ms.openlocfilehash: bfc90d6eec27e55364d4bf2279ffd32fb8d53ca8
ms.sourcegitcommit: f21b2349967feb3db2016c8ff83a2b11957f8863
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/20/2019
ms.locfileid: "1691977"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-june-18-2019"></a>Nowości i zmiany w rozwiązaniu Dynamics 365 for Talent (18 czerwiec 2019)

[!include [banner](includes/banner.md)]

W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 for Talent.

## <a name="changes-in-attract"></a>Zmiany w Attract

Ta wersja zawiera poprawki błędów dla programu Dynamics 365 Talent: Attract.

## <a name="coming-soon-in-attract"></a>Wkrótce w aplikacji Attract

### <a name="job-approvals-appear-on-the-home-page"></a>Zatwierdzenia zadań pojawiają się na stronie głównej

Zatwierdzenia są wyświetlane w sekcji **Zatwierdzenia** na pulpicie nawigacyjnym. Osoby zatwierdzające mogą przeglądać swoje zatwierdzenia w obszarze **Przypisane do Ciebie**, w którym jest wyświetlany identyfikator zadania, tytuł, inne osoby zatwierdzające i data przypisania zadania. Użytkownicy, którzy przesyłają zadanie do zatwierdzenia, mogą przeglądać swoje zadania w obszarze **Żądane przez Ciebie**, w którym są wyświetlane osoby zatwierdzające, które muszą jeszcze zatwierdzić przesłane zadanie.

## <a name="changes-in-onboard"></a>Zmiany w Onboard

Ta wersja zawiera poprawki błędów dla programu Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Zmiany w Core HR

Zmiany opisane w tej części dotyczą kompilacji 8.1.2347.

### <a name="confirmation-of-course-participants-causes-an-error"></a>Potwierdzenie uczestników kursu powoduje błąd

Okno dialogowe drukowania raportu dotyczącego uczestników kursu zostało usunięte. Ten raport nie jest obsługiwany w Talencie.

### <a name="the-compensation-section-of-the-transfer-worker-page-isnt-available-in-some-scenarios"></a>Sekcja wynagrodzeń strony Przeniesienie pracownika jest niedostępna w niektórych scenariuszach

Ta zmiana umożliwia użytkownikom wprowadzanie danych o wynagrodzeniach po ich wypełnieniu na stronie **Pracownik przeniesienia**.

## <a name="in-preview"></a>Wersja próbna

### <a name="preview-features-will-be-enabled-only-in-sandbox-environments"></a>Funkcje wersji Preview będą włączone tylko w środowiskach piaskownicy

Aby uzyskać więcej informacji o publikowaniu zmian, zapoznaj się z tematem [Provision Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).

Podczas zastrzegania nowej instancji talentów można wskazać, czy typem wystąpienia jest **Produkcja** czy **Piaskownica** (środowisko testowe). Typ instancji **Piaskownica** umożliwia wczesne testowanie nowych funkcji. Wszystkie istniejące wystąpienia aplikacji Talent zostaną zaktualizowane do typu wystąpienia **Produkcja**. Jeśli chcesz, aby jedno z istniejących wystąpień zostało zaktualizowane do typu wystąpienia **Piaskownica**, skontaktuj się z [pomocą techniczną](https://docs.microsoft.com/dynamics365/unified-operations/talent/talent-support), aby zainicjować żądanie zmiany.

### <a name="restrict-the-leave-types-in-time-off-requests"></a>Ograniczanie typów urlopu we wnioskach o czas wolny

Organizacje mogą oferować pracownikom wiele różnych typów urlopów. Jednak może nie być właściwe, aby pracownicy składali wnioski o czas wolny na niektóre typy urlopów. Te typy urlopów mogą być zarządzane za pomocą polecenia HR. Za pomocą tej wersji można skonfigurować typy urlopów, na które pracownicy mogą zgłaszać wnioski o czas wolny. 

## <a name="coming-soon-in-core-hr"></a>Już wkrótce w Core HR

### <a name="common-data-service-entity-support-for-custom-fields"></a>Obsługa jednostek w Common Data Service dla pól niestandardowych

Poniższe jednostki obsługują pola niestandardowe: kod zarobków płac i punkt odniesienia wynagrodzeń 

### <a name="new-common-data-service-entities"></a>Nowe Common Data Service jednostki

Jednostka kody przyczyn zostanie dodana do pola Common Data Service.

### <a name="view-performance-information-for-direct-and-extended-reports-in-manager-self-service"></a>Wyświetlanie informacji o wydajności dla bezpośrednich i rozszerzonych raportów w module Self-Service Manager

Nowa opcja umożliwi menedżerom wyświetlanie wyników zarówno ich bezpośrednich raportów, jak i raportów rozszerzonych. Obecnie menedżerowie liniowi mogą przypisywać i aktualizować cele wydajności oraz wystawiać nowe recenzje. Ponadto menedżerowie etatowi i ich pracownicy mogą utrzymywać i aktualizować arkusze wydajności, aby zagwarantować płynność procesu oceny wydajności. Po zaimplementowaniu tej zmiany menedżerowie będą mogli wyświetlać i obsługiwać informacje związane z wydajnością raportów rozszerzonych, a także raporty bezpośrednie.

### <a name="print-performance-reviews"></a>Drukowanie przeglądów wydajności

Pracownicy, menedżerowie i dział personalny będą mogli drukować przegląd wydajności pracownika.
