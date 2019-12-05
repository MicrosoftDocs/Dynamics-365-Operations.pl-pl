---
title: Omówienie zapotrzebowania na zakup
description: W tym temacie opisano przepływ pracy zapotrzebowania na zakup oraz różne stany, jakie może przyjmować zapotrzebowanie na zakup.
author: mkirknel
manager: AnnBe
ms.date: 11/02/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchReqConsolidation, PurchReqCreate, PurchReqCreatePurchDetails, PurchReqCreatePurchListPage, PurchReqTable, PurchReqTableListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2174
ms.assetid: 77d07119-4d9f-4c0e-acbe-d319203571ab
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1bfec4660d9e6b0898cf81e1f1fdd2e4c1fdcaef
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2019
ms.locfileid: "2815349"
---
# <a name="purchase-requisition-overview"></a>Omówienie zapotrzebowania na zakup

[!include [banner](../includes/banner.md)]

W tym temacie opisano przepływ pracy zapotrzebowania na zakup oraz różne stany, jakie może przyjmować zapotrzebowanie na zakup.

W zależności od konfiguracji organizacji, możesz tworzyć zapotrzebowania na zakup dla produktów, których używa organizacja. Zapotrzebowanie na zakup to wewnętrzny dokument, który upoważnia dział zakupów do nabycia towarów lub usług.  

Po zatwierdzeniu zapotrzebowania na zakup, może ono służyć do generowania zamówienia zakupu. Zamówienia zakupu to dokumenty zewnętrzne, które dział zakupów przesyła do dostawców.

## <a name="creating-purchase-requisitions"></a>Tworzenie zapotrzebowań zakupu
Zapotrzebowanie na zakup można utworzyć na stronie **Moje zapotrzebowania na zakup**, a następnie wybierać potrzebne towary i usługi. Można wybrać towary z katalogu zaopatrzenia, który został utworzony w firmie, lub można wygenerować żądanie towarów, których nie ma w katalogu, wybierając kategorię zaopatrzenia i wprowadzając szczegóły produktu.  

Zanim prześlesz zapotrzebowania na zakupu do przeglądu, przepływy pracy muszą zostać skonfigurowany. Przepływ pracy jest używany do przenoszenia zapotrzebowania na zakup przez proces przeglądu, z początkowego stanu **Wersja robocza** do stanu finalnego **Zatwierdzono**.

### <a name="purchase-requisition-statuses"></a>Stany zapotrzebowania zakupu

Podczas tworzenia nowego zamówienia na zakup jest do niego przypisywany stan. Stan jest przypisywany również do każdego wiersza dodawanego do zapotrzebowania na zakup. Podczas przesyłania zapotrzebowania na zakup do przepływu pracy celem przeglądu, stan zapotrzebowania na zakup i stan każdego wiersza są aktualizowane w miarę postępu procesu przepływu pracy.  

Można skonfigurować proces przepływu pracy dla zapotrzebowania na zakup, tak aby kierować zapotrzebowanie przez proces przeglądu jako pojedynczy dokument. Alternatywnie wiersze zapotrzebowania na zakup mogą być kierowane indywidualnie do odpowiednich osób sprawdzających. Jeśli wiersze zapotrzebowania na zakup są sprawdzane pojedynczo, można zaktualizować stan każdego wiersza zapotrzebowania na zakup w miarę przepływu wiersza w trakcie procesu przeglądu. Gdy wszystkie wiersze przejdą proces przeglądu i nie pozostaną do wykonania żadne kroki w procesie przeglądu, stan całego zapotrzebowania na zakup zostanie zaktualizowany.

### <a name="purchase-requisition-workflow"></a>Przepływ pracy w zapotrzebowaniu na zakup

Na poniższym diagramie przedstawiono stany, które są przypisane do zapotrzebowania na zakup i wiersz zapotrzebowania na zakup w miarę jego przekazywania w procesie przepływu pracy.  

[![Stany nagłówka i wierszy zapotrzebowania na zakup](./media/purchasereq_headerline_statuses.jpg)](./media/purchasereq_headerline_statuses.jpg)

