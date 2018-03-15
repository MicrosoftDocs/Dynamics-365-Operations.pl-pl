---
title: "Wyszukiwanie produktów i odbiorców w POS"
description: "Ten temat zawiera omówienie ulepszeń wprowadzonych w produkcie i funkcji wyszukiwania klientów w rozwiązaniu Dynamics 365 for Retail."
author: ShalabhjainMSFT
manager: AnnBe
ms.date: 08/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application user
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 141393
ms.assetid: 
ms.search.region: Global
ms.search.industry: Retail
ms.author: shajain
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: Retail April 2017 update
ms.translationtype: HT
ms.sourcegitcommit: ea07d8e91c94d9fdad4c2d05533981e254420188
ms.openlocfilehash: 2af45de0d63b01e71b5009e2f62cfdff6844da7d
ms.contentlocale: pl-pl
ms.lasthandoff: 02/07/2018

---

# <a name="overview-of-product-and-customer-search-in-point-of-sale"></a>Przegląd produktu i wyszukiwania klientów w punkcie sprzedaży

[!include[banner](includes/banner.md)]

Aplikacje Modern Point of Sale (MPOS) i Cloud Point of Sale (CPOS) udostępniają funkcję łatwego wyszukiwania, która umożliwia pracownikom sklepu szybkie wyszukiwanie produktów i klientów. Pasek wyszukiwania znajduje się zawsze w górnej części aplikacji MPOS i CPOS, aby umożliwić pracownikom szybkie znalezienie produktów i klientów.

Pracownicy mogą wyszukiwać produkty w asortymencie i katalogach skojarzonych z bieżącym sklepem oraz asortymencie i katalogach skojarzonych z innymi sklepami w firmie. Dlatego kasjerzy mogą sprzedawać i zwracać produkty spoza asortymentu sklepu. Podobnie pracownicy mogą wyszukiwać klientów skojarzonych z bieżącym sklepem lub dowolnym innym sklepem w firmie. Ponadto pracownicy mogą wyszukiwać klientów skojarzonych z inną firmą w organizacji nadrzędnej.

## <a name="product-search"></a>Wyszukiwanie produktu 

Domyślnie wyszukiwanie produktu jest przeprowadzane w asortymencie sklepu. Ten typ wyszukiwania jest nazywany *lokalnym wyszukiwaniem produktu*. Pracownicy mogą jednak łatwo przełączyć się na dowolny katalog skojarzony z bieżącym sklepem lub wyszukać w innym sklepie. Ten typ wyszukiwania jest nazywany *zdalnym wyszukiwaniem produktu*. Aby zmienić katalog, wybierz przycisk **Kategorie** w lewej części tej strony. W górnej części wyświetlonego okienka wybierz przycisk **Zmień katalog**, a następnie wybierz jeden z następujących katalogów do przeglądania. System wyszuka produkty w wybranym katalogu.

Na stronie **Zmień katalog** pracownicy mogą łatwo wybrać dowolny sklep, lub wyszukać produkty we wszystkich sklepach.

![Zmiana katalogu](./media/Changecatalog.png "Zmiana katalogu")
 
Lokalne wyszukiwanie produktów powoduje wyszukiwanie w następujących właściwościach produktu:

- Numer produktu
- Nazwa produktu
- opis
- Wymiary
- Kod kreskowy
- Alias

### <a name="enhancements-to-local-product-searches"></a>Ulepszenia lokalnych wyszukiwań produktów

Lokalne wyszukiwanie produktów jest bardziej przyjazne dla użytkownika. Wprowadzono również następujące ulepszenia:

- Do paska wyszukiwania dodano menu rozwijane produktu i klienta, aby pracownicy mogli wybrać opcję **Produkt** lub **Klient** przed rozpoczęciem wyszukiwania. Domyślnie wybrana jest opcja **Produkt**, jak pokazano na poniższej ilustracji.
- W przypadku wyszukiwania słów kluczowych (tj. wyszukiwań wykorzystujących terminy) sprzedawcy mogą skonfigurować, czy wyniki wyszukiwania obejmują wyniki zgodne z dowolnym wyszukiwanym terminem czy tylko wyniki zgodne ze wszystkimi wyszukiwanymi terminami. To ustawienie jest dostępne w profilu funkcji POS, w nowej grupie o nazwie **Wyszukiwanie produktu**. Ustawienie domyślne to **Dopasuj dowolne szukane terminy**. To ustawienie jest także ustawieniem zalecanym. Gdy używane jest ustawienie **Dopasuj dowolne szukane terminy**, wszystkie produkty całkowicie lub częściowo zgodne z co najmniej jednym szukanym terminem są zwracane jako wyniki, które są automatycznie sortowane w kolejności rosnącej produktów dopasowanych do największej liczby słów kluczowych (całkowicie lub częściowo).

    Ustawienie **Dopasuj wszystkie szukane terminy** zwraca tylko produkty zgodne ze wszystkimi szukanymi terminami (całkowicie lub częściowo). To ustawienie jest przydatne, gdy nazwy produktów są długie, a pracownicy chcą zobaczyć w wynikach wyszukiwania tylko ograniczoną liczbę produktów. Jednak ten rodzaj wyszukiwania ma dwa ograniczenia:

    - Wyszukiwanie jest przeprowadzane w poszczególnych właściwościach produktu. Na przykład zwracane są tylko produkty, które zawierają wszystkie wyszukiwane słowa kluczowe we właściwości co najmniej jednego produktu.
    - Wymiary nie są przeszukiwane.

