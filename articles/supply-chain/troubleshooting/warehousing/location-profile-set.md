---
title: Profil lokalizacji nie zezwala na ujemne zapasy, ale ujemne wartości dostępnych zapasów są dozwolone
description: Opcja Zezwalaj na ujemny stan zapasów dla profilu lokalizacji ma wartość Nie, ale system nadal zezwala na ujemne wartości dostępnych zapasów.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: WHSLocationProfile
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: shawan
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 2a7345281301ee70a512dfadcd553cb4eb33003904d0dddf6967659b693f60d7
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6742615"
---
# <a name="location-profile-disallows-negative-inventory-but-negative-on-hand-inventory-is-permitted"></a>Profil lokalizacji nie zezwala na ujemne zapasy, ale ujemne wartości dostępnych zapasów są dozwolone

Numer artykułu z bazy wiedzy: 4613622

## <a name="symptoms"></a>Objawy

Opcja **Zezwalaj na ujemny stan zapasów** dla profilu lokalizacji ma wartość *Nie*, ale system nadal zezwala na ujemne wartości dostępnych zapasów.

## <a name="example-scenario"></a>Przykładowy scenariusz

W przypadku transakcji regulowanych przez rząd system musi mieć możliwość notowania ujemnych wartości zapasów w celu zarezerwowania strat. Towar ma mieć możliwość pokazywania ujemnego stanu magazynowego, ale tylko w wyznaczonych lokalizacjach, np. w magazynie. Jeśli jednak grupa modeli pozycji zezwala na ujemne wartości zapasów, okazuje się, że w lokalizacji jest ustawiona opcja zezwalania na ujemne zapasy. Jeśli towar jest tak ustawiony, że ujemne zapasy nie są dozwolone, nie ma znaczenia, jak jest ustawiony profil lokalizacji.

## <a name="resolution"></a>Rozdzielczość

Ustawienie **Zezwalaj na ujemny stan zapasów** w profilu lokalizacji dotyczy tylko procesów magazynowych, takich jak pobieranie. Grupy modeli pozycji ustawione tak, aby zezwalały na ujemne zapasy, wpływają jednak na wszystkie procesy z modułów Zarządzanie zapasami i Zarządzanie magazynem, a profil lokalizacji nie zastąpi ustawienia.

Istnieje możliwość kontrolowania, czy magazyn może przenosić ujemne zapasy. Należy ustawić grupy modeli pozycji, aby nie zezwalać na ujemne wartości magazynu fizycznego, i ustawić tylko odpowiedni magazyn, aby zezwalać na ujemne zapasy.