### <a name="purchase-requisition-header-and-line-status-relationships"></a>Relacje stanów nagłówka i wierszy zapotrzebowania na zakup

Całościowy stan zapotrzebowania na zakup jest uzależniony od stanu jego wierszy. W związku z tym, do ukończenia przepływu pracy w ramach całego zapotrzebowania na zakup konieczne jest dokonanie przeglądu wszystkich jego wierszy. W poniższej tabeli przedstawiono stany, które są przypisane do nagłówka i wierszy zapotrzebowania na zakup w miarę jego przekazywania w procesie przepływu pracy.

<table>
<thead>
<tr class="header">
<th>Stan zapotrzebowania na zakup</th>
<th>Stan wiersza zapotrzebowania na zakup</th>
<th>Opis</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Wersja robocza</td>
<td>Wersja robocza</td>
<td>Zapotrzebowanie na zakup i wiersz zapotrzebowania na zakup zostały utworzone, ale nie zostały przesłane do przeglądu. Zapotrzebowanie na zakup i jego wiersze o stanie <strong>Robocze</strong> można modyfikować. Zapotrzebowanie na zakup lub wiersz zapotrzebowania na zakup ma także stan <strong>Roboczy</strong>, jeżeli je wycofano, ale nie przesłano do sprawdzenia. <strong>Uwaga:</strong> Zapotrzebowanie na zakup można przesłać lub wycofać na poziomie dokumentu. Jednak nie można przesłać ani wycofać pojedynczego wiersza zapotrzebowania na zakup.</td>
</tr>
<tr class="even">
<td>W trakcie przeglądu</td>
<td><ul>
<li>W trakcie przeglądu</li>
<li>Odrzucono</li>
</ul></td>
<td>Jeśli przepływ pracy został skonfigurowany tak, aby wiersze zapotrzebowania na zakup były przesyłane do różnych osób sprawdzających, każdy z nich będzie miał stan <strong>W trakcie przeglądu</strong> lub <strong>Odrzucono</strong>. Stan zapotrzebowania na zakup zostanie zaktualizowany, gdy zakończy się proces przeglądu wszystkich jego wierszy i nie pozostaną do wykonania żadne kroki procesu przeglądu dla danego zapotrzebowania.
<ul>
<li><strong>Trwa przegląd</strong> — wiersze zapotrzebowania na zakup zostały przesłane do przeglądu. Po zakończeniu procesu przepływu pracy dla wiersza zapotrzebowania na zakup, stan wiersza nadal ma wartość <strong>Trwa przegląd</strong>, aż zakończy się przegląd wszystkich pozostałych wierszy zapotrzebowania na zakup.</li>
<li><strong>Odrzucone</strong> — Wiersz zapotrzebowania na zakup został odrzucony. Odrzucone wiersze zapotrzebowania na zakup można zmodyfikować i ponownie przesłać do przeglądu.</li>
</ul>
Ponowne przesłanie odrzuconego wiersza zamówienia na zakup spowoduje ponowne rozpoczęcie procedury przeglądu dla wszystkich przeglądanych wierszy zamówienia na zakup. <strong>Uwaga:</strong> można wycofać zapotrzebowanie na zakup, które już zostało przesłane. Wycofanie zapotrzebowania na zakup spowoduje również wycofanie jego wszystkich pozostałych wierszy. Wycofane wiersze zapotrzebowania na zakup można usunąć.</td>
</tr>
<tr class="odd">
<td>Odrzucono</td>
<td>Odrzucono</td>
<td>Zapotrzebowanie na zakup i wszystkie jego wiersze zostały wycofane. Wycofane zapotrzebowanie na zakup i jego wiersze można przesłać ponownie.</td>
</tr>
<tr class="even">
<td>Zatwierdzono</td>
<td><ul>
<li>Zatwierdzono</li>
<li>Anulowano</li>
<li>Zamknięto</li>
</ul></td>
<td>Wszystkie wiersze zapotrzebowania na zakup przeszły proces przeglądu i nie zostały do wykonania żadne kroki w procesie przeglądu.
<ul>
<li><strong>Zatwierdzone</strong> — ukończono proces przeglądu wiersza zapotrzebowania na zakup, a wiersz został zatwierdzony.</li>
<li><strong>Anulowano</strong> — zatwierdzono wiersz zapotrzebowania na zakup, ale został on wycofany, ponieważ nie jest już potrzebny. Można wycofać tylko te wiersze zamówienia na zakup, które zostały zatwierdzone.</li>
<li><strong>Zamknięto</strong> — wiersz zapotrzebowania na zakup został zatwierdzony, a dokumenty zostały wygenerowane, w zależności od celu zapotrzebowania.
<ul>
<li>Jeśli celem zapotrzebowania jest zużycie, zostanie wygenerowane zamówienie zakupu dla wiersza zapotrzebowania na zakup.</li>
<li>Jeśli celem zapotrzebowania jest uzupełnienie zapasów, system wygeneruje jeden lub więcej dokumentów uzupełnienia.</li>
</ul></li>
</ul></td>
</tr>
<tr class="odd">
<td>Anulowano</td>
<td>Anulowano</td>
<td>Wycofano zapotrzebowanie i na zakup i wszystkie jego wiersze. <strong>Uwaga:</strong> jeśli nie jest już wymagany towaru w wierszu zapotrzebowania na zakup, należy anulować wiersz zapotrzebowania na zakup, jeśli został już zatwierdzony. Można wycofać tylko te wiersze zamówienia na zakup, które zostały zatwierdzone. Jeśli wszystkie wiersze zapotrzebowania na zakup są w przeglądzie, zapotrzebowanie na zakup będzie mieć stan <strong>Trwa przegląd</strong>. W takim przypadku można wycofać zapotrzebowanie na zakup i usunąć odpowiedni wiersz zapotrzebowania na zakup.</td>
</tr>
<tr class="even">
<td>Zamknięto</td>
<td><ul>
<li>Zamknięto</li>
<li>Anulowano</li>
</ul></td>
<td>Zapotrzebowanie na zakup zostanie zamknięte, a system wygeneruje jeden lub więcej dokumentów uzupełnienia.
<ul>
<li><strong>Zamknięto</strong> — wiersz zapotrzebowania na zakup został zatwierdzony, a dokumenty zostały wygenerowane, w zależności od celu zapotrzebowania.
<ul>
<li>Jeśli celem zapotrzebowania jest zużycie, zostanie wygenerowane zamówienie zakupu dla wiersza zapotrzebowania na zakup.</li>
<li>Jeśli celem zapotrzebowania jest uzupełnienie zapasów, system wygeneruje jeden lub więcej dokumentów uzupełnienia.</li>
</ul></li>
<li><strong>Anulowano</strong> — zatwierdzono wiersz zapotrzebowania na zakup, ale został on wycofany, ponieważ nie jest już potrzebny. Można wycofać tylko te wiersze zamówienia na zakup, które zostały zatwierdzone.</li>
</ul>
<strong>Uwaga:</strong> jeśli nie jest już wymagany towar w wierszu zapotrzebowania na zakup, który został zamknięty, musisz anulować wiersz w dokumencie uzupełnienia wygenerowanym dla wiersza zapotrzebowania na zakup.</td>
</tr>
</tbody>
</table>

