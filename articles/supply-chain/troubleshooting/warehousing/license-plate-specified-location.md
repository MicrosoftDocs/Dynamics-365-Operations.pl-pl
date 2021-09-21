---
title: Dla tej lokalizacji musi zostać określony numer identyfikacyjny
description: Jeśli ten błąd występuje podczas tworzenia zamówienia przeniesienia dla magazynu z włączoną funkcją WMS, pole Domyślna lokalizacja przyjęcia jest puste dla magazynu tranzytowego.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 2e562ad2b41dd149f215adc83bd2d54e55dccc05
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477275"
---
# <a name="license-plate-specification-error-when-confirming-shipment-for-a-transfer-order"></a>Błąd specyfikacji numeru identyfikacyjnego podczas potwierdzania wysyłki dla zamówienia przeniesienia

## <a name="symptoms"></a>Objawy

Jeśli utworzysz zlecenie przeniesienia przy użyciu magazynu, który obsługuje zaawansowane zarządzanie magazynem (WMS), a następnie po zakończeniu pracy spróbujesz potwierdzić wysyłkę, możesz zobaczyć następujący komunikat o błędzie:

> Dla tej lokalizacji musi zostać określony numer identyfikacyjny.

## <a name="cause"></a>Powód

Dzieje się tak, ponieważ pole **Domyślna lokalizacja przychodu** jest puste dla magazynu tranzytowego magazynu „z”.

## <a name="resolution"></a>Rozwiązanie

Aby rozwiązać ten problem, należy określić domyślną lokalizację przychodu w magazynie tranzytowym. Upewnij się, że ta lokalizacja jest kontrolowana za pomocą numeru identyfikacyjnego.
