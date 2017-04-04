---
title: Czeki postdatowane
description: "Ten artykuł zawiera informacje na temat pomocy technicznej dla czeków postdatowanych w usłudze Microsoft Dynamics 365 dla operacji. Czeki postdatowane są wystawiane do celów wykonywania i odbierania płatności w przyszłości. W związku z tym czeki można zrealizować dopiero od określonego dnia."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 21741
ms.assetid: 4eb7c7da-1e6b-4d35-9f41-373b66103229
ms.search.region: Global
ms.author: leguo
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 4bb647cfd3f012efbffa93a81462c538a24ac850
ms.openlocfilehash: 7349771b7f9a1ad4cd5b239f1d10bd3229d2d0df
ms.lasthandoff: 03/31/2017


---

# <a name="postdated-checks"></a>Czeki postdatowane

Ten artykuł zawiera informacje na temat pomocy technicznej dla czeków postdatowanych w usłudze Microsoft Dynamics 365 dla operacji. Czeki postdatowane są wystawiane do celów wykonywania i odbierania płatności w przyszłości. W związku z tym czeki można zrealizować dopiero od określonego dnia.

Microsoft Dynamics 365 dla operacji obsługuje cyklu pełnego zarządzania dla czeków postdatowanych w rozrachunkach z odbiorcami i rozrachunkach z dostawcami, jak pokazano w poniższej tabeli.
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
<td>Zapisujesz szczegóły czeku postdatowanego wystawionego dostawcy. Po zaksięgowaniu płatności zobowiązań dostawcy został rozpoznany, ale nie jest jeszcze kredytowe konta bankowego. Zamiast tego jest używane konto rozliczeniowe.</td>
</tr>
<tr class="odd">
<td>Rejestrowanie i księgowanie czeku postdatowanego dla odbiorcy</td>
<td>Zapisujesz szczegóły czeku postdatowanego otrzymanego od odbiorcy. Po zaksięgowaniu płatności odbiorcy z odbiorcami jest kredytu, ale nie jest jeszcze po stronie debetowej konta bankowego. Zamiast tego jest używane konto rozliczeniowe.</td>
</tr>
<tr class="even">
<td>Rejestrowanie i księgowanie wyboru zastępczy czek postdatowany dla odbiorcy lub dostawcy</td>
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
<td>Można anulować zaksięgowanych czeków postdatowanych w następujących sytuacjach:-kontrola jest zwracany przez bank.
-Sprawdzanie jest rozliczana z fakturą niepoprawne.
-Środków pieniężnych płatności przed czeku.
</td>
</tr>
<tr class="even">
<td>Zatrzymanie płatności dla czeków postdatowanych</td>
<td>Można zatrzymać zapłatę czeku postdatowanego wystawionego dostawcy, np. z powodu niewystarczających funduszy, zmiany warunków umowy z dostawcą, dostawy wadliwych towarów przez dostawcę lub zwrotu towarów do dostawcy. Możesz zatrzymać wypłatę tylko na kontrole, które nie zostały jeszcze rozliczone.</td>
</tr>
</tbody>
</table>





