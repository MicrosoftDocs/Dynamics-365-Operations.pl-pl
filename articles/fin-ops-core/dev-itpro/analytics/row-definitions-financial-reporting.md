---
title: Definicje wierszy w Projektancie raportów finansowych
description: Definicja wiersza to składnik (blok konstrukcyjny) raportu, który określa zawartość każdego wiersza w raporcie finansowym.
author: aprilolson
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.custom:
- "68873"
ms.assetid: 2fd7b5da-700f-48cb-9003-90c0d82f818f
ms.search.form: FinancialReports
ms.openlocfilehash: a60e66c372d85cc05219eaa17b7924aca5f3f337
ms.sourcegitcommit: 3c4dd125ed321af8a983e89bcb5bd6e5ed04a762
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/28/2022
ms.locfileid: "9206327"
---
# <a name="row-definitions-in-financial-report-designer"></a>Definicje wierszy w Projektancie raportów finansowych

[!include [banner](../includes/banner.md)]

Definicja wiersza to składnik (blok konstrukcyjny) raportu, który określa zawartość każdego wiersza w raporcie finansowym. Definicję wiersza można łączyć z definicjami kolumn, drzewa raportowania i raportów, by tworzyć grupy elementów konstrukcyjnych dostępne dla wielu firm.

## <a name="create-a-row-definition"></a>Tworzenie definicji wierszy

1. W Projektancie raportów w okienku nawigacji kliknij **Definicje wierszy**.
2. W menu **Plik** kliknij **Nowy**, a następnie kliknij polecenie **Definicja wiersza**. Aby uzyskać więcej informacji dotyczących zawartości każdej komórki, zobacz [Modyfikowanie komórek definicji wiersza](modify-row-definition-cells-financial-reporting.md).

## <a name="open-a-row-definition"></a>Otwieranie definicji wiersza
1. W Projektancie raportów w okienku nawigacji kliknij **Definicje wierszy**.
2. Kliknij dwukrotnie nazwę definicji wiersza, którą chcesz otworzyć.
3. Aby wyświetlić podstawowe elementy skojarzone z definicja wiersza, kliknij definicję wiersz prawym przyciskiem myszy, a następnie wybierz **Skojarzenia**.

## <a name="contents-of-a-row-definition"></a> Zawartość definicji wiersza
Definicja wiersza może zawierać maksymalnie 20 000 wierszy wymiarów finansowych i uwzględniać następujące informacje:

- Opisowy tekst, który dodaje znaczenie do raportu przez utworzenie nagłówków, wierszy i obszarów sekcji, np. **Gotówka** lub **Całkowity przychód**.
- Łącza do danych finansowych, co może obejmować wartości wymiarów z programu Microsoft Dynamics 365 Finance

    > [!NOTE]
    > Definicję wierszy można skonfigurować w taki sposób, że podczas każdego generowania raportu będzie pobierać dane z systemu wymiarów finansowych.

- Sumy wierszy i formuły oparte na połączonych danych finansowych.

Zazwyczaj każdy wiersz w definicji wiersza zawiera jeden z następujących typów informacji:

- Odwołania do systemu wymiarów finansowych.
- Sumy lub obliczenia oparte na danych.
- Formatowanie

Istnieją dwie metody wprowadzania danych w definicji wiersza:

- Ręczne wprowadzanie danych wiersza w nowej definicji wiersza. Aby uzyskać więcej informacji, zobacz [Modyfikowanie komórek definicji wiersza](modify-row-definition-cells-financial-reporting.md).
- Używanie Projektanta raportów do pobierania danych wiersza bezpośrednio z wymiarów finansowych. Aby uzyskać więcej informacji, zobacz sekcję „Powiązane formuły/wiersze/jednostki” w artykule [Modyfikowanie komórek definicji wiersza](modify-row-definition-cells-financial-reporting.md).

## <a name="add-dimensions-in-a-row-definition"></a> Dodawanie wymiarów w definicji wiersza
Wymiar jest częścią wspólną danych i wartości. W projektancie raportów można grupować dane i wartości. Następnie można klasyfikować i analizować transakcje bardziej szczegółowo. Można użyć okna dialogowego **Wstaw wiersze z wymiarów**, aby dodawać wiersze do definicji wiersza w tym samym czasie. To okno dialogowe wyświetla jedną kolumnę dla każdego wymiaru. W poniższej tabeli opisano informacje, które można podać dla każdego wymiaru.

| Opcja                | Opis |
|-----------------------|-------------|
| Wymiar             | Wzorzec określający wymiar, który ma zostać dodany do definicji wiersza. Ten wzorzec zawiera jeden znak & lub znak \# dla każde pozycji w wymiarach. Ogólnie rzecz biorąc używaj wyłącznie znaków & dla wymiaru Konto główne i wyłącznie znaków # dla innych wymiarów. |
| Początek zakresu wymiarów | Pierwsza wartość dla tego wymiaru, która ma zostać dodana do definicji wierszy. |
| Koniec zakresu wymiarów   | Ostatnia wartość tego wymiaru, która ma zostać dodana do definicji wiersza. |

