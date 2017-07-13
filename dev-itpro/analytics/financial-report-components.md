---
title: "Składniki raportu finansowego"
description: "W tym artykule opisano, jak składniki (bloki konstrukcyjne) definicji raportów są wykorzystywane w sprawozdawczości finansowej. Tymi blokami konstrukcyjnymi mogą być definicje wierszy, kolumn i drzewa raportowania. Artykuł wyjaśnia, jak organizować i blokować bloki konstrukcyjne oraz jak pracować z grupami bloków konstrukcyjnych."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: ShylaThompson
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 59071
ms.assetid: a201cfcb-1672-45f6-897d-2db2dd181d9a
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 5c09b1fc061f95cd78e9f18c2bdf846fdbfc7cf1
ms.contentlocale: pl-pl
ms.lasthandoff: 06/13/2017


---

# Składniki raportu finansowego
<a id="financial-report-components" class="xliff"></a>

[!include[banner](../includes/banner.md)]


W tym artykule opisano, jak składniki (bloki konstrukcyjne) definicji raportów są wykorzystywane w sprawozdawczości finansowej. Tymi blokami konstrukcyjnymi mogą być definicje wierszy, kolumn i drzewa raportowania. Artykuł wyjaśnia, jak organizować i blokować bloki konstrukcyjne oraz jak pracować z grupami bloków konstrukcyjnych. 

Filozofia projektowania stosowana w Projektancie raportów finansowych przewiduje podział informacji na jak najmniejsze składniki, lub bloki konstrukcyjne, a następnie ich mieszanie i łączenie zgodnie z wymaganiami. W związku z tym formatowania raportu jest oddzielone od danych finansowych i projekt raportu można zmienić bez modyfikowania danych finansowych w systemie Microsoft Dynamics ERP. Dzięki metodzie bloków konstrukcyjnych można łączyć tekst, kwoty i obliczenia, aby tworzyć dokładnie potrzebne raporty. Ponadto ta elastyczność zachęca do kreatywności poprzez ułatwienie wyświetlania operacji na różne sposoby. Poszczególne bloki konstrukcyjne definicji raportu są podobne do trójwymiarowego arkusza kalkulacyjnego, ale oferują więcej możliwości. Definicja raportu określa definicję wiersza, definicję kolumny i opcjonalną definicję drzewa raportowania, które mają być używane w raporcie. Zawiera także informacje dotyczące miejsca przechowywania generowanego raportu i sposobu jego formatowania. Abu ułatwić ponowne wykorzystywanie i udostępnianie, można utworzyć grupę bloków konstrukcyjnych, czyli zbiór istniejących definicji raportów, wierszy, kolumn i drzew raportowania oraz zestawów wymiarów, które są skojarzone z firmą.

##  Bloki konstrukcyjne raportu
<a id="building-blocks-of-a-report" class="xliff"></a>
| Blok konstrukcyjny            | Opis                                                                                                                                                                                                                                                                              | Więcej informacji                                                                                                 |
|---------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------|
| Definicja wiersza            | Definicja wiersza określa opisowe wiersze (na przykład wynagrodzeń lub sprzedaży) w raporcie. Ponadto wyszczególnia wartości segmentów lub wymiarów, które zawierają wartości dla każdej pozycji w wierszu, oraz obejmuje formatowanie wierszy i obliczenia.                                                    | [Definicje wierszy](row-definitions-financial-reporting.md)                       |
| Definicja kolumny         | Definicja kolumny wskazuje okres, który ma być używany podczas wyodrębniania danych z wymiarów finansowych. Obejmuje również formatowania kolumn i obliczeń.                                                                                                                                 | [Definicje kolumn](column-definitions-financial-reports.md)         |
| Definicja drzewa raportowania | Definicja drzewa raportowania przypomina schemat organizacyjny. Zawiera ona poszczególne jednostki raportowania, które odpowiadają poszczególnym polom w schemacie. Jednostki mogą być albo pojedynczymi działami z danych finansowych albo jednostkami wyższego poziomu, które podsumowują dane z innych jednostek raportowania. | [Definicje drzew raportowania](financial-reporting-tree-definitions.md) |
| Definicja raportu         | Definicja raportu używa definicji wiersza, kolumny i opcjonalnej definicji drzewa raportowania do tworzenia raportu. Oferuje również dodatkowe opcje i ustawienia, które pozwalają dostosować raport.                                                                    | [Definicja raportu](design-financial-report-definitions.md)                  |

