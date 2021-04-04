---
title: Poprawa śledzenia wyników wygenerowanych raportów ER i porównanie ich z wartościami wyjściowymi
description: W tym temacie opisano usprawnienia podstawowej funkcji ER w wersji Microsoft Dynamics 365 for Finance and Operations 10.0.3 (czerwiec 2019).
author: NickSelin
manager: AnnBe
ms.date: 06/19/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.openlocfilehash: 1579a0bb0dcf21ae16a54969e57ca88301041076
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2021
ms.locfileid: "5568956"
---
# <a name="improvements-in-tracing-the-results-of-generated-er-reports-and-comparing-them-with-baseline-values"></a>Poprawa śledzenia wyników wygenerowanych raportów ER i porównanie ich z wartościami wyjściowymi

[!include[banner](../includes/banner.md)]

W tym temacie wyjaśniono, w jaki sposób można poprawić korzystanie z podstawowej funkcji platformy Elektroniczne raportowanie (ER). Te poprawki są dostępne w Microsoft Dynamics 365 for Finance and Operations wersja 10.0.3 (czerwiec 2019) i późniejsze.

## <a name="automate-the-setting-of-baseline-rules"></a>Zautomatyzuj ustawianie zasad podstawowych

Temat [Śledź wygenerowane wyniki raportu i porównaj je z wartościami bazowymi](er-trace-reports-compare-baseline.md) wyjaśnia, jak skonfigurować strukturę ER do zbierania informacji o wykonaniach w formacie ER i oceny wyników tych egzekucji. Przykład w tym temacie pokazuje kroki, które należy wykonać.

Oto kilka najważniejszych kroków:

- Uruchom format ER, aby wygenerować plik wychodzący, i zapisz plik lokalnie.
- Dodaj plik przechowywany lokalnie jako załącznik linii bazowej dodanej do formatu ER.
- Skonfiguruj regułę bazową dla dodanej linii bazowej. Ta konfiguracja obejmuje następujące kroki:

    - Ustal format ER, aby wygenerować plik wychodzący, i zapisz plik lokalnie.
    - Wybierz załącznik, który odnosi się do pliku wychodzącego.

> [!NOTE]
> Te kroki muszą być wykonane ręcznie, nawet jeśli nowe możliwości ER umożliwiają ich automatyzację. Zapoznaj się z poniższym przykładem, aby dowiedzieć się więcej.

## <a name="example-automate-the-setting-of-baseline-rules"></a>Przykład: Zautomatyzuj ustawianie zasad linii bazowej

Żeby wykonać te kroki, musisz najpierw wypełnić procedury w temacie [Śledź wygenerowane wyniki raportu i porównaj je z wartościami bazowymi](er-trace-reports-compare-baseline.md) aż do "Dodaj nową linię bazową dla wyznaczonego formatu ER".

### <a name="review-added-baseline"></a>Przeglądnij dodaną linię bazową

1. Otwórz **Administracja organizacji** \> **Elektroniczne raportowanie** \> **Konfiguracje**.
2. Wybierz **Linie bazowe**.

    > [!NOTE]
    > Przycisk **Linie bazowe** w panelu akcji jest dostępny tylko wtedy, kiedy parametr ER **Uruchom w trybie debugowania** jest włączony dla danej firmy.

Linia bazowa została dodana do **Format do nauki podstawowych linii ER** format, ale zasady linii bazowej nie zostały jeszcze dodane dla tej linii bazowej.

![Strona podstawy formatu raportowania elektronicznego, w tej chwili bez reguł](media/GER-BaselineSample-AddBaseline2.PNG "Zrzut ekranu strony podstawy formatu raportowania elektronicznego")

### <a name="make-a-new-baseline-rule"></a>Utwórz nową zasadę bazową

