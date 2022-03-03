---
title: Umożliwia dostosowanie konfiguracji raportowania elektronicznego w celu wygenerowania dokumentu elektronicznego
description: W tym temacie wyjaśniono, jak dostosować konfiguracje raportowania elektronicznego (ER) dostarczone przez firmę Microsoft, które są używane do generowania niestandardowego dokumentu elektronicznego.
author: NickSelin
ms.date: 10/21/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERParameters, ERDataModelDesigner, ERModelMappingTable, ERModelMappingDesigner, EROperationDesigner, ERVendorTable
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom:
- "220314"
- intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2c8cf4866b6a8c239359d726d8cd4f03a9eb4137
ms.sourcegitcommit: d5d6b81bd8b08de20cc018c2251436065982489e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/17/2022
ms.locfileid: "8324094"
---
# <a name="customize-electronic-reporting-configurations-to-generate-an-electronic-document"></a>Umożliwia dostosowanie konfiguracji raportowania elektronicznego w celu wygenerowania dokumentu elektronicznego

[!include[banner](../includes/banner.md)]

[Struktura sprawozdawczości elektronicznej (ER)](general-electronic-reporting.md) umożliwia przekazywanie [konfiguracji](general-electronic-reporting.md#Configuration) ER, które są dostarczane do wystąpienia Microsoft Dynamics 365 Finance. W ten sposób konfiguracje dostarczone przez firmę Microsoft mogą pełnić rolę rozwiązania ER używanego do generowania elektronicznych faktur odbiorców (faktury elektronicznej). Za pomocą tego rozwiązania ER można skonfigurować niestandardowe rozwiązanie ER, aby uzyskać dostęp do niestandardowych pól bazy danych i generować faktury elektroniczne zgodne z określonymi wymaganiami, bez konieczności edytowania kodu źródłowego.

## <a name="overview"></a>Omówienie

Na przykład w tym temacie należy określić federalny kod identyfikacji podatkowej jako nowy atrybut niestandardowy każdego klienta, któremu wystawiamy fakturę elektroniczną. Dlatego należy dostosować strukturę aktualnie używanej faktury, dodając nową pozycję, którą należy wypełnić kodem podatkowym w każdej generowanej e-fakturze.

Procedury opisane w tym temacie wyjaśniają, w jaki sposób użytkownik pełniący rolę administratora systemu, dewelopera raportowania elektronicznego lub konsultanta funkcjonalnego raportowania elektronicznego może wykonywać następujące zadania w instancji Finance:

- [Skonfiguruj minimalny zestaw parametrów funkcji ER wymaganych do rozpoczęcia korzystania z struktury ER](#ConfigureER).
- [Zaimportuj początkowe wersje standardowych konfiguracji ER, które są udostępniane w celu generowania faktur elektronicznych](#ImportERConfigurations1).
- [Skonfiguruj Parametry rozrachunków z odbiorcami w celu rozpoczęcia używania standardowych konfiguracji ER](#ConfigureAR1).
- [Skonfiguruj parametry firmy do fakturowania odbiorców](#ConfigureLE).
- [Przygotuj rekord odbiorcy do fakturowania elektronicznego](#ConfigureCustomer1).
- [Umożliwia dodanie, zaksięgowanie i wysłanie faktury dla odbiorcy przy użyciu standardowych konfiguracji modelu ER](#ProcessInvoice1).
- [Umożliwia dodanie niestandardowego pola bazy danych w celu zarządzania kodem federalnego identyfikacji podatkowej dla odbiorców](#AddCustomField).
- [Odśwież metadane ER, aby włączyć zmiany w bazie danych dla konstruktora mapowania modelu ER](#RefreshERMetadata).
- [Zaprojektuj niestandardowe konfiguracje ER, aby generować faktury elektroniczne zawierające nowy kod podatku](#DesignCustomERConfigurations).
- [Skonfiguruj Parametry rozrachunków z odbiorcami w celu rozpoczęcia używania niestandardowych konfiguracji ER](#ConfigureAR2).
- [Aktualizuj rekord odbiorcy do fakturowania elektronicznego](#ConfigureCustomer2).
- [Umożliwia dodanie, zaksięgowanie i wysłanie faktury dla odbiorcy przy użyciu niestandardowych konfiguracji modelu ER](#ProcessInvoice2).
- [Zaimportuj nowe wersje standardowych konfiguracji ER, które są udostępniane w celu generowania faktur elektronicznych](#ImportERConfigurations2).
- [Zatwierdzić zmiany w nowych wersjach standardowych konfiguracji modelu ER w niestandardowych konfiguracjach ER](#RebaseCustomERConfigurations).
- [Umożliwia dodanie, zaksięgowanie i wysłanie faktury dla odbiorcy przy użyciu nowych wersji niestandardowych konfiguracji modelu ER](#ProcessInvoice3).

Wszystkie te procedury można wykonać na danych firmy **DEMF**.

## <a name="configure-the-er-framework"></a><a name="ConfigureER"></a>Konfigurowanie struktury ER

Użytkownik należący do roli konsultanta funkcjonalnego raportowania elektronicznego lub dewelopera raportów elektronicznych musi skonfigurować minimalny zestaw parametrów funkcji ER. Następnie można rozpocząć korzystanie z struktury ER w celu zaprojektowania niestandardowych wersji standardowych konfiguracji rozwiązania ER używanego do generowania faktur elektronicznych.

### <a name="configure-er-parameters"></a>Konfigurowanie parametrów modułu ER

1. Wybierz kolejno opcje **Administrowanie organizacją** \> **Obszary robocze** \> **Raportowanie elektroniczne**.
2. Na stronie **Konfiguracje lokalizacji** w sekcji **Powiązane łącza** wybierz kafelek **Parametry raportowania elektronicznego**.
3. Na stronie **Parametry raportowania elektronicznego** na karcie **Ogólne** ustaw opcję **Włącz tryb projektowania** na **Tak**.
4. Na karcie **Załączniki**, w polu **Konfiguracje** wybierz opcję **Plik**.
5. W polach **Archiwum zadań**, **Tymczasowe**, **Podstawowe** i **Inne** należy wybrać typ **Plik**.

Aby uzyskać więcej informacji o parametrach modułu ER, zapoznaj się z tematem [Konfiguracja struktury ER](electronic-reporting-er-configure-parameters.md).

### <a name="activate-an-er-configuration-provider"></a>Aktywowanie dostawcy konfiguracji ER

Każda dodana konfiguracja ER jest oznaczona jako posiadana przez dostawcę konfiguracji ER. W tym celu jest używany dostawca konfiguracji ER, który został aktywowany w obszarze roboczym **Raportowanie elektroniczne**. Dlatego przed rozpoczęciem dodawania lub edytowania konfiguracji ER należy aktywować dostawcę konfiguracji ER w obszarze roboczym **Raportowanie elektroniczne**.

> [!NOTE]
> Tylko właściciel konfiguracji ER może ją edytować. Dlatego przed rozpoczęciem edytowania konfiguracji ER należy aktywować samą konfigurację w obszarze roboczym **Raportowanie elektroniczne**.

#### <a name="review-the-list-of-er-configuration-providers"></a>Przejrzenie listy dostawców konfiguracji ER

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

#### <a name="activate-an-er-configuration-provider"></a>Aktywowanie dostawcy konfiguracji ER

1. Wybierz kolejno opcje **Administrowanie organizacją** \> **Obszary robocze** \> **Raportowanie elektroniczne**.
2. Na stronie **Konfiguracje lokalizacji** w sekcji **Dostawcy konfiguracji** wybierz pozycję **Litware, Inc.**, a następnie wybierz pozycję **Ustaw, jako aktywne**.

Dalsze informacje o dostawcach konfiguracji ER znajdują się w temacie [Tworzenie dostawców konfiguracji i oznaczanie ich jako aktywnych](tasks/er-configuration-provider-mark-it-active-2016-11.md).

## <a name="import-the-initial-versions-of-standard-er-configurations"></a><a name="ImportERConfigurations1"></a>Importowanie początkowej wersji standardowej konfiguracji ER

Aby dodać standardowe konfiguracje obiektu ER do bieżącego wystąpienia Finance, należy zaimportować je z [repozytorium](general-electronic-reporting.md#Repository) ER, które zostało skonfigurowane dla tego wystąpienia.

1. Wybierz kolejno opcje **Administrowanie organizacją** \> **Obszary robocze** \> **Raportowanie elektroniczne**.
2. Na stronie **Konfiguracje lokalizacji** w sekcji **Dostawcy konfiguracji** wybierz kafelek **Microsoft**, a następnie wybierz pozycję **Repozytoria**, aby wyświetlić listę repozytoriów dla dostawcy rozwiązania: Microsoft.
3. Na stronie **Repozytoria konfiguracji** zaznacz repozytorium typu **Globalne**, a następnie kliknij przycisk **Otwórz**. Jeśli zostanie wyświetlony monit o autoryzację połączenia z usługą Regulatory Configuration Service, postępuj zgodnie z instrukcjami autoryzacji.
4. Na stronie **Repozytorium konfiguracji** w drzewie konfiguracje w panelu po lewej wybierz format konfiguracji **Faktura sprzedaży PEPPOL**.
5. Na skróconej karcie **wersje** wybierz opcję wersja **11.2.2**.
6. Wybierz opcję **Importuj**, aby pobrać wybraną wersję z repozytorium globalnego.

![Strona Repozytorium konfiguracji.](./media/er-quick-start3-import-solution1.png)

> [!TIP]
> Jeśli masz problemy z dostępem do [repozytorium globalnego](er-download-configurations-global-repo.md), zamiast tego możesz [pobrać konfiguracje](download-electronic-reporting-configuration-lcs.md) z Microsoft Dynamics Lifecycle Services (LCS).

### <a name="review-the-imported-er-configurations"></a>Przeglądanie zaimportowanych konfiguracji ER

1. Wybierz kolejno opcje **Administrowanie organizacją** \> **Obszary robocze** \> **Raportowanie elektroniczne**.
2. WNa stronie **Konfiguracje lokalizacji** w sekcji **Konfiguracje** wybierz kafelek **Konfigracje raportowanias**.
3. Na stronie **Konfiguracje** rozwiń skróconą kartę **Składniki konfiguracji**.
4. W drzewie konfiguracji w lewym okienku rozwiń węzeł **Model faktury**, a następnie rozwiń węzeł **UBL faktura sprzedaży**.

Należy zauważyć, że oprócz wybranego formatu ER **Faktura sprzedaży PEPPOL** zostały zaimportowane inne wymagane konfiguracje obiektów konfiguracji. Ponieważ nowe wersje konfiguracji programu ER są regularnie publikowane w repozytorium globalnym i usługi LCS, aby zachować odpowiednie rozwiązania zgodne z nowymi wymaganiami, zostaną zaimportowane najnowsze wersje wymaganej konfiguracji modelu danych i mapowania modeli.

![Strona Konfiguracje.](./media/er-quick-start3-imported-solution1a.png)

Aby symulować stan, w którym będą używane konfiguracje ER w bieżącym wystąpieniu Finance, jeśli w przeszłości zaimportowano wersję **11.2.2** **Faktura sprzedaży PEPPOL** (na przykład 7 sierpnia 2019), należy wykonać następujące kroki:

- W okienku akcji wybierz opcję **Usuń**, aby usunąć wszystkie konfiguracje ER, które zostały opublikowane po 7 sierpnia 2019. Jedyne **Modele faktur**, **Mapowanie modelu faktury** (początkowo nazwane **Mapowanie modeli faktur odbiorców**), **UBL faktura sprzedaży** i **Faktura sprzedaży PEPPOL** muszą być wystawione.
- W przypadku pozostałych konfiguracji systemu, na skróconej karcie **Wersje** wybierz opcję **Usuń**, aby usunąć wszystkie wersje konfiguracji systemu, które zostały opublikowane po 7 sierpnia 2019.

Upewnij się, że w drzewie konfiguracji są dostępne następujące konfiguracje modułu ER:

- Konfiguracja modelu danych ER dla **Modelu faktury** (wstępnie nazwany **Model faktury dla odbiorcy**):

    - Wersja 11 zawiera wersję 10 składnika ER modelu danych, który reprezentuje strukturę danych w domenie biznesowej fakturowania. Ta konfiguracja obiektu ER została zaimportowana jako element nadrzędny w formacie ER **Faktura sprzedaży PEPPOL**, który został wybrany do importu.
    - Wersja 50 zawiera wersję 31 składnika ER modelu danych. Ta konfiguracja obiektu ER została zaimportowana jako element nadrzędny z 7 sierpnia 2019 w wersji konfiguracji mapowania modelu ER **Mapowania modeli faktur**.

    ![Konfiguracja modelu danych ER faktur dla modelu faktury na stronie konfiguracje.](./media/er-quick-start3-imported-solution1b1.png)

    > [!TIP]
    > Jeśli wersja 50 tego modelu danych nie jest wyświetlana, otwórz repozytorium globalne i zaimportuj wersję 50.19 konfiguracji ER **Mapowania modeli faktur**.

- **Mapowanie modelu faktury** Konfiguracja mapowania modelu ER (wstępnie nazwany **Mapowanie faktury dla odbiorcy**):

    - Wersja 50,19 została zaimportowana jako Najnowsza implementacja w wersji 50 konfiguracji modelu danych ER faktur dla **Modelu faktury**. Zawiera dwa składniki ER mapowania modelu, które opisują sposób wypełniania modelu danych danymi aplikacji w czasie wykonywania.

    ![Mapowanie modelu faktury Konfiguracja mapowania modelu ER na stronie Konfiguracje.](./media/er-quick-start3-imported-solution1b2.png)

    > [!TIP]
    > Jeśli wersja 50.19 tego mapowania modelu nie jest wyświetlana, otwórz repozytorium globalne i zaimportuj wersję 50.19 konfiguracji ER **Mapowania modeli faktur**.

- **Faktura sprzedaży UBL** Konfiguracja formatu ER:

    - Wersja 11.2 zawiera format i komponenty ER mapowania formatu. Składnik formatu określa układ raportu. Komponent mapowania formatu zawiera modelowe źródło danych i określa, w jaki sposób to źródło danych jest używane do wypełniania układu raportu w czasie wykonywania. Ten format ER został skonfigurowany do generowania faktur elektronicznych w formacie Universal Business Language (UBL). Został zaimportowany jako nadrzędny dla formatu ER **Faktura sprzedaży PEPPOL**, który został wybrany do importu.

- **Faktura sprzedaży PEPPOL** Konfiguracja formatu ER:

    - Wersja 11.2.2 zawiera format i odwzorowanie formatów komponentów ER, które zostały skonfigurowane do generowania e-faktur w formacie Pan-European Public Procurement OnLine (PEPPOL).

    ![Konfiguracja formatu Peppol Sales Invoice ER na stronie Konfiguracje.](./media/er-quick-start3-imported-solution1b3.png)

## <a name="configure-the-accounts-receivable-parameters"></a><a name="ConfigureAR1"></a>Konfiguruj Parametry modułu rozrachunków z odbiorcami

1. Wybierz kolejno pozycje **Rozrachunki z odbiorcami** \> **Ustawienia** \> **Parametry modułu rozrachunków z odbiorcami**.
2. Na karcie **Dokumenty elektroniczne** na skróconej karcie **Raportowania elektronicznego** w polu **Sprzedaż i Faktura niezależna** wybierz opcję **Faktura sprzedaży PEPPOL**.
3. Wybierz opcję **Zapisz**.

![Karta dokumenty elektroniczne na stronie Parametry modułu rozrachunków z odbiorcami.](./media/er-quick-start3-configure-ar1.png)

## <a name="configure-the-legal-entity-parameters"></a><a name="ConfigureLE"></a>Konfigurowanie parametrów firmy

1. Wybierz kolejno opcje **Administrowanie organizacją** \> **Organizacje** \> **Firmy**.
2. W przypadku wybranej firmy **DEMF**,, na skróconej karcie **Informacje o koncie bankowym** w polu **Numer rozliczeniowy** wprowadź **1234**.
3. Wybierz opcję **Zapisz**.
4. Zamknij stronę **Firmy**.

## <a name="prepare-a-customer-record"></a><a name="ConfigureCustomer1"></a>Przygotuj nowy rekord odbiorcy

1. Wybierz kolejno opcje **Rozrachunki z odbiorcami** \> **Odbiorcy** \> **Wszyscy odbiorcy**.
2. Na stronie **Wszyscy odbiorcy** wybierz łącze konto odbiorcy **DE-014**.

### <a name="add-a-customer-contact"></a>Dodawanie osoby kontaktowej odbiorcy

1. Wybierz kolejno opcje **Rozrachunki z odbiorcami** \> **Odbiorcy** \> **Wszyscy odbiorcy**.
2. W okienku akcji na karcie **Odbiorca** w grupie **KOnta** wybierz opcję **Kontakty**.
3. Wybierz pozycję **Dodaj kontakty**.
4. Na stronie **Kontakty**, w polu **Imię**, otwórz odnośnik, wybierz pozycję **Adam Carter**, a następnie wybierz opcję **Wybierz**, aby zamknąć wyszukiwanie.
5. Wybierz opcję **Zapisz**.
6. Zamknij stronę **Kontakty**.

### <a name="define-a-primary-contact"></a>Definiowanie kontaktu podstawowego

1. Wybierz kolejno opcje **Rozrachunki z odbiorcami** \> **Odbiorcy** \> **Wszyscy odbiorcy**.
2. Na skróconej karcie **Demograficzne dotyczące sprzedaży** w polu **Kontakt główny** wybierz pozycję **Adam Carter**.

### <a name="set-the-e-invoicing-option"></a>Ustawienie opcji fakturowania elektronicznego

1. Wybierz kolejno opcje **Rozrachunki z odbiorcami** \> **Odbiorcy** \> **Wszyscy odbiorcy**.
2. Na skróconej karcie **Faktura i dostawa** należy określić opcję **eFaktura** na wartość **Tak**.
3. Wybierz opcję **Zapisz**.
4. Zamknij stronę **Wszyscy odbiorcy**.

## <a name="process-a-customer-invoice-by-using-the-standard-er-configurations"></a><a name="ProcessInvoice1"></a>Przetwarzaj fakturę dla odbiorcy przy użyciu standardowych konfiguracji ER

Można teraz stosować standardowe konfiguracje dla modelu ER importowane do elektronicznego wysyłania faktur niezależnych do odbiorcy

### <a name="add-a-new-invoice"></a>Dodaj nową fakturę

1. Wybierz kolejno opcje **Rozrachunki z odbiorcami** \> **Faktury** \> **Wszystkie faktury niezależne**.
2. Na stronie **Faktura niezależna** wybierz opcję **Nowy**.
3. Na skróconej karcie **Nagłówek faktury niezależnej** w polu **Konto odbiorcy** wybierz opcję **DE-014**.
4. Na skróconej karcie **Wiersze faktury** jest automatycznie dodawany wiersz faktury. W nowym wierszu ustaw następujące pola:

    - W polu **Opis** wprowadź **Notes**.
    - W polu **Konto główne** wybierz pozycję **401100**.
    - W polu **Cena jednostkowa** wpisz **1000**.

5. Wybierz opcję **Zapisz**.

![Strona faktury niezależnej.](./media/er-quick-start3-add-invoice.png)

Aby uzyskać więcej informacji, zobacz [Tworzenie faktury niezależnej](../../../finance/accounts-receivable/create-free-text-invoice-new.md).

### <a name="post-a-new-invoice"></a>Księguj nową fakturę

1. Wybierz kolejno opcje **Rozrachunki z odbiorcami** \> **Faktury** \> **Wszystkie faktury niezależne**.
2. Na stronie **Faktura niezależna** w okienku akcji wybierz **Księguj**.
3. W oknie dialogowym **Księgowanie faktury niezależnej** wybierz przycisk **OK**.

![Strona Szczegóły faktury niezależnej.](./media/er-quick-start3-post-invoice.png)

### <a name="send-a-posted-invoice"></a>Wyślij zaksięgowaną fakturę

1. Wybierz kolejno opcje **Rozrachunki z odbiorcami** \> **Faktury** \> **Wszystkie faktury niezależne**.
2. Na stronie **Faktura niezależna** w okienku akcji, w grupie **Dokumentów**, wybierz opcję **Wyślij** \> **Oryginał**.

    ![Podgląd oryginalnej faktury.](./media/er-quick-start3-send-invoice.png)

3. Zamknij stronę **Faktura niezależna**.

### <a name="analyze-a-generated-e-invoice"></a>Analizowanie wygenerowanej faktury elektronicznej

1. Wybierz kolejno opcje **Administrowanie organizacją** \> **Raportowanie elektroniczne** \> **Zadania raportowania elektronicznego**.
2. Na stronie **Zadania raportowania elektronicznego** wybierz początkowy rekord zawierający opis zadania, aby **Przesłać plik XML e-faktury**.
3. Wybierz opcję **Pokazuj pliki**, aby uzyskać dostęp do listy wygenerowanych plików.

    ![Strona zadania raportowania elektronicznego.](./media/er-quick-start3-jobs-list.png)

4. Wybierz opcję **Otwórz**, aby pobrać wygenerowany plik XML e-faktury.
5. Analizuj plik XML faktury elektronicznej. Należy zauważyć, że schemat podatku odbiorcy jest obecnie reprezentowany przez atrybuty **schemeID** i **schemeAgencyID**. Należy również zauważyć, że element XML **cbc:CustomizationID** zawiera obecnie następujący tekst: `urn:www.cenbii.eu:transaction:biicoretrdm010:ver1.0:# urn:www.peppol.eu:bis:peppol5a:ver1.0`.

    ![Podgląd wygenerowanego pliku XML e-faktury.](./media/er-quick-start3-e-invoice1.png)

## <a name="add-a-custom-database-field"></a><a name="AddCustomField"></a>Dodaj niestandardowe pole bazy danych

Funkcji [pola niestandardowego](../../fin-ops/get-started/user-defined-fields.md) można użyć w celu dostosowania w bieżącym wystąpieniu finansów następujących kryteriów:

- Umożliwia dostosowanie struktury bazy danych przez dodanie nowego niestandardowego pola bazy danych, w którym jest przechowywany federalny kod identyfikacji podatkowej dla każdego odbiorcy.
- Dostosuj stronę **Odbiorca**, dodając nowe pole wprowadzania danych, którego można użyć do wprowadzenia wartości kodu podatku w polu nowa niestandardowa baza danych

Wykonaj poniższe czynności, aby dostosować.

1. Wybierz kolejno opcje **Rozrachunki z odbiorcami** \> **Odbiorcy** \> **Wszyscy odbiorcy**.
2. Na stronie **Wszyscy odbiorcy** wybierz łącze konto odbiorcy **DE-014**.
3. Na skróconej karcie **Ogólne** kliknij prawym przyciskiem myszy dowolny pusty obszar w polu **Język**, a następnie wybierz polecenie **Personalizuj: UpperGroup**.

    Zawartość skróconej karty **Ogólny** jest wyróżniona, a pojawi się menu **Personalizacja**.

4. W menu **Personalizuj** wybierz opcję **Dodaj pole**.
5. W oknie dialogowym **Dodaj kolumny** wybierz opcję **Utwórz nowe pole**.
6. W oknie dialogowym **Utwórz nowe pole** w polu **Nazwa tabeli** wybierz opcję **Odbiorcy**.
7. W polu **Nazwa prefiksu** wpisz **FederalTaxID**.

    > [!NOTE]
    > Nazwa pola jest automatycznie definiowana jako **FederalTaxID\_Custom**.

8. W polu **Etykieta etykiety** wejdź do **Identyfikator podatkowy**.
9. W polu **Typ** zaznacz opcję **Tekst**.
10. W polu **Długość** wpisz **20**.
11. Wybierz opcję **Zapisz**.
12. W wyświetlonym oknie komunikatu wybierz opcję **Tak**, aby potwierdzić, że chcesz utworzyć nowy wpis pola **FederalTaxID** dla tabeli **Odbiorcy**.
13. W obszarze **Wstaw**, aby <a name="insert_custom_field"></a>dodać pole **FederalTaxID\_Custom** do bieżącej strony.

    ![Strona Wszyscy odbiorcy.](./media/er-quick-start3-create-new-field.gif)

14. Zamknij stronę **Wszyscy odbiorcy**.

## <a name="refresh-the-er-metadata"></a><a name="RefreshERMetadata"></a>Odśwież metadane ER

Aby dodane pole niestandardowe było [widoczne](electronic-reporting-er-configure-parameters.md#frequently-asked-questions) w projektancie mapowania modelu ER, należy odświeżyć metadane ER.

1. Otwórz **Administracja organizacji** \> **Elektroniczne raportowanie** \> **Przebuduj odniesienia do tabeli**.
2. W oknie dialogowym **Aktualizuj model danych** wybierz przycisk **OK**.

## <a name="design-the-custom-er-configurations"></a><a name="DesignCustomERConfigurations"></a>Projektowanie niestandardowych konfiguracji ER

Za pomocą konfiguracji ER dostarczonych przez firmę Microsoft można zaprojektować niestandardowe konfiguracje ER, tak aby generowały faktury elektroniczne zawierające nowy kod podatku.

### <a name="customize-the-data-model-configuration"></a>Dostosuj konfigurację modelu danych

Użytkownik należący do roli konsultanta funkcjonalnego do raportowania elektronicznego może zaprojektować niestandardowy model danych ER.

#### <a name="add-a-custom-data-model-configuration"></a>Dodaj niestandardową konfigurację modelu danych

1. Otwórz **Administracja organizacji** \> **Elektroniczne raportowanie** \> **Konfiguracje**.
2. Na stronie **Konfiguracje** w drzewie konfiguracji w panelu po lewej wybierz pozycję **Model faktur sprzedaży**.
3. W okienku akcji wybierz **Utwórz konfigurację**.
4. W oknie dialogowym rozwijanym w **Nowym** polu wybierz opcję **Na podstawie nazwy: Model faktury klienta, Microsoft** w celu wskazania, że nowy niestandardowy model danych ER powinien być oparty na konfiguracji modelu danych ER.
5. W polu **Nazwa** wpisz **Model faktury (Litware)**.
6. Wybierz **Stwórz konfiguracji**, aby dodać nową konfigurację ER.

Teraz można za jego użyciu edytować wersję 50.1 konfiguracji ER **Modelu faktury (Llitware)** w wersji **Roboczej** [stanu](general-electronic-reporting.md#component-versioning).

![Wersja 50.1 edytowalnej konfiguracji ER na stronie konfiguracje.](./media/er-quick-start3-added-custom-model.png)

#### <a name="configure-a-custom-data-model"></a>Skonfiguruj niestandardowy model danych

Musisz zmodyfikować niestandardowy model danych, dodając nowe pole, aby podać wartość w polu Kod identyfikacji podatkowej. Ten kod jest częścią danych odbiorcy dla każdego formatu ER, który będzie używał tego modelu danych jako źródła danych.

1. Na stronie **Konfiguracje** w drzewie konfiguracji w panelu po lewej wybierz pozycję **Model faktury (Litware)**.
2. Na skróconej karcie **Wersje** wybierz wersję **50.1** wybranej konfiguracji modelu danych ER w stanie **Roboczy**.
3. W okienku akcji wybierz opcję **Projektant** dla wybranej wersji konfiguracji.
4. Na stronie **Projektant modelu danych** w drzewie modelu danych wybierz pozycję **Informacje o odbiorcy (odbiorca)**.
5. Wybierz pozycję **Nowy**.
6. W oknie dialogowym rozwijanym, w polu **Nowy węzeł jako**, zaakceptuj wartość domyślną, **Element podrzędny aktywnego węzła**.
7. W polu **Nazwa** wpisz **FederalTaxID\_Litware**.
8. W polu **Typ towaru** zaakceptuj domyślną wartość, **Ciąg**.
9. Zaznacz element **Dodaj** i kliknij przycisk **Zapisz**.

    ![Strona projektanta modelu danych.](./media/er-quick-start3-add-data-model-field.png)

    > [!NOTE]
    > Pola **Etykieta** i **Opis** opisują cel nowego pola. Pola te można wypełnić w wielu językach. Aby uzyskać więcej informacji, zobacz [Projektuj wielojęzyczne raporty w raportowaniu elektronicznym](er-design-multilingual-reports.md).

10. Zamknij stronę **Projektant modelu danych**.

#### <a name="complete-a-custom-data-model-configuration"></a>Wykonaj konfigurację niestandardowego modelu danych

Musisz [ukończyć](general-electronic-reporting.md#component-versioning) pracę z wersją 50.1 konfiguracji niestandardowego modelu danych ER, aby udostępnić ją w taki sposób, aby można było dodać inne niestandardowe konfiguracje ER.

1. Otwórz **Administracja organizacji** \> **Elektroniczne raportowanie** \> **Konfiguracje**.
2. Na stronie **Konfiguracje** w drzewie konfiguracji w panelu po lewej wybierz pozycję **Model faktury**, a potem wybierz **Model faktury (Litware)**.
3. Na skróconej karcie **Wersje** wybierz **Zmień stan** \> **Zakończ**, a następnie wybierz **OK**.

Stan wersji 50.1 został zmieniony z **Wersji roboczej** na **Zakończone**, a wersja jest tylko do odczytu. Dodano nową wersję do edycji, 50.2, która ma stan **Wersja robocza**. Możesz skorzystać z tej wersji, aby wprowadzić dalsze zmiany w niestandardowej konfiguracji modelu danych ER.

![Wersja 50.1 została zakończona na stronie konfiguracje.](./media/er-quick-start3-completed-custom-model1.png)

### <a name="customize-the-model-mapping-configuration"></a>Dostosuj konfigurację modelu mapowania

Jako użytkownik w roli Deweloper raportowania elektronicznego możesz zaprojektować własne mapowanie modelu ER.

#### <a name="add-a-custom-model-mapping-configuration"></a>Dodaj niestandardową konfigurację mapowania modelu

1. Otwórz **Administracja organizacji** \> **Elektroniczne raportowanie** \> **Konfiguracje**.
2. Na stronie **Konfiguracje** w drzewie konfiguracji w panelu po lewej wybierz pozycję **Model faktur sprzedaży**, a potem wybierz **Mapowanie faktury dla odbiorcy**.
3. W okienku akcji wybierz **Utwórz konfigurację**.
4. W oknie dialogowym rozwijanym w **Nowym** polu wybierz opcję **Na podstawie nazwy: Mapowanie modelu faktury klienta, Microsoft** w celu wskazania, że nowe niestandardowe mapowanie modelu ER powinien być oparty na konfiguracji mapowania modelu ER.
5. W polu **Nazwa** wpisz **Mapowanie modelu faktury (Litware)**.
6. W polu **Model docelowy** wybierz opcję **Model faktury (Litware)**.

    > [!IMPORTANT]
    > Ten krok jest bardzo istotny. Jeśli go pominięto, nie będzie można skorzystać z niestandardowego modelu danych w skonfigurowanym mapowaniu modelu.

7. Wybierz **Stwórz konfiguracji**, aby dodać nową konfigurację ER.

![Dodanie niestandardowej konfiguracji mapowania modelu na stronie Konfiguracje.](./media/er-quick-start3-adding-custom-mapping.png)

#### <a name="configure-a-custom-model-mapping"></a>Skonfiguruj niestandardowe mapowanie modelu

Należy zmodyfikować Mapowanie niestandardowego modelu i określić, jak niestandardowe pole **FederalTaxID\_Litware** niestandardowego modelu danych ma być wypełniane danymi aplikacji w czasie wykonywania.

1. Otwórz **Administracja organizacji** \> **Elektroniczne raportowanie** \> **Konfiguracje**.
2. Na stronie **Konfiguracje** w drzewie konfiguracji w panelu po lewej wybierz pozycję **Model faktur sprzedaży** \> **Mapowanie faktury dla odbiorcy**, a potem wybierz **Mapowanie modelu faktur (Litware)**.
3. W okienku akcji wybierz opcję **Projektant**.
4. Na stronie **Mapowanie modelu do źródła danych** wybierz mapowanie **Faktura dla odbiorcy**.

    ![Mapowanie modelu do źródła danych.](./media/er-quick-start3-select-customer-mapping.png)

5. Wybierz opcję **Konstruktor**.
6. Na stronie **Projektant mapowania modeli** w okienku **Źródła danych** rozwiń Źródło danych **CustInvoiceJour**, które reprezentuje tabelę aplikacji **CustInvoiceJour**.
7. W obszarze **CustInvoiceJour** rozwiń pozycję **Relacje** w celu przejrzenia listy relacji typu wiele-do-jednego (N:1) dla tabeli **CustInvoiceJour**.
8. W obszarze **CustInvoiceJour** \> **Relacje** rozwiń węzeł **Odbiorcy (CustTable)**, aby uzyskać dostęp do pól i relacji między tabelami **Odbiorcy (CustTable)**.
9. Zaznacz pole źródła danych **FederalTaxID\_Custom**, które zostało zaimplementowane [wcześniej](#insert_custom_field).
10. W okienku **Modelu danych** rozwiń węzeł **Informacje o odbiorcy (odbiorca)** i zaznacz pole modelu danych **FederalTaxID\_Litware**.
11. Wybierz **Powiąż**.

    ![Modelowa strona projektanta mapowania.](./media/er-quick-start3-customize-model-mapping.gif)

12. Wybierz opcję **Zapisz**.
13. Zamknij stronę **Projektant mapowania modelu**.
14. Zamknij stronę **Mapowanie modelu do źródła danych**.

#### <a name="complete-a-custom-model-mapping-configuration"></a>Wykonaj niestandardową konfigurację mapowania modelu

Musisz [ukończyć](general-electronic-reporting.md#component-versioning) pracę z wersją 50.19.1 niestandardowej konfiguracji mapowania modelu ER, aby była dostępna do użytku.

1. Otwórz **Administracja organizacji** \> **Elektroniczne raportowanie** \> **Konfiguracje**.
2. Na stronie **Konfiguracje** w drzewie konfiguracji w panelu po lewej wybierz pozycję **Model faktur sprzedaży** \> **Mapowanie faktury dla odbiorcy**, a potem wybierz **Mapowanie modelu faktur (Litware)**.
3. Na skróconej karcie **Wersje** wybierz **Zmień stan** \> **Zakończ**, a następnie wybierz **OK**.

Stan wersji 50.19.1 został zmieniony z **Wersji roboczej** na **Zakończone**, a wersja jest tylko do odczytu. Dodano nową wersję do edycji, 50.19.2, która ma stan **Wersja robocza**. Możesz użyć tej wersji, aby wprowadzić dalsze zmiany w niestandardowej konfiguracji mapowania modelu ER.

![Wersja 50.19.1 została zakończona na stronie konfiguracje.](./media/er-quick-start3-completed-custom-mapping1.png)

> [!NOTE]
> Obsługiwany [cykl życia](general-electronic-reporting-manage-configuration-lifecycle.md) nie obejmuje czasu trwania zmian w bazie danych. Jeśli wyeksportujesz wersję 50.19.1 konfiguracji **Mapowania modelu faktury (Litware)** z bieżącej instancji Finance i spróbujesz zaimportować ją do innej instancji, która nie zawiera pola niestandardowego **FederalTaxID\_Custom** w tabeli **CustTable**, wystąpi wyjątek. Wyjątek będzie stanowił, że zaimportowana konfiguracja ER nie jest zgodna z metadanymi docelowej instancji Finance.

### <a name="customize-the-format-configuration"></a>Dostosuj konfigurację formatu

Użytkownik należący do roli konsultanta funkcjonalnego do raportowania elektronicznego może zaprojektować niestandardowy format ER.

#### <a name="add-a-custom-format-configuration"></a>Dodawanie niestandardowej konfiguracji formatu

1. Otwórz **Administracja organizacji** \> **Elektroniczne raportowanie** \> **Konfiguracje**.
2. Na stronie **Konfiguracje** w drzewie konfiguracji w panelu po lewej wybierz pozycję **Model faktur sprzedaży** \> **Faktura sprzedaży UBL**, a potem wybierz **Faktura sprzedaży PEPPOL**.
3. W okienku akcji wybierz **Utwórz konfigurację**.
4. W oknie dialogowym rozwijanym w **Nowym** polu wybierz opcję **Na podstawie nazwy: Model faktury sprzedaży Peppol, Microsoft** w celu wskazania, że nowy niestandardowy format ER powinien być oparty na konfiguracji formatu ER.
5. W polu **Nazwa** wpisz **Faktura sprzedaży PEPPOL (Litware)**.
6. W polu **Model danych** wybierz opcję **Model faktury (Litware)**, aby skorzystać z niestandardowego modelu danych i składników mapowania modeli.

    > [!NOTE]
    > Ten krok jest bardzo istotny. Jeśli go pominięto, nie będzie można skorzystać z niestandardowego modelu danych w skonfigurowanym formacie.

7. W polu **Definicja modelu** wybierz definicję źródłową **InvoiceCustomer**.
8. Wybierz **Stwórz konfiguracji**, aby dodać nową konfigurację ER.

![Dodanie niestandardowej konfiguracji formatu na stronie Konfiguracje.](./media/er-quick-start3-adding-custom-format.png)

Możesz teraz użyć projektanta operacji ER Operations do edycji wersji 11.2.2.1 **Faktura sprzedaży PEPPOL (Llitware)** w wersji **Roboczej** [stanu](general-electronic-reporting.md#component-versioning).

![Wersja 11.2.2.1 edytowalnej konfiguracji ER na stronie konfiguracje.](./media/er-quick-start3-added-custom-format.png)

#### <a name="configure-a-custom-format"></a>Skonfiguruj format niestandardowy

Należy zmodyfikować format niestandardowy, dodając nowy element formatu, który będzie pełnił wartość kodu federalnego identyfikacji podatkowej odbiorcy.

1. Otwórz **Administracja organizacji** \> **Elektroniczne raportowanie** \> **Konfiguracje**.
2. Na stronie **Konfiguracje** w drzewie konfiguracji w panelu po lewej wybierz pozycję **Model faktur sprzedaży** \> **Faktura sprzedaży UBL** \> **Faktura sprzedaży PEPPOL**, a potem wybierz **Faktura sprzedaży PEPPOL (Litware)**.
3. W okienku akcji wybierz opcję **Projektant**.
4. W drzewie formatu rozwiń pozycję **XMLHeader** \> **Invoice** \> **cac:AccountingCustomerParty** \> **cac:Party** \> **cac:PartyTaxScheme** \> **cac:TaxScheme**, a następnie wybierz **cbc:ID**.
5. Zaznacz element **Dodaj** i wybierz **XML** \> **Atrybut**.
6. W oknie dialogowym **Właściwość składnika** w polu **Nazwa** wpisz **FederalTaxID**.
7. Wybierz **OK**, aby dodać nowy element formatu w celu utworzenia nowego atrybutu XML **FederalTaxID** w generowanym pliku XML.
8. W formacie drzewa pod **XMLHeader** \> **Invoice** \> **cac:AccountingCustomerParty** \> **cac:Party** \> **cac:PartyTaxScheme** \> **cac:TaxScheme** \> **cbc:ID**, wybierz **FederalTaxID**.
9. Wybierz **Przenieś w górę**.

![Nowy element formatu na stronie Projektanta formatów.](./media/er-quick-start3-customized-format.png)

#### <a name="configure-a-custom-format-mapping"></a>Skonfiguruj mapowanie formatu niestandardowego

1. Na stronie **Projektant formatów** na karcie **Mapowanie** rozwiń źródło danych **Faktura** typu **Model**.
2. Na liście **Faktura** rozwiń węzeł **Informacje o odbiorcy (odbiorca)** i wybierz **FederalTaxID \_Litware**.
3. Wybierz **Powiąż**.

    ![Strona projektanta formatu.](./media/er-quick-start3-customized-format-mapping.png)

4. Wybierz źródło danych **Faktura** typu **Model**, a następnie wybierz opcję **Edytuj**.
5. W polu **Wersja** wybierz wersję **1** niestandardowego modelu danych, a następnie kliknij przycisk **OK**.
6. Wybierz opcję **Zapisz**.
7. Zamknij stronę **Projektowanie formuły**.

#### <a name="complete-a-custom-format-configuration"></a>Wykonaj konfigurację formatu niestandardowego

Musisz [ukończyć](general-electronic-reporting.md#component-versioning) pracę z wersją 11.2.2.1 niestandardowej konfiguracji formatu ER, aby była dostępna do użytku.

1. Otwórz **Administracja organizacji** \> **Elektroniczne raportowanie** \> **Konfiguracje**.
2. Na stronie **Konfiguracje** w drzewie konfiguracji w panelu po lewej wybierz pozycję **Model faktur sprzedaży** \> **Faktura sprzedaży UBL** \> **Faktura sprzedaży PEPPOL**, a potem wybierz **Faktura sprzedaży PEPPOL (Litware)**.
3. Na skróconej karcie **Wersje** wybierz **Zmień stan** \> **Zakończ**, a następnie wybierz **OK**.

Stan wersji 11.2.2.1 został zmieniony z **Wersji roboczej** na **Zakończone**, a wersja jest tylko do odczytu. Dodano nową wersję do edycji, 11.2.2.2, która ma stan **Wersja robocza**. Możesz użyć tej wersji, aby wprowadzić dalsze zmiany w konfiguracji niestandardowego formatu ER.

![Wersja 11.2.2.1 została zakończona na stronie konfiguracje.](./media/er-quick-start3-completed-custom-format1.png)

## <a name="configure-the-accounts-receivable-parameters-to-start-to-use-custom-er-configurations"></a><a name="ConfigureAR2"></a>Skonfiguruj Parametry rozrachunków z odbiorcami w celu rozpoczęcia używania niestandardowych konfiguracji ER

1. Wybierz kolejno pozycje **Rozrachunki z odbiorcami** \> **Ustawienia** \> **Parametry modułu rozrachunków z odbiorcami**.
2. Na karcie **Dokumenty elektroniczne** na skróconej karcie **Raportowania elektronicznego** w polu **Sprzedaż i Faktura niezależna** wybierz opcję **Faktura sprzedaży PEPPOL (Litware)**.
3. Wybierz opcję **Zapisz**.

![Strona Parametry rozrachunków z odbiorcami, zakładka Dokumenty elektroniczne, Skrócona karta Raportowanie elektroniczne.](./media/er-quick-start3-configure-ar2.png)

## <a name="update-a-customer-record-by-adding-a-federal-tax-identification-code"></a><a name="ConfigureCustomer2"></a>Aktualizowanie rekordu odbiorcy przez dodanie kodu identyfikacji podatkowej

1. Wybierz kolejno opcje **Rozrachunki z odbiorcami** \> **Odbiorcy** \> **Wszyscy odbiorcy**.
2. Na stronie **Wszyscy odbiorcy** wybierz łącze konto odbiorcy **DE-014**.
3. Na karcie skróconej **Ogólne**, w polu **Identyfikator podatku federalnego**, wprowadź **LITWARE-6789**.
4. Wybierz opcję **Zapisz**.

    ![Strona z danymi klienta DE-014.](./media/er-quick-start3-added-tax-id-value.png)

5. Zamknij stronę **Wszyscy odbiorcy**.

## <a name="process-a-customer-invoice-by-using-custom-er-configurations"></a><a name="ProcessInvoice2"></a>Przetwarzaj fakturę dla odbiorcy przy użyciu niestandardowych konfiguracji ER

### <a name="select-and-send-a-posted-invoice"></a>Wybierz i wyślij zaksięgowaną fakturę

1. Wybierz kolejno opcje **Rozrachunki z odbiorcami** \> **Faktury** \> **Wszystkie faktury niezależne**.
2. Na stronie **Faktura niezależna** wybierz wcześniej dodaną i zaksięgowaną fakturę.
3. W okienku akcji, w grupie **Dokumenty**, wybierz opcję **Wyślij** \> **Oryginał**.
4. Zamknij stronę **Faktura niezależna**.

### <a name="analyze-a-generated-e-invoice"></a>Analizowanie wygenerowanej faktury elektronicznej

1. Wybierz kolejno opcje **Administrowanie organizacją** \> **Raportowanie elektroniczne** \> **Zadania raportowania elektronicznego**.
2. Na stronie **Zadania raportowania elektronicznego** wybierz ostatni rekord zawierający opis zadania, aby **Przesłać plik XML e-faktury**.
3. Wybierz opcję **Pokazuj pliki**, aby uzyskać dostęp do listy wygenerowanych plików.
4. Wybierz opcję **Otwórz**, aby pobrać wygenerowany plik XML e-faktury.
5. Analizuj plik XML faktury elektronicznej. Należy zauważyć, że zgodnie z dostosowaniem, schemat podatkowy odbiorcy zawiera niestandardowy atrybut XML **FederalTaxID**, oprócz atrybutów XML **schemeID** i **schemeAgencyID**. Wartość tego nowego atrybutu XML jest określana przez **LITWARE-6789** federalnego podatku, który został wprowadzony dla zafakturowanego odbiorcy.

    ![Podgląd wygenerowanego pliku XML e-faktury z dostosowaniami.](./media/er-quick-start3-e-invoice2.png)

## <a name="import-the-latest-versions-of-standard-er-configurations"></a><a name="ImportERConfigurations2"></a>Importowanie ostatniej wersji standardowej konfiguracji ER

Aby zapewnić [aktualność](general-electronic-reporting-manage-configuration-lifecycle.md) zestawu standardowych konfiguracji ER w instancji Finance, należy importować ich nowe wersje, gdy tylko staną się dostępne w [repozytorium](general-electronic-reporting.md#Repository) ER skonfigurowanym dla tej instancji.

1. Wybierz kolejno opcje **Administrowanie organizacją** \> **Obszary robocze** \> **Raportowanie elektroniczne**.
2. Na stronie **Konfiguracje lokalizacji** w sekcji **Dostawcy konfiguracji** wybierz kafelek **Microsoft**, a następnie wybierz pozycję **Repozytoria**, aby wyświetlić listę repozytoriów dla dostawcy rozwiązania: Microsoft.
3. Na stronie **Repozytoria konfiguracji** zaznacz repozytorium typu **Globalne**, a następnie kliknij przycisk **Otwórz**. Jeśli zostanie wyświetlony monit o autoryzację połączenia z usługą Regulatory Configuration Service, postępuj zgodnie z instrukcjami autoryzacji.
4. Na stronie **Repozytorium konfiguracji** w drzewie konfiguracje w panelu po lewej wybierz format konfiguracji **Faktura sprzedaży PEPPOL**.
5. Na skróconej karcie **Wersje** wybierz opcję wersja **32.6.7** wybranej konfiguracji formatu ER, która została zwolniona do obsługi faktur elektronicznych dla odbiorców w formacie PEPPOL BIS 3. Aby uzyskać więcej informacji, zobacz [KB4490320](https://support.microsoft.com/help/4490320/an-update-for-european-union-to-support-export-of-customers-electronic).
6. Wybierz **Importuj**, aby pobrać wybraną wersję z Globalnego repozytorium do bieżącego wystąpienia Finance.

![Wersja 32.6.7 wybrana na stronie repozytorium konfiguracji.](./media/er-quick-start3-import-solution2.png)

Aby uzyskać informacje o tym, jak ten proces może być zautomatyzowany, należy zapoznać się z tematem [Importowanie zaktualizowanych wersji konfiguracji ER](er-download-updated-versions-global-repo.md).

### <a name="review-the-imported-er-configurations"></a>Przeglądanie zaimportowanych konfiguracji ER

1. Wybierz kolejno opcje **Administrowanie organizacją** \> **Obszary robocze** \> **Raportowanie elektroniczne**.
2. WNa stronie **Konfiguracje lokalizacji** w sekcji **Konfiguracje** wybierz kafelek **Konfigracje raportowanias**.
3. Rozwiń skróconą kartę **Składniki konfiguracji**.
4. W drzewie konfiguracji w lewym okienku rozwiń **Model faktury**. Należy zauważyć, że nazwa **Modelu faktury dla odbiorcy** została zmieniona na **Model faktury** w jednym z konfiguracji zaimportowanego modelu danych ER.
5. W drzewie konfiguracji w lewym okienku rozwiń **Mapowanie modelu faktury**. Należy zauważyć, że nazwa **Mapowanie modelu faktury dla odbiorcy** została zmieniona na **Mapowanie modelu faktury** w jednym z konfiguracji zaimportowanego mapowania modelu ER.
6. Rozwiń **Faktura sprzedaży UBL** \> **Faktura sprzedaży PEPPOL**.

Należy zauważyć, że oprócz wybranego formatu ER **Faktura sprzedaży PEPPOL** zostały zaimportowane ostatnie wersje innych wymaganych konfiguracji obiektów konfiguracji. Ponieważ nowe wersje konfiguracji programu ER są regularnie publikowane w repozytorium globalnym i usługi LCS, aby zachować odpowiednie rozwiązania ER zgodne z nowymi wymaganiami, zostaną zaimportowane najnowsze wersje wymaganej konfiguracji modelu danych i mapowania modeli.

Upewnij się, że w drzewie konfiguracji są w końcu dostępne następujące konfiguracje modułu ER:

- **Model faktury** Konfiguracja modelu danych ER:

    - Wersja 206 (lub późniejsze) zawiera wersję 24 (lub późniejsze) składnika ER modelu danych, który reprezentuje strukturę danych w domenie biznesowej fakturowania. Ta konfiguracja obiektu ER została zaimportowana jako element nadrzędny najnowszej wersji konfiguracji mapowania modelu ER **Mapowania modeli faktur**.

    ![Wersja 206 na stronie konfiguracje.](./media/er-quick-start3-imported-solution2b1.png)

- **Mapowanie modelu faktury** Konfiguracja mapowania modelu ER:

    - Wersja 206.132 (lub późniejsze) została zaimportowana jako Najnowsza implementacja w wersji 206 konfiguracji modelu danych ER faktur dla **Modelu faktury**. Zawiera kilka składników ER mapowania modelu, które opisują sposób wypełniania modelu danych danymi aplikacji w czasie wykonywania.

    ![Wersja 206.132 na stronie konfiguracje.](./media/er-quick-start3-imported-solution2b2.png)

- **Faktura sprzedaży UBL** Konfiguracja formatu ER:

    - Wersja 32.6 zawiera format i komponenty ER mapowania formatu. Składnik formatu określa układ raportu. Komponent mapowania formatu zawiera modelowe źródło danych i określa, w jaki sposób to źródło danych jest używane do wypełniania układu raportu w czasie wykonywania. Ten format ER został skonfigurowany do generowania faktur elektronicznych w formacie UBL. Został zaimportowany jako nadrzędny dla formatu ER **Faktura sprzedaży PEPPOL**, który został wybrany do importu.

- **Faktura sprzedaży PEPPOL** Konfiguracja formatu ER:

    - Wersja 32.6.7 zawiera format i odwzorowanie formatów komponentów ER, które zostały skonfigurowane do generowania e-faktur w formacie PEPPOL.

    ![Wersja 32.6.7 na stronie konfiguracje.](./media/er-quick-start3-imported-solution2b3.png)

## <a name="adopt-the-changes-to-the-new-standard-er-configurations-in-your-custom-er-configurations"></a><a name="RebaseCustomERConfigurations"></a>Zatwierdzić zmiany w nowych wersjach standardowych konfiguracji modelu ER w niestandardowych konfiguracjach ER

### <a name="adopt-your-custom-er-data-model"></a>Umożliwia przyjęcie niestandardowego modelu danych ER

1. Otwórz **Administracja organizacji** \> **Elektroniczne raportowanie** \> **Konfiguracje**.
2. Na stronie **Konfiguracje** w drzewie konfiguracji w panelu po lewej wybierz pozycję **Model faktury**, a potem wybierz **Model faktury (Litware)**.
3. Na skróconej karcie **Wersje** wybierz wersję roboczą **50.2** wybranej konfiguracji modelu danych ER wybierz **Zmień podstawę**.
4. W polu **Wersja docelowa** potwierdź wybór wersji **206** podstawowej konfiguracji modelu danych er, a następnie kliknij przycisk **OK**.

    Wersja robocza konfiguracji niestandardowego modelu danych ER zostanie przenumerowana od **50.2** do **206.2** w celu wskazania, że teraz zawiera dostosowania, które zostało scalone ze zmianami w najnowszej wersji (206) podstawowej konfiguracji modelu danych ER.

    > [!NOTE]
    > Akcja zmiany podstawy jest odwracalna. Aby anulować tę operację , należy wybrać wersję **50.1** w modelu **Model faktury (Litware)** na skróconej karcie **Wersje**, a następnie wybrać opcję **Pobierz tę wersję**. Następnie w wersji 206.2 zostanie ponownie numerowana na **50.2**, a zawartość wersji roboczej 50.2 będzie zgodna z treścią wersji 50.1.

5. Na skróconej karcie **Wersje** wybierz **Zmień stan** \> **Zakończ**, a następnie wybierz **OK**.

Stan wersji 206.2 został zmieniony z **Wersji roboczej** na **Zakończone**, a wersja jest tylko do odczytu. Dodano nową wersję do edycji, 206.3, która ma stan **Wersja robocza**. Możesz skorzystać z tej wersji, aby wprowadzić dalsze zmiany w niestandardowej konfiguracji modelu danych ER.

![Wersja 206.2 została zakończona na stronie konfiguracje.](./media/er-quick-start3-completed-custom-model2.png)

### <a name="adopt-your-custom-er-model-mapping"></a>Umożliwia przyjęcie niestandardowego mapowania modelu ER

1. Otwórz **Administracja organizacji** \> **Elektroniczne raportowanie** \> **Konfiguracje**.
2. Na stronie **Konfiguracje** w drzewie konfiguracji w panelu po lewej wybierz pozycję **Model faktury** \> **Mapowanie modelu faktury**, a potem wybierz **Mapowanie modelu faktur (Litware)**.
3. Na skróconej karcie **Wersje** wybierz wersję roboczą **50.19.2** wybranej konfiguracji mapowanie modelu ER wybierz **Zmień podstawę**.
4. W polu **Wersja docelowa** potwierdź wybór wersji **206.132** podstawowej konfiguracji mapowania modelu ER, a następnie kliknij przycisk **OK**.

    Wersja robocza konfiguracji niestandardowego mapowania modelu ER zostanie przenumerowana od **50.19.2** do **206.132.2** w celu wskazania, że teraz zawiera dostosowania, które zostało scalone ze zmianami w najnowszej wersji (206.132) podstawowej konfiguracji mapowania modelu ER.

    Zauważ, że wykryto kilka konfliktów zmiany podstawy. Należy teraz ręcznie rozwiązać te konflikty.

    ![Komunikat o konflikcie zmiany podstawy na stronie konfiguracje.](./media/er-quick-start3-rebase-conflicts-model-mapping1.png)

5. W okienku akcji wybierz opcję **Projektant**, a następnie na liście mapowań wybierz pozycję **Faktura dla odbiorcy**.
6. Dla każdego konfliktu zmiany wartości należy wybrać opcję **Zachowaj własną wartość**, ponieważ numer wersji niestandardowego modelu danych jest zachowany dla każdego składnika, który został wymieniony.

    ![Konflikty zmiany podstawy w konstruktorze mapowania modelu.](./media/er-quick-start3-rebase-conflicts-model-mapping2.png)

7. Wybierz **Zapisz** i zamknij stronę **Projektant mapowania modelu**.
8. Z listy mapowań wybierz opcję **Faktura projektu**.
9. Dla każdego konfliktu zmiany wartości należy wybrać opcję **Zachowaj własną wartość**, ponieważ numer wersji niestandardowego modelu danych jest zachowany dla każdego składnika, który został wymieniony.
10. Wybierz **Zapisz** i zamknij stronę **Mapowania modelu**.

    > [!NOTE]
    > Akcja zmiany podstawy jest odwracalna. Aby anulować tę operację , należy wybrać wersję **50.19.1** w mapowaniu modelu **Mapowanie modelu faktury (Litware)** na skróconej karcie **Wersje**, a następnie wybrać opcję **Pobierz tę wersję**. Następnie w wersji 206.132.2 zostanie ponownie numerowana na **50.19.2**, a zawartość wersji roboczej 50.19.2 będzie zgodna z treścią wersji 50.19.1.

11. Na skróconej karcie **Wersje** wybierz **Zmień stan** \> **Zakończ**, a następnie wybierz **OK**.

Stan wersji 206.132.2 został zmieniony z **Wersji roboczej** na **Zakończone**, a wersja jest tylko do odczytu. Dodano nową wersję do edycji, 206.132.3, która ma stan **Wersja robocza**. Możesz użyć tej wersji, aby wprowadzić dalsze zmiany w niestandardowej konfiguracji mapowania modelu ER.

![Wersja 206.132.2 została zakończona na stronie konfiguracje.](./media/er-quick-start3-completed-custom-mapping2.png)

### <a name="adopt-your-custom-er-format"></a>Umożliwia przyjęcie niestandardowego formatu ER

1. Otwórz **Administracja organizacji** \> **Elektroniczne raportowanie** \> **Konfiguracje**.
2. Na stronie **Konfiguracje** w drzewie konfiguracji w panelu po lewej wybierz pozycję **Model faktury** \> **Faktura sprzedaży UBL** \> **Faktura sprzedaży PEPPOL**, a potem wybierz **Faktura sprzedaży PEPPOL (Litware)**.
3. Na skróconej karcie **Wersje** wybierz wersję roboczą **11.2.2.2** wybranej konfiguracji formatu ER wybierz **Zmień podstawę**.
4. W polu wersja **Docelowa** potwierdź wybór wersji **32.6.7** podstawowej konfiguracji formatu ER, a następnie kliknij przycisk **OK**.

    Wersja robocza konfiguracji niestandardowego formatu ER zostanie przenumerowana od **11.2.2.2** do **32.6.7.2** w celu wskazania, że teraz zawiera dostosowania, które zostało scalone ze zmianami w najnowszej wersji (32.6.7) podstawowej konfiguracji formatu ER.

    Zauważ, że wykryto kilka konfliktów zmiany podstawy. Należy teraz ręcznie rozwiązać te konflikty.

5. W okienku akcji wybierz opcję **Projektant**.
6. Dla każdego konfliktu zmiany wartości należy wybrać opcję **Zachowaj własną wartość**, ponieważ numer wersji niestandardowego modelu danych jest zachowany dla każdego składnika, który został wymieniony.
7. Wybierz opcję **Zapisz**.
8. Na karcie **Mapowanie** wybierz źródło danych **Faktura** typu **Model**, a następnie wybierz opcję **Edytuj**.
9. W polu **Wersja** wybierz wersję **2** niestandardowego modelu danych, a następnie kliknij przycisk **OK**.
10. Wybierz opcję **Zapisz**.

    > [!NOTE]
    > Akcja zmiany podstawy jest odwracalna. Aby anulować tę operację , należy wybrać wersję **11.2.2.1** w formacie **Faktura sprzedaży PEPPOL (Litware)** na skróconej karcie **Wersje**, a następnie wybrać opcję **Pobierz tę wersję**. Następnie w wersji 32.6.7.2 zostanie ponownie numerowana na **11.2.2.2**, a zawartość wersji roboczej 11.2.2.2 będzie zgodna z treścią wersji 11.2.2.1.

11. Zamknij stronę **Projektowanie formuły**.
12. Na skróconej karcie **Wersje** wybierz **Zmień stan** \> **Zakończ**, a następnie wybierz **OK**.

Stan wersji 32.6.7.2 został zmieniony z **Wersji roboczej** na **Zakończone**, a wersja jest tylko do odczytu. Dodano nową wersję do edycji, 32.6.7.3, która ma stan **Wersja robocza**. Możesz użyć tej wersji, aby wprowadzić dalsze zmiany w konfiguracji niestandardowego formatu ER.

![Wersja 32.6.7.2 została zakończona na stronie konfiguracje.](./media/er-quick-start3-completed-custom-format2.png)

## <a name="process-a-customer-invoice-by-using-new-versions-of-the-custom-er-configurations"></a><a name="ProcessInvoice3"></a>Przetwarzaj fakturę dla klienta, korzystając z nowych wersji niestandardowych konfiguracji ER

### <a name="select-and-send-a-posted-invoice"></a>Wybierz i wyślij zaksięgowaną fakturę

1. Wybierz kolejno opcje **Rozrachunki z odbiorcami** \> **Faktury** \> **Wszystkie faktury niezależne**.
2. Na stronie **Faktura niezależna** wybierz wcześniej dodaną i zaksięgowaną fakturę.
3. W okienku akcji, w grupie **Dokumenty**, wybierz opcję **Wyślij** \> **Oryginał**.

    > [!NOTE] 
    > Ponieważ w systemie istnieje kilka wersji konfiguracji formatu ER **Faktura sprzedaży PEPPOL (Litware)** i żadna wersja nie ma [daty wejścia w życie](general-electronic-reporting.md#component-date-effectivity), najnowsza wersja jest używana do generowania e-faktury.

4. Zamknij stronę **Faktura niezależna**.

### <a name="analyze-a-generated-e-invoice"></a>Analizowanie wygenerowanej faktury elektronicznej

1. Wybierz kolejno opcje **Administrowanie organizacją** \> **Raportowanie elektroniczne** \> **Zadania raportowania elektronicznego**.
2. Na stronie **Zadania raportowania elektronicznego** wybierz najnowszy rekord zawierający opis zadania, aby **Przesłać plik XML e-faktury**.
3. Wybierz opcję **Pokazuj pliki**, aby uzyskać dostęp do listy wygenerowanych plików.
4. Wybierz opcję **Otwórz**, aby pobrać wygenerowany plik XML e-faktury.
5. Analizuj plik XML faktury elektronicznej. Należy zauważyć, że zgodnie z dostosowaniem, schemat podatkowy odbiorcy wciąż zawiera niestandardowy atrybut XML **FederalTaxID**, oprócz atrybutów XML **schemeID** i **schemeAgencyID**. Ponadto, ponieważ zmiany w nowej wersji formatu **Faktury sprzedaży UBL** zostały scalone z dostosowaniem, tekst elementu XML **cbc:CustomizationID** został zmieniony z `urn:www.cenbii.eu:transaction:biicoretrdm010:ver1.0:# urn:www.peppol.eu:bis:peppol5a:ver1.0` na `urn:cen.eu:en16931:2017#compliant#urn:fdc:peppol.eu:2017:poacc:billing:3.0`.

    ![Podgląd wygenerowanego pliku XML e-faktury z dostosowaniami.](./media/er-quick-start3-e-invoice3.png)

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Raportowanie elektroniczne — omówienie](general-electronic-reporting.md)
- [Pobieranie konfiguracji ER z usługi Lifecycle Services](download-electronic-reporting-configuration-lcs.md)
- [Pobieranie konfiguracji ER z globalnego repozytorium usługi Configuration service](er-download-configurations-global-repo.md)
- [Tworzenie faktury niezależnej](../../../finance/accounts-receivable/create-free-text-invoice-new.md)
- [Tworzenie pól niestandardowych i praca z nimi](../../fin-ops/get-started/user-defined-fields.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
