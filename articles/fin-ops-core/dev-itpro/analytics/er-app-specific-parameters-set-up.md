---
title: Konfiguracja parametrów formatu raportowania elektronicznego dla firmy
description: W tym artykule wyjaśniono, w jaki sposób można skonfigurować parametry formatu raportowania elektronicznego (ER) dla firmy.
author: kfend
ms.date: 03/25/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2019-01-01
ms.dyn365.ops.version: Release 8.1.3
ms.custom: ''
ms.assetid: ''
ms.search.form: ERSolutionTable, EROperationDesigner, ERLookupDesigner, ERComponentLookupStructureEditing
ms.openlocfilehash: 4b2e91e43938b71b78a4b7bc57b5b16ca174b1b7
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9291401"
---
# <a name="set-up-the-parameters-of-an-er-format-per-legal-entity"></a>Umożliwia konfigurowanie parametrów formatu ER dla firmy

[!include[banner](../includes/banner.md)]

## <a name="prerequisites"></a>Wymagania wstępne

Aby wykonać te kroki, należy najpierw wykonać kroki w temacie [Skonfiguruj ER, aby używać parametrów określonych dla danej firmy](er-app-specific-parameters-configure-format.md).

Aby wykonać przykłady opisane w tym artykule, trzeba mieć dostęp do rozwiązania Microsoft Dynamics 365 Finance dla jednej z następujących ról:

- Deweloper raportowania elektronicznego
- Konsultant funkcjonalny raportowania elektronicznego
- Administrator systemu

## <a name="import-er-configurations"></a>Importowanie konfiguracji ER
Aby zaimportować konfiguracje ER, wykonaj następujące kroki: 

1. Zaloguj się do swojego środowiska.
2. Na domyślnym pulpicie nawigacyjnym wybierz opcję **Raportowanie elektroniczne**.
3. Wybierz **Raportowanie konfiguracji**.
4. W bieżącej instancji aplikacji Finance zaimportuj konfiguracje, które zostały wyeksportowane z usług Regulatory Configuration Services (RCS) podczas wykonywania kroków w temacie [Skonfiguruj ER, aby używać parametrów określonych dla danej firmy](er-app-specific-parameters-configure-format.md). Należy wykonać następujące kroki dla każdej konfiguracji [raportowania elektronicznego (ER)](general-electronic-reporting.md) w następującej kolejności: model danych, mapowanie modelu i formaty.

    1. Wybierz **Import/eksport \> Załaduj z pliku XML**.
    2. Kliknij przycisk **Przeglądaj**, aby wybrać plik wymaganej konfiguracji ER w formacie XML.
    3. Kliknij przycisk **OK**.

    Na poniższej ilustracji przedstawiono konfiguracje, które muszą zostać wykonane po zakończeniu pracy.

    ![Strona konfiguracji raportowania elektronicznego.](./media/GER-AppSpecParms-ImportedConfigurations.PNG)

## <a name="set-up-parameters-for-the-demf-company"></a>Konfigurowanie parametrów dla firmy DEMF

Strukturę ER można stosować do konfigurowania parametrów specyficznych dla aplikacji dla formatu ER.

1. Wybierz firmę **DEMF**.
2. W drzewie konfiguracji wybierz **Format, aby uzyskać informacje o wyszukiwaniu danych LE**.
3. W okienku akcji na karcie **Konfiguracje** w grupie **Parametry specyficzne dla aplikacji** wybierz opcję **Konfiguracja**.

    ![Strona parametrów specyficznych dla aplikacji ER do konfigurowania parametrów.](./media/GER-AppSpecParms-LookupForm.PNG)

    Na stronie **parametry właściwe dla aplikacji** można skonfigurować **reguły** dotyczące źródła danych **formatu**, aby dowiedzieć się, jak wyszukać format danych LE.

    Jeśli podstawowy format ER będzie zawierał kilka źródeł danych typu **wyszukiwania**, przed rozpoczęciem konfigurowania reguły dla źródła danych należy wybrać żądane źródło danych na skróconej karcie **wyszukiwania**.

    Dla każdego źródła danych można skonfigurować oddzielne reguły dla każdej wersji wybranego formatu ER.

    Cały zbiór reguł dla wszystkich źródeł danych wyszukiwania, które są dostępne w wybranej wersji podstawowego formatu modelu ER, tworzy parametry specyficzne dla aplikacji dla formatu ER.

