---
title: Rozwiązywanie problemów z raportami analitycznymi
description: W tym temacie wyjaśniono, jak rozwiązywać i diagnozować problemy polegające na tym, że zmiany w danych klienta nie pojawiają się w żadnych jego obszarach roboczych.
author: twheeloc
ms.date: 08/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 6ea04c06858cc98b0e233b9133d9dfbebfe59fd6
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/31/2022
ms.locfileid: "8067736"
---
# <a name="troubleshoot-analytic-reports"></a>Rozwiązywanie problemów z raportami analitycznymi


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

**Wystawienie**

Zmiany danych odbiorcy nie pojawiają się w kartach **Analizy** tych obszarów roboczych odbiorcy.

**Powód**

Domyślnie raporty Microsoft Power BI są odświeżane co cztery godziny, zgodnie z harmonogramem zadania wsadowego Wdróż miarę.

**Rozdzielczość**

Ten problem może być tylko kwestią czasu. Wykonaj poniższe czynności, aby uruchomić zadanie wsadowe i zaktualizować obszary robocze analizy.

1. Otwórz **zadania wsadowe** w menu **administrowanie systemem \>łącza \>zadania wsadowe \>zadania wsadowe**. Można także użyć funkcji Wyszukaj i wpisać **zadania wsadowe**.
1. Znajdź zadanie **Wdróż miarę** na liście.
1. Wybierz **Edytuj** u góry strony i ustaw planowaną datę/godzinę rozpoczęcia na wartość, która odświeży analizy bliżej czasu bieżącego.

![Zadania wsadowe.](media/batch-jobs.png)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
