---
title: Nie można usunąć rezerwacji zapasów w wierszu zamówienia sprzedaży
description: W przypadku otwartej pracy nad wierszem sprzedaży i próby anulowania rezerwacji zapasów w wierszu zostanie wyświetlony błąd. Dokończ lub usuń pracę, aby zwolnić rezerwację.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 1a042065dc4cd637aff58e55cf16179b7022f6ca
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477317"
---
# <a name="cant-unreserve-inventory-on-a-sales-order-line"></a>Nie można usunąć rezerwacji zapasów w wierszu zamówienia sprzedaży

## <a name="symptoms"></a>Objawy

W przypadku otwartej pracy nad wierszem zamówienia sprzedaży i próby anulowania rezerwacji zapasów w tym wierszu zostanie wyświetlony następujący komunikat o błędzie:

> Nie można usunąć rezerwacji, ponieważ utworzono pracę opartą na rezerwacjach.

## <a name="resolution"></a>Rozwiązanie

Sprawdź, czy istnieje otwarta grupa załadunkowa, aby przenieść pozycję z stacji pakowania do innej lokalizacji (np. *Brama dokowa*). Przejrzyj rekordy w **Dzienniku historii tworzenia pracy** i **Szczegóły pracy**, aby określić, co fizycznie rezerwuje zapasy, a następnie ukończyć lub usunąć pracę, aby zwolnić rezerwację.
