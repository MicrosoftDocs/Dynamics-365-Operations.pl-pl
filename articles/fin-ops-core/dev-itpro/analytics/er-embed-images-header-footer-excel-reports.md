---
title: Zaprojektuj format ER, aby wygenerować raport w formacie Excel z osadzonymi obrazami w nagłówkach lub stopkach stron
description: W tym temacie wyjaśniono, jak używać raportowania elektronicznego (ER) do generowania dokumentów biznesowych zawierających obrazy i kształty osadzone w nagłówkach lub stopkach stron.
author: NickSelin
ms.date: 06/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EROperationDesigner, ERParameters
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2021-06-01
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: e67c10ecb9f297d1855a55431cd07c53ee87d40a
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/06/2021
ms.locfileid: "6361417"
---
# <a name="design-an-er-format-to-generate-a-report-in-excel-format-with-embedded-images-in-page-headers-or-footers"></a>Zaprojektuj format ER, aby wygenerować raport w formacie Excel z osadzonymi obrazami w nagłówkach lub stopkach stron

[!include[banner](../includes/banner.md)]

W tym temacie wyjaśniono, w jaki sposób użytkownik w roli administratora systemu lub konsultanta funkcjonalnego ds. raportowania elektronicznego może wykonywać następujące zadania:

- Konfigurowanie parametrów modułu [Raportowanie elektroniczne (ER)](general-electronic-reporting.md).
- Importuj [konfiguracje](general-electronic-reporting.md#Configuration) ER, które są [dostarczane](general-electronic-reporting.md#Provider) przez firmę Microsoft i używane do generowania  [faktur niezależnych](../../../finance/accounts-receivable/create-free-text-invoice-new.md), na podstawie [szablonu](er-fillable-excel.md#excel-file-component) w formacie Microsoft Excel.
- Utwórz [niestandardową (pochodny)](general-electronic-reporting.md#building-a-format-selecting-another-format-as-a-base-customization) wersję standardowej konfiguracji formatu modułu ER, która jest oferowana przez Microsoft.
- Zmodyfikuj niestandardową konfigurację formatu ER, tak aby generował raport faktury elektronicznej, który ma logo firmy w stopce.

Zadania przedstawione w tym temacie można wykonać w kontekście firmy **USMF**. Nie są wymagane umiejętności kodowania. Przed rozpoczęciem musisz pobrać i zapisać następujące pliki.

| opis        | Nazwa pliku |
|--------------------|-----------|
| Obraz logo firmy | [Logo firmy.png](https://download.microsoft.com/download/8/2/e/82e6bd81-caac-4e9a-bfce-1392ce7c8616/Companylogo.png) |

## <a name="content"></a>Zawartość

- [Konfiguracja osoby prawnej](#ConfigureLegalEntity)
- [Konfigurowanie struktury ER](#ConfigureFramework)

    - [Konfigurowanie parametrów modułu ER](#ConfigureParameters)
    - [Aktywowanie dostawcy konfiguracji ER](#ActivateProvider)

        - [Przejrzenie listy dostawców konfiguracji ER](#ReviewProvidersList)
        - [Dodawanie nowego dostawcy formatu ER](#AddProvider)
        - [Aktywowanie nowego dostawcy konfiguracji ER](#ActivateAddedProvider)

- [Importowanie standardowej konfiguracji formatu ER](#ImportERSolution1)

    - [Importowanie standardowych konfiguracji ER](#ImportERFormat)
    - [Przeglądanie zaimportowanych konfiguracji ER](#ReviewImportedERSolution)

- [Wydrukuj fakturę niezależną, korzystając ze standardowego formatu ER](#PrintInvoice1)

    - [Ustaw zarządzanie drukowaniem..](#ConfigurePrintManagement1)
    - [Umożliwia wydrukowanie faktury niezależnej](#ProcessInvoice1)

- [Dostosowywanie standardowego formatu ER](#CustomizeProvidedFormat)

    - [Tworzenie niestandardowego formatu](#DeriveProvidedFormat)
    - [Edytuj format niestandardowy](#ConfigureDerivedFormat)
    - [Oznaczanie formatu niestandardowego jako wykonywalnego](#MarkFormatRunnable)

- [Wydrukuj fakturę niezależną, korzystając z niestandardowego formatu ER](#PrintInvoice2)

    - [Ustaw zarządzanie drukowaniem..](#ConfigurePrintManagement2)
    - [Umożliwia wydrukowanie faktury niezależnej](#ProcessInvoice2)

- [Dodatkowe zasoby](#References)

## <a name="configure-the-legal-entity"></a><a id="ConfigureLegalEntity"></a>Konfiguracja osoby prawnej

1. Wybierz kolejno opcje **Administrowanie organizacją** \> **Organizacje** \> **Firmy**.
2. Na stronie **Firmy** na skróconej karcie **logo firmy raportu** wybierz pozycję **Zmień**.
3. W oknie dialogowym **Wybierz plik obrazu do przekazania** wybierz pozycję **Przeglądaj** i wybierz **plik logo firmy.png**, który został pobrany wcześniej.
4. Wybierz **Zapisz** i zamknij stronę **Firmy**.

![Obraz logo firmy wybrany na stronie Firmy.](./media/er-embed-images-header-footer-excel-reports-company-logo-image.png)

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
> Konfigurację ER może edytować tylko właściciel konfiguracji. Przed rozpoczęciem edytowania konfiguracji ER należy aktywować samą konfigurację w obszarze roboczym **Raportowanie elektroniczne**.

#### <a name="review-the-list-of-er-configuration-providers"></a><a id="ReviewProvidersList"></a>Przejrzenie listy dostawców konfiguracji ER

1. Wybierz kolejno opcje **Administrowanie organizacją** \> **Obszary robocze** \> **Raportowanie elektroniczne**.
2. Na stronie **Konfiguracje lokalizacji** w sekcji **Powiązane łącza** wybierz kafelek **Dostawcy konfiguracji**.
3. Na stronie **Tabela dostawcy konfiguracji** każdy rekord dostawcy ma unikatową nazwę i adres URL. Przejrzyj zawartość tej strony. Jeśli rekord dla **Litware, Inc.** (`https://www.litware.com`) już istnieje, pomiń następną procedurę, [Dodawanie nowego dostawcy konfiguracji ER](#AddProvider).

#### <a name="add-a-new-er-configuration-provider"></a><a id="AddProvider"></a>Dodawanie nowego dostawcy formatu ER

1. Wybierz kolejno opcje **Administrowanie organizacją** \> **Obszary robocze** \> **Raportowanie elektroniczne**.
2. Na stronie **Konfiguracje lokalizacji** w sekcji **Powiązane łącza** wybierz kafelek **Dostawcy konfiguracji**.
3. Na stronie **Dostawcy konfiguracji** wybierz opcję **Nowa**.
4. W polu **Nazwa** wpisz **Litware, Inc.**
5. W polu **Adres internetowy** wprowadź `https://www.litware.com`.
6. Wybierz opcję **Zapisz**.

#### <a name="activate-the-new-er-configuration-provider"></a><a id="ActivateAddedProvider"></a>Aktywowanie nowego dostawcy konfiguracji ER

1. Wybierz kolejno opcje **Administrowanie organizacją** \> **Obszary robocze** \> **Raportowanie elektroniczne**.
2. Na stronie **Konfiguracje lokalizacji** w sekcji **Dostawcy konfiguracji** wybierz pozycję **Litware, Inc.**, a następnie wybierz pozycję **Ustaw, jako aktywne**.

Dalsze informacje o dostawcach konfiguracji ER znajdują się w temacie [Tworzenie dostawców konfiguracji i oznaczanie ich jako aktywnych](tasks/er-configuration-provider-mark-it-active-2016-11.md).

## <a name="import-the-standard-er-format-configurations"></a><a id="ImportERSolution1"></a>Importowanie standardowej konfiguracji formatu ER

### <a name="import-the-standard-er-configurations"></a><a id="ImportERFormat"></a>Importowanie standardowych konfiguracji ER

Aby dodać standardowe konfiguracje obiektu ER do bieżącego wystąpienia rozwiązania Dynamics 365 Finance, należy zaimportować je z [repozytorium](general-electronic-reporting.md#Repository) ER, które zostało skonfigurowane dla tego wystąpienia.

1. Wybierz kolejno opcje **Administrowanie organizacją** \> **Obszary robocze** \> **Raportowanie elektroniczne**.
2. Na stronie **Konfiguracje lokalizacji** w sekcji **Dostawcy konfiguracji** wybierz kafelek **Microsoft**, a następnie wybierz pozycję **Repozytoria**, aby wyświetlić listę repozytoriów dla dostawcy rozwiązania: **Microsoft**.
3. Na stronie **Repozytoria konfiguracji** zaznacz repozytorium typu **Globalne**, a następnie kliknij przycisk **Otwórz**. Jeśli zostanie wyświetlony monit o autoryzację połączenia z usługą [Regulatory Configuration Service](../../../finance/localizations/rcs-overview.md), postępuj zgodnie z instrukcjami autoryzacji.
4. Na stronie **Repozytorium konfiguracji** w drzewie konfiguracje w panelu po lewej wybierz format konfiguracji **Faktura niezależna (Excel)**.
5. Na skróconej karcie **Wersje** wybierz najnowszą wersję (na przykład **240.112**) wybranej konfiguracji formatu ER.
6. Wybierz **Importuj**, aby pobrać wybraną wersję z Globalnego repozytorium do bieżącego wystąpienia Finance.

![Importowanie standardowych konfiguracji ER na stronie repozytorium konfiguracji.](./media/er-embed-images-header-footer-excel-reports-import-solution.png)

> [!TIP]
> Jeśli masz problemy z dostępem do [repozytorium globalnego](er-download-configurations-global-repo.md), zamiast tego możesz [pobrać konfiguracje](download-electronic-reporting-configuration-lcs.md) z Microsoft Dynamics Lifecycle Services (LCS).

### <a name="review-the-imported-er-configurations"></a><a id="ReviewImportedERSolution"></a>Przeglądanie zaimportowanych konfiguracji ER

1. Wybierz kolejno opcje **Administrowanie organizacją** \> **Obszary robocze** \> **Raportowanie elektroniczne**.
2. WNa stronie **Konfiguracje lokalizacji** w sekcji **Konfiguracje** wybierz kafelek **Konfigracje raportowanias**.
3. Na stronie **Konfiguracje** w drzewie konfiguracji w panelu po lewej wybierz pozycję **Model faktury**.
4. Należy zauważyć, że oprócz wybranego formatu ER **Faktura niezależna (Excel)** zostały zaimportowane inne wymagane konfiguracje obiektów konfiguracji. Upewnij się, że w drzewie konfiguracji są dostępne następujące konfiguracje modułu ER:

    - **Model faktury** – Ta konfiguracja zawiera składnik ER [modelu danych](general-electronic-reporting.md#data-model-and-model-mapping-components), który reprezentuje strukturę danych domeny biznesowej fakturowania.
    - **Mapowanie modelu fakturowania** – Ta konfiguracja zawiera [składnik mapowanie modelu](general-electronic-reporting.md#data-model-and-model-mapping-components), który opisuje sposób wypełniania modelu danych przy użyciu danych aplikacji w czasie wykonywania.
    - **Faktura free text (Excel)** — ta konfiguracja zawiera składniki mapowania formatu i [formatu](general-electronic-reporting.md#FormatComponentOutbound) ER. Składnik formatu określa układ raportu na podstawie szablonu w formacie programu Excel. Komponent mapowania formatu zawiera modelowe źródło danych i określa, w jaki sposób to źródło danych jest używane do wypełniania układu raportu w czasie wykonywania.

![Zaimportowane konfiguracje ER na stronie konfiguracje.](./media/er-embed-images-header-footer-excel-reports-imported-solution.png)

## <a name="print-a-free-text-invoice-by-using-the-standard-er-format"></a><a id="PrintInvoice1"></a>Wydrukuj fakturę niezależną, korzystając ze standardowego formatu ER

### <a name="set-up-print-management"></a><a id="ConfigurePrintManagement1"></a>Ustaw zarządzanie drukowaniem

1. Wybierz kolejno opcje **Rozrachunki z odbiorcami** \> **Faktury** \> **Wszystkie faktury niezależne**.
2. Na stronie **Faktura niezależną** wybierz numer **FTI-00000002** fakturę, a następnie w okienku akcji na karcie **Faktura** w grupie **Zarządzanie drukowaniem** wybierz pozycję **Zarządzanie drukowaniem**.
3. Na stronie **Ustawienia zarządzania drukowaniem**, w drzewie po lewej stronie rozwiń **moduł \>dokumenty rozrachunków z odbiorcami \> faktura niezależna**, a następnie wybierz pozycję **Oryginalna \<Default\>**.
4. W polu **Format raportu** wybierz pozycję **Faktura niezależna (Excel)** .
5. Wybierz klawisz **Esc**, aby opuścić stronę konfiguracji **zarządzania drukowaniem** i powrócić do strony **Faktura niezależna**.

![Ustawienia zarządzania drukowaniem dla faktury niezależnej w standardowym formacie ER na stronie Ustawienia zarządzania drukowaniem.](./media/er-embed-images-header-footer-excel-reports-print-management.png)

### <a name="print-a-free-text-invoice"></a><a id="ProcessInvoice1"></a>Umożliwia wydrukowanie faktury niezależnej

1. Na stronie **Faktura niezależna** upewnij się, że faktura **FTI-00000002** jest wciąż zaznaczona, a następnie w okienku akcji na karcie **Faktura** w grupie **Dokument** wybierz pozycję **Drukowanie** \> **Wybrane**.
2. Pobierz wygenerowaną fakturę w formacie programu Excel i otwórz ją do podglądu.
3. Zwróć uwagę, że zgodnie ze strukturą szablonu Excel dla podanego formatu ER, stopka strony wygenerowanej faktury zawiera informacje o bieżącym numerze strony i łącznej liczbie stron w raporcie.

![Generowanie faktury niezależnej.](./media/er-embed-images-header-footer-excel-reports-print-invoice1.gif)

## <a name="customize-the-standard-er-format"></a><a id="CustomizeProvidedFormat"></a>Dostosowywanie standardowego formatu ER

Na przykład w tej sekcji można użyć konfiguracji ER dostarczonych przez firmę Microsoft do wygenerowania faktury niezależnej w formacie programu Excel. Należy jednak dodać dostosowanie, aby obraz logo firmy był umieszczany w stopce strony generowanych faktur.

W takim przypadku jako przedstawiciel Litware, Inc. musisz utworzyć (wyprowadzić) nową konfigurację formatu raportowania elektronicznego opartą na konfiguracji **Faktury niezależnej (Excel)** dostarczonej przez firmę Microsoft.

### <a name="create-a-custom-format"></a><a id="DeriveProvidedFormat"></a>Tworzenie niestandardowego formatu

1. Otwórz **Administracja organizacji** \> **Elektroniczne raportowanie** \> **Konfiguracje**.
2. Na stronie **Konfiguracje** w drzewie konfiguracji w panelu po lewej wybierz pozycję **Model faktury**, a potem wybierz **Faktura niezależna (Excel)**. Litware, Inc. będzie używał importowanej wersji (na przykład **240.112**) tej konfiguracji formatu ER jako podstawy dla wersji niestandardowej.
3. Wybierz przycisk **Utwórz konfigurację**, aby otworzyć rozwijane okno dialogowe. Nowe okno dialogowe pozwoli utworzyć nową konfigurację dla niestandardowego formatu płatności.
4. W **Nowej** grupie pól, wybierz opcję **Pochodna od nazwy: Faktura niezależna (Excel), Microsoft**.
5. W polu **Nazwa** wpisz **Niestandardowa faktura niezależna (Excel)** .
6. Wybierz **Utwórz konfigurację**.

![Tworzenie konfiguracji dla niestandardowego formatu płatności w rozwijanym oknie dialogowym Utwórz konfigurację.](./media/er-embed-images-header-footer-excel-reports-add-derived-format.png)

Zostanie 240.112.1 wersja formatu ER **niestandardowej faktury niezależnej (Excel)**. Ta wersja ma [stan](general-electronic-reporting.md#component-versioning) **Wersji roboczej** i można ją edytować. Bieżąca zawartość niestandardowego formatu ER jest zgodna z zawartością formatu dostarczonego przez Microsoft.

![Nowa wersja konfiguracji formatu ER utworzona na stronie Konfiguracje.](./media/er-embed-images-header-footer-excel-reports-derived-format-configuration1.png)

### <a name="edit-the-custom-format"></a><a id="ConfigureDerivedFormat"></a>Edytuj format niestandardowy

Skonfiguruj niestandardowy format, aby obraz logo firmy był umieszczany w stopce na każdej stronie raportu.

1. Otwórz **Administracja organizacji** \> **Elektroniczne raportowanie** \> **Konfiguracje**.
2. Na stronie **Konfiguracje** w drzewie konfiguracji w panelu po lewej wybierz pozycję **Model płatności**, a potem wybierz **Niestandardowa faktura niezależna (Excel)**.
3. Na skróconej karcie **Wersje** wybierz wersję **240.112.1** wybranej konfiguracji.
4. Wybierz opcję **Konstruktor**.
5. Na stronie **Projektant formatów** wybierz opcję **Pokaż szczegóły**, aby wyświetlić więcej informacji o elementach formatu.
6. Rozwiń i przejrzyj następujące elementy:

    - Element **faktury niezależnej** typu **Excel**. Ten element służy do generowania faktury w formacie skoroszytu programu Excel.
    - Element **faktury niezależnej \\ Faktura** typu **Arkusz**. Ten element służy do generowania arkusza wygenerowanego skoroszytu programu Excel.
    - Element **faktury niezależnej \\ Faktura \\ Stopka** typu **Stopka**. Ten element służy do wypełniania stopki faktur.

7. Wybierz element **Faktura niezależna \\ Faktura \\ Stopka**.

    ![Element stopki w projektancie operacji ER.](./media/er-embed-images-header-footer-excel-reports-derived-format0.png)

    > [!NOTE]
    > Każda stopka strony wygenerowanej faktury zawiera informacje o aktualnym numerze strony oraz łącznej liczbie stron w raporcie. Jak widać, element **Faktura niezależna \\ faktura \\ stopka** nie ma elementów podrzędnych. Dlatego używany szablon programu Excel jest skonfigurowany tak, aby wyświetlać szczegóły stronicowania w środku stopki każdego raportu.

8. Wybierz opcję **Dodaj**, a następnie wybierz typ **Excel \\ Obraz** dodawanego elementu formatu:

    1. W polu **Wyrównanie** wybierz pozycję Wyrównanie do **prawej**.
    2. W polu **Skaluj wysokość** wybierz pozycję **Względna**.
    3. W polu **Skala w procentach** wprowadź **wartość 70**.
    4. Kliknij przycisk **OK**.

        > [!NOTE]
        > Element **Excel \\ Obraz** służy do dodawania obrazu logo firmy i wyrównania go po prawej stronie stopki strony.

    ![Właściwości elementu obrazu w oknie dialogowym Właściwości składnika.](./media/er-embed-images-header-footer-excel-reports-derived-format1.png)

9. W drzewie struktury formatu po lewej stronie wybierz element **Obraz**, który właśnie dodano, a następnie na karcie **Mapowanie** rozwiń źródło danych **modelu**.
10. Rozwiń **model.Payment** \> **model.InvoiceBase \> model.InvoiceBase.CompanyInfo**, a następnie wybierz pole źródła danych **model.InvoiceBase.CompanyInfo.Logo**. Pole źródła danych typu [Kontener](er-formula-supported-data-types-composite.md#container) uwidacznia logo firmy jako zawartość multimediów.
11. Wybierz **Powiąż**. Element formatu **obrazu** jest teraz powiązany z polem źródła danych **model.InvoiceBase.CompanyInfo.Logo**. Dlatego w czasie wykonywania logo firmy zostanie umieszone w stopce wygenerowanych faktur.

    ![Element formatu obrazu powiązany z polem źródła danych model.InvoiceBase.CompanyInfo.Logo w projektancie operacji ER.](./media/er-embed-images-header-footer-excel-reports-derived-format2.png)

12. Zamknij stronę **Projektowanie formuły** i wybierz **Projektant**.

### <a name="mark-the-custom-format-as-runnable"></a><a id="MarkFormatRunnable"></a>Oznaczanie formatu niestandardowego jako wykonywalnego

Teraz, gdy została utworzona pierwsza wersja formatu niestandardowego i ma ona stan **Wersja robocza**, można uruchomić format w celach testowych. Aby uruchomić raport, należy przetworzyć płatność dostawcy, używając metody płatności, która odwołuje się do niestandardowego formatu encji (ER). Domyślnie, podczas wywoływania formatu ER w aplikacji, jedynie wersje, które mają stan **Zakończono** lub **Udostępniono**, są [używane](general-electronic-reporting.md#component-versioning). To zachowanie pomaga zapobiegać używaniu formatów ER, w których znajdują się nieukończone projekty. Jednak w przypadku uruchamiania testów można wymusić na aplikacji używanie wersji formatu ER, która ma stan **Wersja robocza**. W ten sposób można dostosować bieżącą wersję formatu, jeśli są wymagane jakiekolwiek modyfikacje. Aby uzyskać więcej informacji, zobacz [Zastosowanie](electronic-reporting-destinations.md#applicability).

Aby można było skorzystać z wersji roboczej formatu ER, należy odpowiednio go oznaczyć.

1. Otwórz **Administracja organizacji** \> **Elektroniczne raportowanie** \> **Konfiguracje**.
2. Na stronie **Konfiguracje** w okienku akcji na karcie **Konfiguracje** w grupie **Ustawienia zaawansowane** wybierz opcję **Parametry użytkownika**.
3. W oknie dialogowym **Parametry użytkownika** określ opcję **Ustawienia uruchamiania** na **Tak**, a następnie wybierz **OK**.
4. Wybierz **Edytuj**, aby umożliwić edycję bieżącej strony, a następnie w drzewie konfiguracji w lewym okienku wybierz opcję **Niestandardowa faktura niezależna (Excel)**.
5. Ustaw wartość **Uruchom wersję roboczą** na wartość **Tak**.

![Oznaczanie formatu niestandardowego jako uruchamianego na stronie Konfiguracje.](./media/er-embed-images-header-footer-excel-reports-derived-format-configuration2.png)

## <a name="print-a-free-text-invoice-by-using-the-custom-er-format"></a><a id="PrintInvoice2"></a>Wydrukuj fakturę niezależną, korzystając z niestandardowego formatu ER

### <a name="set-up-print-management"></a><a id="ConfigurePrintManagement2"></a>Ustaw zarządzanie drukowaniem

1. Wybierz kolejno opcje **Rozrachunki z odbiorcami** \> **Faktury** \> **Wszystkie faktury niezależne**.
2. Na stronie **Faktura niezależną** wybierz numer **FTI-00000002** fakturę, a następnie w okienku akcji na karcie **Faktura** w grupie **Zarządzanie drukowaniem** wybierz pozycję **Zarządzanie drukowaniem**.
3. Na stronie **Ustawienia zarządzania drukowaniem**, w drzewie po lewej stronie rozwiń **moduł - rozrachunki z odbiorcami** \> **Dokumenty** \> **faktura niezależna**, a następnie wybierz pozycję **Oryginalna** **\<Default\>**.
4. W polu **Format raportu** wybierz pozycję **Niestandardowa faktura niezależna (Excel)** .
5. Wybierz klawisz **Esc**, aby opuścić stronę konfiguracji **zarządzania drukowaniem** i powrócić do strony **Faktura niezależna**.

### <a name="print-a-free-text-invoice"></a><a id="ProcessInvoice2"></a>Umożliwia wydrukowanie faktury niezależnej

1. Na stronie **Faktura niezależna** upewnij się, że faktura **FTI-00000002** jest wciąż zaznaczona, a następnie w okienku akcji na karcie **Faktura** w grupie **Dokument** wybierz pozycję **Drukowanie** \> **Wybrane**.
2. Pobierz wygenerowaną fakturę w formacie programu Excel i otwórz ją do podglądu.
3. Zwróć uwagę, że zgodnie ze strukturą niestandardowego formatu ER, stopka strony wygenerowanej faktury zawiera oprócz informacji o stronicowaniu raportu obraz logo firmy.

![Wygenerowana faktura niezależna z wizerunkiem logo firmy w stopce strony.](./media/er-embed-images-header-footer-excel-reports-print-invoice2.gif)

## <a name="additional-resources"></a><a id="References"></a>Dodatkowe zasoby

- [Projektowanie konfiguracji projektu w celu generowania dokumentów wychodzących w formacie programu Excel](er-fillable-excel.md)
- [Osadzanie obrazów i kształtów w generowanych dokumentach przez raportowanie elektroniczne](electronic-reporting-embed-images-shapes.md)