## <a name="distributing-costs-to-multiple-financial-accounts"></a>Dystrybucja kosztów do wielu kont finansowych
Można dystrybuować koszty produktu, który jest uwzględniany w zapotrzebowaniu zakupu, do wielu kont finansowych. Jeśli organizacja używa wymiarów, takich jak centra i działy kosztów, można dystrybuować koszty produktu do wymiarów dla kont finansowych.

## <a name="requisition-purposes"></a>Cele zapotrzebowania
Cele zapotrzebowania uelastyczniają proces wypełniania zapotrzebowań. Podczas tworzenia zapotrzebowania można przypisać mu jeden z dwóch celów: zużycie lub uzupełnienie. W zależności od celu zapotrzebowania i sposobu ustawień organizacji popyt regulowany zapotrzebowaniem może zostać zaspokojony przez zamówienie zakupu, zlecenie przesunięcia, zlecenie produkcyjne lub kartę Kanban.  

W zasadach zaopatrzenia można kontrolować cele zapotrzebowania, które są dostępne podczas tworzenia zapotrzebowania w danej organizacji.

### <a name="requisitions-that-have-a-purpose-of-consumption"></a>Zapotrzebowania, których celem jest zużycie

Zapotrzebowanie, którego celem jest zużycie, reprezentuje popyt na towary lub usługi, które będą używane wewnętrznie przez organizację. Popyt, który jest tworzony przez ten rodzaj zapotrzebowania, zawsze jest zaspokajany przez zamówienie zakupu. Jeśli system Supply Chain Management jest skonfigurowany do automatycznego generowania zamówień zakupu, zamówienia zakupu są tworzone po zatwierdzeniu zapotrzebowania na zakup.

