---
title: Używanie źródeł danych z kodem kreskowym do generowania obrazów kodów kreskowych
description: W tym temacie objaśniono sposób używania źródeł danych z kodem kreskowym w celu generowania obrazów kodów kreskowych.
author: NickSelin
manager: AnnBe
ms.date: 10/21/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERModelMappingDesigner, EROperationDesigner
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: Version 10.0.13
ms.openlocfilehash: bf71caf2ff14fb815999e63d6b7ee91afccbdd1b
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2021
ms.locfileid: "5563686"
---
# <a name="use-barcode-data-sources-to-generate-bar-code-images"></a>Używanie źródeł danych z kodem kreskowym do generowania obrazów kodów kreskowych

[!include[banner](../includes/banner.md)]

Struktury [Elektronicznego raportowania (ER)](general-electronic-reporting.md) można używać do projektowania [składników frormatu ER](general-electronic-reporting.md#FormatComponentOutbound), które można uruchomić w celu wygenerowania potrzebnych elektronicznych i drukowalnych dokumentów wychodzących. Aby wygenerować dokument wychodzący w formacie Microsoft Office, należy określić układ raportu, używając dokumentu Microsoft Excel lub dokumentu Microsoft Word jako szablonu raportu. [Projektant Operacji ER](general-electronic-reporting.md#building-a-format-that-uses-a-data-model-as-a-base) umożliwia dołączenie dokumentu programu Excel lub Word jako szablonu dla formatu ER. Następujące nazwane elementy w dołączonym szablonie są skojarzone z elementami skonfigurowanego składnika formatu:

- Kontrolki zawartości w programie Word
- Nazwane arkusze, zakresy, komórki, kształty i obrazy w programie Excel

Te nazwane elementy są używane jako symbole zastępcze dla danych wprowadzanych w wygenerowanym dokumencie w przypadku uruchomienia formatu ER. Elementy formatu ER są powiązane ze źródłami danych. Te źródła danych określają dane, które zostaną wprowadzone w wygenerowanych dokumentach w czasie wykonywania. Aby uzyskać więcej informacji, zobacz [Osadzanie obrazów i kształtów w generowanych dokumentach przez raportowanie elektroniczne](electronic-reporting-embed-images-shapes.md)

ER obsługuje obecnie typ źródła danych **Kod kreskowy**. Dlatego teraz można wygenerować obraz reprezentujący kod kreskowy dla określonego tekstu. Konfigurując format ER, można określić źródła danych typu **Kod kreskowy** w celu wygenerowania obrazów kodów kreskowych. Następnie można dodawać te obrazy do wygenerowanych dokumentów biznesowych, takich jak zamówienia, faktury, dokumenty dostawy i przychody. Można je również dodawać do różnych rodzajów etykiet, takich jak etykiety produktów i półek oraz etykiety opakowań i wysyłkowe.

W szablonach raportów można używać następujących symboli zastępczych do wprowadzania obrazów kodów kreskowych:

- Kontrolka zawartości [obrazu](https://docs.microsoft.com/office/client-developer/word/content-controls-in-word) dla programu Word
- Objekt [obrazu](https://support.office.com/article/insert-pictures-3c51edf4-22e1-460a-b372-9329a8724344) w programie Excel

Korzystając ze źródła danych typu **Kod kreskowy**, można generować kody kreskowe w następujących formatach:

- Jednowymiarowe kody kreskowe:

    - Codabar
    - Code 39
    - Code 93
    - Code 128
    - EAN-8
    - EAN-13
    - ITF-14
    - Intelligent Mail
    - MSI
    - Plessey
    - PDF417
    - UPC-A
    - UPC-E

- Dwuwymiarowe kody kreskowe:

    - Aztec
    - Data Matrix
    - Kod QR

Konfigurując źródło danych **Kod kreskowy**, można zdefiniować konkretne parametry renderingu, które są używane do generowania obrazu:

- **Szerokość** — umożliwia określenie szerokości kodu kreskowego w pikselach. Wartość **0** (zero) oznacza, że używana jest szerokość domyślna. Znaczenie może być różne dla różnych formatów.
- **Wysokość** — umożliwia określenie wysokości kodu kreskowego w pikselach. Wartość **0** (zero) oznacza, że używana jest wysokość domyślna. Znaczenie może być różne dla różnych formatów.
- **Margines** — umożliwia określenie rozmiaru margines kodu kreskowego w pikselach. Marża to obszar po obu stronach kodu kreskowego, który musi być wyczyszczony (strefa cicha). Wartość **0** (zero) oznacza, że używana jest margines domyślny. Znaczenie może być różne dla różnych formatów.
- **Zawartość wyjściowa** — ustawienie wartości **Tak** powoduje wygenerowanie obrazu kodu kreskowego zawierającego zakodowane informacje w postaci tekstu. Domyślna wartość to **Nie**.
- **Kodowanie** — umożliwia określenie typu znaków zakodowanych w obrazie generowanego kodu kreskowego. Domyślnie używane jest kodowanie **UTF-8**.

> [!IMPORTANT]
> Dodając nowe źródło danych **Kod kreskowy**, należy umieścić je w innym elemencie (kontener) jako element zagnieżdżony.
>
> W przypadku powiązania źródła danych **Kod kreskowy** z elementem komórki w formacie, a element komórki reprezentuje kontrolka zawartości programu Word lub obraz programu Excel, źródło danych jest prezentowane w tym powiązaniu jako funkcja zawierająca jeden parametr typu **Ciąg**. Tego parametru należy używać do określania tekstu, który powinien zostać przekształcony w obraz kodu kreskowego i odczytywany podczas skanowania wygenerowanego kodu kreskowego.

Aby uzyskać więcej informacji o tej funkcji, uzupełnij przykłady w tym temacie.

## <a name="example-generate-a-payment-check-that-contains-a-bar-code-that-encodes-the-payable-amount"></a>Przykład: generowanie czeku płatności zawierającego kod kreskowy, który koduje kwotę zobowiązania

W tym przykładzie pokazano, jak użytkownik w roli **Administrator systemu** lub **Konsultant funkcjonalny raportowania elektronicznego** może skonfigurować format ER zawierający szablon używany do generowania dokumentu wychodzącego w formacie programu Excel, który zawiera kod kreskowy. Poniżej znajduje się przegląd tych kroków.

1. [Wypełnij wstępnie wymagania](#ExamplePrerequisites).
2. [Aktywuj dostawcę konfiguracji](#ExampleProvider).
3. [Importuj dostarczone rozwiązanie ER](#ExampleImportSolution).
4. [Generowanie sprawdzania płatności](#ExampleGenerateCheque).
5. [Przejrzyj wygenerowany czek płatności](#ExampleReviewGeneratedCheque).
6. [Zmodyfikuj format dostarczonego rozwiązania ER](#ExampleModifyFormat).

    1. [Zastosuj nowy szablon kontroli](#ExampleModifyFormatApplyTemplate).
    2. [Dodaj nowe źródło danych kodów kreskowych](#ExampleModifyFormatAddDataSource).
    3. [Powiąż nowy element formatu](#ExampleModifyFormatBindFormatElement).
    4. [Udostępnij zmodyfikowaną wersję do testów](#ExampleModifyFormatMakeVersionAvailable).

        1. [Wypełnij zmodyfikowaną wersję formatu](#CompleteToRun).
        2. [Udostępnij wersję roboczą do użytku](#MarkToRun).

7. [Generowanie sprawdzania płatności](#ExampleGenerateCheque2).
8. [Przekonwertuj wygenerowane wyniki kontroli na plik PDF](#ExampleConvertToPDF).

W tym przykładzie zostanie użyte dostarczone rozwiązanie ER, które zostało skonfigurowane do generowania czeków płatności. To rozwiązanie generuje czeki płatnicze, w których kwota zobowiązania jest zapisywana jako liczba i jako tekst. Zmodyfikujesz to rozwiązanie ER, aby czek zawierał również wygenerowany kod kreskowy, w którym kodowana jest należna kwota i można go odczytać za pomocą skanera kodów kreskowych.

Kroki można wykonać na przykładzie firmy **USMF** w Microsoft Dynamics 365 Finance.

### <a name="complete-the-prerequisites"></a><a name="ExamplePrerequisites"></a>Wypełnij wstępnie wymagania

Aby wykonać przykłady opisane w tym temacie, trzeba mieć dostęp do firmy USMF wrozwiązaniu Finance dla jednej z następujących ról:

- Konsultant funkcjonalny raportowania elektronicznego
- Administrator systemu

Jeśli nie zakończono jeszcze analizy przykładu w temacie [Osadzanie obrazów i kształtów w generowanych dokumentach przez raportowanie elektroniczne](electronic-reporting-embed-images-shapes.md), pobierz następujące konfiguracje przykładowego rozwiązania ER.

| Opis zawartości         | Nazwa pliku                   |
|-----------------------------|-----------------------------|
| Konfiguracja modelu danych ER | Model czeków.xml       |
| ER format konfiguracji     | Format drukowania czeków.xml |

Ponadto Pobierz następujący plik programu Excel zawierający zmodyfikowany szablon dla dostarczonego rozwiązania ER.

| Opis zawartości | Nazwa pliku                 |
|---------------------|---------------------------|
| Szablon raportu     | Szablon czeków w Excel.xlsx |

### <a name="activate-a-configuration-provider"></a><a name="ExampleProvider"></a>Aktywuj dostawcę konfiguracji

1. Wybierz kolejno opcje **Administrowanie organizacją** \> **Obszary robocze** \> **Raportowanie elektroniczne**.
2. Na stronie **Konfiguracje lokalizacji** w sekcji **Dostawcy konfiguracji** sprawdź, czy [dostawca konfiguracji](general-electronic-reporting.md#Provider) dla przykładowej firmy **Litware, Inc.** jest wymieniony na liście i czy jest oznaczony jako akywny. Jeśli nie ma go na liście lub jeśli nie jest on oznaczony jako aktywny, wykonaj kroki opisane w temacie [Tworzenia dostawcy konfiguracji i zaznaczanie go jako aktywny](tasks/er-configuration-provider-mark-it-active-2016-11.md).

![Ustawienie aktywnej przykładowej firmy na stronie konfiguracji lokalizacji](./media/er-barcode-data-source-active-provider.png)

### <a name="import-the-provided-er-solution"></a><a name="ExampleImportSolution"></a>Importuj dostarczone rozwiązanie ER

1. Wybierz kolejno opcje **Administrowanie organizacją** \> **Obszary robocze** \> **Raportowanie elektroniczne**.
2. WNa stronie **Konfiguracje lokalizacji** w sekcji **Konfiguracje** wybierz kafelek **Konfigracje raportowanias**.
3. Na stronie **Konfiguracje**, jeśli konfiguracja **Model czeków** nie jest dostępna w drzewie konfiguracji, wykonaj następujące kroku, aby importować konfigurację modelu danych ER:

    1. W okienku akcji wybierz opcję **Wymiana** \> **Załaduj z pliku XML**.
    2. W oknie dialogowym wybierz **Przeglądaj**, znajdź i wybierz plik **Model czeków.xml**, a następnie kliknij **OK**.

4. Jeśli konfiguracja **Format drukowania czeków** nie jest dostępna w drzewie konfiguracji, wykonaj następujące kroku, aby importować konfigurację formatu ER:

    1. W okienku akcji wybierz opcję **Wymiana** \> **Załaduj z pliku XML**.
    2. W oknie dialogowym wybierz **Przeglądaj**, znajdź i wybierz plik **Format drukowania czeków.xml**, a następnie kliknij **OK**.

5. W drzewie konfiguracji rozwiń węzeł **Model czeków**.
6. Przejrzyj listę zaimportowanych konfiguracji systemu ER w drzewie konfiguracji.

### <a name="generate-a-payment-check"></a><a name="ExampleGenerateCheque"></a>Generowanie sprawdzania płatności

1. Kliknij kolejno opcje **Zarządzanie gotówką i bankami** \> **Konta bankowe** \> **Konta bankowe**.
2. Na stronie **Konta bankowe** wybierz konto **USMF OPER**.
3. Na stronie szczegółów konta bankowego w okienku akcji na karcie **Konfiguracja**, w grupie **Układ** wybierz opcję **Czek**.
4. Na stronie **Układ czeku** wybierz **Edytuj**.
5. W karcie **Ogólne** ustaw **Ogólny elektroniczny format eksportu** jako **Tak**.
6. W polu **Konfiguracja formatu eksportu** wybierz wcześniej zaimportowany format ER **Format drukowania czeków**.
7. W okienku akcji wybierz pozycję **Drukowanie tekstu**.
8. W oknie dialogowym określ opcję **Format czeków zbywalnych** na **Tak**, a następnie wybierz **OK**.

    ![Układ zaznaczenia — okno dialogowe drukowanie tekstu](./media/er-barcode-data-source-check-layout.png)

### <a name="review-the-generated-payment-check"></a><a name="ExampleReviewGeneratedCheque"></a>Przejrzyj wygenerowany czek płatności

- Otwórz wygenerowany czek w programie Excel.
2. Przejrzyj wygenerowany czek.

    ![Wygenerowany czek płatności w programie Excel](./media/er-barcode-data-source-cheque1.png)

### <a name="modify-the-format-of-the-provided-er-solution"></a><a name="ExampleModifyFormat"></a>Zmodyfikuj format dostarczonego rozwiązania ER

#### <a name="apply-a-new-check-template"></a><a name="ExampleModifyFormatApplyTemplate"></a>Zastosuj nowy szablon kontroli

Za jego poziomu można otworzyć plik **Szablon czeków w Excel.xlsx**, który został wcześniej zaimportowany. Zauważ, że ten szablon różni się od szablonu użytego do wygenerowania czeku płatności w podanym rozwiązaniu ER. Ponadto zawiera element **AmountBarcode** dla obrazu kodu kreskowego.

![Element AmountBarcode w szablonie programu Excel](./media/er-barcode-data-source-cheque2.png)

Musisz teraz zmodyfikować rozwiązanie ER, a następnie [ponownie zastosować](modify-electronic-reporting-format-reapply-excel-template.md) zmodyfikowany szablon.

1. Wybierz kolejno opcje **Administrowanie organizacją** \> **Obszary robocze** \> **Raportowanie elektroniczne**.
2. WNa stronie **Konfiguracje lokalizacji** w sekcji **Konfiguracje** wybierz **Konfigracje raportowanias**.
3. Na stronie **Konfiguracje** w drzewie konfiguracji rozwiń węzeł **Model czeków**, a następnie wybierz opcję **Format drukowania czeków**.
4. W okienku akcji wybierz opcję **Projektant**.
5. W projektancie operacji modułu ER wybierz kartę **Mapowanie** po prawej stronie strony, a następnie w okienku drzewa formatów po lewej stronie wybierz opcję **Rozwiń/Zwiń**.
6. Zwróć uwagę, że wszystkie elementy formatu komórki są powiązane z odpowiednimi źródłami danych.

    ![Powiązanie elementów formatu komórki ze źródłami danych w projektancie operacji ER](./media/er-barcode-data-source-cells-bound.png)

7. Wybierz kartę **Format** po prawej stronie strony.
8. W okienku akcji wybierz wielokropek (**...**), a następnie wybierz opcję **Importuj**.
9. W grupie **Importuj** wybierz **Aktualizację z programu Excel**, a następnie wybierz opcję **Aktualizuj szablon**.
10. W oknie dialogowym przejdź do pliku **Szablon czeków w Excel.xlsx** zapisanego na komputerze, zaznacz go, a następnie wybierz przycisk **OK**, aby potwierdzić, że wybrany szablon ma zostać zastosowany.
11. Wybierz kartę **Mapowanie** po prawej stronie strony, a następnie w okienku drzewa formatów po lewej stronie wybierz opcję **Rozwiń/Zwiń**.
12. Zauważ, że element komórki **AmountBarcode** został dodany do formatu. Ten element jest skojarzony z elementem **AmountBarcode**, który został dodany do zmodyfikowanego szablonu programu Excel jako symbol zastępczy obrazu kodu kreskowego.

    ![Element komórki AmountBarcode dodany do formatu w projektancie operacji ER](./media/er-barcode-data-source-cell-added.png)

#### <a name="add-a-new-barcode-data-source"></a><a name="ExampleModifyFormatAddDataSource"></a>Dodaj nowe źródło danych kodów kreskowych

Następnie należy dodać nowe źródło danych typu **Kod kreskowy**.

1. W projektancie operacji modułu ER na karcie **Mapowanie** po prawej stronie strony wybierz źródło danych **Drukuj**.
2. Wybierz opcję **Dodaj**, a następnie w grupie **Funkcje** wybierz typ źródła danych **Kod kreskowy**.

    ![Wybieranie typu źródła danych kodu kreskowego](./media/er-barcode-data-source-add.png)

3. W oknie dialogowym rozwijanym w polu **Nazwa** wprowadź **kod kreskowy**.
4. W **Format kodu kreskowego** wybierz **Kod 128**.
5. W polu **Szerokość** wpisz wartość **500**.
6. Kliknij przycisk **OK**.

    ![Okno dialogowe Właściwości źródła danych](./media/er-barcode-data-source-add2.png)

#### <a name="bind-a-new-format-element"></a><a name="ExampleModifyFormatBindFormatElement"></a>Powiąż nowy element formatu

Następnie należy powiązać nowy element formatu ze źródłem danych, które zostało właśnie dodane.

1. W projektancie operacji modułu ER na karcie **Mapowanie** po prawej stronie strony wybierz źródło danych **drukuj\\kod kreskowy**.
2. W okienku drzewa formatu po lewej stronie wybierz element komórki **AmountBarcode**, a następnie wybierz opcję **Powiąż**.
3. W okienku akcji wybierz pozycję **Pokaż szczegóły**.
4. Zwróć uwagę, że ponieważ źródło danych **Kod kreskowy** jest reprezentowane w powiązaniu jako funkcja zawierająca jeden parametr, nazwa elementu formatu powiązanego jest automatycznie traktowana jako argument tego parametru.

    ![Szczegóły źródła danych kodu kreskowego w projektancie operacji ER](./media/er-barcode-data-source-bind1.png)

5. Wybierz opcję **Edytuj formułę**, aby dostosować powiązanie.

    Nie chcesz, aby była zwracana nazwa elementu komórki. Dlatego należy skonfigurować Wyrażenie zwracające tekst zawierający kwotę zobowiązania z bieżącego czeku. Ponieważ nadrzędny zakres **ChequeLines** jest powiązany ze źródłem danych **model.cheques**, kwota zobowiązania bieżącego czeku jest dostępna w polu **model.cheques.attributes.amount** źródła danych **Rzeczywisty**.

6. W polu **Formuła** wprowadź wartość **print.barcode(NUMBERFORMAT(@.attributes.amount, "F2"))**.
7. Wybierz **Zapisz** i następnie zamknij [projektanta formuł ER](general-electronic-reporting-formula-designer.md).
8. Zauważ, że powiązanie zostało skorygowane.

    ![Skorygowane powiązanie w projektancie operacji ER](./media/er-barcode-data-source-bind2.png)

9. Wybierz **Zapisz** i następnie zamknij projektanta operacji ER.

#### <a name="make-the-modified-version-available-for-test-runs"></a><a name="ExampleModifyFormatMakeVersionAvailable"></a>Udostępnij zmodyfikowaną wersję do testów

Domyślnie jedynie wersje, które mają stan **Zakończono** i **Udostępniono**, są używane w przypadku uruchamiania formatu ER.

W przypadku sfinalizowania zmian można dokończyć pracę z bieżącą wersją roboczą i wprowadzić zmiany do użycia. Aby uzyskać instrukcje, zajrzyj do następującej sekcji [Wypełnij zmodyfikowaną wersję formatu](#CompleteToRun).

Jeśli chcesz kontynuować pracę z bieżącą wersją roboczą, ale musisz użyć jej do generowania czeków, musisz jawnie określić, że chcesz użyć wersji roboczej formatu do wykonania. Aby uzyskać instrukcje, zajrzyj do sekcji [Utwórz wersję roboczą, która będzie dostępna do użytku](#MarkToRun).

##### <a name="complete-the-modified-format-version"></a><a name="CompleteToRun"></a>Wypełnij zmodyfikowaną wersję formatu

1. Wybierz kolejno opcje **Administrowanie organizacją** \> **Obszary robocze** \> **Raportowanie elektroniczne**.
2. WNa stronie **Konfiguracje lokalizacji** w sekcji **Konfiguracje** wybierz **Konfigracje raportowanias**.
3. Na stronie **Konfiguracje** w drzewie konfiguracji rozwiń węzeł **Model czeków**, a następnie wybierz opcję **Format drukowania czeków**.
4. Na skróconej karcie **wersje** szybkie wybierz rekord o stanie **Wersja robocza**.
5. Wybierz pozycję **Zmień stan**, a następnie wybierz opcję **Zakończono**.
6. W oknie dialogowym kliknij **OK**.

Stan bieżącej wersji zostanie zmieniony z **Wersji roboczej** na **Zakończono** i zostanie utworzona nowa wersja o stanie **Wersja robocza**. Możesz użyć nowej wersji roboczej, aby zastosować dodatkowe zmiany.

##### <a name="make-the-draft-version-available-for-use"></a><a name="MarkToRun"></a>Udostępnij wersję roboczą do użytku

1. Wybierz kolejno opcje **Administrowanie organizacją** \> **Obszary robocze** \> **Raportowanie elektroniczne**.
2. WNa stronie **Konfiguracje lokalizacji** w sekcji **Konfiguracje** wybierz **Konfigracje raportowanias**.
3. Na stronie **Konfiguracje** w okienku akcji na karcie **Konfiguracje** w grupie **Ustawienia zaawansowane** wybierz opcję **Parametry użytkownika**.
4. W oknie dialogowym określ opcję **Ustawienia uruchamiania** na **Tak**, a następnie wybierz **OK**.
5. W drzewie konfiguracji rozwiń węzeł **Model czeków**, a następnie wybierz opcję **Format drukowania czeków**.
6. Ustaw wartość **Wersja robocza uruchomienia** opcji **Uruchomić**.
7. Wybierz opcję **Zapisz**.

Wersja robocza wybranego formatu jest oznaczona jako dostępna do użycia w przypadku uruchomienia wybranego formatu.

### <a name="generate-a-payment-check"></a><a name="ExampleGenerateCheque2"></a>Generowanie sprawdzania płatności

1. Kliknij kolejno opcje **Zarządzanie gotówką i bankami** \> **Konta bankowe** \> **Konta bankowe**.
2. Na stronie **Konta bankowe** wybierz konto **USMF OPER**.
3. Na stronie szczegółów konta bankowego w okienku akcji na karcie **Konfiguracja**, w grupie **Układ** wybierz opcję **Czek**.
4. Na stronie **Układ czeku**, w okienku akcji, wybierz opcję **Drukowanie testu**.
5. W oknie dialogowym określ opcję **Format czeków zbywalnych** na **Tak**.
6. Kliknij przycisk **OK**.
7. Przejrzyj wygenerowany czek. Należy zauważyć, że kod kreskowy został wygenerowany w celu zakodowania kwoty płatności czeku.

    ![Wygenerowane sprawdzenie płatności z kodem kreskowym w programie Excel](./media/er-barcode-data-source-cheque3.png)

> [!IMPORTANT]
> Wyjątek jest generowany, jeśli argument źródła danych **Kod kreskowy** nie jest zgodny z odpowiednimi wymaganiami określonymi dla formatu kodu kreskowego. Jeśli na przykład zostanie wywołane źródło danych **Kod kreskowy** w celu wygenerowania kodu kreskowego [EAN-8](https://wikipedia.org/wiki/EAN-8) dla dostarczonego tekstu, zostanie zgłoszony wyjątek, jeśli długość tekstu przekracza siedem znaków.

### <a name="convert-the-generated-check-to-a-pdf"></a><a name="ExampleConvertToPDF"></a>Przekonwertuj wygenerowane wyniki kontroli na plik PDF

Zgodnie z opisem w temacie [Generowanie drukowalnych formularzy FTI](er-generate-printable-fti-forms.md#finland) z możliwością drukowania można wykorzystać specjalną czcionkę do tworzenia kodów kreskowych w generowanym dokumencie. W takim przypadku dodatkowe przekształcenia wygenerowanego dokumentu mogą zależeć od dostępności tej czcionki w środowisku transformacji. Jeśli na przykład użytkownik spróbuje przekonwertować dokument na format PDF lub wyświetlić go w środowisku, w którym brakuje czcionki, kody kreskowe nie będą renderowane poprawnie.

Jeśli jednak do tworzenia kodów kreskowych jest używane źródło danych **Kod kreskowy**, renderowanie tych kodów kreskowych nie zależy od żadnej czcionki. Dzięki temu można łatwo przekonwertować dokumenty zawierające kody kreskowe na format PDF. Na poniższej ilustracji przedstawiono Podgląd wygenerowanego czeku płatności, który został [przekonwertowany](electronic-reporting-destinations.md#OutputConversionToPDF) na format PDF, na podstawie ustawienia skonfigurowanego [miejsca docelowego](electronic-reporting-destinations.md) ER.

![Podgląd pliku PDF czeku płatniczego](./media/er-barcode-data-source-cheque4.png)

## <a name="limitations"></a>Ograniczenia

> [!NOTE]
> Generowane są pewne typy kodów kreskowych o stałym współczynniku proporcji. Takie zachowanie ma sens, jeśli włączono funkcję **Włącz korzystanie z biblioteki EPPlus w ramach raportowania elektronicznego** do pracy z dokumentami programu Excel w module ER. W takim przypadku obraz jest wprowadzany w symbolu zastępczym z zablokowanym współczynnikiem proporcji. W związku z tym, jeśli wymiary symbolu zastępczego w szablonie odpowiadają współczynnikowi wprowadzonemu obrazowi, rozmiar rzeczywistego obrazu w generowanym dokumencie może zostać zmieniony w celu zachowania wymaganego współczynnika proporcji. Aby zapobiec zmianie rozmiaru obrazu, należy zastosować symbol zastępczy o oczekiwanym współczynniku proporcji.

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Raportowanie elektroniczne — omówienie](general-electronic-reporting.md)
- [Aplikacje docelowe Raportowania elektronicznego](electronic-reporting-destinations.md)
- [Język formuł raportowania elektronicznego](er-formula-language.md)
- [Funkcja NUMBERFORMAT](er-functions-text-numberformat.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]