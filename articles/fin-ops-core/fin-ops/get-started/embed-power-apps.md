---
title: Osadzone Power Apps
description: W tym temacie opisano sposób osadzania aplikacji Power Apps na kliencie w celu rozszerzenia funkcjonalności produktu.
author: jasongre
manager: AnnBe
ms.date: 12/02/2019
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
ms.openlocfilehash: 90422a34499dab7302ad7722cf84d40e1815991c
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/12/2020
ms.locfileid: "3042949"
---
# <a name="embed-microsoft-power-apps"></a>Osadzone Microsoft Power Apps

[!include [banner](../includes/banner.md)]

Finance and Operations obsługuje integrację z Microsoft Power Apps — usługą dla deweloperów i użytkowników nietechnicznych, która umożliwia tworzenie niestandardowych aplikacji biznesowych dla urządzeń przenośnych, tabletów i sieci web bez pisania kodu. Aplikacje Power Apps opracowane przez użytkownika, organizację lub członków szerszego ekosystemu można następnie osadzać w aplikacjach Finance and Operations w celu rozszerzenia funkcjonalności produktu. Na przykład można utworzyć aplikację Power Apps celem uzupełnienia aplikacji Finance and Operations o informacje pobrane z innego systemu.

Aby uzyskać więcej informacji o osadzaniu Power Apps , obejrzyj krótki film [Jak osadzać Power Apps](https://www.youtube.com/watch?v=x3qyA1bH-NY).

## <a name="adding-an-embedded-app-from-power-apps-to-a-page"></a>Dodawanie osadzonej aplikacji Power Apps do strony

### <a name="overview"></a>Omówienie

Przed osadzeniem aplikacji Power Apps w kliencie najpierw należy odnaleźć lub utworzyć aplikację z żądanymi elementami wizualnymi i/lub funkcjami. Tutaj nie opiszemy szczegółowego procesu kompilowania aplikacji. Temat [Wprowadzenie do Power Apps](https://docs.microsoft.com/powerapps/getting-started) jest dobrym punktem wyjściowym dla nowych użytkowników Power Apps.

Gdy masz wszystko gotowe do rozpoczęcia osadzania konkretnej aplikacji, możesz wybrać jeden z dwóch sposobów dostępu do aplikacji na stronie — zależnie od tego, który scenariusz lepiej Ci pasuje. Pierwszy sposób to użycie przycisku Power Apps, który został dodany do standardowego okienka akcji. Aplikacje dodane za pomocą tego mechanizmu będą wyświetlane jako elementy menu wewnątrz przycisku menu Power Apps. Wybranie elementu menu spowoduje otwarcie okienka bocznego zawierającego odpowiednią osadzoną aplikację. Alternatywnie można wybrać wyświetlanie aplikacji bezpośrednio na stronie w postaci nowej karty, karty skróconej, bloku lub nowej sekcji w obszarze roboczym.

Podczas konfigurowania osadzonej aplikacji, można wybrać jedno pole, którego zawartość ma być wysyłana jako dane kontekstualne do aplikacji. Dzięki temu aplikacja może reagować na podstawie danych obecnie wyświetlanych.

### <a name="details"></a>Szczegóły

Poniższe instrukcje przedstawiają sposoby osadzania aplikacji Power Apps w kliencie internetowym.

1. Przejdź do strony, w której chcesz osadzić aplikację. Jest to ta sama strona, która zawiera wszelkie dane, jakie muszą zostać przekazane do aplikacji jako dane wejściowe.
2. Otwórz okno **Dodawanie aplikacji z Power Apps**:

    - Kliknij przycisk **Opcje**, a następnie wybierz opcję **Personalizuj tę stronę**. W menu **Wstaw** wybierz polecenie **Power Apps**. Na koniec wybierz region, w którym chcesz dodać aplikację. Jeśli chcesz osadzić aplikację w przycisku menu Power Apps, wybierz okienko akcji. Jeśli chcesz osadzić aplikację bezpośrednio na stronie, wybierz odpowiednią kartę, kartę skróconą, blok lub sekcję (jeśli pracujesz w obszarze roboczym).
    - Jeśli dostęp do aplikacji będzie uzyskiwany przy użyciu przycisku menu Power Apps, można również kliknąć przycisk menu **Power Apps** w standardowym okienku akcji, a następnie wybrać opcję **Wstaw aplikację**.

3. Konfigurowanie osadzonej aplikacji:

    - Pole **Nazwa** wskazuje tekst, jaki będzie wyświetlany na przycisku lub karcie zawierającej osadzoną aplikację. Często w tym polu warto powtórzyć nazwę aplikacji.
    - **Identyfikator aplikacji** to identyfikator GUID aplikacji, która ma być osadzona. Aby pobrać tę wartość, odszukaj aplikację na stronie [web.powerapps.com](https://web.powerapps.com), a następnie odszukaj pole **Identyfikator aplikacji** w obszarze **Szczegóły**.
    - W obszarze **Dane wejściowe dla aplikacji** można opcjonalnie wybrać pole zawierające dane, które mają być przekazywane do aplikacji jako dane wejściowe. Zobacz w dalszej części tego tematu sekcję zatytułowaną [Kompilowanie aplikacji wykorzystującej dane wysłane z aplikacji Finance and Operations](#building-an-app-that-leverages-data-sent-from-finance-and-operations-apps), gdzie dowiesz się dokładnie, jak aplikacja może uzyskiwać dostęp do danych wysyłanych z aplikacji Finance and Operations.
    - Wybierz wartość **Rozmiar aplikacji** pasującą do typu osadzanej aplikacji. Wybierz opcję **Ograniczona** dla aplikacji przeznaczonych do urządzeń przenośnych, a opcję **Rozbudowana** dla aplikacji przeznaczonych do tabletów. To zagwarantuje przeznaczenie wystarczającej ilości miejsca na wbudowaną aplikację.
    - Na skróconej karcie **Firmy** można wybrać firmy, dla których aplikacja będzie dostępna. Domyślnie aplikacja jest wyświetlana we wszystkich firmach. Ta opcja jest dostępna tylko wtedy, gdy jest wyłączona funkcja [Zapisanych widoków](saved-views.md). 

4. Po potwierdzeniu, że konfiguracja jest poprawna, kliknij przycisk **Wstaw**, co spowoduje osadzenie PowerApp na stronie. Zobaczysz monit o odświeżenie przeglądarki, aby zobaczyć osadzoną aplikację.

## <a name="sharing-an-embedded-app"></a>Udostępnianie osadzonej aplikacji

Po osadzeniu aplikacji na stronie i sprawdzeniu, że działa poprawnie z każdym kontekstem danych przekazanym ze strony, można udostępnić osadzoną aplikację innym użytkownikom w systemie. Można to zrobić na dwa różne sposoby przy użyciu funkcji personalizacji produktu:

- Zalecanym scenariuszem jest skorzystanie z pośrednictwa administratora systemu, który może rozesłać personalizację do wszystkich użytkowników lub tylko do grupy użytkowników.
- Alternatywnie można wyeksportować personalizacje strony, wysłać je do jednego lub więcej użytkowników, a następnie polecić użytkownikom, aby zaimportowali zmiany. Opcja Zarządzaj umieszczona na pasku narzędzi personalizacji zawiera działania umożliwiające eksportowanie i importowanie personalizacji.

Temat [Personalizowanie środowiska użytkownika](personalize-user-experience.md) zawiera więcej informacji o funkcjach personalizacji w produkcie oraz o sposobach ich używania.

## <a name="building-an-app-that-leverages-data-sent-from-finance-and-operations-apps"></a>Budowanie aplikacji, która wykorzystuje dane wysyłane z aplikacji Finance and Operations

Ważną częścią tworzenia aplikacji Power Apps, która będzie osadzana w aplikacji Finance and Operations, jest wykorzystanie danych wejściowych z tej aplikacji. Ze środowiska programistycznego Power Apps można uzyskać dostęp do danych wejściowych przekazywanych z poziomu aplikacji Finance and Operations za pomocą zmiennej Param(„EntityId”).

Na przykład w funkcji OnStart wewnątrz aplikacji można ustawić dane wejściowe z aplikacji Finance and Operations w następujący sposób:

```powerapps
If(!IsBlank(Param("EntityId")), Set(FinOpsInput, Param("EntityId")), Set(FinOpsInput, ""));
```

## <a name="viewing-an-app"></a>Wyświetlanie aplikacji

Aby wyświetlić osadzoną aplikację na stronie Finance and Operations, po prostu przejdź do strony z osadzoną aplikacją. Przypominamy, że dostęp do aplikacji można uzyskać za pomocą przycisku Power Apps w standardowym okienku akcji lub też aplikacje mogą być wyświetlane bezpośrednio na stronie jako nowa karta, karta skrócona, blok lub nowa sekcja w obszarze roboczym. Gdy użytkownik po raz pierwszy próbuje załadować aplikację na stronie, zobaczy monit o zalogowanie się w celu potwierdzenia, że ma odpowiednie uprawnienia potrzebne do korzystania z aplikacji.

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

### <a name="developer-control-over-where-an-app-can-be-embedded"></a>Kontrola dewelopera nad miejscem osadzenia aplikacji

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
