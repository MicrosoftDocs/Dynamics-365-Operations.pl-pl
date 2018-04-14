---
title: Importowanie danych historycznych dla prognoz popytu
description: "Aby uzyskać dokładne prognozy popytu, potrzebne są historyczne dane dotyczące popytu na towar lub klucz alokacji produktów. W tym temacie opisano, jak za pomocą jednostek danych importować historyczne dane popytu z dowolnego systemu, w celu uzyskania dłuższej historii danych dotyczących prognoz popytu."
author: roxanadiaconu
manager: AnnBe
ms.date: 05/10/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqDemPlanCreateForecastDialog
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.assetid: 59c0d269-9db0-48e7-b8c7-9a388781a9ca
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 02daa312d74311432c0c468e3e691637dcf94157
ms.contentlocale: pl-pl
ms.lasthandoff: 11/03/2017

---

# <a name="import-historical-data-for-demand-forecasts"></a>Importowanie danych historycznych dla prognoz popytu

[!INCLUDE [banner](../includes/banner.md)]

W celu zagwarantowania dokładności prognoz popytu, musisz mieć tyle historycznych danych popytu, ile możesz uzyskać dla pozycji lub klucza alokacji produktów. Jeśli historyczne dane popytu nie zostały jeszcze zaimportowane, użyj jednostki danych **Historyczny popyt zewnętrzny** (ReqDemPlanHistoricalExternalDemandEntity) w Microsoft Dynamics 365 for Finance and Operations do ich zaimportowania.

W obszarze roboczym **Zarządzanie danymi** można wyświetlić przegląd wszystkich pól w jednostce.

1. Otwórz obszar roboczy **Zarządzanie danymi**.
2. Kliknij kafelek **Jednostki danych**.
3. Wyszukaj na liście jednostek pozycję **Historyczny popyt zewnętrzny**.
4. Kliknij **Pola docelowe**. Następujące pola jednostki są wymagane: oddziału (**DeliveringSiteId**), daty (**DemandDate**), ilości (**DemandQuantity**) i numeru pozycji (**ItemNumber**) lub klucza alokacji produktów (**ProductAllocationKeyId**).

Aby użyć jednostki danych, musisz mieć plik programu Microsoft Excel lub plik wartości rozdzielanych przecinkami (CSV) zawierający dane historyczne popytu. Poniższy przykład pokazuje, jak przeprowadzić import danych z pliku CSV.

## <a name="example"></a>Przykład

Można użyć następującego pliku jako przykładowego. Pobierz [HistoricalDemandData](https://mbs.microsoft.com/customersource/northamerica/AX/learning/documentation/how-to-articles/365OperationsDemandForecast). Ten plik zawiera historyczne dane dotyczące popytu dla pozycji D0001. Zawiera on tylko następujące wymagane pola: oddział, ilość i data zapotrzebowania.

1. Wybierz firmę do której zostaną zaimportowane historyczne dane popytu.
2. Otwórz obszar roboczy **Zarządzanie danymi**.
3. Kliknij kafelek **Importuj**.
4. Wprowadź nazwę dla importowania projektu, taką jak **Importowanie historycznego popytu dla pozycji D0001**.
5. W polu **Format danych źródłowych** wybierz format pliku, który jest importowany. Aby zaimportować plik HistoricalDemandData w tym przykładzie, zaznacz **CSV**.
6. W polu **Nazwa jednostki** wybierz **Historyczny popyt zewnętrzny**.
7. Zapisz plik na komputerze, a następnie przekaż go.
8. Kliknij **Importuj**.
9. Strona **Podsumowanie wykonania** zostanie automatycznie otwarta. Sprawdź importowane dane na stronie.

Po zaimportowaniu historycznych danych popytu można generować prognozy popytu.

## <a name="see-also"></a>Informacje dodatkowe

[Generowanie bazowej prognozy statystycznej](generate-statistical-baseline-forecast.md)

