---
title: Wyszukiwanie produktów i odbiorców w punkcie sprzedaży (POS)
description: Ten temat zawiera omówienie ulepszeń wprowadzonych w produkcie i funkcji wyszukiwania klientów w rozwiązaniu Dynamics 365 Commerce.
author: ShalabhjainMSFT
manager: AnnBe
ms.date: 07/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 141393
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: shajain
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: Retail April 2017 update
ms.openlocfilehash: 415e8268c504487f2b66afc2ac9a50de1b538911
ms.sourcegitcommit: a8201e0b9033c2afc2b1702b0337facaf7ad4b92
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/28/2020
ms.locfileid: "3628916"
---
# <a name="product-search-and-customer-search-in-the-point-of-sale-pos"></a>Wyszukiwanie produktów i odbiorców w punkcie sprzedaży (POS)

[!include [banner](includes/banner.md)]

Aplikacje Modern Point of Sale (MPOS) i Cloud Point of Sale (CPOS) udostępniają funkcję łatwego wyszukiwania produktów i odbiorców. Ponieważ pasek wyszukiwania znajduje się zawsze w górnej części okien aplikacji MPOS i CPOS, pracownicy mogą szybko znajdować produkty i odbiorców.

Pracownicy mogą szukać produktów w asortymentach i katalogach skojarzonych z bieżącym sklepem. Mogą również szukać w asortymentach i katalogach skojarzonych z dowolnym innym sklepem w firmie. Dlatego kasjerzy mogą sprzedawać i zwracać produkty spoza asortymentu sklepu. Podobnie pracownicy mogą wyszukiwać odbiorców skojarzonych z bieżącym sklepem lub dowolnym innym sklepem w firmie. Ponadto pracownicy mogą wyszukiwać odbiorców skojarzonych z inną firmą w organizacji nadrzędnej.

## <a name="product-search"></a>Wyszukiwanie produktu

Domyślnie wyszukiwania produktów są przeprowadzane w asortymencie sklepu. Ten typ wyszukiwania jest nazywany *lokalnym wyszukiwaniem produktu*. Pracownicy mogą jednak łatwo przełączyć się na dowolny katalog skojarzony z bieżącym sklepem lub wyszukać w innym sklepie. Ten typ wyszukiwania jest nazywany *zdalnym wyszukiwaniem produktu*. Aby zmienić katalog, wybierz przycisk **Kategorie** w lewej części tej strony. W górnej części wyświetlonego okienka wybierz przycisk **Zmień katalog**, a następnie wybierz jeden z następujących katalogów do przeglądania. System wyszuka produkty w wybranym katalogu.

Na stronie **Zmień katalog** pracownicy mogą łatwo wybrać dowolny sklep, lub wyszukać produkty we wszystkich sklepach.

![Zmiana katalogu](./media/Changecatalog.png "Zmiana katalogu")

Lokalne wyszukiwanie produktów powoduje wyszukiwanie w następujących właściwościach produktów:

- Numer produktu
- Nazwa produktu
- opis
- Wymiary
- Kod kreskowy
- Alias

### <a name="enhancements-to-local-product-searches"></a>Ulepszenia lokalnych wyszukiwań produktów

Lokalne wyszukiwanie produktów jest teraz bardziej przyjazne dla użytkownika. Wprowadzono również następujące ulepszenia:

