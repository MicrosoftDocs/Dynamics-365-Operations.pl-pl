---
title: Nie można anulować dokumentu dostawy po zaksięgowaniu go z zamówienia
description: Po włączeniu procesu pobierania i wysyłania dla modułu WMS nie można anulować dokumentu dostawy po jego zaksięgowaniu z zamówienia sprzedaży. Ta strona przedstawia obejście.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: d20e66e2721560b8409eb63c3546a79adc188c7c
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477361"
---
# <a name="cant-cancel-a-packing-slip-after-its-posted-from-a-sales-order"></a>Nie można anulować dokumentu dostawy po zaksięgowaniu go z zamówienia sprzedaży

## <a name="symptoms"></a>Objawy

Po włączeniu procesu pobierania i wysyłania dla modułu zaawansowanego zarządzania magazynem (WMS) nie można anulować dokumentu dostawy po jego zaksięgowaniu z zamówienia sprzedaży.

## <a name="resolution"></a>Rozwiązanie

Aby poprawić zaksięgowane dokumenty dostawy dla towarów, dla których włączono WMS, księgowanie musi nastąpić z ładunku, a nie z zamówienia. Firma Microsoft oceniła ten błąd i ustaliła, że jest to ograniczenie funkcji.  

Ogólnie rzecz biorąc, zamówienie sprzedaży, które zostało pobrane i wysłane w ramach procesów zarządzania magazynem, może być dokumentem dostawy — aktualizowanym na podstawie ładunku lub wysyłki oraz samego dokumentu zamówienia sprzedaży. Jednak w przypadku dokumentu dostawy zaktualizowanie zamówienia sprzedaży z dokumentu zamówienie sprzedaży, wycofanie dokumentu dostawy nadal nie może zostać wykonane z poziomu ładunku lub zamówienia sprzedaży. Dlatego zalecamy użycie księgowania dokumentu dostawy z ładunku. W takim przypadku wycofanie, które musi zostać wykonane z ładunku, będzie włączone.
