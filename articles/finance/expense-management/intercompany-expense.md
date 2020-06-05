---
title: Wydatki międzyfirmowe
description: Pracownik zatrudniony przez jedną firmę w organizacji może wykonywać pracę dla innej firmy w tej samej organizacji. W takiej sytuacji można użyć funkcji wydatków międzyfirmowych w celu przypisania wydatków pracownika do firmy, dla której wykonano pracę.
author: ShylaThompson
manager: AnnBe
ms.date: 05/20/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TrvParameters
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0967f23e4e1f8e0431c55d4d54554e7e90e2451c
ms.sourcegitcommit: 07e425707eb20730f10246a27799f4deeef93f97
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/21/2020
ms.locfileid: "3390891"
---
# <a name="intercompany-expenses"></a>Wydatki międzyfirmowe

[!include [banner](../includes/banner.md)]

Pracownik zatrudniony przez jedną firmę w organizacji może wykonywać pracę dla innej firmy w tej samej organizacji. W takiej sytuacji można użyć funkcji wydatków międzyfirmowych w celu przypisania wydatków pracownika do firmy, dla której wykonano pracę. Firma zatrudniająca pracownika nosi nazwę firmy wypożyczającej. Firma, dla której pracownik ponosi wydatki nosi nazwę firmy pożyczającej. 

Zanim pracownik będzie mógł utworzyć i przesłać wydatki za pracę wykonaną dla różnych firm, w firmie wypożyczającej, na stronie **Parametry zarządzania wydatkami** wybierz opcję **Zezwalaj na wiersze wydatków międzyfirmowych**. 

## <a name="tax-posting-for-intercompany-expenses"></a>Księgowanie podatku dla wydatków międzyfirmowych

[!include [banner](../includes/banner.md)]

Jeśli w raporcie wydatków mają być używane grupy podatków skojarzone z firmą wypożyczającą (źródłową), a nie firmą pożyczającą (docelową), należy skonfigurować tę opcję w konfiguracji podatku w księdze głównej. Jeśli parametr księgi głównej **Firma do księgowania podatku międzyfirmowego** ma ustawioną wartość **Źródło**, a opcja **Zastosuj zasady opodatkowania dla podatku** została ustawiona na wartość **Nie**, zostanie użyta kombinacja podatków dla firmy wypożyczającej. Jeśli ten sam parametr jest ustawiony na **Cel**, zostanie użyta kombinacja podatku dla firmy pożyczającej. W przypadku firm w Stanach Zjednoczonych, gdy parametr jest ustawiony jako **Źródło**, pole **Podatek naliczony** musi również zostać skonfigurowane na nowej stronie **Grupy księgowania**. Aparat księgowania będzie używać informacji z tego pola dla wpisu księgowego związanego z podatkiem.   
Zachowanie jest spójne z wierszami wydatków zaksięgowanymi z projektem lub bez niego.  
