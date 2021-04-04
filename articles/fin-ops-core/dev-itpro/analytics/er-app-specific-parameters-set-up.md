---
title: Umożliwia konfigurowanie parametrów formatu ER dla firmy
description: W tym temacie wyjaśniono, w jaki sposób można skonfigurować parametry formatu raportowania elektronicznego (ER) dla firmy.
author: NickSelin
manager: AnnBe
ms.date: 10/29/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, EROperationDesigner, ERLookupDesigner, ERComponentLookupStructureEditing
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-01-01
ms.dyn365.ops.version: Release 8.1.3
ms.openlocfilehash: eebca6575a0b23f75baabbb91727f498de44d9cb
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2021
ms.locfileid: "5570717"
---
# <a name="set-up-the-parameters-of-an-er-format-per-legal-entity"></a>Umożliwia konfigurowanie parametrów formatu ER dla firmy

[!include[banner](../includes/banner.md)]

## <a name="prerequisites"></a>Wymagania wstępne

Aby wykonać te kroki, należy najpierw wykonać kroki w temacie [Skonfiguruj ER, aby używać parametrów określonych dla danej firmy](er-app-specific-parameters-configure-format.md).

Aby wykonać przykłady opisane w tym temacie, trzeba mieć dostęp do rozwiązania Microsoft Dynamics 365 Finance (Finance) dla jednej z następujących ról:

- Deweloper raportowania elektronicznego
- Konsultant funkcjonalny raportowania elektronicznego
- Administrator systemu

## <a name="import-er-configurations"></a>Importowanie konfiguracji ER

1.  Zaloguj się do swojego środowiska.
2.  Na domyślnym pulpicie nawigacyjnym wybierz opcję **Raportowanie elektroniczne**.
3.  Wybierz **Raportowanie konfiguracji**.
4.  Do bieżącej instancji modułu finanse są importowane konfiguracje, które zostały wyeksportowane z Regulatory Configuration Services (RCS) podczas wykonywania kroków w temacie [Skonfiguruj ER, aby używać parametrów określonych dla danej firmy](er-app-specific-parameters-configure-format.md). Należy wykonać następujące kroki dla każdej konfiguracji elektronicznego raportowania (ER) w następującej kolejności: model danych, mapowanie modelu i formaty.

    1. Wybierz **Import/eksport \> Załaduj z pliku XML**.
    2. Kliknij przycisk **Przeglądaj**, aby wybrać plik wymaganej konfiguracji ER w formacie XML.
    3. Kliknij przycisk **OK**.
    
    Na poniższej ilustracji przedstawiono konfiguracje, które muszą zostać wykonane po zakończeniu pracy.

    ![Strona konfiguracji raportowania elektronicznego](./media/GER-AppSpecParms-ImportedConfigurations.PNG)

## <a name="set-up-parameters-for-the-demf-company"></a>Konfigurowanie parametrów dla firmy DEMF

Strukturę ER można stosować do konfigurowania parametrów specyficznych dla aplikacji dla formatu ER.

1.  Wybierz firmę **DEMF**.
2.  W drzewie konfiguracji wybierz **Format, aby uzyskać informacje o wyszukiwaniu danych LE**.
3.  W okienku akcji na karcie **Konfiguracje** w grupie **Parametry specyficzne dla aplikacji** wybierz opcję **Konfiguracja**.

    ![Strona parametry specyficzne dla aplikacji ER](./media/GER-AppSpecParms-LookupForm.PNG)
    
    Na stronie **parametry właściwe dla aplikacji** można skonfigurować **reguły** dotyczące źródła danych **formatu**, aby dowiedzieć się, jak wyszukać format danych LE.
    
    Jeśli podstawowy format ER będzie zawierał kilka źródeł danych typu **wyszukiwania**, przed rozpoczęciem konfigurowania reguły dla źródła danych należy wybrać żądane źródło danych na skróconej karcie **wyszukiwania**.
    
    Dla każdego źródła danych można skonfigurować oddzielne reguły dla każdej wersji wybranego formatu ER.
    
    Cały zbiór reguł dla wszystkich źródeł danych wyszukiwania, które są dostępne w wybranej wersji podstawowego formatu modelu ER, tworzy parametry specyficzne dla aplikacji dla formatu ER.

