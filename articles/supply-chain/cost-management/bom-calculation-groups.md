---
title: "Grupy obliczeń BOM"
description: "Ten artykuł zawiera informacje o grupach obliczania dla list składowych (BOM) oraz ich konfigurowaniu. Aby uruchomić obliczanie BOM, należy utworzyć grupy obliczania i przypisać je do poszczególnych towarów albo utworzyć domyślną grupę obliczania. Ustawienia obliczania z grupy obliczania są następnie używane jako wartości domyślne na stronie Obliczanie BOM podczas obliczania listy składowej."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BOMCalcGroup, BOMCalcTable, BOMCalcTrans, InventItemPrice
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 94063
ms.assetid: 63e1b7dc-c2c5-41b0-81ed-e3e02d1b39e0
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28T00:00:00.000Z
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 3372c22d6ed90e7669f1335fdd3366b8e167ad27
ms.contentlocale: pl-pl
ms.lasthandoff: 05/25/2017

---

# <a name="bom-calculations-groups"></a>Grupy obliczeń BOM

[!include[banner](../includes/banner.md)]


Ten artykuł zawiera informacje o grupach obliczania dla list składowych (BOM) oraz ich konfigurowaniu. Aby uruchomić obliczanie BOM, należy utworzyć grupy obliczania i przypisać je do poszczególnych towarów albo utworzyć domyślną grupę obliczania. Ustawienia obliczania z grupy obliczania są następnie używane jako wartości domyślne na stronie Obliczanie BOM podczas obliczania listy składowej. 

Należy zdefiniować domyślną grupę obliczania na stronie **Parametry modułu Zarządzanie zapasami i magazynem** lub grupę obliczania specyficzną dla produktu na stronie **Szczegóły zwolnionego produktu**. System w pierwszej kolejności wyszukuje konfigurację grupy obliczania na stronie **Szczegóły zwolnionego produktu**. Jeśli nie znajdzie tam grupy obliczania, szuka na stronie **Parametry modułu Zarządzanie zapasami i magazynem**. Jeśli system nie może znaleźć grupy obliczania, użytkownik otrzymuje komunikat o błędzie podczas obliczania. Grupa obliczania zawiera zasady dla modelu kosztu własnego, modelu ceny sprzedaży i listy kontrolnej ostrzeżeń. Ustawienia obliczania z grupy obliczania są używane jako wartości domyślne na stronie **Obliczanie BOM** podczas obliczania listy składowej.

## <a name="purposes-of-bom-calculation-groups"></a>Cele grup obliczania BOM
Grupę obliczania BOM przypisuje się do pozycji z kilku powodów:

-   Poprzez ustawienie pola **Model kosztu własnego** wskazuje się źródło danych o udziale kosztu nabywanego składnika podczas obliczania planowanego kosztu wytwarzanego towaru. Niektórzy producenci obliczają planowane koszty przy użyciu umów handlowych dotyczących ceny zakupu nabywanych składników lub na innej podstawie, takiej jak rekordy cen zakupu w wersji wyceny.
-   Poprzez ustawienie pola **Model ceny sprzedaży** wskazuje się, w jaki sposób dane dotyczące towaru są używane do obliczania sugerowanej ceny sprzedaży. Można określić cenę sprzedaży lub grupę kosztów towaru. Niektórzy producenci chcą obliczać sugerowaną cenę sprzedaży dla wytwarzanych towarów. Obliczona cena sprzedaży może odzwierciedlać używanie metody ceny skumulowanej, która bazuje na rekordzie ceny sprzedaży składnika. Alternatywnie obliczona cena sprzedaży może odzwierciedlać podejście typu „koszt plus narzut”, które jest oparte na koszcie składnika i określonym procencie zysku (skojarzonym z grupą kosztów towaru).
-   Poprzez ustawienie pola **Zatrzymanie rozłożenia** wskazuje się, czy towar wytwarzany ma być traktowany jako pozycja kupowana dla celów kumulowania podczas obliczania BOM. Typowe scenariusze to pozycja kupowana, która jest od czasu do czasu wytwarzana, lub pozycja wytwarzana, który w danym momencie jest nabywana. Pozycja jest początkowo określana jako towar wytwarzany w celu zdefiniowania danych BOM i marszruty oraz umożliwienia tworzenia zleceń produkcyjnych dla tego towaru. Jednakże flaga **Zatrzymanie rozłożenia** zapobiega używaniu BOM i marszruty pozycji podczas obliczania kosztów. Zamiast tego do obliczania BOM są używane wskazane koszty towaru.

## <a name="calculation-groups"></a>Grupy obliczania
Grupy obliczania definiuje się w oknie **Ustawienia wstępnie określonych zasad kosztów** w module Zarządzanie kosztami. Grupy obliczania przypisane do towarów pozwalają określić, jak koszty własne lub ceny sprzedaży składników, zgodnie z ustawieniami grupy obliczania, są pozyskiwane dla obliczania. Na stronie **Grupy obliczania** można zdefiniować model kosztu własnego, alternatywny model kosztu własnego, model ceny sprzedaży i ostrzeżenia.

