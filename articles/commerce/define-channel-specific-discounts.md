---
title: Definiowanie rabatów właściwych dla kanału
description: Sprzedawcy detaliczni często ustawiają różne rabaty w różnych kanałach. W tym temacie opisano pojęcia, które należy znać, aby tworzyć rabaty dla konkretnych kanałów.
author: scott-tucker
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailAffiliationPriceGroup, RetailCatalogPriceGroup, RetailChannelPriceGroup, RetailDiscountPriceGroup, RetailDiscountPricingWorkspace, RetailPeriodicDiscount, RetailStoreItemPriceList, RetailStoreTable
audience: Application User
ms.reviewer: josaw
ms.custom: 16401
ms.assetid: d807fd51-86aa-47a0-8e00-6c5ddd21ff6b
ms.search.region: global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: c4003bd78e400994f3c164d2f7e8e3aa5ce93146
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5802076"
---
# <a name="define-channel-specific-discounts"></a>Definiowanie rabatów specyficznych dla kanału

[!include [banner](includes/banner.md)]

W tym temacie opisano pojęcia, które należy znać, aby tworzyć rabaty dla konkretnych kanałów.

## <a name="channel-specific-discounts"></a>Rabaty właściwe dla kanału

Sprzedawcy detaliczni często oferują różne rabaty w różnych kanałach. To może zależeć od lokalnych uwarunkowań rynku lub być elementem konkurencji z innymi sprzedawcami detalicznymi.

Commerce używa grup cenowych do definiowania rabatów właściwych dla kanału. Grup cenowe mogą być skojarzone z jednym lub kilkoma następującymi elementami: kanały, katalogi, przynależności i programy lojalnościowe. Ten artykuł dotyczy kanałów, ale te same pojęcia dotyczą rabatów katalogu, przynależności i programów lojalnościowych.

## <a name="price-groups"></a>Grupy cenowe

[![Grupy cenowe](./media/price-groups-1024x608.png)](./media/price-groups.png)

Powyższy wykres ilustruje relację między jednostkami, które mogą znajdować się w transakcji (kanał, katalog, przynależność, odbiorca, karta lojalnościowa), a różnymi typami rabatów, które można skonfigurować. Wszystkie transakcje odbywają się w kanale, więc kanał na pewno będzie ujęty w transakcji. Pozostałe elementy są opcjonalne. Na poszczególnych stronach danych głównych są łącza do powiązanej grupy cenowej, na której można wyświetlać i dodawać grupy cenowe w razie potrzeby. Grupa cenowa służy do tworzenia relacji czterech różnych typów elementów z rabatami, korektami cen i umowami handlowymi. Dobrze jest zaplanować strategię nazywania grup cenowych, która pozwoli lepiej je uporządkować. Jedną z możliwości jest używanie litery i cyfry na początku lub na końcu nazwy dla rozróżnienia typów. Np. 1-xxxxx dla grup cenowych kanału i 2-xxxxx dla grup cenowych katalogu. Dostępne są cztery strony zapytań, które koncentrują się na poszczególnych podmiotach handlowych, dla których są skojarzone rabaty.

- **Grupy cenowe kanału** — ta strona zawiera listę kanałów i rabatów połączonych ze sobą dla każdej grupy cenowej.
- **Grupy cenowe katalogu** — ta strona zawiera listę katalogów i rabatów połączonych ze sobą dla każdej grupy cenowej.
- **Grupy cenowe programów lojalnościowych** — ta strona zawiera listę programów lojalnościowych i rabatów połączonych ze sobą dla każdej grupy cenowej.
- **Grupy cenowe przynależności** — ta strona zawiera listę przynależności i rabatów połączonych ze sobą dla każdej grupy cenowej.

## <a name="example-channel-discount-set-up"></a>Przykładowa konfiguracja rabatu kanału

Przykład poniżej ilustruje zadania niezbędne do skonfigurowania rabatu kanału.

1. W tym przykładzie masz kanał **Houston** i chcesz utworzyć nowy rabat o nazwie **Powrót-do-szkoły**.
2. Ponieważ strategie cenowa i rabatów dają możliwość tworzenia rabatów kanału, to tworząc kanał, zawsze tworzysz grupę cenową właściwą dla kanału.
3. Masz grupę cenową **Houston-GC**, która jest skojarzona z kanałem **Houston**.
4. Po utworzeniu nowego rabatu **Powrót-do-szkoły** musisz kliknąć **Grupy cenowe** na górze strony **Rabat**. Otworzy się strona **Grupy cenowe rabatów**. Następnie kliknij **Nowa** i wybierz grupę cenową **Houston-GC**.
5. Teraz można włączyć rabatu i przesunąć go do kanału.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Korekty cen i rabaty](price-adjustments-discounts.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]