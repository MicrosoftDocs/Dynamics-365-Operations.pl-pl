---
title: Projektowanie konfiguracji raportowania elektronicznego w celu wypełniania szablonów w formacie PDF
description: Ten artykuł zawiera informacje dotyczące projektowania formatu raportowania elektronicznego (ER) w celu wypełnienia szablonu PDF.
author: kfend
ms.date: 03/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.1
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.openlocfilehash: 4056c2b9442e26a0e1c99e6155a3cd605d222974
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9283322"
---
# <a name="design-er-configurations-to-fill-in-pdf-templates"></a>Projektowanie konfiguracji raportowania elektronicznego w celu wypełniania szablonów w formacie PDF

[!include[banner](../includes/banner.md)]

Procedury opisane w tym artykule są przykładami, które pokazują, jak użytkownik w roli **administratora systemu** lub roli **deweloper raportowania elektronicznego** może skonfigurować format raportowania elektronicznego (er), który generuje raporty jako Pliki PDF przy użyciu wypełnialnych dokumentów PDF jako szablonów raportów. Te kroki można wykonać w dowolnej firmie Dynamics 365 Finance lub Regulatory Configuration Services (RCS).

## <a name="prerequisites"></a>Wymagania wstępne

Przed rozpoczęciem, musisz mieć jeden z następujących typów dostępu, w zależności od usługi, której używasz do wykonania procedury w tym artykule:

- Dostęp do Finance w jednej z następujących ról:

    - Deweloper raportowania elektronicznego
    - Konsultant funkcjonalny raportowania elektronicznego
    - Administrator systemu

- Dostęp do RCS w jednej z następujących ról:

    - Deweloper raportowania elektronicznego
    - Konsultant funkcjonalny raportowania elektronicznego
    - Administrator systemu

Musisz też wykonać procedurę [Tworzenie dostawców konfiguracji i oznaczanie ich jako aktywnych](tasks/er-configuration-provider-mark-it-active-2016-11.md).

Na koniec trzeba pobrać następujące pliki.

