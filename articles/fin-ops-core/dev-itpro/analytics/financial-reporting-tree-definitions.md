---
title: Definicje drzewa raportowania w raportach finansowych
description: Ten artykuł zawiera informacje o definicjach drzew raportowania. Definicja drzewa raportowania to składnik (blok konstrukcyjny) raportu, który pomaga określić strukturę i hierarchię organizacji.
author: ShylaThompson
manager: AnnBe
ms.date: 10/07/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: kfend
ms.custom: 57592
ms.assetid: 747faa47-9a23-4277-bc11-8d0a1267c3a4
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 8ae024c2d791e1219c7383dc95283219a9300eac
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2020
ms.locfileid: "4682681"
---
# <a name="reporting-tree-definitions-in-financial-reports"></a>Definicje drzewa raportowania w raportach finansowych

[!include [banner](../includes/banner.md)]

Ten artykuł zawiera informacje o definicjach drzew raportowania. Definicja drzewa raportowania to składnik (blok konstrukcyjny) raportu, który pomaga określić strukturę i hierarchię organizacji.

Aplikacja Raportowanie finansowe obsługuje elastyczne raportowanie, dzięki czemu można łatwo wprowadzać zmiany wraz z rozwojem struktury firmy. Raporty są kompilowane z różnych składników, lub bloków konstrukcyjnych. Jednym z tych bloków konstrukcyjnych jest drzewo definicji raportowania. Drzewo definicji raportowania pomaga zdefiniować strukturę i hierarchię organizacji. To międzywymiarowa hierarchiczna struktura oparta na powiązaniach wymiarów w danych finansowych. Dostarcza informacji na poziomie jednostki raportowania oraz na poziomie podsumowania dla wszystkich jednostek w drzewie. Definicje drzewa raportowania można łączyć z definicjami kolumn i raportów, by tworzyć grupy elementów konstrukcyjnych dostępne dla wielu firm. Jednostka raportowania jest używana dla każdego pola w schemacie organizacyjnym. Jednostką raportowania może być indywidualny dział z danych finansowych albo jednostka zbiorcza na wyższym poziomie, która łączy w sobie informacje z innych jednostek raportowania. Dla definicji raportu zawierającej drzewo raportowania dla każdej jednostki raportowania i poziomu podsumowania generowany jest jeden raport. Wszystkie te raporty korzystają z definicji wierszy i kolumn określonych w definicji raportu, chyba że definicja raportu wymusza stosowanie drzewa raportowania z definicji wiersza. Definicje wierszy i kolumn są ważnymi składnikami projektu i funkcji raportów finansowych. Drzewa raportowania zwiększają siłę składników i obsługują elastyczne raportowanie wraz z rozwoje struktury firmy. Raporty finansowe, które nie są oparte na drzewie raportowania, wykorzystują tylko niektóre funkcje raportowania finansowego. Z tymi samymi definicjami wierszy i kolumn można łączyć wiele definicji drzewa raportowania, umożliwiając wyświetlanie danych organizacji na różne sposoby.

## <a name="reporting-tree-best-practices"></a>Sprawdzone metody korzystania z drzewa raportowania
Przed utworzeniem drzewa raportowania należy wziąć pod uwagę następujące wskazówki:

- Najpierw ustalić, które wymiary raportowania są wymagane w danej firmie lub instytucji.
- Rozważyć, jak jest skonfigurowana obecna struktura, a następnie narysować schemat organizacyjny firmy. Schemat organizacyjny pomoże zwizualizować sposób grupowania jednostek raportowania w co najmniej jednym drzewie raportowania.
- Zacząć od najniższego poziomu szczegółowości, np. od działów i projektów zdefiniowanych w danych finansowych. Dodać dowolną liczbę pól do poziomu szczegółowości, by wyświetlić działy i regiony wyższego poziomu. Każde pole odpowiada potencjalnej jednostce raportowania w dowolnym tworzonym drzewie raportowania.
- Należy też zastanowić się, jak najlepiej tworzyć drzewa. Drzewa raportowania można tworzyć automatycznie lub ręcznie. Przed przystąpieniem do planowania drzew należy dobrze zapoznać się z obiema tymi metodami.
- Można używać jednostek raportowania, które są zdefiniowane w systemie danych finansowych, aby dodawać jednostki raportowania do definicji drzewa raportowania.

