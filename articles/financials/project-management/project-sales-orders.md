---
title: Zamówienia sprzedaży dla projektu
description: W tym temacie opisano, jak tworzyć zamówienia sprzedaży na podstawie projektu dla projektów typu Czas i materiały.
author: KimANelson
manager: AnnBe
ms.date: 04/05/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2019-04-05
ms.dyn365.ops.version: AX 10.0.2
ms.openlocfilehash: 1d54c98a08dc7cccb5cafbbe401d0ce25a276c25
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/07/2019
ms.locfileid: "1529909"
---
# <a name="project-sales-orders-for-time-and-material-projects"></a>Zamówienia sprzedaży dla projektu dla projektów typu czas i materiały

[!include[banner](../includes/banner.md)]
[!include[banner](../includes/preview-banner.md)]

W tym temacie opisano sposób tworzenia zamówień sprzedaży dla projektu. Zamówienia sprzedaży można tworzyć tylko dla projektów typu **Czas i materiały**.

Jeśli projekt typu czas i materiały ma wiele źródeł finansowania w umowie dot. projektu, należy włączyć parametr **Zezwalaj na zamówienia sprzedaży w projektach z wieloma źródłami finansowania** na stronie **Parametry modułu Zarządzanie projektami i ich księgowanie**. 

> [!NOTE]
> - Obsługa zamówień sprzedaży dla projektu z wieloma źródłami finansowania jest dostępna w wersji 10.0.2 aplikacji i nowszych.
> - Parametr umożliwiający obsługę zamówień sprzedaży dla projektu z wieloma źródłami finansowania zostanie usunięty w wersji planowanej na kwiecień 2020 r., a po tym czasie funkcja będzie zawsze włączona.

Zamówienia sprzedaży na podstawie projektu można utworzyć na dwa sposoby:

- Z samego projektu. W okienku akcji wybierz **Zarządzaj > Zadania dotyczące pozycji > Zamówienie sprzedaży**. Informacje o projekcie zostaną domyślnie przypisane do zamówienia sprzedaży z projektu. Jeśli umowa dotycząca projektu ma więcej niż jedno źródło finansowania, należy wybrać źródło finansowania w celu ustawiania odbiorcy dla zamówienia sprzedaży. Jeśli występuje tylko jedno źródło finansowania projektu, odbiorca zostanie automatycznie ustawiony.
- Przejdź do strony listy **Wszystkie zamówienia sprzedaży** i utwórz nowe zamówienie sprzedaży. Należy wybrać projekt dla zamówienia sprzedaży. Po wybraniu projektu, odbiorca zostanie ustawiony na podstawie źródła finansowania lub trzeba będzie wybrać źródło finansowania, jeśli umowa dotycząca projektu ma wiele źródeł finansowania.

