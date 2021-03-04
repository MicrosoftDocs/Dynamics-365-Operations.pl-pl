---
title: Dodawanie nowych pól do szablonu dokumentu biznesowego w formularzu Microsoft Excel
description: Ten temat zawiera informacje dotyczące sposobu dodawania nowych pól do szablonu w Microsoft Excel za pomocą funkcji zarządzania dokumentami biznesowymi systemu.
author: NickSelin
manager: AnnBe
ms.date: 11/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERBDWorkspace, ERBDParameters, ERBDTemplateEditor
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-10-01
ms.dyn365.ops.version: 10.0.7
ms.openlocfilehash: fcfbcb021b192cef75d59b0db1796e994f3dc27d
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2020
ms.locfileid: "4681383"
---
# <a name="add-new-fields-to-a-business-document-template-in-microsoft-excel"></a>Dodawanie nowych pól do szablonu dokumentu biznesowego w formularzu Microsoft Excel

[!include[banner](../includes/banner.md)]

Nowe pola można dodawać do szablonu używanego do generowania dokumentów biznesowych w format Microsoft Excel. Pola te można dodawać jako symbole zastępcze używane do wypełniania wygenerowanych dokumentów informacjami wymaganymi z poziomu aplikacji. Dla każdego dodawanego pola można również określić powiązanie ze źródłami danych, aby określić, jakie dane aplikacji będą wprowadzane do pola w przypadku użycia szablonu do generowania dokumentów biznesowych.

Wykonaj przykład z tego tematu, aby dowiedzieć się więcej na temat tej funkcji. W tym przykładzie przedstawiono sposób aktualizacji szablonu w celu wypełniania pól w wygenerowanych formularzach faktur niezależnych.

## <a name="configure-business-document-management-to-edit-templates"></a>konfigurowanie szablonów przy użyciu funkcji zarządzania dokumentami biznesowymi

Ponieważ zarządzanie dokumentami biznesowymi (BDM) jest zbudowane na podstawie [Omówienie raportowania elektronicznego (ER)](general-electronic-reporting.md), należy skonfigurować wymagane parametry modułu er i BDM, aby można było rozpocząć pracę z BDM.

1.  Zaloguj się do wystąpienia rozwiązania Microsoft Dynamics 365 Finance jako administrator systemu.
2.  W temacie [Omówienie zarządzania dokumentami biznesowymi](er-business-document-management.md) należy wykonać następujące czynności:

    1.  Konfigurowanie parametrów modułu ER.
    2.  Włącz BDM.

Teraz można rozpocząć używanie BDM do edytowania szablonów dokumentów biznesowych.

## <a name="import-er-solutions-that-contain-a-template"></a>Importuj rozwiązania ER, które zawierają szablon

W przykładzie tej procedury użyto oficjalnie opublikowanego rozwiązania ER. Należy zaimportować konfiguracje klasy ER tego rozwiązania do bieżącego wystąpienia Finance.

Konfiguracja **Darmowy tekst faktury (Excel)** tego rozwiązania zawiera szablon dokumentu biznesowego w formacie programu Excel, który można edytować za pomocą BDM. Zaimportuj najnowszą wersję tej konfiguracji formatu na podstawie Microsoft Dynamics usługi Lifecycle Service (usługi LCS). Odpowiednie konfiguracje mapowań modelu danych i modelu ER zostaną zaimportowane automatycznie.

Aby uzyskać więcej informacji jak importować konfiguracji ER, zapoznaj się z [Zarządzanie cyklem życia konfiguracji Raportowania elektronicznego](general-electronic-reporting-manage-configuration-lifecycle.md).

![Strona biblioteki udostępnionych elementów zawartości LCS](./media/BDM-AddFldExcel-LCS.png)

### <a name="edit-the-er-solution-template"></a>Edytuj szablon rozwiązania ER

1.  Zaloguj się jako użytkownik z dostępem do strony obszaru roboczego **zarządzania dokumentami biznesowymi**.
2.  Otwórz obszaru roboczy **zarządzania dokumentami biznesowymi**.

    ![Strona obszaru roboczego zarządzania dokumentami biznesowymi](./media/BDM-AddFldExcel-Workspace.png)

