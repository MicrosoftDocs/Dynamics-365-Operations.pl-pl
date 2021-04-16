---
title: Aktualizowanie struktury szablonu dokumentu biznesowego
description: W tym temacie opisano sposób aktualizacji struktury szablonu dokumentu biznesowego przy użyciu funkcji zarządzania dokumentami biznesowymi.
author: NickSelin
ms.date: 11/19/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERBDWorkspace, ERBDParameters, ERBDTemplateEditor
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-12-01
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: 203c9f0990051c1618660959dad0e184add68ffa
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5750491"
---
# <a name="update-the-structure-of-a-business-document-template"></a>Aktualizowanie struktury szablonu dokumentu biznesowego 

[!include[banner](../includes/banner.md)]

W okienku **Struktura szablonów** w Edytorze szablonów [Zarządzanie dokumentami biznesowymi](er-business-document-management.md) można zmodyfikować szablon dokumentu biznesowego, [dodając nowe pola](er-bdm-add-field-to-excel-template.md) do szablonu w systemie Microsoft Excel. Struktura szablonu jest następnie automatycznie aktualizowana w systemie Dynamics 365 Finance, tak aby odzwierciedlała zmiany wprowadzone w okienku **Struktura szablonu**.

Można również zmodyfikować szablon, korzystając z funkcji online systemu Office 365. Można na przykład dodać do edytowalnego arkusza nowy nazwany element, taki jak obraz lub kształt. W takim przypadku struktura szablonu nie jest automatycznie aktualizowana w module Finance, a dodany element nie jest wyświetlany w okienku **Struktura szablonów**. Aby ręcznie zaktualizować strukturę szablonów w module Finance, należy wybrać opcję **Aktualizuj strukturę** na stronie Edytor szablonów.

Zapoznaj się z poniższym przykładem, aby dowiedzieć się więcej.

## <a name="example-update-the-structure-of-a-business-document-template"></a>Przykład: aktualizowanie struktury szablonu dokumentu biznesowego

W tym przykładzie pokazano, jak administrator systemu może zaktualizować strukturę szablonu dokumentu biznesowego w module Finance po zmodyfikowaniu szablonu w systemie Office Online. W poniższych sekcjach objaśniono wymagane kroki.

### <a name="prepare-a-business-document-template-for-editing"></a>Przygotuj szablon dokumentu biznesowego do edycji

W tym celu należy wykonać poniższe procedury z sekcji [Omówienie zarządzania dokumentami biznesowymi](er-business-document-management.md).

