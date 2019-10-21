---
title: Osadzone aplikacje PowerApps
description: W tym temacie opisano sposób osadzania aplikacji PowerApps na kliencie w celu rozszerzenia funkcjonalności produktu.
author: jasongre
manager: AnnBe
ms.date: 09/20/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: FormRunConfigurationAddPAControl, FormRunConfigurationEditPAControl
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations, Core
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2018-02-28
ms.dyn365.ops.version: Platform update 14
ms.openlocfilehash: 37faf2a7a880c384f6f01d06ef5c9f28055d5006
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/27/2019
ms.locfileid: "2191185"
---
# <a name="embed-powerapps-apps"></a>Osadzone aplikacje PowerApps

[!include [banner](../includes/banner.md)]

W aktualizacji platformy 14 jest obsługiwana integracja z Microsoft PowerApps — usługa dla deweloperów i użytkowników nietechnicznych, która umożliwia tworzenie niestandardowych aplikacji biznesowych dla urządzeń przenośnych, tabletów i sieci web bez pisania kodu. Aplikacje PowerApps opracowane przez użytkownika, organizację lub członków szerszego ekosystemu można następnie osadzać w aplikacjach Finance and Operations w celu rozszerzenia funkcjonalności produktu. Na przykład można utworzyć aplikację PowerApp w celu uzupełniania aplikacji Finance and Operations o informacje pobrane z innego systemu.

