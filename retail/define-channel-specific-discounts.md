---
title: "Definiowanie rabatów właściwych dla kanału"
description: "Sprzedawcy detaliczni często ustawiają różne rabaty w różnych kanałach. W tym temacie opisano pojęcia, które należy znać, aby tworzyć rabaty dla konkretnych kanałów."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: RetailAffiliationPriceGroup, RetailCatalogPriceGroup, RetailChannelPriceGroup, RetailDiscountPriceGroup, RetailDiscountPricingWorkspace, RetailPeriodicDiscount, RetailStoreItemPriceList, RetailStoreTable
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 16401
ms.assetid: d807fd51-86aa-47a0-8e00-6c5ddd21ff6b
ms.search.region: global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: b21fd97426b331726c12ea29f89817a46dd445c3
ms.openlocfilehash: b2f59db59ea49925c3bb5e1d75beee95191220d0
ms.lasthandoff: 03/31/2017


---

# <a name="define-channel-specific-discounts"></a>Definiowanie rabatów właściwych dla kanału

Sprzedawcy detaliczni często ustawiają różne rabaty w różnych kanałach. W tym temacie opisano pojęcia, które należy znać, aby tworzyć rabaty dla konkretnych kanałów. 

<a name="channel-specific-discounts"></a>Rabaty właściwe dla kanału
--------------------------

Sprzedawcy detaliczni często oferują różne rabaty w różnych kanałach. To może zależeć od lokalnych uwarunkowań rynku lub być elementem konkurencji z innymi sprzedawcami detalicznymi.

Moduł Handel detaliczny i inny w programie Microsoft Dynamics 365 for Operations oferuje funkcjonalność grup cenowych definiujących rabaty właściwe dla kanału. Grup cenowe mogą być skojarzone z jednym lub kilkoma następującymi elementami: kanały, katalogi, przynależności i programy lojalnościowe. Ten artykuł dotyczy kanałów, ale te same pojęcia dotyczą rabatów katalogu, przynależności i programów lojalnościowych.

## <a name="price-groups"></a>Grupy cenowe
\[caption id="attachment\_256084" align="alignnone" width="640"\][![Grupy cenowe](./media/price-groups-1024x608.png)](./media/price-groups.png) Łącza do grup cenowych w module Handel detaliczny\[/caption\]

Powyższy wykres ilustruje relację między jednostkami, które mogą znajdować się w transakcji (kanał, katalog, przynależność, odbiorca, karta lojalnościowa), a różnymi typami rabatów, które można skonfigurować. Wszystkie transakcje odbywają się w kanale, więc kanał na pewno będzie ujęty w transakcji. Pozostałe elementy są opcjonalne. Na poszczególnych stronach danych głównych są łącza do powiązanej grupy cenowej, na której można wyświetlać i dodawać grupy cenowe w razie potrzeby. Grupa cenowa służy do tworzenia relacji czterech różnych typów elementów z rabatami, korektami cen i umowami handlowymi. Dobrze jest zaplanować strategię nazywania grup cenowych, która pozwoli lepiej je uporządkować. Jedną z możliwości jest używanie litery i cyfry na początku lub na końcu nazwy dla rozróżnienia typów. Np. 1-xxxxx dla grup cenowych kanału i 2-xxxxx dla grup cenowych katalogu. Dostępne są cztery strony zapytań, które koncentrują się na poszczególnych podmiotach sieci sprzedaży, dla których są skojarzone rabaty.

-   **Grupy cenowe kanału sprzedaży** — ta strona zawiera listę kanałów i rabatów połączonych ze sobą dla każdej grupy cenowej.
-   **Grupy cenowe katalogu** — ta strona zawiera listę katalogów i rabatów połączonych ze sobą dla każdej grupy cenowej.
-   **Grupy cenowe programów lojalnościowych** — ta strona zawiera listę programów lojalnościowych i rabatów połączonych ze sobą dla każdej grupy cenowej.
-   **Grupy cenowe przynależności** — ta strona zawiera listę przynależności i rabatów połączonych ze sobą dla każdej grupy cenowej.

## <a name="example-channel-discount-set-up"></a>Przykładowa konfiguracja rabatu kanału
Przykład poniżej ilustruje zadania niezbędne do skonfigurowania rabatu kanału.

1.  W tym przykładzie masz kanał **Houston** i chcesz utworzyć nowy rabat o nazwie **Powrót-do-szkoły**.
2.  Ponieważ strategie cenowa i rabatów dają możliwość tworzenia rabatów kanału, to tworząc kanał, zawsze tworzysz grupę cenową właściwą dla kanału.
3.  Masz grupę cenową **Houston-GC**, która jest skojarzona z kanałem **Houston**.
4.  Po utworzeniu nowego rabatu **Powrót-do-szkoły** musisz kliknąć **Grupy cenowe** na górze strony **Rabat**. Otworzy się strona **Grupy cenowe rabatów**. Następnie kliknij **Nowa** i wybierz grupę cenową **Houston-GC**.
5.  Teraz można włączyć rabatu i przesunąć go do kanału.

 

<a name="see-also"></a>Informacje dodatkowe
--------

[Korekty ceny i rabaty](price-adjustments-discounts.md)


