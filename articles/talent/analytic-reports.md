---
title: Używanie raportów analitycznych w programie Microsoft Dynamics 365 for Talent - Attract
description: W tym temacie opisano raporty analityczne dotyczące szczegółowego procesu zatrudniania w programie Microsoft Dynamics 365 for Talent - Attract
author: fewatson
manager: AnnBe
ms.date: 04/30/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: fewatson
ms.search.validFrom: 2019-04-30
ms.dyn365.ops.version: Talent April 2019 update
ms.openlocfilehash: f69c45e885d789d05a081064f30ccd6ce6bfec52
ms.sourcegitcommit: 45f8cea6ac75bd2f4187380546a201c056072c59
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/12/2019
ms.locfileid: "1742896"
---
# <a name="use-analytic-reports"></a>Korzystanie z raportów analitycznych

Raporty analityczne w Attract oferują gotowe rozwiązanie (OOTB) do analizy danych w procesie zatrudnienia. Dostępne są następujące funkcje:

- **Analizy funkcji:** kliknij kartę **Analizy** w obszarze zadania, aby zobaczyć dane dotyczące kandydata.
- **Centrum analiz:** kliknij pozycję **analizy** w lewym okienku nawigacyjnym, aby uzyskać zagregowane dane w ramach zadań.
- **Zabezpieczenia na poziomie użytkownika** — dostęp do raportów jest kontrolowany przez Attract [rola](security-attract.md) i rolę uczestnika procesu rekrutacji.
- **Filtrowanie krzyżowe:** kliknij opcję elementy wizualne w raporcie, aby wyświetlić inne dane filtrowane według wybranych danych.

>[!NOTE] 
>- Ta funkcja jest obecnie w [wersjach zapoznawczych](access-preview-feature.md). Aby go wypróbować, należy posiadać [**Dodatek kompleksowej obsługi rekrutacji**](attract-comprehensive-hiring.md).
>- Wszystkie publiczne raporty poglądów są wyświetlane w języku angielskim.
>- Raporty są odświeżane co 3 godziny. Godzina ostatniego odświeżania (w lokalnej strefie czasowej) znajduje się u góry raportu. Czasy odświeżania są podane w przybliżeniu i zależą od ilości danych oraz obciążenia pracą zasobów w Twoim regionie.

## <a name="job-analytics"></a>Analizy funkcji

Raporty Analiza funkcji pokazują migawkę procesu rekrutacji na funkcję.  Kluczowe wskaźniki obejmują:

- Aktywni kandydaci według etapów
- Źródła kandydatów
- Typ kandydata (wewnętrzny lub zewnętrzny)

## <a name="analytics-hub"></a>Centrum analiz

Raporty Centrum analiz agregują informacje o funkcjach w celu pokazania trendów w procesie rekrutacji. Attract oferuje dwa raporty OOTB: Podsumowanie procesu i Analiza lejkowa.

### <a name="pipeline-summary"></a>Podsumowanie procesu

Raport Podsumowanie procesu umożliwia agregowanie danych dla otwartych zadań. Kluczowe wskaźniki obejmują:

- Kandydaci na wszystkie funkcje wg etapów
- Źródła kandydatów
- Otwarte funkcje wg poziomu stażu pracy

### <a name="funnel-analysis"></a>Analiza lejka

Raport analizy lejka agreguje dane dla zadań, które zostały zamknięte jako wypełnione. Kluczowe wskaźniki obejmują:

- Czas do zatrudnienia
- Metryka konwersji (po najechaniu kursorem)
- Współczynnik akceptacji ofert

Uwaga: w celu uzyskania najdokładniejszego czasu na potrzeby raportów zatrudniania zaleca się korzystanie [Zarządzanie ofertami](offer-setup.md), dostępnej jako część dodatku kompleksowej obsługi rekrutacji.

>[!TIP] 
>Aby uzyskać dodatkowe informacje, spróbuj umieścić kursor nad wizualnymi informacjami. Na przykład umieszczenie wskaźnika myszy na **aktywnych kandydatach** powoduje wyświetlenie średniej liczby dni na etapie. Analiza tych informacji może zapewnić informacje niezbędne do skrócenia czasu zatrudniania i umożliwienia rekruterom skoncentrowania się na sposobach skrócenia czasu spędzanego na każdym etapie.

## <a name="user-specific-security"></a>Zabezpieczenia na poziomie użytkownika

Raporty Attract są dostępne dla ról Administrator, Przeczytaj wszystko, Rekruter i Menedżer zatrudnienia [role ](security-attract.md). Nieprzypisani użytkownicy nie mają dostępu do stron raportów analitycznych Analiza funkcji i Centrum analiz.

Raporty Analiza funkcji pokazują dane wybranej funkcji. Raporty centrum analiz służą do agregowania danych dla wszystkich zadań, które użytkownik może wyświetlić. Użytkownicy, którzy mogą wyświetlać moje zadania i wszystkie zadania na stronie zadania, mają te same widoki w Centrum analiz.

## <a name="cross-filter"></a>Filtrowanie krzyżowe

Jedną z doskonałych funkcji tego Power BI jest sposób, w jaki są wzajemnie połączone wszystkie elementy wizualne na stronie raportu. Jeśli wybierzesz punkt danych w jednym z elementów wizualnych, wszystkie pozostałe elementy wizualne na stronie zawierają tę zmianę danych, zależnie od wybranej opcji. Aby dowiedzieć się więcej i zobaczyć przykład, zajrzyj do [Jak elementy wizualne filtrują się krzyżowo nawzajem w raporcie Power BI ](https://docs.microsoft.com/power-bi/consumer/end-user-interactions).

## <a name="export-to-excel"></a>Eksportuj do programu Excel

Aby wyświetlić dane raportu w programie Excel, można kliknąć menu Opcje (trzy kropki) w elemencie wizualnym i wybrać polecenie **Eksportuj dane źródłowe**. Eksportowane dane są eksportowane jako przefiltrowane, zgodnie z uprawnieniami użytkownika w Attract. Aby uzyskać więcej informacji, zajrzyj do [Eksport danych z wizualizacji](https://docs.microsoft.com/power-bi/visuals/power-bi-visualization-export-data).
