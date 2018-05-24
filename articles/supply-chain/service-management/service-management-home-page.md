---
title: "Zarządzanie serwisem"
description: "W module Zarządzanie serwisem można ustalić umowy serwisowe i subskrypcje serwisu, obsługiwać zlecenia serwisowe i zapytania odbiorców oraz analizować usługi świadczone klientom i zarządzać nimi."
author: YuyuScheller
manager: AnnBe
ms.date: 05/09/2018
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
ms.sourcegitcommit: 02cdf4615e2071f2b7de2e86b6f9e6637c6e5d8d
ms.openlocfilehash: 236ab21b2d1c5a4e82270e5381d163e97437cb7f
ms.contentlocale: pl-pl
ms.lasthandoff: 05/09/2018

---


# <a name="service-management"></a>Zarządzanie serwisem 

[!include [banner](../includes/banner.md)]


W module **Zarządzanie serwisem** można ustalić umowy serwisowe i subskrypcje serwisu, obsługiwać zlecenia serwisowe i zapytania odbiorców oraz analizować usługi świadczone klientom i zarządzać nimi. Umowy serwisowe służą do definiowania zasobów, które są używane w typowej wizycie serwisowej. Umowy serwisowe umożliwiają także wyświetlanie sposobu fakturowania tych zasobów do odbiorcy. Umowa serwisowa może również uwzględnić umowę dotyczącą poziomu usług, która określa standardowe czasy odpowiedzi i oferuje narzędzia do rejestrowania czasu rzeczywistego.

Można utworzyć zlecenia serwisowe, aby zarządzać informacjami o zaplanowanych lub niezaplanowanych wizytach technika serwisu w siedzibie klienta. Zlecenia serwisowe zawierają informacje, takie jak:

1.  Godziny pracy technika serwisu

2.  Typ usługi lub naprawy

3.  Element do naprawienia, w tym szczegóły dotyczące objawów i diagnozy

4.  Wszelkie wydatki i opłaty związane z usługą lub naprawą

Klienci mogą przesyłać żądania serwisowe za pośrednictwem Internetu przy użyciu witryny Enterprise Portal. Można odbierać, przetwarzać i wysyłać te żądania. Po utworzeniu zlecenia serwisowego, można używać etapów serwisu, aby monitorować postęp i określać reguły, które kontrolują, jakie akcje są włączone na każdym etapie. Po zakończeniu zlecenia serwisowego, wyrejestruj się na zamówieniu, aby potwierdzić, że jest zakończone, a następnie zaksięguj zamówienie w celu uruchomienia procesu fakturowania.

Użyj narzędzi raportowania, aby monitorować marże zleceń serwisowych i transakcji dotyczących subskrypcji oraz drukować opisy i pokwitowania pracy.

## <a name="business-processes"></a>Procesy biznesowe

Poniższy diagram ilustruje ogólne procesy biznesowe w module **Zarządzanie serwisem** oraz pokazuje, gdzie procesy serwisowe integrują się z innymi modułami w programie Microsoft Dynamics 365 for Finance and Operations.

[![Diagram procesów biznesowych w module Zarządzanie serwisem](./media/sm_home_page.gif)](./media/sm_home_page.gif)

## <a name="service-management-at-a-glance"></a>Zarządzanie usługami w skrócie

<table>
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Ważne zadania</p></th>
<th><p>Formularze podstawowe</p></th>
<th><p>Popularne raporty</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Realizacja umowy serwisowej</a></p></td>
<td><p><a href="https://technet.microsoft.com/en-us/library/aa617823(v=ax.60)">Umowy serwisowe (formularz)</a></p></td>
<td><p><strong>Marża zlecenia serwisowego</strong></p></td>
</tr>
<tr class="even">
<td><p>Obsługa zapytań odbiorców</a></p></td>
<td><p><a href="https://technet.microsoft.com/en-us/library/aa554361(v=ax.60)">Zlecenia serwisowe (formularz)</a></p></td>
<td><p><strong>Opis pracy</strong></p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p><a href="https://technet.microsoft.com/en-us/library/hh242789(v=ax.60)">Pulpit wysyłki (formularz)</a></p></td>
<td><p><strong>Transakcja — subskrypcja</strong></p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p></p></td>
<td><p><strong>Transakcje opłat subskrypcji</strong></p></td>
</tr>
</tbody>
</table>


## <a name="integration-of-service-management"></a>Integracja zarządzania usługami

Moduł Zarządzanie serwisem może być zintegrowany z następujących modułami w programie Microsoft Dynamics 365 for Finance and Operations:

  - [Sprzedaż i marketing](../sales-marketing/overview-sales-marketing.md)

  - [Zasoby ludzkie](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/index)

  


