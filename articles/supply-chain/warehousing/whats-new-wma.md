---
title: Nowości lub zmiany w aplikacji mobilnej Warehouse Management
description: W tym temacie wymieniono nowe i zmienione funkcje dla każdej wydanej wersji aplikacji mobilnej Warehouse Management dla firmy Microsoft Dynamics 365 Supply Chain Management.
author: MarkusFogelberg
ms.date: 09/09/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2021-06-07
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: ac3ea6a088b2086054eb692cd0688b269dafca51
ms.sourcegitcommit: e7eeca05d738e9e46d6185d1ba349836ebafc1a4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/09/2021
ms.locfileid: "7485629"
---
# <a name="whats-new-or-changed-in-the-warehouse-management-mobile-app"></a>Nowości lub zmiany w aplikacji mobilnej Warehouse Management

[!include [banner](../includes/banner.md)]

W tym temacie wymieniono nowe funkcje, poprawki, ulepszenia i znane problemy dla każdej wydanej wersji aplikacji mobilnej Warehouse Management w Microsoft Dynamics 365 Supply Chain Management.

## <a name="version-20100"></a>Wersja 2.0.10.0

Ta wersja wprowadza następujące nowe funkcje, poprawki i ulepszenia:

- Dodano animację po wsuwaniu przez listy i strony.
- Tekst jest teraz prawidłowo wyświetlany na stronie błędu połączenia.
- Pola kombi bez wartości domyślnych będą teraz poprawnie wyświetlane.
- Informacje w obszarze podtytułów są teraz wyświetlane tylko na stronie z pełnymi informacjami.
- Puste pola wejściowe nie są już wyświetlane na karcie szczegółów.
- Wartości potwierdzenia nie są już duplikowane na karcie szczegółów.
- Naprawiono różne problemy, które powodowały, że system przestawał odpowiadać.

## <a name="version-2090"></a>Wersja 2.0.9.0

Ta wersja rozwiąże problem, przez który aplikacja może przestać odpowiadać, jeśli użytkownicy chcą wejść wyżej znajdując się na początku listy.

## <a name="version-2080"></a>Wersja 2.0.8.0

Ta wersja wprowadza następujące nowe funkcje, poprawki i ulepszenia:

- Dodano obsługę [funkcji instrukcji kroku](mobile-app-titles-instructions.md), która została wprowadzona w Supply Chain Management w wersji 10.0.21.
- Dodano animację wskazówki, aby pokazać użytkownikom, że mogą zamykać nakładki, przesuwając palcem w dół.
- Dodano obsługę klawiszy funkcyjnych na listach akcji i w menu. Użytkownicy mogą wyświetlić listę dostępnych poleceń, przytrzymując dowolny klawisz funkcyjny.
- Rozwiązano problem, który powodował wyświetlanie na niektórych urządzeniach następującego komunikatu o błędzie: „Nie można znaleźć odpowiedniego widoku dla określonego rozmiaru”.
- Rozwiązano problem, który powodował, że tryb pełnoekranowy nie zawsze działał, gdy była używana klawiatura ekranowa.
- Rozwiązano problem z tym, że przesuwanie strony nie działało na urządzeniach z systemem Windows.
- Naprawiono różne problemy, które powodowały, że system przestawał odpowiadać.

## <a name="version-2070"></a>Wersja 2.0.7.0

### <a name="new-features-fixes-and-improvements-in-version-2070"></a>Nowe funkcje, poprawki i ulepszenia w wersji 2.0.7.0

