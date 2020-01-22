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
ms.openlocfilehash: 8b5e64cb9ba916f9cbd628703394318b4044867b
ms.sourcegitcommit: dc953c316c396c45ddd596e25c2b358e39a95d84
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/02/2019
ms.locfileid: "2870248"
---
# <a name="embed-microsoft-power-apps"></a>Osadzone Microsoft Power Apps

[!include [banner](../includes/banner.md)]

W aktualizacji platformy 14 jest obsługiwana integracja z Microsoft Power Apps — usługa dla deweloperów i użytkowników nietechnicznych, która umożliwia tworzenie niestandardowych aplikacji biznesowych dla urządzeń przenośnych, tabletów i sieci web bez pisania kodu. Aplikacje Power Apps opracowane przez użytkownika, organizację lub członków szerszego ekosystemu można następnie osadzać w aplikacjach Finance and Operations w celu rozszerzenia funkcjonalności produktu. Na przykład można utworzyć PowerApp w celu uzupełniania aplikacji Finance and Operations o informacje pobrane z innego systemu.

Aby uzyskać więcej informacji o osadzaniu Power Apps , obejrzyj krótki film [Jak osadzać Power Apps](https://www.youtube.com/watch?v=x3qyA1bH-NY).

## <a name="adding-an-embedded-power-app-to-a-page"></a>Dodawanie osadzonej PowerApp do strony

### <a name="overview"></a>Przegląd

Przed osadzeniem PowerApp w kliencie najpierw należy odnaleźć lub utworzyć PowerApp z żądanymi elementami wizualnymi i/lub funkcjami. Tutaj nie opiszemy szczegółowego procesu kompilowania PowerApp. Temat [Wprowadzenie do Power Apps](https://docs.microsoft.com/powerapps/getting-started) jest dobrym punktem wyjściowym dla nowych użytkowników Power Apps.

Gdy masz wszystko gotowe do rozpoczęcia osadzania konkretnej PowerApp, możesz wybrać jeden z dwóch sposobów dostępu do PowerApp na stronie — zależnie od tego, który scenariusz lepiej Ci pasuje. Pierwszy sposób to użycie przycisku Power Apps, który został dodany do standardowego okienka akcji. Aplikacje Power Apps dodane za pomocą tego mechanizmu będą wyświetlane jako elementy menu wewnątrz przycisku menu Power Apps. Wybranie elementu menu spowoduje otwarcie okienka bocznego zawierającego odpowiednią osadzoną PowerApp. Alternatywnie można wybrać wyświetlanie PowerApp bezpośrednio na stronie w postaci nowej karty, karty skróconej, bloku lub nowej sekcji w obszarze roboczym.

Podczas konfigurowania osadzonej PowerApp można wybrać jedno pole, którego zawartość ma być wysyłana jako dane wejściowe do PowerApp. Dzięki temu PowerApp może reagować na podstawie danych obecnie wyświetlanych.

### <a name="details"></a>Szczegóły

Poniższe instrukcje przedstawiają sposoby osadzania PowerApp w kliencie internetowym.

1. Przejdź do strony, w której chcesz osadzić PowerApp. Jest to ta sama strona, która zawiera wszelkie dane, jakie muszą zostać przekazane do PowerApp jako dane wejściowe.
2. Otwórz okienko **Wstaw PowerApp**:

    - Kliknij przycisk **Opcje**, a następnie wybierz opcję **Personalizuj ten formularz**. W menu **Wstaw** wybierz polecenie **Power App**. Na koniec wybierz region, w którym chcesz dodać PowerApp. Jeśli chcesz osadzić PowerApp w przycisku menu Power Apps, wybierz okienko akcji. Jeśli chcesz osadzić PowerApp bezpośrednio na stronie, wybierz odpowiednią kartę, kartę skróconą, blok lub sekcję (jeśli pracujesz w obszarze roboczym).
    - Jeśli dostęp do PowerApp będzie uzyskiwany przy użyciu przycisku menu Power Apps, można również kliknąć przycisk menu **Power Apps** w standardowym okienku akcji, a następnie wybrać opcję **Wstaw PowerApp**.

3. Konfigurowanie osadzonej PowerApp:

    - Pole **Nazwa** wskazuje tekst, jaki będzie wyświetlany na przycisku lub karcie zawierającej osadzoną PowerApp. Często w tym polu warto powtórzyć nazwę PowerApp.
    - **Identyfikator aplikacji** to identyfikator GUID PowerApp, która ma być osadzona. Aby pobrać tę wartość, odszukaj PowerApp na stronie [web.powerapps.com](https://web.powerapps.com), a następnie odszukaj pole **Identyfikator aplikacji** w obszarze **Szczegóły**.
    - W obszarze **Dane wejściowe dla PowerApp** można opcjonalnie wybrać pole zawierające dane, które mają być przekazywane do PowerApp jako dane wejściowe. Zobacz w dalszej części tego tematu sekcję zatytułowaną [Kompilowanie PowerApp wykorzystującej dane z aplikacji Finance and Operations](#building-a-power-app-that-leverages-data-sent-from-finance-and-operations-apps), gdzie dowiesz się dokładnie, jak PowerApp może uzyskiwać dostęp do danych wysyłanych z aplikacji Finance and Operations.
    - Wybierz wartość **Rozmiar aplikacji** pasującą do typu osadzanej PowerApp. Wybierz opcję **Ograniczona** dla Power Apps przeznaczonych na urządzenia przenośne, a opcję **Rozbudowana** dla Power Apps przeznaczonych na tablety. To zagwarantuje przeznaczenie wystarczającej ilości miejsca na wbudowaną PowerApp.
    - Na skróconej karcie **Firmy** można wybrać firmy, dla których PowerApp będzie dostępna. Domyślnie PowerApp jest wyświetlana we wszystkich firmach.

4. Po potwierdzeniu, że konfiguracja jest poprawna, kliknij przycisk **Wstaw**, co spowoduje osadzenie PowerApp na stronie. Zobaczysz monit o odświeżenie przeglądarki, aby zobaczyć osadzoną PowerApp.

## <a name="sharing-an-embedded-power-app"></a>Udostępnianie osadzonej PowerApp

Po osadzeniu PowerApp na stronie i sprawdzeniu, że działa poprawnie z każdym kontekstem danych przekazanym ze strony, można udostępnić osadzoną PowerApp innym użytkownikom w systemie. Można to zrobić na dwa różne sposoby przy użyciu funkcji personalizacji produktu:

- Zalecanym scenariuszem jest skorzystanie z pośrednictwa administratora systemu, który może rozesłać personalizację do wszystkich użytkowników lub tylko do grupy użytkowników.
- Alternatywnie można wyeksportować personalizacje strony, wysłać je do jednego lub więcej użytkowników, a następnie polecić użytkownikom, aby zaimportowali zmiany. Opcja Zarządzaj umieszczona na pasku narzędzi personalizacji umożliwia eksportowanie i importowanie personalizacji.

Temat [Personalizowanie środowiska użytkownika](personalize-user-experience.md) zawiera więcej informacji o funkcjach personalizacji w produkcie oraz o sposobach ich używania.

## <a name="building-a-power-app-that-leverages-data-sent-from-finance-and-operations-apps"></a>Kompilowanie PowerApp wykorzystującej dane z aplikacji Finance and Operations

Ważną częścią procesu tworzenia PowerApp, która zostanie osadzona w aplikacjach Finance and Operations, jest wykorzystywanie danych wejściowych z aplikacji Finance and Operations. Wewnątrz PowerApp dostęp do tych danych wejściowych można uzyskać za pomocą zmiennej Param("EntityId").

Na przykład w funkcji OnStart wewnątrz PowerApp można ustawić dane wejściowe z aplikacji Finance and Operations w następujący sposób:

```
If(!IsBlank(Param("EntityId")), Set(FinOpsInput, Param("EntityId")), Set(FinOpsInput, ""));
```

## <a name="viewing-an-embedded-power-app"></a>Wyświetlanie osadzonej PowerApp

Aby wyświetlić osadzoną PowerApp na stronie aplikacji Finance and Operations, po prostu przejdź do strony z osadzoną PowerApp. Przypominamy, że dostęp do Power Apps można uzyskać za pomocą przycisku Power Apps w standardowym okienku akcji lub też aplikacje PowerApp mogą być wyświetlane bezpośrednio na stronie jako nowa karta, karta skrócona, blok lub nowa sekcja w obszarze roboczym. Gdy użytkownik po raz pierwszy próbuje załadować PowerApp na stronie, zobaczy monit o zalogowanie się do Power Apps w celu potwierdzenia, że ma odpowiednie uprawnienia potrzebne do korzystania z PowerApp.

## <a name="editing-an-embedded-power-app"></a>Edytowanie osadzonej PowerApp

Po osadzeniu PowerApp na stronie może być konieczne wprowadzenie pewnych zmian w konfiguracji tej PowerApp. Na przykład prawdopodobnie zechcesz zmodyfikować etykietę skojarzoną z osadzoną PowerApp lub też utworzono nową wersję PowerApp i trzeba zaktualizować identyfikatora PowerApp, tak aby wskazywał najnowszą wersję.

Wykonaj następujące czynności, aby edytować konfigurację osadzonej PowerApp:

1. Przejdź do okienka **Edytuj PowerApp**.

    - Jeśli dostęp do osadzonej PowerApp uzyskuje się za pośrednictwem przycisk menu Power Apps, kliknij prawym przyciskiem myszy przycisk menu Power Apps i wybierz polecenie **Personalizuj**. Z menu rozwijanego **Wybierz PowerApp** wybierz PowerApp, którą chcesz skonfigurować.
    - Jeśli osadzona PowerApp pojawia się bezpośrednio na stronie, kliknij przycisk **Opcje**, a następnie wybierz opcję **Personalizuj ten formularz**. Za pomocą narzędzia **Wybierz** kliknij osadzoną PowerApp.

2. Wprowadź wymagane modyfikacje w konfiguracji Power Apps, a następnie kliknij przycisk **Zapisz**.

## <a name="removing-an-embedded-power-app"></a>Usuwanie osadzonej PowerApp

Po osadzeniu PowerApp na stronie istnieją dwa sposoby jej usunięcia w razie potrzeby:

- Przejdź do okienka **Edytuj PowerApp** przy użyciu instrukcji zawartych w sekcji [Edytowanie osadzonej PowerApp](#editing-an-embedded-power-app) wcześniej w tym temacie. Upewnij się, że w okienku są wyświetlane informacje dotyczące osadzonej PowerApp, którą chcesz usunąć, a następnie kliknij przycisk **Usuń**.
- Ponieważ osadzona PowerApp jest zapisywana jako dane personalizacji, wyczyszczenie personalizacji strony spowoduje również usunięcie wszelkich osadzonych Power Apps znajdujących się na tej stronie. Należy zauważyć, że wyczyszczenie personalizacji strony jest trwałe i nie można go cofnąć. Aby usunąć personalizacje ze strony, kliknij przycisk **Opcje**, a następnie wybierz opcję **Personalizuj ten formularz**. W menu **Zarządzaj** naciśnij przycisk **Wyczyść**. Po odświeżeniu przeglądarki wszystkie poprzednie personalizacje tej strony zostaną usunięte. W temacie [Personalizuj środowiska użytkownika](personalize-user-experience.md) znajdziesz więcej informacji o optymalizowaniu stron za pomocą personalizacji.

## <a name="appendix"></a>Dodatek

### <a name="developer-control-over-where-a-power-app-can-be-embedded"></a>Kontrola dewelopera nad miejscem osadzenia PowerApp

Domyślnie użytkownicy mogą osadzać Power Apps na każdej stronie, używając do tego przycisku menu Power Apps lub bezpośrednio na stronie w postaci karty, karty skróconej, bloku lub nowej sekcji w obszarze roboczym. Jednak w razie potrzeby deweloperzy mogą również skonfigurować tę funkcję tak, aby zezwalać na osadzanie Power Apps tylko na niektórych stronach. Służą do tego następujące metody:

- **isPowerAppPersonalizationEnabled** — jeśli ta metoda zwraca wartość false dla określonej strony, to przycisk menu Power Apps nie będzie wyświetlany, a użytkownicy nie będą mogli osadzać Power Apps nigdzie na tej stronie, w tym w postaci karty.
- **isPowerAppTabPersonalizationEnabled** — jeśli ta metoda zwraca wartość false dla określonej strony, to użytkownicy nie będą mogli osadzać Power Apps bezpośrednio na stronie w postaci karty, skróconej karty ani sekcji panoramy. Użytkownicy nadal będą mogli osadzać Power Apps za pomocą przycisku menu Power Apps, o ile tylko osadzanie jest dozwolone na stronie.

Poniższy przykład przedstawia nową klasę z dwoma metodami potrzebnymi do określenia, gdzie można osadzać Power Apps.

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