Jeśli dopiero zaczynasz projektować raporty, warto skorzystać z kreatora raportów, aby szybko utworzyć definicje raportowania, które można dostosować później. Jeśli masz doświadczenie w projektowaniu raportów i chcesz mieć większą elastyczność w projektowaniu raportów, można łączyć nowe lub istniejące bloki konstrukcyjne, aby utworzyć nową definicję raportu. Aby tworzyć raporty wysokiej jakości, nie musisz dokładnie znać wszystkich dostępnych opcji definicji raportu. Gdy już nabierzesz wprawy w projektowaniu raportów, możesz rozszerzać swoje definicje raportów, aby korzystać z bardziej zaawansowanych funkcji. Po utworzeniu podstawowego raportu możesz dostosować definicję raportu i wszelkie bloki konstrukcyjne w definicji raportu.

## Organizowanie bloków konstrukcyjnych
<a id="organize-the-building-blocks" class="xliff"></a>
Za pomocą folderów można organizować bloki konstrukcyjne w Projektancie raportów. Wszystkie foldery są specyficzne dla typu bloku konstrukcyjnego, który zawierają. Na przykład wszystkie foldery, które zawierają definicje wierszy, znajdują się w okienku **Definicje wierszy** w Projektancie raportów.

### Tworzenie folderu
<a id="create-a-folder" class="xliff"></a>

1.  W Projektancie raportów wybierz typ bloku konstrukcyjnego do sortowania w okienku nawigacji. Na przykład, aby posortować definicję wiersza, kliknij przycisk **Definicje wierszy**.
2.  W okienku nawigacji wybierz istniejący folder, w którym chcesz utworzyć nowy folder, a następnie wykonaj jedną z następujących czynności:
    -   Kliknij prawym przyciskiem myszy folder nadrzędny i wybierz polecenie **Nowy folder**.
    -   Zaznacz folder nadrzędny i kliknij **Plik**, a następnie wybierz **Nowy folder**.

3.  Gdy pojawi się nowy folder, nadaj mu nazwę, a następnie naciśnij klawisz Enter.

##  Blokowanie bloków konstrukcyjnych
<a id="lock-a-building-block" class="xliff"></a>
Można utworzyć hasło, aby zablokować i chronić blok konstrukcyjny. W ten sposób można dodać pewne zabezpieczenie do składnika raportu bez zabezpieczania całego systemu. Hasło może pomóc chronić informacje zawarte w bloku konstrukcyjnym, które są ważne dla procesu raportowania na koniec miesiąca. Użytkownik w dowolnej roli może zablokować blok konstrukcyjny. Jednak inni użytkownicy zawsze mają dostęp tylko do odczytu do zablokowanego składnika. Użytkownicy mogą otworzyć, zmienić i zapisać zablokowany składnik pod nową nazwą. Użytkownik z rolą administratora zawsze może uzyskać dostęp i zmienić zablokowany blok konstrukcyjny.
1.  W Projektancie raportów otwórz składnik raportu, który chcesz zablokować, np. definicję wiersza, kolumny, raportu lub drzewa raportowania.
2.  Z menu **Narzędzia** wybierz polecenie **Chroń/Nie chroń**. Można także kliknąć ikonę **Chroń/Nie chroń** (kłódkę) na pasku narzędzi.
3.  W oknie dialogowym **Ochrona** wpisz i potwierdź hasło, a następnie kliknij przycisk **OK**. Ikona kłódki na pasku narzędzi jest podświetlona, gdy otwarty blok konstrukcyjny jest zablokowany.

Aby odblokować zablokowany blok konstrukcyjny, otwórz go, a następnie na pasku narzędzi kliknij przycisk **Chroń/Nie chroń**. Alternatywnie z menu **Narzędzia** wybierz polecenie **Nie chroń**.

## Grupy bloków konstrukcyjnych
<a id="building-block-groups" class="xliff"></a>

Bloki konstrukcyjne są definicjami wierszy, kolumn, drzew raportowania i definicjami raportów, które można utworzyć dla raportu. Grupy bloków konstrukcyjnych są kolekcją definicji i zestawów wymiarów, które są skojarzone z firmą. Grupy bloków konstrukcyjnych mogą być specyficzne dla firm lub kilka firm może korzystać z tego samego zestawu bloków konstrukcyjnych. Jeśli niektóre firmy w organizacji mają inne plany kont, być może warto używać innej grupy bloków konstrukcyjnych dla każdej firmy. Alternatywnie można nazwać wszystkie poszczególne bloki konstrukcyjne w sposób sugerujący firmy, z którymi są one zgodne.
### Tworzenie grupy bloków konstrukcyjnych
<a id="create-a-building-block-group" class="xliff"></a>