### <a name="cost-price-model"></a>Model kosztu własnego

Możliwe są cztery opcje dla pola **Model kosztu własnego**:

-   **Koszt własny pozycji** — Jako koszt własny jest używany koszt własny z tabeli **Zwolniony produkt** lub kombinacja wymiarów towaru.
-   **Cena zakupu pozycji** — Jest używana cena zakupu z pola **Koszt własny** na karcie **Zakup** na stronie **Lista zwolnionych produktów**.
-   **Umowy handlowe** — Można skonfigurować umowy handlowe dla określonych kombinacji towarów i dostawców lub dla określonych oddziałów. Następnie po zaznaczeniu w tym polu opcji **Umowy handlowe** będzie używana umowa handlowa utworzona dla ceny zakupu, razem z pozycją i oddziałem.
-   **Cena magazynowa** — Do obliczania kosztu jednostkowego w obliczaniu BOM jest używana bieżąca wartość zapasów towaru. Jednostkowy koszt własny jest obliczany tylko wtedy, gdy ilości zaksięgowana i fizyczna są większe niż 0 (zero).

### <a name="alternative-cost-price"></a>Alternatywny koszt własny

Pole **Alternatywny koszt własny** ma takie same opcje, jak pole **Model kosztu własnego**. Jednak to pole jest używane tylko wtedy, gdy nie można odnaleźć ceny w podstawowym modelu kosztu własnego.

### <a name="sales-price-model"></a>Model ceny sprzedaży

Istnieją dwie opcje obliczania zawartości pola **Ceny sprzedaży**:

-   **Grupa kosztów** — Gdy jest zaznaczona ta opcja, cena sprzedaży jest obliczana na podstawie kosztu własnego oraz ustawienia procentu zysku z grupy kosztów.
-   **Cena sprzedaży pozycji** — Po zaznaczeniu tej opcja jest używana cena sprzedaży ze skróconej karty **Sprzedaż** w tabeli zwolnionych produktów.

### <a name="stop-explosion"></a>Zatrzymanie rozłożenia

Pole wyboru **Zatrzymanie rozłożenia** służy do wskazywania, kiedy wyprodukowany towar powinien być traktowany jako kupowany towar. Zazwyczaj pole wyboru **Zatrzymanie rozłożenia** pozostaje wyczyszczone. Zaznaczenie tego pola wyboru stanowił informację, że w obliczeniach BOM wyprodukowany towar należy traktować jako składnik zakupiony, a nie wyprodukowany. Zależnie od oddziału koszt towaru można nadal obliczyć poprzez obliczenie BOM. Rozwijanie planowanych zamówień zakupu i zleceń produkcyjnych jest zatrzymywane w BOM, którego składniki są skojarzone z grupą obliczania, dla której zaznaczono pole wyboru **Zatrzymanie rozłożenia**. Planowanie główne wygeneruje planowane zamówienia w samym BOM, a nie dla towarów zawartych w BOM. Zasadniczo poprzez zaznaczenie tego pola wyboru określasz, że koszt nie zostanie dodany do obliczania BOM dla towarów objętych tą grupą obliczania.

### <a name="warnings"></a>Ostrzeżenia

Na skróconej karcie **Ostrzeżenia** wybierasz opcje wszelkich komunikatów ostrzegawczych, które użytkownicy powinni otrzymywać podczas obliczania BOM. Na przykład jeśli zaznaczysz pole wyboru **Brak BOM**, użytkownik otrzymuje ostrzeżenie, jeśli nie zostanie znaleziona aktywna wersja BOM dla jednego ze składników lub pozycji nadrzędnej, dla której jest wykonywane obliczanie BOM. Po zaznaczeniu pola wyboru **Brak marszruty** użytkownik zobaczy ostrzeżenie w przypadku, gdy nie zostanie odnaleziona żadna aktywna wersja marszruty. Jeśli w marszrutach i operacjach używasz zasobów, można poinstruować system, aby sprawdzał obecność tych zasobów. Wtedy jeśli zasób nie zostanie odnaleziony w każdym wierszu w aktywnej trasie, użytkownik otrzyma ostrzeżenie. Można również sprawdzać występowanie zużycia i je weryfikować. Zużycie to ilość w konkretnej trasie. Zazwyczaj reprezentuje ona ilość czasu wymaganą w celu wykonania określonej operacji w procesie produkcji. Można sprawdzić, czy dany towar nie ma kosztu własnego. Jeśli nie istnieje aktywny koszt własny dla pozycji, nie będzie dodawany żaden koszt do obliczania BOM. Można również sprawdzać występowanie i weryfikować wiek kosztu własnego. Na przykład wpisz **60**, aby wskazać, że jednostkowy koszt własny musi zostać ponownie oceniony po upływie 60 dni. Po osiągnięciu tego limitu system generuje ostrzeżenie. Na przykład koszt własny wprowadzono dla towaru w styczniu tego roku. Jeśli teraz jest sierpień, czyli więcej niż 60 dni po wprowadzeniu kosztu własnego, użytkownik otrzyma ostrzeżenie podczas obliczania BOM. W polu **Minimalna marża** można wprowadzić wartość procentową. Ta wartość wskazuje punkt, w którym minimalna marża pokrycia nie została osiągnięta. Jeśli marża pokrycia określonego składnika nie jest osiągnięta, użytkownik otrzyma ostrzeżenie. W związku z tym to pole pomaga zagwarantować, że cena sprzedaży nie będzie niższa niż koszty własne oraz dodatkowe koszty magazynowania, które mogą być wymagane dla towarów.
Domyślne ustawienia w oknie Parametry modułu Zarządzanie zapasami i magazynem
--------------------------------------------------------------

