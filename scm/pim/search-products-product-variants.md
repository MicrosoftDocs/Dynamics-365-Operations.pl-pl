---
title: "Wyszukiwanie produktów i wariantów produktów podczas wprowadzania zamówień"
description: "Za pomocą pola <strong>Numer pozycji</strong> można szukać produktów i wariantów produktów podczas ręcznego tworzenia wiersza zamówienia sprzedaży lub zakupu.  Dzięki temu można szybko znaleźć warianty produktu, gdy znasz tylko fragment konfiguracji lub jeden wymiar produktu."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: MCRFullTextIndexField, MCRFullTextParameters, PurchTable, SalesTable
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 248534
ms.assetid: 99dd5ce1-0029-4f06-90e7-865e6d46d86e
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: 9848b70dd6df4d9e3ff616e1a103a5e6ec5b5d05
ms.contentlocale: pl-pl
ms.lasthandoff: 04/25/2017


---

# <a name="search-for-products-and-product-variants-during-order-entry"></a>Wyszukiwanie produktów i wariantów produktów podczas wprowadzania zamówień

[!include[banner](../includes/banner.md)]


Za pomocą pola <strong>Numer pozycji</strong> można szukać produktów i wariantów produktów podczas ręcznego tworzenia wiersza zamówienia sprzedaży lub zakupu.  Dzięki temu można szybko znaleźć warianty produktu, gdy znasz tylko fragment konfiguracji lub jeden wymiar produktu.

Czasami posiadanie zbyt dużo czegoś jest utrudnieniem zamiast ułatwieniem. Szczególnie dotyczy to sytuacji, gdy sprzedajesz wiele produktów podobnych do siebie, i próbujesz zapamiętać numery towarów lub aliasy produktów w celu odnalezienia właściwych produktów do umieszczenia w zamówieniu sprzedaży. Jako pola wyszukiwania można użyć pola **Numer pozycji** w wierszu zamówienia sprzedaży lub wierszu zamówienia zakupu. Można wprowadzić dowolną część nazwy, numeru lub wymiaru produktu i uzyskać odnośnik pokazujący listę wszystkich towarów pasujących do szukanego słowa.

## <a name="how-search-works"></a>Jak działa wyszukiwanie
Podczas wyszukiwania produktów lub wariantów produktów trzeba wiedzieć, jak funkcja wyszukiwania znajduje produkty pasujące do wprowadzonego tekstu. Przy zwracaniu wyników wyszukiwania obowiązują następujące kluczowe zasady wyszukiwania:

-   W wynikach wyszukiwania zostaną zwrócone wszelkie pasujące rekordy, bez uwzględnienia pola, w którym wpisano wyszukiwany tekst.
-   Szukany tekst musi być obecny w pasującym rekordzie w swojej całej długości.
-   System stwierdzi zgodność nawet wtedy, gdy wyszukiwany tekst znajduje się w środku ciągu tekstowego w pasującym rekordzie. Nie musi występować na początku ciągu tekstowego.
-   Wyszukiwany tekst jest traktowany jako jeden ciąg tekstowy, nawet jeśli zawiera znak odstępu.

### <a name="examples"></a>Przykłady

W poniższych przykładach użyto produktów i wariantów produktów w celu zilustrowania działania funkcji wyszukiwania w różnych scenariuszach. **Warunki wstępne:** W ustawieniu **Sprzedaż i marketing &gt; Ustawienia &gt; Wyszukiwanie &gt; Parametry wyszukiwania** &gt; **Typ wyszukiwania** zaznacz wartość **Pełne dopasowanie**.

| Typ produktu     | Nazwa produktu    | Wyświetlany numeru produktu | Numer towaru | Konfiguracja |
|------------------|-----------------|------------------------|-------------|---------------|
| Odrębny produkt | SpeakerMidRange | D0001                  | D0001       | Nie dotyczy            |
| Wariant produktu  | Głośnik aktywny  | D0010:::Czarny:         | D0010       | 000005        |
| Wariant produktu  | Głośnik aktywny  | D0010:::Biały:         | D0010       | Biały         |

Jeśli w polu **Numer pozycji** wpiszesz tekst „głośn”, w odnośniku otrzymasz wszystkie produkty widoczne powyżej. Jeśli w polu **Numer pozycji** wpiszesz tekst „czarny”, w wynikach zostanie wyświetlony drugi produkt, ponieważ zawiera tekst „czarny” w polu Wyświetlany numer produktu. Te dwa przykłady ilustrują, że wyszukiwanie odbywa się nie tylko od początku pola. Zgodność zostanie stwierdzona nawet wtedy, gdy wyszukiwany tekst znajduje się w środku ciągu tekstowego w pasującym rekordzie.  

Jeśli wpiszesz „05”, w wynikach uzyskasz tylko drugi wariant produktu, ponieważ w konfiguracji ma on element „05”. Pokazuje to, że wyszukiwanie obejmuje wszystkie pola zaznaczone na stronie **Kryteria wyszukiwania**.  

Jeśli wpiszesz „głośn 05”, nie otrzymasz żadnych wyników. Jest to spowodowane tym, że funkcja wyszukiwania szuka pełnego wprowadzonego tekstu. Wyszukiwanie nie będzie próbowało znaleźć pozycji ze słowem „głośn”, a następnie zawęzić wyniki tylko do tych, które zawierają element „05”.  

