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
audience: Application User
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi2
ms.search.validFrom:
- month/year of release that feature was introduced in
- in format yyyy-mm-dd
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: eb8ff11a03ba18b78595cd04f63b2456aec53bf2
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---

# <a name="set-up-workflows-for-expense"></a>Ustawianie przepływów pracy dla wydatków

[!include[banner](../includes/banner.md)] Można ustawić proces przepływu pracy, który jest używany do sprawdzania i zatwierdzania dokumentów dotyczących podróży i wydatków. Dokumenty, dla których można zdefiniować przepływy pracy obejmują raporty z wydatków, wnioski wyjazdowe i wnioski o zaliczkę gotówkową.

Przepływ pracy reprezentuje proces biznesowy. Określa sposób przepływu dokumentu przez system i wskazuje osoby, które muszą zakończyć zadanie lub zatwierdzić dokument. Używanie systemu przepływu pracy w organizacji ma kilka zalet:

-   **Spójność procesów** — Możesz zdefiniować proces zatwierdzania określonych dokumentów, takich jak zapotrzebowania zakupu i raporty z wydatków. Używanie systemu przepływu pracy pomaga zapewnić, że dokumenty będą przetwarzane i zatwierdzane w spójny i wydajny sposób.

-   Widoczność procesu — Możesz śledzić stan, historię i miary wydajności określonego wystąpienia przepływu pracy. Pozwala to na określanie, czy zmiany powinny zostać wprowadzone do przepływu pracy w celu poprawienia wydajności.

-   Scentralizowana lista prac — Użytkownicy mogą wyświetlić scentralizowaną listę prac, aby przeglądać przypisane do nich zadania i zatwierdzenia przepływu pracy. 

**Dostępne typy przepływów pracy**

W poniższej tabeli wymieniono typy przepływów pracy, które można tworzyć w module **Wydatek**.

| **Typ**                           | **Ten typ służy do następujących zadań**                                                 |     
|------------------------------------|----------------------------------------------------------------------|
| **Raport o wydatkach**                 | Utwórz przepływy pracy zatwierdzania dla raportu z wydatków.                       |      
| **Automatyczne księgowani raportu wydatków**    | Utwórz przepływy pracy automatycznego księgowania w raportach z wydatków.              |     
| **Pozycja w wierszu wydatku**              | Utwórz przepływy pracy zatwierdzania dla pozycji w wierszu w raportach z wydatków.         |     
| **Automatyczne księgowanie pozycji wiersza wydatków** | Utwórz przepływy pracy automatycznego księgowania dla pozycji w wierszu w raportach z wydatków.|
| **Wniosek wyjazdowy**             | Utwórz przepływy pracy zatwierdzania dla wniosków wyjazdowych.                   |    
| **Wniosek o zaliczkę gotówkową**           | Utwórz przepływy pracy zatwierdzania wniosków o zaliczkę gotówkową.                 |     
| **Zwrot podatku VAT**               | Utwórz przepływy pracy zatwierdzania dla podatku od wartości dodanej (VAT). |       

