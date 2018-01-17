---
title: "Śledzenie towarów i surowców w zapasach, produkcji i sprzedaży"
description: "W tym temacie opisano sposób korzystania ze śledzenia towaru do identyfikowania, gdzie towary lub surowce zostały użyte, są używane lub będą używane w produkcji i procesach sprzedaży."
author: perlynne
manager: AnnBe
ms.date: 11/02/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventTrackingDimTracing, InventTrackingDimTracingCriteria
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 30191
ms.assetid: fdd0939a-855c-430f-a684-94f3baea1df4
ms.search.region: Global
ms.author: pjacobse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 2dd3709ae55e32ec2e5258ced2764c4eb218a4c4
ms.contentlocale: pl-pl
ms.lasthandoff: 11/03/2017

---

# <a name="item-and-raw-material-tracing-in-inventory-production-and-sales"></a>Śledzenie towarów i surowców w zapasach, produkcji i sprzedaży

[!include[banner](../includes/banner.md)]


W tym temacie opisano sposób korzystania ze śledzenia towaru do identyfikowania, gdzie towary lub surowce zostały użyte, są używane lub będą używane w produkcji i procesach sprzedaży.

Funkcja śledzenia zapasów jest dostępna na stronie **Śledzenie towaru**. W poniższych sekcjach opisano sposób korzystania ze śledzenie towaru oraz istniejące opcje i ograniczenia.

## <a name="what-is-item-tracing"></a>Co to jest śledzenie towaru?
Śledzenie towaru to narzędzie analizy biznesowej (BI), które zapewnia wgląd w miejsce źródłowe i docelowe towarów i surowców w łańcuchu dostaw. Producenci mogą śledzić towary, surowce lub składniki wstecz do dostawcy, a w przód przez produkcję i sprzedaż produktu końcowego. Śledzenie towarów pomaga producentom zachowywać zgodność z wymogami regulacyjnymi, a dyrektorzy jakości i menedżerowie produkcji mogą analizować i podejmować działania, aby zaradzić odchyleniom jakości produktów i materiałów. Oto kilka przykładów wykorzystania mechanizmu śledzenia towarów u producentów:

-   Określanie ilości towaru lub surowca, która znajduje się obecnie w zapasach, oraz miejsca, gdzie jest przechowywana.
-   Określanie ilości towarów lub surowca, która została wysłana i do których odbiorców.
-   Określanie wszelkich planowanych wysyłek zawierających towar lub surowiec.
-   Znajdowanie zleceń produkcyjnych, które używają towaru lub surowca, oraz które są zaplanowane, w toku lub zgłoszone jako gotowe.
-   Dowiadywanie się, gdzie został zakupiony towar lub surowiec.
-   Sprawdzanie, gdzie towar lub surowiec został zużyty w produkcji innego towaru.

## <a name="what-can-i-trace-and-are-there-any-limitations"></a>Co mogę śledzić i czy są ograniczenia?
Możesz śledzić historyczne transakcje magazynowe dla towarów i surowców na podstawie numeru towaru i wymiarów śledzenia, takich jak numer seryjny, numer partii lub numer partii dostawcy. Towar lub surowiec można śledzić tylko wtedy, gdy ma przypisany wymiar śledzenia. Ponieważ śledzenie jest oparte na transakcjach magazynowych, istnieją pewne ograniczenia podczas śledzenia towarów. Na przykład istnieją ograniczenia dotyczące transakcji obejmujących projekty, środki trwałe i sprzedaż detaliczną. Ponadto produkty towarzyszące będą wyświetlane w szczegółach śledzenia, ale produkty uboczne nie są uwzględniane. Śledzenie uwzględnia wszystkie transakcje magazynowe między dwoma lokalizacjami. Dlatego ilość wyświetlany informacji może być bardzo duża. Śledzenie jest wyświetlane dla jednej firmy na raz. W kontekście międzyfirmowym nie ma funkcji międzyfirmowych. Należy uruchomić nowe śledzenie dla każdej firmy, w której towar jest przyjmowany lub wydawany.

