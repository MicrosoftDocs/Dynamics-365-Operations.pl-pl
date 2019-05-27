---
title: Uzgadnianie frachtu w module Zarządzanie transportem
description: W tym artykule opisano proces uzgadniania frachtu.
author: MarkusFogelberg
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSAuditMaster, TMSFreightBillInvoiceReconcile, TMSFreightBillSummary, TMSFreightBillType, TMSFreightMatchReason, TMSInvoiceTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 89983
ms.assetid: bc34a9b1-0c11-4797-b463-25409cf98ca8
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1f92808f904ba93513e20b74bd2b597712cb93d4
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1560939"
---
# <a name="reconcile-freight-in-transportation-management"></a>Uzgadnianie frachtu w module Zarządzanie transportem

[!include [banner](../includes/banner.md)]

W tym artykule opisano proces uzgadniania frachtu.

Uzgadnianie frachtu można wykonać ręcznie lub skonfigurować jego wykonywanie automatyczne. Aby używać automatycznego uzgadnianie frachtu, należy skonfigurować główną inspekcję, gdzie można zdefiniować kryteria określające, które listy frachtowe mają być uzgadniane automatycznie.

## <a name="the-freight-reconciliation-process"></a>Proces uzgadniania frachtu
Stawki frachtowe są obliczane przez aparat stawki skojarzony z odnośnym przewoźnikiem. Po potwierdzeniu ładunku jest generowany list frachtowy, a do niego są przenoszone stawki frachtowe. Stawki frachtowe są przypisywane jako opłaty dodatkowe do odnośnego dokumentu źródłowego (zamówienia zakupu, zamówienia sprzedaży i/lub zamówienie przeniesienia), w zależności od konfiguracji używanej w standardowym procesie fakturowania. Proces uzgadniania frachtu (nazywany także procesem dopasowywania) może się rozpocząć natychmiast po otrzymaniu faktury za fracht od firmy przewozowej. Fakturę można odebrać elektronicznie lub na papierze. Jeśli faktura jest otrzymywana na papierze, można wygenerować fakturę elektroniczną, używając listu frachtowego jako szablonu. 

[![Proces uzgadniania frachtu](./media/freight-reconcilation-process.jpg)](./media/freight-reconcilation-process.jpg)

## <a name="manual-reconciliation"></a>Ręczne uzgadnianie
Jeśli uzgadniasz fracht ręcznie, trzeba dopasować każdy wiersz faktury do wiersza lub wierszy listu frachtowego dla fakturowanego ładunku. To dopasowanie odbywa się na stronie **Dopasowywanie opłat frachtowych i faktur**. Jeśli kwota w wierszu faktury nie pasuje do kwoty w liście frachtowym, dla różnicy należy wybrać przyczynę uzgodnienia. Jeśli istnieje wiele przyczyn uzgodnienia, można rozdzielić niezgodną kwotę między nie. Przyczyna uzgodnienia określa, jak kwoty różnic są księgowane w księdze głównej. Po uzgodnieniu całej kwoty faktury faktura jest przedstawiana do zatwierdzenia, po czym następuje zaksięgowanie arkusza. Poniższa ilustracja pokazuje sposób generowania faktury za fracht oraz uzgadniania frachtu w programie Microsoft Dynamics 365 for Finance and Operations. 
[![Zadania uzgadniania frachtu w systemie Dynamics AX](./media/processflowforfreightreconciliation.jpg)](./media/processflowforfreightreconciliation.jpg)
## <a name="automatic-reconciliation"></a>Automatyczne uzgadnianie
Aby użyć automatycznego uzgadniania, należy określić harmonogram uzgadniania oraz faktury i przewoźników, których uzgadnianie ma dotyczyć. Dopasowywanie wierszy faktur i listów frachtowych odbywa się zgodnie z konfiguracją głównej inspekcji i typem listu frachtowego. Po uruchomieniu automatycznego uzgadniania należy zidentyfikować wszystkie faktury, których nie jest w stanie dopasować system. Następnie należy wykonać ręczne przetwarzanie tych faktur, zanim będzie można zaksięgować wszystkie faktury do zapłaty.