## <a name="create-multiple-reporting-trees"></a> Tworzenie wielu drzew raportowania
Można utworzyć dowolną liczbę drzew raportowania, aby wyświetlić dane firmy na różne sposoby. Każde drzewo raportowania może zawierać dowolną kombinację działów i jednostek zbiorczych. Definicja raportu może zawierać łącze tylko do jednego drzewa raportowania naraz. Przez ponowne rozmieszczanie struktury jednostek raportowania można tworzyć różne drzewa raportowania. Można następnie użyć tych samych definicji wierszy i kolumn dla każdego drzewa raportowania. W ten sposób można szybko tworzyć różne układy raportów finansowych. Po utworzeniu wielu drzew raportowania można co miesiąc drukować serię sprawozdań finansowych, które analizują i prezentują działalność firmy na różne sposoby. Aby uzyskać więcej informacji, zobacz przykłady struktur jednostek raportowania na końcu tego artykułu.

## <a name="create-a-reporting-tree-definition"></a> Tworzenie definicji drzewa raportowania
Definicja drzewa raportowania zawiera kolumny opisane w poniższej tabeli.

| Kolumna drzewa raportowania | Opis |
|-----------------------|-------------|
| Firma               | Nazwa firmy dla jednostki raportowania. Wartość **\@ANY**, zazwyczaj przypisywana tylko na poziomie podsumowania, umożliwia wykorzystywanie drzewa raportowania do wszystkich firm. Firma jest przypisywana również do wszystkich gałęzi podrzędnych. |
| Nazwa jednostki             | Kod identyfikujący tę jednostkę raportowania w graficznym drzewie raportowania. Pamiętaj, aby ustanowić unikatowy system kodowania, który będzie spójny i łatwy do zrozumienia dla użytkowników. |
| Opis jednostki      | Tytuł jednostki raportowania jest wyświetlany w nagłówku lub stopce raportu po wprowadzeniu **UnitDesc** jako kodu na karcie **Nagłówki i stopki** w definicji raportu. Tytuł jest wyświetlany w opisie wiersza raportu po wprowadzeniu **UnitDesc** w komórce **Opis** w definicji wiersza. |
| Wymiary            | Jednostka raportowania, która pobiera dane bezpośrednio z danych finansowych. Definiuje ona logiczne pozycjonowanie i długości dla konta i powiązanych segmentów. Każdy wiersz jednostki raportowania musi mieć wymiar w tej kolumnie. Wymiar można również umieścić w wierszu jednostki podsumowania (np. dla wydatków bezpośrednio związanych z tą jednostką). Jeśli wymiar zostanie wprowadzony w wierszu jednostki podsumowania, konta używane w jednostkach nadrzędnych nie powinny być używane w jednostkach podrzędnych. W przeciwnym razie może dojść do zduplikowania kwot. |
| Definicje wierszy       | Nazwa definicji wiersza dla jednostki raportowania. Ta sama definicja wiersza jest używana do każdej jednostki w drzewie raportowania. Podczas generowania raportu definicja jest używana w każdej jednostce raportowania. Definicja wiersza może zawierać wiele łączy do wymiarów finansowych. Jeśli w drzewie raportowania określono definicję wiersza, w oknie definicji raportu na karcie **Raport** zaznacz pole wyboru **Użyj definicji wierszy z drzewa raportowania**. |
| Łącze wiersza              | Łącze wiersza powiązane z jednostką raportowania. Celem tworzenia łączy wierszy w definicjach wierszy jest określenie wymiarów finansowych, z którymi mają zostać nawiązane połączenia. |
| Łącze zewnętrzne         | Łącze wiersza powiązane z tą jednostką raportowania. Łącza wiersza są tworzone dla definicji wiersza w celu identyfikacji raportu, z którym ma nastąpić powiązanie. |
| Plik zewnętrzny         | Ścieżka do pliku arkusza raportowania finansowego, z którego mają być pobierane dane. |
| Opcje strony          | Ta kolumna kontroluje, czy szczegóły jednostki raportowania są pomijane podczas wyświetlania lub drukowania raportu. |
| Procent akumulacji              | Wartość procentowa jednostki raportowania, która powinna być przydzielona do jednostki nadrzędnej. Wartość procentowa wprowadzona w tej kolumnie ma zastosowanie do każdego wiersza w definicji wiersza przed dodaniem wartość w wierszu do raportu nadrzędnego. Na przykład jeśli jednostka podrzędna musi być równo podzielona między dwa działy, kwoty w każdym wierszu zostaną pomnożone przez 50 procent i dopiero wtedy wartości zostaną dodane do raportów poszczególnych działów. Jedna jednostka raportowania nie może mieć dwóch jednostek nadrzędnych. Aby przydzielić kwoty z jednostki raportowania do dwóch jednostek nadrzędnych, należy utworzyć inną jednostkę raportowania z tym samym wymiarem w celu akumulacji dodatkowych 50 procent. Całe procenty należy wpisywać bez separatora dziesiętnego. Na przykład **25** reprezentuje alokację 25 procent do obiektu nadrzędnego. Jeśli dołączysz separator dziesiętny (**,25**), do obiektu nadrzędnego zostanie przydzielone 0,25%. Aby zastosować wartość procentową mniejsza niż 1%, należy w definicji raportu użyć opcji **Zezwalaj na akumulację &lt;1%**. Ta opcja jest dostępna na karcie **Opcje dodatkowe** w oknie dialogowym **Ustawienia raportu**. W celu wyświetlenia tego okna dialogowego należy użyć przycisku **Inne** na karcie **Ustawienia** w definicji raportu. |
| Jednostka zabezpieczeń         | Ograniczenia dostępu do informacji jednostki raportowania dla użytkowników i grup. |
| Dodatkowy tekst       | Tekst zawarty w raporcie. |

