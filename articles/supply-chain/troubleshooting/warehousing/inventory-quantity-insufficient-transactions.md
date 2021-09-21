---
title: Ilość zapasów niezaktualizowana z powodu niewystarczającej liczby transakcji
description: Nie można zaktualizować ilości zapasów -1%, ponieważ nie ma wystarczającej liczby transakcji magazynowych dla pozycji %2 o określonych wymiarach.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 88130a969039dd741c8ea4fbaabe81acf0e6fb6a
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477259"
---
# <a name="system-cant-update-inventory-quantity-because-of-insufficient-transactions"></a>System nie może zaktualizować ilości zapasów z powodu niewystarczającej liczby transakcji

## <a name="symptoms"></a>Objawy

Ten problem może wystąpić, jeśli system nie może zaktualizować ilości zapasów, ponieważ nie ma wystarczającej liczby transakcji magazynowych o określonych wymiarach. Zostanie wyświetlony następujący komunikat o błędzie:

> Ilość zapasów -%1 nie zostać zaktualizowane z powodu niewystarczających transakcji magazynowych dla pozycji %2 o wymiarze Wymiar=%3, Kolor=%4, Dodatki=%5, Oddział=%6, Magazyn=%7, Lokalizacja=%8, Stan zapasów=dostępny, Numer identyfikacyjny=%9, Numer partii=%10 dla identyfikatora odwołania %11 w identyfikatorze partii %12.

## <a name="resolution"></a>Rozwiązanie

Upewnij się, że żadne transakcje magazynowe nie rezerwują ilości fizycznie. Na przykład te transakcje mogą otwierać zlecenia kontroli jakości, rekordy blokowania zapasów lub zamówienia wyjścia.
