---
title: Materiały opakowań i opłaty
description: Ten temat zawiera informacje dotyczące opłat materiałów opakowań zastosowanych do firm zajmujących się recyklingiem w określonych interwałach czasu.
author: MarkusFogelberg
manager: tfehr
ms.date: 02/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventPackagingGroup, InventPackagingMaterialCode, InventPackagingMaterialFee, InventPackagingMaterialTrans, InventPackagingMaterialTransPurch, InventPackagingUnit
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2194
ms.assetid: 040b65dc-43c9-4256-b69f-b2d6e736fbe9
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2020-02-19
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e5364336c5336cbb91caf3c03564f68371273079
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4973642"
---
# <a name="packing-materials-and-fees"></a>Materiały opakowań i opłaty

[!include [banner](../includes/banner.md)]

Opłaty za materiały opakowań są uiszczane firmie recyklingowej w określonych odstępach czasu. Płaci się kwotę według jednostki masy za każdy materiał, z którego jest wykonana jednostka opakowania. Mimo że opłaty za materiały opakowań są obliczane i zgłaszane, nie są księgowane żadne transakcje księgi, ponieważ opłaty nie są uważane za podatki, które należy wpłacić właściwemu organowi.

Wagi materiałów opakowań i opłaty są obliczane dla wierszy zamówienia sprzedaży i zakupu.

Możesz zdefiniować jedną lub więcej jednostek opakowania dla pojedynczego towaru, grupy towarów (grupy pakowania) lub wszystkich towarów. W skład jednostki załadunkowej oprócz towarów, z których jednostka się składa, wchodzą różne materiały opakowań oraz ich wagi. Kod materiału opakowań jest przypisany do każdego zdefiniowanego typu materiału opakowania. Na podstawie kodu materiału opakowania można określić cenę w określonym okresie. Opłata za materiały opakowań jest obliczana na podstawie tych informacji.

> [!NOTE]
> Nawet jeśli firma nie uiszcza opłat materiałowych opakowań, można użyć tej funkcji do obliczania statystyk wag materiałów opakowań.

## <a name="set-up-packing-material-allocation"></a><a name="allocations"></a>Skonfiguruj przydział materiałów opakowań

Aby można było obliczyć wagi materiałów opakowań, opłaty za materiały opakowań lub oba te elementy, należy włączyć obliczenia i określić, które materiały i opłaty będą stosowane dla poszczególnych towarów.

1. Wybierz kolejno opcje **Zarządzanie zapasami \> Ustawienia \> Parametry modułu Zarządzanie zapasami i magazynem**.
1. Na karcie **ogólne**, w sekcji **Materiał opakowania**, dla opcji **Oblicz opłaty materiałowe opakowań** określ wartość **Tak**.
1. Przejdź do **Zarządzanie zapasami \> Ustawienia \> Materiał opakowania \> Grupy opakowań** i utwórz grupy opakowań, których używasz. Wszystkie towary w grupie opakowań używają tej samej alokacji materiałów opakowań. Jeśli nie są używane grupy opakowań, można pominąć ten krok.

    > [!TIP]
    > Po utworzeniu grup opakowań można przypisać grupę do każdego produktu w miarę potrzeb. Przejdź do **Zarządzanie informacjami o produktach \> Produkty \> Zwolnione produkty**, wybierz produkt, a następnie na skróconej karcie **Zarządzanie zapasami** w polu **Grupa opakowań** wybierz odpowiednią grupę opakowań.

