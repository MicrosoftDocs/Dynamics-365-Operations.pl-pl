---
title: Osadzone aplikacje kanwy z Power Apps
description: W tym artykule opisano sposób osadzania aplikacji kanwy z Microsoft Power Apps na kliencie w celu rozszerzenia funkcjonalności produktu.
author: jasongre
ms.date: 09/13/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: FormRunConfigurationAddPAControl, FormRunConfigurationEditPAControl
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2018-02-28
ms.dyn365.ops.version: Platform update 14
ms.openlocfilehash: d7dc45e56c5fa616c288ebb4b919f039b7358794
ms.sourcegitcommit: 873d66c03a51ecb7082e269f30f5f980ccd9307f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/06/2022
ms.locfileid: "9123663"
---
# <a name="embed-canvas-apps-from-power-apps"></a>Osadzone aplikacje kanwy z Power Apps

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

Usługa Microsoft Power Apps to usługa, która umożliwia deweloperom i użytkownikom nietechnicznym tworzenie niestandardowych aplikacji biznesowych dla urządzeń przenośnych, tabletów i sieci Web bez pisania kodu. Aplikacje finansowe i operacyjne wspierają integrację z Power Apps. Aplikacje kanwy, które tworzysz Ty, Twoja organizacja lub szerszy ekosystem, można osadzać w aplikacjach finansowych i operacyjnych, aby zwiększyć funkcjonalność produktu. Na przykład można utworzyć aplikację kanwy Power Apps celem uzupełnienia aplikacji finansowych i operacyjnych o informacje pobrane z innego systemu.

