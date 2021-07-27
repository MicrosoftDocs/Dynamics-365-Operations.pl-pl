---
title: Zautomatyzuj testowanie dzięki Elektronicznemu reportowaniu
description: W tym temacie wyjaśniono, w jaki sposób można skorzystać z podstawowej funkcji platformy Elektroniczne raportowanie (ER) w celu zautomatyzowania testowania funkcjonalności.
author: NickSelin
ms.date: 07/02/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERFormatBaselineTable, ERFormatMappingRunLogTable, ERParameters
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.openlocfilehash: 6b8e3d129c40e33aeb91e823528a3bc89d2d9568
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/06/2021
ms.locfileid: "6351873"
---
# <a name="automate-testing-with-electronic-reporting"></a>Automatyzacja testowania za pomocą modułu Raportowanie elektroniczne

[!include[banner](../includes/banner.md)]

W tym temacie wyjaśniono, w jaki sposób można skorzystać z podstawowej funkcji platformy Elektroniczne raportowanie (ER) w celu zautomatyzowania testowania funkcjonalności. Przykład w tym temacie pokazuje, jak zautomatyzować testowanie przetwarzania płatności dostawców.

Aplikacja korzysta z platformy ER do generowania plików płatności i odpowiednich dokumentów podczas przetwarzania płatności dostawcy. Struktura ER składa się z modelu danych, mapowań modeli i komponentów formatu, które obsługują przetwarzanie płatności dla różnych typów płatności i generowanie dokumentów w różnych formatach. Te komponenty mogą być pobrane z usługi Microsoft Dynamics Lifecycle Services (LCS) i importowane do instancji.

Możesz także dostosować każdy komponent Microsoft i użyć go jako podstawy własnego komponentu niestandardowego. Tworząc niestandardową wersję, możesz wprowadzać zmiany obsługujące określone wymagania. Na przykład można dostosować model danych ER i mapowanie modelu ER, aby uzyskać dostęp do danych aplikacji specyficznych dla klienta, lub zmienić format ER, aby zmodyfikować układ wygenerowanego dokumentu.

Można użyć niestandardowych formatów ER, aby przetworzyć pliki płatności generujące płatności od dostawców, a także raporty kontroli procesu. Wersjonowanie jest obsługiwane w komponentach ER. W związku z tym firma Microsoft może dostarczyć zaktualizowane wersje rozwiązań ER do przetwarzania płatności od dostawców i można automatycznie scalić zaktualizowaną wersję z Twoim dostosowanym komponentem, zmieniając ją. Musisz jednak przetestować wersję opartą na ponownie, aby upewnić się, że działa zgodnie z oczekiwaniami.

Modele danych ER i mapowania modelu ER są wspólne dla wielu formatów ER, które są używane do przetwarzania płatności różnych typów i do generowania dokumentów płatności specyficznych dla kraju/regionu. Dlatego wysoce pożądane jest zautomatyzowanie testów akceptacji użytkowników i integracji, tak aby były one automatycznie wykonywane w wielu firmach, ale uwzględniają kontekst kraju/regionu każdej firmy docelowej, używają różnych zestawów danych i tak dalej.

Aby uzyskać więcej informacji na temat tworzenia niestandardowej wersji formatu opartego na formacie otrzymanym od dostawcy konfiguracji, zobacz [ER Uaktualnij swój format, przyjmując nową, podstawową wersję tego formatu](./tasks/er-upgrade-format.md).

## <a name="key-concepts"></a>Podstawowe pojęcia

Użytkownicy mocy funkcjonalnej mogą tworzyć testy akceptacji i integracji użytkowników bez konieczności pisania kodu źródłowego.

