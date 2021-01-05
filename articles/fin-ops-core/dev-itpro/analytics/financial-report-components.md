---
title: Składniki raportu finansowego
description: W tym artykule opisano, jak składniki (bloki konstrukcyjne) definicji raportów są wykorzystywane w sprawozdawczości finansowej. Tymi blokami konstrukcyjnymi mogą być definicje wierszy, kolumn i drzewa raportowania. Artykuł wyjaśnia, jak organizować i blokować bloki konstrukcyjne oraz jak pracować z grupami bloków konstrukcyjnych.
author: aprilolson
manager: AnnBe
ms.date: 10/27/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: kfend
ms.custom: 59071
ms.assetid: a201cfcb-1672-45f6-897d-2db2dd181d9a
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 97468be0bdea679ca7a52c5cef9c1e10950736e8
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2020
ms.locfileid: "4682728"
---
# <a name="financial-report-components"></a>Składniki raportu finansowego

[!include [banner](../includes/banner.md)]

W tym artykule opisano, jak składniki (bloki konstrukcyjne) definicji raportów są wykorzystywane w sprawozdawczości finansowej. Tymi blokami konstrukcyjnymi mogą być definicje wierszy, kolumn i drzewa raportowania. W tym artykule opisano sposób organizowania i blokowania modułów konstrukcyjnych.

Filozofia projektowania stosowana w Projektancie raportów finansowych przewiduje podział informacji na jak najmniejsze składniki, lub bloki konstrukcyjne, a następnie ich mieszanie i łączenie zgodnie z wymaganiami. W związku z tym formatowania raportu jest oddzielone od danych finansowych i projekt raportu można zmienić bez modyfikowania danych finansowych w systemie Microsoft Dynamics ERP. Dzięki metodzie bloków konstrukcyjnych można łączyć tekst, kwoty i obliczenia, aby tworzyć dokładnie potrzebne raporty. Ponadto ta elastyczność zachęca do kreatywności poprzez ułatwienie wyświetlania operacji na różne sposoby. Poszczególne bloki konstrukcyjne definicji raportu są podobne do trójwymiarowego arkusza kalkulacyjnego, ale oferują więcej możliwości. Definicja raportu określa definicję wiersza, definicję kolumny i opcjonalną definicję drzewa raportowania, które mają być używane w raporcie. Zawiera także informacje dotyczące miejsca przechowywania generowanego raportu i sposobu jego formatowania.

## <a name="building-blocks-of-a-report"></a>Moduły konstrukcyjne raportu

| Blok konstrukcyjny            | opis | Więcej informacji |
|---------------------------|-------------|----------------------|
| Definicja wiersza            | Definicja wiersza określa opisowe wiersze (na przykład wynagrodzeń lub sprzedaży) w raporcie. Ponadto wyszczególnia wartości segmentów lub wymiarów, które zawierają wartości dla każdej pozycji w wierszu, oraz obejmuje formatowanie wierszy i obliczenia. | [Definicje wierszy](row-definitions-financial-reporting.md) |
| Definicja kolumny         | Definicja kolumny wskazuje okres, który ma być używany podczas wyodrębniania danych z wymiarów finansowych. Obejmuje również formatowania kolumn i obliczeń. | [Definicje kolumn](column-definitions-financial-reports.md) |
| Definicja drzewa raportowania | Definicja drzewa raportowania przypomina schemat organizacyjny. Zawiera ona poszczególne jednostki raportowania, które odpowiadają poszczególnym polom w schemacie. Jednostki mogą być albo pojedynczymi działami z danych finansowych albo jednostkami wyższego poziomu, które podsumowują dane z innych jednostek raportowania. | [Definicje drzew raportowania](financial-reporting-tree-definitions.md) |
| Definicja raportu         | Definicja raportu używa definicji wiersza, kolumny i opcjonalnej definicji drzewa raportowania do tworzenia raportu. Oferuje również dodatkowe opcje i ustawienia, które pozwalają dostosować raport. | [Definicja raportu](design-financial-report-definitions.md) |

Jeśli dopiero zaczynasz projektować raporty, warto skorzystać z kreatora raportów, aby szybko utworzyć definicje raportowania, które można dostosować później. Jeśli masz doświadczenie w projektowaniu raportów i chcesz mieć większą elastyczność w projektowaniu raportów, można łączyć nowe lub istniejące bloki konstrukcyjne, aby utworzyć nową definicję raportu. Aby tworzyć raporty wysokiej jakości, nie musisz dokładnie znać wszystkich dostępnych opcji definicji raportu. Gdy już nabierzesz wprawy w projektowaniu raportów, możesz rozszerzać swoje definicje raportów, aby korzystać z bardziej zaawansowanych funkcji. Po utworzeniu podstawowego raportu możesz dostosować definicję raportu i wszelkie bloki konstrukcyjne w definicji raportu.

