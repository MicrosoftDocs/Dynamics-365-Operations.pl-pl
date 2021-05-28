---
title: Planowane zamówienie zakupu jest tworzone, gdy zakup istnieje w ciągu ujemnych dni
description: Jeśli kod zapotrzebowania to Minimum/Maksimum, optymalizacja planowania tworzy planowane zamówienie zakupu jeśli zakup istnieje w ciągu dni ujemnych.
author: ChristianRytt
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo,MpsIntegrationParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ilebedev
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 826496c2de956ff949dd79ab8aa643053719bf75
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026819"
---
# <a name="planned-purchase-order-is-created-when-a-purchase-exists-within-negative-days"></a>Planowane zamówienie zakupu jest tworzone, gdy zakup istnieje w ciągu ujemnych dni

Numer artykułu z bazy wiedzy: 4614298

## <a name="symptoms"></a>Objawy

Jeśli kod zapotrzebowania to *Minimum/Maksimum*, optymalizacja planowania tworzy planowane zamówienie zakupu jeśli zakup istnieje w ciągu dni ujemnych.

## <a name="resolution"></a>Rozdzielczość

Optymalizacja planowania nie obsługuje dni ujemnych.. Jednak zawsze zapewnia, że planowane zamówienia nie zostaną zaplanowane w czasie realizacji w stosunku do bieżącej daty. Na przykład czas realizacji zakupu wynosi 10 dni, a zamówienie powinno dotrzeć osiem dni od dzisiaj. W tym przypadku zamówienie zakupu zostanie użyte jako podaż dla popytu w ciągu pięciu dni od dzisiaj.

Dlatego zalecamy skorygowanie czasów realizacji, tak aby pokrywały się wszystkie (lub prawie wszystkie) scenariusze.
