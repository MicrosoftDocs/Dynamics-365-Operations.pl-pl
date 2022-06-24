---
title: Zaktualizuj budżet z przeniesienia po zmniejszeniu zamówień i faktur
description: Ten artykuł opisuje, jak kontrolować, co dzieje się z budżetem przeniesionym, gdy zamówienia zakupu są anulowane lub zredukowane oraz gdy faktury są zredukowane.
author: TaylorVH
ms.date: 02/11/2022
ms.topic: article
ms.search.form: LedgerFund
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-savanh
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2022-02-01
ms.openlocfilehash: 7f0ef0ffdf697609e811f754b4378b1f7a81c494
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8897966"
---
# <a name="update-the-carry-forward-budget-after-reductions-in-purchase-orders-and-invoices"></a>Zaktualizuj budżet z przeniesienia po zmniejszeniu zamówień i faktur

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Ten artykuł opisuje, jak kontrolować, co dzieje się z budżetem przeniesionym, gdy zamówienia zakupu są anulowane lub zredukowane oraz gdy faktury są zredukowane.

Aby dowiedzieć się, jak zamówienia zakupu są przetwarzane na koniec roku, zobacz [Przetwarzanie zamówień zakupu na koniec roku](/dynamicsax-2012/appuser-itpro/process-purchase-orders-at-year-end).

## <a name="turn-carry-forward-budget-reductions-for-invoice-variances-on-or-off"></a>Włączanie lub wyłączanie przenoszenia redukcji budżetowych dla różnic w fakturach

System może zawsze zaktualizować budżet przeniesiony, gdy zamówienie zakupu zostanie anulowane lub zmniejszone. Jeśli jednak chcesz aktualizować budżet przeniesienia, gdy faktura zostanie zredukowana, musisz włączyć funkcję *Zmniejsz budżet przeniesienia, gdy faktura w zamówieniu zakupu zostanie zredukowana o wariancję*. Administratorzy mogą włączyć lub wyłączyć tę funkcję, wyszukując ją w przestrzeni roboczej **[Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)**.

## <a name="purchase-order-reductions-and-cancellations"></a>Zmniejszanie i anulowanie zamówień

Niezależnie od tego, czy włączona jest opcja *Zmniejsz budżet przeniesiony, gdy faktura w zamówieniu zakupu zostanie zredukowana o wariancję*, budżet przeniesiony zostanie zaktualizowany, gdy kwalifikujące się zamówienie zakupu zostanie anulowane lub zredukowane. Możesz ustawić, aby każdy fundusz księgi głównej odpowiadał w jeden z poniższych sposobów:

- Zachowaj budżet z przeniesieniami w takiej formie, w jakiej został stworzony.
- Automatycznie dostosowuje budżet przeniesienia, aby usunąć anulowaną lub zmniejszoną kwotę.

Tylko linie zamówień zakupu, które mają dystrybucję zawierającą fundusz, są dostępne dla automatycznej korekty budżetu. Automatyczna korekta budżetu następuje po sfinalizowaniu zamówienia zakupu lub potwierdzeniu redukcji zamówienia zakupu.

## <a name="invoice-reductions"></a>Redukcje faktur

Gdy włączona jest opcja *Zmniejsz budżet przeniesiony, gdy faktura w stosunku do zamówienia zakupu jest zmniejszona o wariancję*, możesz określić, czy każdy fundusz powinien zmniejszać budżet przeniesiony, gdy faktura jest zmniejszona, oprócz tego, gdy zamówienie zakupu jest zmniejszone lub anulowane. Faktura musi dotyczyć zamówienia zakupu, które ma przeniesiony budżet. Obniżki obejmują odchylenia cenowe, odchylenia opłat i odchylenia podatkowe. Kiedy zamówienie zakupu z przeniesienia jest zmniejszane podczas fakturowania, tworzona jest wariancja. Kiedy faktura zostanie zaksięgowana, obciążenie zlecenia zakupu zostanie pomniejszone o kwotę różnicy. Funkcja ta utworzy także automatyczną korektę budżetu o kwotę odchylenia.

Po wyłączeniu funkcji *Zmniejsz budżet przeniesienia, gdy faktura w zamówieniu zakupu jest zmniejszona o wariancję*, budżet przeniesienia nie jest zmniejszany w tym scenariuszu. W związku z tym pozostała część budżetu do przeniesienia w wysokości odchylenia pozostaje.

## <a name="configure-the-carry-forward-budget-options-for-each-fund"></a>Skonfiguruj opcje przeniesienia budżetu dla każdego funduszu

Wykonaj poniższe kroki dla każdego funduszu księgi głównej, który powinien mieć możliwość zmniejszenia przeniesionego budżetu, gdy zamówienie zakupu lub faktura są zmniejszane.

1. Wybierz kolejno opcje **Księga główna \> Plan kont \> Fundusze \> Fundusze**.
1. Wybierz fundusz, który chcesz utworzyć.
1. W zakładce **Zakupy na koniec roku** upewnij się, że opcja **Odstąpienie od wybranej opcji na koniec roku** jest ustawiona na *Tak*.
1. W zakładce **Stan budżetu przeniesionego** ustaw pole **Przywróć budżet, gdy przeniesione zlecenie zakupu zostanie anulowane lub zmniejszone** zgodnie z potrzebami. Ustawienia mają nieco inny efekt, w zależności od tego, czy w systemie włączona jest funkcja *Zmniejszaj budżet przeniesiony, gdy faktura do zamówienia zakupu jest zmniejszona o wariancję*.

    - Gdy funkcja ta jest wyłączona, system reaguje tylko na anulowane lub zmniejszone zamówienia zakupu. Ustawienia opcji działają w następujący sposób:

        - *Nie* – system tworzy wpis do rejestru budżetowego dla pozostałego salda zamówień zakupu, które zostały anulowane lub zredukowane.
        - *Tak* – system pozwala na anulowanie lub zmniejszenie zamówień zakupu, ale nie tworzy wpisu do rejestru budżetowego. Przeniesiony budżet pozostaje dostępny do wykorzystania przez inne dokumenty.

    - Kiedy funkcja jest włączona, system reaguje zarówno na odchylenia w fakturach, jak i na anulowane lub zmniejszone zamówienia zakupu. Ustawienia opcji działają w następujący sposób:

        - *Nie* – w przypadku różnic w fakturach system tworzy wpis do rejestru budżetowego w odniesieniu do zamówienia zakupu na kwotę zmniejszającą różnicę. W przypadku anulowanych lub zmniejszonych zamówień zakupu to ustawienie ma taki sam efekt, jak wtedy, gdy funkcja jest wyłączona.
        - *Tak* – w przypadku różnic w fakturach system pozwala na zmniejszenie faktury, ale nie tworzy wpisu w rejestrze budżetowym. Przeniesiony budżet pozostaje dostępny do wykorzystania przez inne dokumenty. W przypadku anulowanych lub zmniejszonych zamówień zakupu to ustawienie ma taki sam efekt, jak wtedy, gdy funkcja jest wyłączona.

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Przetwarzanie zamówień zakupu na koniec roku](/dynamicsax-2012/appuser-itpro/process-purchase-orders-at-year-end)
- [Obsługa rezerwacji środków w budżecie](general-budget-reservation-tasks.md)
- [Fundusze w sektorze publicznym](funds-public-sector.md)
- [Konfigurowanie funduszu w podmiocie z sektora publicznego](tasks/set-up-fund-public-sector.md)