3.  W siatce wybierz szablon **Darmowy tekst faktury (Excel)**.
4.  W prawym okienku wybierz opcję **nowy szablon**, aby utworzyć nowy szablon oparty na wybranym szablonie.
5.  W polu **tytuł** wprowadź **Darmowy tekst faktury (Excel) contoso** jako tytuł nowego szablonu.
6.  Wybierz **OK**, aby potwierdzić rozpoczęcie procesu edycji.

Pojawia się strona Edytor szablonów BDM. Można wykorzystać Microsoft 365 do edytowania wybranego szablonu w trybie online w osadzonym formancie.

![Strona edytora szablonów BDM](./media/BDM-AddFldExcel-EditableTemplate.png)

### <a name="add-the-label-for-a-new-field-to-the-template"></a>Dodaj etykietę nowego pola do szablonu

1.  Na stronie Edytor szablonów BDM na wstążce programu Excel na karcie **Widok** zaznacz pola wyboru **nagłówki i linie siatki** dla edytowalnego szablonu programu Excel.

    ![Zaznaczone pola wyboru nagłówki i linie siatki](./media/BDM-AddFldExcel-EditableTemplate2.png)

2.  Zaznacz komórki **E8:F8**.
3.  Na wstążce programu Excel na karcie **Widok główny** wybierz opcję **Scal & Scentruj**, aby scalić wybrane komórki do nowej, scalonej komórki **E8:F8**.
4.  W Scalonej komórce **E8:F8** wprowadź adres **URL**.
5.  Wybierz scaloną komórkę **E7:F7**, wybierz opcję **Malarz formatów**, a następnie wybierz scaloną komórkę **E8:F8**, aby ją sformatować w ten sam sposób,co scalona komórka **E7:F7**.

    ![Pole nowej etykiety dodanej do szablonu](./media/BDM-AddFldExcel-EditableTemplate3.png)

### <a name="format-the-template-to-reserve-space-for-a-new-field"></a>Sformatuj szablon, aby zarezerwować miejsce dla nowego pola

1.  Na stronie Edytor szablonów BDM wybierz scaloną komórkę **G8:H8**.
2.  Na wstążce programu Excel na karcie **Widok główny** wybierz opcję **Scal & Scentruj**, aby scalić wybrane komórki do nowej, scalonej komórki **G8:H8**.
3.  Wybierz scaloną komórkę **G7:H7**, wybierz opcję **Malarz formatów**, a następnie wybierz scaloną komórkę **G8:H8**, aby ją sformatować w ten sam sposób,co scalona komórka **G7:H7**.

    ![Miejsce zarezerwowane dla nowego pola](./media/BDM-AddFldExcel-EditableTemplate4.png)

4.  W polu **nazwa** wybierz opcję **companyinfo**.

    **Companyinfo** zakres bieżącego szablonu programu Excel zawiera wszystkie pola, które są używane do wypełniania nagłówka wygenerowanego raportu ze szczegółami bieżącej firmy jako strony sprzedającej.

    ![Wybrano zakres CompanyInfo](./media/BDM-AddFldExcel-SelectCompanyInfoRange.png)

### <a name="add-a-new-field-to-the-template"></a>Dodaj nowego pola do szablonu

1.  Na stronie **Edytor szablonów BDM** w okienku akcji wybierz opcję **show format**.
2.  W okienku **struktura szablonów** wybierz pozycję **Dodaj**.

    > [!NOTE]
    > Musisz zmienić sekcję szablonu, która ma być używana jako nowe pole. Ta korekta została już dokonana przez formatowanie Scalonej komórki **G8:H8**.

    ![Dodawa nowego pola do szablonu](./media/BDM-AddFldExcel-AddCell.png)

3.  Wybierz **Excel\Cell**, aby dodać nowe pole jako komórkę w szablonie.

    Jeśli chcesz dodać zakres do szablonu, możesz wybrać **Excel\Zakres**. Wprowadzony zakres może zawierać wiele komórek. Możesz dodać te komórki później.
    
    Zauważ, że składnik szablonu **CompanyInfo** jest automatycznie wybierany w panelu **struktura szablonów**, ponieważ jest to najbardziej odpowiedni składnik nadrzędny w strukturze bieżącego szablonu dla dodawanego pola.
    