1.  W Projektancie raportów w menu **Firma** kliknij polecenie **Grupy bloków konstrukcyjnych**.
2.  W oknie dialogowym **Grupy bloków konstrukcyjny** kliknij przycisk **Nowy**.
3.  Wprowadź unikatową nazwę i opis dla grupy bloków konstrukcyjnych. Każde pole może zawierać maksymalnie 256 znaków (razem ze spacjami).
4.  Kliknij przycisk **OK**, aby utworzyć nową grupę bloków konstrukcyjnych.

### Przypisywanie grupy bloków konstrukcyjnych
<a id="assign-a-building-block-group" class="xliff"></a>

Po utworzeniu grupy bloków należy ją przypisać co najmniej do jednej firmy. Następnie można utworzyć definicje raportów, wierszy, kolumn i drzew raportowania oraz zapisać je w grupie bloków konstrukcyjnych. Przed rozpoczęciem poniższej procedury należy zamknąć wszystkie bloki konstrukcyjne.
1.  W Projektancie raportów w menu **Firma** kliknij przycisk **Firmy**.
2.  W oknie dialogowym **Firmy** wybierz firmę, do której chcesz przypisać grupę bloków konstrukcyjnych.
3.  Kliknij **Modyfikuj**.
4.  W oknie dialogowym **Modyfikowanie firmy** w polu **Grupa bloków konstrukcyjnych** wybierz grupę bloków konstrukcyjnych, która ma zostać przypisana do firmy, lub kliknij **Nowy**, aby utworzyć nową grupę bloków konstrukcyjnych.
5.  Kliknij **OK**, aby przypisać grupę bloków konstrukcyjnych.
6.  Kliknij przycisk **Zamknij**, aby zamknąć okno dialogowe **Firmy**. Grupa bloków konstrukcyjnych jest teraz przypisana do firmy. Teraz wszystkie nowo tworzone definicje wierszy, kolumn itd. będą częścią grupy bloków konstrukcyjnych przypisanej do tej firmy. Można również importować plik .tdbx lub raport z innego systemu.

###  Wyświetlanie grupy bloków konstrukcyjnych
<a id="view-a-building-block-group" class="xliff"></a>

Gdy grupa bloków konstrukcyjny zostanie utworzona i jest używana, można wyświetlić wszystkie bloki konstrukcyjne, które są do niej przypisane. Można również wyeksportować lub zaimportować grupę bloków konstrukcyjnych oraz wykonywać na niej dalsze czynności konserwacyjne.
1.  W Projektancie raportów w menu **Firma** kliknij **Grupy bloków konstrukcyjnych**.
2.  W oknie dialogowym **Grupy bloków konstrukcyjnych** wybierz opcję blok konstrukcyjny, który chcesz wyświetlić.
3.  Kliknij przycisk **Widok**, aby wyświetlić okno dialogowe **Wyświetlanie grupy bloków konstrukcyjnych**, gdzie można obejrzeć zawartość grupy.
4.  Aby zamknąć okna dialogowe, kliknij przycisk **Zamknij**.

### Zapisywanie grupy bloków konstrukcyjnych pod nową nazwą
<a id="save-a-building-block-group-under-a-new-name" class="xliff"></a>

Można zapisać istniejącą grupę bloków konstrukcyjnych pod nową nazwą. Następnie można zmodyfikować nową grupę bloków konstrukcyjnych bez zmiany oryginalnej grupy bloków konstrukcyjnych.
1.  W Projektancie raportów w menu **Firma** kliknij **Grupy bloków konstrukcyjnych**.
2.  W oknie dialogowym **Grupy bloków konstrukcyjnych** wybierz grupę bloków konstrukcyjnych, którą chcesz zapisać pod nową nazwą.
3.  Kliknij **Zapisz jako**.
4.  Wprowadź nową nazwę i opis dla grupy bloków konstrukcyjnych.
5.  Kliknij przycisk **OK** Nowa grupa bloków konstrukcyjnych pojawia się w oknie dialogowym **Grupy bloków konstrukcyjnych**.

###  Eksportowanie grupy bloków konstrukcyjnych
<a id="export-a-building-block-group" class="xliff"></a>