1. Otwórz **Administracja organizacji** \> **Elektroniczne raportowanie** \> **Konfiguracje**.
2. W widoku drzewa otwórz **Model do nauki linii bazowych ER**.
3. W widoku drzewa wybierz **Model do nauki linii bazowych ER\\Format do nauki linii bazowych ER**.
4. Na skróconej karcie **Wersje** wybierz **Uruchom**.
5. W polu **Wpisz Id** wpisz **1**.
6. Ustaw opcję **Zrób pliki linii bazowych** jako **tak**.
7. Kliknij przycisk **OK**.
8. Wybierz **Linie bazowe**.

    ![Zrzut ekranu strony podstawy formatu raportowania elektronicznego, linie bazowe wybrane](media/GER-BaselineSample-ReviewAddedBaselineLine.PNG "Zrzut ekranu strony podstawy formatu raportowania elektronicznego")

    Wygenerowany plik wychodzący został automatycznie dołączony do linii bazowej wykonanego formatu ER. Reguła linii bazowej została automatycznie dodana do tej linii bazowej i zawiera również odniesienie do załączonego pliku.

9. W polu **Nazwa** wpisz **Linia Bazowa 1**.
10. W polu **Maska nazwy pliku** wpisz **.xml**.
11. Wybierz opcję **Zapisz**.

### <a name="run-the-format"></a>Uruchom format

Jesteś gotowy zakończyć pozostałe kroki w [Śledź wygenerowane wyniki raportu i porównaj je z wartościami bazowymi](er-trace-reports-compare-baseline.md) począwszy od „Uruchom zaprojektowany format ER i przejrzyj dziennik, aby przeanalizować wyniki”.

> [!NOTE]
> Po usunięciu automatycznie dodanej reguły linii bazowej w **linie bazowe** na karcie skróconej przywoływany załącznik nie jest automatycznie usuwany.

## <a name="configure-the-baseline-so-that-it-ignores-constantly-changing-parts-of-the-er-output"></a>Skonfiguruj linię bazową, tak aby ignorowała stale zmieniające się części wyjścia ER

Skonfiguruj linię bazową, aby ignorować stare zmieniające się części wyjścia ER Na przykład informacje mogą być datą i godziną przetwarzania lub unikalnym identyfikatorem wygenerowanego dokumentu w różnych formatach (unikatowy identyfikator globalny \[GUID\], itd.). Nowe funkcje ER umożliwiają skonfigurowanie reguły linii bazowej, tak aby ignorowała zmienne elementy formatu ER, gdy format jest uruchamiany w celu porównania wartości linii bazowej z wynikami wykonania formatu. Zapoznaj się z poniższym przykładem, aby dowiedzieć się więcej.

## <a name="example-configure-the-baseline-so-that-it-ignores-constantly-changing-parts-of-the-er-output"></a>Przykład: Skonfiguruj linię bazową, tak aby ignorowała stale zmieniające się części wyjścia ER

Żeby wykonać te kroki, musisz najpierw wypełnić procedury w przykładzie w [Śledź wygenerowane wyniki raportu i porównaj je z wartościami bazowymi](er-trace-reports-compare-baseline.md).

### <a name="modify-a-configured-er-format"></a>Zmodyfikuj skonfigurowany format ER

1. Otwórz **Administracja organizacji** \> **Elektroniczne raportowanie** \> **Konfiguracje**.
2. W widoku drzewa otwórz **Model do nauki linii bazowych ER**.
3. W widoku drzewa wybierz **Model do nauki linii bazowych ER\\Format do nauki linii bazowych ER**.
4. Wybierz opcję **Konstruktor**.
5. W widoku drzewa wybierz **Wyjście\\Dokument**.
6. Wybierz opcję **Dodaj**.
7. W rozwijanym menu w widoku drzewa wybier **XML\\Attribute**.z
8. W polu **Nazwa** wpisz **ProcessingDateTime**.
9. Kliknij przycisk **OK**.
10. Na karcie **Mapowanie** wybierz **Wyjście\\Dokument\\ProcessingDateTime**.
11. Wybierz opcję **Edytuj formułę**.
12. W polu **Formuła** wpisz: **DATETIMEFORMAT(NOW(), "O")**
13. Wybierz **Zapisz** i następnie wybierz **Test**.
14. Wybierz **Test** ponownie, żeby jeszcze raz sprawdzić skonfigurowaną formułę.

    ![Strona projektanta formuł](media/GER-BaselineSample-DefineProcessingDTExpression.PNG "Zrzut ekranu strony projektanta formuł")

    > [!NOTE]
    > Karta **Wyniki testu** pokazuje, że skonfigurowane wyrażenie zwraca inną wartość daty i godziny, gdy jest wywoływana.