4.  W polu **zakres programu Excel** wprowadź **CompanyURL_Value**.
5.  Kliknij przycisk **OK**.

    ![Do struktury szablonu dodano CompanyURL_Value pole](./media/BDM-AddFldExcel-EditableTemplate5.png)

6.  W okienku **struktura szablonów** wybierz przycisk wielokropka (...), a następnie wybierz opcję **pokazuj powiązania**.

    ![Pokaż wybrane powiązania](./media/BDM-AddFldExcel-ShowBindings.png)

    W okienku **struktury szablonów** są teraz wyświetlane źródła danych dostępne w odpowiednim formacie modułu ER.

7.  Wybierz **CompanyInfo_Value** jako pole, które chcesz powiązać ze źródłem danych źródłowego formatu ER.
8.  W sekcji **źródła danych** w panelu **Struktura szablonów** rozwiń gałąź **Model \> InvoiceBase \> CompanyInfo**.
9.  W obszarze **CompanyInfo** wybierz pozycję **WebsiteURL**.

    ![Wybrane elementy WebsiteURL](./media/BDM-AddFldExcel-BindURL.png)

10. Wybierz **Powiąż**.
11. W okienku **struktura szablonu** wybierz opcję **Zapisz**, a następnie zamknij stronę Edytor szablonów BDM.

W obszarze roboczym **zarządzanie dokumentami biznesowymi** na karcie **szablon** w prawym okienku jest wyświetlany zaktualizowany szablon. W siatce Zwróć uwagę, że pole **stan** edytowanego szablonu zostało zmienione na wartość **wersja robocza**, a pole **Poprawka** nie jest już puste. Zmiany te wskazują, że proces edycji tego szablonu został rozpoczęty.

![Szablon edytowany w obszarze roboczym zarządzanie dokumentami biznesowymi](./media/BDM-AddFldExcel-Workspace2.png)

## <a name="review-company-settings"></a>Przejrzyj ustawienia firmy

1.  Wybierz kolejno opcje **Administrowanie organizacją \> Organizacje \> Firmy**.
2.  Na skróconej karcie **informacji kontaktowych** sprawdź, czy adres URL firmy został wprowadzony.

![Adres URL firmy wprowadzony na stronie firmy](./media/BDM-AddFldExcel-CompanyInfo.png)

## <a name="generate-business-documents-to-test-the-updated-template"></a>Generowanie dokumentów biznesowych w celu przetestowania zaktualizowanego szablonu

1.  W aplikacji Zmień firmę na **USMF** i przejdź do **Rozrachunki z odbiorcami \> Faktury \> Wszystkie faktury niezależne**.
2.  Wybierz fakturę **FTI-00000002**, a następnie wybierz opcję **Zarządzanie drukowaniem**.
3.  W lewym okienku rozwiń węzeł **Moduł — Rozrachunki z odbiorcami \> Dokumenty \> Faktura niezależna**.
4.  Pod **Faktura niezależna** wybierz **Dokument oryginalny**, aby określić zakres faktur do przetwarzania.
5.  W prawym okienku w polu **Format raportu** wybierz szablon **Darmowy tekst faktury (Excel) Contoso** dla określonego poziomu dokumentu.

    ![Wybrany szablon Contoso — Faktura niezależna (Excel)](./media/BDM-AddFldExcel-PrintMngtSetting.png)

6.  Naciśnij klawisz **Esc**, aby zamknąć bieżącą stronę.
7.  Wybierz opcje **Drukuj \> Wybrane**.
8.  Pobierz wygenerowany dokument i otwórz go w programie Excel.

    ![Faktura niezależna w Excel](./media/BDM-AddFldExcel-PreviewReport.png)

Zmodyfikowany szablon jest używany do generowania raportu faktury niezależnej dla wybranego towaru. Aby przeanalizować wpływ, jaki na ten raport mają zmiany wprowadzone w szablonie, uruchom raport w jednej sesji aplikacji natychmiast po zmianie szablonu w innej sesji aplikacji.

## <a name="related-links"></a>Powiązane linki

[Omówienie raportowania elektronicznego (RE)](general-electronic-reporting.md)

[Omówienie zarządzania dokumentami biznesowymi](er-business-document-management.md)

[Projektowanie konfiguracji do generowania raportów w formacie OPENXML](tasks/er-design-reports-openxml-2016-11.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]