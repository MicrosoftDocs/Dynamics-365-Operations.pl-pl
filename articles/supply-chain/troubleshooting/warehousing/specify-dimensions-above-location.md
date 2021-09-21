---
title: Nie można zwolnić ładunku dla ilości częściowej z hierarchią powyżej partii
description: W przypadku korzystania z towaru z hierarchią rezerwacji powyżej partii, w wierszach ładunku muszą być określone wymiary powyżej lokalizacji, aby umożliwić alokację zapasów.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: eb7e71cc271903cb689c33777b72862246f2dd42
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477283"
---
# <a name="cant-release-a-load-for-partial-quantity-with-batch-above-reservation-hierarchy"></a>Nie można zwolnić ładunku dla ilości częściowej z hierarchią rezerwacji powyżej partii

## <a name="symptoms"></a>Objawy

W przypadku użycia towaru, który ma rezerwację *partię powyżej* hierarchii rezerwacji, polecenie **Zwolnij do magazynu** na stronie **Pulpitu planowania ładunku** dla wyzwolenia ilości częściowej nie działa. Może zostać wyświetlony następujący komunikat o błędzie:

> Aby przypisać do grupy czynności, wiersze ładunku muszą określać wymiary powyżej lokalizacji. Aby przypisać te wymiary, zarezerwuj i ponownie utwórz wiersz ładunku.

Jeśli jednak używasz towaru, który ma hierarchię rezerwacji *partia poniżej*, możesz zwolnić ładunek dla ilości częściowej ze strony **Środowisko pracy planowania ładunku**.

## <a name="cause"></a>Powód

Jeśli wymiar zostanie umieszczony powyżej wymiaru **Lokalizacji** w hierarchii rezerwacji, musi zostać on określony przed zwolnieniem do magazynu. Zapasy można pomyślnie zaalokować tylko wtedy, gdy nie ma przerw w wymiarach powyżej lokalizacji.

## <a name="resolution"></a>Rozwiązanie

Upewnij się, że wszystkie wymiary powyżej **lokalizacji** zostały przypisane, rezerwując i ponownie tworząc wiersz ładunku.