## <a name="what-criteria-can-i-specify-for-an-item-trace"></a>Jakie kryteria można określić dla śledzenia towaru?
Kryteria wymagane dla śledzenia towaru to numer towaru, wymiar śledzenia (taki jak numer partii lub numer seryjny) oraz kierunek. W poniższej tabeli opisano kryteria, których można używać do śledzenia towaru.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Grupa pola</th>
<th>Opis</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Numer pozycji</td>
<td>Służy do wprowadzania identyfikatora towaru lub surowca, który jest śledzony.</td>
</tr>
<tr class="even">
<td>Wymiary produktu</td>
<td>Opcjonalnie: Śledzenie szczególnych aspektów definicji produktu, takich jak konfiguracja, rozmiar, kolor lub styl.</td>
</tr>
<tr class="odd">
<td>Wymiary śledzenia</td>
<td>Służy do wprowadzania wymiaru śledzenia: numeru partii, numeru partii dostawcy lub numeru seryjnego. Gdy używasz numeru partii jako kryterium, numer partii dostawcy jest wyświetlany, jeśli zarejestrowano tę informację.</td>
</tr>
<tr class="even">
<td>Wymiary magazynowania</td>
<td>Opcjonalnie: Śledzenie towarów, które były przechowywane w określonej lokalizacji.</td>
</tr>
<tr class="odd">
<td>Okres</td>
<td>Opcjonalnie: Wprowadzanie dat, aby ograniczyć śledzenie do określonego okresu. W szczegółach śledzenia zostaną wyświetlone tylko dokumenty i transakcje, które zostały utworzone między tymi datami.</td>
</tr>
<tr class="even">
<td>W przód lub w tył</td>
<td>Wybieranie kierunku śledzenia. Można śledzić do przodu lub wstecz:
<ul>
<li><strong>Wstecz</strong> — Umożliwia śledzenie do początku, aby zidentyfikować źródło, ilość pozostającą na stanie i wszelkie zlecenia produkcyjne, które są co najmniej częściowo zgłoszone jako gotowe.</li>
<li><strong>W przód</strong> — Umożliwia śledzenie od początku w celu zidentyfikowania miejsca docelowego. Można znaleźć zamówienia sprzedaży i odbiorców, do których śledzony towar lub surowiec został co najmniej częściowo wysłany.</li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="what-information-is-included-in-the-trace-details"></a>Jakie informacje zawierają szczegóły śledzenia?
Wyniki śledzenia są wyświetlane w porządku chronologicznym w drzewie na skróconej karcie **Szczegóły** na karcie **Śledzenie towaru**. Kolejność zmienia się w zależności od kierunku śledzenia. Szczegóły uwzględniają wszystkie transakcje — od zakupu towaru od dostawcy aż do sprzedania go odbiorcy. Wyniki śledzenia zawierają także tymczasowe produkty, które są powiązane z towarem lub wymiarem śledzenia, który został określony w kryteriach śledzenia. Węzeł najwyższego poziomu pokazuje ilość towaru (w jednostce magazynowej), która pozostaje na stanie, zgodnie z wymiarami przechowywania określonymi w kryteriach śledzenia. **Uwaga:** Szczegóły śledzenia to migawka informacji, które były dostępne w chwili wykonania śledzenia. Szczegóły śledzenia nie zostaną zaktualizowane, jeśli informacje się zmienią po wykonaniu śledzenia.

## <a name="why-dont-some-nodes-contain-any-details"></a>Dlaczego niektóre węzły nie zawierają żadnych szczegółów?
Aby zmniejszyć ilość informacji w szczegółach śledzenia, tylko węzeł pierwszego wystąpienia towaru lub surowca zawiera szczegóły. Jeśli wybrany węzeł nie zawiera szczegółów, można wyświetlić węzeł, który je zawiera, klikając opcję **Przejdź do śledzonego wiersza**. Następnie można wrócić do opuszczonego węzła, klikając przycisk **Powrót**.

## <a name="can-i-view-only-a-particular-type-of-document-for-example-can-i-view-only-production-orders-customers-or-vendors"></a>Czy można wyświetlać tylko określony typ dokumentu? Na przykład, czy można wyświetlić tylko zlecenia produkcyjne, odbiorców lub dostawców?
Tak, z okna szczegółów śledzenia można otworzyć strony listy zawierające tylko określony typ dokumentu lub transakcji. Do tych stron można przejść z elementu menu **Śledzenie** w okienku akcji wyświetlanym w grupach **Pozycja**, **Sprzedaż**, **Zakup**, **Produkcja** i **Jakość**. Na przykład aby wyświetlić listę dostawców w szczegółach śledzenia, kliknij kolejno opcje **Śledzenie** &gt; **Zakup** &gt; **Dostawcy**. Strony list podsumowują dokumenty lub transakcje na podstawie szczegółów śledzenia. Strony listy **Transakcje oczekujące**, **Zamówienia oczekujące** i **Zamówienie sprzedaży, towary niewysłane** również pokazują informacje, które nie są uwzględnione w szczegółach śledzenia. Ponadto zawsze przedstawiają wyniki na bieżący dzień, nawet jeśli określono zakres dat. W poniższej tabeli przedstawiono dodatkowe informacje, które te strony mogą obejmować.

