---
title: Projektowanie formatu raportowania elektronicznego w celu utrzymania wierszy razem na tej samej stronie programu Excel
description: W tym temacie wyjaśniono, jak zaprojektować format raportowania elektronicznego (ER), który utrzymuje wiersze razem na tej samej stronie programu Microsoft Excel.
author: NickSelin
ms.date: 02/28/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EROperationDesigner
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2022-03-01
ms.dyn365.ops.version: Version 10.0.26
ms.openlocfilehash: 711681ab38fb24b57a83f008f86a8261176aa5a5
ms.sourcegitcommit: b80692c3521dad346c9cbec8ceeb9612e4e07d64
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/05/2022
ms.locfileid: "8388596"
---
# <a name="design-an-er-format-to-keep-rows-together-on-the-same-excel-page"></a>Projektowanie formatu raportowania elektronicznego w celu utrzymania wierszy razem na tej samej stronie programu Excel

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

W tym temacie wyjaśniono, w jaki sposób użytkownik w roli Administrator systemu lub Funkcjonalny konsultant ds. raportowania elektronicznego może skonfigurować [Raportowanie elektroniczne (ER)](general-electronic-reporting.md) [format](er-overview-components.md#format-component), który generuje dokumenty wychodzące w programie Microsoft Excel i zarządzać stronicowaniem dokumentów, tak aby utworzone wiersze były zachowywane na tej samej stronie.

W tym przykładzie można zmodyfikować format ER firmy Microsoft używany do drukowania faktur wolnych w programie Excel. Modyfikacje umożliwiają zarządzanie stronicacją wygenerowanego raportu faktury free text, dzięki czemu wszystkie wiersze jednego wiersza faktury są przechowywane na tej samej stronie, o ile jest to możliwe.

Zadania przedstawione w tym temacie można wykonać w kontekście firmy **USMF**. Nie są wymagane umiejętności kodowania.

W tym przykładzie utworzysz wymagane [konfiguracje](general-electronic-reporting.md#Configuration) ER dla przykładowej firmy **Litware, Inc.**. Upewnij się, że dostawca konfiguracji dla przykładowej firmy **Litware, Inc.** (`http://www.litware.com`) jest wymieniony dla struktury ER i jest oznaczony jako **Aktywny**. Jeśli tego dostawcy konfiguracji nie ma na liście lub jeśli nie jest on oznaczony jako **aktywny**, wykonaj kroki opisane w temacie [Tworzenia dostawcy konfiguracji i zaznaczanie go jako aktywny](tasks/er-configuration-provider-mark-it-active-2016-11.md).

## <a name="enter-a-new-free-text-invoice"></a>Wpisz nową fakturę niezależną

1. Wykonaj czynności opisane w [Utwórz fakturę niezależną](../../../finance/accounts-receivable/create-free-text-invoice-new.md#create-a-free-text-invoice-1), aby dodać fakturę niezależną.

    1. Dodaj jedną linię do faktury.
    2. Dodaj pięć notatek do wiersza faktury.

    ![Przejrzyj uwagi dotyczące wiersza faktury na stronie Załączniki.](./media/er-keep-excel-rows-together-notes.png)

2. Wykonaj kroki w tece [Kopiuj wiersze,](../../../finance/accounts-receivable/create-free-text-invoice-new.md#copy-lines) aby utworzyć pięć dodatkowych wierszy faktury, które są kopiami wiersza faktury dodanego w poprzednim kroku.

    ![Przeglądanie wierszy faktury elektronicznej na stronie Faktura free text.](./media/er-keep-excel-rows-together-invoice.png)

## <a name="configure-the-er-framework"></a>Konfigurowanie struktury ER

Wykonaj kroki opisane w sekcji [Konfigurowanie platformy ER](er-quick-start2-customize-report.md#ConfigureFramework), aby skonfigurować minimalny zestaw parametrów ER. Tę konfigurację należy ukończyć przed rozpoczęciem korzystania z platformy ER do projektowania niestandardowej wersji standardowego formatu ER.

## <a name="import-the-standard-er-format-configuration"></a>Importowanie standardowej konfiguracji formatu ER

Postępuj zgodnie z instrukcjami w [Importuj standardową konfigurację formatu ER](er-quick-start2-customize-report.md#ImportERSolution1), aby dodać standardowe konfiguracje ER do bieżącego wystąpienia Dynamics 365 Finance. Na przykład zaimportuj wersję **252.116** konfiguracji formatu **Faktura niezależna (Excel)**. Podstawowa wersja **252** podstawowej konfiguracji **Model faktury** jest automatycznie importowana z repozytorium wraz z wymaganą konfiguracją **Mapowanie modelu faktury**.

## <a name="set-up-print-management-to-use-the-standard-er-format"></a>Konfigurowanie zarządzania drukowaniem w celu używania standardowego formatu ER

Wykonaj czynności opisane w [Konfigurowanie zarządzania drukowaniem](er-embed-images-header-footer-excel-reports.md#ConfigurePrintManagement1), aby skonfigurować zarządzanie drukowaniem dla modułu **Należności** tak, aby do drukowania faktur niezależnych był używany standardowy format ER.

## <a name="configure-a-format-destination-for-the-standard-er-format"></a>Konfigurowanie miejsca docelowego formatu standardowego formatu ER

Postępuj zgodnie z instrukcjami w [Konfigurowanie miejsca docelowego formatu](er-quick-start1-new-solution.md#ConfigureDestination) podglądu na ekranie, aby skonfigurować [Ekranowe](er-destination-type-screen.md) miejsce docelowe ER standardowego formatu ER, tak aby wygenerowane raporty były konwertowane do formatu PDF i przeglądane na nowej karcie przeglądarki.

## <a name="print-a-free-text-invoice-by-using-the-standard-er-format"></a>Wydrukuj fakturę niezależną, korzystając ze standardowego formatu ER

1. Aby wygenerować raport faktury elektronicznej w formacie programu Excel dla dodanej faktury, należy wykonać czynności opisane w temacie [Drukowanie faktury elektronicznej](er-embed-images-header-footer-excel-reports.md#ProcessInvoice1).
2. Pobierz wygenerowany skoroszyt programu Excel i przejrzyj go w aplikacji pulpitu programu Excel.

    Zwróć uwagę, że szósty wiersz faktury rozpoczyna się na pierwszej stronie raportu i kontynuuje na drugiej stronie. Ostatnia notatka pojawia się na drugiej stronie i nie oznacza, że należy ona do szóstego wiersza faktury. Z tego względu podział strony w środku zawartości wiersza faktury powoduje, że ten dokument jest trudne do odczytania.

    ![Przeglądanie stronicowania wygenerowanej faktury elektronicznej w aplikacji pulpitu programu Excel.](./media/er-keep-excel-rows-together-invoice1.gif)

Pozostałe procedury w tym temacie pokazują, jak można dostrajać standardowy format raportu ER w celu poprawienia wyglądu i czytelności raportu o fakturze, chowając całą zawartość jednego wiersza faktury na tej samej stronie.

## <a name="create-a-custom-format"></a>Tworzenie niestandardowego formatu

Postępuj zgodnie z instrukcjami w [Tworzenie niestandardowego formatu](er-embed-images-header-footer-excel-reports.md#DeriveProvidedFormat), aby uzyskać format z zaimportowanego formatu ER i utwórz **Niestandardową fakturę tekstową (Excel)** Konfigurację ER, która jest dostępna do edycji i modyfikacji.

## <a name="edit-the-custom-format"></a>Edytuj format niestandardowy

1. Aby otworzyć pochodny [format ER do](er-embed-images-header-footer-excel-reports.md#ConfigureDerivedFormat) edycji w konstruktorze formatu ER, należy wykonać kroki w temacie Tworzenie niestandardowego formatu.
2. Na stronie **Projektant formatów** w drzewie komponentów formatu w lewym okienku rozwiń **Faktura niezależna \> Arkusz \> InvoiceLines** i wybierz składnik **InvoiceLines_Values**.
3. Na karcie **Format** ustaw opcję **Trzymaj wiersze razem** o wartości **Tak**.

    ![Ustawienie opcji Zachowaj wiersze razem dla edytowalnego formatu ER na stronie projektanta formatów.](./media/er-keep-excel-rows-together-format.png)

4. Wybierz przycisk **Zapisz** i zamknij stronę.

## <a name="mark-the-custom-format-as-runnable"></a>Oznaczanie formatu niestandardowego jako wykonywalnego

Aby uruchomić zmodyfikowaną wersję niestandardowego formatu ER, wykonaj kroki w temacie [Oznacz format niestandardowy jako uruchamialny](er-embed-images-header-footer-excel-reports.md#MarkFormatRunnable).

## <a name="set-up-print-management-to-use-the-custom-er-format"></a>Skonfiguruj zarządzanie drukowaniem, aby używać niestandardowego formatu ER

Wykonaj czynności opisane w [Konfigurowanie zarządzania drukowaniem](er-embed-images-header-footer-excel-reports.md#ConfigurePrintManagement2), aby skonfigurować zarządzanie drukowaniem dla modułu **Należności** tak, aby do drukowania faktur niezależnych był używany niestandardowy format ER.

## <a name="configure-a-format-destination-for-the-custom-er-format"></a>Konfigurowanie miejsca docelowego formatu niestandardowego formatu ER

Postępuj zgodnie z instrukcjami w [Konfigurowanie miejsca docelowego formatu](er-quick-start1-new-solution.md#ConfigureDestination) podglądu na ekranie, aby skonfigurować **Ekranowe** miejsce docelowe ER niestandardowego formatu ER, tak aby wygenerowane raporty były konwertowane do formatu PDF i przeglądane na nowej karcie przeglądarki.

## <a name="print-a-free-text-invoice-by-using-the-custom-er-format"></a>Wydrukuj fakturę niezależną, korzystając z niestandardowego formatu ER

1. Wykonaj czynności opisane w [Drukuj fakturę niezależną](er-embed-images-header-footer-excel-reports.md#ProcessInvoice2), aby użyć niestandardowego formatu ER do wygenerowania raportu z fakturą niezależną w formacie Excel dla dodanego faktura.
2. Pobierz wygenerowany skoroszyt programu Excel i przejrzyj go w aplikacji pulpitu programu Excel.

    Należy zauważyć, że szósty wiersz faktury rozpoczyna się na drugiej stronie, a wszystkie wiersze programu Excel reprezentujące ten wiersz faktury pojawiają się razem na tej stronie.

    ![Przeglądanie zaktualizowanej paginacji wygenerowanej faktury niezależnej w aplikacji klasycznej Excel.](./media/er-keep-excel-rows-together-invoice2.gif)

## <a name="additional-resources"></a>Dodatkowe zasoby

[Projektowanie konfiguracji projektu w celu generowania dokumentów wychodzących w formacie programu Excel](er-fillable-excel.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
