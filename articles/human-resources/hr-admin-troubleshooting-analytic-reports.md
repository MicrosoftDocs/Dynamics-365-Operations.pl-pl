---
title: Rozwiązywanie problemów z raportami analitycznymi
description: W tym artykule wyjaśniono, co należy zrobić, gdy zmiany w danych klienta nie pojawiają się w żadnych jego obszarach roboczych.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 8dab12213e9730e72aede70c5b5d1368ef77664e
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/18/2021
ms.locfileid: "6053546"
---
# <a name="troubleshoot-analytic-reports"></a>Rozwiązywanie problemów z raportami analitycznymi

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

![Zadania wsadowe](media/batch-jobs.png)


[!INCLUDE[footer-include](../includes/footer-banner.md)]