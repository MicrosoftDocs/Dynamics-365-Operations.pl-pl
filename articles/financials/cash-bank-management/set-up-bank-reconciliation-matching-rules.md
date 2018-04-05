---
title: "Konfigurowanie reguł uzgadniania kont bankowych"
description: "W tym temacie objaśniono metody konfigurowania reguł uzgadniania wyciągów bankowych i zestawów tych reguł, aby ułatwić uzgadnianie konta bankowego. Reguły uzgadniania wyciągów bankowych są zbiorem kryteriów, które są używane do filtrowania wierszy wyciągu bankowego i dokumentów bankowych podczas procesu uzgadniania."
author: twheeloc
manager: AnnBe
ms.date: 10/27/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BankReconciliationMatchRule, BankReconciliationMatchRuleSet
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 12971
ms.assetid: b5073f83-31dc-404f-af42-3fd84a02a7c6
ms.search.region: Global
ms.author: leguo
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: b48accdc7aaaa65b4c620777546b20056038905b
ms.contentlocale: pl-pl
ms.lasthandoff: 03/26/2018

---

# <a name="set-up-bank-reconciliation-matching-rules"></a>Konfigurowanie reguł uzgadniania kont bankowych

[!include[banner](../includes/banner.md)]


W tym temacie objaśniono metody konfigurowania reguł uzgadniania wyciągów bankowych i zestawów tych reguł, aby ułatwić uzgadnianie konta bankowego. Reguły uzgadniania wyciągów bankowych są zbiorem kryteriów, które są używane do filtrowania wierszy wyciągu bankowego i dokumentów bankowych podczas procesu uzgadniania.

Można skonfigurować reguły uzgadniania wyciągów bankowych i zestawy tych reguł, aby ułatwić uzgadnianie konta bankowego. Reguły uzgadniania wyciągów to zestaw kryteriów, które są używane do filtrowania podczas procesu uzgadniania wierszy wyciągu bankowego z wierszami transakcji bankowych w programie Microsoft Dynamics 365 Finance and Operations. Użyj strony **reguł uzgadniania wyciągów** w celu ustawienia reguł uzgadniania. Można skonfigurować więcej niż jedną regułę uzgadniania, a następnie utworzyć zestaw reguł uzgadniania na stronie **Zestaw reguł uzgadniania wyciągów bankowych**. 

> [!NOTE] 
> Reguły uzgadniania wyciągów bankowych są używane w przypadku uzgadniania elektronicznego wyciągu bankowego za pomocą zaawansowanego uzgadniania konta bankowego. 

Na stronie **Reguły uzgadniania wyciągów bankowych** można wybrać akcje i kryteria wyboru używane po uruchomieniu reguły uzgadniania. W grupie pól **Akcje** wybierz akcję, która będzie wykonywana po uruchomieniu reguły uzgadniania podczas procesu uzgadniania.  

> [!NOTE] 
> Wybrana opcja określa wyświetlane pola.

|                                    |                                                                                                                                                                                                                                                                                                               |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
|------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Akcja**                         |                                                                                                                                                                                                                                                                                                               | **Kryteria wyboru dostępne po wybraniu akcji**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| **Połącz z dokumentem bankowym**       |  Umożliwia tworzenie kryteriów określania sposobu dopasowywania wierszy wyciągu bankowego i dokumentów bankowych, gdy reguła uzgadniania jest uruchamiana ze strony **Arkusz uzgadniania konta bankowego**. Wiersze transakcji są wybierane według dodatkowych kryteriów skonfigurowanych na skróconych kartach.                                | **Krok 1: Definiowanie reguły uzgadniania** — wybierz kryteria, aby określić, które wyciągi bankowe mają być dopasowane do transakcji bankowych w programie Finance and Operations. **Krok 2 (opcjonalnie): zaznacz wiersze wyciągu do uruchomienia reguły uzgadniania:** zastosuj filtr, aby określić wiersz, w którym mają zostać uruchomione reguły.                                                                                                                                                                                                                                                                                                               |
| **Wyczyść wycofane wiersze wyciągu** | Utwórz kryteria kryteriów sposobu określania usuwania wierszy wyciągu ze strony **Arkusz uzgadniania konta bankowego** po uruchomieniu reguły uzgadniania. Ta opcja jest używana, jeśli bank robi błąd i istnieją dwa wiersze wyciągu bankowego wymienione w zaimportowanym wyciągu bankowym, które muszą zostać uzgodnione. | **Krok 1**:**Znajdź wycofane wiersze wyciągu**— dodaj kryteria wyboru wierszy wyciągu bankowego do wycofania. Na przykład, aby zaznaczyć tylko czeki, wybierz opcję **Kod transakcji bankowej** w polu Pole, wybierz znak + w polu **Operator**, a następnie wprowadź **Czeki** w polu wartości. **Krok 2: Znajdź oryginalne wiersze wyciągu** — umożliwia dodanie kryteriów wyboru przy uzgadnianiu wierszy dokumentów bankowych z wierszami wyciągu bankowego. **Krok 3: Znajdź transakcje bankowe w programie Finance and Operations** — umożliwia dodanie kryteriów wyboru przy uzgadnianiu transakcji bankowych w programie Finance and Operations z wierszami wyciągu bankowego. |
| **Zaznacz nowe transakcje**          | Utwórz kryteria sposobu oznaczania nowych transakcji na stronie **Arkusz uzgadniania konta bankowego** po uruchomieniu reguły uzgadniania.                                                                                                                                                                 | **Krok 1: Znajdź wiersze wyciągu**— dodaj pola wyboru, aby określić, które wiersze wyciągu bankowego powinny zostać zaznaczone na stronie **Arkusz uzgadniania konta bankowego**. **Krok 2: Znajdź transakcje bankowe w programie Finance and Operations** — umożliwia dodawanie kryteriów wyboru do wyszukiwania wierszy dokumentu bankowego. Jeśli nie zostanie znaleziony żaden dokument bankowy, wiersz wyciągu będzie oznaczony jako nowa transakcja.                                                                                                                                                                                                                                             |

 







