---
title: "Stan usługi i interakcja pola postępu"
description: "W formularzu Zlecenia serwisowe pole Postęp znajdujące się w nagłówku odzwierciedla stan całego zlecenia serwisowego, a pole Stan prezentuje stany poszczególnych wierszy zlecenia serwisowego."
author: YuyuScheller
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: YuyuScheller
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 51ef39266e8de00488954918568d00a297a9b50a
ms.contentlocale: pl-pl
ms.lasthandoff: 05/08/2018

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

  



