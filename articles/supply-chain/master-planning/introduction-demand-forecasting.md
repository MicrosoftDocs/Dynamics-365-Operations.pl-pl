---
title: Podstawowe informacje o prognozowaniu popytu
description: Prognozowanie popytu jest używane do przewidywania niezależnego popytu z zamówień sprzedaży i zależnego popytu w dowolnym punkcie oddzielenia dla zamówień od odbiorców. Rozszerzone reguły redukcji prognozy popytu są doskonałym rozwiązaniem do masowego dostosowywania.
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqDemPlanCreateForecastDialog
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 72004
ms.assetid: 916707c9-1333-460f-a0fa-4e95f6fda2ad
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a645ee6f7e6085abc6e872d490b078f512c15aa1
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1552376"
---
# <a name="demand-forecasting-overview"></a>Podstawowe informacje o prognozowaniu popytu

[!include [banner](../includes/banner.md)]

Prognozowanie popytu jest używane do przewidywania niezależnego popytu z zamówień sprzedaży i zależnego popytu w dowolnym punkcie oddzielenia dla zamówień od odbiorców. Rozszerzone reguły redukcji prognozy popytu są doskonałym rozwiązaniem do masowego dostosowywania.

Aby wygenerować prognozę bazową, podsumowanie transakcji historycznych jest przekazywane do usługi uczenia maszynowego Microsoft Azure hostowanej w Azure. Ponieważ ta usługa nie jest współużytkowana przez użytkowników, można ją łatwo dostosować do wymagań danej branży. Program Finance and Operations umożliwia wizualizację prognozy, korygowanie prognozy i wyświetlanie najważniejszych wskaźników trafności prognozy.

## <a name="key-features-of-demand-forecasting"></a>Najważniejsze funkcje prognozowania popytu
Poniżej przedstawiono główne funkcje prognozowania popytu:

-   Generowanie bazowej prognozy statystycznej opartej na danych historycznych.
-   Korzystanie z dynamicznego zestawu wymiarów prognozy.
-   Wizualizacja trendów popytu, interwałów ufności i korekty prognozy.
-   Autoryzacja skorygowanej prognozy, której można używać w procesach planowania.
-   Usuwanie wartości odstających.
-   Tworzenie miary dokładności prognozy.

## <a name="major-themes-in-demand-forecasting"></a>Najważniejsze motywy w prognozowaniu popytu
Trzy najważniejsze motywy w prognozowaniu popytu:

