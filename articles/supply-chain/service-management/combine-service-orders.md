---
title: Łączenie zleceń serwisowych
description: Zlecenia serwisowe można łączyć.
author: sorenva
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
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f89c60561746ac9f1c2e9d611089bfac69089081
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/03/2022
ms.locfileid: "8676783"
---
# <a name="combine-service-orders"></a>Łączenie zleceń serwisowych   

[!include [banner](../includes/banner.md)]


Podczas tworzenia wierszy zlecenia serwisowego automatycznie w formularzu **Umowy serwisowe** można wybrać jedną z poniższych opcji, aby określić sposób ich grupowania:

  - **Według umowy serwisowej**

  - **Według zadania serwisowego**

  - **Według pracownika etatowego**

  - **Według przedmiotu serwisu**

## <a name="example"></a>Przykład

Tworzysz umowę serwisową o dacie rozpoczęcia 2007-03-31. W polu **Łączenie zleceń serwisowych** wybierasz opcję **Według przedmiotu serwisu**. Następnie zostaną utworzone następujące wiersze umowy serwisowej:

<table>
<colgroup>
<col />
<col />
<col />
<col />
<col />
<col />
</colgroup>
<thead>
<tr class="header">
<th><p>Numer wiersza umowy</p></th>
<th><p>Typ transakcji</p></th>
<th><p>opis</p></th>
<th><p>Zakres</p></th>
<th><p>Przedmiot serwisu</p></th>
<th><p>Rozpoczęcie</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1</p></td>
<td><p><strong>Godzina</strong></p></td>
<td><p>WUS1</p></td>
<td><p>Tygodniowa</p></td>
<td><p>X-1</p></td>
<td><p>2007-04-01</p></td>
</tr>
<tr class="even">
<td><p>2</p></td>
<td><p><strong>Godzina</strong></p></td>
<td><p>WUS2</p></td>
<td><p>Co dwa tygodnie</p></td>
<td><p>X-2</p></td>
<td><p>2007-04-01</p></td>
</tr>
<tr class="odd">
<td><p>3</p></td>
<td><p><strong>Godzina</strong></p></td>
<td><p>WUS3</p></td>
<td><p>Tygodniowa</p></td>
<td><p>X-2</p></td>
<td><p>2007-04-01</p></td>
</tr>
</tbody>
</table>


Okna czasu nie są określane dla żadnego z wierszy umowy serwisowej. Dlatego wiersze zlecenia serwisowego nie będą przenoszone z dnia, na który przypadają w wyniku obliczeń.

Następnie w formularzu **Utwórz zlecenia serwisowe** generujesz wiersze zlecenia serwisowego na okres od 2007-04-01 do 2007-04-30.

W sumie utworzono 10 zleceń serwisowych. Ponieważ wybrano łączone ustawienie **Według przedmiotu serwisu**, wiersze wszystkich utworzonych zleceń serwisowych mają określony tylko jeden przedmiot serwisu. Wiersze zlecenia serwisowego, które są generowane z umowy serwisowej i mają tę samą datę serwisu oraz przedmiot, są łączone w tym samym zleceniu serwisowym.


> [!NOTE]
> <P>W tym przykładzie kalendarz określony w formularzu <STRONG>Parametry modułu Zarządzanie serwisem</STRONG> nie zawiera zamkniętych dni.</P>



Dodatkowe grupowanie wierszy zlecenia serwisowego w zlecenia serwisowe zostanie wykonane zgodnie z oknami czasowymi określonymi w wierszach umowy serwisowej.

## <a name="see-also"></a>Informacje dodatkowe

[Automatyczne tworzenie zleceń serwisowych](create-service-orders-automatically.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]