### <a name="requisitions-that-have-a-purpose-of-replenishment"></a>Zapotrzebowania, których celem jest uzupełnienie

Zapotrzebowanie, które ma cel uzupełnienia, reprezentuje popyt na uzupełnienie zapasów. Na przykład, można utworzyć zapotrzebowanie na uzupełnienie towarów, tak aby mogły być sprzedawane w określonej lokalizacji detalicznej w określonym czasie. Popyt kreowany przez ten rodzaj zapotrzebowania można zaspokoić, korzystając z zamówienia zakupu, zamówienia przeniesienia, zlecenia produkcyjnego lub Kanban.  

Jeśli celem zapotrzebowania jest uzupełnienie, popyt jest wyrażony jako ilość zamiast kwoty pieniężnej. Dlatego księgowania przyszłych zobowiązań wiążących, kontrola budżetowa, reguły biznesowe dotyczące określania środków trwałych (BRAD), księgowania projektu i wszelkie powiązane reguły nie mają zastosowania. Tylko produkty, które są magazynowane i wydawane określonej firmie, mogą zaspokajać popyt regulowany zapotrzebowaniem uzupełniającym. Aby określić produkty, które są dostępne, jeśli celem zapotrzebowania jest uzupełnienie, użyj strony **Reguła dostępu do kategorii uzupełnienia**.  

Aby można było używać zapotrzebowań na zakup, których celem jest uzupełnienie, konfiguracja systemu w module planowania głównego musi obejmować funkcję żądania zapotrzebowania. Metoda zaspokajania popytu generowanego przez ten typ zapotrzebowania jest automatycznie określana na podstawie zasad dostaw skonfigurowanych dla pozycji w organizacji oraz planowana w ramach planowania głównego.

## <a name="purchase-requisitions-and-requests-for-quotation"></a>Zapotrzebowania na zakup i zapytania ofertowe
W niektórych przypadkach należy uruchomić procesu ZO, aby określić dostawcę i cenę produktów uwzględnionych w zapotrzebowaniu na zakup. ZO może zostać wygenerowane, gdy zapotrzebowanie na zakup jest w przeglądzie. Po zaakceptowaniu oferty, informacje o dostawcy, cenie itd. zostaną przeniesione do zapotrzebowania.  

Można wstrzymać zapotrzebowanie na zakup przez zaznaczenie pola wyboru **Wstrzymane** na stronie **Szczegóły zapotrzebowania na zakup**. Można kontynuować przetwarzanie zapotrzebowania na zakup tylko wtedy, gdy zostanie usunięte zaznaczenie tego pola wyboru.  

**Uwaga:** w eProcurement ZO dla zapotrzebowania na zakup mogą umożliwiać dostawcom dodawanie alternatywnych wierszy. W takim przypadku zapotrzebowanie na zakup będzie zawierało zatwierdzone zmiany.

## <a name="demand-consolidation"></a>Konsolidacja popytu
Konsolidowanie wierszy zapotrzebowania na zakup z wielu zapotrzebowań na zakup pozwala wzmocnić pozycję negocjacyjną podczas rozmów z dostawiamy, by uzyskać lepsze ceny, niższe koszty wysyłki i obsługi oraz zmniejszenie kosztów ogólnych.  

