---
title: Korzystanie ze źródeł danych DATA COLLECTION w formatach raportowania elektronicznego
description: W tym artykule wyjaśniono, jak można używać źródeł danych DATA COLLECTION w formatach raportowania elektronicznego (ER).
author: NickSelin
ms.date: 08/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EROperationDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2021-01-01
ms.dyn365.ops.version: AX 10.0.16
ms.openlocfilehash: 7591bed5d01ce2c2f434f0e7c81e441eda98483e
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8883854"
---
# <a name="use-data-collection-data-sources-in-electronic-reporting-formats"></a>Korzystanie ze źródeł danych DATA COLLECTION w formatach raportowania elektronicznego

[!include [banner](../includes/banner.md)]

Za pomocą projektanta operacji w strukturze [elektronicznego modułu sprawozdawczego](general-electronic-reporting.md) (ER) można skonfigurować składnik formatu rozwiązania ER używanego do generowania dokumentów wychodzących w różnych formatach. Hierarchiczna struktura skonfigurowanego składnika formatu składa się z elementów formatu różnych typów. Te elementy formatu służą do wypełniania wygenerowanych dokumentów informacjami wymaganymi w czasie wykonywania. Domyślnie w przypadku uruchamiania formatu ER elementy formatu są uruchamiane w tej samej kolejności, w jakiej są przedstawione w hierarchii formatów: jeden po jednym — od góry do dołu.

Gdy ER korzysta z formatu zawierającego powiązanie, zostanie uruchomiona formuła tego powiązania, a element formatu doda wartość do wygenerowanego dokumentu. Na przykład powiązanie może przekazać wartość pola modelu danych do elementu formatu. Źródło danych DATA COLLECTION można skonfigurować w taki sposób, aby zbierało wartości pól modelu danych w czasie wykonywania, sumowało wartości i wypełniało wygenerowany dokument zebranymi wartościami. Aby użyć tej metody, zmień początkowe powiązanie, tak aby skonfigurowane źródło danych DATA COLLECTION było używane do przekazania wartości pola modelu danych do elementu formatu. Przekazując wartości za pośrednictwem źródła danych DATA COLLECTION, można gromadzić wymagane szczegóły do dalszego użycia.

Konfigurując źródło danych DATA COLLECTION, należy określić typ wartości, który będzie zarządzany w źródle danych. Następujące [typy danych](er-formula-supported-data-types-primitive.md) są obecnie obsługiwane do zbierania wartości:

- Wartość logiczna
- Data
- Data/godzina
- Identyfikator Guid
- Int64
- Wartość całkowita
- Rzeczywisty
- Ciąg
- Godzina

Za pomocą metody źródła danych DATA COLLECTION można przekazać wartość `Collect(Value)` do źródła danych w celu zbierania. W tej metodzie argument `Value` jest stałą lub prawidłową ścieżką pola źródła danych odpowiedniego typu danych.

