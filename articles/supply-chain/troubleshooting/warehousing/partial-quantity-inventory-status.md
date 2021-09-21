---
title: Wprowadzanie zmiany stanu zapasów dla pracy częściowej ilości
description: Na tej stronie opisano, jak utworzyć element menu z odpowiednimi ustawieniami, aby umożliwić pracownikom zmianę stanu zapasów dla częściowej ilości partii.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 056ce412955808ddf126025ad917b874c54a5e62
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477258"
---
# <a name="enable-inventory-status-change-for-partial-quantity-work"></a>Zmiana włączania stanu zapasów dla pracy częściowej ilości

## <a name="symptoms"></a>Objawy

Musisz zmienić stan zapasów dla częściowej ilości partii.

## <a name="resolution"></a>Rozwiązanie

Aby umożliwić pracownikom wprowadzenie tej zmiany, można utworzyć element menu dla aplikacji Warehouse Management. Na stronie **Elementy menu urządzenia przenośnego** utwórz (lub edytuj) element menu, który ma następujące ustawienia:

- **Tryb:** *Praca*
- **Używanie istniejącej pracy:** *Nie*
- **Proces tworzenia pracy:** *Przesunięcie*
- **Wyświetl kolumnę Stan zapasów:** *Tak*

W razie konieczności można skonfigurować inne pola na stronie.