Aby dodać wymiary do definicji wiersza, należy wykonać następujące kroki:

1. W Projektancie raportów kliknij **Definicje wierszy**, a następnie otwórz definicję wiersza, którą chcesz zmodyfikować.
2. W menu **Edycja** kliknij **Wstaw wiersze z wymiarów**.
3. W oknie dialogowym **Wstaw wiersze z wymiarów** w wierszu **Wymiary** wybierz komórki dla wymiaru, który ma zostać przeniesiony do definicji wiersza, a następnie kliknij przycisk **Wszystkie &&&**.
4. Aby ograniczyć definicję wiersza do określonego zakresu wartości wymiarów, wprowadź początkową wartość wymiaru w komórce **Początek zakresu wymiaru**, a następnie wprowadź końcową wartość wymiaru w komórce **Koniec zakresu wymiaru**. Aby uwzględnić wszystkie wartości dla wybranego wymiaru, pozostaw te komórki puste.

    > [!NOTE]
    > Użycie symboli wieloznacznych (\* lub ?) w zakresach wymiarów może spowodować, że nie zostaną zwrócone wszystkie oczekiwane wyniki. Jest to zależne od sposobu gromadzenia danych w bazie danych systemu ERP.

5. W polu **Początkowy kod wiersza** określ kod wiersza dla pierwszej wartości wymiaru, która ma zostać dodana do definicji wiersza.
6. W polu **Przyrost każdego wiersza** określ odstęp między kolejnymi kodami wierszy. Na przykład jeśli kod pierwszego wiersza wynosi 100, a wartość przyrostu wynosi 30, pierwsze nowe wiersze mają kody 100, 130, 160, 190 i 220. Użyj wartość przyrostu, która zapewnia wystarczający odstęp na wstawienie nowych wierszy formatu i formuły.
7. Kliknij przycisk **OK** Dla każdej wybranej wartości wymiaru jest dodawany jeden wiersz do definicji wiersza.

## <a name="adjust-rounding-in-a-row-definition"></a> Korekta zaokrąglenia w definicji wiersza
W przypadku bilansu, w którym kwoty są zaokrąglane, sumy mogą się nie bilansować. Ten problem może wystąpić, jeśli na przykład używasz opcji zaokrąglania w raporcie o bilansie, a definicja raportu również określa zaokrąglanie. Aby bilansować kwoty w bilansach, można w definicji wiersza użyć opcji **Korygowanie zaokrągleń**. W definicji raportu na karcie **Ustawienia** można wyłączyć zaokrąglanie lub je zmodyfikować. W poniższej tabeli przedstawiono sposób zaokrąglania kwot: W tej tabeli sumy wierszy 100 i 200 różnią się, gdy zaokrąglanie jest włączone.

| Kod wiersza | Kwoty bez zaokrąglania | Kwota z zaokrąglaniem do całych tysięcy |
|----------|--------------------------|-----------------------------------------|
| 100      | 3600                    | 4                                       |
| 200      | 3700                    | 4                                       |
| Suma    | 7300                    | 8                                       |

Aby dostosować zaokrąglenie w bilansie, należy wykonać następujące kroki:

1. W Projektancie raportów kliknij **Definicje wiersza**, a następnie otwórz definicje wiersza do zmodyfikowania.
2. W menu **Edycja** kliknij polecenie **Doksięgowanie zaokrągleń**.
3. W oknie dialogowym **Korygowanie zaokrągleń** wpisz następujące wartości:

    - **Wiersz korekty zaokrąglania** — kod wiersza, który powinien być korygowany w celu zbilansowania bilansu.
    - **Wiersz sumy aktywów** — kod wiersza dla wierszy w bilansie, który zawiera sumy aktywów.
    - **Wiersz sumy zobowiązań i kapitału własnego** — kod wiersza dla wierszy w bilansie, który zawiera sumy zobowiązań i kapitału własnego.
    - **Limit kwoty korekty** — dodatnia liczba całkowita określająca limit dla automatycznych korekt. Ta kwota jest porównywana z bezwzględną wartością rzeczywistej różnicy zaokrągleń.

    > [!NOTE]
    > Te kody wierszy muszą być połączone z danymi finansowymi. Innymi słowy, wiersz musi mieć wartość wymiaru w komórce **Łącze do Wymiary finansowe**. **Nie** należy używać odwołania do wiersza opisu (**DESC**), obliczenia (**CALC**) ani sumy (**TOT**).

Kwoty w bilansie będą teraz bilansowane równomiernie, gdy jest włączone zaokrąglanie.

> [!NOTE]
> Limit doksięgowania jest stosowany na podstawie opcji **Dokładność zaokrąglania** określonej w definicji raportu. Na przykład zaokrąglanie raportu do tysięcy i wprowadzenie wartości **2** w polu **Limit kwoty korekty** spowoduje wyświetlanie komunikatu ostrzegawczego, gdy wartość określona w polu **Wiersz korekty zaokrąglania** zwiększy się lub zmniejszy o ponad 2000.

