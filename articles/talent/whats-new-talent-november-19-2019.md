---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Talent (19 listopada 2019 r.)
description: W tym artykule opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 11/19/2019
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
ms.search.validFrom: 2019-11-19
ms.dyn365.ops.version: Talent
ms.openlocfilehash: aa984a01e9da30e6da07516fa2986833366a882b
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/17/2020
ms.locfileid: "4527151"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-november-19-2019"></a>Nowości i zmiany w rozwiązaniu Dynamics 365 Talent (19 listopada 2019 r.)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

W tym artykule opisano nowe oraz zmienione funkcje dostępne w Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Zmiany w Attract

Ta wersja zawiera drobne poprawki błędów dla rozwiązania Dynamics 365 Talent: Attract.

## <a name="changes-in-onboard"></a>Zmiany w Onboard

Ta wersja zawiera drobne poprawki błędów dla rozwiązania Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Zmiany w Core HR

Zmiany opisane w tej części dotyczą kompilacji 8.1.2621. Liczby w nawiasach w niektórych nagłówkach odnoszą się do numerów pomocy w usługach Microsoft Dynamics Lifecycle Services (LCS).

### <a name="platform-update-31-for-finance-and-operations-apps"></a>Aktualizacja 31 platformy dla aplikacji Finance and Operations

Aby uzyskać więcej informacji, zobacz temat [Funkcje w wersji zapoznawczej w aktualizacji platformy 31 dla Finance and Operations (Styczeń 2020)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-update-31).

### <a name="feature-management-workspace-383856"></a>Obszar roboczy zarządzanie funkcjami (383856)

Obszar roboczy **zarządzanie funkcjami** zawiera listę funkcji dostarczanych w każdym wydaniu. Domyślnie nowe funkcje są wyłączone. Można użyć obszaru roboczego, aby włączyć je i wyświetlić dokumentację dla nich. Aby uzyskać więcej informacji o zarządzaniu funkcjami funkcji, zapoznaj się z [Zarządzanie funkcjami — omówienie](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview).

Wszystkie nowe funkcje pozostają w podglądzie przez co najmniej 30 dni, a zazwyczaj 30-60 dni. Najważniejsze funkcje są zazwyczaj dostępne w październiku i kwietniu każdego roku po okresie podglądu. Po wyświetleniu nowych możliwości w obszarze roboczym **zarządzanie funkcjami** można je włączyć. Niektóre funkcje mogą być domyślnie włączone.
 
Czasami funkcja jest domyślnie włączona i nie można jej wyłączyć (na przykład w obszarze roboczym **zarządzanie funkcjami**).
 
Gdy funkcja jest ogólnie dostępna, może być włączana lub wyłączana w środowiskach produkcyjnych. Przestrzeń robocza **Zarządzanie funkcjami** wskazuje, kiedy funkcja podglądu stanie się obowiązkowa. Ta data zazwyczaj jest równa 1 października lub 1 kwietnia w celu dostosowania ich do półrocznych planów zwolnień. Nie można wyłączać obowiązkowych funkcji. Dopóki ta funkcja nie stanie się obowiązkowa, można ją włączać i wyłączać we wszystkich środowiskach.

### <a name="message-appears-when-canceled-action-exists-for-a-position-382887"></a>Komunikat pojawia się, gdy dla danego stanowiska istnieje akcja anulowana (382887)

Następujący komunikat przestaje się pojawiać po wybraniu konkretnego stanowiska, a akcja anulowana jest dostępna dla stanowiska: **w toku jest nieukończona akcja dotycząca stanowiska xxxxxx**.

### <a name="in-learning-analytics-the-course-type-and-status-display-incorrect-data-381151"></a>W analizie nauki typ i stan kursu wyświetlają niepoprawne dane (381151)

Wydanie w tym tygodniu Zaktualizowano analizę nauki w celu poprawnego wyświetlania **typu** i **stanu** kursu.

### <a name="personnel-number-should-display-in-the-new-worker-form-banner-383832"></a>Numer pracownika powinien być wyświetlany w nowym formularzu pracownik-transparent (383832)

W formularzu **nowy pracownik** **numer pracownika** jest wyświetlany na transparencie w celu szybkiego odwoływania się do niego

### <a name="position-start-date-determines-the-job-record-to-use-when-retrieving-a-compensation-level-during-hire-350361"></a>Data rozpoczęcia stanowiska określa rekord zadania, który ma być używany podczas pobierania poziomu wynagrodzeń podczas zatrudnienia (350361)

W tej wersji **Data początkowa wynagrodzenia** określa poziom przypisany do nowego zadania.

### <a name="custom-pick-list-fields-in-the-position-table-arent-synchronized-to-common-data-service-387503"></a>Pola listy pobrania niestandardowego w tabeli stanowisk nie są zsynchronizowane do Common Data Service (387503)

W tym wydaniu pozycje listy wyboru są teraz synchronizowane z Common Data Service.

### <a name="worker-address-entity-doesnt-synchronize-with-common-data-service-while-importing-new-data-349673"></a>Jednostka adresu pracownika nie jest synchronizowana z Common Data Service wraz z importem nowych danych (349673)

W chwili obecnej w tym tygodniu dane adresowe są synchronizowane z Common Data Service podczas importowania nowych danych.

## <a name="in-preview"></a>Wersja próbna

### <a name="print-performance-reviews"></a>Drukowanie przeglądów wydajności

Zapoznaj się z [Drukowanie przeglądów wydajności](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/print-performance-reviews) w Dynamics 365: plan 2. fali publikacji 2019.
