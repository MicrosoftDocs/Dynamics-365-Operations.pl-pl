---
title: Nie można wybrać zmiany stanu zapasów jako Typ pracy
description: Nie można utworzyć wiersza szablonu pracy dla zmiany stanu zapasów, ponieważ typ pracy jest używany tylko przez procesy systemowe. Wybierz inny typ pracy.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: ad7f26f3235d15779583f9cdadeb4e6dca16242a
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477342"
---
# <a name="cant-select-inventory-status-change-in-the-work-type-column"></a>Nie można wybrać zmiany stanu zapasów w kolumnie Typ pracy

## <a name="symptoms"></a>Objawy

Podczas konfigurowania rozwiązania Microsoft Dynamics 365 Supply Chain Management może zostać wyświetlony następujący komunikat o błędzie:

> Nie można utworzyć wiersza szablonu pracy dla zmiany stanu zapasów, ponieważ typ pracy jest nieprawidłowy. Wybierz inny typ pracy.

## <a name="resolution"></a>Rozwiązanie

Jest to celowe. Typ pracy *Zmiana stanu zapasów* jest używany tylko przez procesy systemowe. Nie można go skonfigurować. Ponieważ lista typów prac jest ustalona jako wyliczenie, dodatkowe wpisy nie mogą być filtrowane z menu rozwijanego **Typ pracy**.
