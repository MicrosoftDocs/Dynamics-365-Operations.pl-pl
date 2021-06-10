---
title: Zadanie stanowiska listy płac
description: Ten temat zawiera szczegółowe informacje i przykładowe zapytanie dotyczące jednostki Stanowisko pracy na liście płac w Dynamics 365 Human Resources.
author: jcart
ms.date: 04/07/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2021-04-07
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 62b9caf94f1c9aa8bb5758e62565fe57dfdd245a
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/18/2021
ms.locfileid: "6055035"
---
# <a name="payroll-position-job"></a>Zadanie stanowiska listy płac

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Ten temat zawiera szczegółowe informacje i przykładowe zapytanie dotyczące relacji jednostki Stanowisko pracy na liście płac w Dynamics 365 Human Resources.

## <a name="properties"></a>Właściwości

| Właściwość<br>**Nazwa fizyczna**<br>**_Typ_** | Użycie | opis |
| --- | --- | --- |
| **Identyfikator stanowiska**<br>mshr_jobid<br>*Ciąg* | Tylko do odczytu<br>Potrzebne |Identyfikator zadania. |
| **Data wejścia w życie**<br>mshr_validto<br>*Przesunięcie daty i godziny* | Tylko do odczytu <br>Potrzebne | Data, od której obowiązuje stanowisko i stosunek pracy. |
| **Data ważności**<br>mshr_validto<br>*Przesunięcie daty i godziny* | Tylko do odczytu <br>Potrzebne | Data obowiązywania stanowiska i stosunku pracy.  |
| **Identyfikator stanowiska**<br>mshr_positionid<br>*Ciąg* | Tylko do odczytu<br>Potrzebne | Identyfikator stanowiska. |
| **Pole główne**<br>mshr_primaryfield<br>*Ciąg* | Potrzebne<br>Wygenerowany przez system |  |
| **Wartość identyfikatora zadania stanowiska**<br>_mshr_fk_positionjob_id_value<br>*GUID* | Tylko do odczytu<br>Potrzebne<br>Klucz obcy: mshr_PayrollPositionJobEntity klucza mshr_payrollpositionjobentity |identyfikator stanowiska związany ze stanowiskiem.|
| **Wartość identyfikatora stałego planu wynagrodzeń**<br>_mshr_fk_fixedcompplan_id_value<br>*GUID* | Tylko do odczytu<br>Potrzebne<br>Klucz obcy: mshr_FixedCompPlan_id dla mshr_payrollfixedcompensationplanentity  | Identyfikator planu stałych wynagrodzeń powiązany ze stanowiskiem. |
| **Identyfikator jednostki stanowiska na liście płac**<br>mshr_payrollpositionjobentityid<br>*Guid* | Potrzebne<br>Wygenerowany przez system. | Wygenerowana przez system wartość identyfikatora GUID w celu unikatowego zidentyfikowania zadania.  |

