---
title: Opcje blokowania rabatów na produkty detaliczne
description: Istnieją różne powody, dla których sprzedawcy detaliczni chcą uniemożliwiać stosowanie rabatów do niektórych produktów — poprzez promocję albo podczas sprzedaży w punkcie sprzedaży.
author: jblucher
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailPeriodicDiscount
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 85183
ms.assetid: e8c5a24f-7edd-4fd6-af80-5e0ac9f03127
ms.search.region: Global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 6a683ffce487dc4388711ad160c2e8dc55a690dd
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4414871"
---
# <a name="options-for-preventing-discounts-for-retail-products"></a>Opcje blokowania rabatów na produkty detaliczne

[!include [banner](includes/banner.md)]

Istnieją różne powody, dla których sprzedawcy detaliczni chcą uniemożliwiać stosowanie rabatów do niektórych produktów — poprzez promocję albo podczas sprzedaży w punkcie sprzedaży.

Następujące opcje, które można znaleźć na karcie **Sprzedaż** dla zwolnionych produktów, pozwalają skonfigurować blokadę stosowania wszystkich lub tylko ręcznych rabatów. Te ustawienia można także określić na poziomie kategorii w hierarchii kategorii.

- **Nie zezwalaj na żadne rabaty** — Wybierz tę opcję, aby uniemożliwić stosowanie jakichkolwiek typów rabatów do tego produktu. Obejmuje to promocje takie jak rabat łączony, rabaty ilościowe i progowe, a także ręczne rabaty dla wiersza i transakcji stosowane podczas sprzedaży przez użytkownika punktu sprzedaży.
- **Nie zezwalaj na rabaty ręczne** — Wybierz tę opcję, aby zablokować tylko ręczne rabaty dla wierszy lub transakcji stosowane podczas sprzedaży przez użytkownika punktu sprzedaży. Produkty, dla których zaznaczono tę opcję, nadal kwalifikują się do promocji, takich jak rabaty łączone i progowe.

> [!NOTE]
> Te ustawienia nie ograniczają operacji ręcznej zmiany ceny, ponieważ ustawia ona podstawę ceny i nie jest traktowana jako rabat.

[![Pole blokowania rabatów](./media/prevent-discounts.png)](./media/prevent-discounts.png)
