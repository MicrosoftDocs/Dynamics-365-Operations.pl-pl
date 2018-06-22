---
title: Konfigurowanie importu danych z programu SharePoint
description: "W tym temacie wyjaśniono, jak przeprowadzić import danych z programu Microsoft SharePoint."
author: NickSelin
manager: AnnBe
ms.date: 05/21/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.translationtype: HT
ms.sourcegitcommit: 2fc887668171175d436b9eb281a35c1c9d089591
ms.openlocfilehash: 4285db9c71208bce45d64933e692a25ef3f46b26
ms.contentlocale: pl-pl
ms.lasthandoff: 05/25/2018

---
# <a name="configure-data-import-from-sharepoint"></a>Konfigurowanie importu danych z programu SharePoint

[!include[banner](../includes/banner.md)]

Aby importować dane z przesyłanego pliku przy użyciu narzędzi raportowania elektronicznego (RE), należy skonfigurować format ER, który obsługuje import i następnie uruchomić mapowanie modelu typu **Do miejsca docelowego**, który używa tego formatu jako źródła danych. Aby importować dane, należy przejść do pliku, który chcesz zaimportować. Plik przychodzący może zostać wybrany ręcznie przez użytkownika. Dzięki nowej funkcjonalności ER, która umożliwia importowanie danych z programu Microsoft SharePoint, można skonfigurować ten proces do pracy bez nadzoru. Konfiguracje ER służą do importowania danych z plików przechowywanych w folderach programu Microsoft SharePoint. W tym temacie opisano, jak przeprowadzić import danych z programu SharePoint do programu Microsoft Dynamics 365 for Finance and Operations. W przykładach użyto transakcji dostawcy jako danych biznesowych.

## <a name="prerequisites"></a>Wymagania wstępne
Aby wykonać przykłady opisane w tym temacie, musisz mieć następujące uprawnienia dostępu:

- Dostęp do programu Finance and Operations w jednej z następujących ról:

    - Deweloper raportowania elektronicznego
    - Konsultant funkcjonalny raportowania elektronicznego
    - Administrator systemu

- Dostęp do wystąpienia serwera programu Microsoft SharePoint, który jest skonfigurowany do współpracy z programem Finance and Operations
- Konfiguracje formatu i modelu raportowania elektronicznego na potrzeby płatności wynikających z deklaracji 1099

### <a name="create-required-er-configurations"></a>Tworzenie wymaganych konfiguracji ER
Odtwórz przewodniki po zadaniach **ER Importowanie danych z pliku programu Microsoft Excel**, które wchodzą w skład procesu biznesowego **7.5.4.3 Nabywanie/opracowywanie składników usług/rozwiązań informatycznych (10677)**. Te wskazówki zadania przeprowadzą Cię przez proces projektowania i używania konfiguracji ER do aktywnego importowania transakcji dostawcy z zewnętrznych plików programu Microsoft Excel. Aby uzyskać więcej informacji, zobacz [Analizowanie dokumentów przychodzących w programie Microsoft Excel](parse-incoming-documents-excel.md). Na koniec uzyskujesz:

- Konfiguracje ER:

    - Konfiguracja modelu ER, **Model płatności 1099**
    - Konfiguracja formatu ER, **Format importowania transakcji z dostawcami z programu Excel**

[![Konfiguracje ER do importowania danych z programu SharePoint](./media/GERImportFromSharePoint-01-Configurations.PNG)](./media/GERImportFromSharePoint-01-Configurations.PNG)

- Przykład pliku przychodzącego w imporcie danych:

    - Plik programu Excel **1099import data.xlsx**, z transakcjami z dostawcami, które należy zaimportować do programu Finance and Operations

[![Przykładowy plik programu Microsoft Excel do importowania z programu SharePoint](./media/GERImportFromSharePoint-02-Excel.PNG)](./media/GERImportFromSharePoint-02-Excel.PNG)