4.  Wybierz wersję **1.1.1** formatu ER.
5.  Na skróconej karcie **Warunki** wybierz pozycję **Dodaj**.
6.  W polu **Kod** w nowym rekordzie i wybierz strzałkę rozwijaną, aby otworzyć wyszukiwanie.

    W wyszukiwaniu zostanie wystawiona lista kodów podatku do wybrania. Ta lista jest zwracana przez **Model.Data.Tax** źródło danych podatkowych skonfigurowane w podstawowym formacie ER. Ponieważ to źródło danych zawiera pole **nazwa**, nazwa każdego kodu podatku jest wyświetlana w wyszukiwaniu.

    ![Strona parametry specyficzne dla aplikacji ER](./media/GER-AppSpecParms-LookupForm-CodeFldPicker.PNG)
    
7.  Wybierz kod podatku **VAT19**.
8.  W polu **Wynik wyszukiwania** w nowym rekordzie i wybierz strzałkę rozwijaną, aby otworzyć wyszukiwanie. W wyszukiwaniu zostanie wystawiona lista wartości dla wyliczenia formatu TaxationLevel do wybrania.

    Należy zauważyć, że jeśli jako preferowany język użytkownika, do którego użytkownik jest zalogowany, jest wybrana jako niemiecki, etykiety wartości w wyszukiwaniu będą w języku niemieckim, pod warunkiem, że zostały przetłumaczone w podstawowym formacie ER. Ponadto, jeśli etykieta źródła danych wyszukiwania została przetłumaczona, etykieta zostanie wyświetlona w preferowanym języku użytkownika na karcie **wyszukiwania**.

    ![Strona parametry specyficzne dla aplikacji ER](./media/GER-AppSpecParms-LookupForm-LookupFldPicker.PNG)

9.  Umożliwia wybór wartości **zwykłego opodatkowania**.

    Dodając ten rekord, należy zdefiniować następującą regułę: ilekroć jest wymagane źródło danych wyszukiwania **reguły**, a kod podatku **VAT19** jest przekazywany jako argument, **zwykłe opodatkowanie** zostanie zwrócony jako żądany poziom opodatkowania.

10. Wybierz opcję **Dodaj**, a następnie wykonaj następujące kroki:

    1. W polu **Kod** wybierz kod **InVAT19**.
    2. W polu **wynik wyszukiwania** wybierz wartość **zwykłe opodatkowanie**.
    
11. Wybierz znowu opcję **Dodaj**, a następnie wykonaj następujące kroki:

    1. W polu **Kod** wybierz kod **VAT7**.
    2. W polu **wynik wyszukiwania** wybierz wartość **obniżone opodatkowanie**.
    
12. Wybierz znowu opcję **Dodaj**, a następnie wykonaj następujące kroki:

    1. W polu **Kod** wybierz kod **InVAT7**.
    2. W polu **wynik wyszukiwania** wybierz wartość **obniżone opodatkowanie**.
    
13. Wybierz znowu opcję **Dodaj**, a następnie wykonaj następujące kroki:

    1. W polu **Kod** wybierz kod **THIRD**.
    2. W polu **wynik wyszukiwania** wybierz wartość **brak opodatkowania**.
    
14. Wybierz znowu opcję **Dodaj**, a następnie wykonaj następujące kroki:

    1. W polu **Kod** wybierz kod **InVAT0**.
    2. W polu **wynik wyszukiwania** wybierz wartość **brak opodatkowania**.
    
