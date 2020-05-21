---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources (1 maja 2020 r.)
description: W tym artykule opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Human Resources.
author: Darinkramer
manager: AnnBe
ms.date: 05/01/2020
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
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: f1a0cfd1c1b0dcc9defaad7e4cce22ebe1e91fae
ms.sourcegitcommit: cc5dc0bd90277f1ba684dd310da3274886ce573c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/29/2020
ms.locfileid: "3320926"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-may-1-2020"></a>Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources (1 maja 2020 r.)

W tym artykule opisano nowe oraz zmienione funkcje dostępne w Dynamics 365 Human Resources. Zmiany dotyczą kompilacji o numerze 8.1.3196. Liczby w nawiasach w niektórych nagłówkach odnoszą się do numerów pomocy w LCS w charakterze informacyjnym.

## <a name="new-performance-management-entities-available-in-data-management-framework-dmf"></a>Nowe jednostki zarządzania wydajnością dostępne w strukturze DMF (Data Management Framework)

Dostępne są teraz nowe jednostki. Jeśli te jednostki nie są widoczne na liście jednostek, należy skorzystać z opcji **Odśwież jednostki** w **Parametry struktury > Ustawienia jednostki > Odśwież listę jednostek**.

- **Kompetencje dotyczące dyskusji**
- **Cele dyskusji**
- **Miara dyskusji**
- **Temat dyskusji**
- **Arkusz wydajności**
- **Miara**
- **Miara celu**

Ponadto dodano elementy **Łączny wynik** i **Średni wynik** do jednostki **Dyskusja**.

## <a name="increase-length-of-leave-request-comments-275641"></a>Zwiększona długość komentarzy do wniosku o urlop (275641)

Komentarze we wnioskach o urlop mogą teraz zawierać więcej niż 100 znaków.

## <a name="final-comments-on-reviews-dont-appear-when-the-manager-or-employee-is-signed-into-a-different-company-431688"></a>Ostateczne komentarze dotyczące recenzji nie są wyświetlane, gdy kierownik lub pracownik etatowy są zalogowani do innej firmy (431688)

Wszystkie komentarze będą teraz widoczne podczas przeglądania recenzji.

## <a name="user-defined-links-arent-supported-on-new-worker-form-390374"></a>Linki zdefiniowane przez użytkownika nie są obsługiwane w formularzu nowego pracownika (390374)

Linki zdefiniowane przez użytkownika są teraz włączone w udoskonalonym formularzu **Pracownik**.

## <a name="hcmratinglevelentity-causes-odata-api-crash-439476"></a>Jednostka HcmRatingLevelEntity powoduje awarię interfejsu API OData (439476)

Ta zmiana powoduje usunięcie awarii interfejsu API. Ten błąd powoduje zduplikowana nazwa.

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

## <a name="known-issues"></a>Znane problemy

## <a name="sharepoint-preview-doesnt-work-in-some-environments"></a>Podgląd SharePoint nie działa w niektórych środowiskach

Jeśli Podgląd dokumentów przechowywanych w SharePoint nie działa, spróbuj wykonać poniższą procedurę:

1. Sprawdź, czy konto użytkownika administratora zawiera wiadomość e-mail skojarzoną z rekordem użytkownika. Można przejrzeć te informacje na stronie **Użytkownik**. Jeśli poczta e-mail nie jest skonfigurowana, należy dodać wiadomość e-mail i dostawcę za pomocą dodatku OData dla programu Excel. Domyślnie adres e-mail nie jest obecny w projekcie programu Excel. Musisz edytować projekt programu Excel, dodać wszystkie pola, zastosować je i odświeżyć. Po wykonaniu tych kroków można zaktualizować konto administratora.

2. Gdy konto Administratora ma skojarzone konto e-mail, zaloguj się do modułu Human Resources z poświadczeniami administratora.

3. Aby uruchomić podgląd dokumentu, uzyskaj dostęp do załącznika SharePoint.

4. Zaloguj się przy użyciu konta innego użytkownika, które ma dostęp do załączników i sprawdź, czy podgląd działa zgodnie z oczekiwaniami.