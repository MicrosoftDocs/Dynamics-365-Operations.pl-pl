---
title: Podstawowe informacje o prognozowaniu popytu
description: Prognozowanie popytu jest używane do przewidywania niezależnego popytu z zamówień sprzedaży i zależnego popytu w dowolnym punkcie oddzielenia dla zamówień od odbiorców. Rozszerzone reguły redukcji prognozy popytu są doskonałym rozwiązaniem do masowego dostosowywania.
author: t-benebo
ms.date: 07/07/2020
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: ReqDemPlanCreateForecastDialog
audience: Application User
ms.reviewer: kamaybac
ms.custom:
- "72004"
- intro-internal
ms.assetid: 916707c9-1333-460f-a0fa-4e95f6fda2ad
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e1648808667c8bb9487e7a47b87d8e73cf442d82
ms.sourcegitcommit: d98ecbd9457197ec8f8e281f9c2f24dcce7b8269
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/14/2022
ms.locfileid: "8960200"
---
# <a name="demand-forecasting-overview"></a>Podstawowe informacje o prognozowaniu popytu

[!include [banner](../includes/banner.md)]

Prognozowanie popytu jest używane do przewidywania niezależnego popytu z zamówień sprzedaży i zależnego popytu w dowolnym punkcie oddzielenia dla zamówień od odbiorców. Rozszerzone reguły redukcji prognozy popytu są doskonałym rozwiązaniem do masowego dostosowywania.

Aby wygenerować prognozę bazową, podsumowanie transakcji historycznych jest przekazywane do usługi Microsoft Azure Machine Learning hostowanej na platformie Azure. Ponieważ ta usługa nie jest współużytkowana przez użytkowników, można ją łatwo dostosować do wymagań danej branży. Program Supply Chain Management umożliwia wizualizację prognozy, korygowanie prognozy i wyświetlanie najważniejszych wskaźników trafności prognozy.

