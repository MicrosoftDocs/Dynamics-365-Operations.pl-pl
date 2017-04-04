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

Detaliści często oferują różne rabaty w różnych kanałach. Jest to maja odbywać się do adresów lokalnych warunków rynkowych lub radzić sobie z konkurencyjnych detalistów.

Sieci sprzedaży i handlu w usłudze Microsoft Dynamics 365 dla operacji używa grupy cenowe do definiowania rabatów poszczególnych kanałów. Grup cenowe mogą być skojarzone z jednym lub kilkoma następującymi elementami: kanały, katalogi, przynależności i programy lojalnościowe. Ten artykuł dotyczy kanałów, ale te same pojęcia dotyczą rabatów katalogu, przynależności i programów lojalnościowych.

## <a name="price-groups"></a>Grupy cenowe
\[Identyfikator etykiety = "załącznik\_256084" Wyrównaj = szerokość "alignnone" = "640"\][![cena grup](./media/price-groups-1024x608.png)](./media/price-groups.png) cenę łącza grupy detalicznej\[/caption\]

Na powyższym diagramie przedstawiono relację między obiektami, które mogą znajdować się na transakcję (kanału, katalog, przynależności, klient, karta lojalnościowa) i różnych typów rabatów, które mogą być skonfigurowane. Wszystkie transakcje przeprowadzone w kanale, więc kanał jest musi znajdować się na transakcję. Pozostałe elementy są opcjonalne. Na poszczególnych stronach danych głównych są łącza do powiązanej grupy cenowej, na której można wyświetlać i dodawać grupy cenowe w razie potrzeby. Grupa cenowa służy do wiązania cztery różne typy jednostek do rabatów, korekty cen i umów handlowych. Zaleca się, że plan strategii jak będzie nazwa grupy cen. na utrzymywanie ich w porządku. Jedną z opcji jest użycie litery lub numer prefiks lub sufiks do rozróżniania różnych typów. Na przykład 1-xxxxx dla grupy cen kanału i 2-xxxxx dla wykazu grup cenowych. Dostępne są cztery strony zapytań, które koncentrują się na poszczególnych podmiotach sieci sprzedaży, dla których są skojarzone rabaty.

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

[Price adjustments and discounts](price-adjustments-discounts.md)