Aby utworzyć definicję drzewa raportowania, należy wykonać następujące kroki:

1. Otwieranie projektanta raportów.
2. Kliknij kolejno opcje **Plik** &gt; **Nowy** &gt; **Definicja drzewa raportowania**.
3. Kliknij kolejno opcje **Edycja** &gt; **Wstaw jednostki raportowania z wymiarów**.
4. W oknie dialogowym **Wstawianie jednostek raportowania z wymiarów** zaznacz pole wyboru dla każdego z wymiarów uwzględnianych w drzewie raportowania. Okno dialogowe **Wstawianie jednostek raportowania z wymiarów** zawiera następujące sekcje.

    | Sekcja                          | Opis |
    |----------------------------------|-------------|
    | Segmentowanie wymiaru raportowania | Przyciski **Podziel segmenty** i **Połącz segmenty** umożliwiają zmianę liczby i długości segmentów.<blockquote>[!NOTE] Można łączyć tylko segmenty, które zostały uprzednio podzielone. Aby połączyć wiele wymiarów, użyj symboli wieloznacznych w wartościach wymiarów.</blockquote> |
    | Uwzględnij/położenie znaku       | W tej sekcji jest wyświetlona lista wymiarów zdefiniowanych w danych finansowych, a także liczba znaków w najdłużej wartości zdefiniowanej dla każdego wymiaru. Zaznacz pole wyboru obok wymiaru, aby uwzględnić ten wymiar w hierarchii drzewa raportowania. |
    | Hierarchia i zakresy segmentów     | Ta sekcja pokazuje hierarchię wymiarów. Na liście można przenosić wymiary, aby zmieniać kolejność raportowania. W polach **Od wymiaru** i **Do wymiaru** można określić zakres wartości dla każdego wymiaru. Jeśli nie określisz zakresu, wszystkie wartości wymiarów są wstawiane do drzewa raportowania.<blockquote>[!NOTE] Jeśli jest używanych kilka wymiarów, w wynikach zostaną zwrócone tylko kombinacje wymiarów, które zostały opublikowane.</blockquote> |

    Aby obejrzeć zrzut ekranu pokazujący przykład okna dialogowego **Wstawianie jednostek raportowania z wymiarów**, zobacz sekcję „Przykład okna dialogowego Wstawianie jednostek raportowania z wymiarów” w dalszej części tego artykułu.