1. [Konfigurowanie parametrów modułu ER](er-business-document-management.md#configure-er-parameters)
2. [Importowanie rozwiązań ER](er-business-document-management.md#import-er-solutions)
3. [Włącz zarządzanie dokumentem biznesowym](er-business-document-management.md#enable-business-document-management)
4. [Konfigurowanie parametrów](er-business-document-management.md#configure-parameters)

### <a name="edit-a-business-document-template"></a>Edytowanie szablonu dokumentów biznesowych

1. W obszarze roboczym **Zarządzanie dokumentami biznesowymi** wybierz **Nowy dokument**.
2. Na stronie **Utwórz nowy szablon** wybierz szablon **Faktura niezależna (przykład ER)(Excel)**.
3. Wybierz opcję **Utwórz dokument**.
4. W polu **Tytuł** wpisz **FTI sample Litware**.
5. Wybierz **OK**, aby utworzyć nowy szablon.

    > [!NOTE]
    > Jeśli jeszcze nie zalogowano się do systemu Office Online, nastąpi [przekierowanie do strony logowania Office 365](er-business-document-management.md#frequently-asked-questions). Aby powrócić do środowiska Finance, wybierz przycisk **Wstecz** w przeglądarce.

    Nowy szablon zostanie otwarty do edycji w osadzonym formancie Excel Online na stronie Edytor szablonów.

[![Używanie obszaru roboczego zarządzanie dokumentami biznesowymi w celu rozpoczęcia edycji szablonu dokumentu biznesowego](./media/er-bdm-update-structure1.gif)](./media/er-bdm-update-structure1.gif)

### <a name="review-the-current-structure-of-the-editable-template"></a>Przejrzyj bieżącą strukturę edytowalnego szablonu

1. W formancie Excel Online, na wstążce na karcie **Widok** w grupie **Pokaż** wybierz **Linie siatki**.
2. W szablonie edytowalnym zaznacz prostokąt nad tytułem szablonu. Ten prostokąt jest obrazem o nazwie **rptHeaderCompLogo**.
3. Jeśli okienko **Struktura szablonu** jest ukryte, wybierz **Pokaż strukturę**.
4. W okienku **Struktura szablonu** rozwiń węzeł **Raport \> Faktura \> rptHeader \> rptHeaderPart1**.
5. Należy zauważyć, że w strukturze szablonów w module Finance element **rptHeaderCompLogo** jest przedstawiany jako element podrzędny elementu **Raport \> Faktura \> rptHeader faktury \> rptHeaderPart1**.

[![Przeglądanie bieżącej struktury edytowalnego szablonu za pomocą obszaru roboczego zarządzania dokumentami biznesowymi](./media/er-bdm-update-structure2.gif)](./media/er-bdm-update-structure2.gif)

### <a name="update-the-structure-of-a-business-document-template-by-deleting-a-picture"></a>Aktualizowanie struktury szablonu dokumentu biznesowego przez usunięcie obrazu

1. W formancie Excel Online w szablonie edytowalnym wybierz obraz **rptHeaderCompLogo**.
2. Aby usunąć zaznaczony obraz z szablonu edytowalnego, należy wykonać jedną z następujących czynności:

    - Naciśnij klawisz **Delete**.
    - Zaznacz obraz i przytrzymaj go (lub kliknij prawym przyciskiem myszy), a następnie wybierz opcję **Wytnij**.

    > [!NOTE]
    > **Element rptHeaderCompLogo** nadal znajduje się w strukturze szablonów w module Finance, nawet jeśli tego obrazu nie ma już w szablonie programu Excel.

3. Wybierz opcję **Aktualizuj strukturę**, aby zsynchronizować strukturę szablonu edytowalnego w programie Excel i module Finance.
4. W okienku **Struktura szablonu** rozwiń węzeł **Raport \> Faktura \> rptHeader \> rptHeaderPart1**.
5. Elementu **rptHeaderCompLogo** nie będzie już w strukturze szablonów w module Finance.

[![Używanie obszaru roboczego zarządzanie dokumentami biznesowymi w celu usuwania obrazu z szablonu dokumentu biznesowego](./media/er-bdm-update-structure3.gif)](./media/er-bdm-update-structure3.gif)

### <a name="update-the-structure-of-a-business-document-template-by-adding-a-picture"></a>Aktualizowanie struktury szablonu dokumentu biznesowego przez dodawanie obrazu

1. W formancie Excel Online, na wstążce na karcie **Wstawianie** w grupie **Ilustracje** wybierz **Obraz**.
2. Wybierz opcję **Wybierz plik**, przejdź do obrazu, który chcesz dodać, zaznacz go, a następnie kliknij przycisk **OK**.
3. Wybierz **Wstaw**.
4. Przenieś nowy obraz w odpowiednie miejsce. Domyślnie program Excel nazywa obraz. Na przykład może to być obraz o nazwie **Obraz 2**.
5. Wybierz opcję **Aktualizuj strukturę**, aby zsynchronizować strukturę szablonu edytowalnego w programie Excel i module Finance.
6. W okienku **Struktura szablonu** rozwiń węzeł **Raport \> Faktura \> rptHeader \> rptHeaderPart1**.
7. Nowy obraz jest teraz elementem struktury szablonów w module Finance.

[![Używanie obszaru roboczego zarządzanie dokumentami biznesowymi w celu dodawania obrazu do dokumentu biznesowego](./media/er-bdm-update-structure4.gif)](./media/er-bdm-update-structure4.gif)

## <a name="related-links"></a>Powiązane łącza

[Omówienie raportowania elektronicznego (ER)](general-electronic-reporting.md)

[Omówienie zarządzania dokumentami biznesowymi](er-business-document-management.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]