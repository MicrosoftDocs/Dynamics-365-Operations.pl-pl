---
title: Tworzenie faktury dla odbiorcy
description: '**Faktura dla odbiorcy do zamówienia sprzedaży** jest wekslem związanym ze sprzedażą i który organizacja wystawia odbiorcy.'
author: ShivamPandey-msft
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustFreeInvoice
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 77772
ms.assetid: 00b4b40c-1576-4098-9aed-ac376fdeb8c5
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: aa49b70b07ac3dc6cbc5989b11981098f22be89c
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/01/2019
ms.locfileid: "1835221"
---
# <a name="create-a-customer-invoice"></a>Tworzenie faktury dla odbiorcy

[!include [banner](../includes/banner.md)]

**Faktura dla odbiorcy do zamówienia sprzedaży** jest wekslem związanym ze sprzedażą i który organizacja wystawia odbiorcy. Ten typ faktury dla odbiorcy jest tworzony na podstawie zamówienia sprzedaży, które zawiera wiersze zamówienia i numery towarów. Numery towarów są określane i księgowane w księdze. Zapisy w arkuszu księgi podrzędnej nie są dostępne dla faktury dla odbiorcy do zamówienia sprzedaży. Aby uzyskać więcej informacji, zobacz [Tworzenie faktur zamówienia sprzedaży](tasks/create-sales-order-invoices.md).

**Faktura niezależna** nie jest związana z zamówieniem sprzedaży. Zawiera ona wiersze zamówienia uwzględniające konta księgowe, niezależne opisy oraz wprowadzaną przez użytkownika kwotę sprzedaży. Nie można wprowadzić numeru towaru tego rodzaju na fakturze. Konieczne jest wprowadzenie odpowiedniej informacji o podatku. Konto główne dla sprzedaży jest wskazane w każdym wierszu faktury, który użytkownik może dystrybuować do wielu kont księgowych za pomocą przycisku **Dystrybuuj kwoty** na stronie **Faktura niezależnej**. Ponadto saldo odbiorcy jest księgowane na koncie rozrachunkowym z profilu księgowania, który jest używany dla faktury niezależnej.

Aby uzyskać więcej informacji, zobacz: .

[Tworzenie faktury niezależnej](../accounts-receivable/create-free-text-invoice-new.md)

[Tworzenie szablonu faktury niezależnej](../accounts-receivable/create-free-text-invoice-template-new.md)

[Przypisywanie szablonu faktury niezależnej do odbiorcy](tasks/assign-free-text-invoice-template-customer.md)

[Generowanie i księgowanie cyklicznych faktur niezależnych](tasks/post-recurring-free-text-invoices.md)


**Faktura pro forma** to faktura przygotowana jako oszacowanie rzeczywistej kwoty faktury przed zaksięgowaniem faktury. Fakturę pro forma można wydrukować albo dla faktury dla klienta do zamówienia sprzedaży albo dla faktury niezależnej.

## <a name="post-and-print-individual-customer-invoices-that-are-based-on-sales-orders"></a>Księgowanie i drukowanie pojedynczych faktur dla odbiorcy opartych na zamówieniach sprzedaży
Ten proces służy do tworzenia faktury opartej na zamówieniu sprzedaży. Można to zrobić, jeśli postanowiono wystawić odbiorcy fakturę przed dostarczeniem towarów lub usług. 

W momencie księgowania faktury, ilość **Pozostałe do zafakturowania** dla każdego elementu jest aktualizowana przez sumę wszystkich fakturowanych ilości z wybranego zamówienia sprzedaży. Jeśli obydwie wartości **Pozostałe do zafakturowania** i **Pozostałe do dostarczenia** dla wszystkich towarów z zamówienia sprzedaży są zerowe, to zamówienie sprzedaży otrzymuje stan **Zafakturowane**. Jeśli ilość **Pozostałe do zafakturowania** jest równa zero (0), stan zamówienia sprzedaży nie zmienia się i mogą być wprowadzane kolejne faktury.

