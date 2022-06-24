---
title: Konfiguracja formatów raportowania elektronicznego do używania parametrów określonych dla firmy
description: W tym artykule wyjaśniono, w jaki sposób można skonfigurować format raportowania elektronicznego (ER) do używania z określonymi dla firmy parametrami.
author: NickSelin
ms.date: 04/02/2021
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
ms.openlocfilehash: eb44422c4cdcc87989cdfb28dcd7d5cfea9002eb
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8858836"
---
# <a name="configure-er-formats-to-use-parameters-that-are-specified-per-legal-entity"></a>Skonfiguruj formaty ER do używania parametrów określonych dla firmy

[!include[banner](../includes/banner.md)]

## <a name="overview"></a>Omówienie

W wielu formatach elektronicznego raportowania (ER), które należy zaprojektować, należy filtrować dane przy użyciu zbioru wartości, które są właściwe dla poszczególnych firm danego wystąpienia (np. zestawy kodów podatków do filtrowania transakcji podatkowych). Obecnie, jeśli filtrowanie tego typu jest skonfigurowane w formacie ER, wartości zależne od firmy (np. kody podatków) są używane w wyrażeniach formatu ER w celu określenia reguł filtrowania danych. Z tego względu format ER jest zgodny z daną firmą, a w celu wygenerowania wymaganych raportów należy utworzyć pochodne kopie oryginalnego formatu ER dla każdej firmy, w której ma być uruchamiany format ER. Każdy pochodny format ER musi być edytowany w celu przeniesienia do niego wartości właściwych dla firmy, który jest zmieniany w systemie, o ile oryginalna (podstawowa) wersja została zaktualizowana, wyeksportowana ze środowiska testowego i zaimportowana do środowiska produkcyjnego, jeśli musi zostać wdrożona do produkcji użycia itd. Dlatego obsługa tego typu skonfigurowanego rozwiązania ER jest skomplikowana i czasochłonna z kilku powodów:

-   Im więcej jest firm, tym więcej konfiguracji formatu ER trzeba będzie zachować.
-   Obsługa konfiguracji ER wymaga, aby użytkownicy biznesowi mieli wiedzę na temat ER.

Funkcja parametrów specyficznych dla aplikacji ER umożliwia użytkownikom zaawansowanym konfigurowanie filtrowania danych w formacie ER, tak aby były oparte na zbiorze reguł abstrakcyjnych. Ten zbiór reguł może być skonfigurowany do korzystania ze źródeł danych dostępnych w formacie ER. Użytkownicy biznesowi mogą następnie określać rzeczywiste reguły poza strukturą ER za pomocą interfejsu użytkownika (UI), który jest generowany automatycznie na podstawie ustawień odpowiedniego formatu ER i bieżących danych firmy, do których mają dostęp dane formatu ER źródłem. Zbiór reguł określonych dla formatu ER można wyeksportować z bieżącej firmy w wystąpieniu aplikacji Dynamics 365 Finance (Finance). Może on następnie zostać zaimportowany do innego podmiotu prawnego o tej samej instancji Finance lub innym wystąpieniu jako zbiór reguł dla tego samego formatu ER.

## <a name="prerequisites"></a>Wymagania wstępne

Aby uzupełnić przykłady w tym artykule, musisz mieć dostęp, dostęp do wystąpienia Regulatory Configuration Services (RCS), które zostało zainicjowane dla tej samej dzierżawy co Finance dla jednej z następujących ról:

- Deweloper raportowania elektronicznego
- Konsultant funkcjonalny raportowania elektronicznego
- Administrator systemu

Zaleca się wykonanie kroków opisanych w artykule [Obsługa sparametryzowanych wywołań źródeł danych narzędzia Raportowanie elektroniczne typu pola obliczeniowego](er-calculated-field-type.md). Jeśli wykonano już te kroki, można pominąć kroki opisane w sekcji **Importowanie konfiguracji zadania do RCS**.

