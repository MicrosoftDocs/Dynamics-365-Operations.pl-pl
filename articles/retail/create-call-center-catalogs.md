---
title: "Tworzenie katalogu biura obsługi"
description: "Ten artykuł zawiera omówienie procesu tworzenia katalogu dla biura obsługi."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 16212
ms.assetid: c9d1b9df-82e8-4b3a-a13c-166df8b9718e
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 94ff6d74d4a11b3b04be6b69f85e778c3b45de92
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---

# <a name="create-a-call-center-catalog"></a>Tworzenie katalogu biura obsługi

[!include[banner](includes/banner.md)]


Ten artykuł zawiera omówienie procesu tworzenia katalogu dla biura obsługi. 

W biurze obsługi można używać katalogów produktów do identyfikowania produktów, które chcesz oferować odbiorcom. Zazwyczaj biura obsługi korzystają z katalogów drukowanych. Projektowanie i druk katalogów odbywa się poza programem Microsoft Dynamics 365 for Retail. Możesz jednak utworzyć i zapisać formularz cyfrowy w postaci katalogu za pomocą tych samych formularzy, których używasz do konfiguracji katalogów sieci sprzedaży online. Przed stworzeniem katalogu należy skonfigurować asortymenty produktów oraz przypisać asortymenty do biura obsługi. Następnie należy dodać produkty do katalogu, zaznaczając produkty z tych asortymentów. Po dodaniu produktów do katalogu i zakończeniu pracy z katalogiem, należy sprawdzić poprawność katalogu, aby sprawdzić dane. Następnie należy przesłać katalog do przejrzenia i zatwierdzenia. Po zatwierdzeniu katalogu może on zostać opublikowany. Po utworzeniu katalogu dla biura obsługi, można wykonać migawkę danych katalogu w momencie opublikowania katalogu. Ta funkcja migawki umożliwia uzyskanie dostępu do określonej wersji katalogu, nawet jeśli ulegnie ona później zmianie i aktualizacji. Katalogi biura obsługi można również ustawić w taki sposób, aby uwzględnić także następujące funkcje opcjonalne.

-   **Kody źródłowe** — kody, które są używane do śledzenia odpowiedzi odbiorcy na określone katalogi.
-   **Produkty bezpłatne** — produkty, które są uwzględniane w zamówieniu odbiorcy bez dodatkowych opłat. Produkty te są dodawane do zamówienia automatycznie po wprowadzeniu do zamówienia kodu źródłowego dla katalogu.
-   **Skrypty** — teksty, które pracownik biura obsługi odczytuje w rozmowie z odbiorcą podczas tworzenia zamówienia sprzedaży. Skrypty mogą obejmować powitania lub sugestie dotyczące zakupu.
-   **Sprzedaż dodatkowa i wiązana** — towary są wyświetlane jako sugerowane, gdy określony produkt zostanie dodany do zamówienia.

Przed zaakceptowaniem i opublikowaniem katalogu te opcje muszą być skonfigurowane.

## <a name="prerequisites"></a>Wymagania wstępne
Przed rozpoczęciem muszą być ukończone następujące zadania:

-   Konfigurowanie produktów i asortymentów produktów.
-   Konfigurowanie produktów sieci sprzedaży.
-   Konfigurowanie asortymentu.
-   Tworzenie biura obsług.
-   Konfigurowanie biura obsługi.
-   Dodawanie biura obsługi do hierarchii organizacyjnej.
-   Konfigurowanie lub modyfikowanie hierarchii organizacyjnej.

## <a name="create-a-catalog"></a>Tworzenie katalogu
Należy najpierw otworzyć katalog, dodać produkty do katalogu, a następnie przejrzeć i zaktualizować atrybuty dla produktów.

## <a name="validate-the-catalog"></a>Weryfikacja katalogu
Po zakończeniu konfigurowania katalogu, należy sprawdzić jej poprawność. Ten proces sprawdza, czy dane wymagane dla atrybutów kanału i atrybutów produktu są prawidłowe i kompletne, a katalog może zostać opublikowany.

## <a name="submit-the-catalog-for-review-and-approval"></a>Przesłanie katalogu zaopatrzenia do sprawdzania i zatwierdzenia
Po sprawdzeniu poprawności katalogu, można przesłać katalog do przeglądu i zatwierdzenia. Katalog musi zostać zatwierdzony zanim można go będzie opublikować. Istnieje możliwość konfigurowania przepływu pracy tak, aby katalogi były zatwierdzane automatycznie albo wymagały zatwierdzenia ręcznego.

## <a name="optional-add-source-codes-free-products-and-scripts"></a>Opcjonalnie: Dodaj kody źródłowe, produkty bezpłatne i skrypty
Możesz też dodać następujące elementy do katalogu głównego użytkownika rozmów. Te elementy są opcjonalne.

-   **Kody źródłowe** mogą być używane przez firmy, które mogą używać kodów źródłowych do śledzenie odpowiedzi odbiorcy na określone katalogi. Kody źródłowe są często drukowane na tylnej okładce katalogu i są wprowadzane do zamówienia sprzedaży, gdy odbiorca dokonuje zakupu. Aby dodać kod źródłowy do katalogu, należy najpierw utworzyć rynek docelowy. Rynek docelowy zazwyczaj jest mapowany do własnej lub wynajmowanej listy wysyłkowej.
-   **Produkty bezpłatne** to towary promocyjne dodawane bezpłatnie do zamówienia odbiorcy, gdy występuje odwołanie do katalogu.
-   **Skrypty** mogą służyć do obsługi interakcji między pracownikiem i odbiorcą w kontekście katalogu lub produktu w katalogu.

## <a name="publish-the-catalog"></a>Publikowanie katalogu
Opublikowanie katalogu dla biura obsługi oznacza finalizację informacji o produktach w katalogu. Publikacja wskazuje także, czy katalog jest gotowy do prowadzenia wszelkich dodatkowych akcji, które chcesz wykonać. Można na przykład utworzyć drukowany katalog. Katalogi można publikować ręcznie, ale można też robić to za pomocą zadania przetwarzania wsadowego, umożliwiającego publikację w oparciu o harmonogram. Przed opublikowaniem katalogu, musi on być sprawdzony i zatwierdzony. Aby zmienić katalog po jego opublikowaniu, można wycofać katalog, a następnie ponownie go opublikować.