1. Przejdź do **Zarządzanie zapasami \> Ustawienia \> Materiał opakowania \> Kody materiału opakowania**, zdefiniuj każdy typ używanego materiału opakowania oraz określ jednostkę, w której jest zużywany materiał opakowania podczas przygotowywania wysyłek.
1. Przejdź do **Zarządzanie zapasami \> Ustawnienia \> Materiał opakowania \> Opłaty materiałowe opakowań**, i określ opłatę dla każdego typu materiału opakowania, który jest właśnie zdefiniowany. Opłaty są obliczane na podstawie ceny jednostki, która jest zużywana.
1. Aby alokować materiały opakowań do towarów, należy przejść **Zarządzanie zapasami \> Ustawienia \> Materiał opakowania \> Alokacja materiałów opakowań** i utworzyć alokacje materiałów opakowań. Można utworzyć dowolną liczbę alokacji zależnie od potrzeb. Istnieje możliwość alokowania materiałów opakowań dla poszczególnych towarów, grup towarów (grup opakowań) lub wszystkich towarów, w zależności od tego, jak szczegółowe mają być alokacje.

    Dla każdej utworzonej alokacji należy wykonać następujące czynności.

    1. Na skróconej karcie **Ogólne** ustaw następujące pola:

        - **Kod towaru** — umożliwia wybór zakresu alokacji:

            - **Tabela** — służy do tworzenia alokacji dla jednego konkretnego towaru.
            - **Grupa** — umożliwia utworzenie alokacji wszystkich towarów należących do grupy opakowań zdefiniowanej na stronie **Grupy opakowań**.
            - **Wszystko** — umożliwia tworzenie alokacji dla wszystkich towarów.

            > [!NOTE]
            > Zazwyczaj wszystkie alokacje powinny być dokonywane na tym samym poziomie (**Tabela**, **Grupa** lub **Wszystko**). Jeśli jest używany więcej niż jeden poziom, dla każdego towaru będzie używana najbardziej odpowiednia alokacja. (Poziom **Tabeli** ma pierwszeństwo przed poziomem **Grupy**, a oba poziomy mają pierwszeństwo przed poziomem **Wszystko**.)

        - **Relacja towaru** — Jeśli alokacja jest dokonywana dla jednego towaru, należy wybrać towar. Jeśli alokacja jest wykonywana dla grupy towarów, należy wybrać grupę opakowań. Jeśli alokacja jest przydzielna dla wszystkich towarów, pole należy pozostawić puste.
        - **Konfiguracja**, **Rozmiar**, **Kolor** i **Styl** — wprowadź wartości dla tych wymiarów, aby dokładniej zdefiniować towar, dla którego jest przydzielana alokacja.
        - **Jednostka opakowania** — umożliwia wybór jednostki, w której jest pakowany towar, gdy jest używany materiał opakowania. Ta jednostka może być inna niż jednostka, w której jest nabywany towar i w którym jest przechowywana.
        - **Współczynnik jednostki opakowania** — umożliwia wprowadzenie współczynnika konwersji używanego do konwersji z jednostki magazynowej na jednostkę opakowania. (Konwersja używa wzoru *Jednostki opakowania* = *Jednostki towaru* × *Współczynnik jednostki opakowania*.)

    1. W skróconej karcie **Materiału opakowania** należy dodać wiersz dla każdej sztuki materiału opakowania wymaganej do bieżącej alokacji. W każdym wierszu należy określić typ materiału (zgodnie z definicją na stronie **Kody materiałów opakowań**) oraz kwotę, która jest zużywana dla każdej jednostki wysłanej z bieżącego towaru.

## <a name="packing-units-on-sales-order-lines"></a>Jednostki opakowań w wierszach zamówienia sprzedaży

