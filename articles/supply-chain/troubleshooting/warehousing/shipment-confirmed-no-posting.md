---
title: Wysyłka ładunku została potwierdzona, ale nie zaksięgowano żadnych wierszy
description: Potwierdzenie wysyłki nie ma wpływu na księgowanie. Właśnie aktualizuje stan wysyłki i ładunku. Księgowanie musi nastąpić w oddzielnym procesie.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: e754f1461672c1e9f2d8dd1a7ceffc81f3809120
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477343"
---
# <a name="shipment-for-load-has-been-confirmed-but-no-lines-are-posted"></a>Wysyłka ładunku została potwierdzona, ale nie zaksięgowano żadnych wierszy

## <a name="symptoms"></a>Objawy

Podczas pracy z wychodzącymi operacjami magazynowymi może zostać wyświetlony następujący komunikat:

> Wysyłka ładunku %1 została potwierdzona.

Nie nastąpiło jednak dalsze księgowanie.

## <a name="resolution"></a>Rozwiązanie

Jest to celowe. Potwierdzenie wysyłki nie ma wpływu na księgowanie. Właśnie aktualizuje stan wysyłki i ładunku. Księgowanie musi nastąpić w oddzielnym procesie.
