---
title: Konfigurowanie importu danych z programu SharePoint
description: W tym temacie wyjaśniono, jak przeprowadzić import danych z programu Microsoft SharePoint.
author: NickSelin
ms.date: 11/19/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.openlocfilehash: 6cd717c0c599d68574a5a064761c8d6777418515
ms.sourcegitcommit: 1707cf45217db6801df260ff60f4648bd9a4bb68
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/23/2021
ms.locfileid: "7675352"
---
# <a name="configure-data-import-from-sharepoint"></a>Konfigurowanie importu danych z programu SharePoint

[!include[banner](../includes/banner.md)]

Aby importować dane z przesyłanego pliku przy użyciu narzędzi raportowania elektronicznego (RE), należy skonfigurować format ER, który obsługuje import i następnie uruchomić mapowanie modelu typu **Do miejsca docelowego**, który używa tego formatu jako źródła danych. Aby importować dane, należy przejść do pliku, który chcesz zaimportować. Plik przychodzący może zostać wybrany ręcznie przez użytkownika. Dzięki nowej funkcjonalności ER, która umożliwia importowanie danych z programu Microsoft SharePoint, można skonfigurować ten proces do pracy bez nadzoru. Konfiguracje ER służą do importowania danych z plików przechowywanych w folderach programu Microsoft SharePoint. W tym temacie wyjaśniono, jak ukończyć importowanie danych SharePoint. W przykładach użyto transakcji dostawcy jako danych biznesowych.

## <a name="prerequisites"></a>Wymagania wstępne
Aby wykonać przykłady opisane w tym temacie, musisz mieć następujące uprawnienia dostępu:

- Dostęp do jednej z następujących ról:

    - Deweloper raportowania elektronicznego
    - Konsultant funkcjonalny raportowania elektronicznego
    - Administrator systemu

- Dostęp do wystąpienia serwera Microsoft SharePoint, który jest skonfigurowany do współpracy z aplikacją.
- Konfiguracje formatu i modelu raportowania elektronicznego na potrzeby płatności wynikających z deklaracji 1099.

### <a name="create-required-er-configurations"></a>Tworzenie wymaganych konfiguracji ER
Odtwórz przewodniki po zadaniach **ER Importowanie danych z pliku programu Microsoft Excel**, które wchodzą w skład procesu biznesowego **7.5.4.3 Nabywanie/opracowywanie składników usług/rozwiązań informatycznych (10677)**. Te wskazówki zadania przeprowadzą Cię przez proces projektowania i używania konfiguracji ER do aktywnego importowania transakcji dostawcy z plików programu Microsoft Excel. Aby uzyskać więcej informacji, zobacz [Analizowanie dokumentów przychodzących w formacie Excel](parse-incoming-documents-excel.md). Po wykonaniu kroków przewodnika po zadaniach będziesz mieć następującą konfigurację.

#### <a name="er-configurations"></a>Konfiguracje ER

- Konfiguracja modelu ER, **Model płatności 1099**
- Konfiguracja formatu ER, **Format importowania transakcji z dostawcami z programu Excel**

![Konfiguracje ER do importowania danych z programu SharePoint.](./media/GERImportFromSharePoint-01-Configurations.PNG)

#### <a name="sample-of-the-incoming-file-for-data-import"></a>Przykład pliku przychodzącego w imporcie danych

- Plik programu Excel **1099import data.xlsx**, z transakcjami z dostawcami, które należy zaimportować.

![Przykładowy plik programu Excel do zaimportowania z programu SharePoint.](./media/GERImportFromSharePoint-02-Excel.PNG)
    
> [!NOTE]
> Format na potrzeby importowania transakcji dostawcy jest zaznaczony jako domyślne mapowanie modelu. Dlatego po uruchomieniu mapowania modelu **Model płatności 1099”**, jeśli to mapowanie modelu jest typu **Do lokalizacji docelowej**, mapowanie modelu uruchamia ten format, aby importować dane z plików zewnętrznych. Następnie używa tych danych do aktualizowania tabel aplikacji.

