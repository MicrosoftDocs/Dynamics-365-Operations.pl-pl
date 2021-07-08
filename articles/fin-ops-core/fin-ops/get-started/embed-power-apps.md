---
title: Osadzone aplikacje kanwy z Power Apps
description: W tym temacie opisano sposób osadzania aplikacji kanwy z Microsoft Power Apps na kliencie w celu rozszerzenia funkcjonalności produktu.
author: jasongre
ms.date: 04/23/2021
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
ms.openlocfilehash: 008344766969561417fef5a66faf2c8f0f88910b
ms.sourcegitcommit: cee7887282d372c756c5c11f76684315f249bba5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/24/2021
ms.locfileid: "6303419"
---
# <a name="embed-canvas-apps-from-power-apps"></a>Osadzone aplikacje kanwy z Power Apps

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

Usługa Microsoft Power Apps to usługa, która umożliwia deweloperom i użytkownikom nietechnicznym tworzenie niestandardowych aplikacji biznesowych dla urządzeń przenośnych, tabletów i sieci Web bez pisania kodu. Aplikacje Finance and Operations obsługują integrację z Power Apps. Aplikacje kanwy, które tworzysz Ty, Twoja organizacja lub szerszy ekosystem, można osadzać w aplikacjach Finance and Operations, aby zwiększyć funkcjonalność produktu. Na przykład można utworzyć aplikację kanwy Power Apps celem uzupełnienia aplikacji Finance and Operations o informacje pobrane z innego systemu.