> [!NOTE]
> Format na potrzeby importowania transakcji dostawcy jest zaznaczony jako domyślne mapowanie modelu. Dlatego po uruchomieniu mapowania modelu **Model płatności 1099”**, jeśli to mapowanie modelu jest typu **Do lokalizacji docelowej**, mapowanie modelu uruchamia ten format, aby importować dane z plików zewnętrznych. Następnie używa tych danych do aktualizowania tabel aplikacji.

## <a name="configure-document-management-parameters"></a>Konfigurowanie parametrów zarządzania dokumentami
1. Na stronie **Parametry zarządzania dokumentami** skonfiguruj dostęp do wystąpienia serwera programu SharePoint, który będzie używany w firmie, do której obecnie się logujesz. W tym przykładzie firmą jest USMF.
2. Przetestuj połączenie z wystąpieniem serwera programu SharePoint, aby się upewnić, że przyznano Ci dostęp.

[![Ustawienie zarządzania dokumentami — serwer programu SharePoint](./media/GERImportFromSharePoint-03-SharePointSetup.png)](./media/GERImportFromSharePoint-03-SharePointSetup.png)

3. Otwórz skonfigurowaną witrynę programu SharePoint, a następnie utwórz następujące foldery, w których można przechowywać przychodzące pliki:

    - Źródło importu plików (główne)
    - Źródło importu plików (alternatywne)

[![Ustawienie zarządzania dokumentami — serwer programu SharePoint](./media/GERImportFromSharePoint-04-SharePointFolder1.png)](./media/GERImportFromSharePoint-04-SharePointFolder1.png)

[![Ustawienie zarządzania dokumentami — serwer programu SharePoint](./media/GERImportFromSharePoint-05-SharePointFolder2.png)](./media/GERImportFromSharePoint-05-SharePointFolder2.png)

4. W programie Finance and Operations na stronie **Typy dokumentów** utwórz następujące typy dokumentów, które będą używane w celu uzyskiwania dostępu do nowo utworzonych folderów programu SharePoint:

    - SP główny
    - SP alternatywny

5. Dla utworzonych typów dokumentów w polu **Grupa** wypełnij pole **Plik**, a w pliku **Lokalizacja** wprowadź **SharePoint**. Wprowadź adres folderu programu SharePoint:

    - Dla typu dokumentu **SP główny**: Źródło importu plików (główne)
    - Dla typu dokumentu **SP alternatywny**: Źródło importu plików (alternatywne)

[![Ustawienie programu SharePoint — nowy typ dokumentu](./media/GERImportFromSharePoint-06-SharePointDocumentTypesSetup.png)](./media/GERImportFromSharePoint-06-SharePointDocumentTypesSetup.png)

## <a name="configure-er-sources-for-the-er-format"></a>Konfigurowanie źródeł ER formatu ER
1. Wybierz kolejno opcje **Administrowanie organizacją** > **Raportowanie elektroniczne** > **Źródło raportowania elektronicznego**.
2. Na stronie **Źródło raportowania elektronicznego** skonfiguruj pliki źródłowe importu danych za pomocą skonfigurowanego formatu raportowania elektronicznego.
3. Zdefiniuj maskę nazwy pliku, aby importować tylko pliki z rozszerzeniem .xlsx. Maska nazwy pliku jest opcjonalna i jest używana tylko wtedy, gdy została zdefiniowana. Dla każdego formatu ER można zdefiniować tylko jedną maskę.
4. Zaznacz oba utworzone wcześniej foldery programu SharePoint.

[![Ustawienie źródła plików modułu ER](./media/GERImportFromSharePoint-07-FormatSourceSetup.PNG)](./media/GERImportFromSharePoint-07-FormatSourceSetup.PNG)

> [!NOTE]
>*Źródło* ER jest określane indywidualnie dla każdej firmy aplikacji. Z kolei *konfiguracje* raportowania elektronicznego są wspólne we wszystkich firmach.

