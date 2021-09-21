---
title: Monit o automatyczną rezerwację jest wyświetlany w przypadku dostępnych zapasów
description: W przypadku używania tego samego towaru w magazynie, w którym nie włączono procesów magazynowych, jest wyświetlany monit o automatyczną rezerwację. Określ wszystkie wymiary powyżej lokalizacji.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: a15502ce8c5bc61d37cedd746985176408a2f362
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477345"
---
# <a name="auto-reservation-prompt-for-batch-number-is-shown-even-with-available-inventory"></a>Monit o automatyczną rezerwację dla numeru partii jest wyświetlany nawet w przypadku dostępnych zapasów

## <a name="symptoms"></a>Objawy

Gdy używasz towaru, który ma hierarchię rezerwacji *partia powyżej* w magazynie, w którym nie włączono procesów magazynowych, a rezerwacja automatyczna jest włączona, monit automatycznej rezerwacji o numer partii jest wyświetlany, nawet jeśli tylko jedna partia jest dostępne do pobrania.

Jednak w przypadku używania tego samego towaru w magazynie, w którym są włączone procesy magazynowe, monit o automatyczną rezerwację nie jest wyświetlany.

## <a name="resolution"></a>Rozwiązanie

Jeśli hierarchia rezerwacji jest zdefiniowana jako *partia nad* lub *seria nad*, w zamówieniach popytu zawsze musi być określony wymiar, do których istnieje odwołanie (**Numer partii** lub **Numer seryjny**). Procesy magazynowe mogą być w stanie wypełnić informacje, jeśli jest dostępny jeden numer partii lub numer seryjny. Jednak magazyn nie jest włączony dla procesów magazynowych, użytkownik musi zawsze określić wszystkie wymiary powyżej opcji **Lokalizacja**.
