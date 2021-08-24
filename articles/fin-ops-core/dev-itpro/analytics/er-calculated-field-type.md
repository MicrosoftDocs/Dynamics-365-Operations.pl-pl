---
title: Obsługuj sparametryzowane wywołania źródeł danych ER typu pola obliczeniowego
description: Ten temat zawiera informacje dotyczące używania typu pola obliczeniowego dla źródeł danych ER.
author: NickSelin
ms.date: 08/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: fbe06f2f4f0b9e738f27e87ae3ed5d10998ce949b854d088520837cef3ed9a9d
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6740366"
---
# <a name="support-parameterized-calls-of-er-data-sources-of-the-calculated-field-type"></a>Obsługuj sparametryzowane wywołania źródeł danych ER typu pola obliczeniowego

[!include [banner](../includes/banner.md)]

W tym temacie wyjaśniono, jak można zaprojektować źródło danych elektronicznego raportowania (ER) przy użyciu typu **pola obliczeniowego**. To źródło danych może zawierać wyrażenie właściciela, które po wykonaniu można kontrolować za pomocą wartości argumentów parametrów skonfigurowanych w powiązaniu, które wywołuje to źródło danych. Dzięki skonfigurowaniu sparametryzowanych wywołań takiego źródła danych można ponownie użyć jednego źródła danych w wielu powiązaniach, zmniejszając jednocześnie liczbę źródeł danych, które muszą być skonfigurowane w mapowaniach modelu ER lub w formatach ER. Upraszcza także skonfigurowany składnik ER, który zmniejsza koszty obsługi i koszty użytkowania innych odbiorców.

## <a name="prerequisites"></a>Wymagania wstępne
Aby wykonać przykłady opisane w tym temacie, musisz mieć następujące uprawnienia dostępu:

- Dostęp do jednej z następujących ról:

    - Deweloper raportowania elektronicznego
    - Konsultant funkcjonalny raportowania elektronicznego
    - Administrator systemu

- Dostęp do wystąpienia Regulatory Configuration Services (RCS), które zostało zainicjowane dla tej samej dzierżawy co Finance and Operations dla jednej z następujących ról:

    - Deweloper raportowania elektronicznego
    - Konsultant funkcjonalny raportowania elektronicznego
    - Administrator systemu

Musisz również pobrać i lokalnie zapisać następujące pliki.