- Użyj funkcji linii bazowej ER, aby porównać wygenerowane dokumenty do kopii wzorcowych. Więcej informacji możesz przeczytać w [Śledź wygenerowane wyniki raportu i porównaj je z wartościami bazowymi](er-trace-reports-compare-baseline.md).
- Użyj Rejestratora zadań do rejestrowania przypadków testowych i uwzględnij ocenę bazową. Więcej informacji można znaleźć w see [Zasoby Rejestratora zadań](../user-interface/task-recorder.md).
- Grupuj przypadki testowe dla wymaganych scenariuszy testowych. Aby uzyskać więcej informacji, zajrzyj do części [Tworzenie i automatyzowanie testów akceptacji użytkownika](../lifecycle-services/using-task-guides-and-bpm-to-create-user-acceptance-tests.md).

    - Użyj narzędzia Business Process Modeler (BPM) w LCS, aby stworzyć biblioteki do testów akceptacji użytkowników.
    - Użyj bibliotek testowych BPM do utworzenia planu testów i zestawów testów w Microsoft Azure DevOps Services (Azure DevOps).

Użytkownicy mocy funkcjonalnej mogą tworzyć testy akceptacji i integracji użytkowników.

- Użyj narzędzia Regression suite automation tool (RSAT), aby uruchomić przypadki testowe żądanego zestawu testów.
- Zgłoś wyniki testu do Azure DevOps i użyj tej usługi do zbadania wyników.

## <a name="prerequisites"></a>Wymagania wstępne

Przed zakończeniem zadań w tym temacie, należy najpierw wypełnić następujące procedury:

