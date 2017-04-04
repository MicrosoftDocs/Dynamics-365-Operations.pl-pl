---
title: "Omówienie prognozowania popytu"
description: "Prognozowanie popytu jest używane do przewidywania niezależnego popytu z zamówień sprzedaży i zależnego popytu w dowolnym punkcie oddzielenia dla zamówień od odbiorców. Żądanie rozszerzone prognozy redukcji zasady przewidują masowe Dostosowywanie idealne rozwiązanie."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ReqDemPlanCreateForecastDialog
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 72004
ms.assetid: 916707c9-1333-460f-a0fa-4e95f6fda2ad
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 9152616b81e7873426f296376b5e57c94439379d
ms.lasthandoff: 03/31/2017


---

# <a name="demand-forecasting-overview"></a>Omówienie prognozowania popytu

Prognozowanie popytu jest używane do przewidywania niezależnego popytu z zamówień sprzedaży i zależnego popytu w dowolnym punkcie oddzielenia dla zamówień od odbiorców. Żądanie rozszerzone prognozy redukcji zasady przewidują masowe Dostosowywanie idealne rozwiązanie.

Aby wygenerować prognozę bazową, podsumowanie transakcji historycznych jest przekazywane do usługi uczenia maszynowego Microsoft Azure hostowanej w Azure. Ponieważ ta usługa nie jest współużytkowana przez użytkowników, można ją łatwo dostosować do wymagań danej branży. 365 Dynamics dla operacji służy do wizualizacji prognozy, Dopasuj prognozy i wyświetlanie kluczowych wskaźników wydajności (KPI) o dokładności prognozy.

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