Stan zamówienia sprzedaży można wyświetlić na stronie listy **Wszystkie zamówienia sprzedaży**. Użyj strony listy **Otwarte faktury dla odbiorców**, aby przejrzeć faktury, które zostały zaksięgowane.

## <a name="post-and-print-individual-customer-invoices-that-are-based-on-packing-slips-and-the-date"></a>Księgowanie i drukowanie indywidualnych faktur dla odbiorcy na podstawie dokumentów dostawy i daty
Ten proces jest używany gdy jeden lub kilka dokumentów dostawy zostało zaksięgowanych dla zamówienia sprzedaży. Faktura dla odbiorcy jest oparta na takich właśnie dokumentach dostawy i odzwierciedla wielkości dostaw. Dane finansowe do faktury są oparte na informacjach wprowadzonych podczas księgowania faktury. 

Fakturę dla odbiorcy opartą na pozycjach wierszy dokumentu dostawy, które dotąd wysłano, można utworzyć nawet jeśli wszystkie pozycje dla danego zamówienia sprzedaży nie zostały jeszcze wysłane. Można tak uczynić jeśli, na przykład, co miesiąc jest wystawiana odbiorcy faktura, w której są wyszczególnione wszystkie dostawy zrealizowane w danym miesiącu. Każdy dokument dostawy odpowiada częściowej lub kompletnej dostawie towarów ujętych w zamówieniu sprzedaży. 

Po zaksięgowaniu faktury wartość **Pozostałe do zafakturowania** jest dla każdego towaru aktualizowana z uwzględnieniem całości dostaw w ramach wybranych dokumentów dostawy. Jeśli obydwie wartości **Pozostałe do zafakturowania** i **Pozostałe do dostarczenia** dla wszystkich towarów z zamówienia sprzedaży są zerowe (0), to zamówienie sprzedaży otrzymuje stan **Zafakturowane**. Jeśli ilość **Pozostałe do zafakturowania** jest równa zero (0), stan zamówienia sprzedaży nie zmienia się i mogą być wprowadzane kolejne faktury. 

Numer faktury dla transakcji magazynowych jest aktualizowany, a stan zamówienia sprzedaży w polu **Stan wiersza** na zamówieniu sprzedaży zmienił się na **Zafakturowane**. 

Stan zamówienia sprzedaży można wyświetlić na stronie listy **Wszystkie zamówienia sprzedaży**.

## <a name="consolidate-sales-orders-or-packing-slips-for-posting"></a>Konsolidowanie zamówień sprzedaży lub dokumentów dostawy do księgowania
Za pomocą tego procesu można wyświetlić jedno lub kilka zamówień sprzedaży, które są gotowe do zafakturowania, gdy trzeba skonsolidować je na jednej fakturze. 

Można wybrać wiele faktur na stronie listy **Zamówienie sprzedaży** i skonsolidować je za pomocą funkcji **Generuj faktury**. Na stronie **Księgowanie faktury** można zmienić ustawienie **Zamówienie zbiorcze** w celu podsumowania według numeru zamówienia (jeśli jest wiele dokumentów dostawy dla jednego zamówienia sprzedaży) lub według konta faktury (jeśli istnieje wiele zamówień sprzedaży dla jednego konta faktury). Użyj przycisku **Rozmieść**, aby konsolidować zamówienia sprzedaży na jednej fakturze na podstawie ustawienia **Zamówienie zbiorcze**.

