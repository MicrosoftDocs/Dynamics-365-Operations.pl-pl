---
title: Zwróć produkty w ramach wielu zamówień klientów i faktur
description: W tym temacie opisano funkcje obsługi zwrotów z wielu zamówień i faktur w rozwiązaniu Dynamics 365 Retail.
author: josaw1
manager: AnnBe
ms.date: 03/05/2019
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-01-15
ms.dyn365.ops.version: 10
ms.openlocfilehash: 25a1081e5f903076e23089c41dda7437f8a70124
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2019
ms.locfileid: "2017996"
---
# <a name="return-items-across-multiple-customer-orders-and-invoices"></a>Zwracanie towarów z wielu zamówień i faktur

[!include [banner](includes/banner.md)]


Zwrotów można dokonać z wielu zamówień i faktur. 

## <a name="configure-retail-to-support-returns-across-multiple-customer-order-and-invoices"></a>Konfigurowanie modułu Retail do obsługi zwrotów z wielu zamówień i faktur

1. Przejdź do **Parametry rozwiązania Retail \> Zamówienia odbiorcy**.
1. Włącz parametr **Włącz zawroty z wielu zamówień**. 

## <a name="process-returns"></a>Przetwarzanie zwrotów

Po włączeniu tego parametru i zsynchronizowaniu zmian ze sklepami kasjer w sklepie można wybrać wiele zamówień sprzedaży dla danego odbiorcy i dokonać ich zwrotu.

Gdy zamówienia są wybrane, zostanie wyświetlona lista wszystkich produktów podlegających zwrotowi z wszystkich faktur dla tych zamówień. Kasjer może następnie wybrać produkty do zwrotu. Dla wszystkich wybranych produktów zostanie utworzone jedno zamówienie zwrotu.