| Listy                    | Opis                                                                                                                                                                                                                                                                                                                   |
|--------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Zamówienie sprzedaży, towary niewysłane | Wyświetlanie wierszy zamówienia sprzedaży, które jeszcze nie zostały pobrane i dlatego nie są wyświetlane w szczegółach śledzenia.                                                                                                                                                                                                                        |
| Zamówienia oczekujące           | Służy do wyświetlania wszystkich oczekujących zleceń produkcyjnych dla śledzonego zapasu, niezależnie od tego, które wymiary śledzenia zostały użyte w kryteriach śledzenia. Można także wyświetlić oczekujące zlecenia produkcyjne, w których towar śledzony jest składnikiem oraz nie dokonano rejestracji ani nie zgłoszono żadnych transakcji jako gotowych dla zamówienia. |
| Transakcje oczekujące     | Umożliwia wyświetlenie oczekujących transakcji magazynowych dla towaru śledzonego, które zawierają określone wymiary śledzenia lub puste wymiary śledzenia. Można także wyświetlić oczekujące transakcje magazynowe dla towarów i kombinacji wymiarów śledzenia lub pustej wartości w szczegółach śledzenia.                                                |

## <a name="how-many-levels-can-i-trace-up-or-down-in-a-bom-or-formula"></a>Jak wiele poziomów mogę śledzić w górę lub w dół w BOM lub formule?
W liście składowej (BOM) lub formule można śledzić jeden poziom w górę lub w dół. Na przykład, po uruchomieniu śledzenia surowców, widać produkty gotowe i towarzyszące. Jeśli jednak śledzisz produkt towarzyszący, szczegóły śledzenia nie obejmują gotowego produktu.

## <a name="how-can-i-view-more-details-about-a-document-or-transaction-in-the-trace-details"></a>Jak wyświetlić więcej szczegółów na temat dokumentu lub transakcji w szczegółach śledzenia?
Na skróconej karcie **Szczegóły** istnieją dwa sposoby wyświetlania większej ilości informacji w szczegółach śledzenia wybranego dokumentu lub transakcji:

-   Po wybraniu węzła w szczegółach śledzenia na skróconej karcie **Szczegóły** inne skrócone karty na stronie wyświetlają informacje dotyczące dokumentu lub transakcji w węźle.
-   Otwórz stronę szczegółów dokumentu w wybranym węźle, klikając przycisk **Wyświetl szczegóły**. Na przykład jeśli wybierzesz węzeł, który opisuje zlecenie produkcyjne, i klikniesz przycisk **Wyświetl szczegóły**, zostanie wyświetlona strona **Szczegóły zlecenia produkcyjnego**.

Niektóre skrócone karty zapewniają dostęp do dodatkowych informacji na temat wybranego węzła. Na przykład na skróconej karcie **Niezgodności** można kliknąć opcję **Zapytania** i zbadać, czy istnieje historia niezgodności. Na skróconej karcie **Partia** można kliknąć opcję **Lista dostępnych**, aby wyświetlić ilość zapasów fizycznych, która jest aktualnie na stanie, oraz wszelkie transakcje magazynowe dotyczące tej partii.

## <a name="can-i-run-more-than-one-trace-and-then-compare-the-details"></a>Czy można uruchomić więcej niż jedno śledzenie, a następnie porównać szczegóły?
Po uruchomieniu śledzenia można użyć następujących opcji na przycisku **Śledź od węzła**, aby uruchomić nowe śledzenie transakcji w wybranym węźle:

-   **Wstecz** lub **W przód** — Uruchomienie nowego śledzenia dla wybranego węzła i zastąpienie szczegółów bieżącego śledzenia.
-   **Nowe śledzenie wstecz** lub **Nowe śledzenie w przód** — Uruchomienie nowego śledzenia w nowym oknie i zachowanie szczegółów bieżącego śledzenia.

Jeśli chcesz użyć opcji **Nowe śledzenie wstecz** lub **Nowe śledzenie w przód**, należy użyć funkcji **Otwórz w nowym oknie**, aby nowe śledzenie było wyświetlane w nowym oknie.

