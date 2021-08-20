---
title: Stan usługi i interakcja pola postępu
description: W formularzu Zlecenia serwisowe pole Postęp znajdujące się w nagłówku odzwierciedla stan całego zlecenia serwisowego, a pole Stan prezentuje stany poszczególnych wierszy zlecenia serwisowego.
author: ShylaThompson
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 210ff82a904e9657d9808a0994c70683e9126622d279aae94e946be0c4f484c1
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6756059"
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

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]