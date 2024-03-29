---
title: Prawa dostępu dla kontrolerów obiektów kosztów
description: Ten artykuł zawiera informacje o uprawnieniach dostępu kontrolerów obiektu kosztów.
author: AndersGirke
ms.date: 06/24/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CAMCostControlWorkspace, CAMParameters
audience: Application User
ms.reviewer: twheeloc
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: twheeloc
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: c40be758c5e5d1d1fb025630ed8321ae46251892
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8903197"
---
# <a name="access-rights-for-cost-object-controllers"></a>Prawa dostępu dla kontrolerów obiektów kosztów

[!include [banner](../includes/banner.md)]

Obszar roboczy **Kontrola kosztów** jest centralnym miejscem, w którym menedżerowie mogą wyświetlać działanie podlegających im obiektów ich kosztów. Ten obszar roboczy umożliwia menedżerom wykorzystywanie danych z modułu Rachunek kosztów, mimo iż sami nie są księgowymi kosztów. Ze względów bezpieczeństwa menedżerowie powinni móc wyświetlać tylko dane rachunku kosztów powiązane z konkretnymi obiektami kosztów, za które odpowiadają.

Istnieją cztery unikatowe role w module Rachunek kosztów.

| Nazwa roli               | Licencja      |
|-------------------------|--------------|
| Menedżer rachunku kosztów | Działanie     |
| Księgowy kosztów         | Operations   |
| Pracownik księgowy kosztów   | Działania operacyjne   |
| Kontroler obiektów kosztów  | Członkowie zespołu |

W tym artykule wyjaśniono, jak przypisać rolę **Kontroler obiektów kosztów** do menedżera.

Gdy rola **Kontroler obiektów kosztów** jest przypisana do menedżera, menedżer może wykonywać następujące zadania:

- Dostęp do obszaru roboczego **Kontrola kosztów** (na urządzeniu klienckim).

    - Drążenie wskroś i prawo wyświetlania stron obsługujących funkcjonalność drążenia wskroś.

- Dostęp do obszaru roboczego **Kontrola kosztów** (w aplikacji komórkowej).

> [!NOTE]
> Rola **Kontroler obiektów kosztów** nie pozwala decydować, do których obiektów kosztów użytkownik ma dostęp i z których może wyświetlać dane. Zabezpieczenia na poziomie wiersza są dostarczane za pośrednictwem hierarchii wymiarów i hierarchii listy dostępu.

## <a name="grant-access-rights"></a>Przyznawanie praw dostępu
W poniższym przykładzie pokazano, jak może wyglądać hierarchia wymiarów.

**Szczegóły hierarchii wymiarów**

| Nazwa hierarchii wymiarów | Wymiar    | Nazwa typu hierarchii wymiarów      | Hierarchia list dostępu |
|--------------------------|--------------|------------------------------------|-----------------------|
| Organizacja             | Centra kosztów | Hierarchia klasyfikacji wymiarów | **Tak**               |

Można użyć skróconej karty **Użytkownicy** w projektancie hierarchii w celu wstawienia jednego lub więcej identyfikatorów użytkowników w każdym węźle.

|             Węzły                 | Użytkownicy            | Element członkowski wymiaru początkowego     |   Element członkowski wymiaru docelowego   |
|-----------------------------------|------------------|---------------------------|-------------------------|
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
    - Wizualizacje danych w rozwiązaniu Power BI osadzone w kliencie Dynamics 365 Finance

> [!IMPORTANT]
> - Aby hierarchia list dostępu mogła wpływać na dane w programie Power BI, należy w tym programie sparować hierarchię list dostępu i zabezpieczenia na poziomie wiersza w programie Power BI. Aby uzyskać więcej informacji, zobacz [Konfigurowanie zabezpieczeń pakietu zawartości Rachunek kosztów](../../fin-ops-core/dev-itpro/analytics/setup-security-cost-accounting-content-pack.md).
> - W tym artykule przedstawiono warunki wstępne, które muszą być spełnione, aby można było używać obszaru roboczego **Kontrola kosztów**.

Dodatkowe zasoby

- [Obszar roboczy Kontrola kosztów](cost-control-workspace.md)
- [Hierarchia wymiarów](dimension-hierarchy.md)
- [Konfigurowanie zabezpieczeń pakietu zawartości Rachunek kosztów](../../fin-ops-core/dev-itpro/analytics/setup-security-cost-accounting-content-pack.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
