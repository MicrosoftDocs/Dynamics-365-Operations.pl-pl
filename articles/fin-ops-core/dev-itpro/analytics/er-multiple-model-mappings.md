---
title: Zarządzanie wieloma mapowaniami pochodnymi dla pojedynczego poziomu głównego modelu
description: W tym temacie wyjaśniono, jak zarządzać kilkoma mapowaniami pochodnymi skonfigurowanymi dla pojedynczego poziomu głównego modelu.
author: NickSelin
manager: AnnBe
ms.date: 01/04/2021
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERSolutionTable, ERModelMappingTable
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3116fe98f499637b3bc7f243ed1b5094853caa7e
ms.sourcegitcommit: 7cfe8931dd454e811a691f5118a4ecae7ba4b478
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/04/2021
ms.locfileid: "4826116"
---
# <a name="manage-several-derived-mappings-for-a-single-model-root"></a>Zarządzanie wieloma mapowaniami pochodnymi dla pojedynczego poziomu głównego modelu

[!include [banner](../includes/banner.md)]

Składnik [modelu](general-electronic-reporting.md#data-model-and-model-mapping-components) danych [Raportowanie elektroniczne (ER)](general-electronic-reporting.md) jest używany w każdym skonfigurowanym [formacie](general-electronic-reporting.md#FormatComponentOutbound) raportowania elektronicznego jako źródło danych do generowania dokumentów wychodzących. Aby opisać pojedynczą domenę biznesową, skonfiguruj składnik modelu danych, który ma wiele definicji głównych. 

Każda definicja główna umożliwia reprezentowanie danych tej domeny w sposób najlepiej dopasowany do konkretnych celów raportowania. Dla każdej definicji głównej można skonfigurować składnik [modelu mapowania](general-electronic-reporting.md#data-model-and-model-mapping-components) ER jako specyficzną dla aplikacji Microsoft Dynamics 365 Finance implementację modelu danych. W ten sposób można opisać sposób wypełniania modelu danych w czasie wykonywania.

Składniki mapowania modelu raportowania elektronicznego mogą znajdować się w [konfiguracjach](general-electronic-reporting.md#Configuration) modeli danych ER i konfiguracjach mapowania modelu ER. Konfiguracja pojedynczego raportowania elektronicznego może zawierać wiele składników mapowania, z których każdy jest skonfigurowany dla jednej definicji głównej. Alternatywnie pojedyncza konfiguracja raportowania elektronicznego może zawierać tylko jeden składnik mapowania skonfigurowany dla jednej definicji głównej.

Wielu dostawców konfiguracji może oferować konfiguracje mapowania modelu ER dla tego samego modelu danych ER. Te konfiguracje mapowania modeli mogą zawierać składniki mapowania dla różnych definicji głównych. Mapowanie modelu może być używane dla jednej definicji głównej oferowanej przez jednego [dostawcę](general-electronic-reporting.md#Provider) albo dla innej definicji głównej oferowanej przez innego dostawcę.

Procedury w tym temacie zawierają informacje dotyczące zarządzania wieloma konfiguracjami mapowania modelu ER dla modelu danych ER, jeśli zawierają różne składniki mapowania modelu skonfigurowane dla tej samej definicji głównej. 

Aby wykonać procedury opisane w tym temacie, użytkownik musi mieć przypisaną rolę Administrator systemu lub Deweloper raportowania elektronicznego.

Wszystkie poniższe procedury można wykonać dla firmy USMF. Nie są wymagane umiejętności kodowania.

## <a name="configure-the-er-framework"></a>Konfigurowanie struktury ER

Jako użytkownik w roli dewelopera raportowania elektronicznego, musisz [skonfigurować minimalny zestaw](er-quick-start2-customize-report.md#ConfigureFramework) parametrów ER, zanim będzie można zacząć używać struktury ER do generowania dokumentów biznesowych.

## <a name="import-the-standard-er-format-configurations"></a>Importowanie standardowej konfiguracji formatu ER

Aby dodać standardowe konfiguracje modułu ER do bieżącego wystąpienia aplikacji Finance, należy zaimportować je z repozytorium ER, które zostało skonfigurowane dla tego wystąpienia. Wykonaj kroki opisane w temacie [Pobieranie konfiguracji ER z globalnego repozytorium usługi Configuration service](er-download-configurations-global-repo.md), aby zaimportować konfiguracje formatu raportowania elektronicznego:

- **Faktura niezależna (Excel)**, wersja 220.106
- **Faktura projektu (Excel)**, wersja 226.27

## <a name="review-the-imported-er-configurations"></a>Przeglądanie zaimportowanych konfiguracji ER

1. Wybierz kolejno opcje **Administrowanie organizacją** \> **Obszary robocze** \> **Raportowanie elektroniczne**.
2. WNa stronie **Konfiguracje lokalizacji** w sekcji **Konfiguracje** wybierz kafelek **Konfigracje raportowanias**.
3. Na stronie **Konfiguracje** w drzewie konfiguracji w panelu po lewej wybierz pozycję **Model faktury**.

    ![Przeglądanie zaimportowane konfiguracje na stronie Konfiguracje](./media/er-multiple-model-mappings-image1.png)

4. Przejrzyj format **faktury niezależnej (Excel)**:

    1. W drzewie konfiguracji w lewym okienku wybierz pozycję **Faktura niezależna (Excel)**.
    2. W okienku akcji wybierz opcję **Projektant**.
    3. Na stronie **Projektant formatów** na karcie **Mapowanie** na liście źródeł danych wybierz pozycję **Model**.
    4. Wybierz pozycję **Widok**.
    
       Bieżący format ER jest skonfigurowany do używania definicji głównej **InvoiceCustomer** **modelu faktury**. Po uruchomieniu tego formatu i wywołaniu źródła danych **Model** mapowanie modelu skonfigurowane dla definicji głównej **InvoiceCustomer** będzie używane do uzyskiwania dostępu do danych aplikacji i wypełniania modelu danych.

        ![Przeglądanie źródła danych modelu na stronie projektanta formatów](./media/er-multiple-model-mappings-image2.png)

    6. Zamknij stronę **Projektowanie formuły**.

5. Przejrzyj zawartość konfiguracji **Mapowanie modelu faktury**:

    1. W drzewie konfiguracji w lewym okienku wybierz opcję **Mapowanie modelu faktury**.
    2. W okienku akcji wybierz opcję **Projektant**.
    3. Na stronie **mapowania modelu na źródło danych** zauważ, że bieżąca konfiguracja mapowania modelu ER zawiera kilka składników mapowania modelu:

        + Mapowanie modelu **faktury dla odbiorcy** jest skonfigurowane dla definicji głównej **InvoiceCustomer** **modelu faktury**. Dlatego podczas uruchamiania formatu ER **Faktura niezależna (Excel)** można wybrać mapowanie modelu **Faktura dla odbiorcy** dotyczące tej konfiguracji ER, aby uzyskać dostęp do danych aplikacji i wypełnić model danych.
        + Mapowanie modelu **Faktura projektu** jest skonfigurowane dla definicji głównej **InvoiceProject** **modelu faktury**. Dlatego podczas uruchamiania formatu ER **Faktura projektu (Excel)** można wybrać mapowanie modelu **Faktura projektu** dotyczące tej konfiguracji ER, aby uzyskać dostęp do danych aplikacji i wypełnić model danych.

        ![Mapowanie modelu faktury na stronie Mapowanie modelu do źródła danych](./media/er-multiple-model-mappings-image3.png)

    4. Zamknij stronę **Mapowanie modelu do źródła danych**.
    5. Na skróconej karcie **Wersje** wybierz pozycję **Usuń**, aby usunąć wszystkie wersje tej konfiguracji ER nowsze niż wersja 240.175.

6. Przejrzyj zawartość konfiguracji **Mapowanie modelu faktury projektu (RDP)**:

    1. W drzewie konfiguracji w lewym okienku wybierz opcję **Mapowanie modelu faktury projektu (RDP)**.
    2. W okienku akcji wybierz opcję **Projektant**.
    3. Na stronie **mapowania modelu do źródła danych** zauważ, że bieżąca konfiguracja mapowania modelu ER zawiera mapowanie modelu **InvoiceProject**, a to mapowanie modelu jest skonfigurowane dla definicji głównej **InvoiceProject** dla **modelu faktury**. Podczas uruchamiania formatu ER **Faktura projektu (Excel)** wybierz mapowanie modelu **InvoiceProject** dotyczące tej konfiguracji ER, aby uzyskać dostęp do danych aplikacji i wypełnić model danych.

        ![Mapowanie modelu faktury projektu na stronie Mapowanie modelu do źródła danych](./media/er-multiple-model-mappings-image4.png)

    4. Zamknij stronę **Mapowanie modelu do źródła danych**.
    5. Na skróconej karcie **Wersje** wybierz pozycję **Usuń**, aby usunąć wszystkie wersje tej konfiguracji ER nowsze niż wersja 226.35.

## <a name="customize-the-imported-er-configurations"></a>Dostosowywanie zaimportowanych konfiguracji ER

W tej sekcji opisano sposób [dostosowywania](er-quick-start3-customize-report.md#customize-the-model-mapping-configuration) mapowań modeli dostarczanych przez Microsoft. Na przykład dostosowywanie może być wymagane do zaimplementowania logiki niestandardowej lub dodania brakujących powiązań.

### <a name="customize-the-invoice-model-mapping-configuration"></a>Dostosowywanie konfiguracji modelu mapowania faktury

1. Na stronie **Konfiguracje** w drzewie konfiguracji w panelu po lewej wybierz pozycję **Mapowanie modelu faktury**.
2. W okienku akcji wybierz **Utwórz konfigurację**.
3. W oknie dialogowym listy rozwijanej **Tworzenie konfiguracji** w polu **Nowy** wybierz opcję **Pochodne od nazwy: mapowanie modelu faktury, Microsoft**.
4. W polu **Nazwa** wpisz **Mapowanie modelu faktury, Litware**.
5. Wybierz **Utwórz konfigurację**.
6. [Oznacz](er-quick-start2-customize-report.md#MarkFormatRunnable) [wersję roboczą](general-electronic-reporting.md#component-versioning) pochodnego mapowania jako dostępną w czasie wykonywania:

    1. W okienku akcji na karcie **Konfiguracje** w grupie **Ustawienia zaawansowane** wybierz opcję **Parametry użytkownika**.
    2. W oknie dialogowym **Parametry użytkownika** określ opcję **Ustawienia uruchamiania** na **Tak**, a następnie wybierz **OK**.
    3. W razie potrzeby wybierz opcję **Edytuj**, aby strona była możliwa do edycji.
    4. W przypadku konfiguracji **Mapowanie modelu faktury, Litware**, która jest aktualnie wybrana w drzewie konfiguracji, ustaw opcję **Uruchom w wersji roboczej** na **Tak**.

7. W okienku akcji wybierz opcję **Projektant**, aby przejrzeć mapowania modeli tej konfiguracji.

    ![Przeglądanie mapowań modelu faktury na stronie Mapowanie modelu do źródła danych](./media/er-multiple-model-mappings-image5.png)

    > [!TIP]
    > Aby skonfigurować logikę niestandardową, można w projektancie otworzyć dowolne składniki mapowania modelu ER dla tej konfiguracji ER. Aby uzyskać więcej informacji, zobacz temat [Dostosowywanie konfiguracji mapowania modelu](er-quick-start3-customize-report.md#customize-the-model-mapping-configuration).

8. Zamknij stronę **Mapowanie modelu do źródła danych**.

Masz teraz konfiguracje **Mapowanie modelu faktury** i **Mapowanie modelu faktury, Litware**, z których każda ma mapowanie modelu skonfigurowane dla definicji głównej **InvoiceCustomer**. Jawnie przypisz jedno z mapowań modelu jako domyślne mapowanie modelu, które jest używane w dowolnym formacie raportu elektronicznego, takim jak **Faktura niezależna (Excel)**, zawierający źródło danych modelu, które ma definicję główną **InvoiceCustomer**. W przeciwnym razie podczas uruchamiania, edytowania lub weryfikowania jednego z formatów ER zgłaszany jest następujący wyjątek, aby poinformować Cię, że nie przypisano jawnie żadnego mapowania modelu domyślnego:
 
> Istnieje więcej niż jedno mapowanie modelu dla modelu danych „\<model name\> (\<root descriptor\>)” w konfiguracjach \<configuration names separated by commas\>. Ustaw jedną z konfiguracji jako domyślną.

![Otwieranie formatu do edycji na stronie Konfiguracje](./media/er-multiple-model-mappings-image6.gif)

### <a name="customize-the-project-invoice-model-mapping-rdp-configuration"></a>Dostosowywanie konfiguracji mapowania modelu faktury projektu (RDP)

1. Na stronie **Konfiguracje** w drzewie konfiguracji w panelu po lewej wybierz pozycję **Mapowanie modelu faktury projektu (RDP)**.
2. W okienku akcji wybierz **Utwórz konfigurację**.
3. W oknie dialogowym listy rozwijanej **Tworzenie konfiguracji** w polu **Nowy** wybierz opcję **Pochodne od nazwy: mapowanie modelu faktury projektu (RDP), Microsoft**.
4. W polu **Nazwa** wpisz **Mapowanie modelu faktury projektu, Litware**.
5. Wybierz **Utwórz konfigurację**.
6. W przypadku konfiguracji **Mapowanie modelu faktury projektu, Litware**, która jest aktualnie wybrana w drzewie konfiguracji, ustaw opcję **Uruchom w wersji roboczej** na **Tak**.
7. W okienku akcji wybierz opcję **Projektant**, aby przejrzeć mapowania modeli tej konfiguracji.

    ![Przeglądanie dostosowanych mapowań modelu faktury projektu na stronie Mapowanie modelu do źródła danych](./media/er-multiple-model-mappings-image7.png)

8. Zamknij stronę **Mapowanie modelu do źródła danych**.

Masz teraz konfiguracje **Mapowanie modelu faktury**, **Mapowanie modelu faktury projektu (RDP)** i **Mapowanie modelu projektu faktury, Litware**. Każda z tych konfiguracji ma skonfigurowane mapowanie modelu dla definicji głównej **InvoiceProject**. Jawnie przypisz jedno z mapowań modelu jako domyślne mapowanie modelu używane przez dowolne formaty ER. Na przykład użyj formatu **Faktura projektu (Excel)** zawierającego źródło danych modelu, które ma definicję główną **InvoiceProject**. W przeciwnym razie podczas uruchamiania lub edytowania jednego z formatów ER zgłaszany jest następujący wyjątek, aby poinformować Cię, że nie przypisano jawnie żadnego mapowania modelu domyślnego.

## <a name="select-the-derived-invoice-model-mapping-litware-configuration-as-the-configuration-that-contains-default-model-mappings"></a>Wybierz konfigurację Litware pochodnego mapowania modelu faktury jako konfigurację zawierającą domyślne mapowania modeli

1. Na stronie **Konfiguracje** w drzewie konfiguracji w panelu po lewej wybierz pozycję **Mapowanie modelu faktury, Litware**.
2. Ustaw opcję **domyślnego mapowania modelu** jako **Tak**.

    ![Ustawianie mapowania modelu jako domyślnego mapowania modelu na stronie Konfiguracje](./media/er-multiple-model-mappings-image8.png)

    Z powodu tego ustawienia mapowanie modelu **Kopia faktury dla odbiorcy** jest używane podczas uruchamiania **faktury niezależnej (Excel)** lub podczas jej edytowania lub weryfikowania. Mapowanie modelu **Faktura dla klienta** z konfiguracji **Mapowanie modelu faktury** jest ignorowane.

    Teraz można otworzyć format **Faktura niezależna (Excel)** do przeglądu w projektancie formatów.

## <a name="select-the-derived-project-invoice-model-mapping-litware-configuration-as-the-configuration-that-contains-default-model-mappings"></a>Wybierz konfigurację Litware pochodnego mapowania modelu faktury projektu jako konfigurację zawierającą domyślne mapowania modeli

1. Na stronie **Konfiguracje** w drzewie konfiguracji w panelu po lewej wybierz pozycję **Mapowanie modelu faktury projektu, Litware**.
2. Ustaw opcję **domyślnego mapowania modelu** jako **Tak**.

    W tym przypadku, w przeciwieństwie do przypadku opisanego w konfiguracji **Mapowanie modelu faktury, Litware** w poprzedniej sekcji, nie można rozpocząć korzystania z mapowania modelu **Kopia faktury InvoiceProject** z konfiguracji **Mapowanie modelu faktury projektu, Litware**. Dwie konfiguracje zawierające mapowanie modelu dla definicji głównej **InvoiceProject** są obecnie oznaczone jako konfiguracja domyślna. W związku z tym mają jednakowy priorytet ich używania. Aby rozwiązać ten problem, wykonaj pozostałe kroki tej procedury.

3. W drzewie konfiguracji w lewym okienku wybierz opcję **Mapowanie modelu faktury, Litware**.
4. W okienku akcji wybierz opcję **Projektant**.
5. Na stronie **mapowania modelu do źródła danych** wybierz pozycję **Edytuj**, aby w razie potrzeby edytować stronę.
6. Wybierz mapowanie modelu **Kopia faktury projektu**, a następnie zaznacz pole wyboru **Usunięte**.

    ![Ustawianie mapowania modelu jako wirtualnie usuniętego na stronie mapowania modelu do źródła danych](./media/er-multiple-model-mappings-image9.png)

    Z powodu tego ustawienia konfiguracja **Mapowanie modelu faktury, Litware** będzie traktowana tak, jakby nie zawierała mapowania modelu dla definicji głównej **InvoiceProject**. Mapowanie modelu **Kopia InvoiceProject** jest wydawane domyślnie. Konfiguracja **Mapowanie modelu faktury projektu, Litware**, która zawiera to mapowanie modelu, jest oznaczana jako konfiguracja domyślna. Ponieważ jest ona oznaczona jako domyślna, ma wyższy priorytet niż mapowanie modelu **InvoiceProject** z konfiguracji **Mapowanie modelu faktury projektu (RDP)**.

## <a name="other-considerations"></a>Inne uwagi

Mapowanie modelu **Kopia faktury projektu** konfiguracji **Mapowanie modelu faktury projektu, Litware** zostało zaprojektowane do używania źródła danych **ReportDataProvider**. Źródło danych jest częścią typu *Obiekt*, który odwołuje się do klasy aplikacji **PsaProjInvoiceDP**. Ta klasa jest zaimplementowana jako dostawca danych dla raportu usług SQL Server Reporting Services (SSRS) faktury projektu w ramach struktury zarządzania drukowaniem. Wybierz to źródło danych jako [punkt integracji](er-apis-app10-0-11.md#api-to-run-a-format-mapping-for-the-generation-of-outbound-documents) ER. To ustawienie jest uwzględnione w bieżącej implementacji ER dla raportów zarządzania drukowaniem. Aby uzyskać więcej szczegółów, przejrzyj kod źródłowy klasy aplikacji **ERPrintMgmtDataProviderReport**. W czasie wykonywania przypisanie źródła danych **ReportDataProvider** jako punktu integracji mapowania modelu wymusza, że aplikacji Finance traktuje składnik mapowania jako wyższy priorytet niż składnik mapowania **InvoiceProject** z konfiguracji **Mapowanie modelu faktury projektu (RDP)**.

## <a name="see-also"></a>Informacje dodatkowe

- [Zarządzanie mapowaniem modelu modułu Raportowanie elektroniczne w oddzielnych konfiguracjach modułu Raportowanie elektroniczne](./tasks/er-manage-model-mapping-configurations-july-2017.md)
- [Konfigurowanie mapowań modelu raportowania elektronicznego w zależności od kraju](er-country-dependent-model-mapping.md)
- [Zmiany interfejsu API struktury raportowania elektronicznego](er-apis-app10-0-11.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]