4. Wybierz wersję **1.1.1** formatu ER.
5. Na skróconej karcie **Warunki** wybierz pozycję **Dodaj**.
6. W polu **Kod** w nowym rekordzie i wybierz strzałkę rozwijaną, aby otworzyć wyszukiwanie.

    W wyszukiwaniu zostanie wystawiona lista kodów podatku do wybrania. Ta lista jest zwracana przez **Model.Data.Tax** źródło danych podatkowych skonfigurowane w podstawowym formacie ER. Ponieważ to źródło danych zawiera pole **nazwa**, nazwa każdego kodu podatku jest wyświetlana w wyszukiwaniu.

    ![Wyszukiwanie pola kodu na stronie parametrów specyficznych dla aplikacji raportowania elektronicznego.](./media/GER-AppSpecParms-LookupForm-CodeFldPicker.PNG)

7. Wybierz kod podatku **VAT19**.
8. W polu **Wynik wyszukiwania** w nowym rekordzie i wybierz strzałkę rozwijaną, aby otworzyć wyszukiwanie. W wyszukiwaniu zostanie wystawiona lista wartości dla wyliczenia formatu TaxationLevel do wybrania.

    Należy zauważyć, że jeśli jako preferowany język użytkownika, do którego użytkownik jest zalogowany, wybrano niemiecki, etykiety wartości w wyszukiwaniu będą w języku niemieckim, pod warunkiem, że zostały przetłumaczone w podstawowym formacie ER. Ponadto, jeśli etykieta źródła danych wyszukiwania została przetłumaczona, etykieta zostanie wyświetlona w preferowanym języku użytkownika na karcie **wyszukiwania**.

    ![Pole wyszukiwania przetłumaczone na język niemiecki na stronie parametrów specyficznych dla aplikacji ER.](./media/GER-AppSpecParms-LookupForm-LookupFldPicker.PNG)

9. Umożliwia wybór wartości **zwykłego opodatkowania**.

    Dodając ten rekord, należy zdefiniować następującą regułę: gdy jest wymagane źródło danych wyszukiwania **Selektor**, a kod podatku **VAT19** jest przekazywany jako argument, **zwykłe opodatkowanie** zostanie zwrócone jako żądany poziom opodatkowania.

10. Wybierz opcję **Dodaj**, a następnie wykonaj następujące kroki:

    1. W polu **Kod** wybierz kod **InVAT19**.
    2. W polu **wynik wyszukiwania** wybierz wartość **zwykłe opodatkowanie**.

11. Wybierz opcję **Dodaj**, a następnie wykonaj następujące kroki:

    1. W polu **Kod** wybierz kod **VAT7**.
    2. W polu **wynik wyszukiwania** wybierz wartość **obniżone opodatkowanie**.

12. Wybierz opcję **Dodaj**, a następnie wykonaj następujące kroki:

    1. W polu **Kod** wybierz kod **InVAT7**.
    2. W polu **wynik wyszukiwania** wybierz wartość **obniżone opodatkowanie**.

13. Wybierz opcję **Dodaj**, a następnie wykonaj następujące kroki:

    1. W polu **Kod** wybierz kod **THIRD**.
    2. W polu **wynik wyszukiwania** wybierz wartość **brak opodatkowania**.

14. Wybierz opcję **Dodaj**, a następnie wykonaj następujące kroki:

    1. W polu **Kod** wybierz kod **InVAT0**.
    2. W polu **wynik wyszukiwania** wybierz wartość **brak opodatkowania**.

15. Wybierz opcję **Dodaj**, a następnie wykonaj następujące kroki:

    1. W polu **kod** wybierz opcję **\*Nie pusty\***.
    2. W polu **wynik wyszukiwania** wybierz wartość **Inne opodatkowanie**.

    Dodając ostatni rekord, należy zdefiniować następującą regułę: gdy kod podatkowy przekazany jako argument nie spełnia żadnej z poprzednich reguł, źródło danych odnośnika zwróci **Inne** jako żądany poziom opodatkowania.

    ![Ostatni rekord dodany na stronie parametrów specyficznych dla aplikacji raportowania elektronicznego.](./media/GER-AppSpecParms-LookupForm-RulesSet.PNG)

