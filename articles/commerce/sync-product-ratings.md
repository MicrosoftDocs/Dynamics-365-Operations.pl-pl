---
title: Synchronizacja ocen produktów w rozwiązaniu Dynamics 365 Retail
description: W tym temacie opisano sposób synchronizowania ocen produktów w Microsoft Dynamics 365 Retail.
author: gvrmohanreddy
manager: annbe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: gmohanv
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: db5a4e1f78797d20ded2274cc99bef422fd50acc
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/01/2019
ms.locfileid: "2698172"
---
# <a name="sync-product-ratings-in-dynamics-365-retail"></a>Synchronizacja ocen produktów w rozwiązaniu Dynamics 365 Retail

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

W tym temacie opisano sposób synchronizowania ocen produktów w Microsoft Dynamics 365 Retail.

## <a name="overview"></a>Omówienie

W celu użycia ocen produktów w wielu kanałach, na przykład w punkt sprzedaży (POS) i w biurach obsługi, oceny produktów z usługi ocen i recenzji muszą zostać zaimportowane do bazy danych kanału Retail. Po udostępnieniu ocen produktów w wielu kanałach mogą one pomóc klientom w pośredniej interakcji ze sprzedawcą.

W tym temacie opisano następujące zadania:

1. Skonfiguruj zadanie wsadowe Retail, aby zaimportować klasyfikacje produktów.
1. Sprawdź, czy zadanie wsadowe synchronizacji oceny produktu zakończyło się pomyślnie.
1. Umożliwia udostępnienie ocen produktów w punkcie sprzedaży.

## <a name="configure-a-retail-batch-job-to-import-product-ratings"></a>Skonfiguruj zadanie wsadowe Retail, aby zaimportować oceny produktów

> [!IMPORTANT]
> Przed rozpoczęciem należy się upewnić, że jest zainstalowana wersja 10.0.6 lub nowsza Retail.

### <a name="initialize-the-retail-scheduler"></a>Zainicjuj harmonogram aplikacji Retail

Aby zainicjować harmonogram sieci sprzedaży, wykonaj następujące kroki.

1. Przejdź do **Retail \> Ustawienia centrali \> Transfer danych w sieci sprzedaży \> Zainicjuj harmonogram aplikacji Retail**. Alternatywnie można wyszukać wartość „Inicjuj transfer danych w sieci sprzedaży”.
1. W oknie dialogowym **Inicjowanie transferuw sieci sprzedaży** upewnij się, że opcja **Usuń istniejącą konfigurację** jest ustawiona na wartość **nie**, a następnie kliknij przycisk **OK**.

### <a name="verify-the-retailproductrating-subjob"></a>Sprawdź podzadanie RetailProductRating

Aby sprawdzić, czy istnieje podzadania **RetailProductRating**, wykonaj następujące kroki.

1. Przejdź do **Retail \> Ustawienia centrali \> Transfer danych w sieci sprzedaży \> Podzadania harmonogramu**. Alternatywnie można wyszukać frazę „podzadania harmonogramu”.
1. Na liście podzadania Znajdź lub Wyszukaj podzadanie **RetailProductRating**.

Na poniższej ilustracji pokazano przykład strony szczegóły podzadania w Retail.

![Szczegóły podzadania RetailProductRating](media/rnr-hq-ratings-sub-job.png)

> [!NOTE]
> Jeśli nie znajdziesz podzadania **RetailProductRating**, możesz już wcześniej uruchomić zadanie **Synchronizuj oceny produktów** i zadanie **1040 CDX** przed zainicjowaniem procesu transferu danych w sieci sprzedaży. W takim przypadku należy wykonać następujące kroki w celu uruchomienia zadania **Pełnej synchronizacji danych**.
>
> 1. Przejdź do **Retail \> Ustawienia centrali \> Transfer danych w sieci sprzedaży \> Baza danych kanału**. Alternatywna metoda polega na wyszukaniu „bazy danych kanału”.
> 1. Wybierz bazę danych kanału do zsynchronizowania.
> 1. W okienku akcji wybierz **Pełna synchronizacja danych**.
> 1. W oknie dialogowym **Wybierz harmonogram dystrybucji** wybierz pozycję **1040 - produkty**, a następnie kliknij przycisk **OK**.
> 1. Powtórz kroki poprzedniej procedury, aby sprawdzić, czy utworzono podzadanie **RetailProductRating**.

### <a name="import-product-ratings"></a>Import ocen produktów

Aby zaimportować oceny produktów do Retail z usługi ocen i recenzji, należy wykonać następujące kroki.