## <a name="organize-the-building-blocks"></a>Organizowanie bloków konstrukcyjnych
Za pomocą folderów można organizować bloki konstrukcyjne w Projektancie raportów. Wszystkie foldery są specyficzne dla typu bloku konstrukcyjnego, który zawierają. Na przykład wszystkie foldery, które zawierają definicje wierszy, znajdują się w okienku **Definicje wierszy** w Projektancie raportów.

### <a name="create-a-folder"></a>Tworzenie folderu

1. W Projektancie raportów wybierz typ bloku konstrukcyjnego do sortowania w okienku nawigacji. Na przykład, aby posortować definicję wiersza, kliknij przycisk **Definicje wierszy**.
2. W okienku nawigacji wybierz istniejący folder, w którym chcesz utworzyć nowy folder, a następnie wykonaj jedną z następujących czynności:

    - Kliknij prawym przyciskiem myszy folder nadrzędny i wybierz polecenie **Nowy folder**.
    - Zaznacz folder nadrzędny i kliknij **Plik**, a następnie wybierz **Nowy folder**.

3. Gdy pojawi się nowy folder, nadaj mu nazwę, a następnie naciśnij klawisz Enter.

## <a name="lock-a-building-block"></a>Blokowanie bloków konstrukcyjnych
Można utworzyć hasło, aby zablokować i chronić blok konstrukcyjny. W ten sposób można dodać pewne zabezpieczenie do składnika raportu bez zabezpieczania całego systemu. Hasło może pomóc chronić informacje zawarte w bloku konstrukcyjnym, które są ważne dla procesu raportowania na koniec miesiąca. Użytkownik w dowolnej roli może zablokować blok konstrukcyjny. Jednak inni użytkownicy zawsze mają dostęp tylko do odczytu do zablokowanego składnika. Użytkownicy mogą otworzyć, zmienić i zapisać zablokowany składnik pod nową nazwą. Użytkownik z rolą administratora zawsze może uzyskać dostęp i zmienić zablokowany blok konstrukcyjny.

1. W Projektancie raportów otwórz składnik raportu, który chcesz zablokować, np. definicję wiersza, kolumny, raportu lub drzewa raportowania.
2. Z menu **Narzędzia** wybierz polecenie **Chroń/Nie chroń**. Można także kliknąć ikonę **Chroń/Nie chroń** (kłódkę) na pasku narzędzi.
3. W oknie dialogowym **Ochrona** wpisz i potwierdź hasło, a następnie kliknij przycisk **OK**. Ikona kłódki na pasku narzędzi jest podświetlona, gdy otwarty blok konstrukcyjny jest zablokowany.

Aby odblokować zablokowany blok konstrukcyjny, otwórz go, a następnie na pasku narzędzi kliknij przycisk **Chroń/Nie chroń**. Alternatywnie z menu **Narzędzia** wybierz polecenie **Nie chroń**.

## <a name="building-block-groups"></a>Grupy bloków konstrukcyjnych

Bloki konstrukcyjne są definicjami wierszy, kolumn, drzew raportowania i definicjami raportów, które można utworzyć dla raportu. Grupy modułów konstrukcyjnych to kolekcje definicji i zestawów wymiarów.

### <a name="view-a-building-block-group"></a>Wyświetlanie grupy modułów konstrukcyjnych

Wszystkie moduły konstrukcyjne przypisane do grupy modułów konstrukcyjnych można wyświetlić. Grupę modułów konstrukcyjnych można także wyeksportować lub zaimportować.

1. W Projektancie raportów w menu **Firma** kliknij polecenie **Grupy modułów konstrukcyjnych**.
2. W oknie dialogowym **Grupy bloków konstrukcyjnych** wybierz opcję blok konstrukcyjny, który chcesz wyświetlić.
3. Kliknij przycisk **Widok**, aby wyświetlić okno dialogowe **Wyświetlanie grupy bloków konstrukcyjnych**, gdzie można obejrzeć zawartość grupy.
4. Po obejrzeniu zawartości kliknij przycisk **Zamknij**, aby zamknąć okno.

### <a name="export-a-building-block-group"></a>Eksportowanie grupy modułów konstrukcyjnych

Można wyeksportować grupę bloków konstrukcyjnych lub tylko bloki konstrukcyjne określonego raportu istniejące w grupie bloków konstrukcyjnych. Wyeksportowanej grupy bloków konstrukcyjnych można używać jako kopii zapasowej. Można także kopiować wyeksportowane dane między instalacjami. Projektant raportów zawiera nie tylko grupę bloków konstrukcyjnych, ale również style czcionek i zestawy wymiarów, do których grupa się odwołuje.

