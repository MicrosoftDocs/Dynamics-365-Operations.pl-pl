---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 for Talent (27 sierpnia 2019 r.)
description: W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 for Talent.
author: Darinkramer
manager: AnnBe
ms.date: 8/27/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: andreabichsel
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-08-27
ms.dyn365.ops.version: Talent
ms.openlocfilehash: a405ee96c36dd803fb46894ab58eca9dbfd81b5f
ms.sourcegitcommit: 097492a9e4f53a5e1fd5385d8764798518326818
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/29/2019
ms.locfileid: "1927993"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-august-27-2019"></a>Nowości i zmiany w rozwiązaniu Dynamics 365 for Talent (27 sierpnia 2019 r.)

[!include [banner](includes/banner.md)]

W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Dynamics 365 for Talent.

## <a name="changes-in-attract"></a>Zmiany w Attract

Ta wersja zawiera poprawki błędów dla programu Dynamics 365 Talent: Attract.

## <a name="changes-in-onboard"></a>Zmiany w Onboard

Ta wersja zawiera poprawki błędów dla programu Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Zmiany w Core HR

Zmiany opisane w tej części dotyczą kompilacji 8.1.2447. Liczby w nawiasach w niektórych nagłówkach odnoszą się do numerów pomocy w usługach Microsoft Dynamics Lifecycle Services (LCS).

### <a name="preview-features-are-enabled-only-in-sandbox-instances"></a>Funkcje podglądu są włączone tylko w środowisku testowym

Podczas zastrzegania nowej instancji talentów można określić, czy typem wystąpienia jest Produkcja, czy Piaskownica - środowisko testowe. Wystąpienia typu Piaskownica umożliwiają wczesne testowanie nowych funkcji. Wszystkie istniejące wystąpienia aplikacji Talent zostaną zaktualizowane do typu wystąpienia Produkcja. Jeśli chcesz, aby jedno z istniejących wystąpień zostało zaktualizowane do typu wystąpienia Piaskownica, skontaktuj się z pomocą techniczną, aby zainicjować żądanie zmiany.

Aby uzyskać więcej informacji o publikowaniu zmian, zapoznaj się z tematem [Provision Talent](./provisioning-talent.md).

### <a name="view-extended-information-for-performance-in-manager-self-service"></a>Wyświetlanie rozszerzonych informacji o wydajności w module Self-Service Manager

Nowa opcja umożliwi menedżerom wyświetlanie wyników zarówno ich bezpośrednich raportów, jak i raportów rozszerzonych. Obecnie menedżerowie liniowi mogą przypisywać i aktualizować cele wydajności oraz wystawiać nowe recenzje. Ponadto bezpośredni menedżerowie i ich pracownicy mogą utrzymywać i aktualizować dzienniki wydajności, aby zapewnić sprawny przebieg procesu przeglądu wydajności. Po zaimplementowaniu tej zmiany menedżerowie będą mogli wyświetlać i obsługiwać informacje związane z wydajnością raportów rozszerzonych, a także raporty bezpośrednie.

### <a name="deleting-legal-entities-isnt-allowed-if-employees-exist-within-the-company-339849"></a>Usuwanie firm jest niedozwolone, jeśli pracownicy istnieją w firmie (339849)

W przypadku tej zmiany nie można usuwać ani kasować firm, jeśli istnieją pracownicy i inne powiązane z firmą dane.

### <a name="compensation-management-business-intelligence-analytics-dont-match-on-the-compensation-workspace-322493"></a>Atatystyki analityki biznesowej zarządzania wynagrodzeniem nie pasują do obszaru roboczego wynagrodzenie (322493)

W tej wersji analiza wynagrodzeń została skorygowana w celu dokładnego odzwierciedlenia planów przypisanych do pracowników.

### <a name="workflow-placeholder-company-displays-dat-when-hiring-employees-through-workflow-343905"></a>Symbol zastępczy przepływu pracy %company% wyświetla DAT podczas zatrudniania pracowników za pośrednictwem przepływu pracy (343905)

W tej wersji symbolu zastępczego firmy jest wyświetlana firm skojarzona z zatrudnieniem nowego pracownika.

### <a name="the-cdsjobposition-entity-displays-an-error-when-valid-to-date-is-set-349387"></a>Jednostka CDSJobPosition wyświetla błąd, gdy jest ustawiona data ważności do dnia (349387)

W tej wersji źródła danych **Szczegóły dotyczące stanowiska** i **Okres ważności stanowiska** w jednostce **CDSJobPosition** umożliwiają edycję z Common Data Service do pól **Data wprowadzenia**. 

### <a name="for-employee-termination-the-last-day-worked-is-populated-on-assignment-end-date-332496"></a>W przypadku zakończenia zatrudnienia pracownika ostatni dzień pracy jest wypełniany datą zakończenia przypisania (332496)

Ta zmiana powoduje, że data **Data zakończenia przypisania** jest ustawiana na **Data zakończenia zatrudnienia**. Te ustawienia domyślne można zmieniać podczas wprowadzania danych.

### <a name="legal-entities-arent-limited-with-hire-338871"></a>Firmy nie są ograniczone przez zatrudnienie (338871)
 
Ta zmiana ogranicza proces zatrudniania, tak aby były wyświetlane tylko te firmy, do których użytkownik ma dostęp.  

## <a name="in-preview"></a>Wersja próbna

### <a name="streamlined-employee-entry-and-navigation"></a>Usprawnione wprowadzanie pracowników i nawigacja

Ta funkcja jest teraz dostępna w środowiskach piaskownicy i wersji próbnej. Aby włączyć tę funkcję, przejdź do **Administrowanie systemem > Łącza > Ustawienia > Parametry systemowe > Funkcje w wersji zapoznawczej**. Wybierz **Formularz i nawigację rozszerzonego pracownika**. Dzięki temu zmiany są włączane dla wszystkich użytkowników. Opcję tę można wyłączyć w dowolnym momencie.

Aby uzyskać więcej informacji, zajrzyj do [Usprawnione wprowadzanie pracowników i nawigacja](./streamlined-employee-entry.md).

## <a name="coming-soon"></a>Wkrótce

### <a name="platform-update-29"></a>Aktualizacja platformy Update 29

Aby uzyskać więcej informacji dotyczących 29. aktualizacji platformy, zobacz [Podgląd funkcji w aktualizacji platformy 29 Dynamics 365 for Finance and Operations (Październik 2019)](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-29).