15. Zamknij stronę **Projektowanie formuły** i następnie wybierz **Zapisz**.

    ![Strona projektanta formatu](media/GER-BaselineSample-FormatMappingDesign2.PNG "Zrzut ekranu strony projektanta formatu")

16. Zamknij stronę **Projektowanie formuły**.

### <a name="remove-an-existing-baseline-rule"></a>Usuń istniejącą zasadę bazową

1. Otwórz **Administracja organizacji** \> **Elektroniczne raportowanie** \> **Konfiguracje**.
2. Wybierz **Linie bazowe**.
3. Na liście linii bazowych wybierz linię, która została skonfigurowana do **Format do nauki podstawowych linii ER**.
4. Na skróconej karcie **Linie bazowe** wybierz **Usuń**, żeby usunąć zasadę linii bazowej. którą ustaliłes wcześniej.

![Strona podstawy formatu raportowania elektronicznego, usunięta](media/GER-BaselineSample-AddBaseline3.PNG "Zrzut ekranu strony podstawy formatu raportowania elektronicznego")

### <a name="define-replacements-for-bindings-of-designed-er-format"></a>Zdefiniuj zamienniki dla powiązań zaprojektowanego formatu ER

1. Na stonie **Konfiguracje** na skróconej karcie **Zastąpienia** wybierz **Wybierz komponenty**.
2. Na drzewie komponentów formatu rozwiń **Wyjście**, rozwiń **Wyjście\\Dokument**, a następnie zaznacz okienko dla **Wyjście\\Dokument\\ProcessingDateTime**.
3. Kliknij przycisk **OK**.

![Strona podstawy formatu raportowania elektronicznego, składniki](media/GER-BaselineSample-AddBaseline4.PNG "Zrzut ekranu strony podstawy formatu raportowania elektronicznego")

Wybrany komponent formatu ER został dodany do listy komponentów na skróconej karcie w **Zastąpienia**. Gdy podstawowy format ER jest uruchamiany w trybie debugowania, powiązanie formatu dla każdego komponentu zostanie zastąpione przez powiązanie pokazane w kolumnie **Powiązania**. Aby zmienić domyślne wiązanie dla komponentu wymienionego na skróconej karcie w **Zastąpienia** wybierz **Edytuj**.

### <a name="make-a-new-baseline-rule"></a>Utwórz nową zasadę bazową

Wykonaj kroki opisane w sekcji „Przykład: zautomatyzuj ustawienie zasad podstawowych” wcześniej w tym temacie. Powiadomienie ostrzega, że plik wychodzący został wygenerowany przy użyciu ustawień linii bazowej i wystąpiła wymuszona wymiana powiązań formatu.

![Strona Notyfikacja na stronie konfiguracjii](media/GER-BaselineSample-FormatRunToMakeBaselineFile4.PNG "Zrzut ekranu powiadomienia na stronie konfiguracji")

### <a name="suppress-warnings-about-the-replacement-of-format-bindings"></a>Pomiń ostrzeżenia dotyczące wymiany powiązań formatu

Ustawiając określone parametry ER, można pominąć powiadomienia ostrzegające o zamianie powiązań formatu. To wyłączenie może być przydatne, gdy powiązania formatu są zastępowane w trybie nienadzorowanym za pomocą narzędzia Regression Suite Automation Tool. W takim przypadku ostrzeżenie można uznać za awarię uruchomionego przypadku testowego.

1. na stronie **konfiguracje** na panelu akcji na karcie **Konfiguracje** wybierz **Parametry użytkownika**.
2. Ustaw **Pomiń ostrzeżenia bazowe** na **Tak**, a następnie wybierz **OK**.

### <a name="review-the-generated-baseline-file"></a>Przeglądnij wygenerowany plik bazowy

1. Otwórz **Administracja organizacji** \> **Elektroniczne raportowanie** \> **Konfiguracje**.
2. Wybierz **Linie bazowe**.
3. Wybierz **Załączniki**.
    > [!NOTE]
    > Wygenerowany plik zawiera tekst i datę przetwarzania (**"#"**) z powiązania skonfigurowanego w dodanej regule linii bazowej, a nie z powiązania formatu.
    