5. Aby utworzyć dodatkowe segmenty (np. poprzez podział jednego segmentu na dwa krótsze segmenty), kliknij prawidłową lokalizację w polu **Pozycja znaku**, a następnie kliknij przycisk **Podziel segment**.
6. Aby scalić dwa segmenty w jeden, kliknij pole dowolnego z dwóch segmentów do scalenia, a następnie kliknij przycisk **Połącz segmenty**.
7. Hierarchia określa sposób raportowania wymiarów względem siebie oraz zakres każdego wymiaru. Aby zmienić hierarchię wymiarów, w obszarze **Hierarchia i zakresy segmentów** zaznacz wymiar, który chcesz przenieść, a następnie kliknij przycisk **Przenieś w górę** lub **Przenieś w dół**.
8. Aby określić zakresy wymiarów wartości, które mają zostać dodane do nowego drzewa raportowania, w obszarze **Hierarcha i zakresy segmentów** należy wykonać następujące czynności:

    1. W polu **Z wymiaru** dla tego wymiaru wprowadź pierwszą wartość zakresu.
    2. W polu **Do wymiaru** wprowadź ostatnią wartość zakresu.

9. Powtarzaj kroki 7 i 8 dla każdego wymiaru w obszarze **Hierarchia i zakresy wymiarów**.
10. Po określeniu sposobu wprowadzania jednostek raportowania do drzewa raportowania kliknij **OK**.
11. Kliknij kolejno opcje **Plik** &gt; **Zapisz**, aby zapisać drzewo raportowania. Wprowadź unikatową nazwę i opis dla drzewa raportowania, a następnie kliknij przycisk **OK**.

### <a name="open-an-existing-reporting-tree-definition"></a>Otwieranie istniejącej definicji drzewa raportowania

1. W Projektancie raportów kliknij **Definicje drzewa raportowania** w okienku nawigacji.
2. Kliknij dwukrotnie nazwę na liście drzewa raportowania, aby ją otworzyć.
3. Aby wyświetlić podstawowe elementy skojarzone z drzewem raportowania, kliknij prawym przyciskiem myszy, a następnie wybierz **Skojarzenia**.

### <a name="roll-up-data-in-a-reporting-tree"></a>Akumulacja danych w drzewie raportowania

Korzystając z drzewa raportowania, można agregować kwoty z podrzędnych jednostek raportowania do poziomu nadrzędnej jednostki raportowania. Takie agregowanie jest nazywane akumulacją danych. Poniższe reguły są używane do akumulacji kwot do jednostek nadrzędnych w drzewie raportowania:

- W drzewie raportowania jednostki podrzędne muszą zawierać wymiary, chyba że drzewo raportowania jest jednopoziomowe. Jednostki nadrzędne zwykle nie zawierają wymiarów w drzewie raportowania.

    > [!NOTE]
    > Jeśli określisz wymiary jednocześnie dla jednostek podrzędnych i nadrzędnych, może to spowodować zduplikowanie danych w raporcie.

- Jednostki raportowania, które zawierają wymiary w drzewie raportowania, odpowiadają wymiarom, które są używane w definicjach wierszy i kolumn. Kombinacja wymiarów określa kwoty zwracane dla tej jednostki. Na przykład w przykładzie 2 w dalszej części artykułu wiersze 6 i 7 zwrócą tylko wartości odpowiednio dla działów 00 i 01.
- Kwoty dla nadrzędnych jednostek raportowania, które nie zawierają wymiarów w drzewie raportowania, są określane na podstawie raportów jednostek podrzędnych i akumulują się do kwot w określonych jednostkach nadrzędnych. Jeśli na przykład jednostka nadrzędna (patrz Contoso USA w przykładzie 2 na akumulowanie danych) ma dwie jednostki podrzędne (022 i 023) i nie zawiera wymiarów, generowany jest raport dla każdej jednostki podrzędnej oraz dla jednostki nadrzędnej. Suma nadrzędna jest sumą dwóch kwot podrzędnych.

