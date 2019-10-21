---
title: Czeki postdatowane
description: Ten artykuł zawiera informacje o obsłudze czeków postdatowanych w Microsoft Dynamics 365 Finance. Czeki postdatowane są wystawiane do celów wykonywania i odbierania płatności w przyszłości. W związku z tym czeki można zrealizować dopiero od określonego dnia.
author: ShylaThompson
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendPostDatedChecks, CustPostDatedChecks
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 21741
ms.assetid: 4eb7c7da-1e6b-4d35-9f41-373b66103229
ms.search.region: Global
ms.author: leguo
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 38ee6c5b3d258c313a2066b388a83330bf696d39
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/27/2019
ms.locfileid: "2179430"
---
# <a name="postdated-checks"></a>Czeki postdatowane

[!include [banner](../includes/banner.md)]

Ten artykuł zawiera informacje o obsłudze czeków postdatowanych. Czeki postdatowane są wystawiane do celów wykonywania i odbierania płatności w przyszłości. W związku z tym czeki można zrealizować dopiero od określonego dnia.

Dynamics 365 Finance obsługuje pełny cykl zarządzania dla czeków postdatowanych w module Rozrachunki z odbiorcami i Rozrachunki z dostawcami, jak pokazano w poniższej tabeli.
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Scenariusz</th>
<th>Szczegóły</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Konfigurowanie czeków postdatowanych</td>
<td>Należy utworzyć nową metodę płatności oraz określić procedurę płatności umożliwiającą rozliczanie kont czeków wystawionych, czeków otrzymanych i potrąconej zaliczki na podatek.</td>
</tr>
<tr class="even">
<td>Rejestruje czek postdatowany dla dostawcy i księgowanie</td>
<td>Zapisujesz szczegóły czeku postdatowanego wystawionego dostawcy. Po zaksięgowaniu płatności zobowiązanie wobec dostawcy jest rozpoznawane, ale konto bankowe nie jest jeszcze uznawane. Zamiast tego jest używane konto rozliczeniowe. </td>
</tr>
<tr class="odd">
<td>Rejestrowanie i księgowanie czeku postdatowanego dla odbiorcy</td>
<td>Zapisujesz szczegóły czeku postdatowanego otrzymanego od odbiorcy. Po zaksięgowaniu płatności należność od odbiorcy jest księgowana po stronie kredytowej, ale konto bankowe nie jest jeszcze obciążane. Zamiast tego jest używane konto rozliczeniowe.</td>
</tr>
<tr class="even">
<td>Rejestrowanie i księgowanie zastępczego czeku postdatowanego dla dostawcy lub odbiorcy</td>
<td>
Jeśli oryginalny czek dla dostawcy lub odbiorcy został zniszczony lub utracony, można wystawić zastępczy czek postdatowany. Podczas rejestrowania szczegółów czeku podaj odwołanie do oryginalnego czeku oraz wskaż, że nowy czek zastępuje oryginał. Można również zaksięgować czek zastępczy.</td>
</tr>
<tr class="odd">
<td>Przenoszenie czeku postdatowanego odbiorcy do dostawcy</td>
<td>Po otrzymaniu czeku postdatowanego od odbiorcy można go przenieść do dostawcy jako płatność.</td>
</tr>
<tr class="even">
<td>Rozliczenia postdatowanego czeku dla odbiorcy lub dostawcy</td>
<td>Rozliczanie w dniu terminu płatności czeku postdatowanego, który został zaksięgowany na koncie pomostowym dla odbiorcy lub dostawcy. Po rozliczeniu czeku konto bankowe jest ostatecznie obciążane lub uznawane względem użytego wcześniej konta rozliczeniowego.</td>
</tr>
<tr class="odd">
<td>Anulowanie postdatowanego czeku dla dostawcy</td>
<td>Zaksięgowany czek postdatowany można anulować w następujących sytuacjach: - Czek jest zwracany przez bank.
- Czeku dotyczy błędna faktura.
- Dokonywana jest płatność gotówką względem czeku.
  </td>
  </tr>
  <tr class="even">
  <td>Zatrzymywanie płatności czeku postdatowanego</td>
  <td>Można zatrzymać zapłatę czeku postdatowanego wystawionego dostawcy, np. z powodu niewystarczających funduszy, zmiany warunków umowy z dostawcą, dostawy wadliwych towarów przez dostawcę lub zwrotu towarów do dostawcy. Zatrzymać można zapłatę tylko czeków nierozliczonych.</td>
  </tr>
  </tbody>
  </table>



Aby uzyskać więcej informacji, zobacz następujące tematy:

[Konfigurowanie czeków postdatowanych](tasks/set-up-postdated-checks.md)

[Rejestrowanie i księgowanie czeku postdatowanego dla odbiorcy](tasks/register-post-postdated-check-customer.md)

[Rozliczanie czeku postdatowanego od odbiorcy](tasks/settle-postdated-check-customer.md)

[Rejestrowanie i księgowanie czeku postdatowanego dla dostawcy](tasks/register-post-postdated-check-vendor.md) 

[Rozliczanie czeku postdatowanego dla dostawcy](tasks/settle-postdated-check-vendor.md)



