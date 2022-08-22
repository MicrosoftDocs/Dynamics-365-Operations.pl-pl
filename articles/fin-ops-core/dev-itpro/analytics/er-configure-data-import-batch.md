---
title: Importuj dane z ręcznie wybranych plików w trybie wsadowym
description: Ten artykuł wyjaśnia, jak importować dane z ręcznie wybranych plików w trybie wsadowym.
author: kfend
ms.date: 01/07/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2022-01-01
ms.dyn365.ops.version: Release 10.0.25
ms.custom: 220314
ms.assetid: ''
ms.search.form: ERSolutionTable, ERImportFormatSourceTable, ERWorkspace
ms.openlocfilehash: 21a2ab5f0eb07dda92baf9cc04ee36caeff8b4ec
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9288237"
---
# <a name="import-data-from-manually-selected-files-in-batch-mode"></a>Importuj dane z ręcznie wybranych plików w trybie wsadowym

[!include[banner](../includes/banner.md)]
[!include[banner](../includes/preview-banner.md)]

Aby użyć struktury [Raportowania elektronicznego (ER)](general-electronic-reporting.md) do importowania danych z ręcznie wybranych plików przychodzących w trybie wsadowym, skonfiguruj [format](er-overview-components.md#format-component) ER, który obsługuje import. Następnie uruchom [odwzorowanie modelu](er-overview-components.md#model-mapping-component) typu **Do miejsca docelowego**, które używa tego formatu jako źródła danych. Aby zaimportować dane, przejdź do pliku, który chcesz zaimportować, i wybierz go ręcznie. 

Nowa możliwość ER, która wspiera import danych w trybie wsadowym, pozwala na skonfigurowanie tego procesu jako nienadzorowanego. Możesz użyć konfiguracji ER do wykonania importu danych poprzez zaplanowanie nowego zadania wsadowego z interfejsu użytkownika (UI) ER.

Ten artykuł wyjaśnia, jak dokończyć import danych z ręcznie wybranego pliku w trybie wsadowym. W przykładach użyto transakcji dostawcy jako danych biznesowych. Kroki z tych przykładów mogą być wykonane w firmie **USMF**. Nie są wymagane umiejętności kodowania.

## <a name="prerequisites"></a>Wymagania wstępne

Aby wykonać przykłady opisane w tym artykule, musisz mieć następujące uprawnienia dostępu:

- Jedna z poniższych ról:

    - Deweloper raportowania elektronicznego
    - Konsultant funkcjonalny raportowania elektronicznego
    - Administrator systemu

- Konfiguracje formatu i modelu raportowania elektronicznego na potrzeby płatności wynikających z deklaracji 1099

### <a name="create-the-required-er-configurations"></a>Tworzenie wymaganych konfiguracji ER

Aby stworzyć wymagane konfiguracje ER i uzyskać inne warunki wstępne, wykonaj jeden z poniższych kroków:

- Odtwórz przewodniki po zadaniach **ER Importowanie danych z pliku programu Microsoft Excel**, które wchodzą w skład procesu biznesowego **7.5.4.3 Nabywanie/opracowywanie składników usług/rozwiązań informatycznych (10677)**. Te wskazówki zadania przeprowadzą Cię przez proces projektowania i używania konfiguracji ER do aktywnego importowania transakcji dostawcy z plików programu Microsoft Excel. Aby uzyskać więcej informacji, zobacz [Analizowanie dokumentów przychodzących w formacie Excel](parse-incoming-documents-excel.md).
- Uzupełnij przykłady w pliku [Konfiguruj import danych z SharePoint](er-configure-data-import-sharepoint.md). Te przykłady przeprowadzą cię przez proces projektowania i używania konfiguracji ER, które interaktywnie importują transakcje dostawców z plików Excel, które są przechowywane w folderze SharePoint.

### <a name="download-the-required-er-configurations"></a>Pobierz wymagane konfiguracje ER

1. Pobierz poniższe konfiguracje ER i zapisz je lokalnie.

    | Opis zawartości | Plik |
    |---------------------|------|
    | **Model 1099 Payments** Konfiguracja modelu danych ER Model płatności | [1099model.xml](https://download.microsoft.com/download/b/d/9/bd9e8373-d558-4ab8-aa9b-31981adc97ea/1099model.xml) |
    | **Do importowania transakcji sprzedawców (Excel)** Konfiguracja formatu ER | [1099format-import-from-excel.xml](https://download.microsoft.com/download/b/3/8/b38faf0a-fbaf-4e9e-84c2-dedae7464880/1099format-import-from-excel.xml) |

2. Za pomocą opcji [Wyładuj z pliku XML](er-defer-sequence-element.md#import-the-sample-er-configurations) zaimportuj pobrane konfiguracje ER do wystąpienia Dynamics 365 Finance w następującej kolejności:

    1. Konfiguracja modelu danych ER
    2. ER format konfiguracji

### <a name="download-the-required-excel-files"></a>Pobierz wymagane pliki Excel

- Pobierz poniższy przykładowy zestaw danych i zapisz go lokalnie.

    | Opis zawartości | Plik |
    |---------------------|------|
    | Przychodzący plik **1099import-data.xlsx**, który zawiera przykładowe dane do importu | [1099import-data.xlsx](https://download.microsoft.com/download/f/f/4/ff4dbce9-8364-4391-adee-877945ff01f7/1099import-data.xlsx) |

### <a name="review-the-prerequisites"></a>Zapoznaj się z warunkami wstępnymi

1. Otwórz **Administracja organizacji** \> **Elektroniczne raportowanie** \> **Konfiguracje**.
2. Na stronie **Konfiguracje** przejrzyj przygotowane rozwiązanie rej. do importu danych w trybie wsadowym.
3. Przejrzyj konfigurację formatu **Do importowania transakcji sprzedawców (Excel)**.

    - Komponent format tej konfiguracji jest przeznaczony do przetwarzania przychodzącego pliku Excel.
    - Komponent odwzorowania modelu w tej konfiguracji jest używany do wypełnienia modelu danych bazowych za pomocą danych z sparsowanego pliku Excela.

    ![Konfiguracja formatu ER dla importu danych w trybie wsadowym z UI ER.](./media/er-configure-data-import-batch-configurations-1.png)

4. Sprawdź model konfigurację modelu danych **Model 1099 Payments**.

    - Komponent modelu w tej konfiguracji reprezentuje strukturę modelu danych, który jest używany do przekazywania danych pomiędzy działającymi komponentami ER.
    - Komponent odwzorowania modelu w tej konfiguracji jest używany do pobierania danych z wykonanego komponentu formatu, a następnie do aktualizacji tabel aplikacji.

    ![Konfiguracja modelu danych ER dla importu danych w trybie wsadowym z ER UI.](./media/er-configure-data-import-batch-configurations-2.png)

5. Otwórz plik **1099import-data.xlsx** w programie Excel.

    ![Przykładowy plik Excel z danymi do importu w trybie wsadowym.](./media/er-configure-data-import-batch-excel-content.png)

## <a name="enable-batch-data-import-for-er-from-the-ui"></a>Włączenie wsadowego importu danych dla ER z UI

1. Wybierz kolejno opcje **Administrator systemu** \> **Obszary robocze** \> **Zarządzanie funkcjami**.
2. W obszarze roboczym **Zarządzanie funkcjami** wybierz cechę **Uruchom import ER ręcznie przesłanych dokumentów w trybie wsadowym**, a następnie wybierz **Uruchom teraz**.

## <a name="import-data-from-manually-selected-excel-files"></a>Importuj dane z ręcznie wybranych plików Excela

1. Otwórz **Administracja organizacji** \> **Elektroniczne raportowanie** \> **Konfiguracje**.
2. Na stronie **Konfiguracje** w drzewie konfiguracje wybierz **Model 1099 Payments**.
3. Na skróconej karcie **Składniki konfiguracji** zaznacz łącze **Importowanie transakcji ręcznych dla 1099**.
4. Na stronie **Mapowanie modelu do źródła danych** zaznaczone jest **Mapowanie modelu dla importu ręcznych transakcji 1099**. Wybierz opcję **Uruchom**.
5. Na karcie **Parametry** wybierz pozycję **Przeglądaj**. Znajdź i zaznacz plik **1099import-data.xlsx**, a następnie wybierz **OK**.
6. W polu **Wpisz ID vouchera** wpisz **V-00001**.
7. Na karcie **Uruchom w tle** należy skonfigurować opcję **Przetwarzanie wsadowe** na wartość **Tak**.

    Zauważ, że pole **Opis zadania** jest ustawione na **Uruchomienie odwzorowania modelu "Import ręcznych transakcji 1099", konfiguracja "Model 1099 Payments**. Ta wartość wskazuje, że wykonanie wybranego odwzorowania modelu zostanie zaplanowane jako nowe zadanie wsadowe.

    ![Określanie szczegółów importu danych w trybie wsadowym w oknie dialogowym Parametry raportu elektronicznego.](./media/er-configure-data-import-batch-execution-parameters.png)

8. Kliknij przycisk **OK**. Pojawia się komunikat informujący, że nowe zadanie wsadowe zostało zaplanowane.

    ![Wiadomość o nowym zaplanowanym zadaniu wsadowym na stronie Mapowanie modelu do źródła danych.](./media/er-configure-data-import-batch-scheduled-job-info.png)

## <a name="review-the-data-import-results-on-the-batch-job-page"></a>Przejrzyj wyniki importu danych na stronie Zadania wsadowe

1. Wybierz kolejno opcje **Wspólne** \> **Zapytania** \> **Zadania wsadowe** \> **Moje zadania wsadowe**.
2. Na stronie **Zadanie wsadowe** przefiltruj listę zadań wsadowych w celu znalezienia zaplanowanej partii, a następnie wybierz ją.
3. Wybierz łącze **Identyfikator zadania**, aby przejrzeć szczegóły zadania.
4. Na skróconej karcie **Zadania wsadowe** wybierz pozycję **Dziennik**.

    ![Przycisk dziennika na stronie zadania wsadowego.](./media/er-configure-data-import-batch-scheduled-job-record.png)

5. Przeglądanie szczegółów wykonania.

    ![Dziennik wykonania zaplanowanego zadania wsadowego na stronie Zadanie wsadowe.](./media/er-configure-data-import-batch-scheduled-job-log.png)

## <a name="change-the-data-import-parameters"></a>Zmień parametry importu danych

Po zaplanowaniu zadania, gdy nie zostało ono jeszcze uruchomione, możesz zmienić parametry zaplanowanego importu danych.

1. Wybierz kolejno opcje **Wspólne** \> **Zapytania** \> **Zadania wsadowe** \> **Moje zadania wsadowe**.
2. Na stronie **Zadanie wsadowe** przefiltruj listę zadań wsadowych w celu znalezienia zaplanowanej partii, a następnie wybierz ją.
3. Wybierz opcję **Zmień stan**.
4. W oknie dialogowym **Wybierz nowy status** wybierz **Wstrzymaj**, a następnie wybierz **OK**.
5. Wybierz link **Identyfikator zadania**, aby uzyskać dostęp do szczegółów pracy.
6. Na skróconej karcie **Zadania wsadowe** wybierz pozycję **Parametry**.
7. W oknie dialogowym **Parametry raportu elektronicznego** wykonaj poniższe kroki:

    1. Wybierz przycisk **Przeglądaj**, aby wybrać plik alternatywny do importu danych.
    2. Wybierz opcję **Wprowadź identyfikator załącznika**, aby zmienić numer załącznika w celu zaimportowania transakcji dostawcy.

        ![Zmiana parametrów importu danych dla zaplanowanego zadania wsadowego w oknie dialogowym Parametry raportu elektronicznego.](./media/er-configure-data-import-batch-scheduled-job-parameters.png)

    3. Kliknij przycisk **OK**.

8. Upewnij się, że partia jest nadal zaznaczona, a następnie ponownie wybierz opcję **Zmień stan**.
9. W oknie dialogowym **Wybierz nowy status** wybierz **Czekaj**, a następnie wybierz **OK**.

## <a name="review-the-data-import-results-on-the-er-source-page"></a>Przejrzyj wyniki importu danych na stronie źródła ER

1. Wybierz opcje **Administrowanie organizacją** \> **Raportowanie elektroniczne** \> **Źródło raportowania elektronicznego**.
2. Wybierz rekord **Do importu transakcji sprzedawców (Excel)**, który został automatycznie utworzony podczas importu danych.

    ![Rekord dla konfiguracji Dla importu transakcji sprzedawców (Excel) na stronie Źródło raportowania elektronicznego.](./media/er-configure-data-import-batch-files-source-1.png)

3. Wybierz **Państwa plików dla źródeł**.
4. W **Plikach** i skróconej karcie **Dziennikach źródłowych formatu importu** przejrzyj szczegóły importu.
5. Na skróconej karcie **Pliki** wybierz rekord. Zauważ, że zaimportowany plik jest dołączony do tego rekordu.

    ![Zaimportowany plik dołączony do rekordu na stronie Stany plików dla źródeł.](./media/er-configure-data-import-batch-files-source-2.png)

6. Wybierz **Załączniki**, aby przejrzeć zaimportowany plik.

    ![Zaimportowany plik na stronie widoku dokumentu.](./media/er-configure-data-import-batch-files-source-3.png)

    > [!TIP]
    > Aby zachować te załączniki, system ER używa typu dokumentu, który jest [ustawiony](electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents) dla bieżącej firmy w polu **Inne** w parametrach ER.

## <a name="review-the-data-import-results-on-the-vendor-settlement-for-1099s-page"></a>Przejrzyj wyniki importu danych na stronie Rozliczenie sprzedawcy dla 1099

1. Wybierz kolejno opcje **Rozrachunki z dostawcami** \> **Zadania okresowe** \> **Podatek 1099** \> **Rozliczenia dostawcy dotyczące deklaracji 1099**.
2. W polu **Od dnia** wpisz **31.12.2017** (31 grudnia 2017 r.).
3. Wybierz opcję **Ręczne transakcje podatku 1099**.

    ![Zaimportowane transakcje sprzedawców na stronie Transakcje podatkowe 1099.](./media/er-configure-data-import-batch-imported-data.png)

## <a name="additional-resources"></a>Dodatkowe zasoby

[Raportowanie elektroniczne — omówienie](general-electronic-reporting.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