### <a name="manage-reporting-units"></a>Zarządzanie jednostkami raportowania

Każda definicja drzewa raportowania jest wyświetlana w osobnym widoku. Dostępny jest widok graficzny pokazujący hierarchię elementów nadrzędnych i podrzędnych oraz widok arkusza, który przedstawia szczegółowe informacje dla każdej jednostki raportowania. Widok graficzny i widok arkusza kalkulacyjnego są ze sobą połączone. Po wybraniu jednostki raportowania w jednym widoku zostanie ona również wybrana w drugim. Można tworzyć hierarchie międzywymiarowe oparte na powiązaniach wymiarów w danych finansowych. Podczas tworzenia definicji drzewa raportowania można używać jednej definicji wiersza wiele razy, niezależnie od tego, czy generujesz rachunek zysków i strat w dziale czy skonsolidowany podsumowujący rachunek zysków i strat. Wymiary, które są zdefiniowane w definicji wiersza, mogą być łączone z wymiarami w definicji drzewa raportowania, oferując różne widoki działalności organizacji.

### <a name="reporting-unit-structure"></a> Struktura jednostki raportowania

W raportowaniu finansowym są używane następujące typy jednostek raportowania:

- Jednostka szczegółów pobiera informacje bezpośrednio z danych finansowych, z arkusza programu Excel lub z innego arkusza raportowania finansowego.
- Jednostka podsumowania zestawia dane z jednostek niższego poziomu.

Nadrzędna jednostka raportowania jest jednostką podsumowania, która zbiera podsumowane informacje z jednostki szczegółów. Jednostka podsumowania może być zarówno jednostką szczegółów, jak i jednostką podsumowania. W związku z tym jednostka podsumowania można pobierać informacje z jednostki niższego poziomu, danych finansowych lub arkusza programu Excel. Jednostka nadrzędna może być jednostką podrzędną jednostki nadrzędnej na wyższym poziomie. Podrzędna jednostka raportowania może być jednostką szczegółów, która pobiera informacje bezpośrednio z danych finansowych lub arkusza programu Excel. Podrzędna jednostka raportowania może być również pośrednią jednostką podsumowania. Innymi słowy może być jednostką nadrzędną jednostki niższego poziomu, a równocześnie jednostką podrzędną jednostki podsumowania na wyższym poziomie. W najbardziej typowym scenariuszu jednostek raportowania jednostki nadrzędne mają pustą komórkę w kolumnie **Wymiary**, a jednostki podrzędne mają łącza do konkretnych lub wieloznacznych kombinacji wymiarów.

### <a name="organize-reporting-units"></a> Organizowanie jednostki raportowania

Można zmienić kolejność struktury organizacyjnej definicji drzewa raportowania, przenosząc jednostki raportowania w widoku graficznym. Jednostki raportowania można też przenosić na wyższe i niższe poziomy w drzewie raportowania.

1. W Projektancie raportów otwórz definicję drzewa raportowania do zmodyfikowania.
2. W widoku graficznym definicji drzewa raportowania wybierz jednostkę raportowania.
3. Przeciągnij jednostkę do nowej pozycji. Alternatywnie kliknij jednostkę prawym przyciskiem myszy i wybierz polecenie **Podwyższ poziom jednostki raportowania** lub **Obniż poziom jednostki raportowania**.
4. Kliknij kolejno opcje **Plik** &gt; **Zapisz**, aby zapisać zmiany.

### <a name="add-text-about-a-reporting-unit"></a> Dodawanie tekstu dotyczącego jednostki raportowania