Przy użyciu właściwości `Result` źródła danych DATA COLLECTION można uzyskać dostęp do listy zebranych wartości. Właściwość ta zwraca [listę rekordów](er-formula-supported-data-types-composite.md#record-list). Rekordy listy rekordów zawierają pole `Value`, które umożliwia dostęp do zebranych wartości.

Domyślnie źródło danych DATA COLLECTION zbiera tylko unikatowe wartości.

Aby zebrać wszystkie wartości, ustaw w polu **Zbierz wszystkie wartości** skonfigurowanego źródła danych DATA COLLECTION wartość **Tak**. Gdy w polu **Zbierz wszystkie wartości** jest ustawiona wartość **Tak**, dostępna jest parametryzowana właściwość `Sum(Flag)`. Za pomocą tej właściwości można uzyskać sumę wszystkich aktualnie zebranych wartości. W tej właściwości argument `Flag` jest wartością [logiczną](er-formula-supported-data-types-primitive.md#boolean), która służy do wskazania, czy wartość całkowita musi zostać zresetowana.

- Po podaniu wartości **False** sumowanie jest kontynuowane od poprzednio zebranej kwoty.
- Po podaniu wartości **True** rozpoczynane jest nowe sumowanie.

Następujące typy danych są obecnie obsługiwane do sumowania:

- Int64
- Wartość całkowita
- Rzeczywisty

Zapoznaj się z następującym przykładem, aby dowiedzieć się więcej.

## <a name="example-configure-an-er-format-to-do-counting-and-summing-by-using-a-data-collection-data-source"></a>Przykład: konfigurowanie formatu ER w celu zliczania i sumowania przy użyciu źródła danych DATA COLLECTION

W tym przykładzie pokazano, w jaki sposób użytkownik występujący w roli Administrator systemu lub Konsultant funkcjonalny raportowania elektronicznego może skonfigurować format raportowania elektronicznego, który ma źródło danych DATA COLLECTION używane do obliczania sum bieżących i zbierania sumowanych wartości.

Zadania przedstawione w tym przykładzie można wykonać w kontekście firmy USMF w aplikacji Microsoft Dynamics 365 Finance.

### <a name="upload-and-use-the-provided-er-solution"></a>Przekazywanie i używanie dostarczonego rozwiązania ER

1. [Importuj przykładowe konfiguracje ER](er-defer-sequence-element.md#import-the-sample-er-configurations).
2. [Aktywuj dostawcę konfiguracji](er-defer-sequence-element.md#activate-a-configurations-provider).
3. [Przejrzyj zaimportowane mapowania modelu](er-defer-sequence-element.md#review-the-imported-model-mapping).
4. [Przeglądanie zaimportowanego formatu](er-defer-sequence-element.md#review-the-imported-format).
5. [Uruchamianie zaimportowanego formatu](er-defer-sequence-element.md#run-the-imported-format).

### <a name="run-the-format-of-the-provided-er-solution"></a>Wykonywanie formatu dostarczonego rozwiązania ER

1. Na stronie **Projektant formatów** wybierz opcję **Uruchom**.
2. W oknie dialogowym **Parametry raportu elektronicznego** wybierz przycisk **OK**.
3. Pobierz plik przez przeglądarkę sieci Web i otwórz go do przeglądu.

    ![Pobrany plik zawierający wyniki początkowego wykonania formatu](./media/er-data-collection-data-sources-01.png)

### <a name="modify-the-format-of-the-er-solution-to-calculate-the-running-tax-total"></a>Modyfikowanie formatu rozwiązania ER w celu obliczenia sumy uruchomionego podatku

Jeśli wielkość transakcji jest znacznie większa niż objętość w bieżącym przykładzie, czas wymagany na sumowanie może ulec wydłużeniu i spowodować problemy z wydajnością. Zmiana ustawień formatu pozwala uniknąć tych problemów z wydajnością. Ponieważ są dostępne wartości podatku w celu uwzględnienia ich w generowanym raporcie, można użyć tych informacji do zsumowania wartości podatku.

1. Na stronie **Projektant formatów**, na karcie **Mapowanie** wybierz **Dodaj źródło**.
2. W oknie dialogowym **Dodawanie źródła danych** wybierz kolejno pozycje **Funkcje** \> **Zbieranie danych**.
3. W oknie dialogowym **Właściwości źródła danych „Zbieranie danych”** wykonaj następujące czynności:

    1. W polu **Nazwa** wpisz **CollectedTaxValues**.
    2. W polu **Typ przedmiotu** wybierz **Rzeczywisty**.
    3. W polu **Zbierz wszystkie wartości** wybierz opcję **Tak**.
    4. Kliknij przycisk **OK**.

4. Wybierz liczbowy element formatu **Raport\\Wiersze\\Rekord\\TaxAmount**.

    > [!NOTE]
    > Obecnie dla tego elementu jest skonfigurowane powiązanie `@.Value`. Z tego powodu generowany dokument jest wypełniany wartościami podatku z pola `model.Data.List.Value`.

5. Wybierz opcję **Edytuj formułę**.
6. Na stronie **Projektant formuł** wykonaj następujące kroki:

    1. W polu **Formuła** zmień wartość `@.Value` na `CollectedTaxValues.Collect(@.Value)`.
    2. Zapisz zmiany i zamknij stronę.

    > [!NOTE]
    > Nowe powiązanie przekaże te same wartości podatku do wygenerowanego dokumentu. Jednak te wartości są także zbierane w źródle danych **CollectedTaxValues**.

7. Wybierz liczbowy element formatu **Raport\\Wiersze\\Rekord\\RunnintTotal**.
8. Wybierz opcję **Edytuj formułę**.
9. Na stronie **Projektant formuł** wykonaj następujące kroki:

    1. W polu **Formuła** wpisz `CollectedTaxValues.Sum(false)`.
    2. Zapisz zmiany i zamknij stronę.

    > [!NOTE]
    > Nowe powiązanie przekaże do wygenerowanego dokumentu sumę wartości podatku, które zostały już wprowadzone.

    ![Elementy liczbowe, które zaktualizowały powiązania na stronie Projektant formatów](./media/er-data-collection-data-sources-02.png)

10. Wybierz **Zapisz** i następnie wybierz **Uruchom**.
11. W oknie dialogowym **Parametry raportu elektronicznego** wybierz przycisk **OK**.
12. Pobierz plik przez przeglądarkę sieci Web i otwórz go do przeglądu.

    ![Pobrany plik zawierający wyniki zmodyfikowanego wykonania formatu](./media/er-data-collection-data-sources-03.png)

### <a name="modify-the-format-to-evaluate-the-list-of-collected-tax-values"></a>Modyfikowanie formatu, aby ocenić listę zebranych wartości podatku

1. Na stronie **Projektant formatów**, na karcie **Format** wybierz element liczbowy formatu **Report\\Wiersze\\Rekord\\RunningTotal**, a następnie wykonaj następujące kroki:

    1. W polu **Typ liczbowy** zmień wartość z **Rzeczywisty** na **Całkowity**.
    2. W polu **Format liczbowy** zmień wartość z **F2** na **F0**.

3. Na karcie **Mapowanie** wybierz opcję **Edytuj formułę**.
4. Na stronie **Projektant formuł** wykonaj następujące kroki:

    1. W polu **Formuła** wpisz `COUNT(CollectedTaxValues.Result)`.
    2. Zapisz zmiany i zamknij stronę.

    > [!NOTE]
    > Nowe powiązanie przekaże do wygenerowanego dokumentu liczbę rekordów z listy, na której są zbierane wartości podatku.

5. Wybierz **Zapisz** i następnie wybierz **Uruchom**.
6. W oknie dialogowym **Parametry raportu elektronicznego** wybierz przycisk **OK**.
7. Pobierz plik przez przeglądarkę sieci Web i otwórz go do przeglądu.

    ![Pobrany plik zawierający wyniki innego zmodyfikowanego wykonania formatu](./media/er-data-collection-data-sources-04.png)

## <a name="frequently-asked-questions"></a>Często zadawane pytania

### <a name="if-i-have-to-calculate-running-totals-and-collect-data-what-is-the-difference-between-using-a-data-collection-data-source-and-using-the-built-in-data-collection-functions"></a>Jaka jest różnica między używaniem źródła danych DATA COLLECTION a wbudowanych funkcji DATA COLLECTION, jeśli są obliczane sumy bieżące i zbierane dane?

Zarówno źródła danych DATA COLLECTION, jak i wbudowanych funkcji [DATA COLLECTION](er-functions-category-data-collection.md) można używać do zbierania danych, sumowania i zliczania na podstawie informacji przekazywanych do wygenerowanego dokumentu wychodzącego. Jednak, gdy próbujesz zdecydować, której metody użyć, musisz wziąć pod uwagę następujące kwestie.

| Źródło danych | Funkcje wbudowane |
|-------------| ------------------ |
| Zbierane są tylko wartości. | <p>Zbierane są nazwane wartości. W związku z tym sumy można obliczać dla oddzielnych grup wartości.</p><p>Ponadto grupy mogą być wyodrębnione jako listy.</p><p>Można także zbierać wartości tekstowe.</p> |
| Unikatowe wartości są zbierane automatycznie. | Dodatkowe ustawienia są wymagane, aby wyodrębnić listę unikatowych wartości ze zebranych wartości. |
| Wydajność zależy od objętości zebranych wartości. | W praktyce wydajność nie zależy od objętości zebranych wartości. |
| Ta technika działa ze wszystkimi typami dokumentów wychodzących. | Ta technika działa tylko z dokumentami tekstowymi i XML. |

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Konfigurowanie formatu do inwentaryzacji i sumowania](./tasks/er-format-counting-summing-1.md)
- [Odłóż wykonanie elementów sekwencji w formatach raportowania elektronicznego](er-defer-sequence-element.md#Example)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
