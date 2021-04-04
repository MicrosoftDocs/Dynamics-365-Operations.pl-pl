---
title: Skonfiguruj mapowania modelu ER zależne od kontekstu kraju
description: W tym temacie wyjaśniono, jak można skonfigurować mapowania modeli ER, aby zależały one od kontekstu kraju/regionu firmy kontrolującej ich użycie.
author: NickSelin
manager: AnnBe
ms.date: 11/11/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-01-01
ms.dyn365.ops.version: Release 8.1.2
ms.openlocfilehash: 48d2e3c81d038cc55f6f100f3081561506946199
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2021
ms.locfileid: "5562293"
---
# <a name="configure-country-context-dependent-er-model-mappings"></a>Skonfiguruj mapowania modelu ER zależne od kontekstu kraju

[!include[banner](../includes/banner.md)]

Mapowania modeli raportowania elektronicznego (ER) można skonfigurować w taki sposób, aby były implementowane w ogólnym modelu danych ER, ale są właściwe dla Dynamics 365 Finance. W tym temacie opisano sposób projektowania wielu mapowań modelu ER dla modelu danych ER w celu kontrolowania sposobu ich używania przez odpowiednie formaty ER, które są uruchamiane z firm mających inne konteksty krajów/regionów.

## <a name="prerequisites"></a>Wymagania wstępne

Aby wykonać przykłady opisane w tym temacie, musisz mieć następujące uprawnienia dostępu:

- Dostęp do Finance w jednej z następujących ról:
    - Deweloper raportowania elektronicznego
    - Konsultant funkcjonalny raportowania elektronicznego
    - Administrator systemu

- Dostęp do wystąpienia Regulatory Configuration Service (RCS), które zostało zainicjowane dla tej samej dzierżawy co aplikacja Finance, dla jednej z następujących ról:
    - Deweloper raportowania elektronicznego
    - Konsultant funkcjonalny raportowania elektronicznego
    - Administrator systemu

Niektóre kroki przedstawione w tym temacie wymagają wykonania formatu ER. W niektórych przypadkach do wykonania formatu ER jest zmieniany jest kontekst kraju/regionu firmy, do której użytkownik jest aktualnie zalogowany. Można uruchomić format ER w bieżącym wystąpieniu RCS, jeśli w oprogramowaniu RCS jest dostępna firma, która ma wymagany kontekst kraju/regionu W przeciwnym razie należy przekazać ukończoną wersję konfiguracji mapowania modeli ER i formatu ER, który używa modelu danych ER do wystąpienia Finance, a następnie uruchomić format ER w tym wystąpieniu Finance. Aby uzyskać informacje dotyczące importowania konfiguracji, która znajduje się w oprogramowaniu RCS, należy zapoznać się z tematem [Importowanie konfiguracji z RCS](rcs-download-configurations.md).

## <a name="single-model-mapping-case"></a>Przypadek mapowania jednego modelu

