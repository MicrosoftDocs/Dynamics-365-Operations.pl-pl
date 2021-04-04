---
title: (RCS) Importowanie plików w formacie XML z opcjonalnymi atrybutami
description: Ten temat zawiera informacje o sposobach projektowania konfiguracji formatu ER w celu importowania plików w formacie XML zawierających atrybuty opcjonalne.
author: NickSelin
manager: AnnBe
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-07-28
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ef090270b2e521b870697bb238b50ea92d4f6958
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2021
ms.locfileid: "5565693"
---
# <a name="rcs-import-files-in-xml-format-with-optional-attributes"></a>(RCS) Importowanie plików w formacie XML z opcjonalnymi atrybutami

[!include [banner](../../includes/banner.md)]

W poniższych krokach wyjaśniono, jak użytkownik w roli administratora systemu lub programisty raportowania elektronicznego może zaprojektować konfigurację formatu ER do importowania plików w formacie XML zawierającym atrybuty opcjonalne. Aby wykonać te kroki, należy najpierw wykonać kroki w procedurze „Tworzenie dostawcy konfiguracji i oznaczanie go jako aktywnego”. Przed rozpoczęciem należy pobrać i zapisać lokalnie plik IncomingDocumentToLearnHowToHandleOptionalAttributes. XML z [centrum pobierania Microsoft](https://go.microsoft.com/fwlink/?linkid=874684).

1.    Otwórz **Wszystkie miejsca prac** > **Electroniczne Raportowanie**.
2.    Upewnij się, że dostawca konfiguracji dla przykładowej firmy Litware, Inc. jest dostępny i oznaczony jako **Aktywny** Jeśli ten dostawca konfiguracji nie jest widoczny, wykonaj procedurę [Utwórz dostawców konfiguracji i oznacz ich jako aktywnych](er-configuration-provider-mark-it-active-2016-11.md).
3.    Kliknij opcję **Konfiguracje raportowania**.

## <a name="create-a-new-data-model-configuration"></a>Tworzenie nowej konfiguracji modelu danych
1.    Kliknij przycisk **Utwórz konfigurację**, aby otworzyć rozwijane okno dialogowe.
2.    W polu **Nazwa** wpisz „Model do importu pliku XML”.
3.    Kliknij przycisk **Utwórz konfigurację**.
4.    Kliknij przycisk **Konstruktor**.
5.    Kliknij przycisk **Nowy** aby otworzyć rozwijane okno dialogowe.
6.    W polu **Nazwa** wpisz „Element główny”.
7.    Kliknij przycisk **Dodaj**.
8.    Kliknij przycisk **Nowy** aby otworzyć rozwijane okno dialogowe.
9.    W polu **Nazwa** wpisz „Lista”.
10.    W polu **Kod przedmiotu** wybierz **Lista tabel**.
11.    Kliknij przycisk **Dodaj**.
12.    Kliknij przycisk **Nowy** aby otworzyć rozwijane okno dialogowe.
13.    W polu **Nazwa** wpisz „Kod”.
14.    W polu **Typ przedmiotu** wybierz **Ciąg**.
15.    Kliknij przycisk **Dodaj**.
16.    Kliknij przycisk **Zapisz**.
17.    Zamknij stronę.
18.    Kliknij przycisk **Zmień stan**.
19.    Kliknij przycisk **Wykonaj.**
20.    Kliknij przycisk **OK**.

## <a name="create-a-format-for-data-import"></a>Tworzenie formatu importu danych
1.    Kliknij przycisk **Utwórz konfigurację**, aby otworzyć rozwijane okno dialogowe.
2.    W polu **Nowy** wpisz „Format oparty na modelu danych Model do importowania pliku xml”.
3.    W polu **nazwa** wpisz „format do importu pliku XML”.
4.    Wybierz opcję **Tak** w polu **Obsługuje import danych**.
5.    Kliknij przycisk **Utwórz konfigurację**.

## <a name="design-a-format-to-parse-incoming-file-in-xml-format"></a>Umożliwia zaprojektowanie formatu w celu przeanalizowania pliku przychodzącego w formacie XML
1.    Kliknij przycisk **Konstruktor**.
2.    Kliknij przycisk **Dodaj element główny**, aby otworzyć rozwijane okno dialogowe.
3.    W drzewie zaznacz element **XML\Element**.
4.    W polu **Nazwa** wpisz „Element główny”.
5.    Kliknij przycisk **OK**.
6.    Kliknij przycisk **Dodaj**, aby otworzyć rozwijane okno dialogowe.
7.    W drzewie zaznacz element **XML\Element**.
8.    W polu **Nazwa** wpisz „dokument”.
9.    W polu **Wielość** wybierz opcję **Jeden wiele**.
10.    Kliknij przycisk **OK**.
11.    W drzewie wybierz **element główny\dokument**.
12.    Kliknij przycisk **Dodaj**, aby otworzyć rozwijane okno dialogowe.
13.    W drzewie zaznacz element **XML\Atrybut**.
14.    W polu **Nazwa** wpisz „Identyfikator”.
15.    Kliknij przycisk **OK**.
16.    Kliknij przycisk **Zapisz**.

## <a name="design-a-format-mapping-to-save-parsed-information-to-data-model"></a>Umożliwia zaprojektowanie mapowania formatu w celu zapisania przeanalizowanej informacji w modelu danych
1. Kliknij opcję **Mapuj format na model**.
2. Kliknij przycisk **Nowy**.
3. W polu **Definicja** wprowadź lub wybierz wartość.
4. Na liście kliknij łącze w wybranym wierszu.
5. W polu **Nazwa** wpisz „mapowanie”.
6. Kliknij przycisk **Zapisz**.
7. Kliknij przycisk **Konstruktor**.
8. W drzewie rozwiń węzeł **format**.
9. W drzewie rozwiń **format\root: XML Element(root)**.
10.    W drzewie wybierz **format\root: XML Element(root)\document: XML Element 1..* (dokument)**.
11.    Kliknij **Powiąż**.
12.    W drzewie rozwiń **format\root: XML Element(root)\document: XML Element 1..* (dokument)**.
13.    W drzewie wybierz **format\root: XML Element(root)\document: XML Element 1..* (dokument)\identyfikator**.
14.    W drzewie rozwiń węzeł **List = format.root.document**.
15.    W drzewie wybierz **List = format.root.document\Code**.
16.    Kliknij opcję **Powiąż**.
17.    Kliknij przycisk **Zapisz**.
18.    Zamknij stronę.
 
## <a name="run-format-mapping"></a>Uruchom Mapowanie formatu
1. Kliknij przycisk **Uruchom.**
2. Kliknij przycisk **Przeglądaj** i wybierz **IncomingDocumentToLearnHowToHandleOptionalAttributes.xml**.
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
5. Przejrzyj wygenerowany plik. 

> [!NOTE]
> Ten sam plik został zaimportowany jako projekt formatu; traktuj atrybut „identyfikator” dla elementu „dokument” jako opcjonalny.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]