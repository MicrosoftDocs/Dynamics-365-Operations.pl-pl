---
title: Tłumaczenia informacji dotyczących produktów — często zadawane pytania
description: W tym temacie opisano sposób zarządzania tłumaczeniami produktów, wartości wymiarów produktu i atrybutów produktu.
author: t-benebo
ms.date: 08/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SysTranslationDetail, SysTranslationLanguage, SysTranslationList, EcoResProductListPage, EcoResProductVariants, EcoResProductDetailsExtended, EcoResProductCreate, EcoResProductDetails, RetailSizeGroupTable, RetailStyleGroupTable, RetailColorGroupTable, PCTranslationLanguageLookup, EcoResProductCategory
audience: Application User
ms.reviewer: kamaybac
ms.custom: 201853
ms.assetid: c0286bba-f54b-42de-904c-81fd796bdd1d
ms.search.region: global
ms.search.industry: Product information
ms.author: benebotg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 24a341973b8648b1a697c8c07b6ecbc808e0e504
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/29/2021
ms.locfileid: "7570504"
---
# <a name="product-related-translations-faq"></a>Tłumaczenia informacji dotyczących produktów — często zadawane pytania

[!include [banner](../includes/banner.md)]

W tym temacie opisano sposób zarządzania tłumaczeniami produktów, wartości wymiarów produktu i atrybutów produktu. 

## <a name="what-product-related-data-can-be-translated"></a>Jakie dane dotyczące produktów można przetłumaczyć?

Można utworzyć tłumaczenia następujących informacji dotyczących produktu:
-   Nazwy i opisy produktów.
-   Opisy, przyjazne nazwy i tekst pomocy dla wartości atrybutów produktu.
-   Nazwy i opisy wartości wymiaru produktu.

Można tłumaczyć informacje dotyczące produktu na dowolny język, który jest dostępny ze strony **Tłumaczenie tekstu**. Aby uzyskać więcej informacji, zobacz sekcję **Jak utworzyć tłumaczenia informacji dotyczących produktów**.

## <a name="where-can-i-view-the-translated-information"></a>Gdzie można wyświetlić przetłumaczone informacje?
Tłumaczenia informacji dotyczących produktu można wyświetlić w każdym zewnętrznym dokumencie źródłowym, takim jak faktura, która używa języka, w którym są dostępne tłumaczenia.

## <a name="how-do-i-create-translations-for-product-related-information"></a>Jak utworzyć tłumaczenia informacji dotyczących produktów?
Aby utworzyć tłumaczenia dla produktu, wykonaj następujące kroki:
1.  Kliknij kolejno opcje **Zarządzanie informacjami o produktach** &gt; **Wspólne** &gt; **Zwolnione produkty**.
2.  Wybierz produkt, a następnie w okienku akcji w grupie **Języki** kliknij opcję **Tłumaczenia**.
3.  Na stronie **Tłumaczenie tekstu** w polu **Język** wybierz język. Aby dodać więcej języków, rozwiń pole **Język**, a następnie kliknij przycisk **OK**.
4.  W grupie **Przetłumaczony tekst** wprowadź tłumaczenia w polach **Opis** i **Nazwa produktu**.

Aby utworzyć tłumaczenia dla atrybutów produktu, wykonaj następujące kroki:
1.  Kliknij kolejno opcje **Zarządzanie informacjami o produktach** &gt; **Wspólne** &gt; **Zwolnione produkty**.
2.  Na stronie **Ustawienia** kliknij kolejno opcje **Atrybuty** i **Atrybuty**.
3.  Na stronie **Atrybuty** kliknij przycisk **Przetłumacz**.
4.  Na stronie **Tłumaczenie tekstu** w polu **Język** wybierz język. Aby dodać więcej języków, rozwiń pole **Język**, a następnie kliknij przycisk **OK**.
5.  W grupie **Przetłumaczony tekst** wprowadź tłumaczenia w polach **Opis**, **Przyjazna nazwa** i **Tekst pomocy**.

Aby utworzyć tłumaczenia dla wartości wymiaru produktu, wykonaj następujące kroki:
1.  Kliknij kolejno opcje **Zarządzanie informacjami o produktach** &gt; **Wspólne** &gt; **Zwolnione produkty**.
2.  Wybierz produkt i kliknij opcję **Wymiary produktu**.
3.  Wybierz jedno z łączy dla wymiarów produktu: **Konfiguracje**, **Rozmiary**, **Kolory** lub **Styl**.
4.  Wybierz wartość wymiaru, a następnie kliknij przycisk **Przetłumacz**.
5.  Na stronie **Tłumaczenie tekstu** w polu **Język** wybierz język. Aby dodać więcej języków, rozwiń pole **Język**, a następnie kliknij przycisk **OK**.
6.  W grupie **Przetłumaczony tekst** wprowadź tłumaczenia w polach **Nazwa** i **Opis**.

## <a name="can-the-names-of-product-variants-be-translated"></a>Czy można przetłumaczyć nazwy wariantów produktów?
Warianty produktu są oparte na wymiarach zwolnionego produktu. Nazwy wariantów produktu są oparte na kombinacji wartości wymiarów. Jeśli wartości wymiarów, które są skojarzone z wariantem produktu, są tłumaczone, nazwa wariantu produktu zostanie wyświetlona w przetłumaczonej wersji.  

