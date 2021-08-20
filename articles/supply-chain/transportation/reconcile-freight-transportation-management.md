---
title: Uzgadnianie frachtu w module Zarządzanie transportem
description: W tym artykule opisano proces uzgadniania frachtu.
author: MarkusFogelberg
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TMSAuditMaster, TMSFreightBillInvoiceReconcile, TMSFreightBillSummary, TMSFreightBillType, TMSFreightMatchReason, TMSFBDetailReconcile, TMSInvoiceTable,TMSInvoiceLineReconcile,TMSReconcileInvoice, TMSFreightBillDetail, TMSFreightBillTypeAssignment, TMSRejectInvoiceLine, TMSMiscellaneousCharge
audience: Application User
ms.reviewer: kamaybac
ms.custom: 89983
ms.assetid: bc34a9b1-0c11-4797-b463-25409cf98ca8
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e0fbc877a05b2bd73401c2c4a49228aa7e73fa7526813f6f6285c2bc7c72a5bf
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6756009"
---
# <a name="reconcile-freight-in-transportation-management"></a>Uzgadnianie frachtu w module Zarządzanie transportem

[!include [banner](../includes/banner.md)]

W tym artykule opisano proces uzgadniania frachtu.

Uzgadnianie frachtu można wykonać ręcznie lub skonfigurować jego wykonywanie automatyczne. Aby używać automatycznego uzgadnianie frachtu, należy skonfigurować główną inspekcję, gdzie można zdefiniować kryteria określające, które listy frachtowe mają być uzgadniane automatycznie.

## <a name="the-freight-reconciliation-process"></a>Proces uzgadniania frachtu

Stawki frachtowe są obliczane przez aparat stawki skojarzony z odnośnym przewoźnikiem. Po potwierdzeniu ładunku jest generowany list frachtowy, a do niego są przenoszone stawki frachtowe. Stawki frachtowe są przypisywane jako opłaty dodatkowe do odnośnego dokumentu źródłowego (zamówienia zakupu, zamówienia sprzedaży i/lub zamówienie przeniesienia), w zależności od konfiguracji używanej w standardowym procesie fakturowania. Proces uzgadniania frachtu (nazywany także procesem dopasowywania) może się rozpocząć natychmiast po otrzymaniu faktury za fracht od firmy przewozowej. Fakturę można odebrać elektronicznie lub na papierze. Jeśli faktura jest otrzymywana na papierze, można wygenerować fakturę elektroniczną, używając listu frachtowego jako szablonu.

[![Proces uzgadniania frachtu.](./media/freight-reconcilation-process.jpg)](./media/freight-reconcilation-process.jpg)

## <a name="manual-reconciliation"></a>Ręczne uzgadnianie

Jeśli uzgadniasz fracht ręcznie, trzeba dopasować każdy wiersz faktury do wiersza lub wierszy listu frachtowego dla fakturowanego ładunku. To dopasowanie odbywa się na stronie **Dopasowywanie opłat frachtowych i faktur**. Jeśli kwota w wierszu faktury nie pasuje do kwoty w liście frachtowym, dla różnicy należy wybrać przyczynę uzgodnienia. Jeśli istnieje wiele przyczyn uzgodnienia, można rozdzielić niezgodną kwotę między nie. Przyczyna uzgodnienia określa, jak kwoty różnic są księgowane w księdze głównej. Po uzgodnieniu całej kwoty faktury faktura jest przedstawiana do zatwierdzenia, po czym następuje zaksięgowanie arkusza. Poniższa ilustracja pokazuje sposób generowania faktury za fracht oraz uzgadniania frachtu.

[![Zadania uzgadniania frachtu.](./media/processflowforfreightreconciliation.jpg)](./media/processflowforfreightreconciliation.jpg)

## <a name="automatic-reconciliation"></a>Automatyczne uzgadnianie

Aby użyć automatycznego uzgadniania, należy określić harmonogram uzgadniania oraz faktury i przewoźników, których uzgadnianie ma dotyczyć. Dopasowywanie wierszy faktur i listów frachtowych odbywa się zgodnie z konfiguracją głównej inspekcji i typem listu frachtowego. Po uruchomieniu automatycznego uzgadniania należy zidentyfikować wszystkie faktury, których nie jest w stanie dopasować system. Następnie należy wykonać ręczne przetwarzanie tych faktur, zanim będzie można zaksięgować wszystkie faktury do zapłaty.

## <a name="match-freight-bills-with-freight-invoices-using-automatic-or-manual-reconciliation"></a>Uzgadnianie rachunków frachtowych z fakturami za fracht przy użyciu uzgodnienia automatycznego lub ręcznego

