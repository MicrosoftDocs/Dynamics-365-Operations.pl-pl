---
title: Debugowanie źródeł danych dla wykonanego formatu ER w celu analizowania przekształcenia i przepływu danych
description: W tym temacie wyjaśniono, jak można debugować źródła danych wykonanego formatu ER w celu lepszego zrozumienia skonfigurowanego przekształcenia i przepływu danych.
author: NickSelin
ms.date: 04/22/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, EROperationDesigner
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-04-01
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: ba8f20e7b4ca6579016fa60d0bbf69f7b4e9c7d3
ms.sourcegitcommit: 25b3dd639e41d040c2714f56deadaa0906e4b493
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/06/2021
ms.locfileid: "7605388"
---
# <a name="debug-data-sources-of-an-executed-er-format-to-analyze-data-flow-and-transformation"></a>Debugowanie źródeł danych dla wykonanego formatu ER w celu analizowania przekształcenia i przepływu danych

[!include[banner](../includes/banner.md)]

[!include[banner](../includes/preview-banner.md)]

Podczas [konfigurowania](tasks/er-format-configuration-2016-11.md) rozwiązania Raportowanie elektroniczne (ER) w celu generowania dokumentów wychodzących należy zdefiniować metody, które są używane do uzyskiwania danych z aplikacji i wprowadzania ich do generowanych danych wyjściowych. Aby zapewnić wydajniejszą obsługę cyklu życia rozwiązania ER, powinno ono składać się z [modelu danych ER](general-electronic-reporting.md#DataModelComponent) i jego składników [mapowania](general-electronic-reporting.md#ModelMappingComponent), a także z [formatu ER](general-electronic-reporting.md#FormatComponentOutbound) i jego składników mapowania, dzięki czemu mapowanie modelu jest właściwe dla aplikacji, natomiast inne składniki pozostają niezależne od aplikacji. Z tego powodu kilka składników rozwiązania ER może [wpłynąć na](general-electronic-reporting.md#FormatComponentOutbound) proces wprowadzania danych w wygenerowanych danych wyjściowych.

Czasami dane wygenerowanego wyniku wyglądają inaczej niż te same dane w bazie danych aplikacji. W takich przypadkach określisz, który składnik ER jest odpowiedzialny za przekształcenie danych. Funkcja debugera źródła danych ER znacznie skraca czas i redukuje koszty związane z takim badaniem. Możesz przerwać wykonywanie formatu ER i otworzyć interfejs debugera źródła danych. Można w nim przeglądać dostępne źródła danych i wybierać pojedyncze źródło danych do wykonania. Takie wykonanie ręczne symuluje wykonywanie źródła danych podczas rzeczywistego uruchamiania formatu ER. Wynik jest przedstawiany na stronie, na której można analizować odebrane dane.

Aby włączyć funkcję debugowania źródła danych, w obszarze parametrów użytkownika rozwiązania ER ustaw opcję **Włącz debugowanie danych podczas uruchamiania formatu** na **Tak**. Następnie możesz rozpocząć debugowanie źródła danych podczas uruchamiania formatu ER w celu wygenerowania dokumentów wychodzących. Możesz również użyć opcji **Rozpocznij debugowanie**, aby zainicjować debugowanie źródła danych dla formatu ER skonfigurowanego w [projektancie operacji ER](./tasks/er-format-configuration-2016-11.md#design-the-format-of-an-electronic-document).

W tym temacie przedstawiono wytyczne dotyczące inicjowania debugowania źródła danych dla wykonywanych formatów ER. Wyjaśniono w nim, jak informacje mogą pomóc w zrozumieniu przepływu danych i przekształceń danych. Przykłady przedstawione w tym temacie używają procesu biznesowego do przetwarzania płatności dostawców.

## <a name="limitations"></a>Ograniczenia

Debuger źródła danych może służyć do uzyskiwania dostępu do danych źródeł danych używanych w formatach ER uruchamianych w celu wygenerowania dokumentów wychodzących. Nie można używać go do debugowania źródeł danych w formatach ER zaprojektowanych z myślą o analizowaniu dokumentów przychodzących.

Następujące ustawienia formatów ER nie są obecnie dostępne w przypadku debugowania źródła danych:

- Przekształcenia formatu
- Reguły walidacji formatu i mapowania
- Włączanie wyrażeń
- Szczegóły zbierania danych w pamięci

## <a name="prerequisites"></a>Wymagania wstępne

- Aby wykonać przykłady opisane w tym temacie, trzeba mieć dostęp do jednej z następujących [ról](../sysadmin/tasks/assign-users-security-roles.md):

    - Deweloper raportowania elektronicznego
    - Konsultant funkcjonalny raportowania elektronicznego
    - Administrator systemu

- Firmę należy ustawić na wartość **DEMF**.

- Wykonaj kroki opisane w [dodatku 1](#appendix1) do tego tematu, aby pobrać składniki rozwiązania Microsoft ER wymagane do przetwarzania płatności dostawców.
- Wykonaj kroki opisane w [dodatku 2](#appendix2) do tego tematu, aby przygotować rozrachunki z dostawcami na potrzeby przetwarzania płatności dostawców przy użyciu pobranego rozwiązania ER.

## <a name="process-a-vendor-payment-to-get-a-payment-file"></a>Przetwarzanie płatności dostawcy w celu pobrania pliku płatności

1. Wykonaj kroki opisane w [dodatku 3](#appendix3) do tego tematu, aby przetworzyć płatności dostawców.

    ![Przetwarzanie płatności dostawcy w toku.](./media/er-data-debugger-process-payment.png)

2. Pobierz i zapisz plik ZIP na komputerze lokalnym.
3. Wyodrębnij plik płatności **ISO20022 Credit transfer.xml** z pliku ZIP.
4. Otwórz wyodrębniony plik płatności, korzystając z przeglądarki plików XML.

    W pliku płatności kod IBAN (International Bank Account Number) konta bankowego dostawcy nie zawiera spacji. W związku z tym różni się od wartości [wprowadzonej](#enteredIBANcode) na stronie **Konta bankowe**.

    ![Kod IBAN bez spacji.](./media/er-data-debugger-payment-file.png)

    Możesz użyć debugera źródeł danych ER możesz sprawdzić, który składnik rozwiązania ER jest używany do obcinania spacji w kodzie IBAN.

## <a name="turn-on-data-source-debugging"></a>Włączanie debugowania źródła danych

1. Otwórz **Administracja organizacji** \> **Elektroniczne raportowanie** \> **Konfiguracje**.
2. Na stronie **Konfiguracje** w okienku akcji na karcie **Konfiguracje** w grupie **Ustawienia zaawansowane** wybierz opcję **Parametry użytkownika**.
3. Ustaw opcję **Włącz debugowanie danych podczas uruchamiania formatu** na wartość **Tak**.

    > [!NOTE]
    > Ten parametr jest właściwy dla użytkownika i właściwy dla firmy.

    ![Okno dialogowe parametry użytkownika.](./media/er-data-debugger-user-parameters.png)

## <a name="process-a-vendor-payment-for-debugging"></a>Przetwarzanie płatności dostawcy na potrzeby debugowania

1. Wykonaj kroki opisane w [dodatku 3](#appendix3) do tego tematu, aby przetworzyć płatności dostawców.
2. W oknie komunikatu wybierz opcję **Tak**, aby potwierdzić, że chcesz przerwać przetwarzanie płatności dostawców i w zamian uruchomić debugowanie źródła danych na stronie **Debugowanie źródeł danych**.

    ![Okno komunikatu potwierdzającego.](./media/er-data-debugger-start-debugging.png)

## <a name="debug-data-sources-that-are-used-in-payment-processing"></a>Debugowanie źródeł danych używanych podczas przetwarzania płatności

### <a name="debug-the-model-mapping"></a>Debugowanie mapowania modelu

1. Na stronie **Debugowanie źródeł danych** w okienku akcji wybierz pozycję **Mapowanie modelu** w celu rozpoczęcia debugowania z tego składnika ER.
2. W okienku źródła danych po lewej stronie wybierz źródło danych **\$notSentTransactions**, a następnie wybierz pozycję **Odczytaj wszystkie rekordy**.

    Możesz wybrać pozycję **Odczytaj 1 rekord**, **Odczytaj 10 rekordów**, **Odczytaj 100 rekordów** lub **Odczytaj wszystkie rekordy**, aby wymusić odczytanie odpowiedniej liczby rekordów z wybranego źródła danych. W ten sposób można symulować dostęp do źródła danych z poziomu uruchomionego formatu ER.

3. W okienku danych po prawej stronie wybierz opcję **Rozwiń wszystko**.

    Zobaczysz, czy wybrane źródło danych typu **Lista rekordów** zawiera pojedynczy rekord.

4. Rozwiń źródło danych **\$notSentTransactions** i wybierz zagnieżdżoną metodę **vendBankAccountInTransactionCompany()**.
5. Rozwiń metodę **vendBankAccountInTransactionCompany()** i wybierz zagnieżdżone pole **IBAN**.
6. Wybierz pozycję **Pobierz wartość**.

    Możesz wybrać pozycję **Pobierz wartość**, aby wymusić odczytywanie wartości wybranego pola w wybranym źródle danych. W ten sposób można symulować dostęp do tego pola z poziomu uruchomionego formatu ER.

7. Wybierz **Rozwiń wszystkie**.

    ![Wartość pola IBAN w mapowaniu modelu.](./media/er-data-debugger-debugging-model-mapping.png)

    Jak widzisz, mapowanie modelu nie odpowiada za obcięte spacje, ponieważ zwrócony przez nie kod IBAN dla konta bankowego dostawcy zawiera spacje. Dlatego musisz kontynuować debugowanie źródła danych.

### <a name="debug-the-format-mapping"></a>Debugowanie mapowania formatu

1. Na stronie **Debugowanie źródeł danych** w okienku akcji wybierz pozycję **Mapowanie formatu** w celu kontynuowania debugowania z tego składnika ER.
2. Wybierz źródło danych **\$PaymentByDebtor**, a następnie wybierz pozycję **Odczytaj wszystkie rekordy**.
3. Rozwiń pozycję **\$PaymentByDebtor**.
4. Rozwiń pozycję **\$PaymentByDebtor.Lines**, a następnie wybierz pozycję **Odczytaj wszystkie rekordy**.
5. Rozwiń pozycję **\$PaymentByDebtor.Lines.CreditorAccount**.
6. Rozwiń pozycję **\$PaymentByDebtor.Lines.CreditorAccount.Identification**, a następnie wybierz pozycję **\$PaymentByDebtor.Lines.CreditorAccount.Identification.IBAN**.
7. Wybierz pozycję **Pobierz wartość**.
8. Wybierz **Rozwiń wszystkie**.

    ![Wartość pola IBAN w mapowaniu formatu.](./media/er-data-debugger-debugging-format-mapping.png)

    Jak widzisz, źródła danych mapowania formatu nie odpowiadają za obcięte spacje, ponieważ zwrócony przez nie kod IBAN dla konta bankowego dostawcy zawiera spacje. Dlatego musisz kontynuować debugowanie źródła danych.

### <a name="debug-the-format"></a>Debugowanie formatu

1. Na stronie **Debugowanie źródeł danych** w okienku akcji wybierz pozycję **Format** w celu kontynuowania debugowania z tego składnika ER.
2. Rozwiń elementy formatu, aby wybrać pozycję **ISO20022CTReports** \> **XMLHeader** \> **Document** \> **CstmrCdtTrfInitn** \> **PmtInf**, a następnie wybierz pozycję **Odczytaj wszystkie rekordy**.
3. Rozwiń elementy formatu, aby wybrać pozycję **ISO20022CTReports** \> **XMLHeader** \> **Document** \> **CstmrCdtTrfInitn** \> **PmtInf** \> **CdtTrfTxInf**, a następnie wybierz pozycję **Odczytaj wszystkie rekordy**.
4. Rozwiń elementy formatu, aby wybrać pozycję **ISO20022CTReports** \> **XMLHeader** \> **Document** \> **CstmrCdtTrfInitn** \> **PmtInf** \> **CdtTrfTxInf** \> **CdtrAcct** \> **Id** \> **IBAN** \> **BankIBAN**, a następnie wybierz pozycję **Pobierz wartość**.
5. Wybierz **Rozwiń wszystkie**.

    ![Wartość pola IBAN w formacie.](./media/er-data-debugger-debugging-format.png)

   Jak widzisz, powiązanie formatu nie odpowiada za obcięte spacje, ponieważ zwrócony przez nie kod IBAN dla konta bankowego dostawcy zawiera spacje. Z tego względu element **BankIBAN** został skonfigurowany do używania przekształcenia formatu, które obcina spacje.

6. Zamknij debuger źródła danych.

### <a name="review-the-format-transformations"></a>Przeglądanie przekształceń formatu

1. Otwórz **Administracja organizacji** \> **Elektroniczne raportowanie** \> **Konfiguracje**.
2. Na stronie **Konfiguracje** wybierz pozycję **Model płatności** \> **Polecenie przelewu ISO20022**.
3. Wybierz pozycję **Projektant**, a następnie rozwiń elementy w celu wybrania pozycji **Document** \> **CstmrCdtTrfInitn** \> **PmtInf** \> **CdtTrfTxInf** \> **CdtrAcct** \> **Id** \> **IBAN** \> **BankIBAN**.

    ![Element BankIBAN na stronie Projektant formatów.](./media/er-data-debugger-referred-transformation.png)

    Jak widzisz, element **BankIBAN** został skonfigurowany do używania przekształcenia **usuń niealfanumeryczne**.

4. Wybierz kartę **Przekształcenia**.

    ![Karta Przekształcenia dla elementu BankIBAN.](./media/er-data-debugger-transformation.png)

    Jak widzisz, przekształcenie typu **usuń niealfanumeryczne** zostało skonfigurowane do używania wyrażenia, które obcina spacje z podanego ciągu tekstowego.

## <a name="start-to-debug-in-the-operation-designer"></a>Rozpoczynanie debugowania w projektancie operacji

Podczas konfigurowania wersji roboczej formatu ER, który można uruchomić bezpośrednio z poziomu projektanta operacji, można uzyskać dostęp do debugera źródła danych, wybierając pozycję **Rozpocznij debugowanie** w okienku akcji.

![Przycisk Rozpocznij debugowanie na stronie Projektant formatów.](./media/er-data-debugger-run-from-designer.png)

Do debugowania jest dostępne mapowanie formatu oraz składniki formatu dla edytowanego formatu ER.

## <a name="start-to-debug-in-the-model-mapping-designer"></a>Rozpoczynanie debugowania w projektancie mapowania modelu

Podczas konfigurowania mapowania modelu ER, który można uruchomić bezpośrednio ze strony **Mapowanie modelu**, można uzyskać dostęp do debugera źródła danych, wybierając pozycję **Rozpocznij debugowanie** w okienku akcji.

![Przycisk Rozpocznij debugowanie na stronie projektanta mapowania modelu.](./media/er-data-debugger-run-from-designer-mapping.png)

Do debugowania jest dostępny składnik mapowania modelu dla edytowanego mapowania ER.

## <a name="appendix-1-get-an-er-solution"></a><a name="appendix1"></a>Dodatek 1: pobieranie rozwiązania ER

### <a name="download-an-er-solution"></a>Pobieranie rozwiązania ER

Jeśli chcesz użyć rozwiązania ER do wygenerowania pliku płatności elektronicznych dla przetwarzanej płatności dostawcy, możesz [pobrać](download-electronic-reporting-configuration-lcs.md) format płatności ER **Polecenie przelewu ISO20022**, który jest dostępny z biblioteki aktywów wspólnych w usługach Microsoft Dynamics Lifecycle Services (LCS) lub z repozytorium globalnego.

![Importowanie formatu płatności ER na stronie Repozytorium konfiguracji.](./media/er-data-debugger-import-from-repo.png)

Oprócz wybranego formatu ER następujące [konfiguracje](general-electronic-reporting.md#Configuration) muszą zostać automatycznie zaimportowane do wystąpienia usługi Microsoft Dynamics 365 Finance jako część rozwiązania ER **Polecenie przelewu ISO20022**:

- [Konfiguracja modelu danych ER](general-electronic-reporting.md#DataModelComponent) **Model płatności**
- [Konfiguracja formatu ER](general-electronic-reporting.md#FormatComponentOutbound) **Polecenie przelewu ISO20022**
- [Konfiguracja mapowania modelu ER](general-electronic-reporting.md#ModelMappingComponent) **Mapowanie 1611 modelu płatności**
- Konfiguracja mapowania modelu ER **Mapowanie modelu płatności do miejsca docelowego ISO20022**

Te konfiguracje można znaleźć na stronie **Konfiguracje** struktury ER (**Administracja organizacją** \> **Raportowanie elektroniczne** \> **Konfiguracje**).

![Zaimportowane konfiguracje na stronie Konfiguracje.](./media/er-data-debugger-configurations.png)

Jeśli w drzewie konfiguracji brakuje dowolnej z wymienionych wcześniej konfiguracji, należy pobrać ją ręcznie z biblioteki aktywów wspólnych usług LCS w taki sam sposób, w jaki pobrano format płatności ER **Polecenie przelewu ISO20022**.

### <a name="analyze-the-downloaded-er-solution"></a>Analizowanie pobranego rozwiązania ER

#### <a name="review-the-model-mapping"></a>Przeglądanie mapowania modelu

1. Otwórz **Administracja organizacji** \> **Elektroniczne raportowanie** \> **Konfiguracje**.
2. Wybierz pozycję **Model płatności** \> **Mapowanie 1611 modelu płatności**.
3. Wybierz opcję **Konstruktor**.
4. Wybierz rekord mapowania **Mapowanie modelu płatności ISO20022 CT**.
5. Wybierz pozycję **Projektant**, a następnie przejrzyj otwarte mapowanie modelu.

    Zauważ, że pole **Płatności** modelu danych jest powiązane ze źródłem danych **\$notSentTransactions**, które zwraca listę przetwarzanych wierszy płatności dostawcy.

    ![Pole Płatności na stronie projektanta mapowania modelu.](./media/er-data-debugger-model-mapping.png)

#### <a name="review-the-format-mapping"></a>Przeglądanie mapowania formatu

1. Otwórz **Administracja organizacji** \> **Elektroniczne raportowanie** \> **Konfiguracje**.
2. Wybierz pozycję **Model płatności** \> **Polecenie przelewu ISO20022**.
3. Wybierz opcję **Konstruktor**.
4. Na karcie **Mapowanie** przejrzyj otwarte mapowanie formatu.

    Zwróć uwagę, że element **Document** \> **CstmrCdtTrfInitn** \> **PmtInf** pliku **ISO20022CTReports** \> **XMLHeader** jest powiązany ze źródłem danych **\$PaymentByDebtor**, które skonfigurowano do grupowania rekordów pola **Płatności** modelu danych.

    ![Element PmtInf na stronie Projektant formatów.](./media/er-data-debugger-format-mapping.png)

#### <a name="review-the-format"></a>Przeglądanie formatu

1. Otwórz **Administracja organizacji** \> **Elektroniczne raportowanie** \> **Konfiguracje**.
2. Wybierz pozycję **Model płatności** \> **Polecenie przelewu ISO20022**.
3. Wybierz pozycję **Projektant**, a następnie przejrzyj otwarty format.

    Zauważ, że element formatu w obszarze **Document** \> **CstmrCdtTrfInitn** \> **PmtInf** \> **CdtTrfTxInf** \> **CdtrAcct** \> **Id** \> **IBAN** \> **BankIBAN** został skonfigurowany do wprowadzania kodu IBAN konta dostawcy w pliku płatności.

    ![Element formatu bankowego IBAN na stronie Projektanta formatów.](./media/er-data-debugger-format.png)

## <a name="appendix-2-configure-accounts-payable"></a><a name="appendix2"></a>Dodatek 2: konfigurowanie modułu Rozrachunki z dostawcami

### <a name="modify-a-vendor-property"></a>Modyfikowanie właściwości dostawcy

1. Przejdź do pozycji **Rozrachunki z dostawcami** \> **Dostawcy** \> **Wszyscy dostawcy**.
2. Wybierz dostawcę **DE-01002**, a następnie w okienku akcji na karcie **Dostawca** w grupie **Konfiguracja** wybierz pozycję **Konta bankowe**.
3. Na skróconej karcie **Identyfikacja** w polu **IBAN** <a name="enteredIBANcode"></a>wprowadź ciąg **GB33 BUKB 2020 1555 5555 55**.
4. Wybierz opcję **Zapisz**.

![Ustawione pole IBAN na stronie Konta bankowe dostawcy.](./media/er-data-debugger-iban.png)

### <a name="set-up-a-method-of-payment"></a>Konfigurowanie metody płatności

1. Przejdź do pozycji **Rozrachunki z dostawcami** \> **Ustawienia płatności** \> **Metody płatności**.
2. Wybierz metodę płatności **SEPA CT**.
3. Na skróconej karcie **Formaty plików** w sekcji **Formaty plików** ustaw opcję **Ogólny elektroniczny format eksportu** na **Tak**.
4. W polu **Konfiguracja formatu eksportu** wybierz format ER **Polecenie przelewu ISO20022**.
5. Wybierz opcję **Zapisz**.

![Ustawienia formatu pliku na stronie Metody płatności.](./media/er-data-debugger-payment-method.png)

### <a name="add-a-vendor-payment"></a>Dodawanie płatności dostawcy

1. Przejdź do pozycji **Rozrachunki z dostawcami** \> **Płatności** \> **Arkusz płatności dostawcy**.
2. Dodaj nowy arkusz płatności.
3. Wybierz pozycję **Wiersze** i dodaj nowy wiersz płatności.
4. W polu **Konto** wybierz dostawcę **DE-01002**.
5. W polu **Debet** wprowadź wartość.
6. W polu **Metoda płatności** wybierz pozycję **SEPA CT**.
7. Wybierz opcję **Zapisz**.

![Płatność dostawcy dodana na stronie Płatności dostawcy.](./media/er-data-debugger-payment-journal.png)

## <a name="appendix-3-process-a-vendor-payment"></a><a name="appendix3"></a>Dodatek 3: przetwarzanie płatności dostawcy

1. Przejdź do pozycji **Rozrachunki z dostawcami** \> **Płatności** \> **Arkusz płatności dostawcy**.
2. Na stronie **Arkusz płatności dostawców** wybierz utworzony wcześniej arkusz płatności, a następnie wybierz pozycję **Wiersze**.
3. Wybierz wiersz płatności, a następnie wybierz pozycję **Stan płatności** \> **Brak**.
4. Wybierz **Generuj płatności**.
5. W polu **Metoda płatności** wybierz pozycję **SEPA CT**.
6. W polu **Konto bankowe** wybierz pozycję **DEMF OPER**.
7. W oknie dialogowym **Generowanie płatności** wybierz przycisk **OK**.
8. W oknie dialogowym **Parametry raportu elektronicznego** wybierz przycisk **OK**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