-   **Modułowość** — prognozowania popytu jest modułowe i łatwe do skonfigurowania. Funkcjonalność i wyłączanie można włączyć, zmieniając klucz konfiguracji o **handlu**&gt;**Prognoza zapasów**&gt;**Prognozowanie popytu**.
-   **Ponowne wykorzystanie stosu programie Microsoft** — Microsoft uruchomił platformy edukacyjnej maszyny w lutym 2015. Uczenie maszynowe, która jest obecnie częścią pakietu Microsoft Cortana Analytics, umożliwia szybkie i łatwe tworzenie eksperymenty analizy predykcyjne, takie jak żądanie oceny doświadczeń, przy użyciu algorytmów R lub Python języków programowania i prosty interfejs przeciągania i upuszczania.
    -   Można pobrać Dynamics 365 dla operacji żądanie prognozowania eksperymentów, zmień je odpowiednio do spełnienia wymagań biznesowych, publikować jako usługi sieci web Azure i użyte do generowania prognoz popytu. Eksperymenty są dostępne do pobrania po zakupie 365 Dynamics operacje subskrypcji dla Planista produkcji jako użytkownika na poziomie przedsiębiorstwa.
    -   Można pobrać dowolne z obecnie dostępnych eksperymentów przewidywania popytu z [Galerii narzędzi analitycznych Cortana](https://gallery.cortanaanalytics.com/). Natomiast 365 Dynamics dla operacji żądanie prognozowania eksperymentów automatycznie są zintegrowane z 365 Dynamics dla operacji, klienci i partnerzy muszą obsługiwać integracji doświadczeń, które są do pobrania z [Cortana Analytics galerii](https://gallery.cortanaanalytics.com/). W związku z tym, eksperymenty z [Cortana Analytics galerii](https://gallery.cortanaanalytics.com/) nie są tak samo proste, do użycia jako Dynamics 365 dla operacji żądanie prognozowania eksperymentów. Należy zmodyfikować kod doświadczeń, tak aby używały Dynamics 365 operacje interfejsu programowania aplikacji (API).
    -   Można utworzyć własne eksperymenty w programie Microsoft Azure Machine Learning Studio, opublikować je jako usługi na Azure i używać do generowania prognoz popytu.
    -   Jeśli nie jest wymagana wysoka wydajność lub nie potrzeba przetwarzać bardzo dużych ilości danych, można korzystać z bezpłatnej wersji oprogramowania do uczenia maszynowego. Zalecamy rozpoczęcie pracy od wersji bezpłatnej, zwłaszcza w fazie testowania i implementacji. Jeśli konieczna jest większa wydajność i dodatkowa pamięć, można korzystać z wersji standardowej oprogramowania do uczenia maszynowego. Ta wersja wymaga subskrypcji usługi Azure i wiąże się z dodatkowymi kosztami. Aby uzyskać szczegółowe informacje o cenach oprogramowania do uczenia maszynowego, zobacz <http://aka.ms/machine-learning-price-info>.
-   **Zmniejszenie w dowolnym punkcie odsprzęgania prognozy** -prognozowania w systemie Dynamics 365 dla operacji kompilacji na tę funkcjonalność, która umożliwia prognozowanie zapotrzebowania zarówno zależnych i niezależnych w dowolnym punkcie odsprzęgania popytu.

## <a name="basic-flow-in-demand-forecasting"></a>Podstawowy przepływ w prognozowaniu popytu
Poniższy wykres przedstawia podstawowy przepływ dla prognozowania popytu. 

[![diagram wprowadzenie prognozowania popytu](./media/demand-forecasting-introduction.png)](./media/demand-forecasting-introduction.png)

Ma być uruchamiany w 365 Dynamics dla operacji generowania prognoz popytu. Historycznych danych transakcyjnych z 365 Dynamics dla operacji transakcyjnych baz danych są zbierane i wypełnia tabeli tymczasowej. W tej tabeli tymczasowej później jest podawany do usługi uczenie maszynowe. Wykonując minimalne dostosowania, można podłączyć różne źródła danych do tabeli tymczasowej. Źródła danych może zawierać pliki programu Microsoft Excel, pliki wartości rozdzielanych przecinkami (CSV) i danych z systemu Microsoft Dynamics AX 2009 i systemu Microsoft Dynamics AX 2012. W związku z tym istnieje możliwość wygenerowania prognoz popytu, które należy wziąć pod uwagę dane historyczne, który rozprzestrzenia się wśród wielu systemów. Jednak dane podstawowe, takie jak nazwy towarów oraz jednostki miary, muszą być takie same w różnych źródłach danych.

Jeśli używasz Dynamics 365 dla prognozowania eksperymentów uczących popytu operacji wyglądają na najlepsze dopasowanie spośród pięciu czas serii prognozowania metod do obliczania podstawowej prognozy. Parametry dla tych metod prognozowania są zarządzane w usłudze Dynamics 365 dla operacji. 

Prognozy, dane historyczne i wszelkie zmiany, które zostały wprowadzone do prognoz popytu w poprzedniej iteracji następnie są dostępne w usłudze Dynamics 365 dla operacji. 

365 Dynamics dla operacji umożliwia wizualizację i modyfikację prognozy według planu bazowego. Ręczne korekty wymagają autoryzacji przed zastosowaniem prognoz do planowania.

## <a name="limitations"></a>Ograniczenia
Prognozowanie popytu w usłudze Dynamics 365 dla operacji jest narzędziem, które pomaga klientom w przemyśle wytwórczym, tworzyć procesy prognozowania. To oferuje podstawowe funkcje prognozowania rozwiązanie popytu i został zaprojektowany tak, aby łatwo mogą zostać rozszerzone. Żądać prognozowania, może nie być najlepiej pasuje dla klientów w gałęziach przemysłu, takich jak handel detaliczny, hurtowych, magazynowania, transportu lub innych profesjonalnych usług.

<a name="see-also"></a>Informacje dodatkowe
--------

[Demand forecasting setup](demand-forecasting-setup.md)

[Generating a statistical baseline forecast](generate-statistical-baseline-forecast.md)

[Making manual adjustments to the baseline forecast](manual-adjustments-baseline-forecast.md)

[Authorizing the adjusted forecast](authorize-adjusted-forecast.md)

[Monitoring forecast accuracy](monitor-forecast-accuracy.md)

[Remove outliers from historical transaction data when calculating a demand forecast](remove-historical-outliers-calculating-demand-forecast.md)


