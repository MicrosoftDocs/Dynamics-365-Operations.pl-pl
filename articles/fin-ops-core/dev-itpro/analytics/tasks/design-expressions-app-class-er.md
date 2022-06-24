---
title: Projektowanie wyrażeń ER do wywoływania metod klas aplikacji
description: Ten artykuł zawiera informacje, jak ponownie użyć istniejącej logiki aplikacji w konfiguracjach elektronicznego raportowania poprzez wywołanie wymaganych metod klas aplikacji w wyrażeniach ER.
author: NickSelin
ms.date: 11/02/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0fb0a9725d882fdc330d7adbb49bd3dcadf7805f
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8883633"
---
# <a name="design-er-expressions-to-call-application-class-methods"></a>Projektowanie wyrażeń ER do wywoływania metod klas aplikacji

[!include [banner](../../includes/banner.md)]

Ten artykuł zawiera informacje, jak ponownie użyć istniejącej logiki aplikacji w konfiguracjach [elektronicznego raportowania (RE)](../general-electronic-reporting.md) przez wywołanie wymaganych metod klas aplikacji w wyrażeniach ER. Wartości argumentów dla wywołania klas mogą być dynamicznie definiowane w czasie wykonywania. Na przykład w celu zapewnienia poprawności wartości mogą być oparte na informacjach z dokumentu analizy.

Na przykład w tym artykule zaprojektujesz proces, który analizuje przychodzące wyciągi bankowe pod kątem aktualizacji danych aplikacji. Przychodzące wyciągi bankowe będą odbierane w formacie tekstowym (txt) zawierających kody IBAN (International Bank Account Number). W ramach procesu importu wyciągów bankowych należy zweryfikować poprawność kodu IBAN za pomocą dostępnej już logiki.

## <a name="prerequisites"></a>Wymagania wstępne

Procedury opisane w tym artykule są przeznaczone dla użytkowników, którym przypisano rolę **Administrator systemu** lub **Programista raportowania elektronicznego**.

Procedury można wykonać przy użyciu dowolnego zestawu danych.