16. W polu **Stan** wybierz opcję **ukończone**.

    Jeśli zostanie uruchomiona wersja formatu ER o stanie **ukończona** lub **udostępniona**, ten zbiór reguł musi być w stanie **ukończone**. W przeciwnym razie wykonanie podstawowego formatu ER zostanie przerwane, jeśli format będzie próbował załadować dane z tego zbioru reguł podczas uruchamiania źródła danych wyszukiwania **reguły**.

    Po uruchomieniu wersji formatu ER o stanie **wersja robocza**, podstawowy format ER może uzyskać dostęp do tego zbioru reguł niezależnie od jego stanu.

17. Wybierz opcję **Zapisz**.
18. Zamknij stronę **Parametry specyficzne dla aplikacji**.

## <a name="run-the-er-format-in-the-demf-company"></a>Uruchom format ER w firmie DEMF
Aby uruchomić format ER w firmie DEMF, wykonaj poniższe kroki: 

1. W drzewie konfiguracji wybierz **Format, aby uzyskać informacje o wyszukiwaniu danych LE**.
2. W okienku akcji wybierz opcję **Uruchom**.
3. W oknie dialogowym wybierz **Ok**.
4. Pobierz wygenerowane zestawienia i umieść je lokalnie.

    W wygenerowanym zestawieniu należy zauważyć, że podsumowanie kodu podatku **InVAT7** jest umieszczone na poziomie **Obniżony**, a podsumowania kodów podatków **VAT19** i **InVA19** są umieszczone na poziomie **Zwykłe**. Zachowanie to zależy od konfiguracji w zestawie reguł zależnych od firmy.

5. Wybierz kolejno opcje **Podatek \> Podatki pośrednie \> Podatek \> Kody podatków**.
6. Wybierz kod podatku **InVAT7**.
7. W okienku akcji, na karcie **kod podatku,** w grupie **informacje** wybierz opcję **zaksięgowany podatek**, aby wyświetlić informacje o wartościach podatku i zastosowaniu stawki podatkowej według kodu podatku.

    ![Strona zaksięgowany podatek.](./media/GER-AppSpecParms-Statement.PNG)

8. Zamknij stronę **Zaksięgowany podatek**.

## <a name="set-up-parameters-for-the-usmf-company"></a>Konfigurowanie parametrów dla firmy USMF
Aby skonfigurować parametry firmy USMF, wykonaj następujące kroki: 

1. Wybierz firmę **USMF**.
2. Przejdź do opcji **Administrowanie organizacją \> Raporty elektroniczne \> Konfiguracje**.
3. W drzewie konfiguracje rozwiń **Model do nauczenia sparametryzowanych wywoływań**, rozwiń **Format do nauczania sparametryzowanych wywołań**, a następnie wybierz **Format do nauczania wyszukiwania danych LE**.
4. W okienku akcji na karcie **Konfiguracje** w grupie **Parametry specyficzne dla aplikacji** wybierz opcję **Konfiguracja**.
5. Wybierz wersję **1.1.1** wybranego formatu ER.
6. Na skróconej karcie **Warunki** wybierz pozycję **Dodaj**.
7. W polu **Kod** w nowym rekordzie i wybierz strzałkę rozwijaną, aby otworzyć wyszukiwanie.

    W wyszukiwaniu zostanie wystawiona lista kodów podatków do wybrania dla podatku firmy **USMF**.

    ![Kody podatków dla podatku firmy USMF.](./media/GER-AppSpecParms-LookupForm-CodeFldPicker2.PNG)

8. Wybierz kod podatku **EXEMPT**.
9. W polu **wynik wyszukiwania w nowym rekordzie** wybierz wartość **Brak opodatkowania**.
10. Wybierz opcję **Dodaj**.
11. W polu **kod** nowego rekordu wybierz opcję **\*Nie pusty\***.
12. W polu **wynik wyszukiwania** w nowym rekordzie wybierz wartość **Zwykłe opodatkowanie**.
13. W polu **Stan** wybierz opcję **ukończone**.
14. Wybierz opcję **Zapisz**.

    ![Strona parametry specyficzne dla aplikacji ER.](./media/GER-AppSpecParms-LookupForm-RulesSet2.PNG)

