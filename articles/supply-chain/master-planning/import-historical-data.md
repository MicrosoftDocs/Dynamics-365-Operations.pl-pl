---
title: Importowanie danych historycznych dla prognoz popytu
description: Aby uzyskać dokładne prognozy popytu, potrzebne są historyczne dane dotyczące popytu na towar lub klucz alokacji produktów. W tym temacie opisano, jak za pomocą jednostek danych importować historyczne dane popytu z dowolnego systemu, w celu uzyskania dłuższej historii danych dotyczących prognoz popytu.
author: roxanadiaconu
ms.date: 05/10/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqDemPlanCreateForecastDialog
audience: Application User
ms.reviewer: kamaybac
ms.assetid: 59c0d269-9db0-48e7-b8c7-9a388781a9ca
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9bb3c178a698bdcd46e7c596247360ba9233b398
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5816491"
---
# <a name="import-historical-data-for-demand-forecasts"></a>Importowanie danych historycznych dla prognoz popytu

[!include [banner](../includes/banner.md)]

W celu zagwarantowania dokładności prognoz popytu, musisz mieć tyle historycznych danych popytu, ile możesz uzyskać dla pozycji lub klucza alokacji produktów. Jeśli historyczne dane popytu nie zostały jeszcze zaimportowane, użyj jednostki danych **Historyczny popyt zewnętrzny** (ReqDemPlanHistoricalExternalDemandEntity) w Dynamics 365 Supply Chain Management do ich zaimportowania.

W obszarze roboczym **Zarządzanie danymi** można wyświetlić przegląd wszystkich pól w jednostce.

1. Otwórz obszar roboczy **Zarządzanie danymi**.
2. Wybierz kafelek **Jednostki danych**.
3. Wyszukaj na liście jednostek pozycję **Historyczny popyt zewnętrzny**.
4. Wybierz **Pola docelowe**. Następujące pola jednostki są wymagane: oddziału (**DeliveringSiteId**), daty (**DemandDate**), ilości (**DemandQuantity**) i numeru pozycji (**ItemNumber**) lub klucza alokacji produktów (**ProductAllocationKeyId**).

Aby użyć jednostki danych, musisz mieć plik programu Microsoft Excel lub plik wartości rozdzielanych przecinkami (CSV) zawierający dane historyczne popytu. Poniższy przykład pokazuje, jak przeprowadzić import danych z pliku CSV.

Aby uzyskać więcej informacji dotyczących sposobu importowania danych, w tym sposobu oczyszczania danych po imporcie, zobacz temat [Omówienie zadań importowania i eksportowania danych](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md) oraz tematy pokrewne.

## <a name="example"></a>Przykład

Można użyć następującego pliku jako przykładowego. Pobierz [HistoricalDemandData](https://docs.microsoft.com/dynamics/s-e/). Ten plik zawiera historyczne dane dotyczące popytu dla pozycji D0001. Zawiera on tylko następujące wymagane pola: oddział, ilość i data zapotrzebowania.

1. Wybierz firmę do której zostaną zaimportowane historyczne dane popytu.
2. Otwórz obszar roboczy **Zarządzanie danymi**.
3. Wybierz kafelek **Import**.
4. Wprowadź nazwę dla importowania projektu, taką jak **Importowanie historycznego popytu dla pozycji D0001**.
5. W polu **Format danych źródłowych** wybierz format pliku, który jest importowany. Aby zaimportować plik HistoricalDemandData w tym przykładzie, zaznacz **CSV**.
6. W polu **Nazwa jednostki** wybierz **Historyczny popyt zewnętrzny**.
7. Zapisz plik na komputerze, a następnie przekaż go.
8. Wybierz opcję **Importuj**.
9. Strona **Podsumowanie wykonania** zostanie automatycznie otwarta. Sprawdź importowane dane na stronie.

Po zaimportowaniu historycznych danych popytu można generować prognozy popytu.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Generowanie bazowej prognozy statystycznej](generate-statistical-baseline-forecast.md)  
[Omówienie zadań importowania i eksportowania danych](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]