## <a name="import-er-configurations-into-rcs"></a>Importowanie konfiguracji ER do RCS

Pobierz i lokalnie przechowaj następujące konfiguracje ER.

| **Opis zawartości**                        | **Nazwa pliku**                                        |
|------------------------------------------------|------------------------------------------------------|
| Plik przykładowa **konfiguracja modelu danych ER**    | [Model do nauczenia sparametryzowanych calls.version.1.xml.](https://download.microsoft.com/download/2/d/b/2db913a0-3622-494e-91a2-97fc494af9b9/Modeltolearnparameterizedcalls.version.1.xml)     |
| Plik przykładowa konfiguracja **metadanych ER**      | [Dane do nauczenia sparametryzowanych calls.version.1.xml.](https://download.microsoft.com/download/1/b/3/1b343968-5a47-4000-b5a8-6487698ef4c0/Metadatatolearnparameterizedcalls.version.1.xml)  |
| Plik przykładowa konfiguracja **mapowania modelu ER** | [Mapowanie do nauczenia sparametryzowanych calls.version.1.xml.](https://download.microsoft.com/download/8/6/6/866e0ab6-2e05-4d98-9d52-d2da2038f6e4/Mappingtolearnparameterizedcalls.version.1.1.xml) |
| Plik Przykładowa konfiguracja **formatu ER**             | [Format do nauczenia sparametryzowanych calls.version.1.xml.](https://download.microsoft.com/download/e/3/9/e392eadc-b9b4-4834-95c3-b8066dd00b9c/Formattolearnparameterizedcalls.version.1.1.xml)  |

Następnie zaloguj się do swojego wystąpienia RCS.

W tym przykładzie utworzysz konfigurację dla przykładowej Litware, Inc. Aby ukończyć tę procedurę, musisz wykonać czynności opisane w artykule w RCS [Tworzenie dostawcy konfiguracji i oznaczanie go jako aktywnego](tasks/er-configuration-provider-mark-it-active-2016-11.md).

1.  Na domyślnym pulpicie nawigacyjnym wybierz opcję **Raportowanie elektroniczne**.
2.  Wybierz **Raportowanie konfiguracji**.
3.  Zaimportuj pobrane wcześniej konfiguracje ER do RCS w następującej kolejności: model danych, metadane, mapowanie modelu, format. Dla każdej konfiguracji ER wykonaj następujące czynności:

    1.  Wybierz **Zamień**.
    2.  Wybierz **Załaduj z pliku XML**.
    3.  Kliknij przycisk **Przeglądaj**, aby wybrać plik wymaganej konfiguracji ER w formacie XML.
    4.  Kliknij przycisk **OK**.

## <a name="review-the-er-solution-that-is-provided"></a>Przejrzyj dostarczone rozwiązanie ER

1.  W drzewie konfiguracji rozwiń zawartość **Model, aby uzyskać informacje o elementach sparametryzowanych wywołań**.
2.  Wybierz opcję **Format do nauczenia sparametryzowanych wywołań**.
3.  Wybierz opcję **Konstruktor**.
4.  Wybierz **Rozwiń/zwiń**.

    **Format wywołania sparametryzowanych wywołań** formatu ER jest przeznaczony do generowania deklaracji podatkowej w formacie XML, który przedstawia kilka poziomów opodatkowania (zwykły, ograniczony i brak) Każdy poziom ma inną liczbę szczegółów.

    ![Wiele poziomów formatu ER, Format do nauki parametrów wywołań.](./media/RCS-AppSpecParms-ReviewFormat.PNG)

5.  Na karcie **mapowanie** rozwiń pozycje **model**, **dane** i **podsumowanie**.

    Źródło **Model.Data.Summary** podsumowanie zwraca listę transakcji podatkowych. Transakcje te są podsumowane według kodu podatkowego. Dla tego źródła danych pole obliczeniowe **Model.Data.Summary.Level** na poziomie zostało skonfigurowane w taki sposób, aby zwracała kod poziomu opodatkowania każdego rekordu zbiorczego. Obliczone pole **Model.Data.Summary.Level** zawiera źródło danych w czasie wykonywania obliczone pole zwraca kod poziomu opodatkowania (**Zwykłe**, **Obniżone**, **Brak** lub **Inne**) jako wartość tekstową. Pole **Model.Data.Summary.Level** służy do filtrowania rekordów **Model.Data.Summary** i wprowadź filtrowane dane w każdym elemencie XML, który reprezentuje poziom opodatkowania, przy użyciu pól **Model.Data2.Level1**, **Model.Data2.Level2** i **Model.Data2.Level3**.

    ![Źródło Model.Data.Summary podsumowanie pokazuje listę transakcji podatkowych.](./media/RCS-AppSpecParms-ReviewFormat-Data2Fld.PNG)

    Pole **Model.Data.Summary.Level** zostało skonfigurowane w taki sposób, aby zawierało wyrażenie ER. Kody podatków (**VAT19**, **InVAT19**, **VAT7**, **InVAT7**, **THIRD** i **InVAT0**) są mocno zakodowane w tej konfiguracji. W związku z tym ten format ER jest zależny od firmy, w której skonfigurowano kody podatków.

    ![Pole Model.Data.Summary.Level z kodami stałymi podatków.](./media/RCS-AppSpecParms-ReviewFormat-LevelFld.PNG)

    Aby obsługiwać różne zestawy kodów podatków dla poszczególnych firm, należy wykonać następujące kroki:

    - Utwórz pochodną wersję formatu ER dla każdej firmy.
    - Umożliwia zaktualizowanie kodów podatków w polu obliczeniowym **Model.Data.Summary.Level** na podstawie ustawienia firmy.

6.  Zamknij stronę **Projektowanie formuły**.

## <a name="create-a-derived-format"></a>Tworzenie pochodnego formatu

Następnie użytkownik korzysta z funkcji parametrów specyficznych dla aplikacji ER w celu obsługi różnych kodów podatków dla każdej firmy w jednym formacie ER.

1.  W drzewie konfiguracji rozwiń zawartość **Model, aby uzyskać informacje o elementach sparametryzowanych wywołań**.
2.  Wybierz opcję **Format do nauczenia sparametryzowanych wywołań**.
3.  Wybierz **Utwórz konfigurację**.
4.  Wybierz opcję **pochodną z Nazwy: Format, aby poznać wywołania sparametryzowane Microsoft**.
5.  W polu **nazwa** wprowadź **Format, aby uzyskać informacje o wyszukiwaniu danych LE**.
6.  Wybierz **Utwórz konfigurację**.

## <a name="configure-a-derived-format"></a>Konfiguruj format pochodny

### <a name="add-a-format-enumeration"></a>Dodaj wyliczenie formatów

Następnie zostanie dodane nowe Wyliczenie formatu ER. Wartości tego wyliczenia formatu będą prezentowane użytkownikom biznesowym, którzy będą określać zestawy podatków zależne od firm dla różnych poziomów opodatkowania, które są używane w formacie ER.

1.  Wybierz opcję **Konstruktor**.
2.  Wybierz **wyliczenia formatów**.
3.  Wybierz opcję **Dodaj**.
4.  W polu **Nazwa** wpisz **Lista poziomów opodatkowania**.
5.  Wybierz opcję **Zapisz**.
6.  Na karcie **Wartości wyliczenia formatu** wybierz opcję **Dodaj**.
7.  W polu **Nazwa** wpisz **zwykłe opodatkowanie**.
8.  Wybierz ponownie przycisk **Dodaj**.
9.  W polu **Nazwa** wpisz **obniżone opodatkowanie**.
10. Wybierz ponownie przycisk **Dodaj**.
11. W polu **Nazwa** wpisz **Brak opodatkowania**.
12. Wybierz ponownie przycisk **Dodaj**.
13. W polu **Nazwa** wprowadź nazwę **Inne**.

    ![Nowy rekord na stronie wyliczeń formatów.](./media/RCS-AppSpecParms-ConfigureFormat-Enum.PNG)

    Ponieważ użytkownicy biznesowi mogą stosować różne języki do określania zestawów kodów podatków zależnych od firm, zaleca się przetłumaczenie wartości tego wyliczenia na języki skonfigurowane jako preferowane języki dla tych użytkowników w Finance.

14. Wybierz rekord **Brak opodatkowania**.
15. Kliknij opcję w polu **etykieta**.
16. Wybierz **Tłumacz**.
17. W okienku **tłumaczenie tekstu** w polu **Identyfikator etykiety** wprowadź **LBL_LEVELENUM_NO**.
18. W polu **tekst w języku domyślnym** wprowadź wartość **Brak opodatkowania**.
19. W polu **Język** wybierz **DE**.
20. W polu **Przetłumaczony tekst** wprowadź tekst **keine Besteuerung**.
21. Wybierz **Tłumacz**.

    ![Wysuń tłumaczenie tekstu.](./media/RCS-AppSpecParms-ConfigureFormat-EnumTranslate.PNG)

22. Wybierz opcję **Zapisz**.
23. Zamknij stronę **wyliczenia formatów**.

### <a name="add-a-new-lookup-data-source"></a>Dodaj nowe źródło danych wyszukiwania

Następnie należy dodać nowe źródło danych w celu określenia sposobu, w jaki użytkownicy biznesowi będą określać reguły zależne od firmy w celu rozpoznania poprawnego poziomu opodatkowania dla każdego rekordu transakcji zbiorczej.

1.  Na karcie **mapowanie** wybierz opcję **Dodaj**.
2.  Wybierz **wyliczenia formatów\wyszukiwanie**.

    Użytkownik stwierdził, że każda reguła określona przez użytkowników biznesowych w celu rozpoznania poziomu opodatkowania zwróci wartość wyliczenia formatu ER. Należy zauważyć, że typ źródła danych **wyszukiwania** może być dostępny w **modelu danych** i blokach **Dynamics 365 for Operations** oprócz bloku **wyliczenia formatu**. W związku z tym wyliczenia modeli danych ER i wyliczenia aplikacji mogą służyć do określenia typu wartości zwracanych dla źródeł danych tego typu. Aby dowiedzieć się więcej o źródłach danych **Wyszukiwania**, zobacz temat [Konfiguracja źródeł danych wyszukiwania, aby używać funkcji parametrów specyficznych dla aplikacji ER](er-lookup-data-sources.md).
    
3.  W polu **Nazwa** wpisz **Reguła**.
4.  W polu **Wyliczenie formatów** wybierz **Lista poziomów opodatkowania**.

    Określono, że dla każdej reguły określonej w tym źródle danych użytkownik biznesowy musi wybrać jedną z wartości z **listy poziomów opodatkowania** do wyliczenia jako wartość zwróconą.
    
5.  Wybierz **Edytuj wyszukiwania**.
6.  Wybierz **Kolumny**.
7.  Rozwiń **Model**.
8.  Rozwiń pozycję **Dane**.
9.  Rozwiń pozycję **Podatek**.
10. Wybierz pozycję **Model.Data.Tax.Code**.
11. Wybierz przycisk **Dodaj** (Strzałka w prawo).

    ![Kolumny wysuwają się.](./media/RCS-AppSpecParms-ConfigureFormat-Lookup1.PNG)

    Właśnie określono, że dla każdej reguły określonej w tym źródle danych do rozpoznawania poziomu opodatkowania użytkownik biznesowy musi wybrać jeden z kodów podatkowych jako warunek. Lista kodów podatków, które może wybrać użytkownik biznesowy, zostanie zwrócona przez źródło danych **Model.Data.Tax**. Ponieważ to źródło danych zawiera pole **nazwa**, nazwa kodu podatku będzie wyświetlana dla każdej wartości kodu podatku w wyszukiwaniu prezentowanemu użytkownikowi biznesowemu.
    
12. Kliknij przycisk **OK**.

    ![Strona konstruktora wyszukiwania.](./media/RCS-AppSpecParms-ConfigureFormat-Lookup2.PNG)

    Użytkownicy biznesowi mogą dodawać wiele reguł w postaci rekordów tego źródła danych. Każdy rekord będzie numerowany według kodu wiersza. Reguły będą oceniane w kolejności rosnącego numeru wiersza.

    Ponieważ pole **kod podatku** zostało wybrane jako warunek dla reguł w tym źródle danych wyszukiwania, a **kod podatku** jest skonfigurowany jako pole typu **ciąg znaków**, każda reguła będzie oceniana w czasie wykonywania przez porównanie kodu podatku przekazanego do źródła danych z kodem podatku zdefiniowanym w tym rekordzie źródła danych.

    Gdy zostanie znaleziona reguła, która spełnia skonfigurowany warunek, to źródło danych zwraca wartość wyszukiwania reguły zdefiniowanej w polu **wynik wyszukiwania**. Jeśli nie zostanie znaleziona żadna reguła, zostanie zgłoszony wyjątek w celu powiadomienia użytkownika, że bieżące źródło danych nie może zwrócić poprawnej wartości.

13. Wybierz opcję **Zapisz**.
14. Zamknij stronę **Projektowanie wyszukiwania**.
15. Kliknij przycisk **OK**.

    Należy zauważyć, że dodano nowe źródło danych, które zwróci poziom opodatkowania jako wartość **listy poziomów opodatkowania** dla dowolnego kodu podatku przekazanego do źródła danych jako argumentu parametru **kodu** typu danych **ciągu**.
    
    ![Strona projektanta formatów z nowym źródłem danych.](./media/RCS-AppSpecParms-ConfigureFormat-SelectorFld.PNG)

    Ocena skonfigurowanych reguł zależy od typu danych pól, które zostały wybrane w celu zdefiniowania warunków tych reguł. Po wybraniu pola, które jest skonfigurowane jako pole typu danych **numerycznych** lub **dat**, kryteria różnią się od kryteriów opisanych wcześniej dla typu **ciąg**. W przypadku pól **numerycznych** i **dat** reguła musi być określona jako zakres wartości. Warunek reguły zostanie wówczas uznany za spełniony, gdy wartość przekazywana do źródła danych znajduje się w skonfigurowanym zakresie.
    
    Ilustracja poniżej zawiera przykład tego rodzaju ustawień. Oprócz pole **Model.Data.Tax.Code** w typie danych **Ciąg** w polu **Model.Tax.Summary.Base** w **właściwe** służy do określania warunków dla źródła danych wyszukiwania.
    
    ![Strona konstruktora wyszukiwania z dodatkowymi kolumnami.](./media/RCS-AppSpecParms-ConfigureFormat-SelectorFld2.PNG)

    Ponieważ pola **Model.Data.Tax.Code** i **Model.Tax.Summary.Base** są wybrane, każda reguła tego źródła danych zostanie skonfigurowana w następujący sposób:
    
    -   Na wyświetlonej liście należy wybrać wartość w polu **Lista poziomów opodatkowania** jako wartość zwróconą.
    -   Kod podatku musi zostać wprowadzony jako warunek tej reguły. Mają być tylko kody podatków podane przez **Model.Data.Tax** są odpowiednie.
    -   Minimalna i maksymalna wartość kwoty podstawy podatku musi zostać wprowadzona jako warunki tej reguły.

    Oto, jak Każda reguła tego źródła danych będzie oceniana w czasie wykonywania:
    -   Czy kod typu danych **Ciąg**, który został przekazany do tego źródła danych, jest równy kodowi podatku reguły?
    -   Czy wartość **rzeczywistego** typu danych przekazywana do tego źródła danych odpada między określonymi wartościami minimalnymi i maksymalnymi?

    Reguła będzie uważana za stosowaną, gdy spełnione są oba warunki.

### <a name="translate-the-label-of-the-lookup-data-source-that-was-added"></a>Przetłumacz etykietę dodanego źródła danych wyszukiwania

Ponieważ użytkownicy biznesowi mogą używać różnych języków do określania zestawów kodów podatkowych zależnych od podmiotów prawnych, zalecamy przetłumaczenie etykiety każdego dodanego źródła danych wyszukiwania, aby była ona wyświetlana w preferowanym języku każdego użytkownika na odpowiedniej stronie.

1.  Wybierz źródło danych **Model.Data.Selector**.
2.  Wybierz opcję **Edycja**.
3.  Kliknij opcję w polu **etykieta**.
4.  Wybierz **Tłumacz**.
5.  W okienku **tłumaczenie tekstu** w polu **Identyfikator etykiety** wprowadź **LBL_SELECTOR_DS**.
6.  W polu **tekst w języku domyślnym** wprowadź opcję **Wybierz kod podatku według kodu podatku**.
7.  W polu **Język** wybierz **DE**.
8.  W polu **przetłumaczony tekst** wprowadź **Steuerebene für Steuerkennzeichen auswählen**.
9.  Wybierz **Tłumacz**.
10. Kliknij przycisk **OK**.

    ![Właściwości źródła danych wysuwają się.](./media/RCS-AppSpecParms-ConfigureFormat-SelectorFldTranslate.PNG)

### <a name="add-a-new-field-to-consume-the-configured-lookup"></a>Dodaj nowe pole, aby użyć skonfigurowanego wyszukiwania

1.  Rozwiń **Model.Data**.
2.  Wybierz pozycję **Model.Data.Tax.Summary**.
3.  Wybierz opcję **Dodaj**.
4.  Wybierz **Funkcje/Pole obliczeniowe**.
5.  W polu **Nazwa** wpisz **LevelByLookup**.
6.  Wybierz opcję **Edytuj formułę**.
7.  W **polu formuła** wprowadź **Model.Selector(Model.Data.Summary.Code)**.
8.  Wybierz opcję **Zapisz**.

    ![Dodawanie model.selektora (Model.Data.Summary.Code) do strony projektanta formuł.](./media/RCS-AppSpecParms-ConfigureFormat-AddLevelByLookupFld.PNG)

9.  Zamknij stronę **Edytor formuł**.
10. Kliknij przycisk **OK**.

    ![Strona projektanta formatów z nową dodaną formułą.](./media/RCS-AppSpecParms-ConfigureFormat-AddLevelByLookupFld2.PNG)

    Należy zauważyć, że dodane pole obliczeniowe **LevelByLookup** będzie zwracać poziom opodatkowania jako wartość **listy poziomów opodatkowania** dla każdego rekordu zsumowanej transakcji podatkowej. Kod podatku rekordu zostanie przekazany do wyszukiwania źródła danych **Model.Selector** zostanie użyta lista reguł wyszukiwania selektorów, a dla tego źródła danych zostanie wykorzystana opcja

### <a name="add-a-new-format-enumeration-based-data-source"></a>Dodaj nowe źródło danych oparte na wyliczeniu

Następnie należy dodać nowe źródło danych odwołujące się do wyliczenia formatu, które zostało dodane wcześniej. Wartości tego źródła danych będą używane w wyrażeniu formatu ER w późniejszym terminie.

1.  Wybierz **Dodaj element główny**.
2.  Wybierz **Wyliczenia formatów\Wyliczenia**.
3.  W polu **Nazwa** wpisz **TaxationLevel**.
4.  W polu **Wyliczenie formatów** wybierz **Lista poziomów opodatkowania**.
5.  Wybierz opcję **Zapisz**.

### <a name="modify-an-existing-field-to-start-to-use-the-lookup"></a>Zmodyfikuj istniejące pole, aby rozpocząć korzystanie z wyszukiwania

Następnie zmodyfikuj istniejące pole obliczeniowe, tak aby używało skonfigurowanego źródła danych wyszukiwania do zwrócenia poprawnej wartości poziomu opodatkowania, w zależności od kodu podatku.

1.  Wybierz pozycję **Model.Data.Tax.Level**.
2.  Wybierz opcję **Edycja**.
3.  Wybierz opcję **Edytuj formułę**.

    Zauważ, że bieżące wyrażenie dla pola **Model.Data.Summary.Level** zawiera następujące kody podatków w postaci stałej:
    
    CASE (@. Kod, „VAT19”, „regularny”, „InVAT19”, „regularny”, „VAT7”, „obniżony”, „InVAT7”, „obniżony”, „Trzeci”, „Brak”, „InVAT0”, „Brak”, „inne”)

4.  W polu **formuła** wprowadź **CASE(@.LevelByLookup, TaxationLevel.'Regular taxation', "Regular", TaxationLevel.'Reduced taxation', "Reduced", TaxationLevel.'No taxation', "None", "Other")**.

    ![Strona projektanta operacji ER.](./media/RCS-AppSpecParms-ConfigureFormat-ChangeLookupFld.PNG)
    
    Zwróć uwagę, że wyrażenie w polu **Model.Data.Summary.Level** zwróci teraz poziom opodatkowania na podstawie kodu podatku bieżącego rekordu oraz zbioru reguł, które użytkownik biznes skonfigurowa w **Model.Data.Selector** wyszukiwaniu źródła danych.
    
5.  Wybierz opcję **Zapisz**.
6.  Zamknij stronę **Projektowanie formuły**.
7.  Kliknij przycisk **OK**.
8.  Wybierz opcję **Zapisz**.
9.  Zamknij stronę **Projektant formatu**.

## <a name="complete-the-draft-version-of-a-derived-format"></a>Pełna skorygowana wersja robocza pochodnego formatu

1.  W obszarze **wersje** na skróconej karcie wybierz opcję **Zmień stan**.
2.  Wybierz opcję **Zakończone**.
3.  Kliknij przycisk **OK**.

## <a name="export-completed-version-of-modified-format"></a>Eksport skończonej wersji formatu zmodyfikowanego

1.  W drzewie konfigurację wybierz **Format, aby uzyskać informacje o wyszukiwaniu danych LE**.
2.  Na karcie skróconej **Wersje** wybierz rekord o stanie **Zakończone**.
3.  Wybierz **Zamień**.
4.  Wybierz **Eksportuj jako plik XML**.
5.  Kliknij przycisk **OK**.
6.  Przeglądarka sieci Web pobiera **Format, aby uzyskać informacje o wyszukiwaniu danych LE.xml**. Zapisz ten plik lokalnie.

Powtórz kroki w tej sekcji dla elementów nadrzędnych **Format, aby uzyskać informacje o wyszukiwaniu danych LE** i lokalnie zapisać następujące pliki:

-   Wybierz opcję Format do nauczenia sparametryzowanych wywołań.xml
-   Wybierz opcję mapowanie, aby poznać wywołania sparametryzowane.xml
-   Model do nauczenia sparametryzowanych wywołań.xml

Aby dowiedzieć się, jak wyszukać format ER **Format, aby uzyskać informacje o wyszukiwaniu danych LE** skonfigurować zestawy kodów podatkowych zależne od podmiotu prawnego w celu filtrowania transakcji podatkowych według różnych poziomów opodatkowania należy wykonać kroki opisane w artykule [Konfigurowanie parametrów formatu ER dla firmy](er-app-specific-parameters-set-up.md).

## <a name="additional-resources"></a>Dodatkowe zasoby

[Projektant formuł w module Raportowanie elektroniczne](general-electronic-reporting-formula-designer.md)

[Konfiguracja parametrów formatu raportowania elektronicznego dla firmy](er-app-specific-parameters-set-up.md)

[Konfiguracja źródeł danych wyszukiwania, aby używać funkcji parametrów specyficznych dla aplikacji ER](er-lookup-data-sources.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