> [!NOTE]
> Po usunięciu ustawienia źródła ER dla formatu ER wszystkie powiązane stany pliku (patrz poniżej) również zostaną usunięte.

## <a name="review-the-files-states-for-the-er-format"></a>Przeglądanie stanów plików formatu raportowania elektronicznego
1. Na stronie **Źródło raportowania elektronicznego** wybierz opcję **Stany plików dla źródeł**, aby przejrzeć zawartości skonfigurowanych plików źródłowych dla bieżącego formatu ER.
2. W sekcji **Pliki** przejrzyj listę plików. Ta lista zawiera następujące elementy:

    - Pliki źródłowe mające zastosowanie na podstawie maski nazwy pliku (jeśli ją zdefiniowano) i gotowe do importu danych. W przypadku tych plików sekcja **Dziennik źródeł dla formatu importu** jest pusta.
    - Uprzednio zaimportowane pliki. Dla każdego z tych plików w sekcji **Dziennik źródeł dla formatu importu** można przeglądać historię importu danego pliku.

Można również otworzyć stronę **stanów plików dla źródeł**, wybierając **Administrowanie organizacją**\>**Raportowanie elektroniczne**\>**Stany plików dla źródeł**. W takim przypadku strona zawiera informacje o źródłach plików dla wszystkich formatów ER, dla których skonfigurowano źródła plików w firmie, w której użytkownik jest aktualnie zalogowany.

## <a name="import-data-from-excel-files-that-are-in-a-sharepoint-folder"></a>Importowanie danych z plików programu Excel znajdujących się w folderze programu SharePoint
1. W programie SharePoint przekaż plik programu Microsoft Excel **1099import data.xlsx** zawierający transakcje z dostawcą do utworzonego wcześniej folderu programu SharePoint **Źródło importu plików (główne)**.

[![Zawartość programu SharePoint — plik programu Microsoft Excel do importowania](./media/GERImportFromSharePoint-08-UploadFile.png)](./media/GERImportFromSharePoint-08-UploadFile.png)

2. W programie Finance and Operations na stronie **Stany plików dla źródeł** wybierz opcję **Odśwież**, aby odświeżyć stronę. Należy zauważyć, że plik programu Excel przekazany do programu SharePoint były wyświetlany w tym formularzu ze stanem **Gotowe**. Następujące stany postępu są obecnie obsługiwane:

    - **Gotowe** — Przypisywany automatycznie do każdego nowego pliku w folderze programu SharePoint. Taki stan oznacza, że plik jest gotowy do zaimportowania.
    - **Importowanie** — Przypisywany automatycznie przez raport modułu ER, gdy plik zostanie zablokowany przez proces importu, aby zapobiec wykorzystaniu go przez inne procesy (jeśli wiele procesów jest uruchomionych jednocześnie).
    - **Zaimportowano** — Przypisywany automatycznie przez raport modułu ER, gdy import pliku został pomyślnie wykonany. Taki stan oznacza, że importowany plik został usunięty ze skonfigurowanego źródła plików (folder programu SharePoint).
    - **Niepowodzenie** — Przypisywany automatycznie przez raport modułu ER, gdy import pliku zakończył się z błędami lub wyjątkami.
    - **Wstrzymane** — Przypisywany ręcznie przez użytkownika w tym formularzu. Taki stan oznacza, że nie będzie można teraz zaimportować pliku. Ten stan może służyć do odłożenia w czasie importowania niektórych plików.

[![Strona stanu plików modułu ER dla wybranych źródeł](./media/GERImportFromSharePoint-09-FileStatesForm.png)](./media/GERImportFromSharePoint-09-FileStatesForm.png)

## <a name="import-data-from-sharepoint-files"></a>Importowanie danych z plików programu SharePoint
1. Otwórz drzewo konfiguracji raportowania elektronicznego, zaznacz pozycję **Model płatności 1099** i rozwiń listę składników modelu ER.
2. Wybierz nazwę mapowania modelu, aby otworzyć listę mapowań modeli dla wybranej konfiguracji modelu ER.