Dodatkowy wpis tekstowy jest statycznym ciągiem tekstowym maksymalnie 255 znaków, który dodaje informacje do definicji drzewa raportowania. Ten dodatkowy tekst może być na przykład krótkim opisem firmy. Można utworzyć maksymalnie dziesięć wpisów tekstowych dla każdej jednostki raportowania w definicji drzewa raportowania. Dodatkowy tekst pojawia się w raporcie dla jednostki raportowania, do której jest przypisany. Wpisy tekstowe można dodawać z kolumny **Opis** w definicji wiersza oraz z karty **Nagłówki i stopki** w definicji raportu.

1. W Projektancie raportów otwórz definicję drzewa raportowania do zmodyfikowania.
2. Kliknij dwukrotnie komórkę **Dodatkowy tekst** dla jednostki raportowania.
3. W oknie dialogowym **Dodatkowy tekst** w pierwszym pustym wierszu wprowadź tekst. Pierwszy wiersz, który zawiera tekst, jest określany jako UnitText1, niezależnie od jego pozycji w oknie dialogowym **Dodatkowy tekst**.
4. Aby dodać więcej wpisów tekstowych dla tej jednostki raportowania, wprowadź teksty w pustych wierszach.
5. Kliknij przycisk **OK**

### <a name="remove-additional-text-from-a-reporting-unit"></a>Usuwanie dodatkowego tekstu z jednostki raportowania

1. W Projektancie raportów otwórz definicję drzewa raportowania, którą chcesz zmodyfikować.
2. W wierszu jednostki raportowania kliknij dwukrotnie komórkę **Dodatkowy tekst**.
3. W oknie dialogowym **Dodatkowy tekst** zaznacz wpis do usunięcia, a następnie kliknij przycisk **Wyczyść**. Alternatywnie kliknij wpis prawym przyciskiem myszy i wybierz polecenie **Wytnij**.
4. Kliknij przycisk **OK**

### <a name="restrict-access-to-a-reporting-unit"></a>Ograniczanie dostępu do jednostki raportowania

Aby uniemożliwić wybranym użytkownikom i grupom dostęp do jednostki raportowania. Można także zdefiniować ograniczenia, tak aby odnosiły się do podrzędnych jednostek raportowania wybranej jednostki raportowania.

1. W Projektancie raportów otwórz definicję drzewa raportowania do zmodyfikowania.
2. Kliknij dwukrotnie komórkę **Zabezpieczenia jednostki** dotyczącą wiersza jednostki raportowania, do której chcesz ograniczyć dostęp.
3. W oknie dialogowym **Jednostka zabezpieczeń** kliknij przycisk **Użytkownicy i grupy**.
4. Wybierz użytkowników lub grupy, które powinny mieć dostęp do jednostki raportowania, a następnie kliknij przycisk **OK**.
5. Aby ograniczyć dostęp do podrzędnych jednostek raportowania, zaznacz pole wyboru **Dodaj zabezpieczenia do podrzędnych jednostek raportowania**.
6. Kliknij przycisk **OK**

### <a name="remove-access-to-a-reporting-unit"></a>Anulowanie dostępu do jednostki raportowania

1. W Projektancie raportów otwórz definicję drzewa raportowania do zmodyfikowania.
2. Kliknij dwukrotnie komórkę **Jednostka zabezpieczeń** dla wiersza jednostki raportowania, do którego dostęp chcesz zablokować.
3. W oknie dialogowym **Jednostka zabezpieczeń** zaznacz nazwę i kliknij przycisk **Usuń**.
4. Kliknij przycisk **OK**

### <a name="link-to-reports"></a>Łącza do raportów

Po utworzeniu kolumny **raportu** w definicji wiersza i wskazaniu raportu, który ma się znaleźć w raporcie, należy zaktualizować drzewo raportowania o połączoną kolumnę oraz informacje o raporcie. Raport można zaimportować do dowolnej jednostki w drzewie raportowania.

### <a name="identify-the-report-in-a-reporting-tree"></a>Identyfikowanie raportu w drzewie raportowania

