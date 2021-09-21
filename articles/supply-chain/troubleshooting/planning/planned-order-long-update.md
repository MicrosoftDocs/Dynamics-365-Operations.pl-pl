---
title: Aktualizacja zamówień planowanych zajmuje dużo czasu
description: Podczas aktualizowania ilości zapotrzebowania i/lub daty dostawy w planowanym zamówieniu zapisanie aktualizacji zajmuje zwykle co najmniej 30 sekund na zamówienie
author: ChristianRytt
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: ccf3305cc18ea0ccf2ac3e9ca0dd507fd12a9da7
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477321"
---
# <a name="planned-orders-take-a-long-time-to-update"></a>Aktualizacja zamówień planowanych zajmuje dużo czasu

## <a name="symptoms"></a>Objawy

Podczas aktualizowania ilości zapotrzebowania i/lub daty dostawy w planowanym zamówieniu zapisanie aktualizacji zajmuje zwykle co najmniej 30 sekund na zamówienie.

## <a name="resolution"></a>Rozwiązanie

Jest to znany błąd dotyczący wbudowanego aparatu planowania głównego. Jest to spowodowane przez podstawowe automatyczne rozłożenie przez strukturę BOM podczas edycji. Ten problem rozwiązano w optymalizacji planowania, w której planista może aktualizować i zatwierdzać odpowiednie zamówienia oraz, w razie potrzeby, uruchamiać przebieg planowania w celu zaktualizowania zamówień planowanych dla podstawowej struktury BOM.

Jednym ze sposobów poprawienia wydajności przy użyciu wbudowanego aparatu planowania głównego jest wykonanie następujących kroków:

1. Przejdź do **Planowanie główne \> Ustawienia \> Plany \> Plany główne**.
1. Wybierz plan.
1. Rozwiń kartę skróconą **Horyzont czasowy w dniach**.
1. Ustawienie **Rozłożenie** na wartość *Tak* i ustawienie pola poniżej tego ustawienia na wartość 0 (zero).

> [!NOTE]
> Ograniczy to okres rozłożeń wykonywanych dla tego planu głównego do jednego dnia.
