---
title: Katalogi Commerce dla B2B FAQ
description: Ten temat zawiera odpowiedzi na często zadawane pytania dotyczące katalogów Microsoft Dynamics 365 Commerce.
author: ashishmsft
ms.date: 05/18/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2022-02-28
ms.openlocfilehash: 5bdc7dfcb0e48aa85db2db4d178c5bf62ea0411b
ms.sourcegitcommit: bca0cb730307948368a9aabe322cf963688ed8b1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/19/2022
ms.locfileid: "8782869"
---
# <a name="commerce-catalogs-for-b2b-faq"></a>Katalogi Commerce dla B2B FAQ

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Ten temat zawiera odpowiedzi na najczęściej zadawane pytania dotyczące [katalogów business-to-business (B2B)](catalogs-b2b-sites.md) Microsoft Dynamics 365 Commerce.

## <a name="why-cant-i-configure-a-catalog-specific-navigation-hierarchy-or-see-an-option-to-associate-a-customer-hierarchy"></a>Dlaczego nie mogę skonfigurować hierarchii nawigacji specyficznej dla danego katalogu ani nie widzę opcji powiązania z hierarchią klientów?

Upewnij się, że funkcja **Zezwalaj na korzystanie z wielu katalogów w kanałach sprzedaży detalicznej** jest włączona w obszarze roboczym **Zarządzanie funkcjami** w centrali Commerce. Dodatkowo upewnij się, że twoje środowisko używa Commerce w wersji 10.0.27 lub nowszej.

## <a name="can-i-view-the-catalog-specific-hierarchy-and-enrich-category-pages-in-commerce-site-builder"></a>Czy mogę wyświetlić hierarchię katalogów i wzbogacić strony kategorii w kreatorze witryn Commerce?

Tak, użytkownicy kreatora witryn Commerce, którzy mają dostęp do strony **Produkty**, mogą wybrać katalog i zobaczyć hierarchię specyficzną dla danego katalogu. Na stronie **Produkty** użytkownicy mogą również wzbogacać stronę kategorii dla określonej kategorii w katalogu. Aby uzyskać więcej informacji, zapoznaj się z tematem [Wzbogacanie strony docelowej kategorii](enrich-category-page.md). Jeśli chcesz mieć wzbogacenie specyficzne dla danego katalogu, zalecamy, byś miał dla niego odrębną i unikalną hierarchię nawigacyjną.

## <a name="can-a-b2b-shopper-purchase-from-multiple-catalogs-in-a-single-checkout"></a>Czy klient sklepu B2B może dokonywać zakupów z wielu katalogów w jednej kasie?

Tak, zakupy z wielu katalogów w jednej kasie są dozwolone. Klienci B2B mogą użyć wskaźnika katalogu w widoku koszyka, aby określić, które elementy zostały dodane z którego katalogu.

## <a name="if-a-b2b-shopper-purchases-the-same-item-from-different-catalogs-what-is-the-expected-behavior"></a>Jeśli klient sklepu B2B kupuje ten sam przedmiot w różnych katalogach, jakie jest jego oczekiwane zachowanie?

Mimo że dany użytkownik może mieć w danym momencie dostęp do wielu katalogów, oczekuje się, że produkty w tych katalogach będą się wzajemnie wykluczać. Innymi słowy, w idealnej sytuacji ten sam produkt nie powinien być częścią więcej niż jednego katalogu dla danego użytkownika.

Jeśli jednak pojawi się sytuacja, w której ten sam produkt należy do wielu katalogów, system będzie utrzymywał wiele linii koszyka dla tego produktu. Dla każdego katalogu będzie osobny wiersz. Ten sam produkt z dwóch różnych katalogów nie zostanie połączony przy kasie.

## <a name="when-a-b2b-shopper-is-shopping-is-there-any-validation-for-catalog-availability"></a>Kiedy klient B2B robi zakupy, czy dostępność katalogu jest w ogóle ważna?