Po [włączeniu obliczeń dotyczących opłat za materiały opakowań i skonfigurowaniu alokacji system sprawdza](#allocations), czy jednostki opakowań są określone dla każdego towaru dodawanego do zamówienia sprzedaży. Następnie obliczane są wszelkie wymagane opłaty. Po dodaniu towaru do zamówienia sprzedaży jest wykonywana jedna z następujących czynności:

- **Jeśli określono alokację opakowań dla towaru:** System aktualizuje wiersz zamówienia sprzedaży o określoną jednostkę opakowania i liczbę jednostek opakowania. (Liczba jednostek opakowań jest obliczana na podstawie wzoru *Liczba jednostek opakowania* = *Ilość zamówiona* ÷ *Liczba towarów w wybranej jednostce opakowań*.)
- **Jeśli alokacja opakowań nie została określona dla towaru:** Możesz ręcznie wprowadzić jednostkę opakowania i ilość jednostki opakowania w wierszu zamówienia sprzedaży.

Istnieje również możliwość zmiany jednostki opakowań oraz liczby jednostek opakowań podczas księgowania wiersza zamówienia sprzedaży. Ta możliwość jest istotna w sytuacji, w której wiersz zamówienia sprzedaży jest tylko częściowo dostarczony lub częściowo zafakturowany.

Podczas fakturowania zamówienia sprzedaży system tworzy transakcje dotyczące materiałów opakowań. Transakcje materiałów opakowań zawierają wagi materiałów opakowań w wierszu sprzedaży. Transakcje można modyfikować po ich zafakturowaniu. Następnie można utworzyć nowe transakcje.

## <a name="packing-units-on-purchase-order-lines"></a>Jednostki opakowań w wierszach zamówienia zakupu

System nie tworzy transakcji materiałów opakowań dla wierszy zamówienia zakupu. Zamiast tego ręcznie tworzy się transakcje dla wierszy na fakturze zamówienia zakupu na stronie **Transakcje materiałów opakowań**.

## <a name="set-up-license-numbers-for-customers-that-are-charged-packing-material-fees"></a>Konfigurowanie numerów licencji dla odbiorców, którzy są obciążani opłatami materiałów opakowań

Jeśli zamówienia sprzedaży dla określonego odbiorcy powinny zawierać opłaty związane z materiałami opakowania używanymi dla poszczególnych zamówień, należy wykonać następujące kroki.

1. Wybierz kolejno opcje **Rozrachunki z odbiorcami \> Odbiorcy \> Wszyscy odbiorcy**.
1. Umożliwia wybór odbiorcy, który powinien być obciążany materiałami opakowania.
1. Na skróconej karcie **Faktura i dostawa** ustaw następujące pola:

    - W sekcji **Podatek** w polu **Licencja opłat od opakowań** wprowadź numer licencji firmy.
    - W sekcji **Opłata materiałowa opakowań** w polu **Numer licencji** wprowadź numer licencji firmy.

Teraz podczas tworzenia i fakturowania zamówienia sprzedaży zawierającego jeden lub więcej towarów, które korzystają z materiałów opakowań, faktura będzie zawierać opłaty materiałowe opakowań.

W przypadku odbiorców, którzy nie powinni płacić opłat materiałowych opakowań, należy wykonać te same kroki, ale usunąć numery **Licencja opłat od opakowań** i **Numer licencji**. Faktury dla odbiorców, którzy nie zapłacili opłat za materiały opakowań, pokazują wagi materiałów opakowania, ale nie będą w nich wyświetlane opłaty.

Aby wygenerować raport pokazujący wszystkie opłaty materiałowe opakowań, które firma jest winna w określonym okresie, należy przejść do **Zarządzanie zapasami \> Zapytania i raporty \> Raporty materiałów opakowań \> Obliczanie opłat materiałowych opakowania**, określić zakres dat, a następnie wybrać **OK**.

## <a name="print-packing-material-weights-on-invoices"></a>Drukowanie wag materiałów opakowań na fakturach

Możesz wydrukować wagi materiałów opakowań na fakturze i wskazać, kto płaci powiązane opłaty. Wagi zestawione są na podstawie kodu opakowania.

1. Wybierz kolejno pozycje **Rozrachunki z odbiorcami \> Ustawienia \> Parametry modułu rozrachunków z odbiorcami**.
1. Na karcie **Aktualizacje** na skróconej karcie **Faktury** określ opcję **Drukuj wagę materiału opakowania** na **Tak**.