Aby uzyskać więcej informacji o osadzaniu aplikacji kanwy, obejrzyj krótki film [Jak osadzać aplikacje kanwy](https://www.youtube.com/watch?v=x3qyA1bH-NY).

## <a name="adding-an-embedded-canvas-app-from-power-apps-to-a-page"></a>Dodawanie osadzonej aplikacji kanwy Power Apps do strony

Przed osadzeniem aplikacji kanwy z Power Apps w kliencie musisz znaleźć lub skompilować aplikację, która ma żądane wizualizacje lub funkcje. Ten artykuł nie zawiera szczegółowego opisu procesu kompilowania aplikacji. Jeśli jesteś nowym użytkownikiem Power Apps, zajrzyj do [dokumentacja Power Apps](/powerapps/).

Istnieją trzy sposoby osadzania aplikacji kanwy w aplikacji finansowych i operacyjnych. Możesz użyć podejścia, które najlepiej pasuje do danego scenariusza. 

- Osadzanie aplikacji kanwy w przycisku **Power Apps** w standardowym okienku akcji strony. Aplikacje dodawane w ten sposób są wyświetlane jako elementy w przycisku menu **Power Apps**, a aplikacje otwierane są w okienkach bocznych. 
- Osadzanie aplikacji kanwy bezpośrednio na istniejącej stronie jako nowej karty (karta przestawna, karta skrócona, blok albo sekcja obszaru roboczego).
- Tworzenie nowego środowiska na pełnej stronie dla aplikacji kanwy z pulpitu nawigacyjnego.

Podczas konfigurowania osadzonej aplikacji kanwy, można wybrać jedno pole, którego zawartość ma być wysyłana jako dane kontekstualne do aplikacji. Ten krok umożliwia aplikacji reagowanie na podstawie aktualnie wyświetlanych danych.

> [!NOTE]
> Nie można stosować tego mechanizmu do osadzania aplikacji oparta na modelu.

### <a name="embedding-a-canvas-app-on-an-existing-page"></a>Osadzanie aplikacji kanwy na istniejącej stronie

W następującej procedurze pokazano sposób osadzania aplikacji kanwy na istniejącej stronie z Power Apps.

1. Przejdź do strony, w której chcesz osadzić aplikację kanwy. Ta strona będzie zawierała wszelkie dane, które należy przekazać do aplikacji jako dane wejściowe.
2. Otwórz okno **Dodawanie aplikacji z Power Apps**:

    - Jeśli aplikacja będzie osadzana bezpośrednio na stronie, wybierz pozycje **Opcje** \> **Spersonalizuj tę stronę** \> **Więcej**, a następnie wykonaj jedną z poniższych czynności:

        - Jeśli funkcja **Aplikacje dla całej strony** jest włączona, wybierz opcję **Dodaj stronę**, a następnie wybierz region, w którym chcesz dodać aplikację. Aby osadzić aplikację w przycisku menu **Power Apps**, wybierz okienko akcji. Jeśli osadzasz aplikację na stronie, wybierz odpowiednią kartę, kartę skróconą, blok lub sekcję (jeśli pracujesz w obszarze roboczym). Następnie w okienku **Dodawanie aplikacji** wybierz pozycję **Power Apps**.
        - Jeśli funkcja **Aplikacje dla całej strony** jest wyłączona, wybierz opcję **Dodaj aplikację z Power Apps** stronę, a następnie wybierz region, w którym chcesz dodać aplikację. Aby osadzić aplikację w przycisku menu **Power Apps**, wybierz okienko akcji. Jeśli osadzasz aplikację na stronie, wybierz odpowiednią kartę, kartę skróconą, blok lub sekcję (jeśli pracujesz w obszarze roboczym).

    - Jeśli dostęp do aplikacji będzie uzyskiwany przy użyciu przycisku menu **Power Apps**, można również kliknąć przycisk menu **Power Apps** w standardowym okienku akcji, a następnie wybrać opcję **Dodaj aplikację**.

3. Skonfiguruj osadzoną aplikację. Więcej informacji znajduje się w sekcji [Konfigurowanie aplikacji kanwy](#configuring-a-canvas-app) w tym artykule.
4. Po potwierdzeniu poprawności konfiguracji wybierz pozycję **Wstaw**.

    - Jeśli funkcja **Zapisane widoki** jest wyłączona, wyświetlany jest monit o odświeżenie przeglądarki w celu wyświetlenia osadzonej aplikacji.
    - Jeśli funkcja **Zapisane widoki** jest włączona, należy zapisać widok, aby zmiany zostały utrwalone.

### <a name="embedding-a-canvas-app-as-a-full-page-experience-from-the-dashboard"></a>Osadzanie aplikacji kanwy jako środowiska na pełnej stronie z pulpitu nawigacyjnego

Aplikację kanwy można chcieć osadzić z pulpitu nawigacyjnego, jeśli nie jest ona powiązana z istniejącą stroną lub chcesz, aby była ona wyświetlana jako środowisko na pełnej stronie w obrębie aplikacji finansowych i operacyjnych.

> [!NOTE]
> Jest to możliwe pod warunkiem włączenia funkcji **Aplikacje dla całej strony** w zarządzaniu funkcjami. 

1. Otwórz pulpit nawigacyjny.
2. Wybierz i przytrzymaj stronę (lub kliknij ją prawym przyciskiem myszy), wybierz opcję **Personalizuj**, a następnie wybierz polecenie **Dodaj stronę**.
3. W okienku **Dodawanie strony** wybierz opcję **Power Apps**.
4. Skonfiguruj osadzoną aplikację. Więcej informacji znajduje się w sekcji [Konfigurowanie aplikacji kanwy](#configuring-a-canvas-app) w tym artykule.
5. Wybierz przycisk **Zapisz**, aby dodać aplikację do pulpitu nawigacyjnego jako nowy kafelek.
6. Wybierz nowy kafelek na pulpicie nawigacyjnym i potwierdź, że aplikacja kanwy jest wyświetlana zgodnie z oczekiwaniami.

### <a name="configuring-a-canvas-app"></a>Konfigurowanie aplikacji kanwy

Osadzając aplikację kanwy, należy ustawić następujące parametry:

- **Nazwa** — umożliwia wprowadzenie tekstu, który ma być wyświetlany na przycisku lub karcie zawierającej osadzoną aplikację. Zazwyczaj w tym polu jest ponownie wpisywana nazwa aplikacji.
- **Identyfikator aplikacji** — wskazuje unikatowy identyfikator globalny (GUID) aplikacji obszaru roboczego, która ma zostać osadzona. Aby pobrać tę wartość, odszukaj aplikację na stronie [make.powerapps.com](https://make.powerapps.com), a następnie odszukaj pole **Identyfikator aplikacji** w obszarze **Szczegóły**.
- **Dane wejściowe dla aplikacji** — opcjonalnie można wybrać pole zawierające dane, które mają być przekazywane do aplikacji jako dane wejściowe. Informacje o tym, jak aplikacja może korzystać z danych przesyłanych z aplikacji finansowych i operacyjnych, znajdziesz w rozdziale [Budowanie aplikacji wykorzystującej dane przesyłane z aplikacji finansowych i operacyjnych](#building-a-canvas-app-that-uses-data-that-is-sent-from-finance-and-operations-apps) w dalszej części artykułu.

    Począwszy od wersji 10.0.19 bieżąca firma będzie również przekazywana jako kontekst do aplikacji kanwy za pośrednictwem parametru URL **cmp**. To zachowanie nie będzie miało wpływu na docelową aplikację kanwy, dopóki ta aplikacja nie użyje tych informacji.

- **Rozmiar aplikacji** — wybór typu osadzanej aplikacji. Wybierz opcję **Ograniczona** w przypadku aplikacji przeznaczonych do urządzeń przenośnych lub opcję **Rozbudowana** w przypadku aplikacji przeznaczonych do tabletów. Ten parametr gwarantuje przeznaczenie wystarczającej ilości miejsca na wbudowaną aplikację.
- **Firmy** — można wybrać firmy, dla których aplikacja ma być dostępna. Domyślnie aplikacja jest dostępna dla wszystkich firm. Ta opcja jest dostępna tylko wtedy, gdy osadzasz aplikację bezpośrednio na istniejącej stronie i funkcja **[Zapisane widoki](saved-views.md)** jest wyłączona.

## <a name="sharing-an-embedded-app"></a>Udostępnianie osadzonej aplikacji

Po osadzeniu aplikacji kanwy na stronie i potwierdzeniu, że działa ona poprawnie, możesz chcieć udostępnić aplikację innym użytkownikom w systemie. Aby udostępnić osadzoną aplikację kanwy, wykonaj następujące kroki.

1. [Udostępnij aplikację kanwy w Power Apps](/powerapps/maker/canvas-apps/share-app) odpowiednim użytkownikom, aby mogli oni uzyskać dostęp do aplikacji bezpośrednio w Power Apps.
2. Udostępnij personalizacje skojarzone z osadzoną aplikacją żądanym użytkownikom. Możesz użyć jednej z następujących metod:

    - **Publikowanie widoku (zalecane):** Jeśli funkcja **[Zapisane widoki](saved-views.md)** jest włączona, zalecanym i preferowanym podejściem jest utworzenie widoku, który zawiera osadzoną aplikację kanwy, a następnie opublikowanie tego widoku dla żądanych użytkowników. Dzięki temu wszyscy użytkownicy, którzy mają role zabezpieczeń ukierunkowane na widok opublikowany, będą widzieli aplikację kanwy na stronie.

        Możesz również opublikować aplikację kanwy, która została osadzona jako środowisko na całej stronie, z pulpitu nawigacyjnego. Na pulpicie nawigacyjnym wybierz i przytrzymaj (lub kliknij prawym przyciskiem myszy) kafelek skojarzony z aplikacją, wybierz opcję **Personalizuj**, a następnie wybierz pozycję **Publikuj stronę**. Jest wyświetlane środowisko przypominające środowisko *Publikowanie widoków* i możliwe jest wybranie ról zabezpieczeń, dla których zostanie ono opublikowane. W wersji 10.0.21 i nowszych, jeśli jest włączona funkcja **Usprawniona obsługa zapisanych widoków dla firmy** można także opublikować aplikację dla żądanych firm.

    - Jeśli funkcja **Zapisane widoki** jest wyłączona, administrator systemu może przekazać personalizację, która zawiera aplikację kanwy, odpowiedniemu zestawowi użytkowników, korzystając ze strony **Personalizacja**. Można również wyeksportować personalizacje strony i wysłać je do jednego lub kilku użytkowników. Każdy z tych użytkowników może następnie zaimportować personalizację. Pasek narzędzi personalizacji zawiera przyciski umożliwiające eksportowanie i importowanie personalizacji.

> [!NOTE]
> Jeśli aplikacja kanwy została udostępniona użytkownikom zewnętrznym, użytkownicy ci nie mogą skorzystać z aplikacji osadzonej w aplikacjach finansowych i operacyjnych. Użytkownicy mogą jednak uzyskać dostęp do aplikacji bezpośrednio w Power Apps. Użytkownicy zewnętrzni to goście i użytkownicy, którzy nie należą do katalogu Microsoft 365 Azure, gdzie aplikacja finansowa i operacyjna jest wdrożona.

Temat [Personalizowanie środowiska użytkownika](personalize-user-experience.md) zawiera więcej informacji o funkcjach personalizacji w produkcie oraz o sposobach ich używania.

## <a name="building-a-canvas-app-that-uses-data-that-is-sent-from-finance-and-operations-apps"></a>Budowanie aplikacji kanwy, która korzysta z danych wysyłanych z aplikacji finansowych i operacyjnych

Podczas tworzenia aplikacji kanwy, która zostanie osadzona w aplikacjach finansowych i operacyjnych, ważną częścią procesu jest użycie danych wejściowych z tej aplikacji finansowej i operacyjnej. Ze środowiska programistycznego Power Apps można uzyskać dostęp do danych wejściowych przekazywanych z poziomu aplikacji finansowych i operacyjnych za pomocą zmiennej **Param("EntityId")**. Ponadto, Począwszy od wersji 10.0.19 bieżąca osoba prawna będzie również przekazywana do aplikacji kanwy za pośrednictwem zmiennej **Param(cmp)**. 

Na przykład w funkcji OnStart wewnątrz aplikacji można ustawić dane wejściowe z aplikacji finansowych i operacyjnych w następujący sposób:

``` Power Apps
If(!IsBlank(Param("EntityId")), Set(FinOpsInput, Param("EntityId")), Set(FinOpsInput, ""));

If(!IsBlank(Param("cmp")), Set(FinOpsLegalEntity, Param("cmp")), Set(FinOpsLegalEntity, ""));
```

## <a name="viewing-a-canvas-app"></a>Wyświetlanie aplikacji kanwy

Aby wyświetlić osadzoną aplikację kanwy na stronie aplikacji finansowych i operacyjnych, po prostu przejdź do strony z osadzoną aplikacją. Pamiętaj, że dostęp do aplikacji można uzyskać za pomocą przycisku **Power Apps** w standardowym okienku akcji. Alternatywnie mogą być wyświetlane bezpośrednio na stronie w postaci nowej karty lub karty skróconej, lub bloku, lub nowej sekcji w obszarze roboczym. Podczas pierwszej próby załadowania aplikacji na stronie przez użytkowników zostanie wyświetlony monit o zalogowanie się. Ten krok gwarantuje, że użytkownicy mają odpowiednie uprawnienia do korzystania z aplikacji.

## <a name="editing-an-embedded-app"></a>Edytowanie osadzonej aplikacji

Po osadzeniu aplikacji na stronie może być konieczne wprowadzenie pewnych zmian w konfiguracji tej aplikacji. Na przykład prawdopodobnie zechcesz zmodyfikować etykietę skojarzoną z osadzoną aplikacją lub też utworzono nową wersję aplikacji i trzeba zaktualizować identyfikator aplikacji, tak aby wskazywał najnowszą wersję.

Wykonaj następujące czynności, aby edytować konfigurację osadzonej aplikacji:

1. Przejdź do okienka **Edytuj aplikację**.

    - Jeśli dostęp do osadzonej aplikacji uzyskuje się za pośrednictwem przycisku menu Power Apps, naciśnij i przytrzymaj (lub kliknij prawym przyciskiem myszy) przycisk menu Power Apps i wybierz polecenie **Personalizuj**. Z menu rozwijanego **Wybierz aplikację** wybierz alpikację, którą chcesz skonfigurować.
    - Jeśli osadzona aplikacja pojawia się bezpośrednio na stronie, kliknij przycisk **Opcje**, a następnie wybierz opcję **Personalizuj tę stronę**. Za pomocą narzędzia **Wybierz** kliknij osadzoną aplikację.
    - Jeśli osadzona aplikacja została dodana z pulpitu nawigacyjnego, otwórz pulpit nawigacyjny, wybierz i przytrzymaj (lub kliknij prawym przyciskiem myszy) kafelek skojarzony z aplikacją kanwy, wybierz opcję **Personalizuj**, a następnie wybierz pozycję **Edytuj stronę**.

2. Wprowadź wymagane modyfikacje w konfiguracji aplikacji, a następnie kliknij przycisk **Zapisz**.

## <a name="removing-an-app"></a>Usuwanie aplikacji

Po osadzeniu aplikacji na stronie istnieją różne sposoby jej usunięcia w razie potrzeby:

- Przejdź do okienka **Edytuj aplikację** przy użyciu instrukcji zawartych w sekcji [Edytowanie osadzonej aplikacji](#editing-an-embedded-app) wcześniej w tym artykule. Upewnij się, że w okienku są wyświetlane informacje dotyczące osadzonej aplikacji, którą chcesz usunąć, a następnie kliknij przycisk **Usuń**.
- Jeśli osadzona aplikacja została dodana z pulpitu nawigacyjnego, otwórz pulpit nawigacyjny, wybierz i przytrzymaj (lub kliknij prawym przyciskiem myszy) kafelek skojarzony z aplikacją kanwy, wybierz opcję **Personalizuj**, a następnie wybierz pozycję **Usuń stronę**. 
- Ponieważ osadzona aplikacja jest zapisywana jako dane personalizacji, wyczyszczenie personalizacji strony spowoduje również usunięcie wszelkich osadzonych aplikacji znajdujących się na tej stronie. Należy zauważyć, że wyczyszczenie personalizacji strony jest trwałe i nie można go cofnąć. Aby usunąć personalizacje ze strony, kliknij przycisk **Opcje**, a następnie wybierz opcję **Personalizuj tę stronę** a następnie przycisk **Wyczyść**. Po odświeżeniu przeglądarki wszystkie poprzednie personalizacje tej strony zostaną usunięte. W temacie [Personalizuj środowiska użytkownika](personalize-user-experience.md) znajdziesz więcej informacji o optymalizowaniu stron za pomocą personalizacji.

## <a name="appendix"></a>Dodatek

### <a name="developer-modeling-a-canvas-app-on-a-form"></a>[Deweloper] Modelowanie aplikacji kanwy w formularzu

Chociaż ten artykuł dotyczy osadzania aplikacji kanwy poprzez personalizację, deweloperzy mogą również dodać do formularza aplikację kanwy, korzystając ze środowiska projektowania Visual Studio. W tym celu dodaj po prostu formant powerAppsHostControl do formularza. Właściwości metadanych dostępne w formancie zapewniają te same możliwości, co funkcje personalizacji.

### <a name="developer-specifying-where-an-app-can-be-embedded"></a>[Deweloper] Określanie, gdzie można osadzić aplikację

Domyślnie użytkownicy mogą osadzać aplikacje na każdej stronie, używając do tego przycisku menu Power Apps lub bezpośrednio na stronie w postaci karty, karty skróconej, bloku lub nowej sekcji w obszarze roboczym. Jednak w razie potrzeby deweloperzy mogą również skonfigurować tę funkcję tak, aby zezwalać na osadzanie aplikacji tylko na niektórych stronach; służą do tego następujące metody:

- **isPowerAppPersonalizationEnabled** — jeśli ta metoda zwraca wartość false dla określonej strony, to przycisk menu Power Apps nie będzie wyświetlany, a użytkownicy nie będą mogli osadzać aplikacji nigdzie na tej stronie, w tym w postaci karty.
- **isPowerAppTabPersonalizationEnabled** — jeśli ta metoda zwraca wartość false dla określonej strony, to użytkownicy nie będą mogli osadzać aplikacji PowerApps bezpośrednio na stronie w postaci karty, skróconej karty ani sekcji panoramy. Użytkownicy nadal będą mogli osadzać aplikacje za pomocą przycisku menu Power Apps, o ile tylko osadzanie jest dozwolone na stronie.

Poniższy przykład przedstawia nową klasę z dwoma metodami potrzebnymi do określenia, gdzie można osadzać aplikacje.

```powerapps
[ExtensionOf(classStr(FormRunConfigurationPowerAppsConfiguration))]

public final class ClassTest_Extension
{
    public static boolean isPowerAppPersonalizationEnabled(str pageName)
    {
        var result = next isPowerAppPersonalizationEnabled(pageName);
        return result;
    }
    
    public static boolean isPowerAppTabPersonalizationEnabled(str pageName)
    {
        var result = next isPowerAppTabPersonalizationEnabled(pageName);
        return result;
    }
}
```

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