- Wdrażaj topologię, która obsługuje automatyzację testów. Musisz mieć dostęp do instancji dla tej topologii w roli **Administrator systemu**. Ta topologia musi zawierać dane demonstracyjne, które będą używane w tym przykładzie. Więcej informacji znajdziesz w [Wdrażanie i użycie środowisk obsługujących ciągłą kompilację i automatyzację testów](../perf-test/continuous-build-test-automation.md).
- Aby automatycznie przeprowadzić testy akceptacji i integracji użytkowników, musisz zainstalować RSAT w topologii, z której korzystasz, i skonfigurować go w odpowiedni sposób. Aby uzyskać informacje o tym, jak zainstalować RSAT i skonfigurować go do pracy z aplikacjami Finance and Operations i Azure DevOps, zobacz [Regression Suite Automation Tool](https://www.microsoft.com/download/details.aspx?id=57357). Zwróć uwagę na warunki wstępne użycia narzędzia. Na poniższej ilustracji przedstawiono przykład ustawień RSAT. Niebieski prostokąt zawiera parametry określające dostęp do Azure DevOps. Zielony prostokąt zawiera parametry określające dostęp do instancji.

    ![Ustawienia RSAT.](media/GER-Configure.png "Zrzut ekranu ekranu okna dialogowego Ustawienia RSAT")

- Aby zorganizować przypadki testowe w pakietach, aby zagwarantować poprawną sekwencję wykonania, tak aby można było gromadzić dzienniki wykonań testowych w celu dalszego raportowania i badania, należy mieć dostęp do usługi Azure DevOps z wdrożonej topologii.
- Aby uzupełnić podany przykład, zalecamy pobranie [Korzystanie z ER do testów RSAT](https://go.microsoft.com/fwlink/?linkid=874684). Niniejsza instrukcja obejmuje następujące zadania przykładowe:

    | Zawartość                                           | Nazwa pliku i lokalizacja |
    |---------------------------------------------------|------------------------|
    | Przykładowy zapis zadania w celu przygotowania danych do testowania | Prepare\\Recording.xml |
    | Przykładowe nagranie zadania w celu przetworzenia płatności dostawcy   | Process\\Recording.xml |

## <a name="prepare-the-accounts-payable-module-to-process-vendor-payments"></a>Przygotuj moduł Konta do zapłaty, aby przetworzyć płatności dostawcy

1. Zaloguj się do swojego wystąpienia.
2. Pobierz następujące konfiguracje ER z LCS. Instrukcje zobacz [ER Importuj konfigurację z Lifecycle Services](./tasks/er-import-configuration-lifecycle-services.md).

    - **Model płatności** konfiguracja modelu ER.
    - **Mapowanie 1611 modelu płatności** konfiguracja mapowania modelu ER.
    - **BACS (UK)** Konfiguracja formatu ER

    ![Konfiguracje raportowania elektronicznego.](media/GER-Configurations.png "Zrzut ekranu strony ustawień formatu raportowania elektronicznego")

3. Wybierz dane demonstarcyjne firmy **GBSI** , która ma ustawiony Wielką Brytanię jako kraj/region.
4. Konfiguruj parametry płatnych kont:

    1. Otwórz **Konta płatne \> Konfiguracja zapłat \> Metody zapłaty**.
    2. Wybierz **Elektroniczną** metodę płatności.
    3. Skonfiguruj wybraną metodę płatności, aby korzystała z formatu **BACS (UK)** ER pobranego wcześniej w celu przetworzenia płatności dostawcy:

        1. W karcie **Formaty plików** ustaw **Ogólny elektroniczny format eksportu** jako **Tak**.
        2. W polu **Eksportuj format konfiguracji** wybierz **BACS (UK)**.

    ![Strona Metody płatności.](media/GER-APParameters.png "Zrzut ekranu metod płatności strony")

    > [!NOTE]
    > Jeśli masz pochodną wersję tego formatu ER utworzoną w celu obsługi dostosowań, możesz wybrać tę konfigurację w metodzie płatności **Elektroniczna**.

5. Utwórz przykładową płatność dostawcy:

    1. Otwórz **Konta płatne \> Płatności \> Dziennik płatności**.
    2. Upewnij się, że nie opublikowałeś dziennika płatności.

        ![Strona Nazwa arkusza płatności.](media/GER-APJournal.png "Zrzut ekranu strony arkuszy płatności")

    3. Wybierz **Linie** i wpisz linię, która ma następujące informacje.

        | Pole               | Przykładową wartość   |
        |---------------------|-----------------|
        | Nazwa dostawcy         | GB\_SI\_000001  |
        | Strona debetowa               | 1,000.00        |
        | Waluta            | GBP             |
        | Typ konta przeciwstawnego | Bank            |
        | Konto przeciwstawne      | GBSI OPER       |
        | Metoda płatności   | Elektroniczne      |

    ![Strona Płatności dla dostawców.](media/GER-APJournalLines.png "Zrzut ekranu strony płatności dostawcy")

## <a name="prepare-the-er-framework-to-test-vendor-payment-processing"></a>Przygotuj strukturę ER do przetestowania przetwarzania płatności przez dostawców

### <a name="configure-er-parameters"></a>Konfigurowanie parametrów modułu ER

1. Otwórz **Administracja organizacji \> Elektroniczne raportowanie \> Parametry elektronicznego raportowania**.
2. Na karcie **Załączniki** w polu **Linia bazowa** wybierz **Plik** jako typ dokumentu używany przez strukturę zarządzania dokumentami (DM) do przechowywania dokumentów związanych z funkcją linii bazowej jako załączników DM.

    ![Strona parametrów raportowania elektronicznego.](media/GER-ERParameters.png "Zrzut ekranu strony parametrów raportowania elektronicznego")

### <a name="generate-baseline-copies-of-vendor-paymentrelated-documents"></a>Generuj kopie bazowe dokumentów związanych z płatnościami dostawcy

1. Otwórz **Konta płatne \> Płatności \> Dziennik płatności**.
2. Wybierz **Linie**.
3. Wybierz **Generuj płatności**.
4. Wybierz **Elektroniczną** metodę płatności.
5. Wybierz konto bankowe **GBSI OPER**.
6. Ustaw opcję **Wydrukuj raport kontrolny** jako **tak**.
7. Pobierz wygenerowane dane wyjściowe jako plik zip.
8. Otwórz pobrany plik.
9. Eksportuj następujące pliki z pobranego pliku:

    - **Plik** plik płatności w formie tekstowej
    - **ERVendOutPaymControlReport** plik raportu kontrolnego w formacie XLSX

    ![Strona Wyodrębnione pliki.](media/GER-APJournalProcessed.png "Zrzut ekranu eksportowanych plików w Windows explorer")

### <a name="turn-on-the-er-baseline-feature"></a>Włącz funkcję linii bazowej ER

1. Przejdź do opcji **Administrowanie organizacją \> Raporty elektroniczne \> Konfiguracje**.
2. W panelu Akcji w karcie **Konfiguracja** wybierz **Parametry użytkowanika**.
3. Ustaw opcję **Uruchom w trybie debugowania** jako **tak**.

Poprzez włączenie parametru **Uruchom w trybie debugowania** zmuszasz strukturę ER do wykonania następujących działań po wykonaniu dowolnego formatu ER, który generuje dokumenty wychodzące:

1. Określ, czy linia bazowa została skonfigurowana dla któregokolwiek ze składników wykonanego formatu ER.
2. Określ, czy każda skonfigurowana linia bazowa ma zastosowanie w bieżących warunkach (kod firmy zarejestrowanej firmy, nazwa pliku i rozszerzenie nazwy wygenerowanego pliku wyjściowego itd.).
3. Następujące czynności należy wykonać dla każdej linii bazowej:

    1. Porównaj dane wyjściowe generowane podczas wykonywania formatu ER z odpowiednią linią bazową.
    2. Zapisz wyniki porównania w dzienniku debugowania konfiguracji ER.

### <a name="configure-er-baselines-for-vendor-payment-processing"></a>Skonfiguruj linie bazowe ER do przetwarzania płatności dostawcy

1. Przejdź do opcji **Administrowanie organizacją \> Raporty elektroniczne \> Konfiguracje**.
2. Wybierz **Linie bazowe**.
3. Wybierz pozycję **Nowy**.
4. W polu **Odniesienia** wybierz format **BACS (UK)**.
5. Wybierz **Załączniki**.
6. Dodaj nową linię bazową dla pliku płatności dostawcy:

    1. Wybierz pozycję **Nowy**.
    2. W polu **Typ** zaznacz **Plik** typ dokumentu DM skonfigurowany w parametrach ER w celu przechowywania artefaktów linii bazowej.
    3. Przeglądaj, aby wybrać lokalnie zapisany **Plik** w formacie tekstowym.
    4. W polu **Opis** wpisz **Płatność plik TXT**.

7. Dodaj nową linię bazową dla pliku raportu kontroli dostawcy:

    1. Wybierz pozycję **Nowy**.
    2. W polu **Typ** zaznacz **Plik** typ dokumentu DM skonfigurowany w parametrach ER w celu przechowywania artefaktów linii bazowej.
    3. Przeglądaj, aby wybrać lokalnie zapisany **ERVendOutPaymControlReport** w formacie XLSX.
    4. W polu **Opis** wpisz **Płatność XLSX raport kontrolny**.

    ![Linie bazowe dla pliku płatności dostawcy i raportu kontrolnego.](media/GER-BaselineAttachments.png "Zrzut ekranu strony konfiguracje z wybraną pozycją raport kontroli płatności XLSX")

8. Zamknij stronę.
9. Na skróconej karcie **Linie bazowe** wybierz **Nowy**, żeby skonfigurować linię bazową dla pliku płatności:

    1. Nazwij linię **Ustawienie linii bazowej dla pliku płatności**.
    2. W polu **Nazwa komponentu pliku** wybierz **plik**, aby zastosować tę linię bazową do wyjścia formatu ER, które generuje plik płatności w formacie tekstowym BACS (UK).
    3. W polu **Firmy** wybierz **GBSI**, aby zastosować tę linię bazową, gdy format **BACS (UK)** ER działa w firmie GBSI.
    4. W polu **Maska nazwy pliku** wpisz **\*.TXT** , aby zastosować tę linię bazową tylko do wyjść składowych formatu **pliku**, które mają rozszerzenie nazwy pliku **.txt**.
    5. W polu **Linia bazowa** wybierz **Plik Płatności TXT** tak, że ta linia bazowa jest używana do porównania z wygenerowanym wynikiem.

10. Wybierz **Nowy**, żeby skonfigurować nową linię bazową dla pliku raportu kontroli:

    1. Nazwij linię **Ustawienie linii bazowej dla pliku raportu kontroli**.
    2. W polu **Nazwa komponentu pliku** wybierz **ERVendOutPaymControlReport**, aby zastosować tę linię bazową do wyjścia formatu ER, które generuje plik raportu kontroli.
    3. W polu **Firmy** wybierz **GBSI**, aby zastosować tę linię bazową, gdy format **BACS (UK)** ER działa w firmie GBSI.
    4. W polu **Maska nazwy pliku** wpisz **\*.XLSX** , aby zastosować tę linię bazową tylko do wyjść składowych formatu **ERVendOutPaymControlReport**, które mają rozszerzenie nazwy pliku **.xslx**.
    5. W polu **Linia bazowa** wybierz **Plik raportu kontroli XLSX** tak, że ta linia bazowa jest używana do porównania z wygenerowanym wynikiem.

    ![Skrócona karta Plany bazowe na stronie konfiguracje.](media/GER-BaselineRules.png "Zrzut ekranu skróconej karty Plany bazowe na stronie konfiguracji")

## <a name="record-tests-to-validate-vendor-payment-processing"></a>Przykładowe zadania zadania w celu przetworzenia płatności dostawcy

Jako użytkownik możesz nagrywać własne kroki, aby przetestować przetwarzanie płatności przez dostawców. Zalecamy, abyś oglądał (i edytował zgodnie z wymaganiami) nagranie zadania **Prepare\\Recording.xml**, które pobrałeś wcześniej. To nagranie służy do ustawienia wszystkich danych testowych w prawidłowym stanie. Ten krok jest wymagany, ponieważ testowanie można wykonać wiele razy, a każdy test musi wykorzystywać dane, które są w tym samym stanie.

### <a name="reset-user-settings"></a>Resetowanie ustawień

1. Otwórz domyślny pulpit nawigacyjny.
2. Wybierz przycisk **Ustawienia** (szare koło zębate).
3. Wybierz **Opcje użytkownika**.
4. Wybierz **Użycie danych**.
5. Wybierz **Resetuj**.
6. Zaznacz **Tak**, aby potwierdzić, że chcesz zresetować dane użytkowania.
7. Zamknij stronę.

### <a name="record-the-steps-to-prepare-data-for-testing"></a>Zapisz kroki, aby przygotować dane do testowania

1. Wybierz przycisk **Ustawienia** (szare koło zębate).
2. Wybierz **Rejestrator zadań**.
3. Wybierz **nagranie playback**.
4. Wybierz **Otwórz z tego PC**.
5. Wybierz **Przeglądaj** i zaznacz lokalnie zapisany plik **Prepare\\Recording.xml**.
6. Wybierz **Start**.
7. Wybieraj ciągle **Odtwórz następny oczekujący krok**, aż wszystkie kroki w nagraniu zostaną odtworzone.

To nagranie zadania obejmuje następujące czynności:

1. Ustaw status przetworzonej linii płatności na **Żadne**.

    ![Kroki od 3 do 4 dotyczące rejestrowania zadań.](media/GER-Recording1Review1.png "Zrzut ekranu kroków od 3 do 4 dla rejestrowania zadań")

2. Ustaw opcję **Uruchom w trybie debugowania** w parametrach użytkownika ER.

    ![Kroki od 9 do 10 dotyczące rejestrowania zadań.](media/GER-Recording1Review2.png "Zrzut ekranu kroków od 9 do 10 dla rejestrowania zadań")

3. Wyczyść dziennik debugowania ER zawierający wyniki porównania wygenerowanych plików do linii bazowych.

    ![Kroki od 13 do 15 dotyczące rejestrowania zadań.](media/GER-Recording1Review3.png "Zrzut ekranu kroków od 13 do 15 dla rejestrowania zadań")

### <a name="record-the-steps-to-test-vendor-payment-processing"></a>Nagraj zadania testu przetworzenia płatności dostawcy

Zalecamy, abyś oglądał (i edytował zgodnie z wymaganiami) nagranie zadania **Process\\Recording.xml**, które pobrałeś wcześniej. To nagranie służy do przetwarzania płatności dostawcy i sprawdzania poprawności wyników porównania wygenerowanych dokumentów z odpowiednimi liniami bazowymi.

1. Wybierz przycisk **Ustawienia** (szare koło zębate).
2. Wybierz **Rejestrator zadań**.
3. Wybierz **nagranie playback**.
4. Wybierz **Otwórz z tego PC**.
5. Wybierz **Przeglądaj** i zaznacz lokalnie zapisany plik **Process\\Recording.xml**.
6. Wybierz **Start**.
7. Wybieraj ciągle **Odtwórz następny oczekujący krok**, aż wszystkie kroki w nagraniu zostaną odtworzone.

To nagranie zadania obejmuje następujące czynności:

1. Zacznij przetwarzanie płatności dostawcy.
2. Wybierz poprawne parametry środowiska wykonawczego i włącz generowanie raportu kontrolnego.

    ![Kroki od 3 do 8 dotyczące rejestrowania zadań.](media/GER-Recording2Review1.png "Zrzut ekranu kroków od 3 do 8 dla rejestrowania zadań")

3. Włącz i wyczyść dziennik debugowania ER zawierający wyniki porównania wygenerowanych plików do odpowiadających linii bazowych.

    Zapisz wyniki porównania w dzienniku debugowania konfiguracji ER w polu **Wygenerowany tekst**. Pola **Nazwa komponentu pliku** oraz **Ścieżka formatowa wywołująca wpis w logu**, odnoszą się do komponentu pliku, dla którego wygenerowany wynik został porównany z linią bazową.

    ![Wpisy na stronie Dzienniki przebiegu raportowania elektronicznego.](media/GER-ERDebugLog.png "Zrzut ekranu strony wpisów dzienników przebiegu raportowania elektronicznego")

4. Porównanie bieżącego wyniku z linią bazową jest rejestrowane za pomocą opcji **Potwierdź** opcji Rejestratora zadań i wybranie  **Obecna wartość**.

    ![Używanie opcji Walidacja w celu porównania z bieżącą wartością.](media/GER-TRRecordValidation.png "Zrzut ekranu używania opcji Walidacja w celu porównania z bieżącą wartością")

    Poniższa ilustracja pokazuje, jak wyglądają zarejestrowane kroki sprawdzania poprawności w zapisie zadania.

    ![Kroki od 13 i 15 dotyczące rejestrowania zadań.](media/GER-Recording2Review2.png "Zrzut ekranu kroków od 13 i 15 dla rejestrowania zadań")

## <a name="add-the-recorded-tests-to-azure-devops"></a>Dodaj nagrane testy do Azure DevOps

1. Otwórz środowisko Azure DevOps.
2. Wybierz projekt, który zdefiniowałeś w parametrach RSAT, gdy [konfigurowałeś narzędziel](#prerequisites).
3. Wybierz plan testu, który zdefiniowałeś w parametrach RSAT, gdy [konfigurowałeś narzędziel](#prerequisites).
4. Utwórz nowy przypadek testowy dla wybranego planu testów:

    1. Nazwij przypadek testowy **Przygotuj dane do przetestowania przetwarzania płatności elektronicznej dostawcy**.
    2. Dodaj plik **Nagranie.xml** z folderu **Przygotowanie**, który pobrałeś wcześniej.

5. Utwórz nowy przypadek testowy dla wybranego planu testów:

    1. Nazwij przypadek testowy **Przetestuj przetwarzanie płatności dostawcy za pomocą formatu ER BACS (Wielka Brytania)**.
    2. Dodaj plik **Nagranie.xml** z folderu **Proces**, który pobrałeś wcześniej.

    ![Nowe przypadki testowe dla wybranego planu testów.](media/GER-RSAT-DevOps-Tests-Passed.png "Zrzut ekranu nowych przypadków testowych dla wybranego planu testów")

> [!NOTE]
> Zwróć uwagę na prawidłową kolejność wykonywania dodawanych testów.

## <a name="prepare-rsat-to-run-the-recorded-tests"></a>Przygotuj RSAT do uruchomienia nagranych testów

### <a name="load-the-tests-from-azure-devops-to-rsat"></a>Wczytaj testy z Azure DevOps do RSAT

1. Otwórz lokalną aplikację RSAT w bieżącej topologii.
2. Zaznacz **Wgraj**, żeby załadować testy, które obecnie znajdują się w Azure DevOps na RSAT.

    ![Testy załadowane do pakietu RSAT.](media/GER-RSAT-RSAT-Tests-Loaded.png "Zrzut ekranu testów załadowanych do pakietu RSAT")

### <a name="create-automation-and-parameters-files"></a>Utwórz pliki automatyzacji i parametrów

1. W RSAT wybierz pliki, które wgrałeś z Azure DevOps.
2. Wybierz **Nowy**, żeby stworzyć filty automatyzacji i parametrów.

    ![Pliki automatyzacji i parametrów RSAT utworzone w RSAT.](media/GER-RSAT-RSAT-Tests-Initiated.png "Zrzut ekranu plików automatyzacji i parametrów RSAT utworzone w RSAT")

### <a name="modify-the-parameters-files"></a>Zmodyfikuj pliki parametrów

1. W RSAT wybierz przypadek testowy **Przygotuj dane do przetestowania przetwarzania płatności elektronicznej dostawcy**.
2. Wybierz opcję **Edycja**.
3. W otwartym pliku ćwiczeń Microsoft Excel , w karcie **Ogólne** zmień kod firmy na **GBSI**, ponieważ ta firma będzie używana do wykonywania testów.
4. W RSAT wybierz przypadek testowy **Przetestuj przetwarzanie płatności dostawcy za pomocą formatu ER BACS (Wielka Brytania)**.
5. Wybierz opcję **Edycja**.
6. W otwartym pliku ćwiczeń Excel, w karcie **Ogólne** zmień kod firmy na **GBSI**.
7. W ćwiczeniach **ERFormatMappingRunLogTable** zauważ, że komórki A: 3 i C: 3 zawierają tekst pól w tabeli dziennika debugowania ER, które są używane do sprawdzania poprawności wyników porównania danych wyjściowych z linią bazową. Teksty te zostaną wykorzystane do oceny rekordów dziennika debugowania ER, które są tworzone podczas wykonywania testu.

    ![Arkusz ERFormatMappingRunLogTable.](media/GER-RSAT-RSAT-ExcelParameters.png "Zrzut ekranu arkusza ERFormatMappingRunLogTable")

## <a name="run-the-tests-and-analyze-the-results"></a>Uruchom testy i przeanalizuj wyniki

### <a name="run-the-tests-in-rsat"></a>Uruchom testy w RSAT

1. W RSAT, wybierz wgrane testy.
2. Wybierz opcję **Uruchom**.

Zauważ, że przypadki testowe są automatycznie uruchamiane w obszarze aplikacji za pomocą przeglądarki internetowej.

### <a name="analyze-the-results-of-test-execution"></a>Przeanalizuj wyniki wykonanych testów

Wyniki testów są przechowywane w RSAT. Zauważ, że oba testy zostały zaliczone.

![Testy przekazane w narzędziu RSAT.](media/GER-RSAT-RSAT-Tests-Passed.png "Zrzut ekranu testów przekazanych w narzędziu RSAT")

Zwróć uwagę, że wyniki wykonania testu są również wysyłane do Azure DevOps, dzięki czemu możesz przeprowadzić dalszą analizę.

![Wyniki wykonania testu w Azure DevOps.](media/GER-RSAT-DevOps-Tests-Added.png "Zrzut ekranu wyników wykonywania testu w Azure DevOps")

### <a name="simulate-a-situation-where-tests-fail"></a>Symuluj sytuację, w której testy nie zostaną zaliczone

Ten zestaw testów musi zakończyć się niepowodzeniem, jeśli co najmniej jedno z wygenerowanych wyników nie odpowiada odpowiedniej linii bazowej. Aby osiągnąć tę sytuację, możesz użyć pochodnej wersji formatu **BACS (UK)**, która wygeneruje plik płatności, który ma inną zawartość niż odpowiadająca mu linia bazowa. Aby zasymulować tę sytuację, możesz użyć tego samego formatu **BACS (UK)**, ale zmień kwotę płatności na przetworzonej linii płatności.

1. Otwórz aplikację i przejdź do **Rozrachunki z dostawcami \> Płatności \> Arkusz płatności**.
2. Wybierz **Linie**.
3. Ustaw status przetworzonej linii płatności **Status płatności \> Źadne**.
4. W polu **Debet** zmień wartość z **1,000.00** na **2,000.00**.
5. Wybierz **Zapisz**, żeby zapisać zmiany.

### <a name="run-the-tests-in-rsat"></a>Uruchom testy w RSAT

1. W RSAT, wybierz wgrane testy.
2. Wybierz opcję **Uruchom**.

Zauważ, że przypadki testowe są automatycznie uruchamiane w obszarze aplikacji za pomocą przeglądarki internetowej.

### <a name="analyze-the-results-of-test-execution"></a>Przeanalizuj wyniki wykonanych testów

Wyniki testów są przechowywane w RSAT. Zauważ, że drugi test zakończył się niepowodzeniem podczas drugiego wykonania.

![Wyniki testu zakończonego niepowodzeniem w narzędziu RSAT.](media/GER-RSAT-RSAT-Tests-Failed.png "Zrzut ekranu wyników testu zakończonego niepowodzeniem w narzędziu RSAT")

Zwróć uwagę, że wyniki wykonania testu są również wysyłane do Azure DevOps, dzięki czemu możesz przeprowadzić dalszą analizę.

![Wyniki testu zakończonego niepowodzeniem w Azure DevOps.](media/GER-RSAT-DevOps-Tests-Failed.png "Zrzut ekranu wyników testu zakończonego niepowodzeniem w narzędziu Azure DevOps")

Możesz zobaczyć status każdego testu. Możesz także uzyskać dostęp do dziennika wykonania, aby przeanalizować przyczyny niepowodzenia. Na poniższej ilustracji dziennik wykonania pokazuje, że błąd wystąpił z powodu różnicy treści między wygenerowanym plikiem płatności a jego linią bazową.

![Dziennik wykonywania analizy niepowodzenia w usłudze Azure DevOps.](media/GER-RSAT-DevOps-Tests-Failed-Log.png "Zrzut ekranu dziennika wykonywania analizy niepowodzenia w Azure DevOps")

Dlatego, jak widzieliście, funkcjonowanie dowolnego formatu ER może być oceniane automatycznie za pomocą RSAT jako platformy testowej i przy użyciu przypadków testowych opartych na rejestratorze zadań, które wykorzystują funkcję linii bazowej ER.

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Zasoby rejestratora zadań](../user-interface/task-recorder.md)
- [Narzędzie Regression Suite Automation Tool](https://www.microsoft.com/download/details.aspx?id=57357)
- [Tworzenie i automatyzowanie testów akceptacji użytkownika](../lifecycle-services/using-task-guides-and-bpm-to-create-user-acceptance-tests.md)
- [Wdrażanie i użycie środowisk obsługujących ciągłą kompilację i automatyzację testów](../perf-test/continuous-build-test-automation.md)
- [Śledzenie wyników wygenerowanych raportów i porównywanie ich z wartościami bazowymi](er-trace-reports-compare-baseline.md)
- [ER Uaktualnianie formatu poprzez przyjęcie jego nowej wersji bazowej](tasks/er-upgrade-format.md)
- [ER Importowanie konfiguracji z usługi Lifecycle Services](tasks/er-import-configuration-lifecycle-services.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]