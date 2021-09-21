---
title: Błąd łącznej ilości towaru przy próbie zakończenia zlecenia
description: Podczas próby zakończenia stanu zlecenia produkcyjnego i zgłoszenia go jako gotowego może wystąpić błąd łącznej ilości towaru. Na tej stronie opisano przyczyny i sposób naprawy tego problemu.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 5f0c2c2ca64ada9d72c0ebd04e7de561aaa52039
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477298"
---
# <a name="total-good-quantity-error-when-trying-to-end-a-production-order"></a>Błąd łącznej ilości towaru przy próbie zakończenia zlecenia produkcyjnego

## <a name="symptoms"></a>Objawy

Podczas próby zaksięgowania arkusza zgłoszonych towarów gotowych w zleceniu produkcyjnym wyświetlany jest następujący komunikat o błędzie:

> Całkowita ilość gotowych wyrobów dobrych dla produkcji będzie wynosić %1. Informacja zwrotna dla ostatniej operacji wynosi w sumie 0,00.

## <a name="cause"></a>Powód

Ten problem występuje, jeśli ilości zaksięgowane w ostatniej operacji były nieprawidłowe. Na przykład jeśli rozpoczęto produkcję, ale ilość, która musi zostać uruchomiona, nie została przydzielona, arkusz karty marszruty zostanie zaksięgowany bez żadnych wierszy. Aby potwierdzić sytuację, otwórz zlecenie produkcyjne, a następnie w okienku akcji na karcie **Widok** wybierz opcję **Karta marszruty**.

## <a name="resolution"></a>Rozwiązanie

Ten problem można rozwiązać, księgując dodatkowe arkusze dla operacji, dla których nie zaksięgowano prawidłowo arkuszy. Uruchom ponownie zlecenie produkcyjne i zaznacz opcję, aby zaksięgować dodatkowe arkusze. Ta akcja nie spowoduje rozpoczęcia zlecenia produkcyjnego, ale spowoduje zaksięgowanie arkuszy. Karta marszruty powinna wtedy pokazywać zaksięgowane ilości i powinno być możliwe pomyślne zakończenie zleceń produkcyjnych.
