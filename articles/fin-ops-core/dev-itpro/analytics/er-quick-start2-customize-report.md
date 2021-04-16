---
title: Dostosowanie formatu ER w celu wygenerowania niestandardowego dokumentu elektronicznego
description: W tym temacie opisano sposób korygowania formatu modułu raportowanie elektronicznego (ER) dostarczonego przez Microsoft, aby wygenerować niestandardowy dokument elektroniczny.
author: NickSelin
ms.date: 06/22/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERParameters, ERDataModelDesigner, ERModelMappingTable, ERModelMappingDesigner, EROperationDesigner, ERVendorTable
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7355fbb3321a6b5707ab561e88aed2d22cc967cd
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5743660"
---
# <a name="adjust-an-er-format-to-generate-a-custom-electronic-document"></a>Dostosowanie formatu ER w celu wygenerowania niestandardowego dokumentu elektronicznego

[!include[banner](../includes/banner.md)]

W procedurach opisanych w tym temacie opisano, jak użytkownik o roli Administratora systemu lub konsultanta funkcjonalnego dla funkcji raportowania elektronicznego może wykonywać następujące zadania:

- Konfigurowanie parametrów modułu [Raportowanie elektroniczne (ER)](general-electronic-reporting.md).
- Importowanie konfiguracji systemu, które są dostarczane przez Microsoft i używane do generowania pliku płatności podczas przetwarzania [płatności dostawcy](../../../finance/cash-bank-management/tasks/vendor-payment-overview.md).
- Utwórz niestandardową wersję standardowej konfiguracji formatu modułu ER, która jest oferowana przez Microsoft.
- Zmodyfikuj konfigurację formatu niestandardowego, tak aby generowała pliki płatności spełniające wymagania określonego banku.
- Zastosuj zmiany wprowadzone w standardowej konfiguracji formatu modułu ER w konfiguracji niestandardowego formatu.

Wszystkie poniższe procedury można wykonać dla firmy **GBSI**. Nie są wymagane umiejętności kodowania.