Tak. Klient sklepu B2B będzie mógł przejść do kasy tylko wtedy, gdy wszystkie pozycje w koszyku będą pochodziły z ważnych katalogów. Jeśli jakieś elementy koszyka pochodzą z wygasłych lub wycofanych katalogów, zostaną one usunięte, a użytkownik zostanie o tym poinformowany.

## <a name="during-the-shopping-experience-are-search-and-product-discovery-including-related-and-recommended-product-collections-catalog-specific"></a>Czy podczas zakupów wyszukiwanie i odkrywanie produktów (w tym kolekcji produktów powiązanych i polecanych) jest specyficzne dla katalogu?

Tak. Gdy tylko użytkownik wybierze konkretny katalog, cała podróż zakupowa staje się specyficzna dla katalogu. Ta podróż obejmuje doświadczenia związane z odkrywaniem produktów, takie jak sugestie wyszukiwania, wyniki wyszukiwania, wyniki kategorii, elementy uściślające, ceny, atrybuty i polecane produkty (takie jak nowe, najlepiej sprzedające się, trendy, często kupowane razem i produkty powiązane).

## <a name="can-a-b2b-shopper-purchase-from-the-default-assortment-catalogid0"></a>Czy klient sklepu B2B może dokonać zakupu z domyślnego asortymentu (catalogID=0)?

Nie, klienci B2B nie mogą dokonywać zakupów z domyślnego asortymentu. Ten asortyment jest przeznaczony wyłącznie do anonimowego przeglądania. Jeśli klient sklepu B2B nie ma przypisanych katalogów (oczekujących na aktualizację ze strony administracji), nie będzie mógł zobaczyć żadnych katalogów, z których mógłby wybierać, nie będzie też widoczna hierarchia kategorii.

## <a name="can-marketing-content-be-curated-for-a-product-that-is-specific-to-a-catalog"></a>Czy treści marketingowe mogą być tworzone dla produktów, które są specyficzne dla danego katalogu?

Obecnie wzbogacanie produktów jest obsługiwane tylko na poziomie ośrodka i kanału. Innymi słowy, jeśli produkt jest wzbogacony, jest on współdzielony w wielu katalogach, a odpowiadająca mu strona szczegółów produktu (PDP) dla tego produktu będzie renderowana w ten sam sposób we wszystkich katalogach dla danej witryny.

## <a name="is-catalog-support-available-for-both-b2b-and-business-to-consumer-b2c-online-channels"></a>Czy obsługa katalogów jest dostępna zarówno dla kanałów internetowych B2B, jak i business-to-consumer (B2C)?

Obecnie katalogi Commerce są przeznaczone wyłącznie do pracy w kanałach B2B.

## <a name="can-we-set-up-catalog-specific-upsellcross-sell-items"></a>Czy możemy ustawić pozycje upsell/cross-sell specyficzne dla danego katalogu?

Obecnie obsługiwana jest tylko funkcjonalność produktów powiązanych. Dla call center dostępne są jednak konfiguracje elementów upsell i cross-sell.

Następujące funkcje są również obsługiwane tylko dla centrów obsługi:

- Kod źródłowy katalogu
- Używanie identyfikatora źródła do śledzenia kosztów i wskaźników odpowiedzi
- Skrypty zamówień i przedmiotów specyficzne dla danego katalogu
- Analiza strony katalogu
- Zapotrzebowania na katalog
- Harmonogramy płatności
- Darmowe produkty oparte na kodach źródłowych

## <a name="can-we-use-catalog-source-codes-for-b2b-orders-through-the-e-commerce-portal"></a>Czy możemy używać kodów źródłowych z katalogów przy zamówieniach B2B przez portal e-commerce?

Nie Kody źródłowe katalogów są obsługiwane tylko dla kanałów centrum obsługi.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Tworzenie katalogów Commerce dla stron B2B](catalogs-b2b-sites.md)

[Wpływ rozszerzalności katalogów Commerce na dostosowanie B2B](catalogs-b2b-sites-dev.md)