Aby uzyskać więcej informacji o osadzaniu aplikacji kanwy, obejrzyj krótki film [Jak osadzać aplikacje kanwy](https://www.youtube.com/watch?v=x3qyA1bH-NY).

## <a name="adding-an-embedded-canvas-app-from-power-apps-to-a-page"></a>Dodawanie osadzonej aplikacji kanwy Power Apps do strony

### <a name="overview"></a>Omówienie

Przed osadzeniem aplikacji kanwy z Power Apps w kliencie musisz znaleźć lub skompilować aplikację, która ma żądane wizualizacje lub funkcje. Ten temat nie zawiera szczegółowego opisu procesu kompilowania aplikacji. Jeśli jesteś nowym użytkownikiem Power Apps, zajrzyj do [dokumentacja Power Apps](/powerapps/).

Istnieją dwa sposoby uzyskania dostępu do określonej aplikacji kanwy na stronie, gdy jesteś gotowy do osadzenia aplikacji. W zależności od sytuacji można wybrać lepsze podejście. Pierwszy sposób to użycie przycisku **Power Apps**, który został dodany do standardowego okienka akcji. Aplikacje dodane przy użyciu tej metody są wyświetlane jako elementy na przycisku menu **Power Apps**. Po wybraniu jednego z tych elementów pojawi się panel boczny zawierający osadzoną aplikację. Alternatywnie można wybrać wyświetlanie aplikacji bezpośrednio na stronie w postaci nowej karty, karty skróconej lub bloku lub nowej sekcji w obszarze roboczym.

Podczas konfigurowania osadzonej aplikacji kanwy, można wybrać jedno pole, którego zawartość ma być wysyłana jako dane kontekstualne do aplikacji. Ten krok umożliwia aplikacji reagowanie na podstawie aktualnie wyświetlanych danych.

> [!NOTE]
> Nie można obecnie stosować tego mechanizmu do osadzania aplikacji oparta na modelu.  

### <a name="details"></a>Szczegóły

Poniższa procedura przedstawiaja sposoby osadzania aplikacji kanwy z Power Apps w kliencie internetowym.

1. Przejdź do strony, w której chcesz osadzić aplikację kanwy. Ta strona będzie stroną zawierającą dane, które należy przekazać do aplikacji jako dane wejściowe.
2. Otwórz okno **Dodawanie aplikacji z Power Apps**:

    - Kliknij przycisk **Opcje**, a następnie wybierz opcję **Personalizuj tę stronę**. W menu **Wstaw** wybierz polecenie **Power Apps**. Na koniec wybierz region, w którym chcesz dodać aplikację. Jeśli chcesz osadzić aplikację w przycisku menu Power Apps, wybierz okienko akcji. Jeśli chcesz osadzić aplikację bezpośrednio na stronie, wybierz odpowiednią kartę, kartę skróconą, blok lub sekcję (jeśli pracujesz w obszarze roboczym).
    - Jeśli dostęp do aplikacji będzie uzyskiwany przy użyciu przycisku menu Power Apps, można również kliknąć przycisk menu **Power Apps** w standardowym okienku akcji, a następnie wybrać opcję **Wstaw aplikację**.

3. Konfigurowanie osadzonej aplikacji:

    - Pole **Nazwa** wskazuje tekst, jaki będzie wyświetlany na przycisku lub karcie zawierającej osadzoną aplikację. Często w tym polu warto powtórzyć nazwę aplikacji.
    - Pole **Identyfikator aplikacji** wskazuje unikatowy identyfikator globalny (GUID) dla aplikacji obszaru roboczego, która ma zostać osadzona. Aby pobrać tę wartość, odszukaj aplikację na stronie [make.powerapps.com](https://make.powerapps.com), a następnie odszukaj pole **Identyfikator aplikacji** w obszarze **Szczegóły**.
    - W obszarze **Dane wejściowe dla aplikacji** można opcjonalnie wybrać pole zawierające dane, które mają być przekazywane do aplikacji jako dane wejściowe. Szczegółowy opis uzyskiwania przez aplikację dostępu do danych wysyłanych z aplikacji Finance and Operations znajdują się w sekcji [Budowanie aplikacji, która wykorzystuje dane wysyłane z aplikacji Finance and Operations](#building-a-canvas-app-that-uses-data-that-is-sent-from-finance-and-operations-apps) w dalszej części tego tematu. 
        - Począwszy od wersji 10.0.19 bieżąca osoba prawna będzie również przekazywana jako kontekst do aplikacji kanwy za pośrednictwem parametru URL **cmp**. Nie będzie to miało wpływu na docelową aplikację kanwy, dopóki ta aplikacja nie użyje tych informacji. 
    - Wybierz wartość **Rozmiar aplikacji** pasującą do typu osadzanej aplikacji. Wybierz opcję **Ograniczona** dla aplikacji przeznaczonych do urządzeń przenośnych, a opcję **Rozbudowana** dla aplikacji przeznaczonych do tabletów. To zagwarantuje przeznaczenie wystarczającej ilości miejsca na wbudowaną aplikację.
    - Na skróconej karcie **Firmy** można wybrać firmy, dla których aplikacja będzie dostępna. Domyślnie aplikacja jest wyświetlana we wszystkich firmach. Ta opcja jest dostępna tylko wtedy, gdy jest wyłączona funkcja [Zapisanych widoków](saved-views.md). 

4. Po potwierdzeniu, że konfiguracja jest poprawna, kliknij przycisk **Wstaw**, co spowoduje osadzenie PowerApp na stronie. Zobaczysz monit o odświeżenie przeglądarki, aby zobaczyć osadzoną aplikację.

## <a name="sharing-an-embedded-app"></a>Udostępnianie osadzonej aplikacji

Po osadzeniu aplikacji kanwy na stronie i potwierdzeniu, że działa ona poprawnie z dowolnym kontekstem danych przekazywanym z tej strony, możesz chcieć udostępnić aplikację innym użytkownikom w systemie. Aby udostępnić osadzoną aplikację kanwy, wykonaj następujące kroki.

1. [Udostępnij aplikację kanwy](/powerapps/maker/canvas-apps/share-app) odpowiednim użytkownikom, aby mogli oni uzyskać dostęp do aplikacji w Power Apps. 

2. Upewnij się, że docelowi użytkownicy mają odpowiednie personalizacje, tak aby aplikacja osadzona była wyświetlana, gdy użytkownicy przeglądają tę stronę. Możesz użyć jednej z następujących metod:

    - Zalecane: Aby utworzyć i opublikować widok zawierający osadzoną aplikację, należy skorzystać z funkcji [Zapisane widoki](saved-views.md). Dzięki temu wszyscy użytkownicy, którzy mają role zabezpieczeń, które są ukierunkowane na widok opublikowany, będą widzieli aplikację w aplikacjach Finance and Operations. 
    - Jeśli nie masz włączonej funkcji Zapisane widoki, możesz poprosić administratora systemu o przekazanie personalizacji, która obejmuje osadzoną aplikację, wszystkim użytkownikom lub podzbiorowi użytkowników. Można również wyeksportować personalizacje strony i wysłać je do jednego lub kilku użytkowników. Każdy z tych użytkowników może następnie zaimportować te personalizacje. Opcja Zarządzaj umieszczona na pasku narzędzi personalizacji zawiera działania umożliwiające eksportowanie i importowanie personalizacji. 
    
> [!NOTE]
> Jeśli aplikacja kanwy została udostępniona użytkownikom zewnętrznym, użytkownicy ci nie mogą skorzystać z aplikacji osadzonej w aplikacjach Finance and Operations. Użytkownicy mogą jednak uzyskać dostęp do aplikacji bezpośrednio w Power Apps. Użytkownicy zewnętrzni to goście i użytkownicy, którzy nie należą do katalogu Microsoft 365 Azure, gdzie aplikacja Finance and Operations jest wdrożona.

Temat [Personalizowanie środowiska użytkownika](personalize-user-experience.md) zawiera więcej informacji o funkcjach personalizacji w produkcie oraz o sposobach ich używania.

## <a name="building-a-canvas-app-that-uses-data-that-is-sent-from-finance-and-operations-apps"></a>Budowanie aplikacji kanwy, która korzysta z danych wysyłanych z aplikacji Finance and Operations

Podczas tworzenia aplikacji kanwy, która zostanie osadzona w aplikacji Finance and Operations, ważną częścią procesu jest użycie danych wejściowych z tej aplikacji Finance and Operations. Ze środowiska programistycznego Power Apps można uzyskać dostęp do danych wejściowych przekazywanych z poziomu aplikacji Finance and Operations za pomocą zmiennej **Param("EntityId")**. Ponadto, Począwszy od wersji 10.0.19 bieżąca osoba prawna będzie również przekazywana do aplikacji kanwy za pośrednictwem zmiennej **Param(cmp)**. 

Na przykład w funkcji OnStart wewnątrz aplikacji można ustawić dane wejściowe z aplikacji Finance and Operations w następujący sposób:

``` Power Apps
If(!IsBlank(Param("EntityId")), Set(FinOpsInput, Param("EntityId")), Set(FinOpsInput, ""));

If(!IsBlank(Param("cmp")), Set(FinOpsLegalEntity, Param("cmp")), Set(FinOpsLegalEntity, ""));
```

## <a name="viewing-a-canvas-app"></a>Wyświetlanie aplikacji kanwy

Aby wyświetlić osadzoną aplikację kanwy na stronie Finance and Operations, po prostu przejdź do strony z osadzoną aplikacją. Pamiętaj, że dostęp do aplikacji można uzyskać za pomocą przycisku **Power Apps** w standardowym okienku akcji. Alternatywnie mogą być wyświetlane bezpośrednio na stronie w postaci nowej karty lub karty skróconej, lub bloku, lub nowej sekcji w obszarze roboczym. Podczas pierwszej próby załadowania aplikacji na stronie przez użytkowników zostanie wyświetlony monit o zalogowanie się. Ten krok gwarantuje, że użytkownicy mają odpowiednie uprawnienia do korzystania z aplikacji.

## <a name="editing-an-embedded-app"></a>Edytowanie osadzonej aplikacji

Po osadzeniu aplikacji na stronie może być konieczne wprowadzenie pewnych zmian w konfiguracji tej aplikacji. Na przykład prawdopodobnie zechcesz zmodyfikować etykietę skojarzoną z osadzoną aplikacją lub też utworzono nową wersję aplikacji i trzeba zaktualizować identyfikator aplikacji, tak aby wskazywał najnowszą wersję.

Wykonaj następujące czynności, aby edytować konfigurację osadzonej aplikacji:

1. Przejdź do okienka **Edytuj aplikację**.

    - Jeśli dostęp do osadzonej aplikacji uzyskuje się za pośrednictwem przycisk menu Power Apps, kliknij prawym przyciskiem myszy przycisk menu Power Apps i wybierz polecenie **Personalizuj**. Z menu rozwijanego **Wybierz aplikację** wybierz alpikację, którą chcesz skonfigurować.
    - Jeśli osadzona aplikacja pojawia się bezpośrednio na stronie, kliknij przycisk **Opcje**, a następnie wybierz opcję **Personalizuj tę stronę**. Za pomocą narzędzia **Wybierz** kliknij osadzoną aplikację.

2. Wprowadź wymagane modyfikacje w konfiguracji aplikacji, a następnie kliknij przycisk **Zapisz**.

## <a name="removing-an-app"></a>Usuwanie aplikacji

Po osadzeniu aplikacji na stronie istnieją dwa sposoby jej usunięcia w razie potrzeby:

- Przejdź do okienka **Edytuj aplikację** przy użyciu instrukcji zawartych w sekcji [Edytowanie osadzonej aplikacji](#editing-an-embedded-app) wcześniej w tym temacie. Upewnij się, że w okienku są wyświetlane informacje dotyczące osadzonej aplikacji, którą chcesz usunąć, a następnie kliknij przycisk **Usuń**.
- Ponieważ osadzona aplikacja jest zapisywana jako dane personalizacji, wyczyszczenie personalizacji strony spowoduje również usunięcie wszelkich osadzonych aplikacji znajdujących się na tej stronie. Należy zauważyć, że wyczyszczenie personalizacji strony jest trwałe i nie można go cofnąć. Aby usunąć personalizacje ze strony, kliknij przycisk **Opcje**, a następnie wybierz opcję **Personalizuj tę stronę** a następnie przycisk **Wyczyść**. Po odświeżeniu przeglądarki wszystkie poprzednie personalizacje tej strony zostaną usunięte. W temacie [Personalizuj środowiska użytkownika](personalize-user-experience.md) znajdziesz więcej informacji o optymalizowaniu stron za pomocą personalizacji.

## <a name="appendix"></a>Dodatek

### <a name="developer-modeling-a-canvas-app-on-a-form"></a>[Deweloper] Modelowanie aplikacji kanwy w formularzu

Chociaż ten temat dotyczy osadzania aplikacji kanwy poprzez personalizację, deweloperzy mogą również dodać do formularza aplikację kanwy, korzystając ze środowiska projektowania Visual Studio. W tym celu dodaj po prostu formant powerAppsHostControl do formularza. Właściwości metadanych dostępne w formancie zapewniają te same możliwości, co funkcje personalizacji.


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
