---
title: Osadzanie aplikacji PowerApp
description: "W tym temacie opisano sposób osadzania aplikacji PowerApp na kliencie rozwiązania Finance and Operations w celu rozszerzenia funkcjonalności produktu."
author: jasongre
manager: AnnBe
ms.date: 04/12/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: FormRunConfigurationAddPAControl, FormRunConfigurationEditPAControl
audience: Application User, Developer, IT Pro
ms.search.scope: Operations, Core
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2018-02-28
ms.dyn365.ops.version: Platform update 14
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 07224faabcf2b183d4c8da0ba4588c33ec140d03
ms.contentlocale: pl-pl
ms.lasthandoff: 04/13/2018

---

# <a name="embed-powerapps"></a>Osadzanie aplikacji PowerApp

[!INCLUDE [banner](../includes/banner.md)]

[!INCLUDE [banner](../includes/pre-release.md)]

W aktualizacji platformy 14 program Microsoft Dynamics 365 for Finance and Operations obsługuje integrację z Microsoft PowerApps — usługą dla deweloperów i użytkowników nietechnicznych, która umożliwia tworzenie niestandardowych aplikacji biznesowych dla urządzeń przenośnych, tabletów i sieci web bez pisania kodu. Aplikacje PowerApp opracowane przez użytkownika, organizację lub członków szerszego ekosystemu można następnie osadzać w kliencie rozwiązania Finance and Operations w celu rozszerzenia funkcjonalności produktu. Na przykład można utworzyć aplikację PowerApp w celu uzupełniania programu Finance and Operations o informacje pobrane z innego systemu. 