[![Strona stanu plików modułu ER dla wybranych źródeł](./media/GERImportFromSharePoint-10-SelectModelMapping.PNG)](./media/GERImportFromSharePoint-10-SelectModelMapping.PNG)

3. Wybierz opcję **Uruchom**, aby uruchomić wybrane mapowanie modelu ER. Ponieważ skonfigurowano źródła plików dla formatu ER, można zmienić wartość opcji **Źródło plików** zgodnie z potrzebami. Jeśli zachowasz wartość tej, opcji pliki .xslx będą importowane ze skonfigurowanych źródeł (w tym przykładzie z folderów programu SharePoint).

    W tym przykładzie importujesz tylko jeden plik. Jednak jeśli istnieje wiele plików, są one wybierane do importowania w kolejności, w jakiej zostały dodane do folderu programu SharePoint. Każde uruchomienie formatu ER powoduje import jednego wybranego pliku.

[![Uruchamianie mapowania modelu ER](./media/GERImportFromSharePoint-11-RunModelMapping.PNG)](./media/GERImportFromSharePoint-11-RunModelMapping.PNG)

4. Mapowanie modelu można uruchomić bez nadzoru w trybie wsadowym. W takim przypadku podczas każdego wykonywania zadania wsadowego z tym formatem ER jest importowany jeden plik ze skonfigurowanych źródeł plików. Poniższy kod służy do wdrożenia uruchomienia tej partii.

    ```
    ERObjectsFactory::createMappingDestinationRunByImportFormatMappingId().run()
    ```

    Plik, który został pomyślnie zaimportowanych z folderu programu SharePoint, jest usuwany z tego folderu.

5. Wprowadź identyfikator załącznika, na przykład **V-00001**, a następnie wybierz opcję **OK**.

[![Uruchamianie mapowania modelu ER](./media/GERImportFromSharePoint-12-ModelMappingRunFinished.PNG)](./media/GERImportFromSharePoint-12-ModelMappingRunFinished.PNG)

6. Na stronie **Stany plików dla źródeł** wybierz opcję **Odśwież**, aby odświeżyć stronę.

[![Strona stanu plików modułu ER dla wybranych źródeł](./media/GERImportFromSharePoint-13-FileStatesForm.PNG)](./media/GERImportFromSharePoint-13-FileStatesForm.PNG)

7. W sekcji **Pliki** przejrzyj listę plików. Sekcja **Dziennik źródeł dla formatu importu** zawiera historię importu pliku programu Excel. Ponieważ ten plik został pomyślnie zaimportowany, jest w folderze programu SharePoint oznaczony jako **Usunięty**.
8. Przejrzyj folder programu SharePoint **Źródła importu plików (główne)**. Pliki programu Excel, które zostały zaimportowane pomyślnie, zostały usunięte z tego folderu.
9. W programie Finance and Operations wybierz kolejno opcje **Rozrachunki z dostawcami** \> **Zadania okresowe** \> **Podatek 1099** \> **Rozliczenia dostawcy dotyczące deklaracji 1099**.
10. W polach **Od dnia** i **Do dnia** wprowadź odpowiednie wartości. Następnie wybierz opcję **Ręczne transakcje podatku 1099**.

    Transakcje dostawcy, które zostały zaimportowane z plików programu Excel w programie SharePoint dla załącznika **V-00001**, są wyświetlone na stronie.

[![Strona transakcji z dostawcą z podatkiem 1099](./media/GERImportFromSharePoint-14-ImportedTransactions.PNG)](./media/GERImportFromSharePoint-14-ImportedTransactions.PNG)

## <a name="prepare-an-excel-file-for-import"></a>Przygotowywanie pliku programu Excel do importu
1. Otwórz użyty wcześniej plik programu Excel. W wierszu 1 w kolumnie 3 dodaj kod dostawcy, który nie istnieje w aplikacji. Dodaj do wiersza więcej fałszywych informacji o dostawcy.