1. W Projektancie raportów otwórz definicję drzewa raportowania do zmodyfikowania.
2. W kolumnie **Definicje wierszy** informacje w komórkach bazują na informacjach wybranego wiersza, ponieważ ta sama definicja wiersza musi być używana we wszystkich jednostkach drzewa raportowania. Kliknij dwukrotnie komórkę **Definicje wierszy**, a następnie wybierz definicję wiersza zawierającą informacje o raporcie.
3. W komórce **Łącze skoroszytu** dla jednostki raportowania wybierz nazwę łącza odpowiadającą raportowi.
4. W komórce **Ścieżka skoroszytu lub raportu** dla jednostki raportowania wprowadź nazwę raportu lub przeglądaj w poszukiwaniu żądanego raportu.
5. Aby określić arkusz w raporcie, wprowadź nazwę arkusza w komórce **Nazwa arkusza**.
6. Powtórz kroki od 3 do 5 dla każdej jednostki raportowania, która powinna otrzymywać dane z raportu. Aby uniknąć nieprawidłowych danych w raporcie, upewnij się, że są wyświetlane poprawne nazwy raportów w odpowiedniej jednostce drzewa raportowania.

## <a name="examples"></a>Przykłady
### <a name="reporting-unit-structure--example-1"></a>Struktura jednostki raportowania — przykład 1

Oto struktura jednostek raportowania w poniższym drzewie raportowania:

- Jednostka raportowania Contoso Japan jest nadrzędną jednostką podrzędnych jednostek Contoso Japan Sales i Contoso Japan Consulting.
- Jednostka działu Contoso Japan Sales jest zarówno jednostką podrzędną jednostki Contoso Japan, jak i jednostką nadrzędną dla jednostek Home Sales i Auto Sales.
- Jednostki raportowania najniższego poziomu szczegółów (Home Sales, Auto Sales, Client Services i Operations) reprezentują działy w danych finansowych. Te jednostki raportowania znajdują się w zacienionym obszarze diagramu.
- Jednostki podsumowania wyższego poziomu podsumowują informacje z jednostek szczegółów.

[![ContosoEntertainmentSummaryReportStructure](./media/contosoentertainmentsummaryreportstructure.png)](./media/contosoentertainmentsummaryreportstructure.png)

### <a name="reporting-unit-structure--example-2"></a>Struktura jednostki raportowania — przykład 2

Na diagramie poniżej drzewo raportowania ma strukturę organizacyjną podzieloną według funkcji biznesowych.

[![summaryofallunitscontoso](./media/summaryofallunitscontoso.png)](./media/summaryofallunitscontoso.png)

### <a name="example-of-the-insert-reporting-units-from-dimensions-dialog-box"></a>Przykład okna dialogowego Wstawianie jednostek raportowania z wymiarów

Ilustracja poniżej zawiera przykład okna dialogowego **Wstawianie jednostek raportowania z wymiarów**. W tym przykładzie zwracanymi wynikami są kombinacje jednostek biznesowych, centrów kosztów i działów.

[![InsertReportingUnits](./media/insertreportingunits.png)](./media/insertreportingunits.png)

Powstała definicja drzewa raportowania jest sortowana według jednostek biznesowych, następnie według centrów kosztów, a na końcu według działów. Wymiarem piątej jednostki raportowania jest **Jednostka biznesowa = \[001\], Centrum kosztu =\[\], Dział = \[022\]**. Identyfikuje on jednostkę raportowania dla kont, które są specyficzne dla jednostki biznesowej 001 i działu 022.

[![ReportingTree](./media/reportingtree-1024x646.png)](./media/reportingtree.png)

### <a name="examples-of-data-roll-up"></a>Przykłady akumulacji danych

Poniższe przykłady przedstawiają informacje, które mogą być używane w definicji drzewa raportowania dla akumulowanych danych.

#### <a name="example-1"></a>Przykład 1

[![MutliCompanyRollUp](./media/mutlicompanyrollup.png)](./media/mutlicompanyrollup.png)

#### <a name="example-2"></a>Przykład 2

[![CrossCompanyDepartmentRollUp](./media/crosscompanydepartmentrollup.png)](./media/crosscompanydepartmentrollup.png)

## <a name="additional-resources"></a>Dodatkowe zasoby

[Raporty finansowe](financial-reporting-intro.md)