Aby uzyskać więcej informacji o osadzaniu aplikacji PowerApp, obejrzyj krótki film [Jak osadzać aplikacje PowerApp w programie Dynamics 365 for Finance and Operations](https://www.youtube.com/watch?v=x3qyA1bH-NY).

> [!Video https://www.youtube.com/embed/x3qyA1bH-NY]

## <a name="adding-an-embedded-powerapp-to-a-page"></a>Dodawanie osadzonej aplikacji PowerApp do strony
### <a name="overview"></a>Przegląd
Przed osadzeniem aplikacji PowerApp w kliencie rozwiązania Finance and Operations najpierw należy odnaleźć lub utworzyć aplikację PowerApp z żądanymi elementami wizualnymi i/lub funkcjami. Tutaj nie opiszemy szczegółowego procesu kompilowania aplikacji PowerApp . Temat [Wprowadzenie do usługi PowerApps](https://docs.microsoft.com/en-us/powerapps/getting-started) jest dobrym punktem wyjściowym dla nowych użytkowników usługi PowerApps.

Gdy masz wszystko gotowe do rozpoczęcia osadzania konkretnej aplikacji PowerApp, możesz wybrać jeden z dwóch sposobów dostępu do aplikacji PowerApp na stronie — zależnie od tego, który scenariusz lepiej Ci pasuje. Pierwszy sposób to użycie przycisku usługi PowerApps, który został dodany do standardowego okienka akcji. Aplikacje PowerApp dodane za pomocą tego mechanizmu będą wyświetlane jako elementy menu wewnątrz przycisku menu usługi PowerApps. Wybranie elementu menu spowoduje otwarcie okienka bocznego zawierającego odpowiednią osadzoną aplikację PowerApp. Alternatywnie można wybrać wyświetlanie aplikacji PowerApp bezpośrednio na stronie w postaci nowej karty, karty skróconej, bloku lub nowej sekcji w obszarze roboczym. 

Podczas konfigurowania osadzonej aplikacji PowerApp w programie Finance and Operations można wybrać jedno pole, którego zawartość ma być wysyłana jako dane wejściowe do aplikacji PowerApp. Dzięki temu aplikacja PowerApp może reagować na podstawie danych obecnie wyświetlanych w programie Finance and Operations.  

### <a name="details"></a>Szczegóły
Poniższe instrukcje przedstawiają sposoby osadzania aplikacji PowerApp w kliencie internetowym programu Finance and Operations.  

1. Przejdź do strony, w której chcesz osadzić aplikację PowerApp. Jest to ta sama strona, która zawiera wszelkie dane, jakie muszą zostać przekazane do aplikacji PowerApp jako dane wejściowe.  
2. Otwórz okienko **Wstaw aplikację PowerApp**:
   - Kliknij przycisk **Opcje**, a następnie wybierz opcję **Personalizuj ten formularz**. W menu **Wstaw** wybierz polecenie **PowerApp**. Na koniec wybierz region, w którym chcesz dodać aplikację PowerApp. Jeśli chcesz osadzić aplikację PowerApp w przycisku menu usługi PowerApps, wybierz okienko akcji. Jeśli chcesz osadzić aplikację PowerApp bezpośrednio na stronie, wybierz odpowiednią kartę, kartę skróconą, blok lub sekcję (jeśli pracujesz w obszarze roboczym).   
   - Jeśli dostęp do aplikacji PowerApp będzie uzyskiwany przy użyciu przycisku menu usługi PowerApps, można również kliknąć przycisk menu usługi **PowerApps** w standardowym okienku akcji, a następnie wybrać opcję **Wstaw aplikację PowerApp**.  
3. Konfigurowanie osadzonej aplikacji PowerApp:
   - Pole **Nazwa** wskazuje tekst, jaki będzie wyświetlany na przycisku lub karcie zawierającej osadzoną aplikację PowerApp. Często w tym polu warto powtórzyć nazwę aplikacji PowerApp.  
   - **Identyfikator aplikacji** to identyfikator GUID aplikacji PowerApp, która ma być osadzona. Aby pobrać tę wartość, odszukaj aplikację PowerApp na stronie [web.powerapps.com](https://web.powerapps.com), a następnie odszukaj pole **Identyfikator aplikacji** w obszarze **Szczegóły**.  
   - W obszarze **Dane wejściowe dla aplikacji PowerApp** można opcjonalnie wybrać pole zawierające dane, które mają być przekazywane do aplikacji PowerApp jako dane wejściowe. Zobacz w dalszej części tego tematu sekcję zatytułowaną [Kompilowanie aplikacji PowerApp wykorzystującej dane z programu Finance and Operations](#building-a-powerapp-that-leverages-data-sent-from-finance-and-operations), gdzie dowiesz się dokładnie, jak aplikacja PowerApp może uzyskiwać dostęp do danych wysyłanych z programu Finance and Operations.  
   - Wybierz wartość **Rozmiar aplikacji** pasującą do typu osadzanej aplikacji PowerApp. Wybierz opcję **Ograniczona** dla aplikacji PowerApp przeznaczonych do urządzeń przenośnych, a opcję **Rozbudowana** dla aplikacji PowerApp przeznaczonych do tabletów. To zagwarantuje przeznaczenie wystarczającej ilości miejsca na wbudowaną aplikację PowerApp.
   - Na skróconej karcie **Firmy** można wybrać firmy, dla których aplikacja PowerApp będzie dostępna. Domyślnie aplikacja PowerApp jest wyświetlana we wszystkich firmach.  
4. Po potwierdzeniu, że konfiguracja jest poprawna, kliknij przycisk **Wstaw**, co spowoduje osadzenie aplikacji PowerApp na stronie. Zobaczysz monit o odświeżenie przeglądarki, aby zobaczyć osadzoną aplikację PowerApp. 

## <a name="sharing-an-embedded-powerapp"></a>Udostępnianie osadzonej aplikacji PowerApp
Po osadzeniu aplikacji PowerApp na stronie i sprawdzeniu, że działa poprawnie z każdym kontekstem danych przekazanym ze strony, można udostępnić osadzoną aplikację PowerApp innym użytkownikom w systemie. Można to zrobić na dwa różne sposoby przy użyciu funkcji personalizacji produktu:

- Zalecanym scenariuszem jest skorzystanie z pośrednictwa administratora systemu, który może rozesłać personalizację do wszystkich użytkowników lub tylko do grupy użytkowników. 

- Alternatywnie można wyeksportować personalizacje strony, wysłać je do jednego lub więcej użytkowników, a następnie polecić użytkownikom, aby zaimportowali zmiany. Opcja Zarządzaj umieszczona na pasku narzędzi personalizacji umożliwia eksportowanie i importowanie personalizacji.

Temat [Personalizowanie środowiska użytkownika](personalize-user-experience.md) zawiera więcej informacji o funkcjach personalizacji w produkcie oraz o sposobach ich używania.

## <a name="building-a-powerapp-that-leverages-data-sent-from-finance-and-operations"></a>Kompilowanie aplikacji PowerApp wykorzystującej dane z programu Finance and Operations
Ważną częścią procesu tworzenia aplikacji PowerApp, która zostanie osadzona w programie Finance and Operations, jest wykorzystywanie danych wejściowych z programu Finance and Operations. Wewnątrz aplikacji PowerApp dostęp do tych danych wejściowych można uzyskać za pomocą zmiennej Param("EntityId").  

Na przykład w funkcji OnStart wewnątrz aplikacji PowerApp można ustawić dane wejściowe z programu Finance and Operations w następujący sposób:

If(!IsBlank(Param("EntityId")), Set(FinOpsInput, Param("EntityId")), Set(FinOpsInput, "")); 

## <a name="viewing-an-embedded-powerapp"></a>Wyświetlanie osadzonej aplikacji PowerApp
Aby wyświetlić osadzoną aplikację PowerApp na stronie programu Finance and Operations, po prostu przejdź do strony z osadzoną aplikacją PowerApp. Przypominamy, że dostęp do aplikacji PowerApp można uzyskać za pomocą przycisku usługi PowerApps w standardowym okienku akcji lub też aplikacje PowerApp mogą być wyświetlane bezpośrednio na stronie jako nowa karta, karta skrócona, blok lub nowa sekcja w obszarze roboczym. Gdy użytkownik po raz pierwszy próbuje załadować aplikację PowerApp na stronie, zobaczy monit o zalogowanie się do usługi PowerApps w celu potwierdzenia, że ma odpowiednie uprawnienia potrzebne do korzystania z aplikacji PowerApp.   

## <a name="editing-an-embedded-powerapp"></a>Edytowanie osadzonej aplikacji PowerApp
Po osadzeniu aplikacji PowerApp na stronie może być konieczne wprowadzenie pewnych zmian w konfiguracji tej aplikacji. Na przykład prawdopodobnie zechcesz zmodyfikować etykietę skojarzoną z osadzoną aplikacją PowerApp lub też utworzono nową wersję aplikacji PowerApp i trzeba zaktualizować identyfikatora aplikacji, tak aby wskazywał najnowszą wersję. 

Wykonaj następujące czynności, aby edytować konfigurację osadzonej aplikacji PowerApp:
1. Przejdź do okienka **Edytuj aplikację PowerApp**. 
   - Jeśli dostęp do osadzonej aplikacji PowerApp uzyskuje się za pośrednictwem przycisk menu usługi PowerApps, kliknij prawym przyciskiem myszy przycisk menu usługi PowerApps i wybierz polecenie **Personalizuj**. Z menu rozwijanego **Wybierz aplikację PowerApp** wybierz aplikację PowerApp, którą chcesz skonfigurować.  
   - Jeśli osadzona aplikacja PowerApp pojawia się bezpośrednio na stronie, kliknij przycisk **Opcje**, a następnie wybierz opcję **Personalizuj ten formularz**. Za pomocą narzędzia **Wybierz** kliknij osadzoną aplikację PowerApp.  
2. Wprowadź wymagane modyfikacje w konfiguracji aplikacji PowerApp, a następnie kliknij przycisk **Zapisz**.  

## <a name="removing-an-embedded-powerapp"></a>Usuwanie osadzonej aplikacji PowerApp
Po osadzeniu aplikacji PowerApp na stronie istnieją dwa sposoby jej usunięcia w razie potrzeby: 

- Przejdź do okienka **Edytuj aplikację PowerApp** przy użyciu instrukcji zawartych w sekcji [Edytowanie osadzonej aplikacji PowerApp](#editing-an-embedded-powerapp) wcześniej w tym temacie. Upewnij się, że w okienku są wyświetlane informacje dotyczące osadzonej aplikacji PowerApp, którą chcesz usunąć, a następnie kliknij przycisk **Usuń**. 

- Ponieważ osadzona aplikacja PowerApp jest zapisywana jako dane personalizacji, wyczyszczenie personalizacji strony spowoduje również usunięcie wszelkich osadzonych aplikacji PowerApp znajdujących się na tej stronie. Należy zauważyć, że wyczyszczenie personalizacji strony jest trwałe i nie można go cofnąć. Aby usunąć personalizacje ze strony, kliknij przycisk **Opcje**, a następnie wybierz opcję **Personalizuj ten formularz**. W menu **Zarządzaj** naciśnij przycisk **Wyczyść**. Po odświeżeniu przeglądarki wszystkie poprzednie personalizacje tej strony zostaną usunięte. W temacie [Personalizowanie środowiska użytkownika](personalize-user-experience.md) znajdziesz więcej informacji o optymalizowaniu stron za pomocą personalizacji.  

## <a name="appendix"></a>Dodatek 
### <a name="developer-control-over-where-a-powerapp-can-be-embedded"></a>Kontrola dewelopera nad miejscem osadzenia aplikacji PowerApp
Domyślnie użytkownicy mogą osadzać aplikacje PowerApp na każdej stronie, używając do tego przycisku menu usługi PowerApps lub bezpośrednio na stronie w postaci karty, karty skróconej, bloku lub nowej sekcji w obszarze roboczym. Jednak w razie potrzeby deweloperzy mogą również skonfigurować tę funkcję tak, aby zezwalać na osadzanie aplikacji PowerApp tylko na niektórych stronach. Służą do tego następujące metody: 

- **isPowerAppPersonalizationEnabled** — jeśli ta metoda zwraca wartość false dla określonej strony, to przycisk menu usługi PowerApps nie będzie wyświetlany, a użytkownicy nie będą mogli osadzać aplikacji PowerApp nigdzie na tej stronie, w tym w postaci karty. 

- **isPowerAppTabPersonalizationEnabled** — jeśli ta metoda zwraca wartość false dla określonej strony, to użytkownicy nie będą mogli osadzać aplikacji PowerApp bezpośrednio na stronie w postaci karty, skróconej karty ani sekcji panoramy. Użytkownicy nadal będą mogli osadzać aplikacje PowerApp za pomocą przycisku menu usługi PowerApps, o ile tylko osadzanie jest dozwolone na stronie.  

Poniższy przykład przedstawia nową klasę z dwoma metodami potrzebnymi do określenia, gdzie można osadzać aplikacje PowerApp.  

```
[ExtensionOf(classStr(FormRunConfigurationPowerAppsConfiguration))]

public final class ClassTest_Extension
{

    public static boolean isPowerAppPresonalizationEnabled(str pageName)
    {
        var result = next isPowerAppPresonalizationEnabled(pageName);
        return true;
    }

    public static boolean isPowerAppTabPresonalizationEnabled(str pageName)   
    {
        var result = next isPowerAppTabPresonalizationEnabled(pageName);
        return true;
    }
    ```

}