Wiersze zapotrzebowania na zakup kwalifikują się do konsolidacji popytu tylko wtedy, gdy są spełnione następujące warunki:

-   Zapotrzebowanie na zakup zostało zatwierdzone.
-   Zapotrzebowanie na zakup spełnia kryteria reguły zasad zakupów dla ręcznego przetwarzania i konsolidowania popytu.

Zatwierdzone wiersze zapotrzebowania na zakup spełniające kryteria dla ręcznego przetwarzania są wymienione na stronie **Zwolnij zatwierdzone zapotrzebowania na zakup**. Jeśli wiersz zapotrzebowania na zakup spełnia również kryteria dla konsolidacji popytu, wiersz może zostać dodany do możliwości konsolidacji.  

Możliwości konsolidacji jest zbiorem wierszy zapotrzebowania zakupu, które są grupowane razem, aby pracownik działu zakupów mógł wynegocjować najlepszą umowę z dostawcami. Wiersze zapotrzebowania na zakup, które można wybrać do możliwości konsolidacji pojawiają się na stronie **Konsolidacja zapotrzebowania na zakup**. Wiersze na tej stronie można zmodyfikować, jeśli są wymagane zmiany. Można również dodawać wiersze do możliwości konsolidacji i usuwać istniejące wiersze.  

Po dodaniu wierszy zapotrzebowania do możliwości konsolidacji i wprowadzeniu odpowiednich zmian, można utworzyć zamówienie zakupu dla skonsolidowanych wierszy zapotrzebowania na zakup.  

**Uwaga:** Zmiany wprowadzone w wierszu zapotrzebowania na zakup na stronie **Konsolidacja zapotrzebowania na zakup** są odzwierciedlone w utworzonym zamówieniu zakupu. W zapotrzebowaniu na zakup wiersze pozostają bez zmian, aby jego historia została zachowana.  

Aby utworzyć zamówienie zakupu dla wierszy zapotrzebowania na zakup, które nie kwalifikują się do konsolidacji popytu lub które nie zostały wybrane do możliwości konsolidacji, należy je przetworzyć ręcznie.

### <a name="consolidating-purchase-requisition-lines"></a>Konsolidowanie wierszy zapotrzebowania na zakup

Proces konsolidacji popytu rozpoczyna się po zatwierdzeniu zapotrzebowania na zakup w przepływie pracy i — jeśli została skonfigurowana kontrola budżetu dla organizacji — po zarejestrowaniu rezerwacji budżetu i przyszłych zobowiązań niewiążących. Poniższy diagram przedstawia przepływ procesu konsolidacji popytu.  

[![Przepływ procesu konsolidacji popytu](./media/demand-consolidation.gif)](./media/demand-consolidation.gif)  

Aby skonsolidować zatwierdzone wiersze zapotrzebowania na zakup, wykonaj następujące kroki:

1.  Przejrzyj zatwierdzone wiersze zapotrzebowania, które zostały wstrzymane do przetwarzania ręcznego i które kwalifikują się do konsolidacji popytu.
2.  Wybierz wiersze w celu dodania do możliwości konsolidacji.
3.  Utwórz nową możliwość konsolidacji lub dodaj wiersze zapotrzebowania do istniejącej możliwości konsolidacji.
4.  Zastosuj wszystkie zmiany, które chcesz wprowadzić w wierszach zapotrzebowania, i usuń wiersze zapotrzebowania, których nie chcesz już uwzględniać w możliwości konsolidacji.
5.  Utwórz zamówienia zakupu dla skonsolidowanych wierszy zapotrzebowania lub wierszy zapotrzebowania na zakup w możliwości konsolidacji.


<a name="additional-resources"></a>Dodatkowe zasoby
--------

[Tworzenie zapotrzebowania na zużycie](tasks/create-requisition-consumption.md)

[Przepływ pracy zapotrzebowań na zakup](purchase-requisitions-workflow.md)