- [Konfigurowanie struktury ER](#ConfigureFramework)

    - [Konfigurowanie parametrów modułu ER](#ConfigureParameters)
    - [Aktywowanie dostawcy konfiguracji ER](#ActivateProvider)

        - [Przejrzenie listy dostawców konfiguracji ER](#ReviewProvidersList)
        - [Dodawanie nowego dostawcy formatu ER](#ActivateProvider)
        - [Aktywowanie dostawcy konfiguracji ER](#ActivateAddedProvider)

- [Importowanie standardowej konfiguracji formatu ER](#ImportERSolution1)

    - [Importowanie standardowych konfiguracji ER](#ImportERFormat1)
    - [Przeglądanie zaimportowanych konfiguracji ER](#ReviewImportedERSolution)

- [Przygotowywanie płatności dostawcy na potrzeby przetwarzania](#PrepareVendorPayment)

    - [Dodawanie informacji bankowych dla konta dostawcy](#AddBankAccount)
    - [Podawanie płatności dostawcy](#EnterVendorPayment)

- [Przetwarzanie płatności dostawcy przy użyciu standardowego formatu ER](#ProcessVendorPayment1)

    - [Konfigurowanie elektronicznej metody płatności](#ConfigureMethodOfPayment1)
    - [Przetwarzanie płatności dostawcy](#ProcessPayment1)

- [Dostosowywanie standardowego formatu ER](#CustomizeProvidedFormat)

    - [Tworzenie niestandardowego formatu](#DeriveProvidedFormat)
    - [Edytowanie niestandardowego formatu](#ConfigureDerivedFormat)
    - [Oznaczanie formatu niestandardowego jako wykonywalnego](#MarkFormatRunnable)

- [Przetwarzanie płatności dostawcy przy użyciu niestandardowego formatu ER](#ProcessVendorPayment2)

    - [Konfigurowanie elektronicznej metody płatności](#ConfigureMethodOfPayment2)
    - [Przetwarzanie płatności dostawcy](#ProcessPayment2)

- [Importowanie nowych wersji standardowej konfiguracji formatu ER](#ImportERSolution2)

    - [Importowanie nowych wersji standardowej konfiguracji ER](#ImportERFormat2)
    - [Przeglądanie zaimportowanych konfiguracji formatu ER](#ReviewImportedERFormat)

- [Zaadaptowanie zmian z nowej wersji importowanego formatu w formacie niestandardowym](#AdoptNewBaseVersion)

    - [Zakończenie obecnej wersji roboczej formatu niestandardowego](#CompleteDerivedFormat)
    - [Zmiana formatu niestandardowego do nowej wersji bazowej](#RebaseDerivedFormat)
    - [Przetwarzanie płatności dostawcy przy użyciu zmienionego formatu ER](#ProcessPayment3)

- [Dodatkowe zasoby](#References)

## <a name="configure-the-er-framework"></a><a id="ConfigureFramework"></a>Konfigurowanie struktury ER

Użytkownik należący w roli konsultanta funkcjonalnego do raportowania elektronicznego musi skonfigurować minimalny zestaw parametrów ER, aby można było rozpocząć korzystanie z struktury ER w celu zaprojektowania niestandardowej wersji standardowego formatu ER.

### <a name="configure-er-parameters"></a><a id="ConfigureParameters"></a>Konfigurowanie parametrów modułu ER

1. Wybierz kolejno opcje **Administrowanie organizacją** \> **Obszary robocze** \> **Raportowanie elektroniczne**.
2. Na stronie **Konfiguracje lokalizacji** w sekcji **Powiązane łącza** wybierz kafelek **Parametry raportowania elektronicznego**.
3. Na stronie **Parametry raportowania elektronicznego** na karcie **Ogólne** ustaw opcję **Włącz tryb projektowania** na **Tak**.
4. Na karcie **Załączniki** ustaw następujące parametry:

    - W polu **Konfiguracje** wybierz typ **Plik** dla firmy **USMF**.
    - W polach **Archiwum zadań**, **Tymczasowe**, **Podstawowe** i **Inne** należy wybrać typ **Plik**.

Aby uzyskać więcej informacji o parametrach modułu ER, zapoznaj się z tematem [Konfiguracja struktury ER](electronic-reporting-er-configure-parameters.md).

### <a name="activate-an-er-configuration-provider"></a><a id="ActivateProvider"></a>Aktywowanie dostawcy konfiguracji ER

Każda dodana konfiguracja ER jest oznaczona jako posiadana przez dostawcę konfiguracji ER. W tym celu jest używany dostawca konfiguracji ER, który został aktywowany w obszarze roboczym **Raportowanie elektroniczne**. Dlatego przed rozpoczęciem dodawania lub edytowania konfiguracji ER należy aktywować dostawcę konfiguracji ER w obszarze roboczym **Raportowanie elektroniczne**.

> [!NOTE]
> Tylko właściciel konfiguracji ER może ją edytować. Dlatego przed rozpoczęciem edytowania konfiguracji ER należy aktywować samą konfigurację w obszarze roboczym **Raportowanie elektroniczne**.

#### <a name="review-the-list-of-er-configuration-providers"></a><a id="ReviewProvidersList"></a>Przejrzenie listy dostawców konfiguracji ER

1. Wybierz kolejno opcje **Administrowanie organizacją** \> **Obszary robocze** \> **Raportowanie elektroniczne**.
2. Na stronie **Konfiguracje lokalizacji** w sekcji **Powiązane łącza** wybierz kafelek **Dostawcy konfiguracji**.
3. Na stronie **Tabela dostawcy konfiguracji** każdy rekord dostawcy ma unikatową nazwę i adres URL. Przejrzyj zawartość tej strony. Jeśli rekord dla **Litware, Inc.** (`https://www.litware.com`) już istnieje, pomiń następną procedurę, [Dodawanie nowego dostawcy konfiguracji ER](#ActivateProvider).

#### <a name="add-a-new-er-configuration-provider"></a><a id="ActivateProvider"></a>Dodawanie nowego dostawcy formatu ER

1. Wybierz kolejno opcje **Administrowanie organizacją** \> **Obszary robocze** \> **Raportowanie elektroniczne**.
2. Na stronie **Konfiguracje lokalizacji** w sekcji **Powiązane łącza** wybierz kafelek **Dostawcy konfiguracji**.
3. Na stronie **Dostawcy konfiguracji** wybierz opcję **Nowa**.
4. W polu **Nazwa** wpisz **Litware, Inc.**
5. W polu **Adres internetowy** wprowadź `https://www.litware.com`.
6. Wybierz opcję **Zapisz**.

#### <a name="activate-an-er-configuration-provider"></a><a id="ActivateAddedProvider"></a>Aktywowanie dostawcy konfiguracji ER

1. Wybierz kolejno opcje **Administrowanie organizacją** \> **Obszary robocze** \> **Raportowanie elektroniczne**.
2. Na stronie **Konfiguracje lokalizacji** w sekcji **Dostawcy konfiguracji** wybierz pozycję **Litware, Inc.**, a następnie wybierz pozycję **Ustaw, jako aktywne**.

Dalsze informacje o dostawcach konfiguracji ER znajdują się w temacie [Tworzenie dostawców konfiguracji i oznaczanie ich jako aktywnych](tasks/er-configuration-provider-mark-it-active-2016-11.md).

## <a name="import-the-standard-er-format-configurations"></a><a id="ImportERSolution1"></a>Importowanie standardowej konfiguracji formatu ER

### <a name="import-the-standard-er-configurations"></a><a id="ImportERFormat1"></a>Importowanie standardowych konfiguracji ER

Aby dodać standardowe konfiguracje obiektu ER do bieżącego wystąpienia rozwiązania Microsoft Dynamics 365 Finance, należy zaimportować je z [repozytorium](general-electronic-reporting.md#Repository) ER, które zostało skonfigurowane dla tego wystąpienia.

1. Wybierz kolejno opcje **Administrowanie organizacją** \> **Obszary robocze** \> **Raportowanie elektroniczne**.
2. Na stronie **Konfiguracje lokalizacji** w sekcji **Dostawcy konfiguracji** wybierz kafelek **Microsoft**, a następnie wybierz pozycję **Repozytoria**, aby wyświetlić listę repozytoriów dla dostawcy rozwiązania: Microsoft.
3. Na stronie **Repozytoria konfiguracji** zaznacz repozytorium typu **Globalne**, a następnie kliknij przycisk **Otwórz**. Jeśli zostanie wyświetlony monit o autoryzację połączenia z usługą Regulatory Configuration Service, postępuj zgodnie z instrukcjami autoryzacji.
4. Na stronie **Repozytorium konfiguracji** w drzewie konfiguracje w panelu po lewej wybierz format konfiguracji **BACS (brytyjski)**.
5. Na skróconej karcie **Wersje** wybierz wersję **1.1** wybranej konfiguracji formatu ER.
6. Wybierz **Importuj**, aby pobrać wybraną wersję z Globalnego repozytorium do bieżącego wystąpienia Finance.

![Strona Repozytorium konfiguracji](./media/er-quick-start2-import-solution1.png)

> [!TIP]
> Jeśli masz problemy z dostępem do [repozytorium globalnego](er-download-configurations-global-repo.md), zamiast tego możesz [pobrać konfiguracje](download-electronic-reporting-configuration-lcs.md) z Microsoft Dynamics Lifecycle Services (LCS).

### <a name="review-the-imported-er-configurations"></a><a id="ReviewImportedERSolution"></a>Przeglądanie zaimportowanych konfiguracji ER

1. Wybierz kolejno opcje **Administrowanie organizacją** \> **Obszary robocze** \> **Raportowanie elektroniczne**.
2. WNa stronie **Konfiguracje lokalizacji** w sekcji **Konfiguracje** wybierz kafelek **Konfigracje raportowanias**.
3. Na stronie **Konfiguracje** w drzewie konfiguracji w panelu po lewej wybierz pozycję **Model płatności**.
4. Należy zauważyć, że oprócz wybranego formatu ER **BACS (brytyjski)** zostały zaimportowane inne wymagane konfiguracje obiektów konfiguracji. Upewnij się, że w drzewie konfiguracji są dostępne następujące konfiguracje modułu ER:

    - **Model płatności** – Ta konfiguracja zawiera składnik ER [modelu danych](general-electronic-reporting.md#data-model-and-model-mapping-components), który reprezentuje strukturę danych domeny biznesowej płatności.
    - **Mapowanie modelu płatności 1611** – Ta konfiguracja zawiera [składnik mapowanie modelu](general-electronic-reporting.md#data-model-and-model-mapping-components), który opisuje sposób wypełniania modelu danych przy użyciu danych aplikacji w czasie wykonywania.
    - **BACS (brytyjski)** – Ta konfiguracja zawiera [format](general-electronic-reporting.md#FormatComponentOutbound) i mapowanie formatów składników ER. Składnik formatu określa układ raportu. Składnik mapowanie formatu zawiera źródło danych modelu i określa sposób wypełniania układu raportu przy użyciu tego źródła danych w czasie wykonywania.

![Strona Konfiguracje](./media/er-quick-start2-imported-solution1.png)

## <a name="prepare-a-vendor-payment-for-processing"></a><a id="PrepareVendorPayment"></a>Przygotowywanie płatności dostawcy na potrzeby przetwarzania

### <a name="add-bank-information-for-a-vendor-account"></a><a id="AddBankAccount"></a>Dodawanie informacji bankowych dla konta dostawcy

Należy dodać informacje dotyczące banku dla konta dostawcy, które będzie odwoływać się później w zarejestrowanej płatności.

1. Przejdź do pozycji **Rozrachunki z dostawcami** \> **Dostawcy** \> **Wszyscy dostawcy**.
2. Na stronie **Wszyscy dostawcy** wybierz konto dostawcy **GB_SI_000001**, a następnie w okienku akcji na karcie **Dostawca** w formularzu **Konfiguracja** wybierz pozycję **Konta bankowe**.
3. Na stronie **Konta bankowe dostawcy** wybierz opcję **Nowe**, a następnie wprowadź następujące informacje:

    1. W polu **Konto bankowe** wpisz **GBP OPER**.
    2. W polu **Grupy bankowe** wybierz opcję **BankGBP**.
    3. W polu **Numer konta bankowego** wpisz **202015**.
    4. W polu **Kod SWIFT** wprowadź <a id="DefineSWIFTCode"></a>**CHASDEFXXXX**.
    5. W polu **IBAN** wprowadź **GB33BUKB20201555555555**.
    6. W polu **Numer RBN** zachowaj wartość domyślną <a id="DefineRoutingNumber"></a>**123456**.

    ![Strona konta bankowe dostawcy](./media/er-quick-start2-bank-account.png)

4. Wybierz opcję **Zapisz**.
5. Zamknij stronę.
6. Na stronie **Wszyscy dostawcy** otwórz konto dostawcy **GB_SI_000001**.
7. Na stronie Szczegóły dostawcy wybierz opcję **Edytuj**, aby umożliwić edytowanie strony w razie potrzeby.
8. Na skróconej karcie **Opłaty** w polu **Konto bankowe** wybierz opcję **GBP OPER**.

    ![Strona szczegółów dot. dostawcy](./media/er-quick-start2-bank-account-reference.png)

9. Wybierz opcję **Zapisz**.
10. Zamknij stronę.

### <a name="enter-a-vendor-payment"></a><a id="EnterVendorPayment"></a>Podawanie płatności dostawcy

Należy utworzyć nową płatność dostawcy za pomocą [propozycji płatności](https://docs.microsoft.com/dynamics365/finance/accounts-payable/create-vendor-payments-payment-proposal).

1. Przejdź do pozycji **Rozrachunki z dostawcami** \> **Płatności** \> **Arkusz płatności dostawcy**.
2. Na stronie **Arkusz płatności dostawców** wybierz opcję **Nowa**.
3. W polu **Nazwa** wybierz **VendPay**.
4. Wybierz **Linie**.
5. Wybierz **Propozycja płatności** \> **Utwórz propozycję płatności**.
6. W oknie dialogowym **Propozycja płatności dostawcy** skonfiguruj warunki filtrowania rekordów tylko dla konta dostawcy **GB_SI_000001**, a następnie kliknij przycisk **OK**.
7. Wybierz wiersz faktury **00000007_Inv**, a następnie wybierz opcję **Utwórz płatność**.

    ![Okno dialogowe – propozycje płatności dostawcy](./media/er-quick-start2-payment-proposal.png)

8. Sprawdź, czy wprowadzona płatność jest skonfigurowana do używania **Elektronicznej** metody płatności.

    ![Strona Płatności dla dostawców](./media/er-quick-start2-payment-line.png)

## <a name="process-a-vendor-payment-by-using-the-standard-er-format"></a><a id="ProcessVendorPayment1"></a>Przetwarzanie płatności dostawcy przy użyciu standardowego formatu ER

### <a name="set-up-the-electronic-payment-method"></a><a id="ConfigureMethodOfPayment1"></a>Konfigurowanie elektronicznej metody płatności

Należy skonfigurować elektroniczną metodę płatności, aby korzystała z importowanej konfiguracji formatu ER.

1. Przejdź do pozycji **Rozrachunki z dostawcami** \> **Ustawienia płatności** \> **Metody płatności**.
2. Na stronie **Metody płatności – dostawcy** wybierz **Elektroniczną** metodę płatności w lewym okienku.
3. Wybierz opcję **Edycja**.
4. W karcie **Formaty plików** ustaw **Ogólny elektroniczny format eksportu** jako **Tak**.
5. W polu **Konfiguracja formatu eksportu** wybierz format konfiguracji **BACS (brytyjski)**.

    ![Metody płatności – strona dostawcy](./media/er-quick-start2-method-of-payment1.png)

6. Wybierz opcję **Zapisz**.

### <a name="process-a-vendor-payment"></a><a id="ProcessPayment1"></a>Przetwarzanie płatności dostawcy

1. Przejdź do pozycji **Rozrachunki z dostawcami** \> **Płatności** \> **Arkusz płatności dostawcy**.
2. Na stronie **Arkusz płatności dostawców** wybierz utworzony wcześniej arkusz płatności dodany wcześniej, a następnie wybierz pozycję **Wiersze**.
3. Na stronie **Płatności dostawcy** wybierz pozycję **Generuj płatności**.
4. W oknie dialogowym **Generuj płatności** wprowadź następujące informacje:

    - W polu **Metoda płatności** wybierz pozycję **Elektroniczna**.
    - W polu **Konto bankowe** wybierz pozycję **GBSI OPER**.

5. Kliknij przycisk **OK**.
6. W oknie dialogowym **Parametry raportu elektronicznego**, w polu **Drukuj raport kontroli** wybierz **Tak**, a następnie kliknij przycisk **OK**.

    ![Strona dialogowa Parametry raportu elektronicznego](./media/er-quick-start2-payment-dialog1.png)

    > [!NOTE]
    > Oprócz pliku płatności można teraz wygenerować raport kontroli.

7. Pobierz plik zip, a następnie wyodrębnij z niego następujące pliki:

    - Raport kontrolny w formacie programu Excel
    - Plik płatności w formacie TXT

        Należy zauważyć, że zgodnie ze [strukturą](#PositionRoutingNumber) dostarczonego formatu modułu ER, wiersz płatności w wygenerowanym pliku rozpoczyna się od numeru kodu banku [zdefiniowanego](#DefineRoutingNumber) dla konfigurowanego konta bankowego.

        ![Plik płatności w formacie TXT](./media/er-quick-start2-payment-file1.png)

## <a name="customize-the-standard-er-format"></a><a id="CustomizeProvidedFormat"></a>Dostosowywanie standardowego formatu ER

W przykładzie pokazanym w tej sekcji zachodzi potrzeba użycia konfiguracji ER dostarczonej przez Microsoft w celu wygenerowania plików płatności dostawców w formacie BACS, ale konieczne jest także dodanie dostosowania w celu obsługi wymagań określonego banku. Można również uaktualnić format niestandardowy, gdy będą dostępne nowe wersje konfiguracji systemu ER. Jednak użytkownik chce mieć możliwość dokonania uaktualnienia przy najniższym koszcie.

W tym przypadku, jako przedstawiciel Litware, Inc., należy utworzyć (uzyskać) nową konfigurację formatu ER, używając **BACS (brytyjski)** konfiguracji dostarczonej przez Microsoft jako podstawy.

### <a name="create-a-custom-format"></a><a id="DeriveProvidedFormat"></a>Tworzenie niestandardowego formatu

1. Otwórz **Administracja organizacji** \> **Elektroniczne raportowanie** \> **Konfiguracje**.
2. Na stronie **Konfiguracje** w drzewie konfiguracji w panelu po lewej wybierz pozycję **Model płatności**, a potem wybierz **BACS (brytyjski)**. Litware, Inc. będzie używał wersji 1.1 tej konfiguracji formatu ER jako podstawy dla wersji niestandardowej.
3. Wybierz przycisk **Utwórz konfigurację**, aby otworzyć rozwijane okno dialogowe. Nowe okno dialogowe pozwoli utworzyć nową konfigurację dla niestandardowego formatu płatności.
4. W **Nowej** grupie pól, wybierz opcję **Pochodna od nazwy: BACS (brytyjski), Microsoft**.
5. W polu **Nazwa** wpisz **BACS (niestandardowy brytyjski)**.

    ![Utwórz okno dialogowe tworzenia konfiguracji](./media/er-quick-start2-add-derived-format.png)

6. Wybierz **Utwórz konfigurację**.

Utworzono konfigurację tematu ER **BACS (niestandardowy brytyjski)** w wersji 1.1.1. Ta wersja ma [stan](general-electronic-reporting.md#component-versioning) **Wersji roboczej** i można ją edytować. Bieżąca zawartość niestandardowego formatu ER jest zgodna z zawartością formatu dostarczonego przez Microsoft.

![Strona Konfiguracje](./media/er-quick-start2-derived-format-configuration1.png)

### <a name="edit-a-custom-format"></a><a id="ConfigureDerivedFormat"></a>Edytowanie niestandardowego formatu

Musisz skonfigurować format niestandardowy, aby spełniał wymagania specyficzne dla banku. Na przykład bank może wymagać, aby generowane pliki płatności obejmowały kod SWIFT banku, do którego przypisano rolę agenta w przetwarzanej płatności dostawcy. Kody SWIFT są międzynarodowymi kodami, które identyfikują poszczególne banki na całym świecie. Są one znane także jako kody identyfikacyjne banku (BICs). Kod SWIFT musi składać się z 11 znaków i musi być wprowadzony na początku każdego wiersza płatności w wygenerowanym pliku płatności.

1. Otwórz **Administracja organizacji** \> **Elektroniczne raportowanie** \> **Konfiguracje**.
2. Na stronie **Konfiguracje** w drzewie konfiguracji w panelu po lewej wybierz pozycję **Model płatności**, a potem wybierz **BACS (niestandardowy brytyjski)**.
3. Na skróconej karcie **Wersje** wybierz wersję **1.1.1** wybranej konfiguracji.
4. Wybierz opcję **Konstruktor**.
5. Na stronie **Projektant formatów** wybierz opcję **Pokaż szczegóły**, aby wyświetlić więcej informacji o elementach formatu.
6. Rozwiń i przejrzyj następujące elementy:

    - Element **Element BACSReportsFolder** typu **Folder**. Ten element jest używany do generowania danych wyjściowych w formacie ZIP.
    - Element **plik** typu **Plik**. Ten element jest używany do generowania pliku płatności w formacie TXT.
    - Element **transakcje** typu **Sekwencja**. Ten element jest używany do generowania pojedynczego wiersza płatności w pliku płatności.
    - Element **transakcja** typu **Sekwencja**. Ten element jest używany do generowania pojedynczych pól w jednym wierszu płatności.

7. Umożliwia wybranie elementu **transakcja**.

    ![Element transakcji w projektancie operacji ER](./media/er-quick-start2-derived-format0.png)

    > [!NOTE]
    > Podany raport jest skonfigurowany w taki sposób, aby <a id="PositionRoutingNumber"></a>każdy wiersz płatności zaczynał się od numeru rozliczeniowego banku. Element formatu **vendBankRouteNum** jest do tego używany. 

8. Wybierz opcję **Dodaj**, a następnie wybierz typ **Tekst\\Ciąg** dodawanego elementu formatu:

    1. W polu **Nazwa** wpisz **vendBankSWIFT**.
    2. W polu **Długość minimalna** wpisz **11**.
    3. W polu **Długość maksymalna** wpisz **11**.
    4. Kliknij przycisk **OK**.

    > [!NOTE]
    > Element **vendBankSWIFT** zostanie użyty do wprowadzenia kodu SWIFT banku dostawcy w wygenerowanych plikach.

9. W drzewie struktury formatu wybierz **vendBankSWIFT**.
10. Wybierz przycisk **Przenieś w górę**, aby przenieść wybrany element formatu o jeden poziom w górę. Powtarzaj ten krok do momentu, aż element **vendBankSWIFT** będzie <a id="PositionSWIFTCode"></a>pierwszym elementem w nadrzędnym elemencie **transakcji**.

    ![VendBankSWIFT jako pierwszy element w obszarze transakcja w projektancie operacji ER](./media/er-quick-start2-derived-format1.png)

11. Gdy **vendBankSWIFT** jest wciąż zaznaczone w drzewie struktury formatu, wybierz kartę **Mapowanie**, a następnie rozwiń źródło danych **Model**.
12. Rozwiń **model.Payment** \> **model.Payment.CreditorAgent** oraz wybierz pole źródła danych **model.Payment.CreditorAgent.BICFI**. To pole źródła danych opisuje kod SWIFT banku dostawcy, któremu przypisano rolę agenta w przetwarzanej płatności dostawcy.
13. Wybierz **Powiąż**. Element formatu **vendBankSWIFT** jest powiązany ze źródłem danych **model.Payment.CreditorAgent.BICFI** data source field, dzięki czemu kody SWIFT zostaną wprowadzone w plikach wygenerowanych płatności.

    ![Element formatu vendBankSWIFT powiązany z polem źródła danych model.Payment.CreditorAgent.BICFI. w projektancie operacji ER](./media/er-quick-start2-derived-format2.png)

14. Wybierz opcję **Zapisz**.
15. Zamknij stronę projektowania.

### <a name="mark-a-custom-format-as-runnable"></a><a id="MarkFormatRunnable"></a>Oznaczanie formatu niestandardowego jako wykonywalnego

Teraz, gdy została utworzona pierwsza wersja formatu niestandardowego i ma ona stan **Wersja robocza**, można ją uruchomić w celach testowych. Aby uruchomić raport, należy przetworzyć płatność dostawcy, używając metody płatności, która odwołuje się do niestandardowego formatu encji (ER). Domyślnie, podczas wywoływania formatu ER w aplikacji, jedynie wersje, które mają stan **Zakończono** lub **Udostępniono**, są [używane](general-electronic-reporting.md#component-versioning). To zachowanie pomaga zapobiegać używaniu formatów ER, w których znajdują się nieukończone projekty. Jednak w przypadku uruchamiania testów można wymusić na aplikacji używanie wersji formatu ER, która ma stan **Wersja robocza**. W ten sposób można dostosować bieżącą wersję formatu, jeśli są wymagane jakiekolwiek modyfikacje. Aby uzyskać więcej informacji, zobacz [Zastosowanie](electronic-reporting-destinations.md#applicability).

Aby można było skorzystać z wersji roboczej formatu ER, należy odpowiednio go oznaczyć.

1. Otwórz **Administracja organizacji** \> **Elektroniczne raportowanie** \> **Konfiguracje**.
2. Na stronie **Konfiguracje** w okienku akcji na karcie **Konfiguracje** w grupie **Ustawienia zaawansowane** wybierz opcję **Parametry użytkownika**.
3. W oknie dialogowym **Parametry użytkownika** określ opcję **Ustawienia uruchamiania** na **Tak**, a następnie wybierz **OK**.
4. W razie potrzeby wybierz opcję **Edytuj**, aby bieżąca strona była możliwa do edycji.
5. W drzewie konfiguracji w lewym okienku wybierz **BACS (niestandardowy brytyjski)**.
6. Ustaw wartość **Uruchom wersję roboczą** na wartość **Tak**.

    ![Uruchom Wersję roboczą na stronie konfiguracje](./media/er-quick-start2-derived-format-configuration2.png)

## <a name="process-a-vendor-payment-by-using-the-custom-er-format"></a><a id="ProcessVendorPayment2"></a>Przetwarzanie płatności dostawcy przy użyciu niestandardowego formatu ER

### <a name="set-up-the-electronic-payment-method"></a><a id="ConfigureMethodOfPayment2"></a>Konfigurowanie elektronicznej metody płatności

Należy skonfigurować elektroniczną metodę płatności, aby do przetwarzania płatności dostawców był używany niestandardowy format ER.

1. Przejdź do pozycji **Rozrachunki z dostawcami** \> **Ustawienia płatności** \> **Metody płatności**.
2. Na stronie **Metody płatności – dostawcy** wybierz **Elektroniczną** metodę płatności w lewym okienku.
3. Wybierz opcję **Edycja**.
4. W karcie **Format plików** ustaw **Ogólny elektroniczny format eksportu** jako **Tak**.
5. W polu **Konfiguracja formatu eksportu** wybierz format konfiguracji **BACS (niestandardowy brytyjski)**.

    ![Metody płatności – strona dostawcy](./media/er-quick-start2-method-of-payment2.png)

6. Wybierz opcję **Zapisz**.

### <a name="process-a-vendor-payment"></a><a id="ProcessPayment2"></a>Przetwarzanie płatności dostawcy

1. Przejdź do pozycji **Rozrachunki z dostawcami** \> **Płatności** \> **Arkusz płatności dostawcy**.
2. Na stronie **Arkusz płatności dostawców** wybierz utworzony wcześniej arkusz płatności dodany wcześnie.
3. Wybierz **Linie**.
4. Na **Płatności dostawców**, powyżej siatki, wybierz **Stan płatności** \> **Brak**.
5. Wybierz **Generuj płatność**.
6. W oknie dialogowym **Generuj płatności** wprowadź następujące informacje:

    - W polu **Metoda płatności** wybierz pozycję **Elektroniczna**.
    - W polu **Konto bankowe** wybierz pozycję **GBSI OPER**.

7. Kliknij przycisk **OK**.
8. W oknie dialogowym **Parametry raportu elektronicznego**, w polu **Drukuj raport kontroli** wybierz **Tak**, a następnie kliknij przycisk **OK**.

    > [!NOTE]
    > Oprócz pliku płatności można teraz wygenerować tylko raport kontroli.

9. Pobierz plik zip, a następnie wyodrębnij z niego następujące pliki:

    - Raport kontrolny w formacie programu Excel
    - Plik płatności w formacie TXT

        Należy zauważyć, że zgodnie ze strukturą niestandardowego formatu ER, wiersz płatności w wygenerowanym pliku [rozpoczyna się](#PositionSWIFTCode) od kodu SWIFT, który został [wprowadzony](#DefineSWIFTCode) dla konta bankowego dostawcy, którego płatność została przetworzona.

        ![Plik płatności w formacie TXT](./media/er-quick-start2-payment-file2.png)

## <a name="import-new-versions-of-the-standard-er-format-configurations"></a><a id="ImportERSolution2"></a>Importowanie nowych wersji standardowej konfiguracji formatu ER

W przykładzie pokazanym w tej sekcji zostanie wyświetlone powiadomienie dotyczące artykułu bazy wiedzy [KB3763330](https://fix.lcs.dynamics.com/Issue/Details?kb=3182046). To powiadomienie informuje o nowej wersji formatu ER **BACS (brytyjski)** opublikowanego przez Microsoft. Oprócz raportu kontrolnego, nowa wersja umożliwia użytkownikom generowanie raportu zawiadomienia o płatności oraz raportu notatki towarzyszącej podczas przetwarzania płatności dostawcy. Chcesz rozpocząć korzystanie z tej funkcji.

### <a name="import-new-versions-of-the-standard-er-configurations"></a><a id="ImportERFormat2"></a>Importowanie nowych wersji standardowej konfiguracji ER

Aby dodać nowe wersje konfiguracji ER do bieżącego wystąpienia Finance, należy zaimportować je z [repozytorium](general-electronic-reporting.md#Repository) ER, które zostało skonfigurowane dla tego wystąpienia.

1. Wybierz kolejno opcje **Administrowanie organizacją** \> **Obszary robocze** \> **Raportowanie elektroniczne**.
2. Na stronie **Konfiguracje lokalizacji** w sekcji **Dostawcy konfiguracji** wybierz kafelek **Microsoft**, a następnie wybierz pozycję **Repozytoria**, aby wyświetlić listę repozytoriów dla dostawcy rozwiązania: Microsoft.
3. Na stronie **Repozytoria konfiguracji** zaznacz repozytorium typu **Globalne**, a następnie kliknij przycisk **Otwórz**. Jeśli zostanie wyświetlony monit o autoryzację połączenia z usługą Regulatory Configuration Service, postępuj zgodnie z instrukcjami autoryzacji.
4. Na stronie **Repozytorium konfiguracji** w drzewie konfiguracje w panelu po lewej wybierz format konfiguracji **BACS (brytyjski)**.
5. Na skróconej karcie **Wersje** wybierz wersję **3.3** wybranej konfiguracji formatu ER.
6. Wybierz **Importuj**, aby pobrać wybraną wersję z Globalnego repozytorium do bieżącego wystąpienia Finance.

![Strona Repozytorium konfiguracji](./media/er-quick-start2-import-solution2.png)

> [!TIP]
> Jeśli masz problemy z dostępem do [repozytorium globalnego](er-download-configurations-global-repo.md), zamiast tego możesz [pobrać konfiguracje z](download-electronic-reporting-configuration-lcs.md) LCS.

### <a name="review-the-imported-er-format-configurations"></a><a id="ReviewImportedERFormat"></a>Przeglądanie zaimportowanych konfiguracji formatu ER

1. Wybierz kolejno opcje **Administrowanie organizacją** \> **Obszary robocze** \> **Raportowanie elektroniczne**.
2. WNa stronie **Konfiguracje lokalizacji** w sekcji **Konfiguracje** wybierz kafelek **Konfigracje raportowanias**.
3. Na stronie **Konfiguracje** w drzewie konfiguracji w panelu po lewej wybierz pozycję **Model płatności**, a potem wybierz **BACS (brytyjski)**.
4. Na skróconej karcie **wersje** wybierz opcję wersja **3.3**.
5. Wybierz opcję **Konstruktor**.
6. Na stronie **Projektant formatów** rozwiń element formatu **BACSReportsFolder**.
7.  Zwróć uwagę, że wersja 3.3 element formatu **PaymentAdviceReport** używany do generowania raportu zawiadomienia o płatności podczas przetwarzania płatności dostawcy.

    ![Element formatu PaymentAdviceReport w projektancie operacji ER](./media/er-quick-start2-imported-solution2.png)

8. Zamknij stronę projektowania.

## <a name="adopt-the-changes-in-the-new-version-of-an-imported-format-in-a-custom-format"></a><a id="AdoptNewBaseVersion"></a>Zaadaptowanie zmian z nowej wersji importowanego formatu w formacie niestandardowym

### <a name="complete-the-current-draft-version-of-a-custom-format"></a><a id="CompleteDerivedFormat"></a>Zakończenie obecnej wersji roboczej formatu niestandardowego

Aby zachować bieżący stan formatu niestandardowego, należy uzupełnić wersję roboczą 1.1.1, zmieniając jej stan z **Wersja robocza** na **Zakończone**.

1. Wybierz kolejno opcje **Administrowanie organizacją** \> **Obszary robocze** \> **Raportowanie elektroniczne**.
2. WNa stronie **Konfiguracje lokalizacji** w sekcji **Konfiguracje** wybierz kafelek **Konfigracje raportowanias**.
3. Na stronie **Konfiguracje** w drzewie konfiguracji w panelu po lewej wybierz pozycję **Model płatności**, rozwiń **BACS (brytyjski)**, a potem wybierz **BACS (niestandardowy brytyjski)**.
4. Na skróconej karcie **Wersje** wybierz **Zmień stan** \> **Zakończ**, a następnie wybierz **OK**.

Stan wersji 1.1.1 został zmieniony z **Wersji roboczej** na **Zakończone**, a wersja jest tylko do odczytu. Dodano nową wersję do edycji, 1.1.2, która ma stan **Wersja robocza**. Możesz skorzystać z tej wersji, aby wprowadzić dalsze zmiany w niestandardowym formacie ER.

### <a name="rebase-a-custom-format-to-a-new-base-version"></a><a id="RebaseDerivedFormat"></a>Zmiana formatu niestandardowego do nowej wersji bazowej

Aby rozpocząć korzystanie z nowej funkcji w wersji 3.3 formatu **BACS (brytyjski)** w dostosowaniu, należy zmienić podstawową wersję konfiguracji dla konfiguracji niestandardowej **BACS (niestandardowy brytyjski)**. Ten proces jest nazywany [zmianą bazy](general-electronic-reporting.md#upgrading-a-format-selecting-a-new-version-of-base-format-rebase). Zamiast wersji 1.1 konfiguracji **BACS (brytyjski)** należy używać nowej wersji 3.3.

1. Otwórz **Administracja organizacji** \> **Elektroniczne raportowanie** \> **Konfiguracje**.
2. Na stronie **Konfiguracje** w drzewie konfiguracji w panelu po lewej wybierz pozycję **Model płatności**, a potem wybierz **BACS (niestandardowy brytyjski)**.
3. Na skróconej karcie **Wersje** wybierz wersję **1.1.2**, a następnie wybierz opcję **Zmień podstawę**.
4. W oknie **Zmień podstawę** w polu **Wersja docelowa** wybierz wersję **3.3** konfiguracji podstawowej, aby ją zastosować jako nową podstawę i użyć jej do zaktualizowania konfiguracji.

    ![Okno dialogowe zmiana podstawy](./media/er-quick-start2-rebase1.png)

5. Kliknij przycisk **OK**.
6. Zauważ, że numer wersji roboczej został zmieniony z **1.1.2** na **3.3.2**, aby odzwierciedlić zmianę w wersji bazowej.

    Po scaleniu wersji niestandardowej z nową wersją bazową mogą zostać wykryte konflikty. Konflikty te reprezentują niektóre zmiany formatu, których nie można scalić automatycznie.

    ![Zmiana podstawy konfiguracji z konfliktami na stronie konfiguracje](./media/er-quick-start2-rebase2.png)

    Jeśli zostaną wykryte konflikty, należy je rozwiązać ręcznie w projektancie formatów.

7. Na skróconej karcie **wersje** wybierz opcję wersja **3.3.2**.
8. Wybierz opcję **Konstruktor**.
9. Na stronie **Projektant formatów** na skróconej karcie **Szczegóły**, wybierz rekord powodujący konflikt, a następnie wybierz opcję **Zastosuj wartość podstawową**.

    ![Konflikt rekordów zmiany podstawy w projektancie operacji ER](./media/er-quick-start2-rebase3.png)

10. Wybierz opcję **Zapisz**.

    Konfliktu nie powinien już pojawiać się w skróconej karcie **Szczegóły**.

    ![Konflikt rozwiązany w projektancie operacji ER](./media/er-quick-start2-rebase4.png)

    > [!NOTE]
    > Konflikt został rozwiązany przez potwierdzenie, że w tym formacie ER musi być używana wersja 3 modelu podstawowego.

11. Rozwiń **BACSReportsFolder** \> **plik** \> **transakcje** \> **transakcja**.
12. Na karcie **Mapowanie** należy zauważyć, że wersja 3.3.2 niestandardowego formatu ER zawiera zarówno dostosowanie (element **vendBankSWIFT** i jego powiązanie), jak i nową funkcjonalność wersji 3.3 podstawowego formatu ER dostarczonego przez Microsoft (element **PaymentAdviceReport** wraz z zagnieżdżonymi elementami i skonfigurowanymi powiązaniami). Po kilku kliknięciach myszą zawarto modyfikacje nowej wersji bazowej, scalając je z dostosowaniem.

    ![Format scalony w projektancie operacji ER](./media/er-quick-start2-rebase5.png)

13. Zamknij stronę projektowania.

> [!NOTE]
> Akcja zmiany podstawy jest odwracalna. Aby anulować tę operację , należy wybrać wersję **1.1.1** w formacie **BACS (niestandardowy brytyjski)** na skróconej karcie **Wersje**, a następnie wybrać opcję **Pobierz tę wersję**. Następnie w wersji 3.3.2 zostanie ponownie numerowana na 1.1.2, a zawartość wersji roboczej 1.1.2 będzie zgodna z treścią wersji 1.1.1.

### <a name="process-a-vendor-payment-by-using-a-rebased-er-format"></a><a id="ProcessPayment3"></a>Przetwarzanie płatności dostawcy przy użyciu zmienionego formatu ER

1. Przejdź do pozycji **Rozrachunki z dostawcami** \> **Płatności** \> **Arkusz płatności dostawcy**.
2. Na stronie **Arkusz płatności dostawców** wybierz utworzony wcześniej arkusz płatności dodany wcześnie.
3. Wybierz **Linie**.
4. Na **Płatności dostawców**, powyżej siatki, wybierz **Stan płatności** \> **Brak**.
5. Wybierz **Generuj płatność**.
6. W oknie dialogowym **Generuj płatności** wprowadź następujące informacje:

    - W polu **Metoda płatności** wybierz pozycję **Elektroniczna**.
    - W polu **Konto bankowe** wybierz pozycję **GBSI OPER**.

7. Kliknij przycisk **OK**.
8. W oknie dialogowym **Parametry raportowania elektronicznego** wprowadź następujące informacje:

    - Ustaw opcję **Wydrukuj raport kontrolny** jako **tak**.
    - Ustaw opcję **Wydrukuj poradę odnośnie do płatności** na **Tak**.

    ![Okno dialogowe Parametry raportu elektronicznego](./media/er-quick-start2-payment-dialog2.png)

    > [!NOTE]
    > Oprócz pliku płatności można teraz wygenerować zarówno raport kontrolny, jak i raport zawiadomienia o płatności.

9. Kliknij przycisk **OK**.
10. Pobierz plik zip, a następnie wyodrębnij z niego następujące pliki:

    - Raport kontrolny w formacie programu Excel
    - Porada dot. płatności w formacie programu Excel

        ![Porada dot. płatności w formacie programu Excel](./media/er-quick-start2-payment-advice-report.png)

    - Plik płatności w formacie TXT

        Należy zauważyć, że wiersz płatności w wygenerowanym pliku rozpoczyna się od kodu SWIFT, który został wprowadzony dla konta bankowego dostawcy, którego płatność została przetworzona.

        ![Plik płatności w formacie TXT](./media/er-quick-start2-payment-file3.png)

## <a name="additional-resources"></a><a id="References"></a>Dodatkowe zasoby

- [Raportowanie elektroniczne — omówienie](general-electronic-reporting.md)
- [Pobieranie konfiguracji ER z usługi Lifecycle Services](download-electronic-reporting-configuration-lcs.md)
- [Pobieranie konfiguracji ER z globalnego repozytorium usługi Configuration service](er-download-configurations-global-repo.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]