15. Zamknij stronę **Parametry specyficzne dla aplikacji**.

## <a name="run-the-er-format-in-the-usmf-company"></a>Uruchom format ER w firmie USMF
Aby uruchomić format ER w firmie USMF, wykonaj poniższe kroki:

1. W drzewie konfiguracji wybierz **Format, aby uzyskać informacje o wyszukiwaniu danych LE**.
2. W okienku akcji wybierz opcję **Uruchom**.
3. W oknie dialogowym wybierz **Ok**.
4. Pobierz wygenerowane zestawienia i umieść je lokalnie.

    W wygenerowanym wyciągu należy zauważyć, że teraz ponownie użyto tego samego formatu ER dla innej firmy, ale bez wprowadzania jakichkolwiek zmian w formacie ER.

## <a name="reuse-legal-entitydependent-parameters"></a>Ponowne użycie podmiotu prawnego — parametry zależne

### <a name="duplicate-existing-parameters"></a>Duplikowanie istniejących parametrów

#### <a name="export-parameters"></a>Parametry eksportu
Aby wyeksportować parametry, wykonaj następujące kroki:

1. Wybierz kolejno opcje **Administrowanie organizacją \> Obszary robocze \> Raportowanie elektroniczne**.
2. Wybierz **Raportowanie konfiguracji**.
3. W drzewie konfiguracji wybierz **Format, aby uzyskać informacje o wyszukiwaniu danych LE**.
4. W okienku akcji na karcie **Konfiguracje** w grupie **Parametry specyficzne dla aplikacji** wybierz opcję **Konfiguracja**.
5. Wybierz wersję **1.1.1** formatu ER.
6. W okienku akcji wybierz pozycję **Eksportuj**.
7. Pobierz wygenerowane pliku i umieść je lokalnie.

    Skonfigurowany zbiór parametrów specyficznych dla aplikacji został teraz wyeksportowany jako plik XML.

#### <a name="import-parameters"></a>Parametry importu
Aby zaimportować parametry, wykonaj następujące kroki:

1. Wybierz wersję **1.1.2** formatu ER.
2. W okienku akcji wybierz pozycję **Importuj**.
3. Wybierz **Tak**, aby potwierdzić zamiar zastąpienia istniejących parametrów specyficznych dla aplikacji dla tej wersji formatu.
4. Wybierz przycisk **Przeglądaj**, aby znaleźć plik zawierający wyeksportowane parametry właściwe dla aplikacji dla wersji **1.1.1**.
5. Kliknij przycisk **OK**.

    Wersja **1.1.2** formatu ER zawiera teraz te same parametry właściwe dla aplikacji, które zostały pierwotnie skonfigurowane dla wersji **1.1.1**.

##### <a name="applicability-considerations"></a>Zagadnienia związane z możliwością zastosowania

Parametry właściwe dla aplikacji w formacie ER są zależne od firmy. Aby ponownie użyć parametrów specyficznych dla aplikacji, które zostały skonfigurowane dla jednego podmiotu prawnego w innej firmie, należy je wyeksportować w pierwszej firmie. Następnie zaimportuj je po zalogowaniu się do innej firmy.

Można również skorzystać z metody „eksport-import” w celu przetransferowania parametrów formatu ER specyficznych dla aplikacji, które zostały pierwotnie skonfigurowane w jednym wystąpieniu Finance, do innego wystąpienia Finance.

