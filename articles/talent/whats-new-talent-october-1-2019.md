---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Talent (1 października 2019 r.)
description: W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 10/01/2019
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
ms.search.validFrom: 2019-10-01
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 69c0a805027f215b2a2a42d826ee7a346cfdd511
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/17/2020
ms.locfileid: "4529667"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-october-1-2019"></a>Nowości i zmiany w rozwiązaniu Dynamics 365 Talent (1 października 2019 r.)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Zmiany w Attract

Ta wersja zawiera drobne poprawki błędów dla rozwiązania Dynamics 365 Talent: Attract.

## <a name="changes-in-onboard"></a>Zmiany w Onboard

Ta wersja zawiera drobne poprawki błędów dla rozwiązania Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Zmiany w Core HR

Zmiany opisane w tej części dotyczą kompilacji 8.1.2509. Liczby w nawiasach w niektórych nagłówkach odnoszą się do numerów pomocy w usługach Microsoft Dynamics Lifecycle Services (LCS).

### <a name="streamlined-employee-entry-and-navigation"></a>Usprawnione wprowadzanie pracowników i nawigacja

Ta funkcja jest teraz dostępna we wszystkich środowiskach. Aby włączyć tę funkcję, przejdź do **Administrowanie systemem > Łącza > Ustawienia > Parametry systemowe > Funkcje w wersji zapoznawczej**. Wybierz **Formularz i nawigację rozszerzonego pracownika**. Dzięki temu zmiany są włączane dla wszystkich użytkowników. Opcję tę można wyłączyć w dowolnym momencie.

Aby uzyskać więcej informacji, zajrzyj do [Usprawnione wprowadzanie pracowników i nawigacja](./streamlined-employee-entry.md). Aby zobaczyć film przedstawiający te zmiany, zobacz [Dynamics 365 for Talent przegląd 2. fali publikacji 2019](https://aka.ms/ROGT19RW2ROV).

### <a name="you-can-enable-preview-features-in-sandbox-and-trial-environments"></a>Funkcje podglądu można włączać w środowiskach piaskownicy i wersji próbnej

Podczas zastrzegania nowej instancji talentów można określić, czy typem wystąpienia jest Produkcja, czy Piaskownica - środowisko testowe. Wystąpienia typu Piaskownica umożliwiają wczesne testowanie nowych funkcji. Jeśli chcesz, aby jedno z istniejących wystąpień zostało zaktualizowane do typu wystąpienia Piaskownica, skontaktuj się z pomocą techniczną, aby zainicjować żądanie zmiany.

Aby uzyskać więcej informacji o publikowaniu zmian, zapoznaj się z tematem [Provision Talent](./provisioning-talent.md).

### <a name="compensation-date-defaults-to-a-different-date-than-the-position-assignment-337694"></a>Domyślna data kompensaty jest inna data niż przypisanie stanowiska (337694)

Ta zmiana powoduje, że data rozpoczęcia kompensacji jest domyślnie ustawiana na datę rozpoczęcia przypisania stanowiska.

### <a name="not-able-to-end-compensation-along-with-its-position-assignment-328993"></a>Nie można zakończyć kompensacji wraz z jej przypisaniem stanowiska (328993)

W przypadku tej zmiany można zakończyć kompensację po zakończeniu przypisania stanowiska za pomocą polecenia **Zakończ przypisanie** na stronie **Przypisania pracowników do stanowisk** z włączonymi akcjami dotyczącymi pracowników.

### <a name="bank-account-validation-requires-routing-and-account-numbers-in-all-locations-340403"></a>Sprawdzanie poprawności konta bankowego wymaga numeru rozliczeniowego i numeru konta we wszystkich lokalizacjach (340403)

W przypadku zmian w tym tygodniu dodano nową opcję konfiguracji w celu wyłączenia weryfikacji z wymaganymi danymi **Numer rozliczeniowy** i **Numer konta**. 

### <a name="attachments-are-not-enabled-in-mss-performance-journals-for-performance-feedback-341794"></a>Załączniki nie są włączone w arkuszach wydajności MSS dotyczących informacji o wydajności (341794)

W przypadku wydania w tym tygodniu załączniki są włączone dla elementów informacji zwrotnych na stronie arkusza wydajności.

### <a name="leave-request-details-dont-sync-from-common-data-service-to-talent-369608"></a>Szczegóły żądania nie są sychronizowane z Common Data Service do aplikacji Talent (369608)

Po wprowadzeniu tych zmian szczegóły wniosków urlopowych, które zostały zaktualizowane w Common Data Service będą synchronizowane z powrotem do aplikacji Talent.

### <a name="job-description-doesnt-display-for-the-job-in-the-skill-gap-analysis-page-369398"></a>Opis stanowiska nie jest wyświetlany dla zadania na stronie analizy luk w kwalifikacjach (369398)

W przypadku kompilacji w tym tygodniu opis będzie wyświetlany podczas wybierania zadania na stronie **Analiza luk w kwalifikacjach**.

## <a name="coming-soon"></a>Wkrótce

### <a name="print-performance-reviews"></a>Drukowanie przeglądów wydajności

Pracownicy, menedżerowie i pracownicy działu kadr będą mogli drukować przegląd wydajności pracownika.
