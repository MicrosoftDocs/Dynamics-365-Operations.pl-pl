---
title: Przygotuj metadane dla konkretnej aplikacji dla RCS i ER
description: Ten temat zawiera informacje dotyczące projektowania formatów ER, które określają atrybuty XML służące do analizy przychodzących dokumentów elektronicznych w formacie XML.
author: NickSelin
manager: AnnBe
ms.date: 07/03/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: EROperationDesigner
audience: Application User, Developer, IT Pro
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 7a6fc1e54444584895aa75ae91d39143f27e34d8
ms.sourcegitcommit: d0fa7eb2166a30314205e7f70bbeaff6fbd5fb55
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/03/2019
ms.locfileid: "1726582"
---
# <a name="prepare-application-specific-metadata-for-rcs-and-er"></a>Przygotuj metadane dla konkretnej aplikacji dla RCS i ER

Można zaprojektować formaty raportów elektronicznych ER w taki sposób, aby analizowały przychodzące dokumenty elektroniczne w formacie XML. Niektóre atrybuty elementów XML można określać w zaprojektowanym formacie ER jako opcjonalne. Pozwoli to na prawidłową obsługę przychodzących plików z takimi atrybutami XML lub bez nich. Następnie można użyć zawartości tych plików do aktualizacji danych aplikacji.