15. Wybierz znowu opcję **Dodaj**, a następnie wykonaj następujące kroki:

    1. W polu **kod** wybierz opcję **\*Nie pusty\***.
    2. W polu **wynik wyszukiwania** wybierz wartość **Inne opodatkowanie**.
    
    Dodając ostatni rekord, należy zdefiniować następującą regułę: Ilekroć kod podatkowy przekazany jako argument nie spełnia żadnej z poprzednich reguł, źródło danych odnośnika zwróci **Inne** jako żądany poziom opodatkowania.

    ![Strona parametry specyficzne dla aplikacji ER](./media/GER-AppSpecParms-LookupForm-RulesSet.PNG)
    
16. W polu **Stan** wybierz opcję **ukończone**.

    Jeśli zostanie uruchomiona wersja formatu ER o stanie **ukończona** lub **udostępniona**, ten zbiór reguł musi być w stanie **ukończone**. W przeciwnym razie wykonanie podstawowego formatu ER zostanie przerwane, jeśli format będzie próbował załadować dane z tego zbioru reguł podczas uruchamiania źródła danych wyszukiwania **reguły**.
    
    Po uruchomieniu wersji formatu ER o stanie **wersja robocza**, podstawowy format ER może uzyskać dostęp do tego zbioru reguł niezależnie od jego stanu.
    
17. Wybierz opcję **Zapisz**.
18. Zamknij stronę **Parametry specyficzne dla aplikacji**.

## <a name="run-the-er-format-in-the-demf-company"></a>Uruchom format ER w firmie DEMF

1.  W drzewie konfiguracji wybierz **Format, aby uzyskać informacje o wyszukiwaniu danych LE**.
2.  W okienku akcji wybierz opcję **Uruchom**.
3.  W oknie dialogowym wybierz **Ok**.
4.  Pobierz wygenerowane zestawienia i umieść je lokalnie.

    W wygenerowanym zestawieniu należy zauważyć, że podsumowanie kodu podatku **InVAT7** zostało umieszczone na poziomie **Obniżony**, a podsumowania kodów podatków **VAT19** i **InVA19** zostały umieszczone na poziomie **zwykłe**. Zachowanie to zależy od konfiguracji w zestawie reguł zależnych od firmy.
    
5.  Wybierz kolejno opcje **Podatek \> Podatki pośrednie \> Podatek \> Kody podatków**.
6.  Wybierz kod podatku **InVAT7**.
7.  W okienku akcji, na karcie **kod podatku,** w grupie **informacje** wybierz opcję **zaksięgowany podatek**, aby wyświetlić informacje o wartościach podatku i zastosowaniu stawki podatkowej według kodu podatku.

    ![Strona zaksięgowany podatek](./media/GER-AppSpecParms-Statement.PNG)

8.  Zamknij strony Zaksięgowany podatek.

## <a name="set-up-parameters-for-the-usmf-company"></a>Konfigurowanie parametrów dla firmy USMF

1.  Wybierz firmę **USMF**.
2.  Przejdź do opcji **Administrowanie organizacją \> Raporty elektroniczne \> Konfiguracje**.
3.  W drzewie konfiguracje rozwiń **Model do nauczenia sparametryzowanych wywoływań**, rozwiń **Format do nauczania sparametryzowanych wywołań**, a następnie wybierz **Format do nauczania wyszukiwania danych LE**.
4.  W okienku akcji na karcie **Konfiguracje** w grupie **Parametry specyficzne dla aplikacji** wybierz opcję **Konfiguracja**.
5.  Wybierz wersję **1.1.1** wybranego formatu ER.
6.  Na skróconej karcie **Warunki** wybierz pozycję **Dodaj**.
7.  W polu **Kod** w nowym rekordzie i wybierz strzałkę rozwijaną, aby otworzyć wyszukiwanie.

    W wyszukiwaniu zostanie wystawiona lista kodów podatków do wybrania dla podatku firmy **USMF**.

    ![Strona parametry specyficzne dla aplikacji ER](./media/GER-AppSpecParms-LookupForm-CodeFldPicker2.PNG)
    
