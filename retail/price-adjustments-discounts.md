---
title: Korekty ceny i rabaty
description: "Ten artykuł zawiera informacje dotyczące korekt ceny i rabaty w sprzedaży detalicznej i handlu w usłudze Microsoft Dynamics 365 dla operacji."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 15891
ms.assetid: bab5adf3-ddf0-4c22-a2eb-b4d25b88de99
ms.search.region: global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 01f249cbdabc6febf23dcd7103d4587cecdaad08
ms.lasthandoff: 03/31/2017


---

# <a name="price-adjustments-and-discounts"></a>Korekty ceny i rabaty

Ten artykuł zawiera informacje dotyczące korekt ceny i rabaty w sprzedaży detalicznej i handlu w usłudze Microsoft Dynamics 365 dla operacji.

W usłudze Dynamics 365 dla operacji - handel detaliczny, można wprowadzać korekty cen produktów, a może również skonfigurować rabaty, które są stosowane do wiersza towaru lub transakcję w punkcie sprzedaży (POS) w wywołanie Centrum zamówienia sprzedaży lub zamówienia online. Do grup cen mogą być podłączone zarówno korekty ceny i rabaty. Zarówno w przypadku korekty ceny, jak i rabatów, można określić pojedynczy datę rozpoczęcia i datę zakończenia lub okres cykliczny, kod rabatu i kilka dodatkowych atrybutów. Korekty ceny i rabaty mogą dotyczyć produktów, wariantów lub kategorii. W przypadku zastosowania więcej niż jednego rabatu do produktu odbiorca może otrzymać jeden rabat lub rabat połączony. Dynamics 365 dla operacji automatycznie zastosuje rabat lub kombinacji rabatów, który daje najlepszą cenę do odbiorcy. Podczas ustawiania korekty ceny lub rabatu należy sprawdzić, czy grupy cen są przypisane do właściwych kanałów, katalogów, przynależności lub programów lojalnościowych, do których ma mieć zastosowanie rabat. Ponadto jeśli chcesz automatycznie wygenerować identyfikator rabatu, możesz ustawić sekwencje numerów na stronie **Parametry handlu detalicznego** zanim zdefiniujesz nowy rabat lub korektę ceny lub rabat. **Uwaga:** Korekty ceny lub rabaty można usunąć. Jednak informacje statystyczne zostaną utracone.

### <a name="types-of-discounts"></a>Typy rabatów

Istnieją cztery typy rabatów sieci sprzedaży:

-   **Prosty rabat** — pojedynczy procent lub kwota.
-   **Rabat ilościowy** — stosowany przy zakupie co najmniej dwóch produktów.
-   **Rabat łączony** — stosowany przy zakupie określonej kombinacji produktów.
-   **Rabat progowy** — stosowany przy sumie transakcji powyżej określonej kwoty.

Z grupami cen mogą być skojarzone zarówno korekty ceny i rabaty. Grupy cen mogą być następnie skojarzone z kanałami, katalogami, przynależnościami i programami lojalnościowymi.


