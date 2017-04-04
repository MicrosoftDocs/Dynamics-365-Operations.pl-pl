---
title: "Związane z produktem tłumaczenia często zadawane pytania"
description: "W tym temacie opisano sposób zarządzania tłumaczeniami produktów, wartości wymiarów produktu i atrybutów produktu."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: SysTranslationDetail, SysTranslationLanguage, SysTranslationList
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 201853
ms.assetid: c0286bba-f54b-42de-904c-81fd796bdd1d
ms.search.region: global
ms.search.industry: Product information
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: a9c991a5afaebd10b8812dfc1d67120ed4ebdfd2
ms.lasthandoff: 03/31/2017


---

# <a name="product-related-translations-faq"></a>Związane z produktem tłumaczenia często zadawane pytania

W tym temacie opisano sposób zarządzania tłumaczeniami produktów, wartości wymiarów produktu i atrybutów produktu. 

<a name="what-product-related-data-can-be-translated"></a>Jakie dane dotyczące produktów można przetłumaczyć?
--------------------------------------------

Można utworzyć tłumaczenia następujących informacji dotyczących produktu:
-   Nazwy i opisy produktów.
-   Opisy, przyjazne nazwy i tekst pomocy dla wartości atrybutów produktu.
-   Nazwy i opisy wartości wymiaru produktu.

Można tłumaczyć informacje dotyczące produktu na dowolny język, który jest dostępny ze strony **Tłumaczenie tekstu**. Aby uzyskać więcej informacji, zobacz sekcję **Jak utworzyć tłumaczenia informacji dotyczących produktów**.

## <a name="where-can-i-view-the-translated-information"></a>Gdzie można wyświetlić przetłumaczone informacje?
Tłumaczenia informacji dotyczących produktu można wyświetlić w każdym zewnętrznym dokumencie źródłowym, takim jak faktura, która używa języka, w którym są dostępne tłumaczenia.

## <a name="how-do-i-create-translations-for-productrelated-information"></a>Jak utworzyć tłumaczenia dla productrelated informacji?
Aby utworzyć tłumaczenia dla produktu, wykonaj następujące kroki:
1.  Kliknij **zarządzanie informacjami o produktach**&gt;**wspólne**&gt;**zwolnionych produktów**.
2.  Wybierz produkt, a w okienku akcji, w **języków** grupy, kliknij przycisk **tłumaczenia**.
3.  Na stronie **Tłumaczenie tekstu** w polu **Język** wybierz język. Aby dodać więcej języków, rozwiń **języka** polu, a następnie kliknij **OK**.
4.  W grupie **Przetłumaczony tekst** wprowadź tłumaczenia w polach **Opis** i **Nazwa produktu**.

Aby utworzyć tłumaczenia dla atrybutów produktu, wykonaj następujące kroki:
1.  Kliknij **zarządzanie informacjami o produktach**&gt;**wspólne**&gt;**zwolnionych produktów**.
2.  Na stronie **Ustawienia** kliknij kolejno opcje **Atrybuty** i **Atrybuty**.
3.  Na stronie **Atrybuty** kliknij przycisk **Przetłumacz**.
4.  Na stronie **Tłumaczenie tekstu** w polu **Język** wybierz język. Aby dodać więcej języków, rozwiń **języka** polu, a następnie kliknij **OK**.
5.  W grupie **Przetłumaczony tekst** wprowadź tłumaczenia w polach **Opis**, **Przyjazna nazwa** i **Tekst pomocy**.

Aby utworzyć tłumaczenia dla wartości wymiaru produktu, wykonaj następujące kroki:
1.  Kliknij **zarządzanie informacjami o produktach**&gt;**wspólne**&gt;**zwolnionych produktów**.
2.  Wybierz produkt i kliknij opcję **Wymiary produktu**.
3.  Wybierz jedno z łączy dla wymiarów produktu: **Konfiguracje**, **Rozmiary**, **Kolory** lub **Styl**.
4.  Wybierz wartość wymiaru, a następnie kliknij przycisk **Przetłumacz**.
5.  Na stronie **Tłumaczenie tekstu** w polu **Język** wybierz język. Aby dodać więcej języków, rozwiń **języka** polu, a następnie kliknij **OK**.
6.  W **przetłumaczony tekst** grupy, wprowadzić tłumaczenia w **nazwa** i **opis** pól.

## <a name="can-the-names-of-product-variants-be-translated"></a>Czy można przetłumaczyć nazwy wariantów produktów?
Warianty produktu są oparte na wymiarach zwolnionego produktu. Nazwy wariantów produktu są oparte na kombinacji wartości wymiarów. Jeśli wartości wymiarów, które są skojarzone z wariantem produktu, są tłumaczone, nazwa wariantu produktu zostanie wyświetlona w przetłumaczonej wersji.  

**Przykład **  