1. W Projektancie raportów w menu **Firma** kliknij **Grupy bloków konstrukcyjnych**.
2. W oknie dialogowym **Grupy modułów konstrukcyjnych** zaznacz grupę modułów konstrukcyjnych, którą chcesz wyeksportować, i kliknij przycisk **Eksport**.
3. W oknie dialogowym **Eksportowanie** wybierz definicje raportów do wyeksportowania:

    - Aby wyeksportować wszystkie definicje raportów i powiązane bloki konstrukcyjne, kliknij **Zaznacz wszystko**.
    - Aby wyeksportować wybrane raporty, wiersze, kolumny, drzewa lub zestawy wymiarów, kliknij odpowiednią kartę i wybierz elementy do wyeksportowania. Naciśnij i przytrzymaj klawisz Ctrl, aby wybrać wiele elementów na karcie.

    > [!NOTE]
    > Zaznaczenie raportów spowoduje automatyczne zaznaczenie powiązanych wierszy, kolumn, drzew i zestawów wymiarów.

4. Po zakończeniu wybierania elementów do wyeksportowania kliknij przycisk **Eksport**.
5. W oknie dialogowym **Zapisz jako** wybierz miejsce docelowe eksportu grupy bloków konstrukcyjnych.
6. W polu **Nazwa pliku** wprowadź nazwę pliku. Projektant raportów automatycznie dodaje rozszerzenie nazwy pliku .tdbx.
7. Kliknij przycisk **Zapisz**. Grupa bloków konstrukcyjnych jest zapisywana w lokalizacji wskazanej przez użytkownika.

### <a name="import-a-building-block-group"></a>Importowanie grupy bloków konstrukcyjnych

Grupę modułów konstrukcyjnych można zaimportować do istniejącej grupy modułów konstrukcyjnych. Wszystkie zaimportowane grupy bloków konstrukcyjnych zachowują swoje oryginalne style czcionek i odwołania do firmy oraz zawierają odpowiednie zestawy wymiarów.

1. W Projektancie raportów w menu **Firma** kliknij **Grupy bloków konstrukcyjnych**.
2. W oknie dialogowym **Grupy modułów konstrukcyjnych** zaznacz moduł konstrukcyjny, do którego chcesz zaimportować grupę modułów konstrukcyjnych, i kliknij przycisk **Import**.
3. W oknie dialogowym **Otwieranie** zaznacz grupę modułów konstrukcyjnych, którą chcesz zaimportować, i kliknij przycisk **Otwórz**.
4. W oknie dialogowym **Importowanie** wybierz definicje raportów do zaimportowania:

    - Aby zaimportować wszystkie definicje raportów i wspierające je bloki konstrukcyjne, kliknij opcję **Zaznacz wszystko**.
    - Aby zaimportować konkretne raporty, wiersze, kolumny lub zestawy wymiarów, wybierz raporty, wiersze, kolumny, drzewa lub zestawy wymiarów do zaimportowania.

5. Po zakończeniu wybierania elementów do zaimportowania kliknij przycisk **Import**.

### <a name="undo-a-checkout-of-a-building-block"></a>Cofanie wyewidencjonowania bloku konstrukcyjnego

Po otwarciu bloku konstrukcyjnego inni użytkownicy mają do niego dostęp tylko do odczytu. Może się zdarzyć, że użytkownik zapomni zamknąć blok konstrukcyjny lub zamknie system z otwartym blokiem konstrukcyjnym. Taki blok konstrukcyjny pozostaje wyewidencjonowywany i inni użytkownicy nie mogą go otworzyć. W takich przypadkach administrator raportowania finansowego może użyć okna dialogowego **Elementy wyewidencjonowane**, aby zaewidencjonować bloki konstrukcyjne pozostawione przez użytkowników w stanie wyewidencjonowanym.

> [!NOTE]
> Ewidencjonowania modułów konstrukcyjnych z poziomu okna dialogowego **Elementy wyewidencjonowane** mogą dokonywać wyłącznie administratorzy.

1. W Projektancie raportów w menu **Narzędzia** kliknij **Elementy wyewidencjonowane**.
2. W oknie dialogowym **Elementy wyewidencjonowane** zaznacz opcję **Pokaż elementy od innych użytkowników**. Na liście pojawią się wszystkie wyewidencjonowane moduły konstrukcyjne wraz z nazwami użytkowników, którzy dokonali wyewidencjonowania.
3. Zaznacz żądany moduł konstrukcyjny i kliknij przycisk **Cofnij wyewidencjonowanie**.
4. Kliknij przycisk **Tak**. Moduł konstrukcyjny zostanie zaewidencjonowany.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Raporty finansowe](financial-reporting-intro.md)
