---
title: "Uzgadnianie frachtu w module Zarządzanie transportem"
description: W tym artykule opisano proces uzgadniania frachtu.
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: TMSAuditMaster, TMSFreightBillInvoiceReconcile, TMSFreightBillSummary, TMSFreightBillType, TMSFreightMatchReason, TMSInvoiceTable
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 89983
ms.assetid: bc34a9b1-0c11-4797-b463-25409cf98ca8
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: c85806132efb65c2d4bc85ef1921c003c5c7453b
ms.lasthandoff: 03/31/2017


---

# <a name="reconcile-freight-in-transportation-management"></a>Uzgadnianie frachtu w module Zarządzanie transportem

[!include[banner](../includes/banner.md)]


W tym artykule opisano proces uzgadniania frachtu.

Uzgadnianie frachtu można wykonać ręcznie lub skonfigurować jego wykonywanie automatyczne. Aby używać automatycznego uzgadnianie frachtu, należy skonfigurować główną inspekcję, gdzie można zdefiniować kryteria określające, które listy frachtowe mają być uzgadniane automatycznie.

## <a name="the-freight-reconciliation-process"></a>Proces uzgadniania frachtu
Stawki frachtowe są obliczane przez aparat stawki skojarzony z odnośnym przewoźnikiem. Po potwierdzeniu ładunku jest generowany list frachtowy, a do niego są przenoszone stawki frachtowe. Stawki frachtowe są przypisywane jako opłaty dodatkowe do odnośnego dokumentu źródłowego (zamówienia zakupu, zamówienia sprzedaży i/lub zamówienie przeniesienia), w zależności od konfiguracji używanej w standardowym procesie fakturowania. Proces uzgadniania frachtu (nazywany także procesem dopasowywania) może się rozpocząć natychmiast po otrzymaniu faktury za fracht od firmy przewozowej. Fakturę można odebrać elektronicznie lub na papierze. Jeśli faktura jest otrzymywana na papierze, można wygenerować fakturę elektroniczną, używając listu frachtowego jako szablonu. 

[![Proces uzgadniania frachtu](./media/freight-reconcilation-process.jpg)](./media/freight-reconcilation-process.jpg)

## <a name="manual-reconciliation"></a>Ręczne uzgadnianie
Jeśli uzgadniasz fracht ręcznie, trzeba dopasować każdy wiersz faktury do wiersza lub wierszy listu frachtowego dla fakturowanego ładunku. To dopasowanie odbywa się na stronie **Dopasowywanie opłat frachtowych i faktur**. Jeśli kwota w wierszu faktury nie pasuje do kwoty w liście frachtowym, dla różnicy należy wybrać przyczynę uzgodnienia. Jeśli istnieje wiele przyczyn uzgodnienia, można rozdzielić niezgodną kwotę między nie. Przyczyna uzgodnienia określa, jak kwoty różnic są księgowane w księdze głównej. Po uzgodnieniu całej kwoty faktury faktura jest przedstawiana do zatwierdzenia, po czym następuje zaksięgowanie arkusza. Poniższa ilustracja pokazuje sposób generowania faktury za fracht oraz uzgadniania frachtu w programie Microsoft Dynamics 365 for Operations. 
[![Zadania uzgadniania frachtu w systemie Dynamics AX](./media/processflowforfreightreconciliation.jpg)](./media/processflowforfreightreconciliation.jpg)
## <a name="automatic-reconciliation"></a>Automatyczne uzgadnianie
Aby użyć automatycznego uzgadniania, należy określić harmonogram uzgadniania oraz faktury i przewoźników, których uzgadnianie ma dotyczyć. Dopasowywanie wierszy faktur i listów frachtowych odbywa się zgodnie z konfiguracją głównej inspekcji i typem listu frachtowego. Po uruchomieniu automatycznego uzgadniania należy zidentyfikować wszystkie faktury, których nie jest w stanie dopasować system. Następnie należy wykonać ręczne przetwarzanie tych faktur, zanim będzie można zaksięgować wszystkie faktury do zapłaty.