## <a name="format-row-and-column-text"></a>Formatowanie tekstu wiersza i kolumny
Można dostosować wygląd raportów, zmieniając czcionki i formatując tekst. Poniższe sekcje zawierają wyjaśnienia dotyczące formatowania wyglądu wierszy i kolumn w raportach.

### <a name="manage-font-styles"></a>Zarządzanie stylami czcionek

Można tworzyć i modyfikować style czcionek dla raportu. Następnie można zastosować te style do dokumentu albo do określonego wiersza lub kolumny w raporcie.

<table>
<tbody>
<tr>
<td><strong>Tworzenie stylu czcionki</strong></td>
<td>
<ol>
<li>W Projektancie raportów w menu <strong>Format</strong> kliknij <strong>Style i formatowanie</strong>.</li>
<li>W oknie dialogowym <strong>Style i formatowanie</strong> kliknij przycisk <strong>Nowy</strong>, po czym nadaj nowemu stylowi unikatową nazwę.</li>
<li>Zaznacz parametry czcionki i kliknij przycisk <strong>OK</strong>.</li>
</ol>
</td>
</tr>
<tr>
<td><strong>Modyfikowanie stylu czcionki</strong></td>
<td>
<ol>
<li>W Projektancie raportów w menu <strong>Format</strong> kliknij <strong>Style i formatowanie</strong>.</li>
<li>W oknie dialogowym <strong>Style i formatowanie</strong> zaznacz styl, który chcesz zmodyfikować, i kliknij przycisk <strong>Modyfikuj</strong>.</li>
<li>Zaznacz parametry czcionki i kliknij przycisk <strong>OK</strong>.</li>
</ol>
</td>
</tr>
<tr>
<td><strong>Stosowanie stylu czcionki</strong></td>
<td>
<ol>
<li>W Projektancie raportów, w definicji lub definicji kolumny albo w nagłówkach i stopkach, wybierz jedną lub więcej komórek.</li>
<li>Na pasku narzędzi na liście <strong>Styl</strong> zaznacz styl czcionki.</li>
</ol>
</td>
</tr>
</tbody>
</table>

### <a name="format-row-text"></a>Formatowanie tekstu wiersza

Formatowanie określone w definicji wiersza zastępuje wszelkie formatowanie określone w definicji kolumny oraz w definicji raportu. Format tekstu można zmodyfikować za pomocą formantów na pasku narzędzi formatowania. Są to standardowe formanty systemu Microsoft Windows.

1. W Projektancie raportów otwórz definicję wierszy, którą chcesz zmodyfikować.
2. Zaznacz komórki do formatowania. Aby wybrać wiele komórek, przytrzymaj klawisz Ctrl i zaznaczaj kolejne komórki.
3. Kliknij przycisk na pasku narzędzi dla formatu, który chcesz zastosować. Na przykład aby zwiększyć wcięcie wiersza, zaznacz wiersz, a następnie kliknij **Zwiększ wcięcie** ![Zwiększ wcięcie.](media/indent.gif "Zwiększ wcięcie") na pasku narzędzi.

### <a name="adjust-columns-while-you-design-reports"></a>Dostosowywanie kolumn podczas projektowania raportów

Aby ułatwić wyświetlanie kolumn, nad którymi pracujesz w definicji wiersza, można dopasować szerokość kolumny oraz ukryć (zminimalizować) lub pokazać kolumny w okienku widoku. Wprowadzane modyfikacje wpływają tylko na wygląd kolumn na ekranie. Nie wpływają na formatowanie kolumn w raportach.

### <a name="change-the-width-of-a-column-in-the-view-pane"></a>Zmienianie szerokości kolumny w okienku widoku

1. W Projektancie raportu otwórz definicję wiersza do zmodyfikowania.
2. W menu **Format** wybierz **Szerokość kolumny**.
3. W oknie dialogowym **Szerokość kolumny** wprowadź wartość, a następnie kliknij przycisk **OK**. Alternatywnie można przeciągać prawą granicę komórki nagłówka kolumny, aby zmienić szerokość kolumny.

### <a name="hide-columns-in-the-view-pane"></a>Ukrywanie kolumn w okienku widoku

1. W Projektancie raportu otwórz definicję wiersza do zmodyfikowania.
2. Zaznacz kolumnę lub kolumny, które chcesz zminimalizować.
3. Kliknij prawym przyciskiem myszy, a następnie kliknij **Ukryj**.

### <a name="show-all-hidden-columns-in-the-view-pane"></a>Pokazywanie wszystkich ukrytych kolumn w okienku widoku

1. W Projektancie raportu otwórz definicję wiersza do zmodyfikowania.
2. Kliknij prawym przyciskiem myszy zminimalizowaną kolumnę, którą chcesz wyświetlać, a następnie kliknij **Odkryj**.


## <a name="additional-resources"></a>Dodatkowe zasoby

[Raportowanie finansowe](financial-reporting-intro.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