4. Zamknij stronę **Załączniki**.

### <a name="run-the-designed-er-format-and-review-the-log-to-analyze-the-results"></a>Uruchom zaprojektowany format ER i przejrzyj dziennik, aby przeanalizować wyniki

1. Otwórz **Administracja organizacji** \> **Elektroniczne raportowanie** \> **Konfiguracje**.
2. W widoku drzewa otwórz **Model do nauki linii bazowych ER**.
3. W widoku drzewa wybierz **Model do nauki linii bazowych ER\\Format do nauki linii bazowych ER**.
4. Na skróconej karcie **Wersje** wybierz **Uruchom**.
5. W polu **Wpisz Id** wpisz **1**.
6. Kliknij przycisk **OK**.
7. Otwórz **Administracja organizacji** \> **Elektroniczne raportowanie** \> **Dzienniki debugowania konfiguracji**.

Dziennik wykonania zawiera informacje o wynikach porównania wygenerowanego pliku ze skonfigurowaną linią bazową. Dziennik wskazuje, że wygenerowany plik i linia bazowa są równe, nawet jeśli wykonany format zawiera powiązanie, aby wprowadzić stale zmieniającą się datę i godzinę w pliku wychodzącym.

> [!NOTE]
> Mimo że plik wychodzący został wygenerowany przy użyciu ustawień linii bazowej, które wymuszają zastąpienie powiązań formatu, nie otrzymasz żadnych ostrzeżeń o zmianie.

## <a name="exchange-baseline-settings-between-environments"></a>Wymień ustawienia linii bazowej między środowiskami

### <a name="export-baseline-settings"></a>Eksportuj ustawień linii bazowej

Nowe funkcje ER umożliwiają eksportowanie ustawień podstawowych dla wybranego formatu ER z bieżącego środowiska i zapisywanie ich jako plików XML. 

Aby wyeksportować ustawienia linii bazowej, w przypadku linii bazowych **Elektronicznego formatu raportowania** wybierz opcję **Eksport**.

### <a name="import-baseline-settings"></a>Importuj ustawienia podstawowe

Wyeksportowane ustawienia linii bazowej można zaimportować do innego środowiska. Środowisko należy najpierw zaimportować jako format ER. Możesz importowaćustawienia linii bazowej

Aby zaimportować ustawienia linii bazowej z lokalnie przechowywanego pliku XML, w przypadku linii bazowych na stronie **Elektronicznego formatu raportowania** wybierz **Import**, a następnie wybierz **Przeglądaj**, aby wybrać plik XML.

![Okienko dialogowe importuj ustawienia podstawowe](media/GER-BaselineSample-ImportBaseline1.PNG "Zrzut ekranu okna dialogowego importowania ustawień podstawowych")

Aby zaimportować ustawienia linii bazowej z pliku XML przechowywanego na serwerze Microsoft SharePoint w oparciu o bieżące ustawienia zarządzania dokumentami i wybrany typ dokumentu, w przypadku linii bazowych **Elektronicznego formatu raportowania** wybierz opcję **Import ze źródła**. Następnie wybierz typ dokumentu i plik XML. Wymagany typ dokumentu, aby uzyskać dostęp do folderu SharePoint należy go wcześniej skonfigurować.

![Okno dialogowe Importowanie ze źródła](media/GER-BaselineSample-ImportBaseline2.PNG "Zrzut ekranu okna dialogowego importowania ze źródła")

> [!NOTE]
> Możesz użyć Rejestratora zadań do zapisania kroków wyboru wymaganego typu dokumentu i nazwy pliku w oknie dialogowym **Import ze źródła**. W ten sposób można zachować wymagane ustawienia linii bazowej na serwerze SharePoint, a następnie automatycznie zaimportować je, odtwarzając nagranie zadania po uruchomieniu automatycznych testów za pomocą narzędzia Regression Suite Automation Tool.

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Śledzenie wyników wygenerowanych raportów i porównywanie ich z wartościami bazowymi](er-trace-reports-compare-baseline.md)
- [Zasoby rejestratora zadań](../user-interface/task-recorder.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]