8.  Wybierz kod podatku **EXEMPT**.
9.  W polu **wynik wyszukiwania w nowym rekordzie** wybierz wartość **Brak opodatkowania**.
10. Wybierz ponownie przycisk **Dodaj**.
11. W polu **kod** nowego rekordu wybierz opcję **\*Nie pusty\***.
12. W polu **wynik wyszukiwania** w nowym rekordzie wybierz wartość **Zwykłe opodatkowanie**.
13. W polu **Stan** wybierz opcję **ukończone**.
14. Wybierz opcję **Zapisz**.

    ![Strona parametry specyficzne dla aplikacji ER](./media/GER-AppSpecParms-LookupForm-RulesSet2.PNG)
    
15. Zamknij stronę **Parametry specyficzne dla aplikacji**.

## <a name="run-the-er-format-in-the-usmf-company"></a>Uruchom format ER w firmie USMF

1.  W drzewie konfiguracji wybierz **Format, aby uzyskać informacje o wyszukiwaniu danych LE**.
2.  W okienku akcji wybierz opcję **Uruchom**.
3.  W oknie dialogowym wybierz **Ok**.
4.  Pobierz wygenerowane zestawienia i umieść je lokalnie.

    W wygenerowanym wyciągu należy zauważyć, że teraz ponownie użyto tego samego formatu ER dla innej firmy, ale bez wprowadzania jakichkolwiek zmian w formacie ER.

## <a name="reuse-legal-entitydependent-parameters"></a>Ponowne użycie podmiotu prawnego — parametry zależne

### <a name="export-parameters"></a>Parametry eksportu

1.  Wybierz kolejno opcje **Administrowanie organizacją \> Obszary robocze \> Raportowanie elektroniczne**.
2.  Wybierz **Raportowanie konfiguracji**.
3.  W drzewie konfiguracji wybierz **Format, aby uzyskać informacje o wyszukiwaniu danych LE**.
4.  W okienku akcji na karcie **Konfiguracje** w grupie **Parametry specyficzne dla aplikacji** wybierz opcję **Konfiguracja**.
5.  Wybierz wersję **1.1.1** formatu ER.
6.  W okienku akcji wybierz pozycję **Eksportuj**.
7.  Pobierz wygenerowane pliku i umieść je lokalnie.

    Skonfigurowany zbiór parametrów specyficznych dla aplikacji został teraz wyeksportowany jako plik XML.

### <a name="import-parameters"></a>Parametry importu

1.  Wybierz wersję **1.1.2** formatu ER.
2.  W okienku akcji wybierz pozycję **Importuj**.
3.  Wybierz **Tak**, aby potwierdzić zamiar zastąpienia istniejących parametrów specyficznych dla aplikacji dla tej wersji formatu.
4.  Wybierz przycisk **Przeglądaj**, aby znaleźć plik zawierający wyeksportowane parametry właściwe dla aplikacji dla wersji **1.1.1**.
5.  Kliknij przycisk **OK**.

    Wersja **1.1.2** formatu ER zawiera teraz te same parametry właściwe dla aplikacji, które zostały pierwotnie skonfigurowane dla wersji **1.1.1**.
    
    Należy zauważyć, że parametry właściwe dla aplikacji w formacie ER są zależne od firmy. Aby ponownie użyć parametrów specyficznych dla aplikacji, które zostały skonfigurowane dla jednego podmiotu prawnego w innej firmie, należy je wyeksportować w pierwszej firmie, a następnie zaimportować po zalogowaniu się do innej firmy.

    Można również skorzystać z tej metody w celu przetransferowania parametrów formatu ER specyficznych dla aplikacji, które zostały pierwotnie skonfigurowane w jednym wystąpieniu Finance, do innego wystąpienia Finance.

    Należy pamiętać, że w przypadku konfigurowania parametrów specyficznych dla aplikacji dla jednej wersji formatu ER i importowania wyższej wersji tego samego formatu do bieżącego wystąpienia finansów, istniejące parametry specyficzne dla danej aplikacji nie będą stosowane dla wersji zaimportowanej.
    
    Należy również pamiętać, że po wybraniu pliku do zaimportowania struktura parametrów specyficznych dla aplikacji w tym pliku jest porównywana ze strukturą odpowiedniego źródła danych typu **wyszukiwania** w formacie ER, który został wybrany do importu. Import jest wykonywany, gdy struktura każdego parametru specyficznego dla aplikacji odpowiada strukturze odpowiedniego źródła danych w formacie ER wybranym do importu. Jeśli struktury nie są zgodne, zostanie wyświetlony komunikat ostrzegawczy informujący o tym, że nie można wykonać importu. W przypadku wymuszenia importu, istniejące parametry specyficzne dla aplikacji dla wybranego formatu ER zostaną oczyszczone i należy je skonfigurować od początku.

