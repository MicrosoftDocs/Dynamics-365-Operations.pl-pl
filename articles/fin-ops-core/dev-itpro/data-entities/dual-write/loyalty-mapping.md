---
title: Karty lojalnościowe odbiorców i punkty lojalnościowe
description: W tym temacie opisano integrację danych o kartach lojalnościowych odbiorców i punktach wynagrodzenia w konfiguracjach z podwójnym zapisem.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/10/2019
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 39e1d5b0a73b198b164e51a18222dbd985192070
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2021
ms.locfileid: "5568035"
---
# <a name="customer-loyalty-cards-and-reward-points"></a>Karty lojalnościowe odbiorców i punkty lojalnościowe

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Firmy klasyfikują odbiorców i świadczą zaawansowane usługi w oparciu o zakupy i wydatki klientów. Na przykład w rozwiązaniu Dynamics 365 Commerce istnieje infrastruktura i funkcje ułatwiające i obsługujące karty lojalnościowe odbiorców, punkty wynagrodzenia, ceny na podstawie lojalności i zakupy na podstawie nagród. Gdy dane o kartach lojalnościowych odbiorców i punktach sprzedaży w module Commerce są synchronizowane z Dataverse, aplikacje do zakontraktowania odbiorcy mogą wykorzystywać te dane. Na przykład użytkownicy Dynamics 365 Customer Service mogą skorzystać z danych, aby dostarczać te same zaawansowane usługi za pośrednictwem pomocy technicznej.

## <a name="templates"></a>Szablony

| Aplikacje Finance and Operations | Aplikacje oparte na modelu w systemie Dynamics 365 | opis |
|-----------------------------|-----------------------------------|-------------|
| Karta lojalnościowa                | msdyn\_loyaltycards               | Ten szablon powoduje zsynchronizowanie informacji o kartach lojalnościowych klienta. |
| Punkty lojalnościowe       | msdyn\_loyaltyrewardpoints        | Ten szablon powoduje zsynchronizowanie informacji o punktach nagród klienta. |

[!include [banner](../../includes/dual-write-symbols.md)]

[!include [mapping loyalty card](includes/LoyaltyCard-msdyn-loyaltycards.md)]

[!include [mapping reward points](includes/LoyaltyRewardPoints-msdyn-loyaltyrewardpoints.md)]


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]