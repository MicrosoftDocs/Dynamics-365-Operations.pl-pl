---
title: Projektowanie raportów wielojęzycznych w module raportowanie elektroniczne
description: W tym temacie wyjaśniono, jak można stosować etykiety raportów elektronicznych (ER) do projektowania i generowania raportów wielojęzycznych.
author: NickSelin
ms.date: 04/21/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERModelMappingDesigner, EROperationDesigner, ERExpressionDesignerFormula
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 48e54c0f7d4bd1b4e1661a5bd1d4c11fd9cec986
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/06/2021
ms.locfileid: "6351128"
---
# <a name="design-multilingual-reports-in-electronic-reporting"></a>Projektowanie raportów wielojęzycznych w module raportowanie elektroniczne

[!include[banner](../includes/banner.md)]

## <a name="overview"></a>Omówienie

Użytkownicy biznesowi używają platformy [Raportowanie elektroniczne (ER)](general-electronic-reporting.md), która umożliwia konfigurowanie formatów dokumentów, które muszą zostać utworzone zgodnie z wymogami prawnymi obowiązującymi w różnych krajach lub regionach. Gdy wymagania te wymagają, aby dokumenty wychodzące były generowane w różnych językach dla różnych krajów lub regionów, możesz skonfigurować jeden [format](general-electronic-reporting.md#FormatComponentOutbound) ER zawierający zasoby zależne od języka. W ten sposób można ponownie użyć formatu, aby wygenerować dokumenty wychodzące dla różnych krajów lub regionów. Można również użyć jednego formatu ER do wygenerowania dokumentu wychodzącego w różnych językach dla odpowiednich odbiorców, dostawców, filii lub innych jednostek.

Modele i mapowania danych ER można skonfigurować jako źródła danych skonfigurowanych formatów ER, aby zdefiniować przepływ danych określający, jakie dane aplikacji są umieszczane w generowanych dokumentach. Jako [dostawca](general-electronic-reporting.md#Provider) konfiguracji ER można [publikować](tasks/er-upload-configuration-into-lifecycle-services.md#upload-a-configuration-into-lcs) skonfigurowane [modele danych](general-electronic-reporting.md#data-model-and-model-mapping-components), [mapowania modeli](general-electronic-reporting.md#data-model-and-model-mapping-components) i [formaty](general-electronic-reporting.md#FormatComponentOutbound) jako składniki rozwiązania ER w celu generowania określonych dokumentów wychodzących. Można również zezwolić klientom na [przekazywanie](general-electronic-reporting-manage-configuration-lifecycle.md) opublikowanego rozwiązania ER, aby można było go używać i dostosowywać. Jeśli użytkownik oczekuje, że klienci mogą mówić do innych języków, można skonfigurować składniki ER, tak aby zawierały zasoby zależne od języka. W ten sposób zawartość edytowalnego składnika ER może być prezentowana w języku preferowanym przez użytkownika klienta w czasie projektowania.

Zasoby zależne od języka można konfigurować jako etykiety ER. Następnie można skorzystać z tych etykiet, aby skonfigurować składniki ER do następujących celów:

- W czasie projektowania:

    - Umożliwia prezentowanie zawartości skonfigurowanych składników ER w języku preferowanym przez użytkownika.

- Podczas uruchamiania:

    - Generowanie zawartości zależnej od języka dla dokumentów wychodzących.
    - Umożliwia wyświetlanie komunikatów o błędach i ostrzeżeniach w języku preferowanym przez użytkownika.
    - Monituj o wymagane pola w języku preferowanym przez użytkownika.

Etykiety ER można konfigurować w każdej [konfiguracji](general-electronic-reporting.md#Configuration) ER, która zawiera różne składniki. Etykiety mogą być obsługiwane niezależnie od skonfigurowanej logiki modeli danych ER, mapowań modeli ER i składników formatu ER.

Każda etykieta ER jest identyfikowana przy użyciu identyfikatora, który jest unikatowy w zakresie konfiguracji ER, która zawiera daną etykietę. Każda etykieta może zawierać tekst etykiet dla każdego języka obsługiwanego w bieżącym wystąpieniu rozwiązania Microsoft Dynamics 365 Finance. Do tych obsługiwanych języków należą języki wdrożonych dostosowań.

## <a name="entry"></a>Wpis

Podczas projektowania modelu danych ER, mapowania modelu ER lub modułu, opcja **Tłumacz** jest wyświetlana przy każdym zaznaczeniu pola, które może zawierać kontekst, który można przetłumaczeyć. Po wybraniu tej opcji można połączyć wybrane pole z etykietą ER w <a name="TextTranslationPane">okienku</a> **Tłumaczenie tekstu**. Można wybrać istniejącą etykietę ER lub dodać nową etykietę ER, jeśli jeszcze nie jest dostępna. Po wybraniu lub dodaniu etykiety ER można dodać odpowiedni tekst dla każdego języka obsługiwanego w bieżącym wystąpieniu Finance.

Na poniższej ilustracji pokazano, jak to tłumaczenie zostało wykonane w edytowalnym modelu danych ER. W tym przykładzie atrybut **Opis** pola **PurchaseOrder** dla edytowalnego **Modelu faktury** jest przetłumaczony na język austriacki niemiecki (DE-AT) i japoński (JA).

![Przekazywanie etykiety ER w projektancie modelu danych ER.](./media/er-multilingual-labels-refer.png)

Tłumaczenie może dotyczyć tylko tekstu etykiet znajdujących się w edytowalnym składniku ER. Jeśli na przykład zostanie wybrana opcja **Przetłumacz** dla atrybutu etykiety źródła danych mapowania modelu ER, a następnie wybierzesz etykietę ER, która znajduje się w nadrzędnym modelu danych ER, zobaczysz treść etykiety, ale nie możesz tego zmienić. W takich przypadkach pole **Przetłumaczony tekst** jest niedostępne, jak pokazano na poniższej ilustracji.

![Przejrzenie zapewnionego tłumaczenia etykiety ER w projektancie mapowania modelu ER.](./media/er-multilingual-labels-refer-mapping.png)

> [!NOTE]
> Nie można wykorzystać projektantów do usunięcia etykiety wprowadzonej w edytowalnym składniku ER.

## <a name="scope"></a>Zakres

Etykiety ER można odwoływać do kilku możliwych do tłumaczenia atrybutów składników ER.

### <a name="data-model-component"></a>Składnik modelu danych

Podczas konfigurowania modelu danych ER można dodać do niego etykiety ER. Atrybuty **Etykieta** i **Opis** elementów modelu, pola każdego modelu i każdej wartości wyliczania modelu <a id="LinkModelEnum"></a> można połączyć z etykietą ER dodawaną do modelu danych ER.

![Zapewnienie tłumaczenia atrybutu Opis w projektancie modelu danych ER.](./media/er-multilingual-labels-refer.png)

Gdy model danych ER jest skonfigurowany w ten sposób, jego zawartość zostanie przedstawiona użytkownikom projektanta modelu danych ER w odniesieniu do każdego preferowanego języka każdego użytkownika. Dlatego obsługa modelu jest uproszczona. Na poniższych ilustracjach przedstawiono sposób działania tej funkcji dla użytkowników, którzy mają DE i JA ustawione jako preferowany język.

![Układ projektanta danych modelu ER dla użytkownika, który w danym momencie ustawiony DE-AT jako preferowany język.](./media/er-multilingual-labels-refer-de.png)

![Układ projektanta danych modelu ER dla użytkownika, który w danym momencie ustawiony JA jako preferowany język.](./media/er-multilingual-labels-refer-ja.png)

### <a name="model-mapping-component"></a>Składnik mapowania modelu

Ponieważ mapowanie modelu ER oparte jest na modelu danych ER, etykiety elementów modelu danych, do których się odwołuje, pojawiły się w preferowanym języku użytkownika w projektancie mapowania modelu. Na poniższej ilustracji pokazano, w jaki sposób znaczenie pola **PurchaseOrder** jest objaśnione w mapowaniu edytowalnego modelu przy użyciu etykiety atrybutu **Opis**, która została dodana do skonfigurowanego modelu danych. Zauważ, że etykieta jest przedstawiona w preferowanym języku użytkownika (w tym przykładzie DE-AT).

![Układ projektanta mapowania modelu ER dla użytkownika, który w danym momencie ustawiony DE-AT jako preferowany język.](./media/er-multilingual-labels-show-mapping.png)

Jeśli atrybut **Etykieta** źródła danych **Parametr wejściowy użytkownika** jest skonfigurowany jako połączony z etykietą ER, pole parametru odpowiadające temu źródłu danych jest przedstawiane w oknie dialogowym użytkownika w czasie wykonywania do użytkowników w preferowanym języku.

### <a name="format-component"></a>Składnik formatu

Podczas konfigurowania formatu ER można dodać do niego etykiety ER. Atrybuty **Etykieta** i **Tekst pomocy** dla każdego skonfigurowanego źródła danych mogą być połączone z etykietą właściciela dodawaną do formatu ER. Atrybuty **Etykieta** i **Opis** dla każdej wartości wyliczenia formatu <a id="LinkFormatEnum"></a> można również połączyć z etykietą ER dostępną z poziomu edytowalnego formatu ER.

> [!NOTE]
> Można również połączyć te atrybuty z etykietą właściciela nadrzędnego modelu danych ER, która ponownie używa etykiet modelu w każdym formacie, który jest skonfigurowany dla tego modelu danych ER.

Gdy format ER zostanie skonfigurowany w ten sposób, treść tego formatu zostanie przedstawiona użytkownikom projektanta Operacji ER w preferowanym języku każdego użytkownika. Dlatego utrzymanie formatu i analiza skonfigurowanej logiki są uproszczone.

Ponieważ format ER oparty jest na modelu danych ER, etykiety przywoływane w elementach modelu danych są prezentowane w projektancie formatu ER w języku preferowanym przez użytkownika.

Jeśli atrybut **Etykieta** źródła danych **Parametr wejściowy użytkownika** jest połączony z etykietą ER, pole odpowiadające parametrowi w oknie dialogowym użytkownika w czasie wykonywania jest przedstawiane użytkownikowi jako monit. Na poniższych ilustracjach przedstawiono sposób łączenia atrybutu **Etykieta** źródła danych **Parametr wejściowy użytkownika** w czasie projektowania z etykietą ER, dzięki czemu użytkownicy są monitowani o podanie parametru w różnych językach preferowanych przez użytkownika w czasie uruchomienia (pokazane dla języka angielskiego amerykańskiego (EN-US) i DE-AT).

![Przekazywanie atrybutów parametru wejściowego użytkownika w projektancie operacji ER.](./media/er-multilingual-labels-refer-format.png)

![Przetwarzanie płatności dostawcy ER w czasie wykonywania dla preferowanego przez użytkownika języka EN-US.](./media/er-multilingual-labels-show-runtime-en.png)

![Przetwarzanie płatności dostawcy ER w czasie wykonywania dla preferowanego przez użytkownika języka DE-AT.](./media/er-multilingual-labels-show-runtime-de.png)

### <a name="expressions"></a>Then

Aby użyć etykiety w [wyrażeniu](er-formula-language.md) ER należy użyć składni **@"GER\_LABEL:X"**, gdzie prefiks **@** wskazuje, że argument odnosi się do etykiety, a **GER\_LABEL** wskazuje, że zaangażowana jest etykieta ER, a **X** to identyfikator etykiety ER.

![Konfigurowanie wyrażenia ER zawierającej odwołanie do etykiety ER w projektancie formuł ER.](./media/er-multilingual-labels-expression1.png)

Aby odwołać się do etykiety systemu (aplikacji), należy zastosować składnię **@"X"**, gdzie prefiks **@** wskazuje, że argument odwołuje się do etykiety, a **X** to identyfikator etykiety systemowej.

![Konfigurowanie wyrażenia ER zawierającej odwołanie do etykiety aplikacji w projektancie formuł ER.](./media/er-multilingual-labels-expression2.png)

#### <a name="model-mapping"></a>Mapowanie modelu

Wyrażenie mapowania modelu ER można skonfigurować za pomocą etykiety. Jeśli to mapowanie jest wywoływane przez format ER, który jest uruchamiany w celu wygenerowania dokumentu wychodzącego, kontekst wykonania zawiera kod języka. Skonfigurowana etykieta wyrażenia zostanie uzupełniona tekstem etykiety skonfigurowanym dla języka tego kontekstu.

Jeśli etykieta, której dotyczy odwołanie, nie ma tłumaczenia dla języka kontekstu formatu, który wywołuje mapowanie modelu, w zamian zostanie użyty tekst etykiety w języku EN-US.

#### <a name="format"></a>Format

Wyrażenie ER formatu ER można skonfigurować za pomocą etykiet. Kiedy format jest uruchamiany w celu wygenerowania dokumentu wychodzącego, kontekst wykonania zawiera kod języka. Skonfigurowana etykieta wyrażenia zostanie uzupełniona tekstem etykiety skonfigurowanym dla języka tego kontekstu.

![Zapewnienie tłumaczenia etykiety ER edytowalnego wyrażenia ER w projektancie formuł ER.](./media/er-multilingual-labels-refer-in-expression.png)

![Próbka powiązania danych odnoszącego się do etykiety ER w projektancie operacji ER.](./media/er-multilingual-labels-refer-in-binding.png)

Składnik **PLIK** formatu ER można skonfigurować w taki sposób, aby raport był generowany w preferowanym języku użytkownika.

![Aby wygenerować raport w preferowanym języku użytkownika, należy skonfigurować składnik PLIK w projektancie operacji ER.](./media/er-multilingual-labels-language-context-user.png)

Jeśli w ten sposób skonfigurujesz format ER, raport zostanie wygenerowany przy użyciu odpowiedniego tekstu etykiet ER. Poniższe ilustracje przedstawiają przykłady raportów dotyczących języków EN-US i DE-AT użytkownika.

![Podgląd raportu wygenerowanego w preferowanym języku użytkownika EN-US.](./media/er-multilingual-labels-report-preview-en.png)

![Podgląd raportu wygenerowanego w preferowanym języku użytkownika DE-AT.](./media/er-multilingual-labels-report-preview-de.png)

Jeśli etykieta, której dotyczy odwołanie, nie ma tłumaczenia dla języka kontekstu formatu, w zamian zostanie użyty tekst etykiety w języku EN-US.

## <a name="language"></a>Język

ER obsługuje różne sposoby określania języka wygenerowanego raportu. W polu **Preferencje językowe** na karcie **Format** można wybrać następujące wartości:

- **Preferencja firmy** — generowanie raportu w języku określonym przez firmę.

    ![W projektancie operacji ER należy określić język preferowany przez firmę jako język wygenerowanego raportu.](./media/er-multilingual-labels-language-context-company.png)

- **Preferencja użytkownika** — generowanie raportu w języku preferowanym dla użytkownika.
- **Jawnie zdefiniowany** — generowanie raportu w języku określonym w czasie projektowania.

    ![Określ w projektancie operacji ER język zdefiniowany w czasie projektowania jako język generowanego raportu.](./media/er-multilingual-labels-language-context-fixed.png)

- **Zdefiniowane w czasie wykonywania** — generowanie raportu w języku określonym w czasie wykonywania. W przypadku wybrania tej wartości w polu **Język** skonfiguruj wyrażenie ER, która zwraca kod języka dla języka, na przykład język odpowiedniego odbiorcy.

    ![Określ w projektancie operacji ER język zdefiniowany w czasie wykonania jako język generowanego raportu.](./media/er-multilingual-labels-language-context-runtime.png)

## <a name="culture-specific-formatting"></a>Formatowanie specyficzne dla kultury

ER obsługuje różne sposoby określania kultury wygenerowanego raportu. Dlatego poprawnego formatowania odpowiedniego dla danej kultury można użyć dla daty, czasu i wartości liczbowych. Podczas projektowania formatu ER, na karcie **Format**, w polu **Preferencje kultury** można wybrać jedną z następujących wartości dla każdego składnika formatu typu **Plik\\Common**, **Plik\\Excel**, **Plik\\PDF** lub **PDF\\Merger**:

- **Preferencje użytkownika** — sformatowanie wartości zgodnie z preferowaną przez użytkownika kulturę. Do definicji tej kultury służy pole **Data, godzina i format liczby** na karcie **Preferencje** na stronie **Opcje użytkownika**.

    ![Definiowanie preferowanej kultury użytkownika jako kultury generowanego raportu w konstruktorze operacji ER.](./media/er-multilingual-labels-culture-context-user-preferred.png)

- **Jawnie zdefiniowane** — format wartości zgodnie z kulturę określoną w czasie projektowania.

    ![Definiowanie kultury, która została określona w czasie projektowania, jako kultury generowanego raportu w konstruktorze operacji ER.](./media/er-multilingual-labels-culture-context-fixed.png)

- **Zdefiniowane w czasie wykonywania** — format wartości zgodnie z kulturę określoną w czasie wykonywania. Po wybraniu tej wartości na karcie **Mapowanie** w polu **Data, godzina i format liczby** skonfiguruj wyrażenie ER, które zwraca kod kultury dla kultury, takie jak kultura odpowiedniego odbiorcy.

    ![Definiowanie kultury, która została określona w czasie wykonywania, jako kultury generowanego raportu w konstruktorze operacji ER.](./media/er-multilingual-labels-culture-context-runtime.png)

> [!NOTE]
> Składnik ER, dla którego definiujesz określoną kulturę, może zawierać podrzędne składniki ER, skonfigurowane do wstawienia jako wartość tekstowa. Domyślnie do formatowania wartości tych składników jest używana kultura składnika nadrzędnego. Można używać następujących wbudowanych funkcji ER do konfigurowania powiązań dla tych składników i stosowania alternatywnej kultury formatowania wartości:
>
> - [DATEFORMAT](er-functions-datetime-dateformat.md#syntax-2)
> - [DATETIMEFORMAT](er-functions-datetime-datetimeformat.md#syntax-2)
> - [NUMBERFORMAT](er-functions-text-numberformat.md#syntax-2)
>
> W wersji 10.0.20 i nowszych do formatowania wartości podczas [konwersji PDF](electronic-reporting-destinations.md#OutputConversionToPDF) wygenerowanego dokumentu używane są ustawienia lokalne składników formatu typu **Plik\\Common** i **Plik\\Excel**.

## <a name="translation"></a>Przeliczanie walut

Wymagane etykiety ER można dodać do edytowalnego składnika ER. Po dodaniu etykiety ER można ją przetłumaczyć na dwa sposoby: ręcznie i automatycznie.

### <a name="manual-translation"></a>Tłumaczenie ręczne

Dodanie etykiety ER w [okienku](#TextTranslationPane) **Tłumaczenie tekstu** umożliwia ręczne przetłumaczenie jej na wszystkie języki obsługiwane w bieżącym wystąpieniu Finance. Można wybrać preferowany język w polu **Język** w sekcji **Język systemu** lub **Język użytkownika**, wprowadzić odpowiedni tekst w odpowiednim polu **Przetłumaczony tekst**, a następnie wybrać opcję **Przetłumacz**. Ten proces należy powtórzyć dla każdego wymaganego języka i każdej dodawanej etykiety.

### <a name="automatic-translation"></a>Tłumaczenie automatyczne

Konfigurację składnika ER należy wykonać w wersji roboczej konfiguracji ER, w której znajduje się składnik edytowalny ER.

![Strona konfiguracji ER zapewnia dostęp do wersji konfiguracji w wersji roboczej.](./media/er-multilingual-labels-configurations.png)

Jak opisano wcześniej w tym temacie, można dodać wymagane etykiety ER do edytowalnego składnika ER. W ten sposób można określić tekst etykiet ER w języku EN-US. Następnie można wyeksportować etykiety składnika ER za pomocą wbudowanej funkcji ER. Wybierz wersję roboczą konfiguracji ER, która zawiera edytowalny składnik ER, a następnie wybierz **Wymiana \> Eksportuj etykiety**.

![Strona konfiguracji ER umożliwiająca eksportowanie etykiet ER z wybranej wersji konfiguracji.](./media/er-multilingual-labels-export.png)

Można eksportować albo wszystkie etykiety, albo etykiety dla jednego języka, który jest określony na początku eksportu. Etykiety są eksportowane jako plik zip zawierający pliki XML. Każdy plik XML zawiera etykiety dla jednego języka.

![Przykład wyeksportowanego pliku zawierającego etykiety ER dla języka DE-AT.](./media/er-multilingual-labels-in-xml.png)

Ten format jest używany do automatycznego tłumaczenia etykiet za pomocą usług tłumaczenia zewnętrznego, takich jak [Dynamics 365 Translation Service](../lifecycle-services/translation-service-overview.md). Po odebraniu przetłumaczonych etykiet można je zaimportować z powrotem do wersji roboczej konfiguracji ER, która zawiera składniki odnoszące się do tych etykiet. Wybierz wersję roboczą konfiguracji ER, która zawiera edytowalny składnik ER, a następnie wybierz **Wymiana \> Załaduj etykiety**.

![Strona konfiguracji ER umożliwiająca importowanie etykiet ER do wybranej wersji konfiguracji.](./media/er-multilingual-labels-load.png)

Przetłumaczone etykiety zostaną zaimportowane do wybranej konfiguracji ER. Przetłumaczone etykiety istniejące w tej konfiguracji ER są zastępowane. Jeśli w konfiguracji ER nie ma żadnej przetłumaczonej etykiety, zostanie ona dołączona.

## <a name="lifecycle"></a>Cykl życia

Etykiety składnika ER, które mogą być edytowane, są zachowywane wraz z inną zawartością składnika, w odpowiedniej wersji konfiguracji ER.

Etykiety podstawowego składnika ER można odwoływać w wersji pochodnej składnika ER tworzonego w celu wprowadzenia modyfikacji.

Wersja ER kontroluje przypisywanie etykiet do dowolnego atrybutu w składniku ER. Zmiany w przypisaniu etykiety są rejestrowane na liście zmian (delta) edytowalnego składnika ER, który został utworzony jako pochodna wersja dostarczonego składnika ER. Te zmiany zostaną sprawdzone, gdy wersja pochodna zostanie zmieniona na nową wersję bazową.

## <a name="functions"></a>Funkcje

Wbudowana funkcja ER [LISTOFFIELDS](er-functions-list-listoffields.md) może uzyskiwać dostęp do etykiet ER skonfigurowanych dla niektórych elementów składników ER.

Zgodnie z opisem opisanym wcześniej w tym temacie atrybuty **Etykieta** i **Opis** dla wartości wszystkich [modeli](#LinkModelEnum) lub [formatów](#LinkFormatEnum) ER wartości wyliczania można połączyć z etykietą ER dostępną w odpowiednim składniku ER. Istnieje możliwość skonfigurowania wyrażenia ER, w którym wywoływana jest funkcja **LISTOFFIELDS** przy użyciu wyliczenia ER jako argumentu. To wyrażenie zwraca listę zawierającą rekord dla każdej wartości wyliczenia ER, który został zdefiniowany jako argument tej funkcji. Każdy rekord zawiera wartość etykiety ER, która jest połączona z wartością wyliczenia ER:

- Wartość etykiety ER połączona z atrybutami **Etykiety** jest przechowywana w polu **Etykieta** zwróconego rekordu.
- Wartość etykiety ER połączona z atrybutami **Opisu** jest przechowywana w polu **Opis** zwróconego rekordu.

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Raportowanie elektroniczne — omówienie](general-electronic-reporting.md)
- [Funkcje raportowania elektronicznego](er-formula-language.md#functions)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
