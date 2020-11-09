---
title: Karty lojalnościowe odbiorców i punkty lojalnościowe
description: W tym temacie opisano integrację danych o kartach lojalnościowych odbiorców i punktach wynagrodzenia między aplikacjami Finance and Operations i Common Data Service.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-10
ms.openlocfilehash: 24ce08bb6cba9c74075151bafe0b07509fbdf73d
ms.sourcegitcommit: 0a741b131ed71f6345d4219a47cf5f71fec6744b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "3998021"
---
# <a name="customer-loyalty-cards-and-reward-points"></a>Karty lojalnościowe odbiorców i punkty lojalnościowe

[!include [banner](../../includes/banner.md)]



Firmy klasyfikują odbiorców i świadczą zaawansowane usługi w oparciu o zakupy i wydatki klientów. W pakiecie aplikacji Microsoft Dynamics 365 Dynamics 365 Commerce istnieje infrastruktura i funkcje ułatwiające i obsługujące karty lojalnościowe odbiorców, punkty wynagrodzenia, ceny na podstawie lojalności i zakupy na podstawie nagród. Gdy dane o kartach lojalnościowych odbiorców i punktach sprzedaży w module Commerce są synchronizowane z Common Data service, aplikacje oparte na modelach w Dynamics 365 mogą wykorzystywać te dane. Na przykład użytkownicy Dynamics 365 Customer Service mogą skorzystać z danych, aby dostarczać te same zaawansowane usługi za pośrednictwem pomocy technicznej.

## <a name="templates"></a>Szablony

| Aplikacje Finance and Operations | Aplikacje oparte na modelu w systemie Dynamics 365 | opis |
|-----------------------------|-----------------------------------|-------------|
| Karta lojalnościowa                | msdyn\_loyaltycards               | Ten szablon powoduje zsynchronizowanie informacji o kartach lojalnościowych klienta. |
| Punkty lojalnościowe       | msdyn\_loyaltyrewardpoints        | Ten szablon powoduje zsynchronizowanie informacji o punktach nagród klienta. |

[!include [banner](../../includes/dual-write-symbols.md)]

[!include [mapping loyalty card](includes/LoyaltyCard-msdyn-loyaltycards.md)]

[!include [mapping reward points](includes/LoyaltyRewardPoints-msdyn-loyaltyrewardpoints.md)]
