---
title: Zaawansowany edytor formuł raportów elektronicznych
description: W tym temacie opisano sposób, w jaki można użyć Zaawansowanego edytora formuł w celu skonfigurowania wyrażeń w mapowaniu modelu raportowania elektronicznego (ER) i formatu składników.
author: NickSelin
ms.date: 06/17/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERExpressionDesignerFormula
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-04-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 58d7a936f94e1cd453c904ef6404e0db65083c54235c8420b9cfa561bcde1584
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6714666"
---
# <a name="electronic-reporting-advanced-formula-editor"></a>Zaawansowany edytor formuł raportów elektronicznych

[!include [banner](../includes/banner.md)]

Poza [elektronicznym raportowaniem](general-electronic-reporting.md) [edytor formuł](general-electronic-reporting-formula-designer.md), można stosować zaawansowane edytory formuł elektronicznego raportowania, aby usprawnić proces konfigurowania wyrażeń modułu raportowanie elektroniczne (er). Edytor zaawansowany jest oparty na przeglądarce i obsługiwany przez [Edytor Monaco](https://microsoft.github.io/monaco-editor). W tym temacie opisano najczęściej używane funkcje edytora zaawansowanego:

- [Autoformatowanie kodu](#Autoformatting)
- [IntelliSense](#IntelliSense)
- [Zakończenie kodu](#CodeCompletion)
- [Nawigacja kodu](#CodeNavigation)
- [Tworzenie struktury kodu](#CodeStructuring)
- [Znajdź i zastąp](#FindAndReplace)
- [Wklejanie danych](#DataPasting)
- [Kolorowanie składni](#SyntaxColorization)

## <a name=""></a><a name="ActivateAdvEditor">Uaktywnianie zaawansowanego edytora formuł</a>

Wykonaj poniższe kroki, aby rozpocząć korzystanie z Zaawansowanego edytora formuł w wystąpieniu rozwiązania Microsoft Dynamics 365 Finance.

1.  Otwórz **Administracja organizacji** \> **Elektroniczne raportowanie** \> **Konfiguracje**.
2.  Na stronie **Konfiguracje** w okienku akcji na karcie **Konfiguracje** w grupie **Ustawienia zaawansowane** wybierz opcję **Parametry użytkownika**.
3.  W oknie dialogowym **Parametry użytkownika** w sekcji **Śledzenie wykonywania** określ parametr **Włącz zaawansowany edytor formuł** na wartość **Tak**.

[![Okno dialogowe Parametry użytkownika, zaznaczony parametr Włącz zaawansowany edytor formuł.](./media/ER-AdvEditor-Activate.png)](./media/ER-AdvEditor-Activate.png)

> [!NOTE]
> Należy pamiętać, że ten parametr jest właściwy dla użytkownika i właściwy dla firmy.

Począwszy od wersji 10.0.19 Microsoft Dynamics 365 Finance można kontrolować, co jest domyślnie oferowane w edytorze formuły ER. Wykonaj następujące kroki, aby włączyć zaawansowany edytor formuł dla wszystkich użytkowników i firm w bieżącej instancji Finance.

1.  Otwórzz obszar roboczy **Zarządzanie funkcjami**.
2.  Znajdź i wybierz funkcję **Ustaw zaawansowany edytor formuły ER jako domyślny dla wszystkich użytkowników** na liście, a następnie wybierz opcję **Włącz teraz**.
3.  Wybierz kolejno opcje **Administrowanie organizacją** > **Raportowanie elektroniczne** > **Konfiguracje**.
4.  Na stronie **Konfiguracje** w okienku akcji na karcie **Konfiguracje** w grupie **Ustawienia zaawansowane** wybierz opcję **Parametry użytkownika**.
5.  W oknie dialogowym **Parametry użytkownika** znajdź parametr **Zaawansowanego edytora formuły** i sprawdź, czy ma wartość **Nie**.

[![Okno dialogowe Parametry użytkownika, wyłączony parametr Włącz zaawansowany edytor formuł.](./media/ER-AdvEditor-Activate2.png)](./media/ER-AdvEditor-Activate2.png)

> [!NOTE]
> Wartości parametrów **Włącz edytor formuł zaawansowanych** i **Wyłącz edytor formuł zaawansowanych** są zachowywane oddzielnie dla każdego użytkownika i oferowane w oknie dialogowym **Parametry użytkownika** w zależności od stanu funkcji **Ustaw edytor formuł zaawansowanych ER jako domyślny dla wszystkich użytkowników**.

## <a name=""></a><a name="Autoformatting">Autoformatowanie kodu</a>

Po zapisaniu złożonego wyrażenia składającego się z wielu wierszy kodu, wcięcie nowego wprowadzonego wiersza będzie automatycznie oparte na wcięciach poprzedniego wiersza. Można wybrać wiersze i zmienić wcięcia, wpisując **Tab** lub **kombinację SHIFT+TAB**.

[![Gif edytora formuły ER pokazujący zaznaczanie linii i zmianę wcięcia.](./media/ER-AdvEditor-Indentation.gif)](./media/ER-AdvEditor-Indentation.gif)

Autoformatowanie pozwala na zachowanie całego wyformatowanego wyrażenia, ułatwiając dalszą konserwację i upraszcza zrozumienie skonfigurowanej logiki.

## <a name=""></a><a name="IntelliSense">IntelliSense</a>

Edytor zapewnia uzupełnianie wyrazów ułatwiających pisanie wyrażeń i unikanie literówek. Po rozpoczęciu dodawania nowego tekstu edytor automatycznie udostępnia listę funkcji obsługiwanych w funkcjach ER, które zawierają wprowadzone znaki. Narzędzie IntelliSense można również uruchamiać w dowolnym miejscu skonfigurowanego wyrażenia, naciskając kombinację klawiszy **CTRL+ Spacja**.

[![ER edytor formuły gif pokazujący wyzwalanie IntelliSense.](./media/ER-AdvEditor-Intelisense.gif)](./media/ER-AdvEditor-Intelisense.gif)

## <a name=""></a><a name="CodeCompletion">Zakończenie kodu</a>

Edytor automatycznie umożliwia wykonanie kodu przez:

- Wstawianie nawiasu zamykającego przy wprowadzaniu nawiasu otwierającego, pozostawiając kursor w nawiasach.
- Wstawienie symbolu drugiej oferty, gdy zostanie wprowadzony pierwszy z nich, utrzymując kursor w ofertach.
- Wstawienie drugiego symbolu drugiej oferty, gdy zostanie wprowadzony pierwszy z nich, utrzymując kursor w ofertach.

[![Gif edytora formuł ER pokazujący edytor automatycznie uzupełniający kod.](./media/ER-AdvEditor-CodeCompletion.gif)](./media/ER-AdvEditor-CodeCompletion.gif)

Po wskazaniu wprowadzonego nawiasu, drugi nawias tej pary jest automatycznie wyróżniany w celu przedstawienia obsługiwanej konstrukcji.

## <a name=""></a><a name="CodeNavigation">Nawigacja kodu</a>

Wymagane symbole lub wiersze w wyrażeniu można zlokalizować, wpisując polecenie **Przejdź do** za pomocą palety poleceń lub menu kontekstowego.

Aby na przykład przeskoczyć do wiersza **8**, wykonaj następujące czynności:

- Naciśnij **klawisze CTRL+G**, wprowadź wartość **8**, a następnie naciśnij klawisz **ENTER**

  — lub —

- Naciśnij klawisz **F1**, wpisz **G**, wybierz opcję **Przejdź do wiersza**, wprowadź wartość **8**, a następnie naciśnij klawisz **ENTER**.

[![Gif edytora formuły ER pokazujący, jak lokalizować części wyrażenia za pomocą palety poleceń.](./media/ER-AdvEditor-Goto.gif)](./media/ER-AdvEditor-Goto.gif)

## <a name=""></a><a name="CodeStructuring">Tworzenie struktury kodu</a>

Kod niektórych funkcji, takich [IF](er-functions-logical-if.md) lub [CASE](er-functions-logical-case.md), jest automatycznie uporządkowany. Można rozwijać i zwijać dowolne lub wszystkie regiony składane w tym kodzie w celu zmniejszenia możliwej do edycji części wyrażenia w celu skoncentrowania się na thepiece kodu, który wymaga uwagi użytkownika. W tym celu można użyć polecenia przełącz złóż/rozłóż.

Aby na przykład złożyć wszystkie regiony, należy wykonać następujące czynności:

- Naciśnij klawisze **CTRL+K**

  — lub —

- Naciśnij klawisz **F1**, naciśnij **FO**, wybierz opcję **Złóż wszystko**, a następnie naciśnij klawisz **ENTER**

Aby na przykład rozłożyć wszystkie regiony, należy wykonać następujące czynności:

- Naciśnij klawisze **CTRL+J**

  — lub —
  
- Naciśnij klawisz **F1**, naciśnij **UN**, wybierz opcję **Rozłóż wszystko**, a następnie naciśnij klawisz **ENTER**

[![Edytor formuły ER gif pokazujący rozwijany kod.](./media/ER-AdvEditor-ToggleFold.gif)](./media/ER-AdvEditor-ToggleFold.gif)

## <a name=""></a><a name="FindAndReplace">Znajdź i zastąp</a>

Aby wyszukać wystąpienia określonego tekstu, zaznacz tekst w wyrażeniu i wykonaj następujące czynności:

- Naciśnij klawisze **CTRL+F**, a następnie naciśnij klawisz **F3**, aby znaleźć następne wystąpienie zaznaczonego tekstu, lub naciśnij klawisze **Shift+F3**, aby znaleźć poprzednie wystąpienie.

  — lub —
  
- Naciśnij klawisz **F1**, wpisz **F**, a następnie wybierz żądaną opcję, aby odnaleźć zaznaczony tekst.

Aby zamienić wystąpienia określonego tekstu, zaznacz tekst w wyrażeniu i wykonaj następujące czynności:

- Naciśnij klawisze **CTRL+H**. Wprowadź tekst alternatywny i zaznacz opcję zamiana, aby zastąpić zaznaczony tekst lub wszystkie wystąpienia tego tekstu w bieżącym wyrażeniu.

  — lub —
  
- Naciśnij klawisz **F1**, wpisz **R**, a następnie wybierz żądaną opcję, aby podmienić zaznaczony tekst. Wprowadź tekst alternatywny i zaznacz opcję zamiana, aby zastąpić zaznaczony tekst lub wszystkie wystąpienia tego tekstu w bieżącym wyrażeniu.

Aby zmienić wszystkie wystąpienia określonego tekstu, zaznacz tekst w wyrażeniu i wykonaj następujące czynności:

- Naciśnij klawisze **CTRL+F2**, a następnie wprowadź tekst alternatywny.

  — lub —
  
- Naciśnij klawisz **F1**, wpisz **R**, a następnie wybierz żądaną opcję, aby zmienić zaznaczony tekst. Wpisz tekst alternatywny.

[![Edytor formuły ER gif pokazujący znajdź i zamień.](./media/ER-AdvEditor-Find.gif)](./media/ER-AdvEditor-Find.gif)

## <a name=""></a><a name="DataPasting">Wklejanie źródeł danych i funkcji</a>

Możesz wybrać opcję **Dodaj źródło danych**, która wkleja do bieżącego wyrażenia źródło danych, które jest aktualnie zaznaczone w lewym panelu  **Źródła danych**. Możesz wybrać opcję **Dodaj funkcję**, która wkleja do bieżącego wyrażeniafunkcję, która jest aktualnie zaznaczona w prawym panelu **Funkcje**. Jeśli zostanie użyty Edytor formuł ER, wybrana funkcja lub wybrane źródło danych będzie zawsze wklejane na końcu skonfigurowanego wyrażenia. Jeśli zostanie użyty Zaawansowany edytor formuł ER, wybrana funkcja lub wybrane źródło danych może być wklejone gdziekolwiek w skonfigurowanym wyrażeniu. W celu określenia miejsca, w którym mają być wklejone dane, należy użyć kursora.

[![Edytor formuły ER gif pokazujący dodawanie źródła danych i wklejanie funkcji.](./media/ER-AdvEditor-PasteValue.gif)](./media/ER-AdvEditor-PasteValue.gif)

## <a name=""></a><a name="SyntaxColorization">Kolorowanie składni</a>

Obecnie różne kolory są używane do podświetlania następujących części wyrażeń:

- Tekst w podwójnych nawiasach, który może reprezentować identyfikator etykiety stałej tekstowej.

[![Edytor formuł ER.](./media/ER-AdvEditor-SyntaxColorization.png)](./media/ER-AdvEditor-SyntaxColorization.png)

## <a name="limitations"></a>Ograniczenia

Edytor jest obecnie obsługiwany w następujących przeglądarkach sieci Web:

- Chrome
- Edge
- Firefox
- Opera
- Safari

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Omówienie raportowania elektronicznego (ER)](general-electronic-reporting.md)
- [Projektant formuł w module Raportowanie elektroniczne](general-electronic-reporting-formula-designer.md)
- [Edytor Monaco](https://microsoft.github.io/monaco-editor)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
