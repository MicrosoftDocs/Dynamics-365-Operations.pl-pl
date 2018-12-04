---
title: Naliczanie subskrypcji
description: "W przypadku subskrypcji serwisu należy ręcznie naliczać przychód w okresach następujących po dacie zafakturowania transakcji opłaty."
author: ShylaThompson
manager: AnnBe
ms.date: 04/30/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMASubscriptionGroup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: acbf7432c9487cbefaf24a2a98772c8f0ec7ffe6
ms.contentlocale: pl-pl
ms.lasthandoff: 05/08/2018

---

# <a name="accruing-subscriptions"></a>Naliczanie subskrypcji 

[!include [banner](../includes/banner.md)]


W przypadku subskrypcji serwisu należy ręcznie naliczać przychód w okresach następujących po dacie zafakturowania transakcji opłaty.

Okresy naliczania są tworzone dla okresu fakturowania skonfigurowanego dla opłaty subskrypcji i są oparte na kodzie okresu subskrypcji.

Można naliczyć przychód i można też wycofać naliczony przychód.

## <a name="reverse-accruals-of-credit-amounts"></a>Stornowanie naliczeń kwot uznań

Jeśli zapiszesz zafakturowane kwoty subskrypcji po stronie kredytowej (uznasz je), można użyć dwóch metod do wycofania naliczonych kwot:

  - Każdą transakcję naliczenia przychodu można wycofać indywidualnie przed utworzeniem propozycji faktury korygującej dla transakcji. To jest metoda ręczna. (ręcznie)

  - Naliczone kwoty można wycofać na dzień zaksięgowania faktury korygującej lub na pierwotny dzień zaksięgowania naliczenia.

Aby uzyskać więcej informacji, zobacz temat [Parametry subskrypcji (formularz)](https://technet.microsoft.com/en-us/library/aa619615.aspx).

## <a name="setup-requirements"></a>Skonfiguruj wymagania

Aby można było naliczać przychód, muszą być spełnione następujące wymagania dotyczące danych:

## <a name="account-setup"></a>Konfiguracja kont

Konta **PWT — subskrypcja** i **Naliczony przychód — subskrypcja** muszą być skonfigurowane w module **Projekt**.

Podczas księgowania naliczonego przychodu naliczona kwota jest księgowana po stronie debetowej konta **PWT — subskrypcja** i po stronie kredytowej konta **Naliczony przychód — subskrypcja**.

## <a name="set-up-accounts-for-accrual-of-subscription-revenue"></a>Konfigurowanie kont służących do naliczania przychodu subskrypcji

1.  Kliknij kolejno opcje **Zarządzanie projektami i ich księgowanie** \> **Ustawienia** \> **Księgowanie** \> **Konfiguracja księgowania**.

2.  Kliknij kartę **Konta przychodów**, a następnie wybierz opcję **PWT — subskrypcja** lub **Naliczony przychód — subskrypcja** i skonfiguruj konta.

## <a name="subscription-group-setup"></a>Konfiguracja grupy subskrypcji

Aby można było naliczać przychody z subskrypcji, musi być zaznaczone pole wyboru **Nalicz przychód**. Znajduje się ono w formularzu **Grupy subskrypcji** dla grupy dołączonej do subskrypcji. Kliknij kolejno opcje **Zarządzanie serwisem** \> **Ustawienia** \> **Subskrypcje serwisowe** \> **Grupy subskrypcji**.

## <a name="enable-revenue-accrual-on-a-subscription-group"></a>Włączanie naliczania przychodu w grupie subskrypcji

1.  Kliknij kolejno opcje **Zarządzanie serwisem** \> **Ustawienia** \> **Subskrypcje serwisowe** \> **Grupy subskrypcji**.

## <a name="periods"></a>Okresy

Trzeba skonfigurować kod okresu fakturowania. Należy również skonfigurować okres naliczania, chyba że przychód ma być naliczany w tych samych przedziałach czasowych, jak używane dla fakturowania.

W następującej tabeli pokazano, które okresy naliczania można skonfigurować w poszczególnych okresach fakturowania:

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Okres fakturowania</p></th>
<th><p>Okres naliczania</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Lata</strong></p></td>
<td><ul>
<li><p><strong>Lata</strong></p></li>
<li><p><strong>Kwartał</strong></p></li>
<li><p><strong>Miesiąc</strong></p></li>
<li><p><strong>Dzień</strong></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Kwartał</strong></p></td>
<td><ul>
<li><p><strong>Kwartał</strong></p></li>
<li><p><strong>Miesiąc</strong></p></li>
<li><p><strong>Dzień</strong></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Miesiąc</strong></p></td>
<td><ul>
<li><p><strong>Miesiąc</strong></p></li>
<li><p><strong>Dzień</strong></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Tydzień</strong></p></td>
<td><ul>
<li><p><strong>Dzień</strong></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Dzień</strong></p></td>
<td><ul>
<li><p><strong>Dzień</strong></p></li>
</ul></td>
</tr>
</tbody>
</table>

Skonfigurowanie okresu fakturowania jest obowiązkowym elementem całościowej konfiguracji grupy subskrypcji. Można zdecydować, czy chcesz również ustawić okres naliczania dla grupy subskrypcji. W przypadku skonfigurowania okresu naliczania dla grupy subskrypcji okres ten będzie sugerowany w polu **Kod okresu**. To pole znajduje się w formularzu **Naliczanie przychodu z subskrypcji** podczas naliczania przychodu z subskrypcji. Jednak okres naliczania jest opcjonalnym ustawieniem konfiguracji dla grupy subskrypcji.


> [!NOTE]
> <P>Aby otworzyć formularz <STRONG>Naliczanie przychodu z subskrypcji</STRONG>, użyj następującej ścieżki. Kliknij kolejno opcje <STRONG>Zarządzanie serwisem</STRONG> &gt; <STRONG>Okresowe</STRONG> &gt; <STRONG>Subskrypcje serwisowe</STRONG> &gt; <STRONG>Naliczanie przychodu z subskrypcji</STRONG>.</P>


## <a name="transactions"></a>Transakcje

Można określić liczbę transakcji finansowych, które będą tworzone podczas księgowania naliczonego przychodu. W subskrypcjach określ, czy transakcje finansowe mają tworzone jako sumy czy dla poszczególnych wierszy.

## <a name="specify-the-level-of-posting-details-to-display-for-accrued-transactions"></a>Określanie poziomu szczegółów dotyczących księgowania, które mają być wyświetlane dla naliczonych transakcji

1.  Kliknij kolejno opcje **Zarządzanie projektami i ich księgowanie** \> **Ustawienia** \> **Parametry modułu Zarządzanie projektami i ich księgowanie**.

2.  Na karcie **Finanse** w polu **Faktura** zaznacz opcję **Suma** lub **Wiersz**.


## <a name="see-also"></a>Informacje dodatkowe

[Nalicz przychód subskrypcji](accrue-subscription-revenue.md)

  