Można wyeksportować grupę bloków konstrukcyjnych lub określone bloki konstrukcyjne raportu istniejące w grupie bloków konstrukcyjnych. Wyeksportowana grupa bloków konstrukcyjnych może służyć jako kopia zapasowa. Można także kopiować wyeksportowane dane między grupami bloków konstrukcyjnych lub instalacjami programu Finance and Operations. Projektant raportów zawiera nie tylko grupę bloków konstrukcyjnych, ale również style czcionek i zestawy wymiarów, do których grupa się odwołuje.
1.  W Projektancie raportów w menu **Firma** kliknij **Grupy bloków konstrukcyjnych**.
2.  W oknie dialogowym **Grupy bloków konstrukcyjnych**, wybierz grupę bloków konstrukcyjnych do wyeksportowania, a następnie kliknij **Eksportuj**.
3.  W oknie dialogowym **Eksportowanie** wybierz definicje raportów do wyeksportowania:
    -   Aby wyeksportować wszystkie definicje raportów i powiązane bloki konstrukcyjne, kliknij **Zaznacz wszystko**.
    -   Aby wyeksportować wybrane raporty, wiersze, kolumny, drzewa lub zestawy wymiarów, kliknij odpowiednią kartę i wybierz elementy do wyeksportowania. Naciśnij i przytrzymaj klawisz Ctrl, aby wybrać wiele elementów na karcie. **Uwaga**: Podczas zaznaczania raportów do wyeksportowania są zaznaczane także powiązane wiersze, kolumny, drzewa i zestawy wymiarów.

4.  Po zakończeniu wybierania elementów do wyeksportowania kliknij przycisk **Eksport**.
5.  W oknie dialogowym **Zapisz jako** wybierz miejsce docelowe eksportu grupy bloków konstrukcyjnych.
6.  W polu **Nazwa pliku** wprowadź nazwę pliku. Projektant raportów automatycznie dodaje rozszerzenie nazwy pliku .tdbx.
7.  Kliknij przycisk **Zapisz**. Grupa bloków konstrukcyjnych jest zapisywana w lokalizacji wskazanej przez użytkownika.

###  Importowanie grupy bloków konstrukcyjnych
<a id="import-a-building-block-group" class="xliff"></a>

Grupę bloków konstrukcyjnych można zaimportować do istniejącej grupy bloków konstrukcyjnych albo można utworzyć nową grupę bloków konstrukcyjnych dla danych. Wszystkie zaimportowane grupy bloków konstrukcyjnych zachowują swoje oryginalne style czcionek i odwołania do firmy oraz zawierają odpowiednie zestawy wymiarów.
1.  W Projektancie raportów w menu **Firma** kliknij **Grupy bloków konstrukcyjnych**.
2.  W oknie dialogowym **Grupy bloków konstrukcyjnych**, wybierz grupę bloków konstrukcyjnych do, której chcesz zaimportowania grupę bloków konstrukcyjnych, a następnie kliknij **Importuj**.
3.  W oknie dialogowym **Otwieranie** wybierz grupę bloków konstrukcyjnych do zaimportowania, a następnie kliknij **Otwórz**.
4.  W oknie dialogowym **Importowanie** wybierz definicje raportów do zaimportowania:
    -   Aby zaimportować wszystkie definicje raportów i wspierające je bloki konstrukcyjne, kliknij opcję **Zaznacz wszystko**.
    -   Aby zaimportować konkretne raporty, wiersze, kolumny lub zestawy wymiarów, wybierz raporty, wiersze, kolumny, drzewa lub zestawy wymiarów do zaimportowania.

5.  Po zakończeniu wybierania elementów do zaimportowania kliknij przycisk **Import**.

### Cofanie wyewidencjonowania bloku konstrukcyjnego
<a id="undo-a-checkout-of-a-building-block" class="xliff"></a>

Po otwarciu bloku konstrukcyjnego inni użytkownicy mają do niego dostęp tylko do odczytu. Może się zdarzyć, że użytkownik zapomni zamknąć blok konstrukcyjny lub zamknie system z otwartym blokiem konstrukcyjnym. Taki blok konstrukcyjny pozostaje wyewidencjonowywany i inni użytkownicy nie mogą go otworzyć. W takich przypadkach administrator raportowania finansowego może użyć okna dialogowego **Elementy wyewidencjonowane**, aby zaewidencjonować bloki konstrukcyjne pozostawione przez użytkowników w stanie wyewidencjonowanym. **Uwaga**: Musisz mieć rolę administratora, aby ewidencjonować bloki konstrukcyjne w oknie dialogowym **Elementy wyewidencjonowane**.
1.  W Projektancie raportów w menu **Narzędzia** kliknij **Elementy wyewidencjonowane**.
2.  W oknie dialogowym **Elementy wyewidencjonowane** wybierz opcję **Pokaż elementy z wszystkich użytkowników**. Lista jest aktualizowana, aby wyświetlić wszystkie bloki konstrukcyjne, które zostały wyewidencjonowane i użytkowników, którzy mają je wyewidencjonowali.
3.  Wybierz blok konstrukcyjny, a następnie kliknij przycisk **Cofnij wyewidencjonowanie**.
4.  Kliknij **Tak**, aby zaewidencjonować blok konstrukcyjny.

# Informacje dodatkowe
<a id="see-also" class="xliff"></a>

[Raporty finansowe](financial-reporting-intro.md)