Aby uzyskać więcej informacji o osadzaniu PowerApps , obejrzyj krótki film [Jak osadzać PowerApps](https://www.youtube.com/watch?v=x3qyA1bH-NY).

## <a name="adding-an-embedded-powerapp-to-a-page"></a>Dodawanie osadzonej aplikacji PowerApp do strony

### <a name="overview"></a>Przegląd

Przed osadzeniem aplikacji PowerApp w kliencie najpierw należy odnaleźć lub utworzyć aplikację PowerApp z żądanymi elementami wizualnymi i/lub funkcjami. Tutaj nie opiszemy szczegółowego procesu kompilowania aplikacji PowerApp . Temat [Wprowadzenie do PowerApps](https://docs.microsoft.com/powerapps/getting-started) jest dobrym punktem wyjściowym dla nowych użytkowników PowerApps.

Gdy masz wszystko gotowe do rozpoczęcia osadzania konkretnej aplikacji PowerApp, możesz wybrać jeden z dwóch sposobów dostępu do aplikacji PowerApp na stronie — zależnie od tego, który scenariusz lepiej Ci pasuje. Pierwszy sposób to użycie przycisku PowerApps, który został dodany do standardowego okienka akcji. Aplikacje PowerApps dodane za pomocą tego mechanizmu będą wyświetlane jako elementy menu wewnątrz przycisku menu PowerApps. Wybranie elementu menu spowoduje otwarcie okienka bocznego zawierającego odpowiednią osadzoną aplikację PowerApp. Alternatywnie można wybrać wyświetlanie aplikacji PowerApp bezpośrednio na stronie w postaci nowej karty, karty skróconej, bloku lub nowej sekcji w obszarze roboczym.

Podczas konfigurowania osadzonej aplikacji PowerApp można wybrać jedno pole, którego zawartość ma być wysyłana jako dane wejściowe do aplikacji PowerApp. Dzięki temu aplikacja PowerApp może reagować na podstawie danych obecnie wyświetlanych.

### <a name="details"></a>Szczegóły

Poniższe instrukcje przedstawiają sposoby osadzania aplikacji PowerApp w kliencie internetowym.

1. Przejdź do strony, w której chcesz osadzić aplikację PowerApp. Jest to ta sama strona, która zawiera wszelkie dane, jakie muszą zostać przekazane do aplikacji PowerApp jako dane wejściowe.
2. Otwórz okienko **Wstaw aplikację PowerApp**:

    - Kliknij przycisk **Opcje**, a następnie wybierz opcję **Personalizuj ten formularz**. W menu **Wstaw** wybierz polecenie **PowerApp**. Na koniec wybierz region, w którym chcesz dodać aplikację PowerApp. Jeśli chcesz osadzić aplikację PowerApp w przycisku menu PowerApps, wybierz okienko akcji. Jeśli chcesz osadzić aplikację PowerApp bezpośrednio na stronie, wybierz odpowiednią kartę, kartę skróconą, blok lub sekcję (jeśli pracujesz w obszarze roboczym).
    - Jeśli dostęp do aplikacji PowerApp będzie uzyskiwany przy użyciu przycisku menu PowerApps, można również kliknąć przycisk menu **PowerApps** w standardowym okienku akcji, a następnie wybrać opcję **Wstaw aplikację PowerApp**.

3. Konfigurowanie osadzonej aplikacji PowerApp:

    - Pole **Nazwa** wskazuje tekst, jaki będzie wyświetlany na przycisku lub karcie zawierającej osadzoną aplikację PowerApp. Często w tym polu warto powtórzyć nazwę aplikacji PowerApp.
    - **Identyfikator aplikacji** to identyfikator GUID aplikacji PowerApp, która ma być osadzona. Aby pobrać tę wartość, odszukaj aplikację PowerApp na stronie [web.powerapps.com](https://web.powerapps.com), a następnie odszukaj pole **Identyfikator aplikacji** w obszarze **Szczegóły**.
    - W obszarze **Dane wejściowe dla aplikacji PowerApp** można opcjonalnie wybrać pole zawierające dane, które mają być przekazywane do aplikacji PowerApp jako dane wejściowe. Zobacz w dalszej części tego tematu sekcję zatytułowaną [Kompilowanie aplikacji PowerApp wykorzystującej dane z aplikacji Finance and Operations](#building-a-powerapp-that-leverages-data-sent-from-finance-and-operations-apps), gdzie dowiesz się dokładnie, jak aplikacja PowerApp może uzyskiwać dostęp do danych wysyłanych z aplikacji Finance and Operations.
    - Wybierz wartość **Rozmiar aplikacji** pasującą do typu osadzanej aplikacji PowerApp. Wybierz opcję **Ograniczona** dla PowerApps przeznaczonych na urządzenia przenośne, a opcję **Rozbudowana** dla PowerApps przeznaczonych na tablety. To zagwarantuje przeznaczenie wystarczającej ilości miejsca na wbudowaną aplikację PowerApp.
    - Na skróconej karcie **Firmy** można wybrać firmy, dla których aplikacja PowerApp będzie dostępna. Domyślnie aplikacja PowerApp jest wyświetlana we wszystkich firmach.

4. Po potwierdzeniu, że konfiguracja jest poprawna, kliknij przycisk **Wstaw**, co spowoduje osadzenie aplikacji PowerApp na stronie. Zobaczysz monit o odświeżenie przeglądarki, aby zobaczyć osadzoną aplikację PowerApp.

## <a name="sharing-an-embedded-powerapp"></a>Udostępnianie osadzonej aplikacji PowerApp

Po osadzeniu aplikacji PowerApp na stronie i sprawdzeniu, że działa poprawnie z każdym kontekstem danych przekazanym ze strony, można udostępnić osadzoną aplikację PowerApp innym użytkownikom w systemie. Można to zrobić na dwa różne sposoby przy użyciu funkcji personalizacji produktu:

- Zalecanym scenariuszem jest skorzystanie z pośrednictwa administratora systemu, który może rozesłać personalizację do wszystkich użytkowników lub tylko do grupy użytkowników.
- Alternatywnie można wyeksportować personalizacje strony, wysłać je do jednego lub więcej użytkowników, a następnie polecić użytkownikom, aby zaimportowali zmiany. Opcja Zarządzaj umieszczona na pasku narzędzi personalizacji umożliwia eksportowanie i importowanie personalizacji.

Temat [Personalizowanie środowiska użytkownika](personalize-user-experience.md) zawiera więcej informacji o funkcjach personalizacji w produkcie oraz o sposobach ich używania.

## <a name="building-a-powerapp-that-leverages-data-sent-from-finance-and-operations-apps"></a>Kompilowanie aplikacji PowerApp wykorzystującej dane z aplikacji Finance and Operations

Ważną częścią procesu tworzenia aplikacji PowerApp, która zostanie osadzona w aplikacjach Finance and Operations, jest wykorzystywanie danych wejściowych z aplikacji Finance and Operations. Wewnątrz aplikacji PowerApp dostęp do tych danych wejściowych można uzyskać za pomocą zmiennej Param("EntityId").

Na przykład w funkcji OnStart wewnątrz aplikacji PowerApp można ustawić dane wejściowe z aplikacji Finance and Operations w następujący sposób:

```
If(!IsBlank(Param("EntityId")), Set(FinOpsInput, Param("EntityId")), Set(FinOpsInput, ""));
```

## <a name="viewing-an-embedded-powerapp"></a>Wyświetlanie osadzonej aplikacji PowerApp

Aby wyświetlić osadzoną aplikację PowerApp na stronie aplikacji Finance and Operations, po prostu przejdź do strony z osadzoną aplikacją PowerApp. Przypominamy, że dostęp do PowerApps można uzyskać za pomocą przycisku PowerApps w standardowym okienku akcji lub też aplikacje PowerApp mogą być wyświetlane bezpośrednio na stronie jako nowa karta, karta skrócona, blok lub nowa sekcja w obszarze roboczym. Gdy użytkownik po raz pierwszy próbuje załadować aplikację PowerApp na stronie, zobaczy monit o zalogowanie się do PowerApps w celu potwierdzenia, że ma odpowiednie uprawnienia potrzebne do korzystania z aplikacji PowerApp.

## <a name="editing-an-embedded-powerapp"></a>Edytowanie osadzonej aplikacji PowerApp

Po osadzeniu aplikacji PowerApp na stronie może być konieczne wprowadzenie pewnych zmian w konfiguracji tej aplikacji. Na przykład prawdopodobnie zechcesz zmodyfikować etykietę skojarzoną z osadzoną aplikacją PowerApp lub też utworzono nową wersję aplikacji PowerApp i trzeba zaktualizować identyfikatora aplikacji, tak aby wskazywał najnowszą wersję.

Wykonaj następujące czynności, aby edytować konfigurację osadzonej aplikacji PowerApp:

1. Przejdź do okienka **Edytuj aplikację PowerApp**.

    - Jeśli dostęp do osadzonej aplikacji PowerApp uzyskuje się za pośrednictwem przycisk menu PowerApps, kliknij prawym przyciskiem myszy przycisk menu PowerApps i wybierz polecenie **Personalizuj**. Z menu rozwijanego **Wybierz aplikację PowerApp** wybierz aplikację PowerApp, którą chcesz skonfigurować.
    - Jeśli osadzona aplikacja PowerApp pojawia się bezpośrednio na stronie, kliknij przycisk **Opcje**, a następnie wybierz opcję **Personalizuj ten formularz**. Za pomocą narzędzia **Wybierz** kliknij osadzoną aplikację PowerApp.

2. Wprowadź wymagane modyfikacje w konfiguracji PowerApps, a następnie kliknij przycisk **Zapisz**.

## <a name="removing-an-embedded-powerapp"></a>Usuwanie osadzonej aplikacji PowerApp

Po osadzeniu aplikacji PowerApp na stronie istnieją dwa sposoby jej usunięcia w razie potrzeby:

- Przejdź do okienka **Edytuj aplikację PowerApp** przy użyciu instrukcji zawartych w sekcji [Edytowanie osadzonej aplikacji PowerApp](#editing-an-embedded-powerapp) wcześniej w tym temacie. Upewnij się, że w okienku są wyświetlane informacje dotyczące osadzonej aplikacji PowerApp, którą chcesz usunąć, a następnie kliknij przycisk **Usuń**.
- Ponieważ osadzona aplikacja PowerApp jest zapisywana jako dane personalizacji, wyczyszczenie personalizacji strony spowoduje również usunięcie wszelkich osadzonych PowerApps znajdujących się na tej stronie. Należy zauważyć, że wyczyszczenie personalizacji strony jest trwałe i nie można go cofnąć. Aby usunąć personalizacje ze strony, kliknij przycisk **Opcje**, a następnie wybierz opcję **Personalizuj ten formularz**. W menu **Zarządzaj** naciśnij przycisk **Wyczyść**. Po odświeżeniu przeglądarki wszystkie poprzednie personalizacje tej strony zostaną usunięte. W temacie [Personalizowanie środowiska użytkownika](personalize-user-experience.md) znajdziesz więcej informacji o optymalizowaniu stron za pomocą personalizacji.

## <a name="appendix"></a>Dodatek

### <a name="developer-control-over-where-a-powerapp-can-be-embedded"></a>Kontrola dewelopera nad miejscem osadzenia aplikacji PowerApp

Domyślnie użytkownicy mogą osadzać PowerApps na każdej stronie, używając do tego przycisku menu PowerApps lub bezpośrednio na stronie w postaci karty, karty skróconej, bloku lub nowej sekcji w obszarze roboczym. Jednak w razie potrzeby deweloperzy mogą również skonfigurować tę funkcję tak, aby zezwalać na osadzanie PowerApps tylko na niektórych stronach. Służą do tego następujące metody:

- **isPowerAppPersonalizationEnabled** — jeśli ta metoda zwraca wartość false dla określonej strony, to przycisk menu PowerApps nie będzie wyświetlany, a użytkownicy nie będą mogli osadzać PowerApps nigdzie na tej stronie, w tym w postaci karty.
- **isPowerAppTabPersonalizationEnabled** — jeśli ta metoda zwraca wartość false dla określonej strony, to użytkownicy nie będą mogli osadzać PowerApps bezpośrednio na stronie w postaci karty, skróconej karty ani sekcji panoramy. Użytkownicy nadal będą mogli osadzać PowerApps za pomocą przycisku menu PowerApps, o ile tylko osadzanie jest dozwolone na stronie.

Poniższy przykład przedstawia nową klasę z dwoma metodami potrzebnymi do określenia, gdzie można osadzać PowerApps.

```
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
