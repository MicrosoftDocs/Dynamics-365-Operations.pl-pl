---
title: Domyślne konta przeciwstawne dla arkuszy faktur od dostawców i zatwierdzania faktur
description: Ten artykuł pomoże określić miejsce przypisania domyślnych kont i transakcji przeciwstawnej dla arkuszy faktur.
author: abruer
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 62093
ms.assetid: 553933ca-928d-4031-bb8c-f9cff458320b
ms.search.region: global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fb351a1f3df54f74b3a0fc7ca2669f04f3f68301
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8889186"
---
# <a name="default-offset-accounts-for-vendor-invoice-and-invoice-approval-journals"></a>Domyślne konta przeciwstawne dla arkuszy faktur od dostawców i zatwierdzania faktur

[!include [banner](../includes/banner.md)]

Domyślne konta przeciwstawne są używane w następujących formularzach arkusza stron od dostawcy:

-   Arkusz faktur
-   Arkusz zatwierdzania faktur

Skorzystaj z poniższej tabeli, aby określić miejsce przypisania domyślnych kont i transakcji przeciwstawnej dla arkuszy faktur.

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th>Konfigurowanie domyślnych kont tutaj</th>
<th>Gdzie są dostarczane domyślne konta</th>
<th>Jak ta opcja wpływa na przetwarzanie</th>
<th>Kiedy należy używać tej opcji</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Grupa dostawców</strong> — pozwala ustawić domyślne konta przeciwstawne dla grup dostawców na stronie <strong>Ustawienia konta domyślnego</strong>, którą można otworzyć ze strony <strong>Grupy dostawców</strong>.</td>
<td><ul>
<li>Konto dostawcy</li>
<li>Zapisy arkuszy dla kont dostawców w grupie dostawców, jeśli domyślne konta nie zostały określone dla kont dostawców</li>
</ul></td>
<td>Domyślne konta przeciwstawne dla grup dostawców są pokazywane jako domyślne konta przeciwstawne dla dostawców na stronie <strong>Ustawienia konta domyślnego</strong>. Można otworzyć tę stronę ze strony listy <strong>Wszyscy dostawcy</strong>.</td>
<td>Zaznacz tę opcję, jeśli zwykle płacisz za te same typy towarów z tej samej grupy dostawców przez dłuższy czas.</td>
</tr>
<tr class="even">
<td><strong>Konto dostawcy</strong> — pozwala ustawić domyślne konta dostawcy na stronie <strong>Ustawienia konta domyślnego</strong>, którą można otworzyć ze strony <strong>Dostawcy</strong>.</td>
<td>Zapisy arkusza dla konta dostawcy</td>
<td>Domyślne konta przeciwstawne dla kont dostawców są wyświetlane jako domyślne konta przeciwstawne dla zapisów w arkuszu dla konta dostawcy.</td>
<td>Zaznacz tę opcję, jeśli zwykle płacisz za te same typy towarów od tych samych dostawców przez dłuższy czas.</td>
</tr>
<tr class="odd">
<td><strong>Nazwy arkuszy</strong> — pozwala ustawić domyśle konta przeciwstawne na stronie <strong>Nazwy arkuszy</strong>. Wybierz opcję <strong>Stałe konto przeciwstawne</strong>. Warto pamiętać, że nie można określić domyślnych kont przeciwstawnych dla nazwy arkusza, jeśli typem arkusza dla nazwy arkuszy jest <strong>Rejestr faktur</strong> lub <strong>Zatwierdzenie</strong>.</td>
<td><ul>
<li>Nagłówek arkusza, dla którego używana jest nazwa arkusza.</li>
<li>Zapisy w arkuszach w arkuszach używających nazwy arkusza</li>
</ul></td>
<td>Jeśli opcja <strong>Stałe konto przeciwstawne</strong> na stronie <strong>Nazwy arkuszy</strong> jest zaznaczona, konto przeciwstawne dla nazwy arkusza zastępuje domyślne konto przeciwstawne dla dostawcy lub grupy dostawców.</td>
<td>Ta opcja służy do konfigurowania arkuszy dla określonych kosztów i wydatków, które są naliczane dla określonych kont, niezależnie od dostawcy czy grupy dostawców, do której przynależy dostawca.</td>
</tr>
<tr class="even">
<td><strong>Nazwy arkuszy</strong> — pozwala ustawić domyśle konta przeciwstawne na stronie <strong>Nazwy arkuszy</strong>. Usuń zaznaczenie opcji <strong>Stałe konto przeciwstawne</strong>. Warto pamiętać, że nie można określić domyślnych kont przeciwstawnych dla nazwy arkusza, jeśli typem arkusza dla nazwy arkuszy jest <strong>Rejestr faktur</strong> lub <strong>Zatwierdzenie</strong>.</td>
<td><ul>
<li>Nagłówek arkusza</li>
<li>Zapisy w arkuszach w arkuszach używających nazwy arkusza</li>
</ul></td>
<td>Te wpisy domyślne są używane na stronach nagłówka arkusza, a konto przeciwstawne na stronie nagłówka arkusza jest używane jako domyślny wpis na stronach załącznika arkusza. Domyślne konta ze strony <strong>Nazwy arkuszy</strong> są używane tylko wtedy, gdy nie są ustawione domyślne konta dla konta dostawcy.</td>
<td>Ta opcja służy do konfigurowania domyślnych kont do użycia, gdy domyślne konto przeciwstawne dostawcy nie jest przypisane.</td>
</tr>
<tr class="odd">
<td><strong>Nagłówek arkusza</strong> — pozwala ustawić domyślne konto przeciwstawne dla arkusza, które będzie używane jako domyślny wpis na stronach załącznika arkusza. Warto pamiętać, że nie można określić domyślnych kont przeciwstawnych dla nagłówka arkusza, jeśli typem arkusza dla nazwy arkuszy jest <strong>Rejestr faktur</strong> lub <strong>Zatwierdzenie</strong>.</td>
<td>Zapisy arkusza w arkuszu</td>
<td>Domyślne konto przeciwstawne dla arkusza jest używane jako domyślny wpis na stronach załącznika arkusza.</td>
<td>Opcja ta pomaga przyspieszyć wprowadzanie danych, jeśli większość zapisów w arkuszu ma to samo konto przeciwstawne.</td>
</tr>
</tbody>
</table>







[!INCLUDE[footer-include](../../includes/footer-banner.md)]