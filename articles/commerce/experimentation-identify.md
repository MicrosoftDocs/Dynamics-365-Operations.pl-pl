---
title: Określanie hipotezy i ustalanie metryki eksperymentu
description: W tym artykule opisano sposób identyfikowania hipotez i metryk sukcesu dla eksperymentu, który zostanie przeprowadzony na stronie internetowej środowiska handlu elektronicznego w systemie Dynamics 365 Commerce.
author: sushma-rao
ms.date: 10/21/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 0b6bdf160522fc93e841ec2f8a4542ff80d8f67f
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8852793"
---
# <a name="identify-a-hypothesis-and-determine-success-metrics-for-an-experiment"></a>Określanie hipotezy i ustalanie metryki sukcesu eksperymentu
Pierwsza faza cyklu życia eksperymentowania obejmuje określenie hipotezy dotyczącej eksperymentu i określenie metryk, które będą śledzone w celu oceny sukcesu. Na poniższym diagramie przedstawiono wszystkie kroki związane z [konfigurowaniem i przeprowadzaniem eksperymentu](experimentation-overview.md) na stronie internetowej środowiska handlu elektronicznego w systemie Dynamics 365 Commerce. Dodatkowe kroki są zawarte w odrębnych artykułach. 

[ ![Proces użytkownika eksperymentu — identyfikacja.](./media/experimentation_identify.svg) ](./media/experimentation_identify.svg#lightbox)

Hipoteza jest deklaracją, w której przewidywany jest wynik eksperymentu. Wiele czynników umożliwia zdefiniowanie hipotezy, na przykład badanie zachowań użytkownika i zebranych danych z witryn sieci Web. W przypadku hipotezy należy zdefiniować założenie lub teorię, które mają być zweryfikowane przez doświadczenie. Przykładem hipotezy dotyczącej eksperymentu może być „ *zdjęcie białej koszulki na stronie głównej w lecie spowoduje więcej kliknięć w niż zdjęcie granatowa swetra, ponieważ ludzie chcą latem nosić lekkie ubrania w jasnych kolorach*”. W takim przypadku użytkownik utworzy odmiany, które zawierają białe koszulkę i granatowy sweter i opublikuje je jednocześnie.

Aby sprawdzić hipotezę, sukces lub niepowodzenie eksperymentu powinno być bezpośrednio powiązane z akcjami użytkownika; na przykład, czy użytkownik serwisu witryny internetowej kliknie łącze lub przycisk. Te akcje muszą odpowiadać zdarzeniom, które będą raportowane usłudze firmy zewnętrznej do śledzenia doświadczeń. W miarę upływu czasu procent użytkowników, którzy podejmą akcję, zostanie podliczony jako metryka, która może być używana do generowania raportów i przeprowadzania analiz. Aby przejrzeć wszystkie dostępne zdarzenia i atrybuty, zobacz [Zdarzenia komponentów Commerce do diagnostyki i rozwiązywania problemów](dev-itpro/retail-component-events-diagnostics-troubleshooting.md).

## <a name="previous-step"></a>Poprzedni krok
[Eksperymentowanie w programie Dynamics 365 Commerce](experimentation-overview.md)


## <a name="next-step"></a>Następne kroki
[Konfigurowanie eksperymentu](experimentation-setup.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]