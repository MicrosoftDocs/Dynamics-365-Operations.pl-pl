---
title: "Ustawianie alertów o oszustwie"
description: "W tym temacie wyjaśniono sposób konfigurowania reguł powiadomień dla działu obsługi klienta o potencjalnie fałszywych informacjach przy przetwarzaniu zamówień. Można zdefiniować określone kody, które będą używane do automatycznego lub ręcznego wstrzymania podejrzanych zamówień."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 79103
ms.assetid: e342af8d-7498-4d20-8483-ab368429c578
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 7255f2b7e49f56a731d0e3745b4752091013668b
ms.contentlocale: pl-pl
ms.lasthandoff: 05/25/2017



---

# <a name="set-up-fraud-alerts"></a>Ustawianie alertów o oszustwie

[!include[banner](includes/banner.md)]


W tym temacie wyjaśniono sposób konfigurowania reguł powiadomień dla działu obsługi klienta o potencjalnie fałszywych informacjach przy przetwarzaniu zamówień. Można zdefiniować określone kody, które będą używane do automatycznego lub ręcznego wstrzymania podejrzanych zamówień. 

Aby skonfigurować i używać reguł sprawdzania oszustwa, należy włączyć sprawdzanie oszustwa i zdefiniować podstawowe wartości sprawdzania oszustwa w parametrach biura obsługi. Istnieją dwa typy reguł dotyczących oszustw:

-   **Reguły statyczne** używaj konkretnych wartości, np. numeru telefonu, który znajduje się na czarnej liście.
-   **Reguły dynamiczne** mogą składać ze zmiennych i warunków.

Aby utworzyć regułę dynamiczną, należy najpierw utworzyć zmienne i warunki określające, czego dotyczy reguła i kiedy ma być stosowana. Na przykład użytkownik chce utworzyć regułę, która wymaga, by każde zamówienie sprzedaży składane przez odbiorcę 1202 o wartości 1000,00 lub większej musi być wstrzymywane do czasu zweryfikowania płatności odbiorcy. W tym przypadku zmiennymi są odbiorca 1202 i 1000,00 jako suma zamówienia. Warunek określa, czy jeśli odbiorca 1202 złoży zamówienie i łączna suma zamówienia wynosi 1000,00 lub jest wyższa od tej kwoty, zamówienie sprzedaży musi być wstrzymywane do chwili sprawdzenia płatności odbiorcy.




