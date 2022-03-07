---
title: Jednostka i ilość jednostek nie działają poprawnie w arkuszu magazynowym
description: Jednostka i ilość jednostek nie działają poprawnie w arkuszu magazynowym
author: sherry-zheng
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 39f462ae325aa1104a25a8290daed70388e624ec
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477289"
---
# <a name="the-unit-and-unit-quantity-arent-working-correctly-in-the-inventory-journal"></a>Jednostka i ilość jednostek nie działają poprawnie w arkuszu magazynowym

## <a name="symptoms"></a>Objawy

Podczas pracy z jednostkami i ilościami w arkuszu magazynowymi może wystąpić jeden lub oba następujące problemy:

- Nie ma żadnych jednostek ani ilości jednostek w arkuszu magazynowym, gdy dla zwolnionego produktu jest ustawiona jednostka konwersji i nie można zmienić tej jednostki w arkuszu magazynowym.
- W arkuszu magazynowym są widoczne pola **Ilość** i **Jednostka**, ale pole **Ilość jednostki** jest niewidoczne. Po zmianie jednostki, wprowadzeniu ilości i zaksięgowaniu arkusza w arkuszu będzie nadal wyświetlana oryginalna jednostka miary dla tej ilości.

## <a name="resolution"></a>Rozwiązanie

Aby naprawić ten problem, należy wykonać następujące czynności.

1. Upewnij się, że w obszarze roboczym **Zarządzanie funkcjami** jest włączona funkcja *Używanie jednostki miary i ilości jednostek w arkuszach magazynowych*. Ta funkcja dodaje pola **Jednostka** i **Ilość jednostek** do arkusza.
1. Po włączeniu tej funkcji użyj pól **Ilość**, **Ilość jednostki** i **Jednostka** w następujący sposób:

    - **Ilość** — określ ilość, używając domyślnej jednostki zdefiniowanej dla zwolnionego produktu. W tym miejscu jednak nie jest wyświetlana jednostka domyślna. Jeśli zostanie ustawiona konwersja między jednostką domyślną a jednostką wybraną w polu **Jednostka**, pole **Ilość** jest automatycznie aktualizowane na podstawie opcji wybranych w polach **Ilość jednostki** i **Jednostka**.
    - **Ilość jednostki** — określ ilość, używając jednostki wybranej w polu **Jednostka**.
    - **Jednostka** — wybierz jednostkę, która zostanie zastosowania do wartości w polu **Ilość jednostki**.