-   **Modułowość** — prognozowania popytu jest modułowe i łatwe do skonfigurowania. Funkcję tę można włączać i wyłączać poprzez zmianę klucza konfiguracji w oknie **Handel** &gt; **Prognoza zapasów** &gt; **Prognozowanie popytu**.
-   **Ponowne użycie stosu Microsoft** — Firma Microsoft uruchomiła platformę do uczenia maszynowego w lutym 2015 r. Uczenie maszynowe, obecnie część pakietu analitycznego Microsoft Cortana, umożliwia szybkie i łatwe tworzenie eksperymentów analiz predykcyjnych, takich jak eksperymenty szacowania popytu, przy użyciu języków programowania algorytmów R lub Python oraz prostego w obsłudze interfejsu typu przeciągnij i upuść.
    -   Można pobrać eksperymenty prognozowania popytu programu Finance and Operations, zmienić je odpowiednio do wymagań biznesowych, publikować jako usługi sieci web na Azure i używać ich do generowania prognoz popytu. Eksperymenty są dostępne do pobrania w ramach subskrypcji programu Finance and Operations do planowania produkcji przez użytkowników na poziomie organizacji.
    -   Można pobrać dowolne z obecnie dostępnych eksperymentów przewidywania popytu z [Galerii narzędzi analitycznych Cortana](https://gallery.cortanaanalytics.com/). Eksperymenty prognozowania popytu programu Finance and Operations są automatycznie integrowane z programem, natomiast klienci i partnerzy muszą ręcznie integrować eksperymenty pobierane z [Galerii narzędzi analitycznych Cortana](https://gallery.cortanaanalytics.com/). Z tego względu eksperymenty z [Galerii narzędzi analitycznych Cortana](https://gallery.cortanaanalytics.com/) nie są tak samo proste w użytkowaniu, jak eksperymenty w programie Finance and Operations. Konieczne jest zmodyfikowanie kodu eksperymentów, aby mogły korzystać z interfejsu API programu Finance and Operations.
    -   Można utworzyć własne eksperymenty w programie Microsoft Azure Machine Learning Studio, opublikować je jako usługi na Azure i używać do generowania prognoz popytu.
    -   Jeśli nie jest wymagana wysoka wydajność lub nie potrzeba przetwarzać bardzo dużych ilości danych, można korzystać z bezpłatnej wersji oprogramowania do uczenia maszynowego. Zalecamy rozpoczęcie pracy od wersji bezpłatnej, zwłaszcza w fazie testowania i implementacji. Jeśli konieczna jest większa wydajność i dodatkowa pamięć, można korzystać z wersji standardowej oprogramowania do uczenia maszynowego. Ta wersja wymaga subskrypcji usługi Azure i wiąże się z dodatkowymi kosztami. Aby uzyskać szczegółowe informacje o cenach oprogramowania do uczenia maszynowego, zobacz <http://aka.ms/machine-learning-price-info>.
-   **Zmniejszenie prognozy w dowolnym punkcie oddzielania** — Prognoza popytu w programie Finance and Operations dla tej funkcji, która pozwala prognozować zarówno zależny, jak i niezależny popyt w dowolnym punkcie oddzielania.

## <a name="basic-flow-in-demand-forecasting"></a>Podstawowy przepływ w prognozowaniu popytu
Poniższy wykres przedstawia podstawowy przepływ dla prognozowania popytu. 

[![diagram wprowadzenia do prognozowania popytu](./media/demand-forecasting-introduction.png)](./media/demand-forecasting-introduction.png)

Generowanie prognozy popytu zaczyna się w programie Finance and Operations. Historyczne dane transakcji z bazy danych transakcji w programie Finance and Operations są zbierane i wpisywane do tabeli przejściowej. Zawartość tej tabeli przejściowej jest później przekazywana do usługi uczenia maszynowego. Do tabeli można podłączać różne źródła danych po ich odpowiednim dostosowaniu. Źródła danych mogą obejmować pliki programu Microsoft Excel, pliki z wartościami rozdzielanymi przecinkami (CSV) oraz danych z Microsoft Dynamics AX 2009 i Microsoft Dynamics AX 2012. W związku z tym można generować prognozy popytu uwzględniające dane historyczne rozproszone w wielu systemach. Jednak dane podstawowe, takie jak nazwy towarów oraz jednostki miary, muszą być takie same w różnych źródłach danych.

W przypadku korzystania z eksperymentów uczenia maszynowego do prognozowania popytu w programie Finance and Operations szukają one najlepszego dopasowania spośród pięciu metod prognozowania i obliczają prognozę bazową. Parametrami dla tych metod prognozowania zarządza się w programie Finance and Operations. 

Prognozy, dane historyczne i wszelkie zmiany, które zostały wprowadzone w prognozach popytu w poprzednich iteracjach, są następnie dostępne w programie Finance and Operations. 

Za pomocą programu Finance and Operations można wizualizować i modyfikować prognozy bazowe. Ręczne korekty wymagają autoryzacji przed zastosowaniem prognoz do planowania.

## <a name="limitations"></a>Ograniczenia
Prognozowanie popytu w programie Finance and Operations to narzędzie, które pomaga odbiorcom w przemyśle wytwórczym tworzyć procesy prognozowania. Oferuje podstawowe funkcje rozwiązania do prognozowania i jest zaprojektowane w taki sposób, że może być łatwo rozszerzone. Prognozowanie popytu nie musi być najlepszym narzędziem dla odbiorców w takich branżach, jak handel detaliczny, handel hurtowy, magazynowanie, transport lub inne usługi profesjonalne.

<a name="additional-resources"></a>Dodatkowe zasoby
--------

[Ustawienia prognozowania popytu](demand-forecasting-setup.md)

[Generowanie bazowej prognozy statystycznej](generate-statistical-baseline-forecast.md)

[Wprowadzanie ręcznych korekt prognozy bazowej](manual-adjustments-baseline-forecast.md)

[Autoryzowanie skorygowanej prognozy](authorize-adjusted-forecast.md)

[Monitorowanie dokładności prognozy](monitor-forecast-accuracy.md)

[Usuwanie wartości odstających z danych transakcji historycznych podczas obliczania prognozy popytu](remove-historical-outliers-calculating-demand-forecast.md)

[Rozszerzanie funkcji prognozowania popytu](https://www.youtube.com/watch?v=4OIKIXLiNjI&feature=youtu.be)