| Opis zawartości                       | Nazwa pliku                                     |
|-------------------------------------------|-----------------------------------------------|
| Szablon dla pierwszej strony raportu | [IntrastatReportTemplate1.pdf](https://download.microsoft.com/download/0/8/3/0832c82b-4448-4562-afbf-01e0efc8d999/IntrastatReportTemplate1.pdf)                  |
| Szablon dla innych stron raportu    | [IntrastatReportTemplate2.pdf](https://download.microsoft.com/download/c/7/a/c7a8a806-2192-4034-9052-e8b84b527d5e/IntrastatReportTemplate2.pdf)                  |
| Przykładowy format ER – PDF                          | [Raport Intrastat (PDF).version.1.1.xml](https://download.microsoft.com/download/a/8/7/a87aea3e-3f60-404c-8899-c471d20e7ea9/IntrastatreportPDFversion1.1.xml)        |
| Przykładowy format ER – Excel                          | [Intrastat (import z programu Excel).version.1.1.xml](https://download.microsoft.com/download/a/2/c/a2c0c145-d989-4e55-9d47-9647c02e4ee4/IntrastatimportfromExcelversion1.1.xml) |
| Przykładowy zestaw danych                            | [Intrastat sample data.xlsx](https://download.microsoft.com/download/9/f/1/9f1c5b96-3800-475f-8cf6-1ddd42873758/Intrastatsampledata.xlsx)                    |

## <a name="design-the-format-configuration"></a>Projektowanie konfiguracji formatu

### <a name="get-access-to-the-list-of-configurations-provided-by-microsoft"></a>Uzyskiwanie dostępu do listy konfiguracji dostarczanej przez firmę Microsoft

1. Wybierz kolejno opcje **Administrowanie organizacją \> Obszary robocze \> Raportowanie elektroniczne**.
2. Upewnij się, że dostawca **Litware, Inc.** jest dostępny i oznaczony jako aktywny.
3. Na kafelku dla dostawcy **Microsoft** wybierz **Repozytoria**.

    > [!NOTE]
    > Jeśli repozytorium typu **LCS** już istnieje, pomiń pozostałe kroki tej procedury.

4. Wybierz opcję **Dodaj**.
5. W oknie dialogowym listy rozwijanej w polu **Typ repozytorium konfiguracji** wybierz opcję **LCS.**
6. Kliknij opcję **Utwórz repozytorium**.
7. Kliknij przycisk **OK**.

### <a name="get-the-model-configurations-provided-by-microsoft"></a>Pobierz model konfiguracji dostarczanych przez firmę Microsoft

1. W lewej części strony **repozytoria konfiguracji** wybierz przycisk **Pokaż filtry** (symbol lejka).
2. Dodaj filtr dla wartości **LCS** w polu **typ**, a następnie użyj **zaczyna się od** operatora.
3. Wybierz opcję **Zastosuj**.
4. Kliknij przycisk **Otwórz**.
5. W drzewie zaznacz element **Model Intrastat**.
6. Na skróconej karcie **wersje** wybierz opcję wersja **1**.

    > [!NOTE]
    > Jeśli przycisk **Importuj** na skróconej karcie **wersje** nie jest dostępny, pomiń pozostałe kroki tej procedury.

7. Wybierz opcję **Importuj**.
8. Wybierz opcję **tak**, aby potwierdzić import wybranej wersji konfiguracji modelu **Model Intrastat**.

### <a name="create-a-new-format-configuration"></a>Utwórz nową konfigurację formatu.

1. W obszarze roboczym **raportowanie elektroniczne** wybierz kafelek **konfiguracje raportowania**.
2. W drzewie zaznacz element **Model Intrastat**.
3. Wybierz **Utwórz konfigurację**.

    > [!NOTE]
    > Jeśli przycisk **Utwórz konfigurację** jest niedostępny, należy włączyć tryb projektowania na stronie **parametry raportowania elektronicznego**, który można otworzyć z obszaru roboczego **raportowania elektronicznego**.

4. W oknie dialogowym listy rozwijanej w polu **Nowa** grupa pól wybierz opcję **format oparty na modelu danych Intrastat**.
5. W polu **nazwa** wprowadź **raport Intrastat (PDF)**.
6. W polu **opis** wprowadź **raport Intrastat w formaciePDF**.

    > [!NOTE]
    > Aktywny dostawca konfiguracji jest wprowadzany automatycznie. Ten dostawca będzie mógł obsługiwać tę konfigurację. Inni dostawcy mogą używać tej konfiguracji, ale nie będą mogli nią zarządzać.

7. Opcjonalnie: w polu **typ formatu** można wybrać konkretny format dokumentu elektronicznego. Jeśli wybierzesz **PDF**, w czasie projektowania, Projektant operacji raportowania elektronicznego będzie oferować tylko elementy formatu, które mają zastosowanie tylko do dokumentów, które są generowane w formacie PDF (**pdf\plik**, **scalanie pdf\pdf**, itp.). Jeśli to pole pozostanie puste, format dokumentu elektronicznego zostanie określony w czasie projektowania w projektancie operacji raportowania elektronicznego, gdy zostanie dodany pierwszy element formatu. Na przykład jeśli dodasz **Excel\plik** jako pierwszy element formatu, Projektant operacji raportowania elektronicznego będzie oferować tylko elementy formatu, które mają zastosowanie tylko do dokumentów, które są generowane w formacie programu Excel (**Excel\komórka**, **Excel\zakres** itd.). itd..
8. Wybierz **Utwórz konfigurację**.

Zostanie utworzona nowa konfiguracja raportowania elektronicznego. Można użyć wersji roboczej tej konfiguracji do przechowywania składnika formatu raportowania elektronicznego, który jest przeznaczony do generowania dokumentów elektronicznych w formacie PDF.

### <a name="design-the-format-of-an-electronic-document"></a>Zaprojektuj format dokumentu elektronicznego.

Następnie w utworzonej konfiguracji formatu raportowania elektronicznego zaprojektujesz format raportowania elektronicznego, który wygeneruje raport **kontroli Intrastat** w formacie PDF. Pierwsza strona tego raportu musi wykazywać podsumowanie raportu i szczegóły transakcji handlu zagranicznego, które są zgłaszane. Pozostałe strony muszą wykazywać tylko szczegóły transakcji handlu zagranicznego, które są zgłaszane. Ponieważ generowane strony raportu muszą mieć różne układy, w formacie raportowania elektronicznego będą używane dwa różne szablony w formacie PDF.

W dowolnej przeglądarce plików PDF otwórz pobrane szablony PDF. Należy zauważyć, że każdy szablon zawiera wiele pól, które muszą być wypełnione. W każdym szablonie szczegóły transakcji handlu zagranicznego są przedstawiane jako 42 wiersze, z których każdy ma dziewięć pól. Numer wiersza pojawia się na końcu nazwy każdego pola (na przykład **Data 1**... **Data 42** i **asortyment 1**... **asortyment 42**).

Poniższa ilustracja przedstawia szablon PDF dla pierwszej strony raportu.

![Szablon 1.](media/rcs-ger-filloutpdf-template1.png)

Poniższa ilustracja przedstawia szablon PDF dla innych stron raportu.

![Szablon 2.](media/rcs-ger-filloutpdf-template2.png)

1. Na stronie **Konfiguracje** wybierz opcję **Projektant**.
2. Wybierz **Dodaj element główny**.
3. W oknie dialogowym rozwijanym w drzewie zaznacz opcję **PDF \> Scalanie PDF**.

    Po wybraniu elementu **Scalanie PDF** jako elementu głównego formatu, wszystkie dokumenty PDF, które są generowane w czasie wykonywania, zostaną scalone w pojedynczym końcowym dokumencie PDF. Jeśli potrzebny jest tylko jeden szablon PDF do generowania wszystkich wymaganych dokumentów przy użyciu projektowanego formatu raportowania elektronicznego, można wybrać **plik PDF** jako element główny.

4. W polu **Nazwa** wprowadź nazwę **Dane wyjściowe**.
5. W polu **Preferencje dotyczące języka** wybierz **Preferencje użytkownika**. Raport zostanie wygenerowany w preferowanym języku użytkownika, który go uruchomi.
6. W polu **Preferencje dotyczące kultury** wybierz **Preferencje użytkownika**. Wartości i daty prezentowane na stronach raportu zostaną sformatowane zgodnie z preferowanymi ustawieniami regionalnymi użytkownika, który uruchamia raport.
7. Kliknij przycisk **OK**.
8. W okienku akcji na karcie **Import** wybierz opcję **Importuj z pliku PDF**.

    Gdy dokument PDF do wypełnienia jest importowany jako szablon dla tego formatu raportowania elektronicznego, er, wszystkie wymagane elementy formatu raportowania elektronicznego (**plik PDF**, **Grupa pól** i **Pole**) są tworzone automatycznie w projektowanym formacie na podstawie struktury importowanego dokumentu PDF.

9. Wybierz opcję **Przeglądaj**. Przejdź do pliku **IntrastatReportTemplate1.pdf**, który został pobrany wcześniej jako wstępnie wymagany, i wybierz ten plik.
10. Kliknij przycisk **OK**.

    Wybrany plik zostanie załadowany, a pole **szablon** w oknie dialogowym **Importuj z pliku PDF** zostanie wypełnione.

11. Ustaw opcję **Grupuj pola** jako **Tak**. Jeśli wybrany dokument PDF zawiera grupy pól, będą one używane do grupowania utworzonych elementów formatu raportowania elektronicznego. W tym celu zostanie utworzony element formatu **grupy pól**.

    Jeśli ta opcja ma wartość **nie**, wymagane elementy formatu raportowania elektronicznego zostaną utworzone jako płaska lista elementów, które są zagnieżdżone w utworzonym elemencie formatu **pliku PDF**.

12. Kliknij przycisk **OK**.

    ![Okno dialogowe Importowanie z pliku PDF.](media/rcs-ger-filloutpdf-importtemplate.png)

13. W drzewie rozwiń **Dane wyjściowe**.

    Zauważ, że składnik **pliku PDF** został utworzony automatycznie, aby zarządzać tworzeniem pierwszej strony raportu generowanego w czasie wykonywania.

14. W drzewie rozwiń **Dane wyjściowe \> Plik PDF**.

    Należy zauważyć, że uporządkowana lista elementów formatu została utworzona automatycznie w tym formacie raportowania elektronicznego na podstawie struktury zaimportowanego wcześniej dokumentu PDF do wypełnienia.

15. W drzewie wybierz **Dane wyjściowe \> Plik PDF**.
16. W polu **Nazwa** wprowadź **Strona 1**.

    Ten element formatu zostanie użyty do wygenerowania pierwszej strony **raportu kontrolnego Intrastat**. Na tej stronie będzie widoczne podsumowanie raportu i szczegółów transakcji handlu zagranicznego.

    Jeśli pole **Preferencje dotyczące języka** pozostanie puste, ustawienie **preferencji dotyczących języka** nadrzędnego elementu **scalania PDF** określi język raportu generowanego za pomocą tego elementu formatu. Można wybrać inną wartość, aby zastąpić ustawienie elementu nadrzędnego.

    Jeśli pole **Preferencje dotyczące kultury** pozostanie puste, ustawienie **preferencji dotyczących kultury** nadrzędnego elementu **scalania PDF** określi ustawienia regionalne raportu generowanego za pomocą tego elementu formatu. Ustawienia regionalne określają format wartości i dat na stronach raportu. Można wybrać inną wartość, aby zastąpić ustawienie elementu nadrzędnego.

17. W okienku akcji wybierz kartę **import**. Zauważ, że przycisk **Aktualizuj z pliku PDF** stał się dostępny dla wybranego elementu formatu **Plik PDF**.

    Ten przycisk służy do importowania zaktualizowanego szablonu PDF do formatu edytowanego. Po zaimportowaniu zaktualizowanego szablonu PDF lista elementów formatu zostanie odpowiednio zmieniona:

    - W przypadku wszystkich nowych pól w zaktualizowanym szablonie PDF w edytowanym formacie systemu tworzony jest nowy element formatu raportowania elektronicznego.
    - Jeśli zaktualizowany szablon PDF nie zawiera już pól odpowiadających istniejącym elementom formatu w edytowanym formacie raportowania elektronicznego, te elementy formatu zostaną usunięte z formatu raportowania elektronicznego.

18. Na karcie **format** wybierz opcję **załączniki**.

    Należy zauważyć, że importowany dokument PDF jest dołączony do edytowanego formatu raportowania elektronicznego.

    ![Podgląd załącznika PDF.](media/rcs-ger-filloutpdf-attachedtemplate.png)

19. Kontynuuj projektowanie tego formatu przez zaimportowanie drugiego szablonu PDF, dodanie niezbędnych powiązań do źródeł danych itd.
20. Wybierz opcję **Zapisz**.
21. Zamknij stronę.
22. Wybierz opcję **Usuń**.
23. Wybierz opcję **Tak**.

Aby dowiedzieć się, jak używać elementów formatu **Scalanie PDF**, **Plik PDF**, **Grupa pól** i **Pole** w celu generowania dokumentów w formacie PDF, można zaimportować przykładowy format raportowania elektronicznego i zapoznać się z nim.

### <a name="import-the-format-configuration"></a>Import konfiguracji formatu

Następnie zaimportuj przykładowy, pobrany wcześniej format raportowania elektronicznego w celu wygenerowania **raportu kontrolnego Intrastat** w formacie PDF. Pierwsza strona tego raportu musi wykazywać podsumowanie raportu i szczegóły transakcji handlu zagranicznego, które są zgłaszane. Pozostałe strony muszą wykazywać tylko szczegóły transakcji handlu zagranicznego, które są zgłaszane.

1. Na stronie **konfiguracje** wybierz pozycję **Wymiana \> Załaduj z pliku XML**.
2. Wybierz opcję **Przeglądaj**. Przejdź do pliku **Intrastat report (PDF).version.1.1.xml**, który został pobrany wcześniej jako wstępnie wymagany, i wybierz ten plik.
3. Kliknij przycisk **OK**.

## <a name="analyze-the-format-configuration"></a>Zapoznaj się z konfiguracją formatu

### <a name="format-layout"></a>Układ formatu

1. Na stronie **konfiguracje** w drzewie wybierz opcję **Model Intrastat \> Raport Intrastat (PDF)**.
2. Wybierz opcję **Konstruktor**.
3. Wybierz **Pokaż szczegóły**.
4. W drzewie rozwiń **Dane wyjściowe: scalanie PDF**.

    Należy zauważyć, że ten format raportowania elektronicznego zawiera dwa elementy **pliku PDF**, a każdy z nich korzysta z innego szablonu PDF. Do wygenerowania pierwszej strony raportu w formacie PDF jest używany jeden szablon, a drugi szablon jest używany do generowania innych stron.

5. W drzewie rozwiń węzeł **Dane wyjściowe: scalanie PDF \> Strona 1: Plik PDF (IntrastatReportTemplate1)**.
6. W drzewie rozwiń węzeł **Dane wyjściowe: scalanie PDF \> Strona N: Plik PDF (IntrastatReportTemplate2)**.

    Należy zauważyć, że ponieważ zawartość dwóch szablonów PDF różni się od siebie, struktura elementów formatu zagnieżdżonego dla dwóch elementów **pliku PDF** również jest inna.

### <a name="format-mapping"></a>Mapowanie formatu

1. Na stronie **Projektant formatów** wybierz kartę **mapowanie.**
2. W drzewie rozwiń węzeł **Stronicowanie \> Strony**.

    ![Strona projektanta formuł z rozwiniętym drzewem modelu.](media/rcs-ger-filloutpdf-reviewformat.png)

    Warto pamiętać o następujących szczegółach:

    - Element formatu **Dane wyjściowe \> Strona 1** typu **pliku PDF** nie jest powiązany z żadnym źródłem danych, a wyrażenie **włączone** tego elementu formatu jest puste. Dlatego, w czasie wykonywania, szablon PDF **IntrastatReportTemplate1** jest wypełniany tylko raz podczas generowania pojedynczego dokumentu PDF.
    - Element formatu **Dane wyjściowe \> Strona N** typu **pliku PDF** jest związany ze źródłem danych **Paging.PageN** typu **lista rekordów**, a wyrażenie **włączone** tego elementu formatu jest puste. Dlatego, w czasie wykonywania, szablon PDF **IntrastatReportTemplate2** jest wypełniany dla każdego rekordu z listy powiązanych rekordów podczas generowania pojedynczego dokumentu PDF.
    - Ponieważ **Strona 1: plik PDF** i **Strona N: format PDF** są elementami podrzędnymi elementów formatu **Dane wyjściowe: scalanie PDF**, wszystkie wypełnione dokumenty PDF zostaną scalone w jednym, końcowym dokumencie PDF.
    - Źródła danych **Paging.Page1** i **Paging.PageN** są skonfigurowane jako filtry rekordów ze źródła **Paging.Pages**. To źródło danych jest skonfigurowane tak, aby dzielić cały zbiór transakcji handlu zagranicznego na partie. Każda partia zawiera maksymalnie 42 rekordów. Poniższe wyrażenie raportowania elektronicznego jest używane do dzielenia transakcji na partie:

        SPLITLIST(Totals.CommodityRecord,42)

    - Źródło danych **Paging.Pages** zawiera element **Paging.Pages.Enumerated**, który zwraca szczegóły wszystkich rekordów uwzględnionych w partii. Te szczegóły obejmują sekwencję rekordu w bieżącej partii (pole **Paging.Pages.Enumerated.Number**). Pole **Paging.Pages.Enumerated.Number** jest używane w wyrażeniu **Nazwa** elementów formatu **Pole PDF** w celu dynamicznego wygenerowania nazwy pola na podstawie numeru transakcji w danej partii. Wygenerowana nazwa pola jest następnie używana do wypełniania odpowiedniego pola PDF w używanym szablonie PDF.
    - Element formatu **Dane wyjściowe \> Strona N \> Szczegóły 2** typu **Grupa PDF** jest powiązany ze źródłem danych **Paging.PageN.Enumerated** (lub **\@.Enumerated**, jeśli jest używany tryb widoku **Ścieżka względna**) typu **Lista rekordów**. Dlatego w czasie wykonywania zagnieżdżone elementy tej grupy PDF są wypełniane dla każdego rekordu z listy rekordów powiązanych. W ten sposób poszczególne wiersze PDF są generowane, jeśli dla każdego n-tego z 42 rekordów listy **Paging.PageN.Enumerated** są wypełnione następujące pola PDF: Data N, Kierunek N, Asortyment N, itp. Dlatego też zachowanie tego elementu formatu **grupy pól** przypomina zachowanie sekwencji **XML \> Sekwencja** i elementów formatu **Tekst \> Sekwencja**.

3. W drzewie rozwiń **Dane wyjściowe \> Strona N \> Szczegóły2**.
4. W drzewie wybierz pozycję **Dane wyjściowe \> Strona N \> Szczegóły 2 \> PageFooter**.

    Zauważ, że atrybut **nazwy** tego elementu formatu jest zdefiniowany jako **PageFooter.** Należy również zauważyć, że wyrażenie **nazwy** elementu formatu jest puste.

5. W drzewie wybierz pozycję **Dane wyjściowe \> Strona N \> Szczegóły 2 \> Korekta 1**.

    Zauważ, że atrybut **nazwy** tego elementu formatu jest zdefiniowany jako **Korekta 1.** Należy również zauważyć, że wyrażenie **nazwy** elementu formatu jest zdefiniowane jako **Paging.FldName("Correction", \@. Number)**.

![Projektant formatów, w którym wybrano mapowanie.](media/rcs-ger-filloutpdf-reviewformat2.png)

Należy zauważyć, że element formatu **pola** służy do wypełniania pojedynczego pola w dokumencie PDF, który jest zdefiniowany jako szablon nadrzędnego elementu formatu **pliku PDF**. Powiązanie elementu formatu pliku **Plik PDF** lub elementów zagnieżdżonych, jeśli zawiera jakiekolwiek zagnieżdżone elementy, określa wartość wprowadzoną w odpowiednich polach PDF. Różne właściwości element formatu **Pola** można wykorzystywać do określenia, które pole pliku PDF zostanie wypełnione przez poszczególne elementy formatu:

- Na karcie **format** atrybut **nazwy** elementu formatu
- Na karcie **Mapowanie** wyrażenie **nazwy** elementu formatu

Ponieważ obie właściwości są opcjonalne dla elementu formatu **pola**, do określenia docelowego pola PDF są stosowane następujące reguły:

- Jeśli atrybut **nazwy** jest pusty, a wyrażenie **nazwy** zwraca ciąg pusty w czasie wykonywania, w czasie wykonywania jest generowany wyjątek w celu powiadomienia użytkownika o znalezieniu pola PDF w szablonie PDF, który jest używany do wypełniania pliku PDF dokumencie.
- Jeśli atrybut **nazwy** jest zdefiniowany, a wyrażenie **nazwy** jest puste, pole PDF o takiej samej nazwie jak atrybut **nazwy** elementu formatu jest wypełnione.
- Jeśli atrybut **nazwy** jest zdefiniowany, a wyrażenie **nazwy** jest skonfigurowane, pole PDF o takiej samej nazwie jak wartość jest zwracane przez wyrażenie **nazwy** wypełnionego elementu formatu.

> [!NOTE]
> Gdy pole wyboru w szablonie PDF nie należy do grupy pól wyboru, jest ono reprezentowane w edytowalnym formacie ER jako element **Pól**, który jest zagnieżdżony pod elementem **Plik PDF**. Ten typ pola wyboru PDF można ustawić jako zaznaczony w następujący sposób:
>
> - Odpowiedni element formatu **Pole** jest związany z polem źródła danych typu danych *[Wartość logiczna](er-formula-supported-data-types-primitive.md#boolean)*, które ma wartość **True**.
> - Odpowiedni element formatu **pola** zawiera element formatu **ciągu** zagnieżdżonego powiązany z polem źródła danych o wartości tekstowej **1**, **prawda** lub **tak**.
>
> Twój szablon może zawierać grupę pól wyboru, w których w danym momencie może być zaznaczone tylko jedno pole. Te pola wyboru są reprezentowane w szablonie PDF jako wiele pól formularza typu *CHECKBOX*. Każde pole ma tę samą nazwę, ale inną wartość eksportową. Kiedy zaimportujesz szablon do edytowalnego formatu ER, każde pole wyboru będzie reprezentowane w strukturze hierarchicznej formatu jako element **grupy pól wyboru**, który jest zagnieżdżony pod tym samym elementem **grupy pól wyboru**. Nazwa elementu **Grupa pól wyboru** będzie równa nazwie pól wyboru w szablonie PDF. Nazwa każdego elementu **Grupy pól wyboru** będzie równa wartości eksportu odpowiedniego pola wyboru w szablonie PDF.
>
> Możesz powiązać **Element grupy pól wyboru** polem źródła danych typu *wartość logiczna*.

## <a name="run-the-format-configuration"></a>Uruchom konfigurację formatu

### <a name="import-the-format-configuration"></a>Import konfiguracji formatu

Następnie zostanie załadowany przykładowy format raportowania elektronicznego **systemu Intrastat (import z programu Excel)**. Ten format jest przeznaczony do analizy skoroszytu Microsoft Excel wybranego przez użytkownika, który symuluje transakcje handlu zagranicznego.

1. Na stronie **konfiguracje** wybierz pozycję **Wymiana \> Załaduj z pliku XML**.
2. Wybierz opcję **Przeglądaj**. Przejdź do pliku **Intrastat (import from Excel).version.1.1.xml**, który został pobrany wcześniej jako wstępnie wymagany, i wybierz ten plik.
3. Kliknij przycisk **OK**.
4. W drzewie zaznacz element **Model Intrastat \> Intrastat (importuj z programu Excel)**.
5. Wybierz opcję **Edycja**.
6. Ustaw opcję **domyślnego mapowania modelu** jako **Tak**.

    > [!NOTE]
    > Jeśli wcześniej ustawiono opcję **domyślnego mapowania modelu** jako **Tak** dla konfiguracji **Modelu Intrastat** lub innej konfiguracji osadzonej w konfiguracji **Modelu Intrastat**, ustaw tę opcję jako **Nie**.

    Jeśli opcja **domyślnego mapowania modelu** jest ustawiona jako **tak**, zaimportowany format raportowania elektronicznego **Intrastat (import z programu Excel)** jest przypisywany jako domyślne źródło danych dla konfiguracji formatu **Raport Intrastat (PDF)**. Następnie, gdy zostanie uruchomiona konfiguracja formatu **raportu Intrastat (PDF)**, zawartość skoroszytu programu Excel, która jest analizowana przez format systemu **Intrastat (import z programu Excel)**, będzie symulować transakcje handlu zagranicznego, które muszą być zgłoszone. Na poniższej ilustracji pokazano przykład skoroszytu programu Excel.

    ![Skoroszyt programu Excel zawierający przykładowe dane.](media/rcs-ger-filloutpdf-excelworkbook.png)

### <a name="run-the-format-configuration"></a>Uruchom konfigurację formatu

1. Na stronie **konfiguracje** w drzewie wybierz opcję **Model Intrastat \> Raport Intrastat (PDF)**.
2. Wybierz opcję **Uruchom**.
3. Wybierz opcję **Przeglądaj**. Przejdź do pliku **Intrastat sample data.xlsx**, który został pobrany wcześniej jako wstępnie wymagany, i wybierz ten plik.
4. Kliknij przycisk **OK**.
5. W polu **kierunek raportu** wybierz opcję **oba**, aby wypełnić wszystkie transakcje z importowanego skoroszytu programu Excel w generowanym raporcie PDF
6. Kliknij przycisk **OK**.
7. Przejrzyj generowany dokument PDF.

Na poniższej ilustracji przedstawiono przykład pierwszej strony generowanego raportu.

![Pierwsza strona wygenerowanego raportu.](media/rcs-ger-filloutpdf-generatedreport.png)

Na poniższej ilustracji przedstawiono przykład innej strony generowanego raportu.

![Inna strona wygenerowanego raportu.](media/rcs-ger-filloutpdf-generatedreport2.png)

## <a name="limitations"></a>Ograniczenia

Nazwy pól, które można wypełnić, powinny być unikatowe w formularzu PDF, który ma zostać użycia jako szablon raportu. Dla każdego takiego pola podczas importowania formularza PDF tworzony jest indywidualny element formatu o odpowiedniej nazwie w edytowalnym formacie ER. Jeśli formularz PDF zawiera kilka pól o tej samej nazwie, dla pól tworzony jest jeden element formatu, który nie pozwala na ich indywidualne wypełnianie w czasie wykonywania.

## <a name="frequently-asked-questions"></a>Często zadawane pytania

### <a name="when-i-run-the-er-format-to-generate-a-report-in-pdf-format-why-do-i-get-the-following-errors--cannot-handle-iref-streams-the-current-implementation-of-pdfsharp-cannot-handle-this-pdf-feature-introduced-with-acrobat-6-and-a-pdf-name-must-start-with-a-slash-"></a>Gdy uruchamiam format rej. W celu wygenerowania raportu w formacie PDF, zgłaszam następujące błędy: **Nie mogę obsłużyć strumieni iref. Bieżąca implementacja narzędzia PDFSharp nie może obsługiwać tej funkcji w formacie PDF wprowadzonej w programie Acrobat 6.** i nazwy **w formacie PDF muszą rozpoczynać się ukośnikiem (/).**

Struktura ER używa wersji 1.5 biblioteki PDFSharp do generowania tych raportów PDF. Niektóre funkcje pliku PDF 1.5 (Adobe Reader 6.0) nie zostały jeszcze zaimplementowane w tej bibliotece. Dlatego program PDFSharp nie może jeszcze **otworzyć niektórych plików oznaczonych jako pliki PDF 1.5 lub wyższe** i mogą powodować błędy. Aby rozwiązać problem, użyj jednego z następujących rozwiązań:

-   W przypadku korzystania z własnego szablonu PDF: Zmień szablon na starszą wersję Adobe i zacznij korzystać z nowego szablonu w formacie ER.
-   W przypadku korzystania z szablonu formatu ER, który został Ci udostępniony przez innego dostawcę konfiguracji w ramach rozwiązania ER: Skontaktuj się z właścicielem tego rozwiązania ER i podaj opis problemu.
-   W przypadku korzystania z rozwiązania ISV zawierającego wcześniejszą wersję biblioteki PDFSharp: Skontaktuj się z właścicielem rozwiązania i zasugeruj uaktualnienie do nowszej wersji PDFSharp.

## <a name="additional-resources"></a>Dodatkowe zasoby

- [ER Projektowanie konfiguracji do generowania raportów w formacie OPENXML (listopad 2016)](tasks/er-design-reports-openxml-2016-11.md)
- [Projektowanie konfiguracji raportowania elektronicznego w celu generowania raportów w formacie programu Word](tasks/er-design-configuration-word-2016-11.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