## <a name="additional-settings-that-change-the-posting-behavior"></a>Dodatkowe ustawienia, które zmieniają działanie procesu księgowania
Następujące pola zmieniają działanie procesu księgowania.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Pole</th>
<th>Opis</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Ilość</td>
<td>Umożliwia wybranie ilości, na podstawie której ma się odbywać księgowanie dokumentu. Opcje znajdujące się w tym polu zależą od typu księgowanego dokumentu, na przykład dokument dostawy lub faktura.
<ul>
<li><strong>Dostawa teraz</strong> — zaznaczanie wszystkich ilości wprowadzonych w polu <strong>Dostawa teraz</strong>. Opcja ta umożliwia potwierdzenie lub dostarczenie zamówienia częściowego.</li>
<li><strong>Pobrane</strong> — zaznaczanie wszystkich ilości, które zostały pobrane.</li>
<li><strong>Wszystko</strong> — zaznaczanie wszystkich ilości w zamówieniu sprzedaży, które nie zostały jeszcze zaktualizowane przez bieżący typ dokumentu.</li>
<li><strong>Dokument dostawy</strong> — zaznaczanie wszystkich ilości, które zostały zaktualizowane przez dokument dostawy.</li>
<li><strong>Ilość pobrana i produkty niemagazynowane</strong> — zaznaczanie wszystkich ilości, które zostały pobrane, oraz wszystkich ilości produktów, które nie są magazynowane.</li>
</ul></td>
</tr>
<tr class="even">
<td>Księgowanie</td>
<td><ul>
<li>Wybranie tej opcji pozwala zapisywać zamówienie sprzedaży w arkuszu.</li>
<li>Jeśli ta opcja nie jest wybrana, drukowane jest zamówienie sprzedaży pro forma. <strong>Uwaga:</strong> jeśli zawarto umowę dotyczącą harmonogramu płatności, nie będzie on widoczny na zamówieniu sprzedaży pro forma. Harmonogramy płatności są wyświetlane tylko dla rzeczywistych zamówień sprzedaży.</li>
</ul></td>
</tr>
<tr class="odd">
<td>Wybierz później</td>
<td>Zaznaczenie tej opcji umożliwia zastosowanie wybranej kwerendy w późniejszym terminie. Ta opcja jest używana do zadań wsadowych. Kwerenda jest uruchamiana po uruchomieniu zadania wsadowego.</td>
</tr>
<tr class="even">
<td>Zmniejsz ilość</td>
<td>Zaznaczenie tej opcji spowoduje automatyczne zmniejszenie ilości dostarczanej podczas księgowania dokumentu, dzięki czemu ilość dostępnych zapasów jest równa ilości dostarczanej.</td>
</tr>
<tr class="odd">
<td>Drukuj</td>
<td>Określ, kiedy drukować dokumenty:
<ul>
<li><strong>Bieżące</strong> — drukowanie dokumentów po zaktualizowaniu każdej faktury.</li>
<li><strong>Po</strong> — drukowanie dokumentów po zaktualizowaniu wszystkich faktur.</li>
</ul>
<strong>Uwaga</strong> Pole <strong>Drukowanie</strong> jest dostępne tylko po wybraniu opcji <strong>Drukowanie faktury</strong>, <strong>Drukowanie potwierdzenia</strong>, <strong>Drukowanie listy pobrania</strong> lub <strong>Drukowanie dokumentu dostawy</strong>. Na przykład na stronie <strong>Sortowanie formularza</strong> się w systemie opcję sortowania informacji według konta fakturowania. Następnie możesz wybrać opcję <strong>Po</strong>, aby drukować dokumenty w partii, które są posortowane według konta faktury. W przeciwnym razie dokumenty są drukowane, zanim zakończy się przetwarzanie i dokumenty nie są sortowane w kolejności określonej na stronie <strong>Sortowanie formularzy</strong>.</td>
</tr>
<tr class="even">
<td>Drukuj fakturę</td>
<td>Tę opcję należy wybrać w celu wydrukowania faktury. Jeśli ta opcja jest wyłączona, można księgować fakturę bez jej drukowania.</td>
</tr>
<tr class="odd">
<td>Wyślij wiadomość e-mail</td>
<td>Wybierz tę opcję, aby wysłać fakturę dla zamówienia sprzedaży do odbiorcy jako załącznik do wiadomości e-mail po zaksięgowaniu faktury. Załączniki są wysyłane jako pliki PDF i XML. Ta opcja jest dostępna tylko po zaznaczeniu opcji <strong>Włącz CFD (faktury elektroniczne)</strong> na stronie <strong>Parametry faktury elektronicznej</strong>. <strong>Uwaga:</strong> (MEX) Ten formant jest dostępny tylko w firmach, których adresem podstawowym jest Meksyk.</td>
</tr>
<tr class="even">
<td>Wydrukuj na urządzeniu skonfigurowanym w opcjach zarządzania drukowaniem</td>
<td>Wybierz tę opcję, aby użyć ustawień wydruku określonych dla transakcji, dokumentu lub modułu na stronie <strong>Ustawienia zarządzania drukowaniem</strong>.</td>
</tr>
<tr class="odd">
<td>Sprawdzanie limitu kredytu</td>
<td>Umożliwia wybór informacji analizowanych podczas sprawdzania limitu kredytowego.
<ul>
<li><strong>Brak</strong> — nie ma wymogu przeprowadzania sprawdzenia limitu kredytu.</li>
<li><strong>Saldo</strong> — limit kredytu jest porównywany z saldem odbiorcy.</li>
<li><strong>Saldo + dokument dostawy lub dokument przyjęcia produktów</strong> — limit kredytu jest porównywany z saldem odbiorcy i dostawami.</li>
<li><strong>Saldo + wszystko</strong> — limit kredytu jest porównywany z saldem odbiorcy, dostawami i otwartymi zamówieniami.</li>
</ul></td>
</tr>
<tr class="even">
<td>Korekta z czerwonym stornem</td>
<td>Wybranie tej opcji pozwala wyświetlić fakturę korygującą jako debet w transakcjach załącznika.</td>
</tr>
<tr class="odd">
<td>Pozostała ilość kredytu</td>
<td>Jeśli księgowana jest faktura korygująca, tę opcję należy zaznaczyć, aby zachować na zamówieniu pozostałą ilość. Jeśli ta opcja jest wyczyszczona, pozostała ilość jest ustawiona na 0 (zero).</td>
</tr>
<tr class="even">
<td>Aktualizacja zbiorcza dla</td>
<td>Umożliwia wybranie sposobu, w jaki należy sumować wiele zamówień sprzedaży:
<ul>
<li><strong>Brak</strong> — nie należy sumować zamówień sprzedaży. Na przykład oddzielna faktura będzie tworzona dla każdego zamówienia sprzedaży.</li>
<li><strong>Konto płatnika</strong> — podsumowanie wszystkie wybranych zamówień w oparciu o kryteria ustawione na stronie <strong>Parametry aktualizacji zbiorczej</strong>.</li>
<li><strong>Zamówienie</strong> — należy zsumować wybrany zakres zamówień w jedno określone zamówienie. Zamówienia są sumowane na podstawie kryteriów, które zostały ustawione na stronie <strong>Parametry aktualizacji zbiorczej</strong>. Po wybraniu tej opcji należy wybrać wartość w polu <strong>Zamówienie sprzedaży</strong>.</li>
<li><strong>Podsumowanie automatyczne</strong> — jeśli aktualizacja podsumowania została określona na stronie <strong>Aktualizacja podsumowania</strong> należy zsumować wszystkie zaznaczone zamówienia zgodnie z kryteriami ustawionymi na stronie <strong>Parametry aktualizacji zbiorczej</strong>. Jeśli aktualizacja podsumowania nie została jeszcze określona, zamówienie jest księgowane oddzielnie.</li>
<li><strong>Dokument dostawy</strong> — należy zsumować wybrany zakres zamówień w jedną fakturę na dokument dostawy. Ta opcja jest dostępna tylko wtedy, gdy wybrano opcję <strong>Dokument dostawy</strong> w polu <strong>Ilość</strong>.</li>
</ul></td>
</tr>
</tbody>
</table>