Aby je ukończyć, musisz pobrać i zapisać następujący plik: [SampleIncomingMessage.txt](https://download.microsoft.com/download/8/0/a/80adbc89-f23c-46d9-9241-e0f19125c04b/SampleIncomingMessage.txt).

W tym artykule utworzysz wymagane konfiguracje ER dla przykładowej firmy Litware, Inc. Dlatego przed wykonaniem procedur opisanych w tym artykule należy wykonać następujące kroki.

1. Wybierz kolejno opcje **Administrowanie organizacją** \> **Obszary robocze** \> **Raportowanie elektroniczne**.
2. Na stronie **Konfiguracje lokalizacji** sprawdź, czy dostawca konfiguracji dla przykładowej firmy **Litware, Inc.** jest dostępny i oznaczony jako aktywny. Jeśli ten dostawca konfiguracji nie jest widoczny, należy najpierw wykonać procedurę [Tworzenie dostawcy konfiguracji i oznaczanie go jako aktywnego](er-configuration-provider-mark-it-active-2016-11.md).

## <a name="import-a-new-er-model-configuration"></a>Importowanie nowej konfiguracji modelu ER

1. Na stronie **Konfiguracje lokalizacji** w sekcji **Dostawcy konfiguracji** wybierz kafelek dostawcy konfiguracji **Microsoft**.
2. Wybierz **Repozytoria**.
3. Na **stronie Repozytoria lokalizacji** wybierz pozycję **Pokaż filtry**.
4. Aby wybrać rekord repozytorium globalnego, dodaj pole filtru **Nazwa**.
5. W polu **Nazwa** wprowadź nazwę **Globalne**. Następnie wybierz operator filtru **zawiera**.
6. Wybierz opcję **Zastosuj**.
7. Wybierz **[Otwórz](../er-download-configurations-global-repo.md#open-configurations-repository)**, aby wyświetlić listę konfiguracji modułu ER dla wybranego repozytorium.
8. Na stronie **Repozytorium konfiguracji** w drzewie konfiguracji wybierz pozycję Model płatności **Przykładowy raport arkusza**.
9. Na skróconej karcie **Wersje**, jeśli przycisk **Importuj** jest dostępny, zaznacz go, a następnie wybierz **Tak**.

    Jeśli przycisk **Importuj** jest niedostępny, oznacza to, że zaimportowano już wybraną wersję konfiguracji **Model płatności** ER.

10. Zamknij **stronę Repozytorium konfiguracji**, a następnie stronę **Repozytorium lokalizacji**.

## <a name="add-a-new-er-format-configuration"></a>Dodawanie nowej konfiguracji formatu ER

Dodaj nowy format ER do analizowania przychodzących wyciągów bankowych w formacie TXT.

1. Na stronie **Konfiguracje lokalizacji** i wybierz kafelek **Konfiguracje raportowania**.
2. Na stronie **Konfiguracje** w drzewie konfiguracji w panelu po lewej wybierz pozycję **Model płatności**.
3. Wybierz **Utwórz konfigurację**. 
4. W oknie dialogowym rozwijanym wykonaj następujące kroki:

    1. W polu **Nowy** wpisz **Format oparty na modelu danych PaymentModel**.
    2. W polu **Nazwa** wpisz **Format importu wyciągu bankowego (przykładowy)**.
    3. W polu **Obsługuje import danych** wybierz opcję **Tak**.
    4. Wybierz **Stwórz konfiguracj**, aby zakończyć tworzenie konfiguracji.

## <a name="design-the-er-format-configuration--format"></a>Projektowanie konfiguracji formatu ER – Format

Zaprojektuj format ER, który reprezentuje oczekiwaną strukturę pliku zewnętrznego w formacie TXT.

1. W **dodanej konfiguracji formatu importu wyciągu bankowego (przykładowy)** wybierz pozycję **Konstruktor**.
2. Na stronie **Projektant formatów** w drzewie struktury formatu w lewym okienku wybierz **Dodaj katalog główny**.
3. W wyświetlonym oknie dialogowym wykonaj następujące kroki:

    1. W drzewie wybierz pozycję **Tekst\\Sekwencja**, aby dodać składnik formatu **sekwencji**.
    2. W polu **Nazwa** wprowadź nazwę **Element główny**.
    3. W polu **Znaki specjalne** wybierz opcję **Nowy wiersz — Windows (CR LF)**. Na podstawie tego ustawienia każdy wiersz analizy pliku musi być traktowany jako oddzielny rekord.
    4. Kliknij przycisk **OK**.

4. Wybierz opcję **Dodaj**.
5. W wyświetlonym oknie dialogowym wykonaj następujące kroki:

    1. W drzewie zaznacz element **Tekst\\Sekwencja**.
    2. W polu **Nazwa** wprowadź nazwę **Wiersze**.
    3. W polu **Wielość** wybierz opcję **Jeden wiele**. Na podstawie tego ustawienia oczekuje się, że w pliku analizy będzie znajdować się co najmniej jeden wiersz.
    4. Kliknij przycisk **OK**.

6. W drzewie wybierz opcję **Element główny\\Wiersze**, a następnie wybierz **Dodaj sekwencję**.
7. W wyświetlonym oknie dialogowym wykonaj następujące kroki:

    1. W polu **Nazwa** wprowadź nazwę **Pola**.
    2. W polu **Liczebność** zaznacz opcję **Dokładnie jeden**.
    3. Kliknij przycisk **OK**.

8. W drzewie wybierz opcję **Element główny\\Wiersze\\Pola**, a następnie wybierz **Dodaj**.
9. W wyświetlonym oknie dialogowym wykonaj następujące kroki:

    1. W drzewie zaznacz element **Tekst\\Ciąg**.
    2. Wprowadź **nazwę** w polu, wpisz **IBAN**.
    3.. Kliknij przycisk **OK**.

10. Wybierz opcję **Zapisz**.

Konfiguracja jest teraz ustawiona tak, że każda linia w pliku parsowania zawiera tylko kod IBAN.

![Konfiguracja formatu importu wyciągów bankowych (przykład) na stronie Projektant formatów.](../media/design-expressions-app-class-er-01.png)

## <a name="design-the-er-format-configuration--mapping-to-a-data-model"></a>Projektowanie konfiguracji formatu ER – Mapowanie do modelu danych

Projektowanie mapowania formatu ER, które używa informacji z pliku analizy do wypełnienia modelu danych.

1. Wybierz opcję **Projektant formatów** w okienku akcji, aby otworzyć stronę **Mapowanie formatu do modelu**.
2. Wybierz opcję **Nowe** w okienku akcji, aby otworzyć stronę **Modelowanie do mapowania źródła danych**.
3. W polu **Definicja** wybierz **BankToCustomerDebitCreditNotificationInitiation**.
4. W polu **Nazwa** wpisz **Mapowanie do modelu danych**.
5. Wybierz opcję **Zapisz**.
6. Wybierz opcję **Konstruktor**.
7. Na stronie **Projektant mapowania modelu** w drzewie **Typy źródła danych** wybierz pozycję **Dynamics 365 for Operations\\Klasa**.
8. W sekcji **Źródła danych** wybierz pozycję **Dodaj główny**, aby dodać źródło danych, które wywołuje istniejącą logikę aplikacji dla weryfikacji kodów IBAN.
9. W wyświetlonym oknie dialogowym wykonaj następujące kroki:

    1. W polu **Nazwa** wpisz **Sprawdź\_kody**.
    2. W polu **klasy** wybierz lub wpisz **ISO7064**.
    3. Kliknij przycisk **OK**.

10. W drzewie **Typy źródła danych** wykonaj następujące kroki:

    1. Rozwiń źródło danych **formatu**.
    2. Rozwiń węzeł **format\\Główny: Sequence(Root)**.
    3. Rozwiń węzeł **format\\Główny: Sequence(Root)\\Rows: Sequence 1..\* (Rows)**.
    4. Rozwiń węzeł **format\\Root: Sequence(Root)\\Rows: Sequence 1..\* (Rows)\\Fields: Sequence 1..1 (Fields)**.

11. W drzewie **Model danych** wykonaj następujące kroki:

    1. Rozwiń pole **Płatności** modelu danych.
    2. Rozwiń **Payments\\Creditor Account(CreditorAccount)**.
    3. Rozwiń **Payments\\Creditor Account(CreditorAccount)\\Identification**.
    4. Rozwiń **Payments\\Creditor Account(CreditorAccount)\\Identification\\IBAN**.

12. Aby powiązać składniki skonfigurowanego formatu ze polami modelu danych, należy wykonać następujące kroki:

    1. Wybierz **format\\Główny: Sequence(Root)\\Rows: Sequence 1..\* (Rows)**.
    2. Wybierz **płatność**.
    3. Wybierz **Powiąż**. Na podstawie tego ustawienia każdy wiersz w pliku analizy będzie traktowany jako pojedyncza płatność.
    4. Wybierz **format\\Root: Sequence(Root)\\Rows: Sequence 1..\* (Rows)\\Fields: Sequence 1..1 (Fields)\\IBAN: String(IBAN)**.
    5. Wybierz **Payments\\Creditor Account(CreditorAccount)\\Identification\\IBAN**.
    6. Wybierz **Powiąż**. Na podstawie tego ustawienia pole **IBAN** modelu danych zostanie wypełnione wartością z pliku analizy.

    ![Powiązanie składników formatu z polami modelu danych na stronie projektanta mapowania modelu.](../media/design-expressions-app-class-er-02.png)

13. Na karcie **Weryfikacje** wykonaj następujące kroki, aby dodać regułę [sprawdzania](../general-electronic-reporting-formula-designer.md#Validation) poprawności, która wyświetla komunikat o błędzie dla każdego wiersza w pliku analizy, który zawiera nieprawidłowy kod IBAN:

    1. Wybierz **Nowy**, a następnie wybierz opcję **Edytuj warunek**.
    2. Na stronie **Projektant formuł** w drzewie **Źródło danych** rozwiń źródło danych **Check\_codes**, które reprezentuje klasę aplikacji **ISO7064**, aby wyświetlić dostępne metody tej klasy.
    3. Wybierz **Check\_codes\\verifyMOD1271\_36**.
    4. Wybierz **Dodaj źródło danych**.
    5. W polu **Formuła** wpisz następujące [wyrażenie](../general-electronic-reporting-formula-designer.md#Binding): **Check\_codes.verifyMOD1271\_36(format.Root.Rows.Fields.IBAN)**.
    6. Wybierz przycisk **Zapisz** i zamknij stronę.
    7. Wybierz **Edytuj wiadomość**.
    8. Na stronie **Projektant formuł** w polu **Formuła** wpisz **CONCATENATE("Invalid IBAN code has been found:&nbsp;", format.Root.Rows.Fields.IBAN)**.
    9. Wybierz przycisk **Zapisz** i zamknij stronę.

    Na podstawie tych ustawień warunek walidacji zwróci *[FALSE](../er-formula-supported-data-types-primitive.md#boolean)* dla każdego nieprawidłowego kodu IBAN, wywołując istniejący **verifyMOD1271\_36** metoda klasy aplikacji **ISO7064**. Zauważ, że wartość kodu IBAN jest definiowana dynamicznie w czasie wykonywania jako argument metody wywołującej, na podstawie zawartości parsowanego pliku tekstowego.

    ![Reguła walidacji na stronie Projektant mapowania modelu.](../media/design-expressions-app-class-er-03.png)

14. Wybierz opcję **Zapisz**.
15. Zamknij stronę **konstruktora mapowania modelu**, a następnie stronę **Mapowanie modelu do źródła danych**.

## <a name="run-the-format-mapping"></a>Uruchamianie mapowania

W celach testowych uruchom mapowanie formatu przy użyciu pobranego wcześniej pliku SampleIncomingMessage.txt. Wygenerowane dane wyjściowe będą zawierać dane, które są importowane z wybranego pliku tekstowego i przenoszone do niestandardowego modelu danych podczas rzeczywistego importu.

1. Na stronie **Mapowanie modelu na źródło danych** wybierz **Uruchom**.
2. Na stronie **Parametry raportu elektronicznego** wybierz pozycję **Przeglądaj**, przejdź do pobranego pliku **SampleIncomingMessage.txt** i wybierz go.
3. Kliknij przycisk **OK**.
4. Zwróć uwagę, że na stronie **mapowania modelu na źródło danych** wyświetlany jest komunikat o błędzie o nieprawidłowym kodzie IBAN.

    ![Wynik uruchomienia mapowania formatu na stronie mapowania modelu na źródło danych.](../media/design-expressions-app-class-er-04.png)

5. Przejrzyj dane wyjściowe w formacie XML, które reprezentują dane zaimportowane z wybranego pliku i przeniesione do modelu danych. Należy zauważyć, że tylko trzy wiersze zaimportowanego pliku tekstowego zostały przetworzone bez błędów. Kod IBAN online 4 jest nieprawidłowy i został pominięty.

    ![Dane wyjściowe XML.](../media/design-expressions-app-class-er-05.png)

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
