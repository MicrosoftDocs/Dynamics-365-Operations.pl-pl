---
title: "Definiowanie uprawnień dostępu kontrolerów obiektów kosztów"
description: "Ten temat zawiera informacje o uprawnieniach dostępu kontrolerów obiektu kosztów."
author: YuyuScheller
manager: AnnBe
ms.date: 06/24/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CAMCostControlWorkspace, CAMParameters
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: YuyuScheller
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: 63160b9473c7f45b0eb0ca7139f9ed47c8e1446f
ms.openlocfilehash: 4d26d690e63898bfb463177da6654f1175ff35af
ms.contentlocale: pl-pl
ms.lasthandoff: 06/20/2017


---

## Prawa dostępu kontrolera obiektów kosztów
<a id="access-rights-of-a-cost-object-controller" class="xliff"></a>

[!include[banner](../includes/banner.md)]

Obszar roboczy **Kontrola kosztów** jest centralnym miejscem, w którym menedżerowie mogą wyświetlać działanie podlegających im obiektów ich kosztów. Ten obszar roboczy umożliwia menedżerom wykorzystywanie danych z modułu Rachunek kosztów, mimo iż sami nie są księgowymi kosztów. Ze względów bezpieczeństwa menedżerowie powinni móc wyświetlać tylko dane rachunku kosztów powiązane z konkretnymi obiektami kosztów, za które odpowiadają.

Istnieją cztery unikatowe role w module Rachunek kosztów.

| Nazwa roli               | Licencja      |
|-------------------------|--------------|
| Menedżer rachunku kosztów | Działanie     |
| Księgowy kosztów         | Operations   |
| Księgowy rachunku kosztów   | Operations   |
| Kontroler obiektów kosztów  | Członkowie zespołu |

W tym temacie wyjaśniono, jak przypisać rolę **Kontroler obiektów kosztów** do menedżera.

Gdy rola **Kontroler obiektów kosztów** jest przypisana do menedżera, menedżer może wykonywać następujące zadania:

- Dostęp do obszaru roboczego **Kontrola kosztów** (na urządzeniu klienckim).

    - Drążenie wskroś i prawo wyświetlania stron obsługujących funkcjonalność drążenia wskroś.

- Dostęp do obszaru roboczego **Kontrola kosztów** (w aplikacji komórkowej).

> [!NOTE]
> Rola **Kontroler obiektów kosztów** nie pozwala decydować, do których obiektów kosztów użytkownik ma dostęp i z których może wyświetlać dane. Zabezpieczenia na poziomie wiersza są dostarczane za pośrednictwem hierarchii wymiarów i hierarchii listy dostępu.

## Przyznawanie praw dostępu
<a id="grant-access-rights" class="xliff"></a>
W poniższym przykładzie pokazano, jak może wyglądać hierarchia wymiarów.

**Szczegóły hierarchii wymiarów**

| Nazwa hierarchii wymiarów | Wymiar    | Nazwa typu hierarchii wymiarów      | Hierarchia list dostępu |
|--------------------------|--------------|------------------------------------|-----------------------|
| Organizacja             | Centra kosztów | Hierarchia klasyfikacji wymiarów | **Tak**               |

Można użyć skróconej karty **Użytkownicy** w projektancie hierarchii w celu wstawienia jednego lub więcej identyfikatorów użytkowników w każdym węźle.

|                                   | Użytkownicy            | Zakresy elementów członkowskich wymiaru   |                         |
|-----------------------------------|------------------|---------------------------|-------------------------|
| **Węzły**                         | **Identyfikator użytkownika**      | **Element członkowskiego wymiaru źródłowego** | **Element członkowski wymiaru docelowego** |
| Organizacja                      | Benjamin, Claire |                           |                         |
| &nbsp;&nbsp;Administrator                 | kwiecień            |                           |                         |
| &nbsp;&nbsp;&nbsp;&nbsp;Finanse   | Alicia           | CC002                     | CC003                   |
|                                   |                  | CC007                     | CC007                   |
| &nbsp;&nbsp;&nbsp;&nbsp;Zasoby ludzkie        | Arnie            | CC001                     | CC001                   |
| &nbsp;&nbsp;Produkcja            | David            |                           |                         |
| &nbsp;&nbsp;&nbsp;&nbsp;Opakowanie | Ellen            | CC005                     | CC005                   |
| &nbsp;&nbsp;&nbsp;&nbsp;Zestaw  | Chris            | CC006                     | CC006                   |

> [!NOTE]
> Księgowi kosztów powinni być przypisani do najwyższego poziomu hierarchii, tak aby widzieli wszystkie wpisy w module Rachunek kosztów.

Aby można było zastosować hierarchię list dostępu i jej ustawienia zabezpieczeń, na karcie **Ogólne** na stronie **Parametrów rachunku kosztów** (**Rachunek kosztów** > **Ustawienia** > **Parametry**) w opcji **Włącz dostęp z prawem do wyświetlania elementów członkowskich wymiaru obiektu kosztów** musi być zaznaczona wartość **Tak**.

Ustawienia hierarchii list dostępu umożliwiają kontrolowanie danych, które są wyświetlane w następujących obszarach:

- Obszar roboczy **Kontrola kosztów** (na urządzeniu klienckim):

    - Dane na stronach używanych do drążenia wskroś

- Obszar roboczy **Kontrola kosztów** (w aplikacji komórkowej):

    - Salda na kartach

- Microsoft Power BI:

    - Dane wyświetlane w wizualizacjach programu Power BI
    - Wizualizacje danych z programu Power BI osadzone w aplikacji klienckiej Microsoft Dynamics 365 for Finance and Operations Enterprise Edition

> [!IMPORTANT]
> - Aby hierarchia list dostępu mogła wpływać na dane w programie Power BI, należy w tym programie sparować hierarchię list dostępu i zabezpieczenia na poziomie wiersza. Aby uzyskać więcej informacji, zobacz [Konfigurowanie zabezpieczeń pakietu zawartości Rachunek kosztów](/dynamics365/operations/dev-itpro/analytics/setup-security-cost-accounting-content-pack).
> - W tym temacie przedstawiono warunki wstępne, które muszą być spełnione, aby można było używać obszaru roboczego **Kontrola kosztów**.

Informacje dodatkowe

- [Obszar roboczy kontroli kosztów](cost-control-workspace.md)
- [Hierarchia wymiarów](dimension-hierarchy.md)
- [Konfigurowanie zabezpieczeń pakietu zawartości Rachunek kosztów](/dynamics365/operations/dev-itpro/analytics/setup-security-cost-accounting-content-pack)
