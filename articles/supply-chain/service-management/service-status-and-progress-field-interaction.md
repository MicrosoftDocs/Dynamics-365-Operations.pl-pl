---
title: Stan usługi i interakcja pola postępu
description: W formularzu Zlecenia serwisowe pole Postęp znajdujące się w nagłówku odzwierciedla stan całego zlecenia serwisowego, a pole Stan prezentuje stany poszczególnych wierszy zlecenia serwisowego.
author: ShylaThompson
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2dd7b5160149a38dd62535901c1225bf704f404d
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1570793"
---
# <a name="service-status-and-progress-field-interaction"></a>Stan usługi i interakcja pola postępu 

[!include [banner](../includes/banner.md)]


W formularzu **Zlecenia serwisowe** pole **Postęp** znajdujące się w nagłówku zlecenia serwisowego odzwierciedla stan całego zlecenia serwisowego, a pole **Stan** prezentuje stany poszczególnych wierszy zlecenia serwisowego.

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Postęp</p></th>
<th><p>Stan wiersza 1</p></th>
<th><p>Stan wiersza 2</p></th>
<th><p>Stan wiersza 3</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>W toku</strong></p></td>
<td><p><strong>Utworzone</strong></p></td>
<td><p><strong>Utworzone</strong></p></td>
<td><p><strong>Utworzone</strong></p></td>
</tr>
<tr class="even">
<td><p><strong>W toku</strong></p></td>
<td><p><strong>Anulowane</strong></p></td>
<td><p><strong>Utworzone</strong></p></td>
<td><p><strong>Utworzone</strong></p></td>
</tr>
<tr class="odd">
<td><p><strong>W toku</strong></p></td>
<td><p><strong>Utworzone</strong></p></td>
<td><p><strong>Anulowane</strong></p></td>
<td><p><strong>Zaksięgowano</strong></p></td>
</tr>
<tr class="even">
<td><p><strong>Anulowane</strong></p></td>
<td><p><strong>Anulowane</strong></p></td>
<td><p><strong>Anulowane</strong></p></td>
<td><p><strong>Anulowane</strong></p></td>
</tr>
<tr class="odd">
<td><p><strong>Zaksięgowano</strong></p></td>
<td><p><strong>Zaksięgowano</strong></p></td>
<td><p><strong>Zaksięgowano</strong></p></td>
<td><p><strong>Zaksięgowano</strong></p></td>
</tr>
<tr class="even">
<td><p><strong>Zaksięgowano</strong></p></td>
<td><p><strong>Zaksięgowano</strong></p></td>
<td><p><strong>Anulowane</strong></p></td>
<td><p><strong>Anulowane</strong></p></td>
</tr>
</tbody>
</table>


Zlecenie serwisowe jest przetwarzane, jeśli wszystkie wiersze mają stan **Utworzono**. Nadal jest przetwarzane, jeśli niektóre wiersze mają stan **Anulowano** lub **Zaksięgowano**.

Jeśli wszystkie wiersze zlecenia serwisowego są oznaczone jako **Zaksięgowano**, postęp przetwarzania zlecenia serwisowego jest oznaczony jako **Zaksięgowano**. Jeśli niektóre wiersze są oznaczone jako **Zaksięgowano**, a inne jako **Anulowano**, postęp przetwarzania jest wciąż oznaczony jako **Zaksięgowano**.

  


