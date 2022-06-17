---
title: Zwracanie pozycji w ramach wielu zamówień i faktur dla odbiorcy
description: W tym artykule opisano funkcje obsługi zwrotów z wielu zamówień i faktur dla odbiorców w rozwiązaniu Dynamics 365 Commerce.
author: josaw1
ms.date: 08/27/2020
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-01-15
ms.dyn365.ops.version: 10
ms.openlocfilehash: 65ef700db5a81c49a962fd388af54e7811c088d2
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8890329"
---
# <a name="return-items-across-multiple-customer-orders-and-invoices"></a>Zwracanie pozycji w ramach wielu zamówień i faktur dla odbiorcy

[!include [banner](includes/banner.md)]


Zwrotów można dokonać z wielu zamówień i faktur. 

## <a name="configure-commerce-to-support-returns-across-multiple-customer-order-and-invoices"></a>Konfigurowanie modułu Commerce do obsługi zwrotów z wielu zamówień i faktur

1. Przejdź do **Parametry rozwiązania Commerce \> Zamówienia odbiorcy**.
1. Włącz parametr **Włącz zwroty z wielu zamówień**. 

## <a name="process-returns"></a>Przetwarzanie zwrotów

Po włączeniu tego parametru i zsynchronizowaniu zmian ze sklepami kasjer w sklepie można wybrać wiele zamówień sprzedaży dla danego odbiorcy i dokonać ich zwrotu.

Gdy zamówienia są wybrane, zostanie wyświetlona lista wszystkich produktów podlegających zwrotowi z wszystkich faktur dla tych zamówień. Kasjer może następnie wybrać produkty do zwrotu. Dla wszystkich wybranych produktów zostanie utworzone jedno zamówienie zwrotu.