> [!NOTE]
> Środowisko Microsoft Azure Machine Learning Studio (klasyczne) jest wymagane do generowania prognozy za pomocą uczenia maszynowego. Od 1 grudnia 2021 roku nie będzie można tworzyć nowych zasobów Machine Learning Studio (klasycznego). Jednak do 31 sierpnia 2024 będzie można nadal korzystać z istniejących zasobów Machine Learning Studio (klasycznego). Aby uzyskać zaktualizowane informacje, zobacz [Azure Machine Learning Studio](/azure/machine-learning/overview-what-is-machine-learning-studio#ml-studio-classic-vs-azure-machine-learning-studio).
> 
> Dynamics 365 Supply Chain Management wersja 10.0.23 i nowsza wersja obsługuje nowe Azure Machine Learning Studio.

## <a name="key-features-of-demand-forecasting"></a>Najważniejsze funkcje prognozowania popytu

Poniżej przedstawiono główne funkcje prognozowania popytu:

- Generowanie bazowej prognozy statystycznej opartej na danych historycznych.
- Korzystanie z dynamicznego zestawu wymiarów prognozy.
- Wizualizacja trendów popytu, interwałów ufności i korekty prognozy.
- Autoryzacja skorygowanej prognozy, której można używać w procesach planowania.
- Usuwanie wartości odstających.
- Tworzenie miary dokładności prognozy.

## <a name="major-themes-in-demand-forecasting"></a>Najważniejsze motywy w prognozowaniu popytu

Trzy najważniejsze motywy w prognozowaniu popytu:

- **Modułowość** — prognozowania popytu jest modułowe i łatwe do skonfigurowania. Funkcję tę można włączać i wyłączać poprzez zmianę klucza konfiguracji w oknie **Handel** &gt; **Prognoza zapasów** &gt; **Prognozowanie popytu**.
- **Ponowne użycie Microsoft Stack** – Machine Learning, obecnie część pakietu analitycznego Microsoft Cortana, umożliwia szybkie i łatwe tworzenie eksperymentów analiz predykcyjnych, takich jak eksperymenty szacowania popytu, przy użyciu języków programowania algorytmów R lub Python oraz prostego w obsłudze interfejsu typu przeciągnij i upuść.
  - Można pobrać eksperymenty prognozowania popytu, zmienić je odpowiednio do wymagań biznesowych, publikować jako usługi sieci web na Azure i używać ich do generowania prognoz popytu. Eksperymenty są dostępne do pobrania w ramach zakupionej subskrypcji programu Supply Chain Management dla planisty produkcji jako użytkownika na poziomie organizacji.
  - Można pobrać dowolne z obecnie dostępnych eksperymentów przewidywania popytu z [Galerii narzędzi analitycznych Cortana](https://gallery.cortanaanalytics.com/). Eksperymenty prognozowania popytu są automatycznie integrowane z programem Supply Chain Management, natomiast klienci i partnerzy muszą ręcznie integrować eksperymenty pobierane z [Galerii narzędzi analitycznych Cortana](https://gallery.cortanaanalytics.com/). Z tego względu eksperymenty z [Galerii narzędzi analitycznych Cortana](https://gallery.cortanaanalytics.com/) nie są tak samo proste w użytkowaniu, jak eksperymenty w programie Finance and Operations. Konieczne jest zmodyfikowanie kodu eksperymentów, aby mogły korzystać z interfejsu API programu Finance and Operations.
  - Można utworzyć własne eksperymenty w programie Microsoft Azure Machine Learning Studio (wersja klasyczna), opublikować je jako usługi na platformie Azure i używać do generowania prognoz popytu.
  - Jeśli nie jest wymagana wysoka wydajność lub nie potrzeba przetwarzać bardzo dużych ilości danych, można korzystać z bezpłatnej wersji oprogramowania do uczenia maszynowego. Zalecamy rozpoczęcie pracy od wersji bezpłatnej, zwłaszcza w fazie testowania i implementacji. Jeśli konieczna jest większa wydajność i dodatkowa pamięć, można korzystać z wersji standardowej oprogramowania do uczenia maszynowego. Ta wersja wymaga subskrypcji usługi Azure i wiąże się z dodatkowymi kosztami. Aby uzyskać szczegółowe informacje o cenach oprogramowania do uczenia maszynowego, zobacz [Ceny studio uczenia maszynowego](https://aka.ms/machine-learning-price-info).
- **Zmniejszenie prognozy w dowolnym punkcie oddzielania** — prognoza popytu dla tej funkcji, która pozwala prognozować zarówno popyt zależny, jak i niezależny w dowolnym punkcie oddzielania.

## <a name="basic-flow-in-demand-forecasting"></a>Podstawowy przepływ w prognozowaniu popytu

Poniższy wykres przedstawia podstawowy przepływ dla prognozowania popytu.

[![diagram wprowadzenia do prognozowania popytu.](./media/demand-forecasting-introduction.png)](./media/demand-forecasting-introduction.png)

Generowanie prognozy popytu rozpoczyna się w Supply Chain Management. Historyczne dane transakcji z bazy danych transakcji w programie Supply Chain Management są zbierane i wpisywane do tabeli przejściowej. Zawartość tej tabeli przejściowej jest później przekazywana do usługi uczenia maszynowego. Do tabeli można podłączać różne źródła danych po ich odpowiednim dostosowaniu. Źródła danych mogą obejmować pliki programu Microsoft Excel, pliki z wartościami rozdzielanymi przecinkami (CSV) oraz danych z Microsoft Dynamics AX 2009 i Microsoft Dynamics AX 2012. W związku z tym można generować prognozy popytu uwzględniające dane historyczne rozproszone w wielu systemach. Jednak dane podstawowe, takie jak nazwy towarów oraz jednostki miary, muszą być takie same w różnych źródłach danych.

W przypadku korzystania z eksperymentów uczenia maszynowego do prognozowania popytu, szukają one najlepszego dopasowania spośród pięciu metod prognozowania i obliczają prognozę bazową. Parametrami dla tych metod prognozowania zarządza się w programie Supply Chain Management.

Prognozy, dane historyczne i wszelkie zmiany, które zostały wprowadzone w prognozach popytu w poprzednich iteracjach, są następnie dostępne w programie Supply Chain Management.

Za pomocą programu Supply Chain Management można wizualizować i modyfikować prognozy bazowe. Ręczne korekty wymagają autoryzacji przed zastosowaniem prognoz do planowania.

## <a name="limitations"></a>Ograniczenia

Prognozowanie popytu to narzędzie, które pomaga odbiorcom w przemyśle produkcyjnym tworzyć procesy prognozowania. Oferuje podstawowe funkcje rozwiązania do prognozowania i jest zaprojektowane w taki sposób, że może być łatwo rozszerzone. Prognozowanie popytu nie musi być najlepszym narzędziem dla odbiorców w takich branżach, jak handel, handel hurtowy, magazynowanie, transport lub inne usługi profesjonalne.

### <a name="demand-forecast-variant-conversion-limitation"></a>Ograniczenie konwersji wariantów prognozy popytu

Jednostka miary (JM) na konwersję wariantu nie jest w pełni obsługiwana podczas generowania prognozy popytu, jeśli jednostka miary magazynu jest inna niż ilość w polu Jednostka miary prognozy popytu.

Generowanie prognozy (**Jednostka miary zapasów > Prognozy popytu jednostki miary**) używa konwersji jednostki miary produktu. Podczas ładowania danych historycznych dla generowania prognozy popytu konwersja jednostek miary na poziomie produktu będzie zawsze używana podczas konwersji z magazynu zapasów na prognozę popytu, nawet jeśli na poziomie wariantu są zdefiniowane konwersje.

W pierwszej części zatwierdzania prognozy (**Prognoza popytu jednostki miary > Jednostka miaryzapasów**) jest używana konwersja jednostki miary produktu. W drugiej części jednostki autoryzowanie autoryzacji (**Jednostka miary zapasów > Jednostka miary sprzedaży**) jest używana konwersja jednostki miary wariantu. Jeśli wygenerowana prognoza popytu jest autoryzowana, konwersja do jednostki miary magazynowej z prognozy popytu na jednostkę miary zostanie wykonana przy użyciu konwersji jednostki miary na poziomie produktu. W tym samym czasie konwersja między jednostkami magazynowymi a jednostką miary sprzedaży uwzględnia konwersje zdefiniowane na poziomie wariantu.

Należy zauważyć, że jednostka miary prognozy popytu nie musi mieć żadnych właściwych znaczenia. Można ją zdefiniować jako „jednostkę prognozy popytu”. Dla każdego produktu można zdefiniować konwersję na 1:1 przy użyciu jednostki miary zapasów.

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Ustawienia prognozowania popytu](demand-forecasting-setup.md)
- [Generowanie bazowej prognozy statystycznej](generate-statistical-baseline-forecast.md)
- [Wprowadzanie ręcznych korekt prognozy bazowej](manual-adjustments-baseline-forecast.md)
- [Autoryzowanie skorygowanej prognozy](authorize-adjusted-forecast.md)
- [Monitorowanie dokładności prognozy](monitor-forecast-accuracy.md)
- [Usuwanie wartości odstających z danych transakcji historycznych podczas obliczania prognozy popytu](remove-historical-outliers-calculating-demand-forecast.md)
- [Wideo: Rozszerzanie funkcji prognozowania popytu](https://www.youtube.com/watch?v=4OIKIXLiNjI&feature=youtu.be)
- [Seminarium internetowe: Prognozowanie popytu z serią Azure Machine Learning](https://aka.ms/DemandForecastingwithAzureMachineLearningSeries)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