Aby zaprojektować wymagane składniki ER, należy wykonać kroki opisane w [Dodatku 1](#appendix1) do tego tematu Teraz istnieje konfiguracja mapowania modelu **Mapowania (ogólne)**, która zawiera mapowanie modelu dla definicji **Punktu wejścia 1**.

![Strona konfiguracji raportowania elektronicznego](./media/RCS-Context-specific-mapping-Tree.PNG)

### <a name="run-the-configured-format"></a>Uruchom skonfigurowany format

1.  Na **stronie konfiguracje** w skróconej karcie **Wersje** wybierz opcję **Uruchom**.
2.  Kliknij przycisk **OK**.

Należy zauważyć, że przeglądarka sieci Web proponuje pobranie pliku tekstowego wygenerowanego przez uruchomiony format ER. Ponieważ ten format został skonfigurowany w taki sposób , aby używał definicji **punktu wejścia 1** i tylko mapowanie jednego modelu jest obecnie dostępne dla modelu podstawowego, który zawiera mapowanie dla tej definicji, wykonany format ER użył **Mapowanie (ogólne)** z modelem konfiguracji **Mapowanie (ogólne)** jako źródła danych. W związku z tym pobrany plik zawiera tekst **Funkcji ogólnej 1**.

## <a name="multiple-shared-model-mappings-case"></a>Przypadek mapowań wielu wspólnych modeli

Aby zaprojektować wymagane składniki ER, należy wykonać kroki opisane w [Dodatku 2](#appendix2) do tego tematu Teraz istnieją konfiguracje mapowania modelu **Mapowanie (ogólne)** i **Mapowanie (ogólnie) niestandardowe**, które zawierają mapowanie modelu dla definicji **Punktu wejścia 1**.

![Strona konfiguracji raportowania elektronicznego](./media/RCS-Context-specific-mapping-TreeCustom.PNG)

### <a name="run-the-configured-format"></a>Uruchom skonfigurowany format

1.  Na stronie **Konfiguracje** w drzewie konfiguracji wybierz pozycję **Format do nauki mapowania**.
2.  Na skróconej karcie **Wersje** wybierz **Uruchom**.
3.  Kliknij przycisk **OK**.

Zauważ, że wykonanie wybranego formatu ER nie powiedzie się. Komunikat o błędzie informuje o tym, że dla modelu istnieje więcej niż jedno mapowanie modelu dla modelu **Model nauki mapowania** i definicja **Punktu wejścia 1** w **Mapowanie (ogólne)** i **Mapowanie (ogólnie) niestandardowe**. Ponadto w komunikacie zaleca się wybranie jednej z tych konfiguracji jako konfiguracji domyślnej.

![Strona konfiguracji raportowania elektronicznego](./media/RCS-Context-specific-mapping-FormatRunCustomFailed.PNG)

### <a name="define-a-default-mapping-configuration"></a>Definiowanie domyślnej konfiguracji mapowania

Wykonaj poniższe kroki, aby określić konfigurację **Mapowanie (ogólne) niestandardowe** jako konfigurację domyślną, tak aby można było używać jej mapowań jako źródeł danych dla formatu ER **Format do nauki mapowania**.

1.  Na stronie **Konfiguracje** w drzewie konfiguracji wybierz pozycję **Mapowanie (ogólnie) niestandardowe**.
2.  W razie potrzeby wybierz opcję **Edytuj**, aby bieżąca strona była gotowa do edycji.
3.  Ustaw opcję **domyślnego mapowania modelu** jako **Tak**.
4.  Wybierz opcję **Zapisz**.

![Strona konfiguracji raportowania elektronicznego](./media/RCS-Context-specific-mapping-MappingsCustomDefault.PNG)

### <a name="run-the-configured-format"></a>Uruchom skonfigurowany format

1.  Na stronie **Konfiguracje** w drzewie konfiguracji wybierz pozycję **Format do nauki mapowania**.
2.  Na skróconej karcie **Wersje** wybierz **Uruchom**.
3.  Kliknij przycisk **OK**.

Zauważ, że wykonanie wybranego formatu ER powiedzie się. Przeglądarka sieci Web proponuje pobranie pliku tekstowego wygenerowanego przez uruchomiony format ER. Ponieważ ten format został skonfigurowany w taki sposób , aby używał definicji **Punktu wejścia 1** i tylko konfiguracja mapowania modelu **Mapowanie (ogólnie) niestandardowe** została wybrana jako konfiguracja domyślna, wykonany format ER użył **Mapowanie (ogólne) kopia** z konfiguracją **Mapowanie (ogólne) niestandardowe** jako źródłem danych. W związku z tym pobrany plik zawiera tekst **Funkcji ogólnej 1 niestandardowej**.

> [!NOTE]
> W przypadku zmiany firmy, w której użytkownik jest aktualnie zalogowany i ponownego uruchomienia tego formatu ER, zostanie wykorzystana ta sama zawartość w wygenerowanym pliku, ponieważ domyślna konfiguracja mapowania modelu ER nie zawiera żadnych ograniczeń zależnych od firmy.

## <a name="multiple-mixed-model-mappings-case"></a>Przypadek mapowań wielu zmieszanych modeli

Aby zaprojektować wymagane składniki ER, należy wykonać kroki opisane w [Dodatku 3](#appendix3) do tego tematu Teraz istnieją konfiguracje mapowania modelu **Mapowanie (ogólne)** i **Mapowanie (ogólnie) niestandardowe** i **Mapowanie (FR) modeli mapowania**, które zawierają mapowanie modelu dla definicji **Punktu wejścia 1**.

Zauważ, że wersja 1 konfiguracji mapowania modelu **Mapowanie (FR)** jest skonfigurowana w taki sposób, że dotyczy ona tylko formatów ER **Model nauki mapowania** uruchamiane w Finance, które mają francuski kontekst kraju/regionu.

![Strona konfiguracji raportowania elektronicznego](./media/RCS-Context-specific-mapping-TreeFR.PNG)

### <a name="run-the-configured-format"></a>Uruchom skonfigurowany format

1.  Zmień firmę na **FRSI**.
2.  Na stronie **Konfiguracje** w drzewie konfiguracji wybierz pozycję **Format do nauki mapowania**.
3.  Na skróconej karcie **Wersje** wybierz **Uruchom**.
4.  Kliknij przycisk **OK**.

Zauważ, że wykonanie wybranego formatu ER powiedzie się. Przeglądarka sieci Web proponuje pobranie pliku tekstowego wygenerowanego przez uruchomiony format ER. Ponieważ ten format został skonfigurowany w taki sposób , aby używał definicji **Punktu wejścia 1** i tylko konfiguracja mapowania modelu **Mapowanie (ogólnie) niestandardowe** została wybrana jako konfiguracja domyślna, wykonany format ER użył **Mapowanie (ogólne) kopia** z konfiguracją **Mapowanie (ogólne) niestandardowe** jako źródłem danych. W związku z tym pobrany plik zawiera tekst **Funkcji ogólnej 1 niestandardowej**.

### <a name="define-the-france-specific-mapping-configuration-as-the-default-configuration"></a>Zdefiniuj konfigurację mapowania specyficznego dla Francji jako konfigurację domyślną

Wykonaj poniższe kroki, aby zdefiniować konfigurację **mapowania (FR)** modelu jako konfigurację domyślną. Należy zauważyć, że ponieważ mapowanie jest specyficzne dla Francji, będzie traktowane jako domyślne mapowanie między wszystkimi konfiguracjami mapowania modeli, dla których określono kod kraju **FR** w polu **standardzie ISO kody krajów/regionów**.

1.  Na stronie **Konfiguracje** w drzewie konfiguracji wybierz pozycję **Mapowanie (FR)**.
2.  W razie potrzeby wybierz opcję **Edytuj**, aby bieżąca strona była gotowa do edycji.
3.  Ustaw opcję **domyślnego mapowania modelu** jako **Tak**.
4.  Wybierz opcję **Zapisz**.

![Strona konfiguracji raportowania elektronicznego](./media/RCS-Context-specific-mapping-TreeFRDefault.PNG)

### <a name="run-the-configured-format"></a>Uruchom skonfigurowany format

1.  Na stronie **Konfiguracje** w drzewie konfiguracji wybierz pozycję **Format do nauki mapowania**.
2.  Na skróconej karcie **Wersje** wybierz **Uruchom**.
3.  Kliknij przycisk **OK**.

Zauważ, że wykonanie wybranego formatu ER powiedzie się. Przeglądarka sieci Web proponuje pobranie pliku tekstowego wygenerowanego przez uruchomiony format ER. Ponieważ ten format został skonfigurowany w taki sposób , aby używał definicji **Punktu wejścia 1** i tylko konfiguracja mapowania modelu **Mapowanie (FR)** została wybrana jako konfiguracja domyślna, wykonany format ER użył **Mapowanie (FR)** z konfiguracją **Mapowanie (FR)** jako źródłem danych. W związku z tym pobrany plik zawiera tekst **Funkcji FR 1**.

> [!NOTE]
> W przypadku zmiany firmy, w której obecnie zalogowany jest użytkownik i ponownego uruchomienia tego formatu, dane wyjściowe będą uzależnione od kontekstu kraju/regionu wybranej firmy.

## <a name="other-model-mapping-cases"></a>Inne przypadki mapowania modeli

Jak widać, wybór mapowania modelu na potrzeby wykonania formatu ER przebiega w następujący sposób:

- Określono definicję mapowania modelu używaną przez format ER (**punkt wejścia 1** w przykładach w tym temacie).
- Wszystkie konfiguracje mapowania zawierające mapowanie mające określoną definicję i spełniające wszystkie skonfigurowane ograniczenia kontekstu kraju/regionu mogą być używane do uruchamiania formatu ER (**Mapowanie (ogólne)**, **Mapowania (ogólne) niestandardowe** i **Mapowania (FR)** w przykładach w tym temacie).
- Każde domyślne mapowanie modelu o ograniczeniach kontekstu kraju/regionu ma najwyższy priorytet w wyborze (**mapowanie (FR)** w przykładach przedstawionych w tym temacie).
- Każde domyślne mapowanie modelu bez ograniczeń kontekstu kraju/regionu ma następny najwyższy priorytet w wyborze (**mapowanie (ogólne) niestandardowe** w przykładach przedstawionych w tym temacie).
- Każde mapowanie modelu o ograniczeniach kontekstu kraju/regionu ma wyższy priorytet dla wyboru niż mapowanie modelu, które nie ma ograniczeń kontekstu kraju/regionu.

Poniższa tabela zawiera informacje o wynikach wyboru mapowania modelu dla wszystkich możliwych przypadków dla ustawień mapowania modeli:

- Kolumna 1 wskazuje, czy jest przedstawione pierwsze mapowanie modelu, które nie ma ograniczeń kontekstu kraju/regionu (na przykład wspólne **Mapowanie (ogólnie)**), a jeśli obecna, to czy dla **domyślnego mapowania modelu** jest ustawiona wartość **tak**.
- Kolumna 2 wskazuje, czy jest przedstawione drugie mapowanie modelu, które nie ma ograniczeń kontekstu kraju/regionu (na przykład wspólne **Mapowanie (ogólnie) niestandardowe**), a jeśli obecna, to czy dla **domyślnego mapowania modelu** jest ustawiona wartość **tak**.
- Kolumna 3 wskazuje, czy jest przedstawione pierwsze mapowanie modelu, które ma ograniczenia kontekstu kraju/regionu A (na przykład określone dla Francji **Mapowanie (FR)**), a jeśli obecna, to czy dla **domyślnego mapowania modelu** jest ustawiona wartość **tak**.
- Kolumna 4 wskazuje, czy jest przedstawione drugie mapowanie modelu, które ma ograniczenia kontekstu kraju/regionu A, a jeśli obecna, to czy dla **domyślnego mapowania modelu** jest ustawiona wartość **tak**.
- Kolumna 5 przedstawia wynik zaznaczenia mapowania modelu w celu wykonania formatu ER pod kontrolą firmy, która ma kontekst kraju/regionu.
- Kolumna 6 przedstawia wynik zaznaczenia mapowania modelu w celu wykonania formatu ER pod kontrolą firmy, która ma kontekst kraju/regionu B.

W tabeli znak plus (+) wskazuje obecność konfiguracji mapowania modelu w bieżącym wystąpieniu Microsoft Azure, która jest używana do uruchamiania formatu ER (Finance lub SWR)

| Skrzynka | Mapowanie modelu 1 bez kontekstu kraju/regionu (MM1) | Mapowanie modelu 2 bez kontekstu kraju/regionu (MM2) | Mapowanie modelu 1 bez kontekstu kraju/regionu A (MM1A) | Mapowanie modelu 2 bez kontekstu kraju/regionu A (MM2A) | Uruchom pod kontrolą firmy, która ma kontekst kraju/regionu A | Uruchom pod kontrolą firmy, która ma kontekst kraju/regionu B |
|---------|---------|---------|---------|---------|---------------------------|----------------------------|
|         |     1   |     2   |    3    |    4    |           5               |            6               |
|     1   |         |         |         |         | Błąd (Brak mapowania)   | Błąd (Brak mapowania)    |
|     2   |     +   |         |         |         | MM1                       | MM1                        |
|     3   |     +   |     +   |         |         | Błąd (wielokrotne mapowanie) | Błąd (wielokrotne mapowanie)  |
|     4   |     +   |         |    +    |         | MM1A                      | MM1                        |
|     5   |     +   |         |    +    |    +    | Błąd (wielokrotne mapowanie) | MM1                        |
|     6   |     +   | domyślnie |    +    |    +    | MM2                       | MM2                        |
|     7   |     +   |         | domyślnie |         | MM1A                      | MM1                        |
|     8   |     +   |         | domyślnie |    +    | MM1A                      | MM1                        |
|     9   |     +   |         | domyślnie | domyślnie | Błąd (wielokrotne mapowanie) | MM1                        |
|    10   | domyślnie |         |         |         | MM1                       | MM1                        |
|    11   | domyślnie |    +    |         |         | MM1                       | MM1                        |
|    12   | domyślnie |         |    +    |         | MM1                       | MM1                        |
|    13   | domyślnie | domyślnie |         |         | Błąd (wielokrotne mapowanie) | Błąd (wielokrotne mapowanie)  |
|    14   | domyślnie |         | domyślnie |         | MM1A                      | MM1                        |
|    15   | domyślnie |         | domyślnie | domyślnie | MM1A                      | MM2A                       |
|    16   |         |         |    +    |    +    | MM1A                      | MM2A                       |
|    17   |         |         | domyślnie | domyślnie | MM1A                      | MM2A                       |

## <a name="learn-what-mapping-was-used-in-the-execution-of-an-er-format"></a>Mapowanie użyte w wykonaniu formatu ER

### <a name="configure-er-user-parameters"></a>Konfigurowanie parametrów użytkownika modułu ER

1.  na stronie **konfiguracje** na panelu akcji na karcie **KONFIGURACJE** wybierz **Parametry użytkownika**.
2.  Ustaw opcję **Uruchom w trybie debugowania** jako **tak**.
4.  Kliknij przycisk **OK**.

### <a name="run-the-configured-format"></a>Uruchom skonfigurowany format

1.  Na stronie **Konfiguracje** w drzewie konfiguracji wybierz pozycję **Format do nauki mapowania**.
2.  Na skróconej karcie **Wersje** wybierz **Uruchom**.
3.  Kliknij przycisk **OK**.

### <a name="review-the-er-debug-log"></a>Przejrzyj dziennik debugowania ER

1.  W okienku nawigacji przejdź do **Moduły \> Administrowanie organizacją \> Obszary robocze \> Dzienniki debugowania konfiguracji**.
2.  Wybierz przycisk **Załaduj ponownie tę stronę**.

![Strona dzienniki wykonywania ER](./media/RCS-Context-specific-mapping-DebugLog.PNG)

Należy zauważyć, że nowy rekord został dodany do dziennika debugowania modułu operacji (ER) dla wykonywanego formatu ER. Ponieważ pole **poziomu** tego rekordu ma wartość **informacje**, rekord ma charakter informacyjny. Ponieważ pole składnik formatu jest ustawione na **konfigurację mapowania**, rekord informuje o mapowaniu modelu, które zostało użyte podczas wykonywania **formatu w celu uzyskania informacji** o formacie ER mapowania rekordów (wybranym w polu **Nazwa konfiguracji**). Zawartość **wygenerowanego pola tekstowego** informuje, że składnik **mapowania (FR)**, który znajduje się w konfiguracji **mapowania (FR)**, został użyty do uruchomienia tego raportu.

## <a name="appendix-1"></a><a name="appendix1"></a>Załącznik 1

### <a name="configure-a-sample-data-model"></a>Konfigurowanie przykładowego modelu danych

Zaloguj się do swojego wystąpienia RCS.

W tej procedurze utworzysz wymagane konfiguracje ER dla przykładowej firmy Litware, Inc. aby wykonać te kroki, najpierw w RCS trzeba wykonać kroki wymienione w procedurze [ER Tworzenie dostawcy konfiguracji i oznaczanie go jako aktywnego](tasks/er-configuration-provider-mark-it-active-2016-11.md).

#### <a name="create-an-er-data-model-configuration"></a>Tworzenie nowej konfiguracji modelu danych ER

1.  Na domyślnym pulpicie nawigacyjnym wybierz opcję **Raportowanie elektroniczne**.
2.  Wybierz **Raportowanie konfiguracji**.
3.  Na stronie **Konfiguracje** wybierz opcję **Stwórz konfigurację**.
4.  W oknie dialogowym rozwijanym w polu **nazwa** wprowadź **Model nauki mapowania**.
5.  Wybierz **Utwórz konfigurację**.
6.  Wybierz **składniki konfiguracji** skróconej karcie.

Zwróć uwagę, że wersja 1 tej konfiguracji ER jest gotowa do edycji. Ta wersja zawiera składnik modelu danych.

#### <a name="design-a-sample-data-model"></a>Zaprojektuj przykładowego modelu danych

1.  Na stronie **Konfiguracje** wybierz opcję **Projektant**.
2.  Wybierz pozycję **Nowy**.
3.  W oknie dialogowym rozwijanym w polu **nazwa** wprowadź **Punkt wejścia 1**.
4.  Wybierz opcję **Dodaj**.
5.  Wybierz pozycję **Nowy**.
6.  W oknie dialogowym rozwijanym w polu **nazwa** wprowadź **Opis funkcji**.
7.  Wybierz opcję **Dodaj**.
8.  Wybierz pozycję **Nowy**.
9.  W oknie dialogowym rozwijanym w polu **nazwa węzła** wybierz **Element główny modelu**.
10. W polu **Nazwa** wpisz **Punkt wejścia 2**.
11. Wybierz **punkt wejścia 2**.
12. Wybierz opcję **Dodaj**.
13. Wybierz pozycję **Nowy**.
14. W oknie dialogowym rozwijanym w polu **nazwa** wprowadź **Opis funkcji**.
15. Wybierz opcję **Dodaj**.

    ![Strona projektanta mapowania modelu danych ER](./media/RCS-Context-specific-mapping-Model.PNG)

16. Wybierz opcję **Zapisz**.
17. Zamknij stronę.

#### <a name="complete-the-modified-version-of-the-model-configuration"></a>Kończenie zmodyfikowanej wersji konfiguracji modelu ER

1.  Na **stronie konfiguracje** w skróconej karcie **Wersje** wybierz opcję **Zmień status**.

    > Umożliwia zmianę stanu konfiguracji modelu zaprojektowanego z **wersji roboczej** na **zakończoną**, tak aby można było jej użyć do zaprojektowania wymaganych mapowań i formatów modeli.

2.  Wybierz opcję **Zakończone**.
3.  Kliknij przycisk **OK**.

Należy zauważyć, że utworzona konfiguracja została zapisana jako ukończona wersja 1.

### <a name="configure-a-sample-model-mapping"></a>Konfigurowanie przykładowego mapowania

#### <a name="create-an-er-model-mapping-configuration"></a>Tworzenie konfiguracji mapowania modelu ER

1.  Na stronie **Konfiguracje** wybierz opcję **Stwórz konfigurację**.
2.  W oknie dialogowym listy rozwijanej w polu **Nowa** grupa pól wybierz opcję **Mapowanie modelu na podstawie modelu danych Model do nauki mapowań**.
3.  W polu **Nazwa** wpisz **Mapowanie (ogólnie)**.
4.  W polu **Definicja modelu danych** zaznacz wartość **Punkt wejścia 1**.
5.  Wybierz **Utwórz konfigurację**.

Zwróć uwagę, że wersja 1 tej konfiguracji ER jest gotowa do edycji. Ta wersja zawiera składnik modelu mapowania danych.

#### <a name="design-a-sample-model-mapping"></a>Zaprojektuj przykładowego mapowania

1.  Na stronie **Konfiguracje** wybierz opcję **Projektant**.

    Należy zauważyć, że mapowanie modelu typu kierunek **do modelu** zostało automatycznie dodane do tego składnika dla definicji **Punkt wejścia 1**.
    
2.  Wybierz **Projektant**, aby rozpocząć edytowanie dodanego mapowania modelu.
3.  W sekcji **Model danych** wybierz **Edytuj**.
4.  W polu **Formuła** wpisz tekst **Funkcja ogólna 1**.
5.  Wybierz opcję **Zapisz**.
6.  Zamknij stronę **Projektowanie formuły**.

    ![Strona projektanta mapowania modelu ER](./media/RCS-Context-specific-mapping-Mapping1.PNG)

7.  Wybierz opcję **Zapisz**.
8.  Zamknij stronę **Projektant mapowania modelu**.
9.  Wybierz pozycję **Nowy**.
10. W polu **Definicja** zaznacz wartość **Punkt wejścia 2**.
11. W polu **Nazwa** wpisz **Mapowanie (ogólnie) 2**.
12. Wybierz opcję **Konstruktor**.
13. W sekcji **Model danych** wybierz **Edytuj**.
14. W polu **Formuła** wpisz tekst **Funkcja ogólna 2**.
15. Wybierz opcję **Zapisz**.
16. Zamknij stronę **Projektowanie formuły**.

    ![Strona projektanta mapowania modelu ER](./media/RCS-Context-specific-mapping-Mapping2.PNG)

17. Wybierz opcję **Zapisz**.
18. Zamknij stronę **Projektant mapowania modelu**.

    ![Strona Projektowanie mapowań modeli ER](./media/RCS-Context-specific-mapping-Mappings.PNG)

19. Zamknij stronę **Mapowanie modelu**.

#### <a name="complete-the-modified-version-of-the-model-mapping-configuration"></a>Kończenie zmodyfikowanej wersji konfiguracji modelu ER mapowania

1.  Na **stronie konfiguracje** w skróconej karcie **Wersje** wybierz opcję **Zmień status**.

    > Umożliwia zmianę stanu konfiguracji modelu mapowania zaprojektowanego z **wersji roboczej** na **zakończoną**, tak aby można było jej użyć przez formaty ER.

2.  Wybierz opcję **Zakończone**.
3.  Kliknij przycisk **OK**.

Należy zauważyć, że utworzona konfiguracja została zapisana jako ukończona wersja 1.

### <a name="configure-a-sample-format"></a>Konfiguruj format przykładowy

#### <a name="create-an-er-format-configuration"></a>Tworzenie konfiguracji formatu ER

1.  Na stronie **Konfiguracje** w drzewie konfiguracji wybierz pozycję **Model do nauki mapowania**.
2.  Wybierz **Utwórz konfigurację**.
3.  W oknie dialogowym listy rozwijanej w polu **Nowa** grupa pól wybierz opcję **format oparty na modelu Model do nauki mapowania**.
4.  W polu **nazwa** wprowadź **format do nauki mapowania**.
5.  W polu **Definicja modelu danych** zaznacz wartość **Punkt wejścia 1**.
6.  Wybierz **Utwórz konfigurację**.

Zwróć uwagę, że wersja 1 tej konfiguracji ER jest gotowa do edycji. Ta wersja zawiera składnik formatu.

#### <a name="design-a-sample-format"></a>Projektowanie formatu przykładu

1.  Na stronie **Konfiguracje** wybierz opcję **Projektant**.
2.  Wybierz **Dodaj element główny**.
3.  W grupie **Tekst** wybierz **ciąg**.
4.  Kliknij przycisk **OK**.

#### <a name="bind-format-elements-to-a-data-source"></a>Powiązanie elementów formatu na źródła danych

1.  Na stronie **Projektant formatów** na karcie **mapowanie** rozwiń gałąź źródło danych modelu.
2.  Zaznacz pole **opis funkcji**.
3.  Wybierz **Powiąż**.

    ![Strona projektanta formatu ER](./media/RCS-Context-specific-mapping-Format.PNG)

4.  Wybierz opcję **Zapisz**.
5.  Zamknij stronę.

## <a name="appendix-2"></a><a name="appendix2"></a>Załącznik 2

### <a name="configure-a-sample-model-mapping-for-general-customization"></a>Konfigurowanie przykładowego mapowania modelu na potrzeby ogólnego dostosowania

Istnieje możliwość dostosowania mapowania modelu dostarczonego przez dostawcę konfiguracji (partner), a następnie użycia dostosowanej wersji jako źródła danych dla formatów ER W takim przypadku należy utworzyć niestandardową konfigurację mapowania modelu ENCJi, aby wprowadzić wymagane zmiany w istniejących mapowaniach modeli. W procedurach przedstawionych w tym dodatku jest używane mapowanie modelu **mapowania (ogólne)** na przykład.

#### <a name="create-an-er-model-mapping-configuration"></a>Tworzenie konfiguracji mapowania modelu ER

1.  Na stronie **Konfiguracje** w drzewie konfiguracji wybierz pozycję **Mapowanie (ogólnie)**.
2.  Wybierz **Utwórz konfigurację**.
3.  W oknie dialogowym rozwijanym w **nowej** grupie pól wybierz opcję **Pochodne od nazwy: mapowanie (ogólne), litware, Inc.**
4.  W polu **Nazwa** wpisz **Mapowanie (ogólnie) niestandardowe**.
5.  Wybierz **Utwórz konfigurację**.

Zwróć uwagę, że wersja 1 tej konfiguracji ER jest gotowa do edycji.

#### <a name="design-a-sample-model-mapping"></a>Zaprojektuj przykładowego mapowania

1.  Na stronie **Konfiguracje** wybierz opcję **Projektant**.

    > Należy zauważyć, że mapowania modeli konfiguracji podstawowej zostały automatycznie skopiowane do tej konfiguracji.

2.  Wybierz mapowanie **Mapowanie (ogólne) kopia**.
3.  Wybierz opcję **Konstruktor**.
4.  W sekcji **Model danych** wybierz **Edytuj**.
5.  W polu **Formuła** wpisz tekst **Funkcja ogólna 1 niestandardowe**.
6.  Wybierz opcję **Zapisz**.
7.  Zamknij stronę.

    ![Strona projektanta mapowania modelu ER](./media/RCS-Context-specific-mapping-Mapping1Custom.PNG)

8.  Wybierz opcję **Zapisz**.
9.  Zamknij stronę.
10. Wybierz mapowanie **Mapowanie (ogólne) 2 kopia**.
11. Wybierz opcję **Konstruktor**.
12. W sekcji **Model danych** wybierz **Edytuj**.
13. W polu **Formuła** wpisz tekst **Funkcja ogólna 2 niestandardowe**.
14. Wybierz opcję **Zapisz**.
15. Zamknij stronę.

    ![Strona projektanta mapowania modelu ER](./media/RCS-Context-specific-mapping-Mapping2Custom.PNG)

16. Wybierz opcję **Zapisz**.
17. Zamknij stronę.

    ![Strona Projektowanie mapowań modeli ER](./media/RCS-Context-specific-mapping-MappingsCustom.PNG)

18. Zamknij stronę.

#### <a name="complete-the-modified-version-of-the-model-mapping-configuration"></a>Kończenie zmodyfikowanej wersji konfiguracji modelu ER mapowania

1.  Na **stronie konfiguracje** w skróconej karcie **Wersje** wybierz opcję **Zmień status**.

    > Umożliwia zmianę stanu konfiguracji modelu mapowania zaprojektowanego z **wersji roboczej** na **zakończoną**, tak aby można było jej użyć przez formaty ER.

2.  Wybierz opcję **Zakończone**.
3.  Kliknij przycisk **OK**.

Należy zauważyć, że utworzona konfiguracja została zapisana jako ukończona wersja 1.

## <a name="appendix-3"></a><a name="appendix3"></a>Załącznik 3

### <a name="configure-a-sample-model-mapping-for-countryregion-specific-customization"></a>Konfigurowanie przykładowego mapowania modelu na potrzeby dostosowania według kraju/regionu

W przypadku niektórych formatów ER mogą być dostępne wymagania specyficzne dla kraju/regionu dotyczące przygotowania danych. W takim przypadku można zarządzać oddzielną konfiguracją mapowania modelu odwzorowania i wyodrębnić implementację wymagań specyficznych dla danego kraju/regionu z ogólnej implementacji. Procedury opisane w tym dodatku wykorzystują **format do nauczenia się na przykład mapowań ER** i zagranicznych dla języka francuskiego.

#### <a name="create-an-er-model-mapping-configuration"></a>Tworzenie konfiguracji mapowania modelu ER

Najpierw utwórz nową konfigurację mapowania modelu ER, aby zaimplementować wymagania specyficzne dla kraju/regionu. Jako podstawy należy skorzystać z niestandardowej konfiguracji mapowania modeli ER.

1.  Na stronie **Konfiguracje** w drzewie konfiguracji wybierz pozycję **Mapowanie (ogólnie) niestandardowe**.
2.  Wybierz **Utwórz konfigurację**.
3.  W oknie dialogowym rozwijanym w **nowej** grupie pól wybierz opcję **Pochodne od nazwy: mapowanie (ogólne) niestandardowe, Litware, Inc**.
4.  W polu **Nazwa** wpisz **Mapowanie (FR)**.
5.  Wybierz **Utwórz konfigurację**.

Zwróć uwagę, że wersja 1 tej konfiguracji ER jest gotowa do edycji.

#### <a name="design-a-sample-model-mapping"></a>Zaprojektuj przykładowego mapowania

1.  Na stronie **Konfiguracje** wybierz opcję **Projektant**.

    > Należy zauważyć, że mapowania modeli konfiguracji podstawowej zostały automatycznie skopiowane do tej konfiguracji.

2.  Wybierz mapowanie **Mapowanie (ogólne) kopia kopii**.
3.  Zmień nazwę **Mapowanie (FR)**
4.  Wybierz opcję **Konstruktor**.
5.  W sekcji **Model danych** wybierz **Edytuj**.
6.  W polu **Formuła** wpisz tekst **Funkcja FR 1**.
7.  Wybierz opcję **Zapisz**.
8.  Zamknij stronę.

    ![Strona projektanta mapowania modelu ER](./media/RCS-Context-specific-mapping-Mapping1FR.PNG)

9.  Wybierz opcję **Zapisz**.
10. Zamknij stronę.
11. Wybierz mapowanie **Mapowanie (ogólne) 2 kopia kopii**.
12. Zmień nazwę **Mapowanie (FR) 2**
13. Wybierz opcję **Konstruktor**.
14. W sekcji **Model danych** wybierz **Edytuj**.
15. W polu **Formuła** wpisz tekst **Funkcja FR 2**.
16. Wybierz opcję **Zapisz**.
17. Zamknij stronę.

    ![Strona projektanta mapowania modelu ER](./media/RCS-Context-specific-mapping-Mapping2FR.PNG)

18. Wybierz opcję **Zapisz**.
19. Zamknij stronę.

    ![Strona Projektowanie mapowań modeli ER](./media/RCS-Context-specific-mapping-MappingsFR.PNG)

20. Zamknij stronę.

#### <a name="specify-countryregion-context-restrictions-for-use"></a>Określ ograniczenia kontekstu kraju/regionu dla użycia

1.  Na stronie **Konfiguracje** na skróconej karcie **Kody ISO kraju/regionu** wybierz **Nowe**.
2.  W polu **ISO** wybierz wartość **FR**.
3.  Wybierz opcję **Zapisz**.

Zwróć uwagę, że musisz zalogować się do konkretnej firmy w Finance, aby można było uruchomić format ER. Z tego względu firma może być traktowana jako strona, która steruje wykonaniem formatu ER i wyborem poprawnego mapowania modelu ER dla podstawowego modelu danych ER. Dodając kod kraju **FR**, można określić, że to mapowanie modelu będzie dostępne do wybrania przez format ER podstawowego modelu danych tylko wtedy, gdy ten format jest uruchamiany pod kontrolą firmy, która ma francuski kontekst kraju/regionu.

Można dodać wiele kodów krajów/regionów dla jednej wersji konfiguracji mapowania modelu ER. W ten sposób mapowania modeli znajdujące się w konfiguracji mapowania modeli mogą być używane dla formatu ER, który jest uruchamiany w ramach kontroli firm mających inny kontekst kraju/regionu.

Należy zauważyć, że lista kodów krajów/regionów jest określona dla każdej wersji konfiguracji mapowania modelu ER i może się różnić od wersji do wersji.

#### <a name="complete-the-modified-version-of-the-model-mapping-configuration"></a>Kończenie zmodyfikowanej wersji konfiguracji modelu ER mapowania

1.  Na **stronie konfiguracje** w skróconej karcie **Wersje** wybierz opcję **Zmień status**.

    > Umożliwia zmianę stanu konfiguracji modelu mapowania zaprojektowanego z **wersji roboczej** na **zakończoną**, tak aby można było jej użyć przez formaty ER.

2.  Wybierz opcję **Zakończone**.
3.  Kliknij przycisk **OK**.

Należy zauważyć, że utworzona konfiguracja została zapisana jako ukończona wersja 1.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie raportowania elektronicznego (RE)](general-electronic-reporting.md)

[Zarządzanie mapowaniem modelu modułu Raportowanie elektroniczne w oddzielnych konfiguracjach modułu Raportowanie elektroniczne](./tasks/er-manage-model-mapping-configurations-july-2017.md)

[Stosowanie kontekstu kraju/regionu](../lcs-solutions/apply-country-context.md)

## <a name="frequently-asked-questions"></a>Często zadawane pytania

#### <a name="i-configured-two-shared-er-model-mapping-configurations-in-rcs-and-marked-one-of-them-as-the-default-model-mapping-configuration-i-successfully-ran-an-er-format-that-was-created-for-the-same-base-er-data-model-configuration-to-test-model-mappings-i-then-imported-the-whole-er-solution-er-data-model-two-er-model-mapping-configurations-and-er-format-configuration-into-finance-why-do-i-receive-an-error-message-when-i-try-to-run-the-same-er-format-in-finance"></a>Skonfigurowano dwie konfiguracje mapowania współużytkowanych modeli ER w oprogramowaniu RCS i oznaczono jedną z nich jako domyślną konfigurację mapowania modeli. Pomyślnie uruchomiono format modułu ER utworzony dla tej samej konfiguracji modelu danych bazowych ER, aby przetestować mapowania modeli. Następnie zaimportowano całe rozwiązanie ER (model danych ER), dwie konfiguracje mapowania modeli ER i konfigurację formatu ER do Finance. Dlaczego podczas próby uruchomienia tego samego formatu ER w Finance jest wyświetlany komunikat o błędzie?
Domyślne ustawienie mapowania modelu jest specyficzne dla środowiska. Jest on skonfigurowany w oprogramowaniu RCS, ale nie jest eksportowany do Finance. Aby pomyślnie uruchomić ten format ER, należy zaznaczyć jedną z konfiguracji mapowania modelu programu ER jako domyślną konfigurację mapowania modeli w Finance.

#### <a name="i-configured-one-model-mapping-as-a-shared-model-mapping-and-completed-the-draft-version-of-it-i-then-added-a-new-model-mapping-configuration-for-same-data-model-and-configured-it-as-french-specific-why-is-the-shared-model-mapping-selected-when-i-run-an-er-format-even-though-this-er-format-uses-the-correct-root-definition-and-execution-is-done-under-the-control-of-the-company-that-has-french-countryregion-context"></a>Skonfigurowano jedno mapowanie modelu jako mapowanie modelu współużytkowanego i zakończono jego wersję roboczą. Następnie dodano nową konfigurację mapowania modelu dla tego samego modelu danych i skonfigurowano ją jako specjalną w języku francuskim Dlaczego mapowanie współużytkowanych modeli jest wybierane podczas uruchamiania formatu ER, nawet jeśli ten format ER korzysta z poprawnej definicji głównej i wykonanie jest wykonywane pod kontrolą firmy, która ma francuski kontekst kraju/regionu?
Upewnij się, że konfiguracja mapowania modelu udostępnionego nie jest oznaczona jako domyślna konfiguracja mapowania modeli. W przeciwnym razie wybranie mapowania będzie miało wyższy priorytet. Należy również upewnić się, że konfiguracja mapowania modelu specyficznego dla języka francuskiego jest brana pod uwagę w przypadku wybrania mapowania w trakcie wykonywania operacji na formacie ER. Konfiguracja mapowania modelu ER jest dostępna do wybrania tylko wtedy, gdy spełniony jest co najmniej jeden z następujących warunków:
- Co najmniej jedna wersja konfiguracji mapowania modelu ER ma **stan zakończony** lub **udostępniony**. W tym przypadku wersja o najwyższym numerze wersji zostanie użyta w celu wykonania formatu ER.
- Opcja **Uruchom wersję roboczą** dla konfiguracji mapowania modelu ER jest włączona. W tym przypadku wersja o statusie **Wersja robocza** zostanie użyta w celu wykonania formatu ER.
> Opcja **Uruchom wersję roboczą** staje się dostępna na stronie **konfiguracje** dla każdej konfiguracji mapowania modelu ER, jeśli jest włączony parametr **Uruchom ustawienia** użytkownika ER.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]