**Przykład**  

Produkt to koszulka, występująca w różnych rozmiarach i kolorach, a nazwy wariantów opierają się na następujących szczegółach:
-   Numer produktu: \#3
-   Wymiary: Rozmiar i kolor
-   Wartości wymiarów rozmiaru: Mały, Średni, Duży
-   Wartości wymiarów koloru: Czerwony, Zielony, Czarny

Nazwa wariantu produktu oparta na wartościach wymiarów Mały i Czerwony to **\#3:Mały:Czerwony**.  

Odbiorca chce kupić małe, czerwone koszulki, a nazwa koszulki na fakturze musi być w języku francuskim. Tłumaczysz wartości wymiarów, Mały i Czerwony, na francuski, wówczas nazwa wariantu produktu to **\#3:Petit:Rouge**.
<table>
<colgroup>
<col width="100%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Porada</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Aby ustawić preferowany język odbiorcy, wykonaj następujące kroki:
<ol><br/><li>Kliknij kolejno opcje <strong>Sprzedaż i marketing</strong> &gt; <strong>Wspólne</strong> &gt; <strong>Odbiorcy</strong> &gt;> <strong>Wszyscy</strong> <strong>odbiorcy</strong>.</li>
<li>Kliknij dwukrotnie odbiorcę, a zostanie otwarta strona <strong>Odbiorcy</strong>. Na karcie <strong>Ogólne</strong> w polu <strong>Język</strong> wybierz <strong>język</strong>.</li>
</ol></td>
</tr>
</tbody>
</table>

## <a name="what-happens-if-a-customer-has-a-preferred-language-for-which-no-translations-are-available"></a>Co się stanie, jeśli odbiorca ma preferowany język, dla którego tłumaczenia nie są dostępne?
Jeśli tłumaczenia nie są dostępne w języku preferowanym przez odbiorcę, nazwy i opisy są wyświetlane w globalnym języku firmy.

## <a name="can-i-manage-translations-for-a-series-of-dimension-values-at-the-same-time"></a>Czy w tym samym czasie można zarządzać tłumaczeniami dla serii wartości wymiarów?
Wartości wymiarów są specyficzne dla produktu i można zarządzać tłumaczeniami dla wartości wymiarów dla każdego produktu. Jednakże, po utworzeniu grupy wartości wymiarów i stworzeniu tłumaczeń dla wartości w grupie wartości, łatwiej zarządzać tłumaczeniami.   

**Przykład**  

Firma produkuje koszulki w różnych stylach, a każdy styl jest dostępny w rozmiarach Mały, Średni i Duży. Rozmiary są gromadzone w jednej grupie wartości wymiarów. W przypadku dodawania nowego stylu koszulek, można skojarzyć go z grupą wartości wymiarów, która jest używana w przypadku rozmiarów, tak aby wszystkie rozmiary były dostępne dla produktu. Można też w dowolnym momencie dodać lub zmienić tłumaczenia rozmiarów w grupie wartości wymiarów.  

Wartość wymiaru skojarzona z produktem za pomocą grupy wariantów wymiaru musi zostać zachowana z grupy wariantów produktu.   
Aby utworzyć grupę wartości wymiaru, należy wykonać poniższe kroki:
1.  Kliknij kolejno opcje **Zarządzanie informacjami o produktach** &gt; **Ustawienia** &gt; **Grupy wariantów**.
2.  Wybierz opcję **Grupy** **rozmiarów**, **Grupy kolorów** lub **Grupy stylów**.
3.  Kliknij opcję **Nowy**, a następnie wprowadź nazwę grupy w polu **Grupa** **rozmiarów**, **Grupa kolorów** lub **Grupa stylów**. Kliknij opcję **Rozmiary**, **Kolory** lub **Style**, aby utworzyć wiersze dla grup.
4.  Na stronie **Wiersze grupy** **rozmiarów**, **Wiersze** **grupy** **kolorów** lub **Wiersze grupy stylów** kliknij przycisk **Nowy**, a następnie utwórz rozmiary, kolory lub style dla grup.

Aby zarządzać tłumaczeniami wartości w grupie wartości wymiarów, należy wykonać następujące czynności:
1.  Wykonaj kroki opisane w poprzedniej procedurze tworzenia grupy wartości wymiarów, aby otworzyć stronę **Wiersze grupy rozmiarów**, **Wiersze grupy kolorów** lub **Wiersze grupy stylów**.
2.  Kliknij opcję **Tłumaczenie tekstu**. Na stronie **Tłumaczenie tekstu** w grupie **Przetłumaczony tekst** wprowadź tłumaczenia w polach **Nazwa** i **Opis**.

## <a name="when-can-translations-of-product-related-information-be-managed"></a>Kiedy można zarządzać tłumaczeniami informacji dotyczących produktu?
Tłumaczeniami informacji dotyczących produktu można zarządzać w dowolnym momencie. Gdy tłumaczenia są aktualizowane dla wartości wymiaru skojarzonej z produktem, informacje o produkcie są aktualizowane, bez względu na to, czy produkt ma transakcje.







[!INCLUDE[footer-include](../../includes/footer-banner.md)]