Aby dowiedzieć się więcej o tej funkcji, należy wykonać kroki opisane w temacie, [Importuj pliki RCS w formacie XML z opcjonalnymi atrybutami](tasks/import-files-xml-format-optional-attributes.md), które są częścią procesu biznesowego 7.5.4.3 Nabycie/Opracowanie procesu biznesowego dotyczącego usług IT/komponentów rozwiązania (10677). Możesz pobrać ten przewodnik zadań i powiązane przykładowe pliki z [Microsoft Download Center](https://go.microsoft.com/fwlink/?linkid=874684).


| Opis zawartości       | Plik                                                         |
|---------------------------|--------------------------------------------------------------|
| Przykładowy plik w formacie XML | IncomingDocumentToLearnHowToHandleOptionalAttributes.xml.     |
| Przewodniki po zadaniach                | RCS Importowanie plików w formacie XML z opcjonalnymi atrybutami.axtr |


W poniższych krokach wyjaśniono, jak użytkownik w roli administratora systemu lub programisty raportowania elektronicznego może zaprojektować konfigurację formatu ER do importowania plików w formacie XML zawierającym atrybuty opcjonalne. Aby wykonać te czynności, musisz najpierw wykonać kroki procedury [Utwórz dostawcę konfiguracji i oznacz go jako aktywnego](tasks/er-configuration-provider-mark-it-active-2016-11.md). Przed rozpoczęciem należy pobrać i zapisać lokalnie plik IncomingDocumentToLearnHowToHandleOptionalAttributes.XML z centrum pobierania Microsoft (https://go.microsoft.com/fwlink/?linkid=874684 ).

1. Wybierz kolejno opcje **Administrowanie organizacją** > **Obszary robocze** > **Raportowanie elektroniczne**.
2. Upewnij się, że dostawca konfiguracji dla przykładowej firmy Litware, Inc. jest dostępny i oznaczony jako **Aktywny** Jeśli ten dostawca konfiguracji nie jest widoczny, wykonaj kroki w [Tworzenie dostawcy konfiguracji i oznaczanie go jako aktywnego](tasks/er-configuration-provider-mark-it-active-2016-11.md).
3. Kliknij opcję **Konfiguracje raportowania**.

## <a name="create-a-new-data-model-configuration"></a>Tworzenie nowej konfiguracji modelu danych
1. Kliknij przycisk **Utwórz konfigurację**, aby otworzyć rozwijane okno dialogowe.
2. W polu **Nazwa** wpisz „Model do importu pliku XML”.
3. Kliknij przycisk **Utwórz konfigurację**.
4. Kliknij przycisk **Konstruktor**.
5. Kliknij przycisk **Nowy** aby otworzyć rozwijane okno dialogowe.
6. W polu **Nazwa** wpisz „Element główny”.
7. Kliknij przycisk **Dodaj**.
8. Kliknij przycisk **Nowy** aby otworzyć rozwijane okno dialogowe.
9. W polu **Nazwa** wpisz „Lista”.
10. W polu **Kod przedmiotu** wybierz **Lista tabel**.
11. Kliknij przycisk **Dodaj**.
12. Kliknij przycisk **Nowy** aby otworzyć rozwijane okno dialogowe.
13. W polu **Nazwa** wpisz „Kod”.
14. W polu **Typ przedmiotu** wybierz **Ciąg**.
15. Kliknij przycisk **Dodaj**.
16. Kliknij przycisk **Zapisz**.
17. Zamknij stronę.
18. Kliknij przycisk **Zmień stan**.
19. Kliknij przycisk **Wykonaj.**
20. Kliknij przycisk **OK**.

## <a name="create-a-format-for-data-import"></a>Tworzenie formatu importu danych
1. Kliknij przycisk **Utwórz konfigurację**, aby otworzyć rozwijane okno dialogowe.
2. W polu **Nowy** wpisz „Format oparty na modelu danych Model do importowania pliku xml”.
3. W polu **Nazwa** wpisz „Format do importu pliku XML”. 
4. Wybierz opcję **Tak** w polu **Obsługuje import danych**.
5. Kliknij przycisk **Utwórz konfigurację**.

## <a name="design-a-format-to-parse-incoming-file-in-xml-format"></a>Umożliwia zaprojektowanie formatu w celu przeanalizowania pliku przychodzącego w formacie XML
1. Kliknij przycisk **Konstruktor**.
2. Kliknij przycisk **Dodaj element główny**, aby otworzyć rozwijane okno dialogowe.
3. W drzewie zaznacz element **XML\Element**.
4. W polu **Nazwa** wpisz „Element główny”.
5. Kliknij przycisk **OK**.
6. Kliknij przycisk **Dodaj**, aby otworzyć rozwijane okno dialogowe.
7. W drzewie zaznacz element **XML\Element**.
8. W polu **Nazwa** wpisz „dokument”.
9. W polu **Wielość** wybierz opcję **Jeden wiele**.
10. Kliknij przycisk **OK**.
11. W drzewie wybierz **element główny\dokument**.
12. Kliknij przycisk **Dodaj**, aby otworzyć rozwijane okno dialogowe.
13. W drzewie zaznacz element **XML\Atrybut**.
14. W polu **Nazwa** wpisz „id”.
15. Kliknij przycisk **OK**.
16. Kliknij przycisk **Zapisz**.

## <a name="design-a-format-mapping-to-save-parsed-information-to-data-model"></a>Umożliwia zaprojektowanie mapowania formatu w celu zapisania przeanalizowanej informacji w modelu danych
1.  Kliknij opcję **Mapuj format na model**.
2.  Kliknij przycisk **Nowy**.
3.  W polu **Definicja** wprowadź lub wybierz wartość.
4.  W polu **Nazwa** wpisz „mapowanie”.
5.  Kliknij przycisk **Zapisz**.
6.  Kliknij przycisk **Konstruktor**.
7.  W drzewie rozwiń węzeł **format**.
8.  W drzewie rozwiń węzeł **format\root: XML Element (root)**.
9.  W drzewie wybierz **1format\root: XML Element(root)\document: XML Element 1..* (dokument)**.
10. Kliknij opcję **Powiąż**.
11. W drzewie rozwiń **format\root: XML Element(root)\document: XML Element 1..* (dokument)**.
12. W drzewie wybierz **1format\root: XML Element(root)\document: XML Element 1..* (dokument)\id**.
13. W drzewie rozwiń węzeł **List = format.root.document**.
14. W drzewie wybierz **List = format.root.document\Code**.
15. Kliknij opcję **Powiąż**.
16. Kliknij przycisk **Zapisz**.
17. Zamknij stronę.

## <a name="run-format-mapping"></a>Uruchom mapowanie formatu
1. Kliknij przycisk **Uruchom.**
2. Kliknij przycisk **Przeglądaj** i wybierz plik **IncomingDocumentToLearnHowToHandleOptionalAttributes.xml**.
3. Kliknij przycisk **OK**.

> [!NOTE]
> Wybrany plik nie został zaimportowany, ponieważ projekt formatu przyjmuje istnienie atrybutu „ID” dla elementu „Document”, ale importowany plik nie zawiera takiego atrybutu.

## <a name="modify-format-structure-to-handle-xml-attribute-as-optional"></a>Modyfikowanie struktury formatu w celu obsługi atrybutu XML jako opcjonalnego
1. Zamknij stronę.
2. W drzewie rozwiń **element główny\dokument**.
3. W drzewie wybierz **element główny\dokument\id**.
4. Wybierz wartość **Tak** w polu **Ciąg pusty dla brakującego atrybutu**.
5. Kliknij przycisk **Zapisz**.

## <a name="run-format-mapping-to-test-changes"></a>Uruchom mapowanie formatu w celu przetestowania zmian
1. Kliknij opcję **Mapuj format na model**.
2. Kliknij przycisk **Uruchom.**
3. Kliknij przycisk **Przeglądaj** i wybierz plik **IncomingDocumentToLearnHowToHandleOptionalAttributes.xml**.
4. Kliknij przycisk **OK**.
5. Przejrzyj wygenerowany plik. Zauważmy, że ten sam plik został zaimportowany, ponieważ projekt formatu uwzględnia teraz atrybut „id” dla elementu „dokument” jako opcjonalny.