- Dodano sekcję na stronie **Informacje**, która sprawdza najnowszą wydaną wersję aplikacji.
- Ułatwiono szybkie przesuwanie i przeciąganie między stronami.
- Zmieniono ikonę przycisku Rosnąco/malejąco na liście pracy.
- Zmniejszono marginesy na karcie **Szczegóły**, aby umożliwić zmieszczenie większej ilości informacji.
- Zastosowano różne ulepszenia wydajności, aby zmniejszyć problem z aplikacją działającą coraz wolniej w czasie.
- Jeśli kontrolek jest tak dużo, że nie mieszczą się na ekranie, co powoduje dzielenie na strony, kontrolka pokrętła nie jest już przewijana w taki sam sposób, jak strona.
- Ustalono priorytet pokazujący wartość ostatniego skanowania nad tytułem zadania, więc jeśli nakładają się na siebie, tytuł zadania zostanie obcięty.
- Naprawiono różne problemy, które powodowały, że system przestawał odpowiadać.
- Tekst w różnych miejscach nie jest już obcięty w niektórych językach.
- Aplikacja jest teraz domyślnie uruchamiana w trybie pełnoekranowym.
- Naprawiono błąd, który czasami powodował, że skanowanie było ignorowane na stronie głównej na niektórych urządzeniach.

### <a name="known-issues-in-version-2070"></a>Znane problemy w wersji 2.0.7.0

- Na niektórych urządzeniach podczas uruchamiania aplikacji lub rozpoczynania zadania zostanie wyświetlony następujący komunikat o błędzie: „Nie można znaleźć odpowiedniego widoku dla określonego rozmiaru”. Jeśli ten komunikat o błędzie jest wyświetlany na dowolnym urządzeniu, musisz obniżyć wersję aplikacji mobilnej Warehouse Management do wersji 2.0.6.0 na tym urządzeniu i poczekać na uaktualnienie do wydania następnej wersji aplikacji.

## <a name="version-2060"></a>Wersja 2.0.6.0

### <a name="new-features-fixes-and-improvements-in-version-2060"></a>Nowe funkcje, poprawki i ulepszenia w wersji 2.0.6.0

Ta wersja wprowadza następujące nowe funkcje, poprawki i ulepszenia:

- Tryb demonstracyjny pokazuje teraz wszystkie etykiety w języku urządzenia.
- Jest mniej prawdopodobne, że otrzymasz następujący komunikat o błędzie: „Nie można znaleźć odpowiedniego widoku dla określonego rozmiaru.”
- Zwiększono minimalną wysokość dla kart pracy (dla przypadków, gdy na liście pracy mają się pojawić trzy lub mniej pól).
- Poprawiono marginesy (wygaszanie) na dole kart szczegółów.
- Nieprawidłowe symbole w plikach XML, które są wymieniane z serwerem, są teraz obsługiwane z wdziękiem. (Na przykład, znaki niedrukowalne są teraz obsługiwane z wdziękiem i nie powodują już, że aplikacja przestaje odpowiadać).
- Błędy HTTP (takie jak „błąd 503”), gdy żądanie serwera jest wysyłane, są teraz obsługiwane z wdziękiem.
- Podczas wyświetlania błędu lista opcji nie jest już automatycznie wyświetlana dla kontrolek pola kombi.
- Aplikacja nie przestaje odpowiadać z powodu orientacji wyświetlacza wybranej w ustawieniach użytkownika.
- Obrazy produktów są teraz wyświetlane w środowiskach samoobsługowych. (Ta zmiana dotyczy tylko wersji o niskiej rozdzielczości. Usługa zarządzania plikami nie obsługuje pełnowymiarowych obrazów w środowiskach samoobsługowych).
- Usunięto problem związany z krótkim pobieraniem o zerowej ilości.
- Aplikacja nie przestaje odpowiadać, gdy na karcie szczegółów znajduje się wiele identycznych pól.

### <a name="known-issues-in-version-2060"></a>Znane problemy w wersji 2.0.6.0

W tej wersji występują następujące znane problemy:

- Aplikacja (zwłaszcza lista prac) z czasem staje się wolniejsza.
- **Wersja dla systemu Windows:** Gdy USB gun jest używany do skanowania w systemie Windows, niespójne wyniki powodują mieszanie zeskanowanych symboli.

## <a name="version-2050"></a>Wersja 2.0.5.0

