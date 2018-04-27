---
title: "Ustawianie przepływów pracy dla wydatków"
description: "Można ustawić proces przepływu pracy, który jest używany do sprawdzania i zatwierdzania dokumentów dotyczących podróży i wydatków."
author: saraschi2
manager: AnnBe
ms.date: 09/13/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WorkflowtableListPageRnr
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom:
- month/year of release that feature was introduced in
- in format yyyy-mm-dd
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: cf35406b43c1ec40a7c248b970559b65fcd8a6c6
ms.contentlocale: pl-pl
ms.lasthandoff: 04/13/2018

---

# <a name="set-up-workflows-for-expense"></a>Ustawianie przepływów pracy dla wydatków

[!INCLUDE [banner](../includes/banner.md)]

 Można ustawić proces przepływu pracy, który jest używany do sprawdzania i zatwierdzania dokumentów dotyczących podróży i wydatków. Dokumenty, dla których można zdefiniować przepływy pracy obejmują raporty z wydatków, wnioski wyjazdowe i wnioski o zaliczkę gotówkową.

Przepływ pracy reprezentuje proces biznesowy. Określa sposób przepływu dokumentu przez system i wskazuje osoby, które muszą zakończyć zadanie lub zatwierdzić dokument. Używanie systemu przepływu pracy w organizacji ma kilka zalet:

-   **Spójność procesów** — Możesz zdefiniować proces zatwierdzania określonych dokumentów, takich jak zapotrzebowania zakupu i raporty z wydatków. Używanie systemu przepływu pracy pomaga zapewnić, że dokumenty będą przetwarzane i zatwierdzane w spójny i wydajny sposób.

-   Widoczność procesu — Możesz śledzić stan, historię i miary wydajności określonego wystąpienia przepływu pracy. Pozwala to na określanie, czy zmiany powinny zostać wprowadzone do przepływu pracy w celu poprawienia wydajności.

-   Scentralizowana lista prac — Użytkownicy mogą wyświetlić scentralizowaną listę prac, aby przeglądać przypisane do nich zadania i zatwierdzenia przepływu pracy. 

**Dostępne typy przepływów pracy**

W poniższej tabeli wymieniono typy przepływów pracy, które można tworzyć w module **Wydatek**.


|              <strong>Typ</strong>              |                   <strong>Ten typ służy do następujących zadań</strong>                   |
|-------------------------------------------------|-----------------------------------------------------------------------|
|         <strong>Raport o wydatkach</strong>         |            Utwórz przepływy pracy zatwierdzania dla raportu z wydatków.             |
|  <strong>Automatyczne księgowani raportu wydatków</strong>   |        Utwórz przepływy pracy automatycznego księgowania w raportach z wydatków.        |
|       <strong>Pozycja w wierszu wydatku</strong>        |     Utwórz przepływy pracy zatwierdzania dla pozycji w wierszu w raportach z wydatków.      |
| <strong>Automatyczne księgowanie pozycji wiersza wydatków</strong> | Utwórz przepływy pracy automatycznego księgowania dla pozycji w wierszu w raportach z wydatków. |
|       <strong>Wniosek wyjazdowy</strong>       |          Utwórz przepływy pracy zatwierdzania dla wniosków wyjazdowych.           |
|      <strong>Wniosek o zaliczkę gotówkową</strong>      |         Utwórz przepływy pracy zatwierdzania wniosków o zaliczkę gotówkową.          |
|        <strong>Zwrot podatku VAT</strong>        | Utwórz przepływy pracy zatwierdzania dla podatku od wartości dodanej (VAT).  |