[![Przykładowy plik programu Microsoft Excel do importowania z programu SharePoint](./media/GERImportFromSharePoint-15-Excel.PNG)](./media/GERImportFromSharePoint-15-Excel.PNG)

2. Prześlij zaktualizowany plik programu Excel zawierający transakcje dostawcy do folderu programu SharePoint **Źródło importu plików (główne)**.
3. W programie Finance and Operations otwórz drzewo konfiguracji raportowania elektronicznego, zaznacz pozycję **Model płatności 1099** i rozwiń listę składników modelu ER.
4. Wybierz nazwę mapowania modelu w celu aktualizacji tego mapowania, tak aby niepoprawny kod dostawcy był uważany za błąd w trakcie procesu importowania danych.
5. Wybierz opcję **Konstruktor**.
6. Na karcie **Weryfikacje** należy zmienić akcję po weryfikacji w skonfigurowanej reguły weryfikacji, tak aby oceniać, czy importowane konto dostawcy istnieje w aplikacji. Aktualizuj wartość pola **Akcja po weryfikacji** na **Zatrzymać wykonywanie**, zapisz zmiany i zamknij stronę.

[![Strona projektanta mapowania modelu ER](./media/GERImportFromSharePoint-16-UpdateModelMapping.PNG)](./media/GERImportFromSharePoint-16-UpdateModelMapping.PNG)

7. Zapisz zmiany i zamknij projektanta mapowania modelu ER.
8. Wybierz opcję **Uruchom**, aby uruchomić zmodyfikowane mapowanie modelu ER.
9. Wprowadź identyfikator załącznika, na przykład **V-00002**, a następnie wybierz opcję **OK**.

    Należy zwrócić uwagę, że dziennik informacyjny zawiera powiadomienie mówiące o tym, że plik znajdujący się w folderze programu SharePoint zawiera niepoprawne konto dostawcy i nie można go zaimportować.

[![Uruchamianie mapowania modelu ER](./media/GERImportFromSharePoint-17-ModelMappingRunFinished.PNG)](./media/GERImportFromSharePoint-17-ModelMappingRunFinished.PNG)

10. Na stronie **Stany plików dla źródeł** wybierz opcję **Odśwież**, a następnie w sekcji **Pliki** przejrzyj listę plików.

[![Strona stanu plików modułu ER dla wybranych źródeł](./media/GERImportFromSharePoint-18-FileStatesForm.PNG)](./media/GERImportFromSharePoint-18-FileStatesForm.PNG)

Sekcja **Dziennik źródeł dla formatu importu** wskazuje, że proces importowania nie powiódł się, a plik jest wciąż w folderze programu SharePoint (pole wyboru **Jest usunięty** nie jest zaznaczone). Jeśli naprawisz ten plik w programie SharePoint poprzez dodanie odpowiedniego kodu dostawcy, a następnie w sekcji **Dziennik źródeł dla formatu importu** zmienisz stan pliku z **Niepowodzenie** na **Gotowe**, można ponownie zaimportować plik.

11. Przejrzyj folder programu SharePoint **Źródła importu plików (główne)**. Należy zauważyć, że plik programu Excel, który nie został zaimportowany wciąż znajduje się w tym folderze.
12. W programie Finance and Operations wybierz kolejno opcje **Rozrachunki z dostawcami** \> **Zadania okresowe** \> **Podatek 1099** \> **Rozliczenia dostawcy dotyczące deklaracji 1099**, wprowadź odpowiednie wartości w polach **Od dnia** i **Do dnia**, a następnie wybierz opcję **Ręczne transakcje podatku 1099**.

    Dostępne są tylko transakcje załącznika V-00001. Nie są dostępne żadne transakcje związane z załącznikiem V-00002, nawet jeśli w pliku programu Excel wykryto błąd dotyczący ostatniej zaimportowanej transakcji.