Jeśli skonfigurujesz parametry specyficzne dla aplikacji dla jednej wersji formatu ER, a następnie zaimportujesz późniejszą wersję tego samego formatu do bieżącego wystąpienia aplikacji Finance, istniejące parametry specyficzne dla aplikacji nie będą stosowane do zaimportowanej wersji, chyba że użyjesz funkcji **Użyj parametrów specyficznych dla aplikacji z poprzednich wersji formatów raportowania elektronicznego**. Więcej informacji znajduje się w dalszej sekcji [Ponowne używanie istniejących parametrów](#reuse-existing-parameters) w tym artykule.

Po wybraniu pliku do zaimportowania struktura parametrów specyficznych dla aplikacji w tym pliku jest porównywana ze strukturą odpowiednich źródeł danych typu **Wyszukiwanie** w formacie ER, który został wybrany do importu. Domyślnie jest wykonywany tylko wtedy, gdy struktura każdego parametru specyficznego dla aplikacji odpowiada strukturze odpowiedniego źródła danych w formacie ER wybranym do importu. Jeśli struktury nie są zgodne, komunikat ostrzegawczy poinformuje Cię o tym, że nie można wykonać importu. W przypadku wymuszenia importu istniejące parametry specyficzne dla aplikacji dla wybranego formatu ER zostaną oczyszczone i należy je skonfigurować od początku.


Od aplikacji Finance w wersji 10.0.24 można zmienić domyślne zachowanie i uniknąć pojawiania się komunikatów ostrzegawczych, włączając funkcję **Podczas importowania wyrównaj parametry specyficzne dla aplikacji raportowania elektronicznego** w obszarze roboczym **Zarządzanie funkcjami**. Po włączeniu tej funkcji, jeśli struktura importowanych parametrów specyficznych różni się od struktury odpowiedniego źródła danych typu wyszukiwania w docelowym formacie ER, który został wybrany do importu, w następujących przypadkach importowanie zakończy się powodzeniem:

- Struktura docelowego formatu ER została zmieniona przez dodanie nowych kolumn warunku do istniejących źródeł danych typu **Wyszukiwanie**. Po zakończeniu importowania parametry specyficzne dla aplikacji są aktualizowane. We wszystkich importowanych rekordach parametrów specyficznych dla aplikacji wartości w każdej kolumnie dodawanego warunku są inicjowane z wartością domyślną dla [typu danych](er-formula-supported-data-types-primitive.md) danej kolumny.
- Struktura docelowego formatu ER została zmieniona przez usunięcie niektórych kolumn warunku z istniejących źródeł danych typu **Wyszukiwanie**. Po zakończeniu importowania parametry specyficzne dla aplikacji są aktualizowane. Ze wszystkich importowanych rekordów parametrów specyficznych dla aplikacji usuwane są wartości z każdej usuniętej kolumny warunku.
- Struktura docelowego formatu ER została zmieniona przez dodanie nowych źródeł danych typu **Wyszukiwanie**. Po zakończeniu importowania dodane wyszukiwania są dołączane do parametrów specyficznych dla aplikacji.
- Struktura docelowego formatu ER została zmieniona przez usunięcie niektórych istniejących źródeł danych typu **Wyszukiwanie**. Po zakończeniu importowania wszystkie artefakty powiązane ze źródłami danych typu **Wyszukiwanie**, które zostały usunięte z docelowego formatu ER, są usuwane z importowanych parametrów specyficznych dla aplikacji.

Po zakończeniu importowania, oprócz opisanych zmian, stan zaimportowanych parametrów specyficznych dla aplikacji zmienia się na **W toku**. Komunikat ostrzegawczy informuje, że automatycznie skorygowane parametry aplikacji należy edytować ręcznie.

#### <a name="replicate-parameters"></a>Parametry replikacji

Od wersji Finance 10.0.27 możesz kopiować parametry, które skonfigurowałeś w jednej firmie, do innych firm w tym samym czasie.

Aby skopiować parametry, wykonaj następujące czynności.

1. Wybierz kolejno opcje **Administrowanie organizacją** \> **Obszary robocze** \> **Raportowanie elektroniczne**.
2. Wybierz **Raportowanie konfiguracji**.
3. W drzewie konfiguracji wybierz **Format, aby uzyskać informacje o wyszukiwaniu danych LE**.
4. W okienku akcji na karcie **Konfiguracje** w grupie **Parametry specyficzne dla aplikacji** wybierz opcję **Konfiguracja**.
5. Wybierz wersję **1.1.1** formatu ER.
6. W okienku akcji wybierz opcję **Replikuj**.
7. W oknie dialogowym **Replikuj**, w zakładce **Firmy** wybierz firmy, do których chcesz skopiować parametry.

    > [!NOTE]
    > Lista firm docelowych jest dostępna tylko dla użytkowników, którzy mają przypisaną [rolę](../sysadmin/role-based-security.md#security-roles) bezpieczeństwa skonfigurowaną tak, aby dawała dostęp do wszystkich organizacji.

8. Kliknij przycisk **OK**.

    > [!NOTE]
    > Okno dialogowe potwierdzenia informuje cię, czy niektóre firmy docelowe zawierają wcześniej skonfigurowane parametry dla wybranej wersji formatu ER. Wybierz przycisk **Tak**, aby zastąpić parametry, kopiując je z bieżącej firmy.

    Skonfigurowany zestaw parametrów specyficznych dla aplikacji jest teraz kopiowany do wybranych firm.

### <a name="reuse-existing-parameters"></a>Ponowne używanie istniejących parametrów

Od aplikacji Finance w wersji 10.0.23 można używać parametrów specyficznych dla aplikacji skonfigurowanych dla jednej wersji formatu ER, gdy jest uruchamiana wyższa wersja tego samego formatu. Aby ponownie wykorzystać istniejące parametry, **Użyj parametrów specyficznych dla aplikacji z poprzednich wersji formatów raportowania elektronicznego** w obszarze roboczym **Zarządzanie funkcjami**. Gdy ta funkcja jest włączona i uruchamiana jest jedna wersja formatu raportu ER, który próbuje odczytać parametry specyficzne dla aplikacji, funkcja ER spróbuje znaleźć parametry specyficzne dla aplikacji, które zostały skonfigurowane dla uruchomionej wersji tego formatu. Jeśli nie są one dostępne, ER postara się je znaleźć dla najbliższej niższej wersji formatu.

> [!NOTE]
> Parametrów specyficznych dla aplikacji można używać ponownie tylko w zakresie bieżącej firmy.
>
> Błąd jest wyświetlany w czasie wykonywania, gdy jest uruchamiana wyższa wersja formatu ER, która próbuje ponownie użyć parametrów specyficznych dla aplikacji, skonfigurowanych dla niższej wersji tego samego formatu, a struktura co najmniej jednego źródła danych typu **Wyszukiwanie** w nowszej wersji formatu uległa zmianie.

## <a name="relationship-between-application-specific-parameters-and-an-er-format"></a>Relacja między parametrami specyficznymi dla aplikacji a formatem ER

Relacja między formatem ER a jego parametrami specyficznymi dla aplikacji jest ustalana na podstawie unikatowego kodu identyfikacyjnego w formacie obiektu ER. Dlatego po usunięciu formatu ER z Finance, parametry właściwe dla aplikacji skonfigurowane dla formatu ER są przechowywane w bieżącym wystąpieniu Finance. Dostęp do nich jest możliwy po powrotnym zaimportowaniu podstawowego formatu ER do tego wystąpienia aplikacji Finance.

## <a name="access-application-specific-parameters-by-using-the-er-framework"></a>Uzyskiwanie dostępu do parametrów specyficznych dla aplikacji przy użyciu struktury ER

W powyższym przykładzie uzyskano dostęp do parametrów specyficznych dla aplikacji w formacie ER przy użyciu struktury ER. Takie rozwiązanie nie pozwala na ograniczenie dostępu do parametrów specyficznych dla aplikacji w określonym formacie ER. Jeśli konieczne jest zastosowanie takich ograniczeń, należy wykonać następujące kroki. 

1. Należy ponownie użyć istniejącego elementu menu **ERSolutionAppSpecificParametersDesigner** lub zaimplementować własny element menu **ERSolutionAppSpecificParametersDesigner**.

    ![Element menu wyświetlający obiekt ERSolutionAppSpecificParametersDesigner.](./media/GER-AppSpecParms-LookupForm-Access1.PNG)

2. Wykonaj jeden z następujących kroków:

    1. Utwórz nowy przycisk elementu menu i połącz go z odpowiednim rekordem z tabeli **ERSolutionTable**, ustawiając właściwość **źródła danych** na **ERSolutionTable.**

        ![Wyświetlanie nowych ustawień elementu menu.](./media/GER-AppSpecParms-LookupForm-Access2.PNG)

    2. Utwórz prosty przycisk i Zastąp **klikniętą** metodę, tak jak to pokazano w poniższym przykładzie.

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
