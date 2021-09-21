---
title: Jeden z wierszy jest już w ładunku
description: 'Ta strona wyjaśnia, dlaczego pojawia się błąd: „Jeden z wierszy jest już w ładunku. Zwolnienie do magazynu jest niemożliwe” i jak można rozwiązać ten problem.'
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 0bdfaed005b9c58f7bd5f87dd6dffe648de47261
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477358"
---
# <a name="one-of-the-lines-is-already-on-a-load"></a>Jeden z wierszy jest już w ładunku

## <a name="symptoms"></a>Objawy

Podczas pracy z tworzeniem ładunku i wysyłkami może zostać wyświetlony następujący komunikat o błędzie:

> Jeden z wierszy jest już w ładunku. Zwolnienie do magazynu jest niemożliwe.

W przypadku ręcznego tworzenia ładunków lub konfigurowania procesu w taki sposób, aby ładunki były już tworzone przed wprowadzeniem wiersza zamówienia sprzedaży, założeniem jest, że kolejna wersja zostanie wykonana ręcznie i zostanie użyta trasa i ocena z ładunku.

W innym możliwym scenariuszu podejmowana jest próba automatycznego wydania do magazynu, ale nie udało się utworzyć pracy w procesie grupy czynności. W związku z tym zostanie utworzona otwarta wysyłka lub ładunek. Ta otwarta przesyłka lub ładunek blokuje następnie kolejne próby automatycznego zwolnienia zamówienia do czasu usunięcia otwartej przesyłki lub załadowania albo ręcznego ponownego przetworzenia grupy czynności.

## <a name="resolution"></a>Rozwiązanie

Można zwolnić ze strony zamówienia sprzedaży lub automatyczne zwolnienie można wykonać ze strony zwolnienia zamówienia sprzedaży tylko wtedy, gdy przed wydaniem do magazynu nie ma żadnego ładunku. Ładunek zostanie automatycznie utworzony po przetworzeniu grupy czynności.
