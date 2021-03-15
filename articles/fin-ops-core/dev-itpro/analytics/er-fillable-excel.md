---
title: Projektowanie konfiguracji projektu w celu generowania dokumentów wychodzących w formacie programu Excel
description: Ten temat zawiera informacje o tym, jak zaprojektować format modułu raportowania elektronicznego (ER) do wypełniania w szablonie programu Excel, a następnie generować dokumenty wychodzące w formacie programu Excel.
author: NickSelin
manager: AnnBe
ms.date: 11/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: EROperationDesigner, ERParameters
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c8d6a18741d57829d1929fb8362dc4ba8e03a1bd
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/30/2021
ms.locfileid: "5094036"
---
# <a name="design-a-configuration-for-generating-documents-in-excel-format"></a>Projektowanie konfiguracji projektu w celu generowania dokumentów wychodzących w formacie programu Excel

[!include[banner](../includes/banner.md)]

Istnieje możliwość zaprojektowania konfiguracji formatu modułu [Raportowanie elektroniczne (ER)](general-electronic-reporting.md) ze [składnikiem formatu](general-electronic-reporting.md#FormatComponentOutbound) ER, który można skonfigurować do generowania dokumentu wychodzącego w formacie skoroszytu programu Microsoft Excel. W tym celu muszą być używane określone składniki formatu ER.

Aby dowiedzieć się więcej o tej funkcji, wykonaj kroki opisane w temacie [Projektowanie konfiguracji do generowania raportów w formacie OPENXML](tasks/er-design-reports-openxml-2016-11.md).

## <a name="add-a-new-er-format"></a>Dodawanie nowego formatu ER

Podczas dodawania nowej konfiguracji formatu ER do generowania dokumentu wychodzącego w formacie skoroszytu programu Excel należy wybrać wartość **Excel** dla atrybutu **Typ formatu** lub pozostawić atrybut **Typ formatu**.

- W przypadku wybrania pozycji **Excel** można skonfigurować format w celu generowania dokumentu wychodzącego tylko w formacie programu Excel.
- Jeśli atrybut pozostanie pusty, można skonfigurować format do generowania dokumentu wychodzącego w dowolnym formacie obsługiwanym przez platformę ER.

Aby skonfigurować składnik formatu ER konfiguracji, wybierz pozycję **Projektant** w okienku akcji, a następnie otwórz składnik formatu ER do edycji w projektancie operacji ER.

![Strona Konfiguracje](./media/er-excel-format-add-format.png)

## <a name="excel-file-component"></a>Składnik pliku programu Excel

### <a name="manual-entry"></a>Wpis ręczny

Musisz dodać składnik **Excel\\Plik** do skonfigurowanego formatu ER, aby wygenerować dokument wychodzący w formacie programu Excel.

![Składnik Excel\Plik](./media/er-excel-format-add-file-component.png)

Aby określić układ dokumentu wychodzącego, dołącz skoroszyt programu Excel z rozszerzeniem xlsx do składnika **Excel\\Plik** jako szablon dokumentów wychodzących.

> [!NOTE]
> Podczas ręcznego dołączania szablonu należy użyć [typu dokumentu](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-document-management#configure-document-types), który został skonfigurowany dla tego celu w obszarze [parametrów ER](electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents).

![Dodawanie załącznika do składnika Excel\Plik](./media/er-excel-format-add-file-component2.png)

Aby określić sposób, w jaki dołączony szablon będzie wypełniany po uruchomieniu skonfigurowanego formatu ER, musisz dodać zagnieżdżone składniki **Arkusz**, **Zakres** i **Komórka** do składnika **Excel\\Plik**. Każdy zagnieżdżony składnik musi być skojarzony z nazwanym elementem programu Excel.

### <a name="template-import"></a>Importowanie szablonu

Możesz wybrać pozycję **Importuj z programu Excel** na karcie **Importowanie** w okienku akcji, aby zaimportować nowy szablon do pustego formatu ER. W tym przykładzie składnik **Excel\\Plik** zostanie utworzony automatycznie, a następnie zostanie do niego dołączony zaimportowany szablon. Wszystkie wymagane składniki ER również zostaną utworzone automatycznie na podstawie listy odnalezionych nazwanych elementów w programie Excel.

![Wybieranie pozycji Importuj z programu Excel](./media/er-excel-format-import-template.png)

> [!NOTE]
> Jeśli chcesz utworzyć opcjonalny element **Arkusz** w edytowalnym formacie ER, ustaw opcję **Utwórz element formatu Arkusz programu Excel** na **Tak**.

## <a name="sheet-component"></a>Składnik Arkusz

Składnik **Arkusz** wskazuje arkusz dołączonego skoroszytu programu Excel, który musi zostać wypełniony. Nazwa arkusza w szablonie programu Excel jest definiowana we właściwości **Arkusz** tego składnika.

> [!NOTE]
> Ten składnik jest opcjonalny dla skoroszytów programu Excel zawierających pojedynczy arkusz.

Na karcie **Mapowanie** projektanta operacji ER można skonfigurować właściwość **Włączone** dla składnika **Arkusz**, aby określić, czy składnik musi być umieszczany w generowanym dokumencie:

- Jeśli wyrażenie właściwości **Włączone** zostało skonfigurowane do zwracania wartości **Prawda** w czasie wykonywania lub nie skonfigurowano żadnego wyrażenia, odpowiedni arkusz zostanie umieszczony w wygenerowanym dokumencie.
- Jeśli wyrażenie właściwości **Włączone** zostało skonfigurowane tak, aby zwracało wartość **Fałsz** w czasie wykonywania, wygenerowany dokument nie będzie zawierać arkusza.

![Przykład składnika Arkusz](./media/er-excel-format-sheet-component.png)

## <a name="range-component"></a>Składnik Zakres

Składnik **Zakres** wskazuje zakres programu Excel, który musi być kontrolowany przez ten składnik ER. Nazwa zakresu jest definiowana we właściwości **Zakres programu Excel** tego składnika.

Właściwość **Kierunek replikacji** określa, czy i w jaki sposób zakres będzie powtarzany w wygenerowanym dokumencie:

- Jeśli właściwość **Kierunek replikacji** została ustawiona na wartość **Brak replikacji**, odpowiedni zakres programu Excel nie będzie powtarzany w wygenerowanym dokumencie.
- Jeśli właściwość **Kierunek replikacji** została ustawiona na wartość **Pionowo**, odpowiedni zakres programu Excel będzie powtarzany w wygenerowanym dokumencie. Każdy replikowany zakres jest umieszczany poniżej oryginalnego zakresu w szablonie programu Excel. Liczba powtórzeń jest definiowana przez liczbę rekordów w źródle danych typu **Lista rekordów** powiązanego z tym składnikiem ER.
- Jeśli właściwość **Kierunek replikacji** została ustawiona na wartość **Poziomo**, odpowiedni zakres programu Excel będzie powtarzany w wygenerowanym dokumencie. Każdy replikowany zakres jest umieszczany po prawej stronie oryginalnego zakresu w szablonie programu Excel. Liczba powtórzeń jest definiowana przez liczbę rekordów w źródle danych typu **Lista rekordów** powiązanego z tym składnikiem ER.

Aby dowiedzieć się więcej o replikacji poziomej, wykonaj kroki opisane w temacie [Używanie poziomo rozszerzalnych zakresów w celu dynamicznego dodawania kolumn w raportach programu Excel](tasks/er-horizontal-1.md).

Składnik **Zakres** może zawierać inne zagnieżdżone składniki ER, które służą do wprowadzania wartości w odpowiednich nazwanych zakresach programu Excel.

- Jeśli dowolny składnik grupy **Tekst** jest używany do wprowadzania wartości, wartość jest wprowadzana w zakresie programu Excel jako wartość tekstowa.

    > [!NOTE]
    > Ten wzorzec służy do formatowania wprowadzonych wartości na podstawie ustawień regionalnych zdefiniowanych w aplikacji.

- Jeśli składnik **Komórka** grupy **Excel** jest używany do wprowadzania wartości, wartość jest wprowadzana w zakresie programu Excel jako wartość typu danych definiowana przez powiązanie tego składnika **Komórka** (np **Ciąg**, **Liczba rzeczywista** lub **Liczba całkowita**).

    > [!NOTE]
    > Ten wzorzec służy do formatowania w aplikacji Excel wprowadzonych wartości na podstawie ustawień regionalnych komputera lokalnego, na którym jest otwierany dokument wychodzący.

Na karcie **Mapowanie** projektanta operacji ER można skonfigurować właściwość **Włączone** dla składnika **Zakres**, aby określić, czy składnik musi być umieszczany w generowanym dokumencie:

- Jeśli wyrażenie właściwości **Włączone** zostało skonfigurowane do zwracania wartości **Prawda** w czasie wykonywania lub nie skonfigurowano żadnego wyrażenia, odpowiedni zakres zostanie wypełniony w wygenerowanym dokumencie.
- Jeśli wyrażenie właściwości **Włączone** zostało skonfigurowane do zwracania wartości **Fałsz** w czasie wykonywania, a zakres nie reprezentuje całych wierszy lub kolumn, odpowiedni zakres nie zostanie wypełniony w wygenerowanym dokumencie.
- Jeśli wyrażenie właściwości **Włączone** zostało skonfigurowane do zwracania wartości **Fałsz** w czasie wykonywania, a zakres reprezentuje całe wiersze lub kolumny, wygenerowany dokument będzie zawierać te wiersze i kolumny jako ukryte.

## <a name="cell-component"></a>Składnik Komórka

Składnik **Komórka** służy do wypełniania nazwanych komórek, kształtów i obrazów w programie Excel. Aby wskazać nazwany obiekt programu Excel, który musi zostać wypełniony przez składnik ER **Komórka**, należy określić nazwę tego obiektu we właściwości **Zakres programu Excel** składnika **Komórka**.

Na karcie **Mapowanie** projektanta operacji ER można skonfigurować właściwość **Włączone** dla składnika **Komórka**, aby określić, czy obiekt musi być wypełniany w generowanym dokumencie:

- Jeśli wyrażenie właściwości **Włączone** zostało skonfigurowane do zwracania wartości **Prawda** w czasie wykonywania lub nie skonfigurowano żadnego wyrażenia, odpowiedni obiekt zostanie wypełniony w wygenerowanym dokumencie. Powiązanie tego składnika **Komórka** określa wartość, która jest umieszczana w odpowiednim obiekcie.
- Jeśli wyrażenie właściwości **Włączone** zostało skonfigurowane tak, aby zwracało wartość **Fałsz** w czasie wykonywania, odpowiedni obiekt nie będzie wypełniany w wygenerowanym dokumencie.

Jeśli składnik **Komórka** został skonfigurowany do wprowadzania wartości w komórce, może być powiązany ze źródłem danych zwracającym wartość z pierwotnym typem danych (na przykład **Ciąg**, **Liczba rzeczywista** lub **Liczba całkowita**). W takim przypadku wartość jest wprowadzana do komórki jako wartość tego samego typu danych.

Jeśli składnik **Komórka** został skonfigurowany do wprowadzania wartości w kształcie programu Excel, może być powiązany ze źródłem danych zwracającym wartość z pierwotnym typem danych (na przykład **Ciąg**, **Liczba rzeczywista** lub **Liczba całkowita**). W takim przypadku wartość jest wprowadzana w kształcie programu Excel jako tekst tego kształtu. W przypadku wartości typów danych innych niż **Ciąg**, konwersja na tekst jest dokonywana automatycznie.

> [!NOTE]
> Składnik **Komórka** można skonfigurować do wypełniania kształtu tylko w przypadkach, w których właściwość tekstu kształtu jest obsługiwana.

Jeśli składnik **Komórka** został skonfigurowany do wprowadzania wartości w obrazie programu Excel, może być powiązany ze źródłem danych zwracającym wartość z typem danych **Kontener**, które reprezentuje obraz w formacie binarnym. W takim przypadku wartość jest wprowadzana w obrazie programu Excel jako obraz.

> [!NOTE]
> Każdy obraz i kształt programu Excel jest traktowany jako zakotwiczony do lewego górnego rogu do konkretnej komórki lub zakresu w programie Excel. Aby replikować obraz lub kształt programu Excel, należy skonfigurować komórkę lub zakres, do którego zostały one zakotwiczone, jako zreplikowaną komórkę lub zakres.

Aby dowiedzieć się więcej na temat osadzania obrazów i kształtów, zobacz temat [Osadzanie obrazów i kształtów w generowanych dokumentach przez raportowanie elektroniczne](electronic-reporting-embed-images-shapes.md).

## <a name="page-break-component"></a>Składnik Podział strony

Składnik **PageBreak** wymusza rozpoczęcie nowej strony przez program Excel. Ten składnik nie jest wymagany, jeśli ma być używany domyślne stronicowanie programu Excel, ale powinien być używany, jeśli chcesz, aby program Excel korzystał z formatu ER w celu utworzenia struktury stronicowania.

## <a name="edit-an-added-er-format"></a>Edytowanie dodanego formatu ER

### <a name="update-a-template"></a>Aktualizowanie szablonu

Możesz wybrać pozycję **Aktualizuj z programu Excel** na karcie **Importowanie** w okienku akcji, aby zaimportować zaktualizowany szablon do edytowalnego formatu ER. W trakcie tego procesu szablon wybranego składnika **Excel\\File** zostanie zastąpiony nowym szablonem. Zawartość edytowalnego formatu ER zostanie zsynchronizowana z zawartością zaktualizowanego szablonu ER.

- Nowy składnik formatu ER zostanie utworzony automatycznie dla każdej nazwy programu Excel, jeśli składnik formatu ER nie zostanie znaleziony w formacie edytowalnym.
- Każdy składnik formatu ER zostanie usunięty z edytowalnego formatu ER, jeśli dla niego nie zostanie znaleziona odpowiednia nazwa programu Excel.

> [!NOTE]
> Ustaw opcję **Utwórz element formatu Arkusz programu Excel** na **Tak**, jeśli chcesz utworzyć opcjonalny element **Arkusz** w edytowalnym formacie ER.
>
> Jeśli edytowalny format ER pierwotnie zawierał elementy **Arkusz**, zalecamy ustawienie opcji **Utwórz element formatu Arkusz programu Excel** na wartość **Tak** podczas importowania zaktualizowanego szablonu. W przeciwnym razie wszystkie zagnieżdżone elementy oryginalnego elementu **Arkusz** zostaną utworzone od początku. Dlatego wszystkie powiązania nowo utworzonych elementów formatu zostaną utracone w zaktualizowanym formacie ER.

![Opcja Utwórz element formatu Arkusz programu Excel w oknie dialogowym aktualizowania z programu Excel](./media/er-excel-format-update-template.png)

Aby dowiedzieć się więcej o tej funkcji, wykonaj kroki opisane w temacie [Modyfikowanie formatów raportowania elektronicznego przez ponowne zastosowanie szablonów programu Excel](modify-electronic-reporting-format-reapply-excel-template.md).

## <a name="validate-an-er-format"></a>Weryfikowanie formatu ER

Podczas weryfikowania formatu ER, który można edytować, jest przeprowadzane sprawdzenie spójności w celu upewnienia się, że nazwa programu Excel znajduje się w aktualnie używanym szablonie programu Excel. Otrzymasz powiadomienie o ewentualnych niespójnościach. W przypadku niektórych niespójności będą oferowane opcje automatycznego rozwiązania danego problemu.

![Komunikat o błędzie weryfikacji](./media/er-excel-format-validate.png)

## <a name="control-the-calculation-of-excel-formulas"></a>Sterowanie obliczaniem formuł programu Excel

Podczas generowania dokumentu wychodzącego w formacie skoroszytu programu Microsoft Excel niektóre komórki tego dokumentu mogą zawierać formuły programu Excel. Gdy jest włączona funkcja **Włącz korzystanie z biblioteki EPPlus w ramach raportowania elektronicznego**, można kontrolować, kiedy formuły będą obliczane, zmieniając wartość [parametru](https://support.microsoft.com/office/change-formula-recalculation-iteration-or-precision-in-excel-73fc7dac-91cf-4d36-86e8-67124f6bcce4#ID0EAACAAA=Windows) **Opcje obliczania** w używanym szablonie programu Excel:

- Wybierz opcję **Automatycznie**, aby ponownie obliczać wszystkie formuły zależne za każdym razem, gdy do wygenerowanego dokumentu są dołączane nowe zakresy, komórki itp.
    >[!NOTE]
    > Może to spowodować problemy z wydajnością działania szablonów programu Excel zawierających wiele powiązanych formuł.
- Wybierz opcję **Ręcznie**, aby uniknąć ponownego obliczania formuł podczas generowania dokumentu.
    >[!NOTE]
    > Ponowne obliczanie formuł jest wymuszane ręcznie po otwarciu wygenerowanego dokumentu do podglądu za pomocą programu Excel.
    > Nie należy stosować tej opcji w przypadku konfigurowania miejsca docelowego modułu ER, które zakłada używanie wygenerowanego dokumentu bez obejrzenia jego podglądu w programie Excel (konwersja do pliku PDF, wysłanie wiadomości e-mail itp.), ponieważ wygenerowany dokument może nie zawierać wartości w komórkach z formułami.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Raportowanie elektroniczne — omówienie](general-electronic-reporting.md)

[Projektowanie konfiguracji do generowania raportów w formacie OPENXML](tasks\er-design-reports-openxml-2016-11.md)

[Modyfikowanie formatów raportowania elektronicznego przez ponowne zastosowanie szablonów programu Excel](modify-electronic-reporting-format-reapply-excel-template.md)

[Używanie poziomo rozszerzalnych zakresów w celu dynamicznego dodawania kolumn w raportach programu Excel](tasks/er-horizontal-1.md)

[Osadzanie obrazów i kształtów w generowanych dokumentach przez raportowanie elektroniczne](electronic-reporting-embed-images-shapes.md)

[Konfigurowanie w module Raportowanie elektroniczne (ER) ściągania danych do usługi Power BI](general-electronic-reporting-report-configuration-get-data-powerbi.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]