Ta wersja wprowadza następujące nowe funkcje, poprawki i ulepszenia:

- Sekret klienta nie jest już ukryty w ustawieniach połączenia.
- Możesz teraz długo nacisnąć na dowolny tekst, aby zobaczyć go w całości.
- Poprawiono komunikat o błędzie w przypadku braku uprawnień do przechowywania danych.
- Dla niektórych przepływów dodano nowe sekwencje sterujące.
- Przycisk wysyłania nie jest już nieprawidłowo dostępny ze względu na rozmiar okna.
- Suwaki mogą teraz działać na mniejszych ekranach, gdy używane są większe rozmiary przycisków.
- Nakładka na cztery przyciski nie jest już ucięta.
- Klawiatura obsługuje teraz przycisk usuwania.
- Usunięto problem z jasnością, który mógł wystąpić po naciśnięciu klawiatury.
- Naprawiono różne problemy z danymi demo.
- Naprawiono błąd, który dotyczył pól numerycznych na stronie szczegółów.
- Klawiatura ekranowa nie znika już czasami na niektórych urządzeniach.
- Naprawiono różne błędy interfejsu użytkownika (UI), takie jak błędy, które wpływały na kolor tła i pozycjonowanie.
- Ulepszono interfejs użytkownika w języku rosyjskim.
- Naprawiono różne problemy, które powodowały, że system przestawał odpowiadać.
- Usunięto problem związany z ponownym otwieraniem kalkulatora.
- **Wersja Android:** Rozwiązano problem, który powodował, że Android 4.4 przestał odpowiadać podczas uruchamiania.
- **Wersja Android** Minimalne skalowanie zostało zmniejszone do 50 procent.

## <a name="version-2040"></a>Wersja 2.0.4.0

Wersja 2.0.4.0 była pierwszym ogólnie dostępnym wydaniem aplikacji mobilnej Warehouse Management.

### <a name="new-features-fixes-and-improvements-in-version-2040"></a>Nowe funkcje, poprawki i ulepszenia w wersji 2.0.4.0

Ta wersja wprowadza następujące nowe funkcje, poprawki i ulepszenia, które nie były dostępne w wersji zapoznawczej:

- Jeśli na karcie szczegółów znajdują się dwie etykiety z identycznymi danymi, jedna z nich jest ukryta.
- Znaki specjalne są teraz wyświetlane domyślnie, a opcja ich ukrywania została usunięta z ustawień użytkownika.
- Wyłączone przyciski wysyłania są teraz wyświetlane jako niedostępne w widoku kompaktowym z ręki.
- Zmiana w logice sekwencjonowania elementów sterujących zapewnia płynniejsze skalowanie w różnych urządzeniach. Dzięki temu nie ma potrzeby dostosowywania skalowania czcionek czy przycisków.
- Domyślny motyw kolorów został zmieniony na *Ciemny*.
- Brakująca ikona dla wyłączonego przycisku wysyłania została dodana w widoku wstążki.
- Wyjątki przekroczenia limitu czasu przenoszą teraz użytkownika na stronę połączenia zamiast pokazywać błąd w linii.
- Jeśli nie ma dostępnej akcji przesyłania (np. **OK**, **Tak**, **Zaakceptowana**, **Zakończona** lub **Zakończona**), przycisk przesyłania będzie wyłączony.
- Poprawiono stabilność aplikacji.
- Istnieje poprawka zagrożeń dla bezpieczeństwa [CVE-2021-26701](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-26701).
- **Wersja systemu Windows:** Naprawiono problem występujący w systemie Windows, w którym menu nie reagowało po zmianie rozmiaru okna.

### <a name="known-issue-in-version-2040"></a>Znane problemy w wersji 2.0.4.0

W tej wersji występuje następujący znany problem:

- Ta wersja stanowi problem z urządzeniami, które korzystają z Android w wersji 4.4. Podczas korzystania z aplikacji w tej wersji Android mogą wystąpić problemy.
