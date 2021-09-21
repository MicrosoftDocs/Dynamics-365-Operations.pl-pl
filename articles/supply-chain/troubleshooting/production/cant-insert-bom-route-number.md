---
title: Nie można wstawić aktywnej wersji BOM i numerów marszruty
description: Jeśli już zdefiniowano domyślną lokację i magazyn dla wybranego produktu, nie jest wyświetlany monit o wstawienie aktywnej wersji BOM i numerów marszruty.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 241618d70f01c85df946a48493f5d84e0964218e
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477261"
---
# <a name="cant-insert-bill-of-material-and-route-when-creating-a-new-production-order"></a>Nie można wstawić listy składowej (BOM) i marszruty podczas tworzenia nowego zlecenia produkcyjnego

## <a name="symptoms"></a>Objawy

Podczas tworzenia nowego zlecenia produkcyjnego, po wprowadzeniu numeru towaru, pola **Oddział** i **Magazyn** są automatycznie ustawiane na domyślny oddział i magazyn, które są zdefiniowane na stronie **Domyślne ustawienia zamówienia** dla towaru gotowego. Ponadto aktywny numer BOM i numer marszruty są wprowadzane automatycznie, więc nie jest wyświetlany następujący komunikat z monitem o te wartości:

> Czy wstawić aktywną wersję BOM i trasy?

## <a name="resolution"></a>Rozwiązanie

Nie jest wyświetlany monit o wstawienie numerów BOM i marszruty w przypadku wybrania produktu, dla którego oddział i magazyn są już na stronie **Ustawienia domyślne zamówień**. Monit jest wyświetlany tylko wtedy, gdy nie zdefiniowano tych wartości dla wybranego produktu.
