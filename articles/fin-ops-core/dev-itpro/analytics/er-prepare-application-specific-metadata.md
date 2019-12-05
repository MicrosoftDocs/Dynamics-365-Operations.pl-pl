---
title: Przygotuj metadane dla konkretnej aplikacji dla RCS i ER
description: Kroki w tym temacie wyjaśniają, w jaki sposób można przygotować metadane konkretnej aplikacji dla usługi Regulatory configuration service (RCS) oraz Elektronicznego raportowania (ER).
author: NickSelin
manager: AnnBe
ms.date: 04/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERWorkspace
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 89d36c305bc9210f7906cd4288e33e5028baecdb
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/06/2019
ms.locfileid: "2771267"
---
# <a name="prepare-application-specific-metadata-for-rcs-and-er"></a>Przygotuj metadane dla konkretnej aplikacji dla RCS i ER

[!include[banner](../includes/banner.md)]

W tym temacie przedstawiono przykłady następujących zadań:

- [Przygotuj metadane dla konkretnej aplikacji dla użycia w RCS](#prepare-application-metadata-that-can-be-used-in-rcs)
- [Uzyskaj dostęp do metadanych aplikacji za pomocą konfiguracji ER](#access-application-metadata-by-using-an-er-configuration)
- [Uzyskaj dostęp do metadanych aplikacji za pomocą połączonych aplikacji](#access-application-metadata-by-using-connected-applications)

## <a name="prepare-application-metadata-that-can-be-used-in-rcs"></a>Przygotuj metadane dla konkretnej aplikacji dla użycia w RCS

Poniższa procedura pokazuje, w jaki sposób użytkownik, który ma rolę **Administratora Systemu** lub **Programisty Elektronicznego Reportowania**, może utworzyć konfigurację raportowania elektronicznego (ER), która zawiera metadane aplikacji, która jest używana do projektowania konfiguracji mapowania modeli ER w usłudze Regulatory configuration service (RCS). Przykładowe mapowanie modelu ER zostanie stworzone w tym przykładzie do uzyskania dostępu do transakcji handlu zagranicznego.

W tym przykładzie chcesz użyć RCS do zaprojektowania rozwiązania ER dla aplikacji, które będzie wykorzystywane do generowania dokumentów elektronicznych zawierających informacje z dziedziny handlu zagranicznego. Aby określić mapowanie między modelem danych ER a źródłami wymaganych danych, musisz mieć dostęp do metadanych aplikacji w RCS. Dlatego też, w ramach procesu projektowania rozwiązania ER, należy skonfigurować nową konfigurację metadanych ER, która zawiera wszystkie metadane, które są obecnie wymagane w celu wygenerowania raportów ER dla wybranej domeny biznesowej.

> [!NOTE]
> W tym przykładzie utworzysz konfigurację dla przykładowej firmy Litware, Inc. Te kroki można wykonać dla dowolnej firmy.

1. Wybierz kolejno opcje **Administrowanie organizacją \> Obszary robocze \> Raportowanie elektroniczne**.
2. Upewnij się, że dostawca konfiguracji dla przykładowej firmy Litware, Inc. jest dostępny i oznaczony jako **Aktywny** Jeśli nie widzisz dostawcy konfiguracji, musisz wykonać kroki opisane w procedurze, [Tworzenie dostawców konfiguracji i oznaczanie ich jako aktywnych](tasks/er-configuration-provider-mark-it-active-2016-11.md). 
3. Wybierz **Konfiguracja metadanych**.
4. Wybierz **Utwórz konfigurację**.
5. W rozwijanym menu w polu **Nazwa** wpisz nazwę. Dla tego przykładu wpisz **Metadane handlu zagranicznego**.
6. Wybierz **Utwórz konfigurację**.
7. Wybierz opcję **Konstruktor**.
8. Wybierz opcję **Dodaj**.

    > [!NOTE]
    > Możesz wybrać wszystkie metadane dla całej aplikacji lub dla wybranych modeli lub modułów. W obu przypadkach należy pamiętać, że następujące metadane zostaną automatycznie dodane: tabele, wyliczenia i rozszerzone typy danych (EDT). Gdy wymagane są dodatkowe typy metadanych, należy je ręcznie dodać.

    Musisz dodać kilka metadanych związanych z transakcjami handlu zagranicznego i ręcznie wybrać elementy metadanych.

9. Wybierz **Dodaj źródło danych \> Tabele**.
10. Filtruj wartość **Intrastat** w polu **Nazwa**.
11. Wybierz tabelę **Intrastat**.
12. Kliknij przycisk **OK**.

    Musisz dodać informacje metadanych o tabeli Intrastat.

13. W widoku drzewa wybierz **Tabele Intrastat \> \>Relacje \> IntrastatCommodity (Tabele EcoResCategory)**.
14. Wybierz **Dodaj metadane**.

    > [!NOTE]
    > Metadane dotyczące wymaganych relacji dla wybranej tabeli muszą zostać dodane ręcznie.

15. Wybierz **Dodaj źródło danych**.
16. Wybierz **Wyliczenie**.
17. Filtruj wartość **IntrastatDirection** w polu **Nazwa**.
18. Wybierz dane wyliczenia w **IntrastatDirection**.
19. Kliknij przycisk **OK**.
20. Wybierz opcję **Zapisz**.
21. Zamknij stronę.
22. Wypełnij wersję roboczą konfiguracji metadanych:

    1. Wybierz **Zmień status \> Zakończone**.
    2. Kliknij przycisk **OK**.
    3. Wybierz ukończoną wersję 1.

23. Wyeksportuj ukończoną wersję konfiguracji metadanych z aplikacji jako plik XML:

    1. Wybierz **Zamień \> Eksportuj jako plik XML**.
    2. Kliknij przycisk **OK**.

Utworzona konfiguracja metadanych ER jest zapisywana jako plik **Zagraniczny handel metadane.xml**. Możesz teraz zaimportować go do RCS, aby mógł być używany jako źródło metadanych dla domeny handlu zagranicznego. Na podstawie tych informacji można określić mapowanie między metadanymi aplikacji a modelem danych ER.

## <a name="access-application-metadata-by-using-an-er-configuration"></a>Uzyskaj dostęp do metadanych aplikacji za pomocą konfiguracji ER

Poniższa procedura pokazuje, w jaki sposób użytkownik RCS, który ma rolę **Administratora Systemu** lub **Programisty Elektronicznego Reportowania**, może zaprojektować nowe mapowanie modelu ER przy użyciu metadanych z aplikacji. Dostęp do metadanych aplikacji będzie możliwy za pomocą konfiguracji metadanych ER, która zawiera przykładowy zestaw metadanych umożliwiających dostęp do transakcji handlu zagranicznego.

Przed zakończeniem tej procedury, należy najpierw wypełnić następujące procedury:

- [Tworzenie dostawców konfiguracji i oznaczanie ich jako aktywnych](tasks/er-configuration-provider-mark-it-active-2016-11.md)
- [Przygotuj metadane dla konkretnej aplikacji dla użycia w RCS](#prepare-application-metadata-that-can-be-used-in-rcs)

1. Otwórz **Wszystkie miejsca prac \> Electroniczne Raportowanie**.
2. Upewnij się, że dostawca konfiguracji dla przykładowej firmy Litware, Inc. jest dostępny i oznaczony jako **Aktywny** Jeśli nie widzisz dostawcy konfiguracji, musisz wykonać kroki opisane w procedurze, [Tworzenie dostawców konfiguracji i oznaczanie ich jako aktywnych](tasks/er-configuration-provider-mark-it-active-2016-11.md). 
3. Zaimportuj konfigurację metadanych ER, która zawiera metadane z aplikacji, i która jest skonfigurowana do generowania dokumentów elektronicznych dla domeny biznesowej handlu zagranicznego. Stworzona konfiguracja metadanych ER została wyeksportowana jako plik XML w opisanej wcześniej procedurze [Przygotuj metadane aplikacji do użycia w RCS](#prepare-application-metadata-that-can-be-used-in-rcs).

    1. Wybierz **Konfiguracje metadanych**.
    2. Wybierz **Zamień**.
    3. Wybierz **Załaduj z pliku XML**.
    4. Przeglądaj i wybierz plik **Handel zagraniczny metadane.xml**.
    5. Kliknij przycisk **OK**.
    6. Zamknij stronę.

4. Stwórz model danych konfiguracji:

    1. Wybierz **Raportowanie konfiguracji**.
    2. Wybierz **Utwórz konfigurację**.
    3. W rozwijanym menu w polu **Nazwa** wpisz **Model handlu zagranicznego**.
    4. Wybierz **Utwórz konfigurację**.
    5. Wybierz opcję **Konstruktor**.
    6. Wybierz **Nowe**, aby otworzyć listę rozwijania.

        1. W polu **Nazwa** wpisz **Źródło**.
        2. Wybierz opcję **Dodaj**.
    
    7. Wybierz **Nowe**, aby otworzyć listę rozwijania.

        1. W polu **Nazwa** wpisz **Transakcje**.
        2. W polu **Kod przedmiotu** wybierz **Lista tabel**.
        3. Wybierz opcję **Dodaj**.
 
    8. Wybierz **Nowe**, aby otworzyć listę rozwijania.

        1. W polu **Nazwa** wpisz **Kod towaru**.
        2. W polu **Typ przedmiotu** wybierz **Ciąg**.
        3. Wybierz opcję **Dodaj**.

    9. Wybierz **Nowe**, aby otworzyć listę rozwijania.

        1. W polu Nazwa wpisz **Kwota zafakturowana**.
        2. W polu **Typ przedmiotu** wybierz **Rzeczywisty**.
        3. Wybierz opcję **Dodaj**.

    10. Wybierz **Nowe**, aby otworzyć listę rozwijania.

        1. W polu **Nazwa** wpisz **Data**.
        2. W polu **Typ przedmiotu** wybierz **Data**.
        3. Wybierz opcję **Dodaj**.
 
    11. Wybierz **Dodaj \> Odniesienia do źródeł**.
    12. Kliknij przycisk **OK**.
    13. Wybierz opcję **Zapisz**.
    14. Zamknij stronę.
    15. Wybierz **Zmień status \> Zakończone**.
    16. Kliknij przycisk **OK**.

5. Stwórz model konfiguracji mapowania:

    1. Wybierz **Utwórz konfigurację**.
    2. W rozwijanym polu **Nowe** wpisz **Model mapowania oparty na modelu danych Model handlu zagranicznego**.
    3. W polu **Nazwa** wpisz **Mapowanie handlu zagranicznego**.
    4. Wybierz **Utwórz konfigurację**.
    5. Na skróconej karcie **Wymagania** wybierz **Edytuj**.
    6. Wybierz pozycję **Nowy**.
    7. W polu **Wymagany typ komponentu** wybierz **Konfiguracja**.
    8. Wybierz konfigurację **Metadane handlu zagranicznego**.
    9. Wybierz opcję **Zapisz**. Dodaliśmy odniesienie do wersji pierwszej konfiguracji **Metadane handlu zagranicznego**. Metadane aplikacji z tej konfiguracji będą proponowane podczas projektowania tego modelu mapowania.
    10. Zamknij stronę.
    11. Wybierz opcję **Konstruktor**.
    12. Wybierz opcję **Konstruktor**.
    13. W widoku drzewa wybierz **Dynamics 365 for Operations \> Tabele**.
    14. Wybierz **Dodaj element główny**.
    15. W polu **Nazwa** wpisz **Intrastat**.
    16. Wybierz tabelę danych **Intrastat**.
    17. Kliknij przycisk **OK**.

        > [!NOTE]
        > Jedynie 2 tabele są proponowane, ponieważ tylko 2 tabele zostały dodane do zestawu metadanych, który jest aktualnie używany.

    18. Wybierz **Powiąż**.
    19. W widoku drzewa wybierz **Intrastat \> AmountMST**.
    20. W widoku drzewa wybierz **Transakcja = Intrastat \> Kwota zafakturowana**.
    21. Wybierz **Powiąż**.
    22. W widoku drzewa wybierz **Intrastat \> TransDate**.
    23. W widoku drzewa wybierz **Transakcja = Intrastat \> Data**.
    24. Wybierz **Powiąż**.
    25. W widoku drzewa wybierz **Intrastat \> \>Relacje \> IntrastatCommodity \> Kod**.
    26. W widoku drzewa wybierz **Transakcja = Intrastat \> Kod towaru**.
    27. Wybierz **Powiąż**.
    28. Wybierz **Potwierdź**.

        > [!NOTE]
        > Po zakończeniu zatwierdzania, udało nam się powiązać elementy modelu danych z elementami źródeł danych opisanymi przy użyciu szczegółów metadanych aplikacji, do której odwołanie znajduje się w konfiguracji metadanych ER.

    29. Wybierz opcję **Zapisz**.

Jeśli musisz rozszerzyć istniejący zestaw metadanych, możesz to zrobić w aplikacji. Następnie można wyeksportować nową ukończoną wersję konfiguracji metadanych ER, zaimportować ją do RCS i zaktualizować wymagania wstępne skonfigurowanej konfiguracji mapowania modelu w odniesieniu do nowej wersji importowanej konfiguracji metadanych.

> [!NOTE]
> Ten sposób uzyskiwania informacji o metadanych aplikacji jest jedynym dostępnym dla aplikacji wdrażanych lokalnie (w przypadku gdy używany jest lokalny model danych biznesowych \[LBD\] lub lokalny model wdrażania jest używany dla aplikacji).

## <a name="access-application-metadata-by-using-connected-applications"></a>Uzyskaj dostęp do metadanych aplikacji za pomocą połączonych aplikacji

Poniższa procedura pokazuje, w jaki sposób użytkownik RCS, który ma rolę **Administratora Systemu** lub **Programisty Elektronicznego Reportowania**, może zaprojektować nowe mapowanie modelu ER przy użyciu metadanych aplikacji. Metadane aplikacji będą dostępne online za pomocą aplikacji połączonej z RCS. Przykładowe mapowanie modelu ER zostanie skonfigurowane dla dostępu do transakcji handlu zagranicznego.

Żeby zakończyć tą procedurę, musisz wykonać kroki opisane w procedurze, [Tworzenie dostawców konfiguracji i oznaczanie ich jako aktywnych](tasks/er-configuration-provider-mark-it-active-2016-11.md) w RCS. Jeśli jeszcze nie ukończyłeś [Dostęp do metadanych aplikacji przy użyciu konfiguracji ER](#access-application-metadata-by-using-an-er-configuration) procedury opisanej wcześniej w tym temacie, przejdź do strony [Przewodniki zadań elktronicznego raportowania dla Dynamics 365 for Finance and Operations 8.1](https://go.microsoft.com/fwlink/?linkid=2082739), aby pobrać z następujące pliki konfiguracyjne ER i zapisać je lokalnie: **Handel zagraniczny metadane.xml**, **Handel zagraniczny model.xml** i **Handel zagraniczny mapowanie.xml**.


### <a name="get-required-er-configurations"></a>Uzyskaj wymagane konfiguracje ER

Jeśli wykonałeś już kroki w procedurze [Uzyskaj dostęp do metadanych aplikacji przy użyciu konfiguracji ER](#access-application-metadata-by-using-an-er-configuration) i masz już wszystkie niezbędne konfiguracje ER (metadane handlu zagranicznego, model i konfiguracje mapowania) w bieżącej instancji RCS. W takim przypadku pomiń tą procedurę.

1. Otwórz **Wszystkie miejsca prac \> Electroniczne Raportowanie**.
2. Wybierz **Raportowanie konfiguracji**.
3. Załaduj pliki konfiguracyjne **handel zagraniczny metadane.xml**, **Handel zagraniczny model.xml**, and **Handel zagraniczny mapowanie.xml** i powtórz następujące czynności dla każdego z nich:

    1. Wybierz **Zamień**.
    2. Wybierz **Załaduj z pliku XML**.
    3. Wybierz **Przeglądaj** i wybierz plik.
    4. Kliknij przycisk **OK**.

### <a name="register-the-connection-with-the-application"></a>Zarejestruj połączenie z aplikacją

1. Otwórz **Wszystkie miejsca prac \> Electroniczne Raportowanie**.
2. Wybierz **Połączone aplikacje**.
3. Upewnij się, że skonfigurowana aplikacja jest oparta na Microsoft Azure i ogólnie dostępna dla użytkowników RCS. Wymagane jest również, aby bieżący użytkownik RCS miał dostęp do konfigurowanej aplikacji i został zarejestrowany jako użytkownik tej aplikacji, odgrywając rolę dającą mu uprawnienia dostępu do metadanych aplikacji.
4. Wybierz pozycję **Nowy**.
5. W polu **Nazwa** wpisz **MyConnectedApp** jako nazwę połączonej aplikacji.
6. W polu **Aplikacja** wpisz URL aplikacji.
7. W polu **Dzierżawca** wpisz dostawcę aplikacji.
8. Wybierz opcję **Zapisz**. 
9. Po sprawdzeniu połączenia ze skonfigurowaną aplikacją na **Połącz ze zdalną aplikacją** kliknij link **Kliknij tutaj, aby połączyć się z wybraną aplikacją zdalną**. 
10. Wybierz **Sprawdź połączenie**, żeby sprawdzić dostęp do skonfigurowanej aplikacji.
11. Kliknij przycisk **Zamknij**.

Gdy wykonasz tą procedurę i sprawdzenie poprawności połączenia powiedzie się, szczegóły wersji i dzierżawcy zostaną zaktualizowane dla skonfigurowanej aplikacji w bieżącej sieci.

### <a name="review-the-existing-model-mapping-configuration"></a>Przejrzyj istniejącą konfigurację mapowania konfiguracji

1. Otwórz **Wszystkie miejsca prac \> Electroniczne Raportowanie**.
2. Wybierz **Raportowanie konfiguracji**.
3. W widoku drzewa wybierz **Model handlu zagranicznego \> Handel zagraniczny mapowanie**.
4. Na skróconej karcie wybierz **Wymagania**.

    > [!NOTE]
    > Obecnie to mapowanie odnosi się do konfiguracji metadanych. Metadane aplikacji z tej konfiguracji będą proponowane podczas projektowania danego modelu mapowania.

4. Wybierz opcję **Konstruktor**.
5. Wybierz opcję **Konstruktor**.
6. W widoku drzewa wybierz **Dynamics 365 for Operations \> Tabele**.
7. Wybierz **Dodaj element główny**.
8. W polu **Tabela** wpisz wartość.

    > [!NOTE]
    > Obecnie to mapowanie odnosi się do konfiguracji metadanych. Metadane aplikacji z tej konfiguracji będą proponowane podczas projektowania danego modelu mapowania.

9. Wybierz **Anuluj**.

### <a name="assign-the-connected-application-to-a-model-mapping"></a>Przypisz daną podłączoną aplikację do mapowania modelu

1. Wybierz opcję **Edycja**.
2. W polu **Połączona aplikacja** wybierz aplikaję **MyConnectedApp**.

    > [!NOTE]
    > To mapowanie odnosi się do metadanych wybranej połączonej aplikacji. Jeśli to samo mapowanie odnosi się do konfiguracji metadanych i połączonej aplikacji w tym samym czasie, zostaną użyte metadane połączonej aplikacji.

3. Wybierz opcję **Konstruktor**.
4. Wybierz opcję **Konstruktor**.
5. W widoku drzewa wybierz **Dynamics 365 for Operations \> Tabele**.
6. Wybierz **Dodaj element główny**.
7. W polu **Tabela** wpisz wartość.

    > [!NOTE]
    > W tym momencie, zaproponowano więcej niż dwie tabele aplikacji, ponieważ to mapowanie wykorzystuje wszystkie metadane połączonej aplikacji, która została do niej przypisana.

8. Wybierz **Anuluj**.
9. Wybierz **Potwierdź**.

Udało się powiązać elementy modelu danych z elementami źródeł danych opisanymi przy użyciu szczegółów metadanych połączonej aplikacji, która została przypisana do tego mapowania.

Jeśli trzeba ocenić ten model mapowania przy użyciu metadanych innej wersji aplikacji, zarejestruj inną połączoną aplikację, przypisz ją do tego mapowania modelu i sprawdź poprawność względem nowych metadanych.

## <a name="additional-resources"></a>Dodatkowe zasoby

Możesz również otworzyć instrukcje **Przygotuj metadane aplikacji, które mogą być użyte w RCS** w aplikacji lub **Uzyskaj dostęp do metadanych aplikacji przez konfigurację ER** i **Uzyskaj dostęp do metadanych aplikacji przez inne połączone aplikacje** w RCS. Te przewodniki mogą zostać pobrane ze strony [Przewodniki Elektronicznego Raportowania dla Dynamics 365 for Finance and Operations 8.1](https://go.microsoft.com/fwlink/?linkid=2082739).