- Do paska wyszukiwania dodano menu rozwijane produktu i klienta, aby pracownicy mogli wybrać opcję **Produkt** lub **Klient** przed rozpoczęciem wyszukiwania. Domyślnie wybrana jest opcja **Produkt**, jak pokazano na poniższej ilustracji.
- W przypadku wyszukiwania słów kluczowych (tj. wyszukiwań wykorzystujących terminy) sprzedawcy mogą skonfigurować, czy wyniki wyszukiwania obejmują wyniki zgodne z *dowolnym* wyszukiwanym terminem czy tylko wyniki zgodne ze *wszystkimi* wyszukiwanymi terminami. Ustawienie tej funkcji jest dostępne w profilu funkcji POS, w nowej grupie o nazwie **Wyszukiwanie produktu**. Ustawienie domyślne to **Dopasuj dowolne szukane terminy**. To ustawienie jest także ustawieniem zalecanym. Gdy używane jest ustawienie **Dopasuj dowolne szukane terminy**, wszystkie produkty całkowicie lub częściowo zgodne z co najmniej jednym szukanym terminem są zwracane jako wyniki. Te wyniki są automatycznie sortowane w kolejności rosnącej produktów dopasowanych do największej liczby słów kluczowych (całkowicie lub częściowo).

    Ustawienie **Dopasuj wszystkie szukane terminy** zwraca tylko produkty zgodne ze wszystkimi szukanymi terminami (całkowicie lub częściowo). To ustawienie jest przydatne, gdy nazwy produktów są długie, a pracownicy chcą zobaczyć w wynikach wyszukiwania tylko ograniczoną liczbę produktów. Jednak ten rodzaj wyszukiwania ma dwa ograniczenia:

    - Wyszukiwanie jest przeprowadzane w poszczególnych właściwościach produktu. Na przykład zwracane są tylko produkty, które zawierają wszystkie wyszukiwane słowa kluczowe we właściwości co najmniej jednego produktu.
    - Wymiary nie są przeszukiwane.

- Sprzedawcy mogą teraz konfigurować wyszukiwanie produktu tak, aby wyświetlać sugestie wyszukiwania, gdy użytkownicy wpisują nazwy produktów. Nowe ustawienie tej funkcji jest dostępne w profilu funkcji POS, w grupie o nazwie **Wyszukiwanie produktu**. To ustawienie nosi nazwę **Pokaż sugestie podczas wpisywania**. Ta funkcja może ułatwić pracownikom szybkie znalezienie wyszukiwanego produktu, ponieważ nie muszą wprowadzać ręcznie pełnej nazwy.
- Algorytm wyszukiwania produktów wyszukuje także szukane terminy we właściwości **Wyszukaj nazwę** produktu.

![Sugestie produktów](./media/Productsuggestions.png "Sugestie produktów")

## <a name="customer-search"></a>Wyszukiwanie odbiorcy

Wyszukiwanie odbiorcy służy do znalezienia odbiorców w różnych celach. Kasjerzy mogą na przykład wyświetlić listę życzeń lub historię zakupów odbiorców albo dodać odbiorcę do transakcji. Algorytm wyszukiwania dopasowuje terminy wyszukiwania do wartości obecnych w następujących właściwościach odbiorcy:

- Nazwisko
- Adres e-mail
- Numer telefonu
- Numer karty lojalnościowej
- Adres 
- Numer konta

Wśród tych właściwości nazwa zapewnia największą elastyczność podczas wyszukiwania z wieloma słowami kluczowym, ponieważ algorytm zwraca wszystkich klientów, którzy pasują do któregokolwiek z wyszukiwanych słów kluczowych. Odbiorcy zgodni z większością słów kluczowych są wyświetlani na początku wyników. Ta funkcja pomaga kasjerom w sytuacjach, gdy szukają, wpisując pełne imię i nazwisko, ale nazwisko i imię zostały zamienione podczas wstępnego wprowadzania danych. Jednak ze względu na wydajność wszystkie pozostałe właściwości zachowują kolejność słów kluczowych wyszukiwania. Jeśli więc kolejność słów kluczowych wyszukiwania nie odpowiada kolejności, w jakiej dane są przechowywane, żadne wyniki nie zostaną zwrócone.

Domyślnie wyszukiwanie odbiorców jest wykonywane w książkach adresowych odbiorców skojarzonych ze sklepem. Ten typ wyszukiwania jest nazywany *lokalnym wyszukiwaniem odbiorcy*. Pracownicy mogą jednak wyszukiwać odbiorców globalnie. Inaczej mówiąc, mogą przeszukiwać sklepy w firmie oraz we wszystkich innych firmach. Ten typ wyszukiwania jest nazywany *zdalnym wyszukiwaniem odbiorcy*.