## <a name="configure-access-to-sharepoint-for-file-storage"></a>Konfigurowanie dostępu do witryny programu SharePoint do przechowywania plików
Aby zapisywać pliki raportów elektronicznych w lokalizacji programu SharePoint, należy skonfigurować dostęp do wystąpienia programu SharePoint Server używanego przez bieżącą firmę. W tym przykładzie firmą jest USMF. Aby uzyskać instrukcje, zobacz [Konfigurowanie magazynu SharePoint](../../fin-ops/organization-administration/configure-document-management.md#configure-sharepoint-storage).

1. Wykonaj kroki opisane w temacie [Konfigurowanie magazynu SharePoint](../../fin-ops/organization-administration/configure-document-management.md#configure-sharepoint-storage).
2. Otwórz skonfigurowaną witrynę programu SharePoint.
3. Utwórz następujące foldery do magazynowania przychodzących plików raportów elektronicznych.

     - Źródło importu plików (główne) (przykład pokazany na zrzucie ekranu poniżej)
     - Źródło importu plików (alternatywne)

    ![Źródło importu plików (główne).](./media/GERImportFromSharePoint-04-SharePointFolder1.png)

4. (Opcjonalnie) Utwórz następujące foldery, w których pliki mogą być zapisywane po zaimportowaniu. 

    - Folder archiwum plików — ten folder jest przeznaczony na pliki pomyślnie zaimportowane.
    - Folder plików z ostrzeżeniami — ten folder jest przeznaczony na pliki, które zostały zaimportowane z ostrzeżeniem.
    - Folder plików z błędami — ten folder jest przeznaczony na pliki zaimportowane z błędami.

4. Wybierz kolejno opcje **Administrowanie organizacją > Zarządzanie dokumentami > Typy dokumentów**.
5. Utwórz następujące typy dokumentów, które będą używane do uzyskiwania dostępu do folderów programu SharePoint, które zostały utworzone. Aby uzyskać instrukcje, zobacz [Konfigurowanie typów dokumentów](../../fin-ops/organization-administration/configure-document-management.md#configure-document-types).

|Typ dokumentu        | Grupa              | Lokalizacja      | Folder programu SharePoint      |
|--------------------|--------------------|---------------|------------------------|
|SP główny             |Plik                |SharePoint     |Źródło importu plików (główne)|
|SP alternatywny             |Plik                |SharePoint     |Źródło importu plików (alternatywne)|
|Archiwum SP             |Plik                |SharePoint     |Folder archiwum plików|
|Ostrzeżenie SP             |Plik                |SharePoint     |Folder plików z ostrzeżeniami|
|Błąd SP             |Plik                |SharePoint     |Folder plików z błędami|

![Ustawienie programu SharePoint — nowy typ dokumentu.](./media/GERImportFromSharePoint-06-SharePointDocumentTypesSetup.png)

## <a name="configure-er-sources-for-the-er-format"></a>Konfigurowanie źródeł ER formatu ER
1. Wybierz kolejno opcje **Administrowanie organizacją** \> **Raportowanie elektroniczne** \> **Źródło raportowania elektronicznego**.
2. Na stronie **Źródło raportowania elektronicznego** skonfiguruj pliki źródłowe importu danych za pomocą skonfigurowanego formatu raportowania elektronicznego.
3. Zdefiniuj maskę nazwy pliku, aby importować tylko pliki z rozszerzeniem .xlsx. Maska nazwy pliku jest opcjonalna i jest używana tylko wtedy, gdy została zdefiniowana. Dla każdego formatu ER można zdefiniować tylko jedną maskę.
4. Zmień ustawienie **Sortuj pliki przed zaimportowaniem** na **Nie sortuj**, jeśli istnieje kilka plików do importu i kolejność importu nie jest ważna
5. Zaznacz wszystkie utworzone wcześniej foldery programu SharePoint.

    [![Ustawienie źródła plików modułu ER.](./media/GERImportFromSharePoint-07-FormatSourceSetup.PNG)](./media/GERImportFromSharePoint-07-FormatSourceSetup.PNG)

> [!NOTE]
> - *Źródło* ER jest określane indywidualnie dla każdej firmy aplikacji. Z kolei *konfiguracje* raportowania elektronicznego są wspólne we wszystkich firmach.
> - Po usunięciu ustawienia źródła ER dla formatu ER wszystkie powiązane stany pliku (patrz poniżej) również zostaną usunięte przez potwierdzenie.

## <a name="review-the-files-states-for-the-er-format"></a>Przeglądanie stanów plików formatu raportowania elektronicznego
1. Na stronie **Źródło raportowania elektronicznego** wybierz opcję **Stany plików dla źródeł**, aby przejrzeć zawartości skonfigurowanych plików źródłowych dla bieżącego formatu ER.
2. W sekcji **Pliki** przejrzyj listę plików. Ta lista zawiera następujące elementy:

    - Pliki źródłowe mające zastosowanie na podstawie maski nazwy pliku (jeśli ją zdefiniowano) i gotowe do importu danych. W przypadku tych plików sekcja **Dziennik źródeł dla formatu importu** jest pusta.
    - Uprzednio zaimportowane pliki. Dla każdego z tych plików w sekcji **Dziennik źródeł dla formatu importu** można przeglądać historię importu danego pliku.

Można również otworzyć stronę **stanów plików dla źródeł**, wybierając **Administrowanie organizacją**\>**Raportowanie elektroniczne**\>**Stany plików dla źródeł**. W takim przypadku strona zawiera informacje o źródłach plików dla wszystkich formatów ER, dla których skonfigurowano źródła plików w firmie, w której użytkownik jest aktualnie zalogowany.

## <a name="import-data-from-excel-files-that-are-in-a-sharepoint-folder"></a>Importowanie danych z plików programu Excel znajdujących się w folderze programu SharePoint
1. W programie SharePoint przekaż plik programu Microsoft Excel **1099import data.xlsx** zawierający transakcje z dostawcą do utworzonego wcześniej folderu programu SharePoint **Źródło importu plików (główne)**.

    [![Zawartość SharePoint — plik programu Microsoft Excel do zaimportowania.](./media/GERImportFromSharePoint-08-UploadFile.png)](./media/GERImportFromSharePoint-08-UploadFile.png)

2. Na stronie **Stany plików dla źródeł** wybierz opcję **Odśwież**, aby odświeżyć stronę. Plik programu Excel przekazany do programu SharePoint były wyświetlany na tej stronie ze stanem **Gotowe**. Następujące stany postępu są obecnie obsługiwane:

    - **Gotowe** — Przypisywany automatycznie do każdego nowego pliku w folderze programu SharePoint. Taki stan oznacza, że plik jest gotowy do zaimportowania.
    - **Importowanie** — Przypisywany automatycznie przez raport modułu ER, gdy plik zostanie zablokowany przez proces importu, aby zapobiec wykorzystaniu go przez inne procesy (jeśli wiele procesów jest uruchomionych jednocześnie).
    - **Zaimportowano** — Przypisywany automatycznie przez raport modułu ER, gdy import pliku został pomyślnie wykonany. Taki stan oznacza, że importowany plik został usunięty ze skonfigurowanego źródła plików (folder programu SharePoint).
    - **Niepowodzenie** — Przypisywany automatycznie przez raport modułu ER, gdy import pliku zakończył się z błędami lub wyjątkami.
    - **Wstrzymane** — Przypisywany ręcznie przez użytkownika na tej stronie. Taki stan oznacza, że nie będzie można teraz zaimportować pliku. Ten stan może służyć do odłożenia w czasie importowania niektórych plików.

    [![Odświeżona strona stanu plików modułu ER dla wybranych źródeł.](./media/GERImportFromSharePoint-09-FileStatesForm.png)](./media/GERImportFromSharePoint-09-FileStatesForm.png)

## <a name="import-data-from-sharepoint-files"></a>Importowanie danych z plików programu SharePoint
1. Otwórz drzewo konfiguracji raportowania elektronicznego, zaznacz pozycję **Model płatności 1099** i rozwiń listę składników modelu ER.
2. Wybierz nazwę mapowania modelu, aby otworzyć listę mapowań modeli dla wybranej konfiguracji modelu ER.

    [![Strona konfiguracji.](./media/GERImportFromSharePoint-10-SelectModelMapping.PNG)](./media/GERImportFromSharePoint-10-SelectModelMapping.PNG)

3. Wybierz opcję **Uruchom**, aby uruchomić wybrane mapowanie modelu ER. Ponieważ skonfigurowano źródła plików dla formatu ER, można zmienić wartość opcji **Źródło plików** zgodnie z potrzebami. Jeśli zachowasz wartość tej, opcji pliki .xslx będą importowane ze skonfigurowanych źródeł (w tym przykładzie z folderów programu SharePoint).

    W tym przykładzie importujesz tylko jeden plik. Jednak jeśli istnieje wiele plików, są one wybierane do importowania w kolejności, w jakiej zostały dodane do folderu programu SharePoint. Każde uruchomienie formatu ER powoduje import jednego wybranego pliku.

    [![Importowanie z programu SharePoint i uruchamianie mapowania modelu ER.](./media/GERImportFromSharePoint-11-RunModelMapping.PNG)](./media/GERImportFromSharePoint-11-RunModelMapping.PNG)

4. Mapowanie modelu można uruchomić [bez nadzoru](#limitations) w trybie wsadowym. W takim przypadku podczas każdego wykonywania zadania wsadowego z tym formatem ER jest importowany jeden plik ze skonfigurowanych źródeł plików.

    Kiedy plik zostanie pomyślnie zaimportowany do folderu programu SharePoint, jest usuwany z tego folderu i przenoszony do folderu pomyślnie zaimportowanych plików lub do folderu, do którego importowane są pliki z ostrzeżeniami. W przeciwnym jest on przenoszony do folderu na pliki z błędami lub zostaje w tym folderze, jeśli folder plików z błędami nie został skonfigurowany. 

5. Wprowadź identyfikator załącznika, na przykład **V-00001**, a następnie wybierz opcję **OK**.

    [![Uruchamianie mapowania modelu ER.](./media/GERImportFromSharePoint-12-ModelMappingRunFinished.PNG)](./media/GERImportFromSharePoint-12-ModelMappingRunFinished.PNG)

6. Na stronie **Stany plików dla źródeł** wybierz opcję **Odśwież**, aby odświeżyć stronę.

    [![Strona stanu plików modułu ER dla źródeł.](./media/GERImportFromSharePoint-13-FileStatesForm.PNG)](./media/GERImportFromSharePoint-13-FileStatesForm.PNG)

7. W sekcji **Pliki** przejrzyj listę plików. Sekcja **Dziennik źródeł dla formatu importu** zawiera historię importu pliku programu Excel. Ponieważ ten plik został pomyślnie zaimportowany, jest w folderze programu SharePoint oznaczony jako **Usunięty**.
8. Przejrzyj folder programu SharePoint **Źródła importu plików (główne)**. Pliki programu Excel, które zostały zaimportowane pomyślnie, zostały usunięte z tego folderu.
9. Wybierz kolejno opcje **Rozrachunki z dostawcami** \> **Zadania okresowe** \> **Podatek 1099** \> **Rozliczenia dostawcy dotyczące deklaracji 1099**.
10. W polach **Od dnia** i **Do dnia** wprowadź odpowiednie wartości. Następnie wybierz opcję **Ręczne transakcje podatku 1099**.

    Transakcje dostawcy, które zostały zaimportowane z plików programu Excel w programie SharePoint dla załącznika **V-00001**, są wyświetlone na stronie.

    [![Strona transakcji z dostawcą z podatkiem 1099.](./media/GERImportFromSharePoint-14-ImportedTransactions.PNG)](./media/GERImportFromSharePoint-14-ImportedTransactions.PNG)

## <a name="prepare-an-excel-file-for-import"></a>Przygotowywanie pliku programu Excel do importu
1. Otwórz użyty wcześniej plik programu Excel. W wierszu 1 w kolumnie 3 dodaj kod dostawcy, który nie istnieje w aplikacji. Dodaj do wiersza więcej fałszywych informacji o dostawcy.

    [![Przykładowy plik programu Microsoft Excel do zaimportowania z programu SharePoint.](./media/GERImportFromSharePoint-15-Excel.PNG)](./media/GERImportFromSharePoint-15-Excel.PNG)

2. Prześlij zaktualizowany plik programu Excel zawierający transakcje dostawcy do folderu programu SharePoint **Źródło importu plików (główne)**.
3. Otwórz drzewo konfiguracji raportowania elektronicznego, zaznacz pozycję **Model płatności 1099** i rozwiń listę składników modelu ER.
4. Wybierz nazwę mapowania modelu w celu aktualizacji tego mapowania, tak aby niepoprawny kod dostawcy był uważany za błąd w trakcie procesu importowania danych.
5. Wybierz opcję **Konstruktor**.
6. Na karcie **Weryfikacje** należy zmienić akcję po weryfikacji w skonfigurowanej reguły weryfikacji, tak aby oceniać, czy importowane konto dostawcy istnieje w aplikacji. Aktualizuj wartość pola **Akcja po weryfikacji** na **Zatrzymać wykonywanie**, zapisz zmiany i zamknij stronę.

    [![Strona projektanta mapowania modelu ER.](./media/GERImportFromSharePoint-16-UpdateModelMapping.PNG)](./media/GERImportFromSharePoint-16-UpdateModelMapping.PNG)

7. Zapisz zmiany i zamknij projektanta mapowania modelu ER.
8. Wybierz opcję **Uruchom**, aby uruchomić zmodyfikowane mapowanie modelu ER.
9. Wprowadź identyfikator załącznika, na przykład **V-00002**, a następnie wybierz opcję **OK**.

    Dziennik informacyjny zawiera powiadomienie mówiące o tym, że w folderze programu SharePoint znajduje się plik zawierający niepoprawne konto dostawcy i nie można go zaimportować.

    [![Zakończone mapowania modelu ER.](./media/GERImportFromSharePoint-17-ModelMappingRunFinished.PNG)](./media/GERImportFromSharePoint-17-ModelMappingRunFinished.PNG)

10. Na stronie **Stany plików dla źródeł** wybierz opcję **Odśwież**, a następnie w sekcji **Pliki** przejrzyj listę plików.

    [![Strona stanu plików modułu ER dla wybranych źródeł.](./media/GERImportFromSharePoint-18-FileStatesForm.PNG)](./media/GERImportFromSharePoint-18-FileStatesForm.PNG)

   Sekcja **Dziennik źródeł dla formatu importu** wskazuje, że proces importowania nie powiódł się, a plik jest wciąż w folderze plików z błędami programu SharePoint (pole wyboru **Jest usunięty** nie jest zaznaczone). Jeżeli naprawisz ten plik w programie SharePoint, dodając odpowiedni kod dostawcy, a następnie przeniesiesz go do (głównego) folderu źródła importu plików programu SharePoint, możesz zaimportować plik ponownie.

11. Wybierz kolejno opcje **Rozrachunki z dostawcami** \> **Zadania okresowe** \> **Podatek 1099** \> **Rozliczenia dostawcy dotyczące deklaracji 1099**, wprowadź odpowiednie wartości w polach **Od dnia** i **Do dnia**, a następnie wybierz opcję **Ręczne transakcje podatku 1099**.

    Dostępne są tylko transakcje załącznika V-00001. Nie są dostępne żadne transakcje związane z załącznikiem V-00002, nawet jeśli w pliku programu Excel wykryto błąd dotyczący ostatniej zaimportowanej transakcji.

## <a name=""></a><a name="limitations">Ograniczenia</a>

Struktura modułu ER nie oferuje możliwości inicjowania nowego zadania wsadowego, które wykona mapowanie modelu w trybie nienadzorowanym w celu zaimportowania danych. Chcąc to zrobić, trzeba opracować nową logikę umożliwiającą wywoływanie skonfigurowanego mapowania modelu ER z interfejsu użytkownika aplikacji w celu importowania danych z przychodzących plików. W związku z tym wymagane są pewne prace technologiczne. 

Aby dowiedzieć się więcej o odpowiednim interfejsie API modułu ER, zobacz sekcję [Kod źródłowy uruchamiania mapowania formatu w celu importowania danych](er-apis-app73.md#code-to-run-a-format-mapping-for-data-import) w temacie [Zmiany w interfejsie API struktury ER w aktualizacji Application update 7.3](er-apis-app73.md).

Przejrzyj kod w klasie `BankImport_RU` modelu `Application Suite`, aby zobaczyć, jak można zaimplementować niestandardową logikę. Ta klasa rozszerza klasę `RunBaseBatch`. W szczególności przejrzyj metodę `runER()`, w której obiekt `ERIModelMappingDestinationRun` jest tworzony jako moduł uruchamiający mapowania modelu ER.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Raportowanie elektroniczne — omówienie](general-electronic-reporting.md)

[Zmiany w interfejsie API struktury ER w aktualizacji Application update 7.3](er-apis-app73.md)

[Zmiany w interfejsie API struktury ER w aktualizacji Application update 10.0.23](er-apis-app10-0-23.md)



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