## <a name="can-i-save-the-trace-details"></a>Czy mogę zapisać szczegóły śledzenia?
Informacje można zapisać na karcie **Szczegóły** jako plik XML, klikając przycisk **Eksport** pod akcją ****Śledzenie**** w okienku akcji. Oprócz szczegółów śledzenia plik XML zawiera kryteria śledzenia, węzeł nadrzędny oraz ilość na stanie. Możliwość zapisywania szczegółów śledzenia przydaje się, jeśli na przykład chcesz dołączyć informacje do zlecenia kontroli jakości lub innej dokumentacji zgodności z przepisami. Można określić, gdzie jest zapisany plik. Aby od razu wyświetlić plik, zaznacz opcję **Pokaż dokument**. **Uwaga:** Plik jest zawsze zapisywany, nawet jeśli chcesz go tylko wyświetlić. Domyślnie plik XML zostanie otwarty w oknie przeglądarki. Jednak można to zmienić, klikając prawym przyciskiem myszy plik, wybierając polecenie **Otwórz za pomocą**, a następnie wybierając program, który ma zostać użyty do wyświetlania zawartości.

## <a name="can-i-calculate-a-balance-for-a-particular-item-or-ingredient"></a>Czy można obliczyć saldo dla określonego towaru lub składnika?
Można eksportować informacje ze stron podsumowania do programu Microsoft Excel. Otwórz odpowiednią stronę, kliknij ikonę **Otwórz w pakiecie Microsoft Office**, a następnie zaznacz opcję **Eksportuj do programu Microsoft Excel**. Ta funkcja jest szczególnie użyteczna, gdy chcesz obliczyć zbiorcze saldo towaru lub składnika ze strony **Podsumowanie transakcji**. Na stronie **Podsumowanie transakcji** można wyfiltrować według towaru lub składnika, a opcjonalnie również według partii, a następnie wyeksportować informacje do programu Excel. W programie Excel można na przykład wyodrębnić ilość zapasów na stanie, ilość sprzedaną oraz ilość użytą w produkcji.

## <a name="can-i-investigate-whether-there-is-a-history-of-issues-with-items-or-raw-materials"></a>Czy można sprawdzić, czy istnieje historia problemów dotyczących towarów lub surowców?
Szczegóły śledzenia zawierają informacje o zleceniach kontroli jakości i niezgodnościach dotyczących towaru lub surowca. Aby wyświetlić podsumowanie zleceń kontroli jakości i niezgodności, w okienku akcji kliknij opcję **Zlecenia kontroli jakości** lub **Niezgodności**. **Uwaga:** Niszczące zlecenia kontroli jakości mogą się pojawić więcej niż raz w szczegółach śledzenia. Po utworzeniu niszczącego zlecenia kontroli jakości dla dokumentu, na przykład zamówienia zakupu, jest ono wyświetlane dla każdej z udziałem tego dokumentu.

## <a name="are-there-any-reporting-capabilities-that-are-related-to-item-tracing"></a>Czy istnieją funkcje raportowania związane ze śledzeniem towaru?
Można wygenerować raport **Wysłane do klientów** w celu zidentyfikowania ilości towaru lub surowca, która została wysłany, oraz odbiorców, do których została wysłana. W przypadku zapytania powiązanego ze zgodnością z przepisami można wygenerować raport obejmujący wszystkich odbiorców. W przypadku zapytania powiązanego ze obsługą klientów można wygenerować raport dla wybranego odbiorcy. Jeśli produkt był surowcem użytym w produkcji towaru gotowego produktu, gotowy towar jest również uwzględniony. **Uwaga:** Jeśli używasz funkcji usuwania lub archiwizacji zamówień sprzedaży, wyniki raportów zawierają również wszelkie zamówienia sprzedaży, które zostały usunięte lub zarchiwizowane.

## <a name="can-i-trace-coproducts-and-byproducts"></a>Czy mogę śledzić produkty towarzyszące i produkty uboczne?
Można śledzić produkty towarzyszące, ale nie można śledzić produktów ubocznych, ponieważ wymiary śledzenia zwykle nie są przypisane do produktów ubocznych. Podczas śledzenia towaru szczegóły śledzenia uwzględniają wszelkie pokrewne produkty towarzyszące. Węzeł, który zawiera produkt towarzyszący, zawiera określenie „co-product” (produkt towarzyszący) w szczegółach. Można również wyświetlić szczegóły dotyczące produktu towarzyszącego, zaznaczając węzeł w szczegółach śledzenia, a następnie klikając skróconą kartę **Produkcja**.