## <a name="relationship-between-application-specific-parameters-and-an-er-format"></a>Relacja między parametrami specyficznymi dla aplikacji a formatem ER

Relacja między formatem ER a jego parametrami specyficznymi dla aplikacji jest ustalana na podstawie unikatowego kodu identyfikacyjnego w formacie obiektu ER. Dlatego po usunięciu formatu ER z Finance, parametry właściwe dla aplikacji skonfigurowane dla formatu ER są przechowywane w bieżącym wystąpieniu Finance. Dostęp do nich jest możliwy po powrotnym zaimportowaniu podstawowego formatu ER do tego wystąpienia Finance.

## <a name="access-application-specific-parameters-by-using-the-er-framework"></a>Uzyskiwanie dostępu do parametrów specyficznych dla aplikacji przy użyciu struktury ER

W powyższym przykładzie uzyskano dostęp do parametrów specyficznych dla aplikacji w formacie ER przy użyciu struktury ER. Takie rozwiązanie nie pozwala na ograniczenie dostępu do parametrów specyficznych dla aplikacji w określonym formacie ER. Jeśli konieczne jest zastosowanie takich ograniczeń, należy wykonać następujące kroki. 

1.  Należy ponownie użyć istniejącego elementu menu **ERSolutionAppSpecificParametersDesigner** lub zaimplementować własny element menu **ERSolutionAppSpecificParametersDesigner**.

    ![Strona Visual Studio](./media/GER-AppSpecParms-LookupForm-Access1.PNG)
    
2.  Wykonaj jeden z następujących kroków:

    1.  Utwórz nowy przycisk elementu menu i połącz go z odpowiednim rekordem z tabeli **ERSolutionTable**, ustawiając właściwość **źródła danych** na **ERSolutionTable.**
    
        ![Strona Visual Studio](./media/GER-AppSpecParms-LookupForm-Access2.PNG)
        
    2.  Utwórz prosty przycisk i Zastąp **klikniętą** metodę, tak jak to pokazano w poniższym przykładzie.
    
        Korzystając z tego podejścia, można określić unikatowy identyfikator rozwiązania (zdefiniowany za pomocą wartości **GUID**), aby umożliwić dostęp do parametrów specyficznych dla aplikacji w oddzielnym formacie ER i kopiach podrzędnych, które zostały z niego utworzone.
        
        ```xpp
        public void clicked()
            {
                super();

                ERSolutionTable solutionTableRecord = ERSolutionTable::findByGUID(str2Guid('ADACCB2F-EFD1-4C90-877D-7E1E5D1AEE92'));

                Args args = new Args();
                args.record(solutionTableRecord);
                args.caller(this);

                new MenuFunction(menuItemDisplayStr(ERSolutionAppSpecificParametersDesigner), MenuItemType::Display)
                    .run(args);
            }
        ```

## <a name="additional-resources"></a>Dodatkowe zasoby

[Projektant formuł w module Raportowanie elektroniczne](general-electronic-reporting-formula-designer.md)

[Skonfiguruj formaty ER do używania parametrów określonych dla firmy](er-app-specific-parameters-configure-format.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]