Liczbę wyników wyszukiwania można ograniczyć. Służy do tego pole **Liczba wyników** na stronie **Sprzedaż i marketing &gt; Ustawienia &gt; Wyszukiwanie &gt; Parametry wyszukiwania**. Jeśli w tym polu zostanie ustawiona wartość 0, będą zwracane wszystkie wyniki wyszukiwania. Jeśli zostanie ustawiona wartość 10, będzie zwracanych maksymalnie 10 wyników wyszukiwania.

## <a name="configure-the-product-search"></a>Konfigurowanie wyszukiwania produktów
Zanim będzie można używać funkcji wyszukiwania produktów i wariantów produktów, wykonaj następujące kroki w celu skonfigurowania funkcji wyszukiwania produktów. [![3 kroki konfigurowania wyszukiwania produktów\_AXAppFall](./media/3-steps-to-configure-product-search_axappfall.png)](./media/3-steps-to-configure-product-search_axappfall.png)

### <a name="step-1-include-all-the-relevant-product-and-product-variant-identifiers-and-dimensions-in-the-search-criteria"></a>Krok 1: Umieszczenie wszystkich odpowiednich identyfikatorów i wymiarów produktów i wariantów produktów w kryteriach wyszukiwania

Przykładami identyfikatorów i wymiarów produktów i wariantów produktów, które można wyszukiwać, są **Nazwa produktu, Numer pozycji**, **Wyświetlany numeru produktu, Konfiguracja, Kolor, Rozmiar, Styl, Alias** itp.  

Przejdź do strony **Sprzedaż i marketing &gt; Ustawienia &gt; Wyszukiwanie &gt; Kryteria wyszukiwania**. Na stronie **Kryteria wyszukiwania** można określić kryteria dotyczące odbiorcy, prospekta i wyszukiwania produktów. Upewnij się, że strona jest filtrowana przy użyciu kryteriów wyszukiwania produktów. Można to zrobić, przełączając na widok **Produkt** w menu strony.  

Aby do kryteriów wyszukiwania dodać wyświetlany numer produktu, w menu strony kliknij przycisk **Nowy**. Spowoduje to dodanie nowego rekordu w siatce **Kryteria wyszukiwania**. Otwórz odnośnik kolumny **Nazwa pola** i wybierz opcję **DisplayProductNumber**. Aby do kryteriów wyszukiwania dodać konfigurację produktu, utwórz nowy rekord w siatce **Kryteria wyszukiwania** i wybierz opcję **configId** w kolumnie **Nazwa pola**. W ten sam sposób utwórz rekord z **Nazwa pola** > **InventColorId** dla wymiaru koloru, **InventSizeId** dla wymiaru rozmiaru i **InventStyleId** dla wymiaru stylu.

### <a name="step-2-populate-the-database-table-that-is-used-for-product-search"></a>Krok 2: Wypełnienie tabeli bazy danych używanej do wyszukiwania produktów

Na stronie **Kryteria wyszukiwania** kliknij przycisk **Aktualizuj dane wyszukiwania**. W oknie dialogowym **Aktualizuj dane wyszukiwania** upewnij się, że ustawienie **Źródło** ma wartość **Produkt**, a następnie kliknij przycisk **OK**. System zbierze w jednej tabeli wszystkie wybrane kryteria wyszukiwania określone w kroku 1. Jeśli masz wiele produktów i wariantów produktów, ta operacja może być czasochłonna i może się pojawić ostrzeżenie. Zalecamy, aby zaplanować wypełnianie tabeli wyszukiwania na serwerze przetwarzania wsadowego w czasie, gdy serwer nie jest zbyt zajęty.  

Do czasu wypełnienia tabeli wyszukiwanie produktów nie będzie zwracać poprawnych wyników. Jeśli nie otrzymujesz żadnych wyników wyszukiwania, sprawdź, czy ta tabela jest wypełniona.  

Tabelę należy wypełniać tylko po zmodyfikowaniu kryteriów wyszukiwania. Nowo zwalniane produkty i warianty są automatycznie dodawane do tabeli. Usunięte produkty i warianty są automatycznie usuwane z tabeli.

### <a name="step-3-enable-the-lookup-for-product-search-on-sales-and-purchase-order-lines"></a>Krok 3: Włączenie odnośnika dla wyszukiwania produktów w wierszach zamówień sprzedaży i zakupu

Można włączyć tę funkcję, przechodząc strony **Sprzedaż i marketing &gt; Ustawienia &gt; Wyszukiwanie &gt; Parametry wyszukiwania** i na karcie **Ogólne** w opcji **Włącz odnośnik dla wyszukiwania** zaznaczyć wartość **Tak**.  

Zachowaniem domyślnym przy wprowadzaniu wiersza zamówienia sprzedaży jest otwarcie strony **Wyszukiwanie produktu**, gdy zaczniesz pisać w polu **Numer pozycji**, a następnie naciśniesz klawisz **Tab**. Strona **Wyszukiwanie produktu** zmienia kontekst podczas tworzenia wiersza zamówienia, dlatego może być uznawana za niepotrzebnie natarczywą. Jeśli wolisz otrzymać wyniki wyszukiwania w odnośniku i nie tracić kontekstu podczas wprowadzania wiersza zamówienia, możesz użyć odnośnika wyszukiwania. Jeśli wyszukiwano produktu lub wariantu produktu, ale nie zaznaczysz nic w odnośniku i naciśniesz klawisz **Tab**, zostanie wyświetlona strona **Wyszukiwanie produktu**.




