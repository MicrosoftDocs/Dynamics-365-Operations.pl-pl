---
title: "Przepływy pracy dla zaopatrzenia i sourcingu"
description: "Niektóre organizacje wymagają, aby zapotrzebowania na zakup i zamówienia zakupu były zatwierdzane przez użytkowników innych niż osoby, która wprowadziły transakcję. Aby skonfigurować proces zatwierdzania, można utworzyć przepływ pracy."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WorkflowTableListPageRnr
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 2074
ms.assetid: e54a1d59-b9fb-421b-821d-01f32878aa9b
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28T00:00:00.000Z
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 67bdb8436ff379b0e55cfe1660597e8f93235eeb
ms.contentlocale: pl-pl
ms.lasthandoff: 05/25/2017

---

# <a name="procurement-and-sourcing-workflows"></a>Przepływy pracy dla zaopatrzenia i sourcingu

[!include[banner](../includes/banner.md)]


Niektóre organizacje wymagają, aby zapotrzebowania na zakup i zamówienia zakupu były zatwierdzane przez użytkowników innych niż osoby, która wprowadziły transakcję. Aby skonfigurować proces zatwierdzania, można utworzyć przepływ pracy.

Przepływ pracy reprezentuje proces biznesowy. Określa sposób przepływu dokumentu przez system i wskazuje osoby, które muszą zakończyć zadanie lub zatwierdzić dokument. Używanie systemu przepływu pracy w organizacji ma kilka zalet:
-   **Spójność procesów** — Możesz zdefiniować proces zatwierdzania określonych dokumentów, takich jak zapotrzebowania zakupu i raporty z wydatków. Używanie systemu przepływu pracy pomaga zapewnić, że dokumenty będą przetwarzane i zatwierdzane w spójny i wydajny sposób.
-   **Widoczność procesu** — Możesz śledzić stan, historię i miary wydajności określonego wystąpienia przepływu pracy. Pozwala to na określanie, czy zmiany powinny zostać wprowadzone do przepływu pracy w celu poprawienia wydajności.
-   **Scentralizowana Lista prac** — Na scentralizowanej liście prac użytkownicy mogą wyświetlać zadania i zatwierdzenia przepływów pracy przypisane im we wszystkich przepływach pracy, w których uczestniczą. Ta opcja jest dostępna na stronie Elementy pracy.

## <a name="the-types-of-workflows-that-you-can-create"></a> Dostępne typy przepływów pracy
Następujące typy przepływu pracy są dostępne w module Zaopatrzenie i sourcing.

|                                  |                                                               |
|----------------------------------|---------------------------------------------------------------|
| **Typ**                         | **Ten typ służy do następujących zadań**                                          |
| Przegląd zapotrzebowań na zakup      | Tworzenie przepływów pracy przeglądu zatwierdzania zapotrzebowań zakupu.            |
| Przegląd wiersza zapotrzebowania na zakup | Tworzenie przepływów pracy przeglądu wierszy zapotrzebowania zakupu.       |
| Przepływ pracy zamówienia zakupu          | Tworzenie przepływów pracy przeglądania i zatwierdzania dla zamówień zakupu.     |
| Przepływ pracy wiersza zamówienia zakupu     | Tworzenie przepływów pracy przeglądania i zatwierdzania dla wierszy zamówień zakupu. |

## <a name="creating-a-workflow"></a>Tworzenie przepływu pracy
Aby utworzyć przepływ pracy, kliknij kolejno opcje Zaopatrzenie i sourcing &gt; Ustawienia &gt; Przepływy pracy dla zaopatrzenia i sourcingu i utwórz nowy przepływ pracy poprzez wybranie typu przepływu pracy, który chcesz utworzyć.  

Na kanwie przepływu pracy możesz przeciągać elementy przepływu pracy do projektanta i łączyć elementy w sekwencje. Elementy przepływu pracy powinny być skonfigurowane. Dla elementów przepływu pracy zatwierdzania i zadań można skonfigurować, którzy uczestnicy powinni wykonywać czynności.
Typy uczestników
----------------------

Można przypisać krok zatwierdzania do następujących grup uczestników.

| Grupa użytkowników    | Opis                                                               |
|---------------|---------------------------------------------------------------------------|
| Uczestnik   | Przypisanie kroku zatwierdzania do członków grupy lub roli.                   |
| Hierarchia     | Przypisz krok zatwierdzania do użytkowników w określonej hierarchii organizacyjnej. |
| Użytkownik przepływu pracy | Przypisanie kroku zatwierdzania do użytkowników tego przepływu pracy.                       |
| Kolejka         | Przypisanie kroku zatwierdzania do kolejki etapów przepływu pracy.                            |
| Użytkownik          | Przypisanie kroku zatwierdzania do określonych użytkowników.                               |



<a name="see-also"></a>Informacje dodatkowe
--------

[Definiowanie przepływów pracy procesów biznesowych dla zapotrzebowań na zakup](https://mbs.microsoft.com/customersource/Global/AX/learning/documentation/white-papers/Defining_business_process_workflows_for_purchase_requisitions)

[Przepływ pracy zapotrzebowania na zakup](purchase-requisitions-workflow.md)