*Uzgadnianie* to proces znajdowania rachunków frachtowych odpowiadających każdej fakturze za fracht. W tym celu należy kolejno uzgadniać wiersze faktury (uzgadnianie ręczne) lub uzgadniać wszystkie dostępne faktury na raz (automatyczne uzgadnianie).

### <a name="auto-matching"></a>Automatyczne uzgadnianie

W przypadku uzgadniania wielu faktur za fracht do tej samej opłaty frachtowej proces automatycznego uzgadniania działa następująco:

1. Wszystkie niedopasowane faktury frachtowe są sortowane według kwoty, z największą kwotą jako pierwsza.
1. Faktury za fracht są dopasowywane kolejno, dopóki rachunek za fracht nie będzie mieć pozostałej kwoty dodatniej.
1. W zależności od ustawień głównej inspekcji i pozostałej kwoty na fakturach za fracht jest ustawiana pozostała kwota.

### <a name="manual-matching"></a>Uzgadnianie ręczne

Wszystkie opłaty frachtowe z kwotami dodatnimi będą dostępne do dopasowania. Podobnie jak automatyczne uzgadnianie, użytkownik może dopasować tylko faktury za fracht z ujemnymi kwotami do w pełni dopasowanych rachunków frachtowych.

### <a name="example"></a>Przykład

Załóżmy, że użytkownik ma rachunek frachtowy na kwotę 1500 i utworzono trzy faktury za fracht, po jednym wierszu faktury dla każdej faktury z następującymi ustawieniami:

- Oryginalny rachunek frachtowy (FB): kwota 1500
- Faktura 1 (Inv1): kwota 1000
- Faktura 2 (Inv2): kwota 600
- Faktura 3 (Inv3): kwota -100

#### <a name="automatic-matching-result"></a>Wynik automatycznego uzgadniania

Automatyczne uzgadnianie będzie wykonywane w następującej kolejności:

1. Sortuj wszystkie faktury za fracht malejąco według kwoty: Inv1 -> Inv2 -> Inv3.
1. Dopasuj fakturę Inv1 do rachunku FB. Inv1 ma dopasowane 1000, a FB ma pozostałą kwotę 500, więc stan jest ustawiony na *Częściowo dopasowane*.
1. Dopasuj fakturę Inv2 do rachunku FB. Inv2 ma dopasowane 500, a FB ma pozostałą kwotę 0, więc stan jest ustawiony na *W pełni dopasowane*.
1. Ponieważ konto FB jest teraz w pełni dopasowane, nie można przetworzyć faktury Inv3.

#### <a name="manual-matching-result"></a>Wynik uzgadniania ręcznego

W przypadku uzgadniania ręcznego wyniki różnią się w zależności od kolejności uzgadniania, co przedstawiono w poniższych przykładowych przypadkach.

##### <a name="manual-matching-case-1"></a>Uzgadnianie ręczne — przypadek 1

W tym przykładzie można wykonać uzgadnianie ręczne w następujący sposób:

1. Dopasuj rachunek FB do faktury Inv1. FB ma dopasowaną kwotę 500, więc stan jest ustawiony na *Częściowo dopasowane*.
1. Dopasuj fakturę Inv2 do rachunku FB. Inv2 ma dopasowane 500, a FB ma pozostałą kwotę 0, więc stan jest ustawiony na *W pełni dopasowane*.
1. Podczas ręcznego uzgadniania faktury Inv3 nie będzie można znaleźć żadnych niedopasowanych rachunków frachtowych.

Te przypadek jest w zasadzie taki sam jak automatyczne uzgadnianie

##### <a name="manual-matching-case-2"></a>Uzgadnianie ręczne — przypadek 2

W tym przykładzie można wykonać uzgadnianie ręczne w inny sposób:

1. Dopasuj fakturę Inv3 do rachunku FB. Teraz FB ma pozostałą kwotę 1600, która jest taka sama jak odjęcie ujemnej 100 od 1500. Zarówno FB, jak i Inv3 mają dopasowaną ilość -100.
1. Dopasuj kolejno faktury Inv1 i Inv 2 do FB. Rachunek FB jest w pełni dopasowany.

Jak pokazano w tym przykładzie, uzgadnianie faktur za fracht z kwotami ujemnymi należy wykonać tylko ręcznie. Zapewnia to, że zawsze jest możliwe dopasowanie faktur za fracht z kwotami ujemnymi do w pełni dopasowanej opłaty frachtowej, ponieważ umożliwia to kontrolowanie kolejności uzgadniania.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]