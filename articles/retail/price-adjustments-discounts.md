---
title: Korekty ceny i rabaty
description: "Ten artykuł zawiera informacje o korektach ceny i rabatach w programie Microsoft Dynamics 365 for Retail."
author: scott-tucker
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 15891
ms.assetid: bab5adf3-ddf0-4c22-a2eb-b4d25b88de99
ms.search.region: global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: c96f7afdb095fd45b5dd88c7760a24226518f61c
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---

# <a name="price-adjustments-and-discounts"></a>Korekty ceny i rabaty

[!include[banner](includes/banner.md)]


Ten artykuł zawiera informacje o korektach ceny i rabatach w programie Microsoft Dynamics 365 for Retail.

W module Dynamics 365 for Retail użytkownik może dokonywać korygowania cen na produkty, a także konfigurowania rabatów, które są stosowane do wiersza towaru lub transakcji w punkcie sprzedaży, w zamówieniu sprzedaży biura obsługi lub w zamówieniu online. Do grup cen mogą być podłączone zarówno korekty ceny i rabaty. Zarówno w przypadku korekty ceny, jak i rabatów, można określić pojedynczy datę rozpoczęcia i datę zakończenia lub okres cykliczny, kod rabatu i kilka dodatkowych atrybutów. Korekty ceny i rabaty mogą dotyczyć produktów, wariantów lub kategorii. W przypadku zastosowania więcej niż jednego rabatu do produktu odbiorca może otrzymać jeden rabat lub rabat połączony. Program Dynamics 365 for Retail automatycznie zastosuje rabat lub kombinację rabatów oferującą odbiorcy najlepszą cenę. Podczas ustawiania korekty ceny lub rabatu należy sprawdzić, czy grupy cen są przypisane do właściwych kanałów, katalogów, przynależności lub programów lojalnościowych, do których ma mieć zastosowanie rabat. Ponadto jeśli chcesz automatycznie wygenerować identyfikator rabatu, możesz ustawić sekwencje numerów na stronie **Parametry handlu detalicznego** zanim zdefiniujesz nowy rabat lub korektę ceny lub rabat. **Uwaga:** Korekty ceny lub rabaty można usunąć. Jednak informacje statystyczne zostaną utracone.

### <a name="types-of-discounts"></a>Typy rabatów

Istnieją cztery typy rabatów sieci sprzedaży:

-   **Prosty rabat** — pojedynczy procent lub kwota.
-   **Rabat ilościowy** — stosowany przy zakupie co najmniej dwóch produktów.
-   **Rabat łączony** — stosowany przy zakupie określonej kombinacji produktów.
-   **Rabat progowy** — stosowany przy sumie transakcji powyżej określonej kwoty.

Z grupami cen mogą być skojarzone zarówno korekty ceny i rabaty. Grupy cen mogą być następnie skojarzone z kanałami, katalogami, przynależnościami i programami lojalnościowymi.




