---
title: Reguły mapowania rozwiązania Invoice Capture
description: Ten artykuł zawiera informacje o konfiguracji reguł mapowania w rozwiązaniu Invoice Capture.
author: sunfzam
ms.date: 09/25/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: VendorInvoiceWorkspace, VendInvoiceInfoListPage
audience: Application User
ms.reviewer: twheeloc
ms.custom:
- "13971"
- intro-internal
ms.assetid: 0ec4dbc0-2eeb-423b-8592-4b5d37e559d3
ms.search.region: Global
ms.author: zezhangzhao
ms.search.validFrom: 2022-09-28
ms.dyn365.ops.version: ''
ms.openlocfilehash: cd0d06f7fd3ed946756e975d0706687c2d4acc93
ms.sourcegitcommit: 40c80a617b903c2b26e44b41147e0021c5cb680d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2022
ms.locfileid: "9691237"
---
# <a name="invoice-capture-solution-mapping-rules"></a>Reguły mapowania rozwiązania Invoice Capture

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Reguły mapowania używają podstawowych danych głównych z aplikacji Microsoft Dynamics 365 Finance lub platformy planowania zasobów przedsiębiorstwa (ERP). Po skonfigurowaniu reguł mapowania są pobierane informacje wymagane do tworzenia faktur od dostawcy w aplikacji Finance. Gdy używane są reguły mapowania, urzędnik ds. rozrachunków z dostawcami będzie sprawdzać stan zamiast ręcznie wypełniać wszystkie brakujące wartości pól.

Istnieją cztery typy reguł mapowania:

- Firma
- Konto dostawcy
- Pozycja
- Typ wydatków

## <a name="manage-mapping-rules-by-using-the-app"></a>Zarządzanie regułami mapowania za pomocą aplikacji

Aby zarządzać regułami mapowania za pomocą aplikacji, wybierz pozycję **Ustawienia**. Karta **Konfiguracja reguły mapowania** zawiera cztery opcje:

- Firma 
- Konto dostawcy 
- Mapowanie pozycji 
- Typ wydatków

Możesz na przykład wybrać opcję **Reguły mapowania osoby prawnej**. Kod osoby prawnej będzie identyfikowany przy użyciu nazwy firmy, adresu i numeru identyfikacji podatkowej. W przypadku reguły o nazwie **LE-USPM**, jeśli nazwa firmy zawiera tekst „Contoso Robotics USA”, kodem osoby prawnej będzie **USPM**.

Na stronie są wszystkie aktywne reguły mapowania. Aby wyświetlić nieaktywne reguły mapowania, wybierz pozycję **Aktywne reguły mapowania osoby prawnej**, a następnie wybierz pozycję **Nieaktywne reguły mapowania osoby prawnej**.

Dla reguł mapowania dostępne są następujące działania.

### <a name="create-a-mapping-rule"></a>Tworzenie reguły mapowania

Tworząc regułę mapowania, można użyć dwóch metod:

- Wybierz pozycję **Nowy**, aby utworzyć nową regułę mapowania. Następnie wprowadź informacje dotyczące reguły mapowania. Wartość **Nazwa reguły** powinna być unikatowa dla każdego typu reguły mapowania.
- W przypadku wybrania istniejącej reguły mapowania przycisk **Kopiuj** staje się dostępny. Wybierz go, a następnie w wyświetlonym oknie dialogowym wybierz przycisk **OK**. Reguła mapowania jest tworzona przez duplikowanie wybranej reguły.

### <a name="edit-a-mapping-rule"></a>Edytowanie reguły mapowania

Aby edytować regułę mapowania, wybierz pole i zmień wartość.

### <a name="activatedeactivate-mapping-rules"></a>Aktywowanie/dezaktywowanie reguł mapowania

Aby dezaktywować jedną lub więcej reguł mapowania, wybierz je na stronie **Aktywne reguły mapowania**, a następnie wybierz opcję **Dezaktywuj**. Reguły są przenoszone ze strony **Aktywne reguły mapowania** na stronę **Nieaktywne reguły mapowania**.

Podobnie, aby aktywować reguły mapowania, wybierz je na stronie **Nieaktywne reguły mapowania**, a następnie wybierz opcję **Aktywuj**.

### <a name="remove-mapping-rules"></a>Usuwanie reguł mapowania

Aby usunąć reguły mapowania, wybierz je, a następnie wybierz przycisk **Usuń**.

### <a name="check-for-conflicts"></a>Sprawdzanie, czy wystąpiły konflikty

Jeśli dwie reguły mapowania mają takie same wartości **Osoba prawna** i **Konto dostawcy**, ale inne wartości **Nazwa pozycji**, zostanie wykryty konflikt, a reguła mapowania nie zostanie utworzona lub zaktualizowana.

## <a name="importexport-mapping-rules-from-excel"></a>Importowanie/eksportowanie reguł mapowania z programu Excel

Dodatku programu Excel można używać do zarządzania regułami w partii. Dostępne są następujące opcje:

- Pobierz szablon programu Excel.
- Eksportuj do programu Excel.
- Importuj z programu Excel.

### <a name="download-an-excel-template"></a>Pobieranie szablonu programu Excel

Aby pobrać szablon programu Excel, wybierz pozycję **Pobierz szablon**. Następnie wybierz pola do uwzględnienia w szablonie.

### <a name="export-to-excel"></a>Eksportuj do programu Excel

Eksportować można na dwa sposoby:

- Wybierz pozycję **Otwórz w programie Excel Online**, aby otworzyć plik w programie Excel. Następnie możesz edytować plik w trybie online. Po zakończeniu wybierz przycisk **Zapisz**. Wszystkie zmiany zostaną zapisane na stronie **Reguła mapowania**.
- Wybierz pozycję **Pobierz arkusz**, aby pobrać plik programu Excel zawierający reguły mapowania. Następnie możesz edytować plik. Po zakończeniu wybierz pozycję **Importuj z programu Excel**, aby przekazać zaktualizowany arkusz.

### <a name="import-from-excel"></a>Importuj z programu Excel

1. Wybierz pozycję **Importuj z programu Excel** w celu zaimportowania danych z pliku XLSX. Można także importować z plików wartości oddzielanych przecinkami (CSV) i XML. Przed rozpoczęciem importowania należy określić, czy są dozwolone duplikaty.
2. Wybierz pozycję **Przejrzyj mapowanie**, aby przejrzeć mapowanie atrybutów i ustalić, czy jest ono poprawne. Możesz modyfikować relację mapowania.
3. Po zakończeniu wybierz pozycję **Zakończ import**.
4. Możesz wybrać pozycję **Śledź postęp**, aby śledzić postęp procesu importu.

    Stan importu jest aktualizowany ze stanu **Zakończ** na **Analizowanie**, następnie na **Przekształcanie**, a na koniec na **Zakończono**.

Po zakończeniu procesu importowania są wyświetlane statystyki dotyczące sukcesów, częściowych niepowodzeń, błędów i łącznej liczby przetworzonych operacji.
