---
title: Ustawianie przepływów pracy dla wydatków
description: Można ustawić proces przepływu pracy, który jest używany do sprawdzania i zatwierdzania dokumentów dotyczących podróży i wydatków.
author: ShylaThompson
manager: AnnBe
ms.date: 09/13/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WorkflowtableListPageRnr
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 86cadf7277fbb7e08dad4b5dc2a46e1c6ce5a888
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/01/2019
ms.locfileid: "1840968"
---
# <a name="set-up-workflows-for-expense"></a>Ustawianie przepływów pracy dla wydatków

[!include [banner](../includes/banner.md)]

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

