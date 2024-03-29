---
title: Karty lojalnościowe odbiorców i punkty lojalnościowe
description: W tym artykule opisano integrację danych o kartach lojalnościowych odbiorców i punktach wynagrodzenia w konfiguracjach z podwójnym zapisem.
author: RamaKrishnamoorthy
ms.date: 03/10/2019
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-03-10
ms.openlocfilehash: 399682b3042c32fbf6fa200213f1b4982ed97174
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9289123"
---
# <a name="customer-loyalty-cards-and-reward-points"></a>Karty lojalnościowe odbiorców i punkty lojalnościowe

[!include [banner](../../includes/banner.md)]



Firmy klasyfikują odbiorców i świadczą zaawansowane usługi w oparciu o zakupy i wydatki klientów. Na przykład w rozwiązaniu Dynamics 365 Commerce istnieje infrastruktura i funkcje ułatwiające i obsługujące karty lojalnościowe odbiorców, punkty wynagrodzenia, ceny na podstawie lojalności i zakupy na podstawie nagród. Gdy dane o kartach lojalnościowych odbiorców i punktach sprzedaży w module Commerce są synchronizowane z Dataverse, aplikacje do zakontraktowania odbiorcy mogą wykorzystywać te dane. Na przykład użytkownicy Dynamics 365 Customer Service mogą skorzystać z danych, aby dostarczać te same zaawansowane usługi za pośrednictwem pomocy technicznej.

## <a name="templates"></a>Szablony

Aplikacje Finanse i Działania | Aplikacje Customer Engagement     | opis
|-----------------------------|-----------------------------------|-------------|
[Karta lojalnościowa](mapping-reference.md#149) | msdyn_loyaltycards | Ten szablon powoduje zsynchronizowanie informacji o kartach lojalnościowych klienta. |
[Poziomy lojalności](mapping-reference.md#226) | msdyn_loyaltylevels | Ten szablon powoduje zsynchronizowanie informacji o punktach nagród klienta. |
[Punkty lojalnościowe](mapping-reference.md#150) | msdyn_loyaltyrewardpoints | |

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
