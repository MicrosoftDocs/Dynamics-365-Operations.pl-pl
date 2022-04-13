---
title: Importowanie danych historycznych dla prognoz popytu
description: Aby uzyskać dokładne prognozy popytu, potrzebne są historyczne dane dotyczące popytu na towar lub klucz alokacji produktów. W tym temacie opisano, jak za pomocą jednostek danych importować historyczne dane popytu z dowolnego systemu, w celu uzyskania dłuższej historii danych dotyczących prognoz popytu.
author: t-benebo
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
ms.author: benebotg
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c52d27d6e3aa8a20d6cc1dc81e4ade981c6a8091
ms.sourcegitcommit: ad1afc6893a8dc32d1363395666b0fe1d50e983a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/23/2022
ms.locfileid: "8470409"
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

Zobacz także [Generowanie bazowej prognozy statystycznej](generate-statistical-baseline-forecast.md).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]