Aby wyszukiwać globalnie, pracownicy mogą wybrać przycisk **Filtruj wyniki** na dole strony, a następnie wybrać opcję **Wyszukaj we wszystkich sklepach**, jak pokazano na poniższej ilustracji. W tym przypadku zwracani są nie tylko odbiorcy. Zwracane są także wszystkie typy jednostek, które nie są częścią żadnej książki adresowej w centrali. Te jednostki obejmują pracowników, dostawców, kontakty i konkurentów.

> [!NOTE]
> Aby zdalne wyszukiwanie odbiorców zwróciło wyniki, należy wprowadzić co najmniej cztery znaki.

W zdalnym wyszukiwaniu odbiorców identyfikator odbiorcy nie jest widoczny dla odbiorców z innych firm, ponieważ żaden identyfikator odbiorcy nie został utworzony dla tych jednostek w bieżącej firmie. Jeżeli jednak pracownik otworzy stronę szczegółów klienta, system automatycznie wygeneruje identyfikator odbiorcy dla jednostki i skojarzy z klientem książkę adresową klienta sklepu. Dlatego odbiorca będzie widoczny w lokalnych wyszukiwaniach sklepu wykonanych później.

![Globalne wyszukiwanie odbiorcy](./media/Globalcustomersearch.png "Globalne wyszukiwanie odbiorcy")

### <a name="enhancements-to-local-customer-search"></a>Ulepszenia lokalnego wyszukiwania odbiorców

Wyszukiwania oparte na numerze telefonu zostały uproszczone. Te wyszukiwania teraz ignorują znaki specjalne, takie jak spacje, łączniki i nawiasy, które mogły zostać dodane podczas tworzenia odbiorcy. Dzięki temu kasjerzy nie muszą się już martwić o formaty numerów telefonów podczas wyszukiwania. Mogą również szukać odbiorców przez wpisanie częściowego numeru telefonu. Jeśli numer telefonu zawiera znaki specjalne, również można go znaleźć, wyszukując numery występujące po znakach specjalnych. Jeżeli na przykład numer telefonu odbiorcy wprowadzono jako **123-456-7890**, kasjer może wyszukać odbiorcę, wpisując **123**, **456**, **7890** lub **1234567890** albo wpisując kilka pierwszych cyfr numeru telefonu.

> [!NOTE]
> Odbiorca może mieć wiele numerów telefonów i wiele wiadomości e-mail. Algorytm wyszukiwania odbiorcy również przeszukuje te pomocnicze wiadomości e-mail i numery telefonów, ale na stronie wyników wyszukiwania odbiorcy jest wyświetlany główny adres e-mail i numer telefonu. Może to spowodować pewne pomyłki, ponieważ zwrócone wyniki odbiorcy nie będą pokazywały poszukiwanego adresu e-mail lub numeru telefonu. W przyszłych zwolnieniach planuje się poprawienie ekranu wyniki wyszukiwania klientów w celu wyświetlenia tych informacji.

Tradycyjne wyszukiwanie odbiorcy może być czasochłonne, ponieważ obejmuje wiele pól. Zamiast tego kasjerzy mogą teraz szukać jedną właściwość klienta, taką jak imię i nazwisko, adres e-mail lub numer telefonu. Właściwości używane przez algorytm wyszukiwania odbiorców są zbiorczo nazywane *kryteriami wyszukiwania odbiorców*. Administrator systemu może w prosty sposób skonfigurować jedno lub więcej kryteriów jako skróty, które będą wyświetlane w aplikacji POS. Ponieważ wyszukiwanie jest ograniczone do jednego kryterium, są wyświetlane tylko pasujące wyniki wyszukiwania, a proces działa znacznie szybciej, niż standardowe wyszukiwanie odbiorców. Poniższa ilustracja przedstawia skróty wyszukiwania odbiorców w aplikacji POS.