- Sprzedawcy mogą teraz konfigurować wyszukiwanie produktu tak, aby wyświetlać sugestie wyszukiwania, gdy użytkownicy wpisują nazwy produktów. Nowe ustawienie tej funkcji jest dostępne w profilu funkcji POS, w grupie o nazwie **Wyszukiwanie produktu**. To ustawienie nosi nazwę **Pokaż sugestie podczas wpisywania**. Ta funkcja może ułatwić pracownikom szybkie znalezienie wyszukiwanego produktu, ponieważ nie muszą wprowadzać ręcznie pełnej nazwy.
- Algorytm wyszukiwania produktów wyszukuje także szukane terminy we właściwości **Wyszukaj nazwę** produktu.

![Sugestie produktów](./media/Productsuggestions.png "Sugestie produktów")

## <a name="customer-search"></a>Wyszukiwanie odbiorcy

Wyszukiwanie odbiorcy służy do znalezienia odbiorców w różnych celach. Kasjerzy mogą na przykład wyświetlić listę życzeń lub historię zakupów odbiorców albo dodać odbiorcę do transakcji. W przypadku wyszukiwania wielu słów kluczowych algorytm wyszukiwania odbiorcy zwraca wszystkich odbiorców zgodnych z dowolnym wyszukiwanym słowem kluczowym. Jednakże odbiorcy zgodni z większością słów kluczowych są wyświetlani na początku wyników. To zachowanie jest analogiczne do sposobu wyświetlania wyników przez inne mechanizmy wyszukiwania. Najpierw pokazują wyniki zgodne z największą liczbą wyszukiwanych terminów most, a następnie wyniki częściowo zgodne z wyszukiwanymi słowami kluczowymi. To zachowanie pomaga kasjerom w sytuacjach, gdy używają wielu słów kluczowych w wyszukiwaniu, ale jedno ze słów kluczowych zawiera błąd pisowni.

Domyślnie wyszukiwanie odbiorców jest wykonywane w książkach adresowych odbiorców skojarzonych ze sklepem. Ten typ wyszukiwania jest nazywany *lokalnym wyszukiwaniem odbiorcy*. Pracownicy mogą jednak wyszukiwać odbiorców globalnie. Inaczej mówiąc, mogą przeszukiwać sklepy w firmie oraz we wszystkich innych firmach. Ten typ wyszukiwania jest nazywany *zdalnym wyszukiwaniem odbiorcy*.

Aby wyszukiwać globalnie, pracownicy mogą wybrać przycisk **Filtruj wyniki** na dole strony, a następnie wybrać opcję **Wyszukaj we wszystkich sklepach**, jak pokazano na poniższej ilustracji. W tym przypadku zwracani są nie tylko odbiorcy. Zwracane są także wszystkie typy jednostek, które nie są częścią żadnej książki adresowej w centrali. Te jednostki obejmują pracowników, dostawców, kontakty i konkurentów.

> [!NOTE]
> Aby zdalne wyszukiwanie odbiorców zwróciło wyniki, należy wprowadzić co najmniej cztery znaki.

W zdalnym wyszukiwaniu odbiorców identyfikator odbiorcy nie jest widoczny dla odbiorców z innych firm, ponieważ żaden identyfikator odbiorcy nie został utworzony dla tych jednostek w bieżącej firmie. Jeżeli jednak pracownik otworzy stronę szczegółów klienta, system automatycznie wygeneruje identyfikator odbiorcy dla jednostki i skojarzy z klientem książkę adresową klienta sklepu. Dlatego odbiorca będzie widoczny w lokalnych wyszukiwaniach sklepu wykonanych później.

![Globalne wyszukiwanie odbiorcy](./media/Globalcustomersearch.png "Globalne wyszukiwanie odbiorcy")

### <a name="enhancements-to-local-customer-searches"></a>Ulepszenia lokalnych wyszukiwań odbiorców

Lokalne wyszukiwania odbiorców ułatwia pracownikom znalezienie odbiorców według numeru telefonu. Pracownicy nie muszą wpisywać żadnych znaków specjalnych, które zostały dodane do numeru telefonu odbiorcy, na przykład spacji, myślników lub nawiasów. Mimo że kasjerzy mogą zapisać numery telefonu w dowolnym formacje (mogą na przykład dodać nawiasy, myślniki, symbole itd.), mogą także wyszukiwać odbiorców, wpisując częściowy numer telefonu. Jeżeli kasjer dodał znaki specjalne przy wprowadzaniu numeru telefonu, inni kasjerzy mogą znaleźć odbiorcę, wpisując cyfry widoczne po znakach specjalnych. Jeżeli na przykład numer telefonu odbiorcy wprowadzono jako **123-456-7890**, kasjer może wyszukać odbiorcę, wpisując **123**, **456**, **7890** lub **1234567890** albo wpisując kilka pierwszych cyfr numeru telefonu.