| **Zawartość**                           | **Nazwa pliku**                                        |
|---------------------------------------|------------------------------------------------------|
| Przykładowa konfiguracja modelu danych ER    | [Model do nauczenia sparametryzowanych calls.version.1.xml.](https://mbs.microsoft.com/customersource/global/AX/downloads/hot-fixes/365optelecrepeg)     |
| Przykładowa konfiguracja metadanych ER      | [Dane do nauczenia sparametryzowanych calls.version.1.xml.](https://mbs.microsoft.com/customersource/global/AX/downloads/hot-fixes/365optelecrepeg)  |
| Przykładowa konfiguracja mapowania modelu ER | [Mapowanie do nauczenia sparametryzowanych calls.version.1.xml.](https://mbs.microsoft.com/customersource/global/AX/downloads/hot-fixes/365optelecrepeg) |
| Przykładowa konfiguracja formatu ER        | [Format do nauczenia sparametryzowanych calls.version.1.xml.](https://mbs.microsoft.com/customersource/global/AX/downloads/hot-fixes/365optelecrepeg)  |

## <a name="sign-in-to-your-rcs-instance"></a>Zaloguj się do swojego wystąpienia RCS.
W tej procedurze utworzysz wymagane konfiguracje ER dla przykładowej firmy Litware, Inc. Aby wykonać te kroki, najpierw trzeba wykonać kroki wymienione w procedurze [ER Tworzenie dostawców konfiguracji i oznaczanie ich jako aktywnych](tasks/er-configuration-provider-mark-it-active-2016-11.md).

1. Na domyślnym pulpicie nawigacyjnym wybierz opcję **Raportowanie elektroniczne**.
2. Wybierz **Raportowanie konfiguracji**.
3. Zaimportuj pobrane konfiguracje do RCS w następującej kolejności: model danych, metadane, mapowanie modelu, format. W każdej konfiguracji modułu ER należy wykonać następujące kroki:

    1. Wybierz **Zamień**.
    2. Wybierz **Załaduj z pliku XML**.
    3. Kliknij przycisk **Przeglądaj**, nastepnie wybierz odpowiedni plik wymaganej konfiguracji ER w formacie XML.
    4. Kliknij przycisk **OK**.

## <a name="review-the-provided-er-solution"></a>Przejrzyj dostarczone rozwiązanie ER

### <a name="review-model-mapping"></a>Przejrzyj mapowanie modelu

1. W drzewie konfiguracji rozwiń zawartość **Model, aby uzyskać informacje o elementach sparametryzowanych wywołań**.
2. Wybierz opcję **mapowanie, aby poznać wywołania sparametryzowane**.
3. Wybierz opcję **Konstruktor**.
4. Wybierz opcję **Konstruktor**.  
   
    W tym mapowaniu modelu ER jest przeznaczona do wykonywania następujących czynności:

    - Pobierz listę kodów podatków (Źródło danych **podatku**) znajdujących się w tabeli **Tabela Podatkowa**.
    - Pobierz listę kodów transakcji podatkowych (Źródło danych **tansakcji**) znajdujących się w tabeli **Tabela Podatkowa**:
    
        - Umożliwia grupowanie listy pobranych transakcji (**Gr** Źródło danych) według kodów podatków.
        - Oblicz dla zgrupowanych transakcji po wartości zagregowanych według kodu podatku:

            - Suma wartości podstawowych podatku.
            - Suma wartości podatku.
            - Minimalna wartość zastosowanej stawki podatkowej.

    Mapowanie modelu w tej konfiguracji implementuje podstawowy model danych dla dowolnego formatu ER utworzonego dla tego modelu i wykonywany w Finance and Operations. W wyniku tego zawartość źródeł danych **podatków** i **Gr** jest udostępniana dla formatów ER, takich jak abstrakcyjne źródła danych.

    ![Strona projektanta mapowania modelu pokazująca źródła danych podatkowych i Gr.](media/er-calculated-field-type-01.png)

5.  Zamknij stronę **Projektant mapowania modelu**.
6.  Zamknij stronę **Mapowanie modelu**.

### <a name="review-format"></a>Format przeglądu

1. W drzewie konfiguracji rozwiń zawartość **Model, aby uzyskać informacje o elementach sparametryzowanych wywołań**.
2. Wybierz opcję **Format do nauczenia sparametryzowanych wywołań**.
3. Wybierz opcję **Konstruktor**. Format ER jest przeznaczona do wykonywania następujących czynności:

    - Generowanie oświadczenia podatkowego w formacie XML.
    - Zaprezentuj następujące poziomy opodatkowania w sprawozdaniu podatkowym: regularnym, obniżonym i brak.
    - Umożliwia prezentowanie wielu szczegółów na poziomie opodatkowania, mających różną liczbę szczegółów na każdym poziomie.

    ![Strona projektanta formatu.](media/er-calculated-field-type-02.png)

4. Wybierz **Mapowanie**.
5. Rozwiń **Model**, **Dane,** i **podsumowanie**. 

    Obliczone pole **Model.Data.Summary.Level** zawiera wyrażenie zwracające kod poziomu opodatkowania (**zwykły**, **ograniczony**, **brak** lub **inny**) jako wartość tekstowa dla dowolnego kodu podatku, który może zostać pobrany z **Model.Data.Summary** źródła danych w czasie wykonywania.

    ![Strona projektant formatów pokazująca szczegóły modelu modelu danych, aby poznać wywołania parametryczne.](media/er-calculated-field-type-03.png)

6. Rozwiń **Model**.**Dane2**.
7. Rozwiń **Model**.**Dane2.Summary2**.
   
    **Model**.**Data2.Summary2** źródło danych jest skonfigurowane do grupowania **Model.Data.Summary** transakcji źródła danych sumarycznych według poziomu opodatkowania (zwrócone przez pole obliczeniowe **Model.Data.Summary.Level**) i oblicza agregacje.

    ![Strona Projektant formatów pokazująca szczegóły źródła danych Model.Data2.Summary2.](media/er-calculated-field-type-04.png)

8. Umożliwia przejrzenie obliczonych pól **Model**.**Data2.Level1**, **Model**.**Data2.Level2**, and **Model**.**Data2.Level3.** Te pola obliczeniowe służą do filtrowania **Model**.**Dane2.Summary2** rekordów listy i zwracają tylko rekordy reprezentujące określony poziom opodatkowania.
9. Zamknij stronę **Projektowanie formuły**.

## <a name="create-a-derived-format"></a>Tworzenie pochodnego formatu
Można poprawić podany format, dodając jedno pole obliczeniowe w celu odfiltrowania wymaganego poziomu opodatkowania, zamiast korzystać z trzech pól **Model**.**Data2.Level1**, **Model**.**Data2.Level2,** i **Model**.**Data2.Level3**. Wymagany poziom opodatkowania można określić w lokalizacji, w której zostanie wywołane nowe pole obliczeniowe.

1. W drzewie konfiguracji rozwiń zawartość **Model, aby uzyskać informacje o elementach sparametryzowanych wywołań**.
2. Wybierz opcję **Format do nauczenia sparametryzowanych wywołań**.
3. Wybierz **Utwórz konfigurację**.
4. Wybierz **pochodną z Nazwy: Format, aby poznać wywołania sparametryzowane Microsoft**.
5. W polu **nazwa** wprowadź **Format, aby poznać wywołania sparametryzowane (dostosowane)**.
6. Wybierz **Utwórz konfigurację**.

## <a name="configure-a-parameterized-calculated-field-that-returns-a-list-of-records"></a>Skonfiguruj sparametryzowane pole obliczeniowe, które zwraca listę rekordów

### <a name="start-adding-a-new-calculated-field"></a>Rozpocznij dodawanie nowego pola obliczeniowego

1. Wybierz opcję **Konstruktor**.
2. Wybierz **Rozwiń/Zwiń**, aby rozwinąć wszystkie elementy formatu.
3. Wybierz **Mapowanie**.
4. Rozwiń **Model**.
5. Wybierz  **Model.Data2**.
6. Wybierz opcję **Dodaj**.
7. Wybierz **Funkcje\\Pole obliczeniowe**.
8. W polu **Nazwa** wprowadź nazwę **Poziomy**.
9. Wybierz opcję **Edytuj formułę**.

### <a name="define-a-parameter-for-adding-a-calculated-field"></a>Definiowanie parametru służącego do dodawania pola obliczeniowego

1. Wybierz **Parametry**.
2. Wybierz pozycję **Nowy**.
3. W polu **Nazwa** wpisz **Poziom opodatkowania**.
4. W polu **Typ** wybierz **Ciąg**.

    Do określania typu argumentu parametru mogą być używane tylko pierwotne typy danych Dlatego w tym celu nie można używać **Listy rekordów**, **Rekordu** i **Wyliczeń**.

    Maksymalna liczba parametrów, które można określić dla pojedynczego pola obliczeniowego wynosi 8.

    ![Lista źródeł danych parametrów.](media/er-calculated-field-type-05.png)

5. Kliknij przycisk **OK**.

Dodając ten parametr, należy określić warunek, który musi mieć miejsce w celu wywołania tego pola obliczeniowego. Po wywołaniu tego pola obliczeniowego należy określić argument parametru **poziomu opodatkowania** jako wartość w formacie **ciągu**.

   Należy się upewnić, że parametry są definiowane tylko dla tych pól obliczeniowych, które znajdują się w kontenerze (**Lista rekordów**, **Rekord** lub **Kontener**).

   Skonfigurowany parametr jest dostępny na liście źródeł danych dla tego pola obliczeniowego. Ten parametr można dodać do skonfigurowanego wyrażenia, wybierając opcję **Dodaj źródło danych**.

   ![Pola źródła danych.](media/er-calculated-field-type-06.png)

### <a name="define-an-expression-for-adding-a-calculated-field"></a>Definiowanie wyrażenia służącego do dodawania pola obliczeniowego

1. W polu **Formuła** wpisz: 

    **WHERE(\@.Summary2, \@.Summary2.grouped.Level =**
    
2. Wybierz parametr **poziomu opodatkowania** z listy źródeł danych.
3. Wybierz **Dodaj źródło danych**.
4. W polu **Formuła** skończ następujące wyrażenie:  

    **WHERE(\@.Summary2, \@.Summary2.grouped.Level = 'Taxation Level')**

5. Wybierz opcję **Zapisz**.

    ![Informacje dotyczące pola źródła danych.](media/er-calculated-field-type-07.png)

6. Zamknij stronę **Projektowanie formuły**.

### <a name="finish-adding-a-new-calculated-field"></a>Skończ dodawanie nowego pola obliczeniowego

- Kliknij przycisk **OK**.

Na stronie **Projektant formatu** dla skonfigurowanych **poziomów** pól obliczeniowych z parametrami jest wymagany argument typu **ciąg**.

![Rozszerzona lista poziomów pól obliczeniowych.](media/er-calculated-field-type-08.png)

### <a name="use-the-configured-calculated-field-for-binding-format-elements"></a>Dla elementów formatu powiązania należy zastosować skonfigurowane pole obliczeniowe

1. Wybierz **Model.Data2.Levels** poziomy, aby wybrać skonfigurowane pole obliczeniowe.
2. Umożliwia wybranie **elemeStatement.Taxation.Regular**.
3. Wybierz **Powiąż**.
4. Wybierz **tak**, aby potwierdzić zastąpienie aktualnie używanego źródła danych **, Level1**, według nowego źródła danych, **poziomów** we wszystkich zagnieżdżonych elementach formatu wybranego elementu formatu.

    Zastosowane powiązanie zostało skompilowane jako wywołanie pola obliczeniowego sparametryzowanego. Domyślnie nazwa elementu formatu powiązanego jest używana jako argument dla sparametryzowanego pola obliczeniowego w następujących warunkach:

      - W polu obliczeniowym jest skonfigurowane użycie jednego parametru.
      - Typ danych tego parametru jest zdefiniowany jako **ciąg**.

    Jeśli nazwa elementu formatu powiązanego jest pusta, nazwa źródła danych tego elementu jest używana w zastosowaniu powiązania.

5. Wybierz element formatu **Statement.Taxation.Reduced**.
6. Wybierz **Powiąż**.
7. Wybierz **tak**, aby potwierdzić zastąpienie aktualnie używanego źródła danych **, Level2**, według nowego źródła danych, **poziomów** we wszystkich zagnieżdżonych elementach formatu poniżej wybranego elementu formatu.
8. Wybierz element formatu **Statement.Taxation.None**.
9. Wybierz **Powiąż**.
10. Wybierz **tak**, aby potwierdzić zastąpienie aktualnie używanego źródła danych **Level3**, według nowego źródła danych, **poziomów** we wszystkich zagnieżdżonych elementach formatu poniżej wybranego elementu formatu.

   Po określeniu argumentu sparametryzowanego pola obliczeniowego dla elementu XML reprezentującego poziom opodatkowania (na przykład **Model.Data2.Levels(„zmniejszone”)** jako wartość tekstową), nie trzeba tego robić w przypadku zagnieżdżonych atrybutów XML — ich powiązania automatycznie odziedziczą wartość argumentu zdefiniowanego na poziomie nadrzędnym (**Model.Data2.Levels.aggregated.Base**, a nie **Model.Data2.Levels("Reduced").aggregated.Base**).

Cykliczne wywołania wszelkich sparametryzowanych pól obliczeniowych nie są obsługiwane.

Można wybrać opcję **Edytuj formułę** i zmienić argument zastosowany przez domyślny dla sparametryzowanego pola obliczeniowego w wybranym powiązaniu. Brak tego argumentu może spowodować błędy w czasie wykonywania — użytkownicy są informowani o takiej sytuacji w przypadku sprawdzania poprawności bieżącego formatu.

![Powiadomienie o sprawdzeniu poprawności.](media/er-calculated-field-type-10.png)

## <a name="configure-a-parameterized-calculated-field-to-return-a-record"></a>Skonfiguruj sparametryzowane pole obliczeniowe, które zwraca rekord
Jeśli sparametryzowane pole obliczeniowe zwraca rekord, należy obsługiwać powiązanie poszczególnych pól tego rekordu, aby formatować elementy. W takich przypadkach nie zostanie utworzone powiązanie nadrzędne zawierające wartość argumentu wywołującego sparametryzowane pole obliczeniowe — ta wartość musi być zdefiniowana w powiązaniu pola z pojedynczym rekordem.

### <a name="start-adding-a-new-calculated-field"></a>Rozpocznij dodawanie nowego pola obliczeniowego

1. Wybierz  **Model.Data2**.
2. Wybierz opcję **Dodaj**.
3. Wybierz **Funkcje\\Pole obliczeniowe**.
4. W polu **Nazwa** wpisz **LevelRecord**.
5. Wybierz opcję **Edytuj formułę**.

### <a name="define-a-parameter-for-adding-a-calculated-field"></a>Definiowanie parametru służącego do dodawania pola obliczeniowego

1. Wybierz **Parametry**.
2. Wybierz pozycję **Nowy**.
3. W polu **Nazwa** wpisz **Poziom opodatkowania**.
4. W polu **Typ** wybierz **Ciąg**.
5. Kliknij przycisk **OK**.

### <a name="define-an-expression-for-adding-a-calculated-field"></a>Definiowanie wyrażenia służącego do dodawania pola obliczeniowego

1. W polu **Formuła** wprowadź następujące:  
    
    **FIRSTORNULL(\@.Levels(**

2. Wybierz parametru **poziomu opodatkowania**.
3. Wybierz **Dodaj źródło danych**.
4. W polu **formuła** dołącz **„poziom opodatkowania”))** do tego, co zostało wprowadzone w kroku 1, aby zakończyć wyrażenie:  
    
    **FIRSTORNULL(\@.Levels(„poziom opodatkowania”))**

5. Wybierz opcję **Zapisz**.
6. Zamknij stronę **Projektowanie formuły**.

### <a name="finish-adding-a-new-calculated-field"></a>Skończ dodawanie nowego pola obliczeniowego

-   Kliknij przycisk **OK**.

### <a name="use-the-configured-calculated-field-to-bind-format-elements"></a>Dla elementów formatu powiązania należy zastosować skonfigurowane pole obliczeniowe

1. Rozwiń **Model.Data2.LevelRecord** poziomy, aby wybrać skonfigurowane pole obliczeniowe.
2. Rozwiń **Model.Data2.LevelRecord.aggregated** kontener, aby wybrać skonfigurowane pole obliczeniowe.
3. Wybierz **Model.Data2.LevelRecord.aggregated.Base**.
4. Wybierz element formatu **Statement.Taxation.None**.
5. Wybierz **Odwiąż**.
6. Wybierz element formatu **Statement.Taxation.Base**.
7. Wybierz **Powiąż**.
8. Wybierz opcję **Edytuj formułę**.
9. Zmień wyrażenie na **Model.Data2.LevelRecord("None").aggregated.Base**.

![Aktualizowane wyrażenie.](media/er-calculated-field-type-11.png)

## <a name="remove-calculated-fields-that-are-not-used"></a>Usuń pola obliczeniowe, które nie są używane

1. Wybierz **Model.Data2.Level1**.
2. Wybierz opcję **Usuń**.
3. Wybierz **Model.Data2.Level2**.
4. Wybierz opcję **Usuń**.
5. Wybierz **Model.Data2.Level3**.
6. Wybierz opcję **Usuń**.
7. Wybierz opcję **Zapisz**.

  > [!NOTE]
  > Ponownie użyto tego samego modelu pola **Model.Data2.Levels** w powiązaniach formatu. Znacznie łatwiej jest używać jednego pola obliczeniowego i utrzymywać je w odniesieniu do wielu podobnych pól.

8. Zamknij stronę **Projektowanie formuły**.

## <a name="complete-adjusted-version-of-a-derived-format"></a>Pełna skorygowana wersja formatu pochodnego

1. W obszarze **wersje** na skróconej karcie wybierz opcję **Zmień stan**.
2. Wybierz opcję **Zakończone**.

## <a name="export-completed-version-of-a-derived-format"></a>Eksport skończonej wersji formatu pochodnego

1. Wybierz **Format, aby uzyskać informacje o formacie wywołań sparametryzowanych (niestandardowy)** w drzewie konfiguracje.
2. W obszarze **wersje** na skróconej karcie wybierz wersję zakończoną 1.1.1.
3. Wybierz **Zamień**.
4. Wybierz **Eksportuj jako plik XML**.
5. Przechowaj pobraną konfigurację lokalnie w formacie XML.

## <a name="test-er-formats"></a>Testowanie formatów ER 
Można uruchomić wstępne i ulepszone formaty ER, aby upewnić się, że skonfigurowane pola obliczeniowe o sparametryzowanym działaniu będą działać prawidłowo.

### <a name="import-er-configurations"></a>Importowanie konfiguracji ER
Przejrzane konfiguracje można importować ze RCS za pomocą repozytorium ER typu **RCS.** Jeśli wykonano już kroki opisane w temacie, należy [zaimportować konfiguracje raportowania elektronicznego z usług Regulatory Configuration Services (RCS)](rcs-download-configurations.md), a następnie skorzystać z skonfigurowanego repozytorium ER, aby zaimportować konfiguracje opisane wcześniej w tym temacie do środowiska. W innym razie należy wykonać następujące czynności:

1. Wybierz firmę **DEMF** i na domyślnym pulpicie nawigacyjnym, wybierz opcję **Raportowanie elektroniczne**.
2. Wybierz **Raportowanie konfiguracji**.
3. Zaimportuj pobrane konfiguracje z Microsoft Download Center w następującej kolejności: model danych, metadane, mapowanie modelu, format. W każdej konfiguracji modułu ER należy wykonać następujące kroki:

    1. Wybierz **Zamień**.
    2. Wybierz **Załaduj z pliku XML**.
    3. Kliknij przycisk **Przeglądaj**, nastepnie wybierz odpowiedni plik wymaganej konfiguracji ER w formacie XML.
    4. Kliknij przycisk **OK**.

4. Zaimportuj eksport ze RCS ukończył wersję 1.1.1 formatu , aby uzyskać informacje o **formacie sparametryzowanych wywołań (niestandardowych)**:

    1. Wybierz **Zamień**.
    2. Wybierz **Załaduj z pliku XML**.
    3. Wybierz **Przegladaj**, aby wybrać **format przechowywany lokalnie, aby poznać plik wywołań sparametryzowanych (niestandardowych)** w formacie XML.
    4. Kliknij przycisk **OK**.

### <a name="run-er-formats"></a>Uruchamianie formatów ER

1. W drzewie konfiguracji rozwiń zawartość **Model, aby uzyskać informacje o elementach sparametryzowanych wywołań**.
2. Wybierz opcję **Format do nauczenia sparametryzowanych wywołań**.
3. Wybierz **Uruchom** na wstążce u góry.
4. Zapisz wygenerowane lokalnie dane wyjściowe.
5. Wybierz opcję **Format do nauczenia sparametryzowanych wywołań (niestandardowe)**.
6. Wybierz **Uruchom** na wstążce u góry.
7. Zapisz wygenerowane lokalnie dane wyjściowe. 
8. Umożliwia porównanie zawartości wygenerowanych wyjść.

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Projektant formuł w module Raportowanie elektroniczne (ER)](general-electronic-reporting-formula-designer.md)
- [Zwiększ wydajność rozwiązań Raportowania elektronicznego, dodając sparametryzowane źródła danych PÓL OBLICZENIOWYCH](er-calculated-field-ds-performance.md)



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]