1. Przejdź do **Retail \> Ustawienia centrali \> Transfer danych w sieci sprzedaży \> Zadanie synchronizacji ocen produktu**. Możesz również wyszukać frazę „Zadanie synchronizacji ocen produktu”.
1. W oknie dialogowym **Pobierz oceny produktu**, na skróconej karcie **Uruchom w tle** wybierz pozycję **Wielokrotnie**.
1. W oknie dialogowym **Definiuj cykl** ustaw wzorzec cyklu. (Sugerowana wartość wynosi dwie godziny.) Nie planuj cyklu krótszego niż jedna godzina.
1. Kliknij przycisk **OK**.
1. W opcji **Przetwarzanie wsadowe** ustaw wartość **Tak**. To ustawienie pomaga zagwarantować, że dzienniki będą mogły być poddawane inspekcji i sprawdzać stan uruchomienia zadania wsadowego.
1. Kliknij przycisk **OK**, aby zaplanować zadanie wsadowe.

Na poniższej ilustracji pokazano przykład strony konfiguracji zadania wsadowego w Retail.

![Konfiguracja zadania wsadowego Synchronizuj oceny produktów](media/rnr-hq-batchjob-recurrence.png)

## <a name="verify-that-the-batch-job-for-product-rating-synchronization-was-successful"></a>Sprawdź, czy zadanie wsadowe synchronizacji ocen produktu zakończyło się pomyślnie

Aby sprawdzić, czy zadanie wsadowe **Synchronizacja ocen produktów w rozwiązaniu** zostało wykonane pomyślnie, wykonaj następujące kroki.

1. Przejdź do **Retail \> Administrator systemu \> Zapytania \> Zadania wsadowe** lub, jeśli jest używana jednostka magazynowa detaliczna (SKU) dostępna tylko w Retail, **Retail \> Zapytania i raporty \> Zadania wsadowe**. Alternatywnie można wyszukać frazę „zadania wsadowe”.
1. Aby wyświetlić szczegóły zadania wsadowego, na liście zadań wsadowych w kolumnie **Opis zadania** należy wyszukać opis zawierający ciąg „Pobierz oceny produktu”.
1. Umożliwia wybranie identyfikatora zadania w celu wyświetlenia szczegółów zadania wsadowego, np. zaplanowanej daty/godziny i tekstu cyklu.

Na poniższej ilustracji przedstawiono przykładowe szczegóły zadania wsadowego w Reyail, gdy zaplanowano uruchomienie zadania wsadowego w odstępach dwugodzinnych.

![Szczegóły zadania wsadowego Synchronizuj oceny produktów](media/rnr-hq-batchjob-status-checking.png)

## <a name="make-product-ratings-available-at-the-pos"></a>Umożliwia udostępnienie ocen produktów w punkcie sprzedaży

Rozwiązanie oceny i recenzje w Dynamics 365 Commerce jest rozwiązaniem wielokanałowym. Jednak oceny produktów domyślnie nie są wyświetlane w punkcie sprzedaży. Aby ułatwić klientom w sklepach korzystanie z ocen i recenzji, gdy są one pomocne przez partnerów sprzedaży, należy włączyć oceny produktów w punkcie sprzedaży.

Aby włączyć oceny produktu w punkcie sprzedazy, wykonaj następujące czynności.

1. Kliknij kolejno opcje **Retail \> Ustawienia Retail \> Parametry \> Parametry sieci sprzedaży**. Alternatywna metoda polega na wyszukaniu frazy „parametry Retail”.
1. Na karcie **Parametry konfiguracji** wybierz opcję **Nowe**.
1. Wprowadź nazwę, na przykład **RatingsAndReviews.EnableProductRatingsForRetailStores**, i nadaj jej wartość **prawda**.
1. Wybierz opcję **Zapisz**.
1. Wybierz kolejno opcje **Handel detaliczny \> Dane IT sieci sprzedaży \> Harmonogram dystrybucji**. Alternatywna metoda polega na wyszukaniu terminu „harmonogram dystrybucji”.
1. Na liście zadań wybierz pozycję **1110** (**konfiguracja globalna**), a następnie wybierz opcję **Uruchom teraz**.
1. Po pomyślnym uruchomieniu zadania sprawdź, czy oceny produktów są teraz widoczne w punkcie sprzedaży.

Na poniższej ilustracji przedstawiono przykład konfiguracji parametrów Retail w celu włączenia ocen produktów w punkcie sprzedaży.

![Konfiguracja parametrów retail dla ocen produktów w punkcie sprzedaży](media/rnr-hq-enable-ratings-in-pos.png)

Na poniższej ilustracji przedstawiono przykład ocen produktów w POS.

![Oceny produktu w POS](media/rnr-pos-catalog-ratings.png)

Na poniższej ilustracji przedstawiono przykład ocen produktów w kanałach biura obsługi.

![Oceny produktu w kanale biura obsługi](media/rnr-call-center-ratings.png)

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie ocen i recenzji](ratings-reviews-overview.md)

[Zgoda na korzystanie z ocen i recenzji](opt-in-ratings-reviews.md)

[Zarządzanie ocenami i recenzjami](manage-reviews.md)

[Konfigurowanie ocen i recenzji](configure-ratings-reviews.md)