Produkt to koszulka, występująca w różnych rozmiarach i kolorach, a nazwy wariantów opierają się na następujących szczegółach:
-   Numer produktu: \#3
-   Wymiary: Rozmiar i kolor
-   Wartości wymiarów rozmiaru: Mały, Średni, Duży
-   Wartości wymiarów koloru: Czerwony, Zielony, Czarny

Nazwa wariantu produktu, który jest oparty na wymiar wartości małych a jest czerwony **\#3:Small:Red**.  

Odbiorca chce kupić małe, czerwone koszulki, a nazwa koszulki na fakturze musi być w języku francuskim. Przekształcania wartości wymiarów, małe i czerwony, język francuski, a Nazwa wariantu produktu jest **\#3: Petit: Rouge**.
<table>
<colgroup>
<col width="100%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Tip</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Aby ustawić preferowany język odbiorcy, wykonaj następujące kroki:
<ol>  
<li>Kliknij <strong>sprzedaży i marketingu</strong>&gt;<strong>wspólne</strong>&gt;<strong>klienci</strong>&gt;<strong>wszystkie</strong> <strong>klienci</strong>.</li>
<li>Kliknij dwukrotnie odbiorcę, a zostanie otwarta strona <strong>Odbiorcy</strong>. Na karcie <strong>Ogólne</strong> w polu <strong>Język</strong> wybierz <strong>język</strong>.</li>
</ol></td>
</tr>
</tbody>
</table>

## <a name="what-happens-if-a-customer-has-a-preferred-language-for-which-no-translations-are-available"></a>Co się stanie, jeśli odbiorca ma preferowany język, dla którego tłumaczenia nie są dostępne?
Jeśli tłumaczenia nie są dostępne w języku preferowanym przez odbiorcę, nazwy i opisy są wyświetlane w globalnym języku firmy.

## <a name="can-i-manage-translations-for-a-series-of-dimension-values-at-the-same-time"></a>Czy w tym samym czasie można zarządzać tłumaczeniami dla serii wartości wymiarów?
Wartości wymiarów są specyficzne dla produktu i można zarządzać tłumaczeniami dla wartości wymiarów dla każdego produktu. Jednakże, po utworzeniu grupy wartości wymiarów i stworzeniu tłumaczeń dla wartości w grupie wartości, łatwiej zarządzać tłumaczeniami.   

**Example**  

Firma produkuje koszulki w różnych stylach, a każdy styl jest dostępny w rozmiarach Mały, Średni i Duży. Rozmiary są gromadzone w jednej grupie wartości wymiarów. W przypadku dodawania nowego stylu koszulek, można skojarzyć go z grupą wartości wymiarów, która jest używana w przypadku rozmiarów, tak aby wszystkie rozmiary były dostępne dla produktu. Można też w dowolnym momencie dodać lub zmienić tłumaczenia rozmiarów w grupie wartości wymiarów.  

Wartość wymiaru skojarzona z produktem za pomocą grupy wariantów wymiaru musi zostać zachowana z grupy wariantów produktu.   
Aby utworzyć grupę wartości wymiaru, należy wykonać poniższe kroki:
1.  Kliknij **zarządzanie informacjami o produktach**&gt;**instalacji**&gt;**grupy wariantów**.
2.  Wybierz opcję **Grupy** **rozmiarów**, **Grupy kolorów** lub **Grupy stylów**.
3.  Kliknij **nowy**, a następnie wpisz nazwę dla grupy w **rozmiar****grupy**, **grupy kolorów**, lub **grupę stylów** pole. Kliknij opcję **Rozmiary**, **Kolory** lub **Style**, aby utworzyć wiersze dla grup.
4.  W **rozmiar****grupy** linie, **kolor****grupy****linii**, lub **wierszy grupy stylów** kliknij przycisk **nowy**, a następnie utworzyć rozmiarów, kolorów i stylów dla grup.

Aby zarządzać tłumaczeniami wartości w grupie wartości wymiarów, należy wykonać następujące czynności:
1.  Wykonaj kroki opisane w poprzedniej procedurze tworzenia grupy wartości wymiarów, aby otworzyć stronę **Wiersze grupy rozmiarów**, **Wiersze grupy kolorów** lub **Wiersze grupy stylów**.
2.  Kliknij opcję **Tłumaczenie tekstu**. W **tłumaczenie tekstu** strona w **przetłumaczony tekst** grupy, wprowadzić tłumaczenia w **nazwa** i **opis** pól.

## <a name="when-can-translations-of-productrelated-information-be-managed"></a>Kiedy można zarządzać tłumaczenia informacji productrelated?
Tłumaczeniami informacji dotyczących produktu można zarządzać w dowolnym momencie. Gdy tłumaczenia są aktualizowane dla wartości wymiaru skojarzonej z produktem, informacje o produkcie są aktualizowane, bez względu na to, czy produkt ma transakcje.