Ponieważ grupy obliczania są wymagane do wykonywania obliczeń, należy skonfigurować domyślną grupę obliczania w parametrach modułu Zarządzanie zapasami. Ta konfiguracja umożliwi firmom posiadanie standardowych ustawień grupy kosztów i zysków dla wszystkich towarów. Następnie jeśli określony towar ma specjalne wymagania dotyczące obliczania, użytkownik może przypisać inną grupę obliczania do tej pozycji. Zazwyczaj można ustawić grupy obliczania dla pozycji składowych BOM zamiast bezpośrednio dla pozycji BOM. Jednakże gdy pojawiają się komunikaty ostrzegawcze, można zastosować grupy obliczania. Grupa obliczania przypisana do towarów zastępuje domyślną wartość skonfigurowaną w parametrach modułu Zarządzanie zapasami. Parametr domyślny można zdefiniować w oknie **Zarządzanie kosztami** &gt; **Ustawienia zasad księgowania zapasów** &gt; **Parametry** &gt; **Księgowanie zapasów** &gt; **Grupa obliczania**. Konfigurując domyślną grupę konfiguracji, można również skonfigurować warunki ostrzegawcze powodujące wyświetlanie użytkownikom monitów w trakcie procesu obliczania BOM, jeśli wybrane składniki mogły powodować błędy w obliczeniach.
Wyświetlanie komunikatów ostrzegawczych na stronie Zakończono
------------------------------------------

Podczas obliczania BOM są generowane komunikaty ostrzegawcze. Można obejrzeć ostrzeżenia o wybranym towarze. Na przykład w module Sprzedaż i marketing utworzono nowe zamówienie sprzedaży na towar D0001. Następnie w wierszu zamówienia sprzedaży w menu **Aktualizuj wiersz** kliknij polecenie **Oblicz na podstawie BOM/formuły**, aby wyświetlić szczegóły obliczania i ostrzeżenia. Wyniki obliczania można też obejrzeć na stronie **Zakończono**. W przypadku komunikatów ostrzegawczych tylko dwa warunki ostrzegawcze mają zastosowanie do towarów wytwarzanych, a cztery do każdego towaru:
-   Ostrzegaj, jeśli wytwarzany towar nie ma aktywnego BOM.
-   Ostrzegaj, jeśli wytwarzany towar nie ma aktywnej marszruty.
-   Ostrzegaj, jeśli towar w wierszu BOM ma ilość równą 0 (zero).
-   Ostrzegaj, jeśli towar w wierszu BOM ma koszt równy 0 (zero) lub nie ma rekordu kosztu.
-   Ostrzegaj, jeśli towar w wierszu BOM ma nieaktualny koszt. Ostrzeżenie jest wynikiem porównania daty obliczania z wyrażonym w dniach maksymalnym wiekiem kosztu.
-   Ostrzegaj, jeśli towar w wierszu BOM ma zbyt mały procent zyskowności.

Można zdefiniować wiele grup obliczania BOM, w zależności od wymaganego zróżnicowania komunikatów ostrzegawczych. Na przykład może wystarczyć jedna grupa obliczania BOM, która ma warunki ostrzegawcze dotyczące aktywnego BOM, zerowej ilości składnika i zerowego kosztu składnika. Podczas rozpoczynania obliczania BOM można zastępować warunki ostrzegawcze skojarzone z grupą obliczania BOM. Można również dodawać i usuwać warunki ostrzegawcze. Na przykład jeśli obecna sytuacja nie obejmuje żadnych danych marszruty, można usunąć warunek ostrzegawczy dotyczący aktywnej marszruty. **Uwaga:** Moduł Czas i frekwencja zawiera stronę **Grupy obliczania**, ale ta strona nie ma żadnego powiązania z grupami obliczania BOM. W module Czas i frekwencja można przypisywać pracowników do grup obliczania, które odzwierciedlają grupy pracowników skojarzonych z tym samym przełożonym lub kierownikiem. Obliczanie rejestracji pracowników może być wykonywane automatycznie lub ręcznie przez przełożonego lub kierownika.