![Skróty wyszukiwania odbiorcy](./media/SearchShortcutsPOS.png "Skróty wyszukiwania odbiorcy")

Aby ustawić kryteria wyszukiwania jako skróty, administrator musi otworzyć stronę **Parametry sprzedaży** w aplikacji Commerce , a następnie na karcie **Kryteria wyszukiwania w punkcie sprzedaży** zaznaczyć wszystkie kryteria, które powinny być wyświetlane w postaci skrótów.

![Konfiguruj skróty wyszukiwania](./media/ConfigureShortcutsAX.png "Konfiguruj skróty wyszukiwania")

> [!NOTE]
> Jeśli dodasz zbyt wiele skrótów, menu rozwijane na pasku wyszukiwania w aplikacji POS będzie bardzo nieczytelne, co utrudni pracownikowi wyszukiwanie. Zalecamy, aby dodać tylko potrzebną liczbę skrótów.

Pole **Kolejność wyświetlania** określa kolejność, w jakiej skróty są wyświetlane w aplikacji POS. Wyświetlane kryteria są standardowymi właściwościami używanymi przez algorytm wyszukiwania odbiorców do znajdowania odbiorców. Jednak partnerzy mogą dodawać niestandardowe właściwości jako skróty wyszukiwania. Aby dodać niestandardowe właściwości jako skróty wyszukiwania, administrator systemu musi poszerzyć rozszerzalny element stałotekstowy (enum) używany w kryteriach wyszukiwania odbiorców, a następnie oznaczyć niestandardowe właściwości dostarczone przez partnera jako skróty. Partnerzy są odpowiedzialni za napisanie kodu zapewniającego znajdowanie wyników, gdy ich niestandardowe skróty są używane do wyszukiwania.

> [!NOTE]
> Niestandardowa właściwość dodana do elementu stałotekstowego nie wpływa na standardowy algorytm wyszukiwania odbiorców. Innymi słowy algorytm wyszukiwania odbiorców nie wyszukuje w niestandardowej właściwości. Użytkownicy mogą stosować niestandardową właściwość do wyszukiwania tylko wtedy, gdy jest ona dodana jako skrót albo gdy domyślny algorytm wyszukiwania zostanie zastąpiony.

W nadchodzącej wersji Commerce, sprzedawcy detaliczni będą mogli skonfigurować domyślny tryb wyszukiwania klientów w punkcie sprzedaży, aby **Przeszukiwać wszystkie sklepy**. Ta konfiguracja może być przydatna w scenariuszach, w których klienci, którzy zostali wytworzeniu poza systemem, muszą być natychmiast wyszukiwani (na przykład, jeszcze przed uruchomieniem zadania dystrybucji). Nowa opcja **Domyślny tryb wyszukiwania odbiorców** będzie dostępna w profilu funkcji punktu sprzedaży. Ustaw na **Włączony** aby skonfigurować domyślny tryb wyszukiwania na **Szukaj we wszystkich sklepach**. Każda próba wyszukania odbiorcy spowoduje przetworzenie połączenia w czasie rzeczywistym z centralą.

Aby zapobiec nieoczekiwanem problemom z wydajnością, ta konfiguracja jest ukryta za flagą lotu o nazwie **CUSTOMERSEARCH_ENABLE_DEFAULTSEARCH_FLIGHTING**. Dlatego w celu wyświetlenia ustawienia interfejs użytkownika (UI) **Tryb domyślnego wyszukiwania klientów**, należy utworzyć bilet pomocy technicznej dla systemu testowania akceptacji użytkowników (UAT) i środowisk produkcyjnych. Po otrzymaniu biletu zespół inżynierów będzie pracował ze sprzedawcą, aby upewnić się, że sprzedawca przeprowadza testy w środowiskach nieprodukcyjnych, aby ocenić wydajność i wdrożyć wymagane optymalizacje.

