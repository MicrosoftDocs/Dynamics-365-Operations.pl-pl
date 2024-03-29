---
title: Tworzenie katalogów rozwiązania Commerce dla witryn B2B
description: W tym artykule opisano, jak tworzyć katalogi Commerce dla witryn business-to-business (B2B) Microsoft Dynamics 365 Commerce.
author: ashishmsft
ms.date: 07/11/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2022-02-28
ms.openlocfilehash: 7d4ed3e2a76924c2c3c0ba55e21ba648e8da7b76
ms.sourcegitcommit: d1491362421bf2fcf72a81dc2dc2d13d3b98122b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/11/2022
ms.locfileid: "9136834"
---
# <a name="create-commerce-catalogs-for-b2b-sites"></a>Tworzenie katalogów rozwiązania Commerce dla witryn B2B

[!include [banner](includes/banner.md)]

W tym artykule opisano, jak tworzyć produkty Commerce dla witryn business-to-business (B2B) Microsoft Dynamics 365 Commerce. Aby uzyskać odpowiedzi na najczęściej zadawane pytania dotyczące katalogów Commerce dla stron B2B, zobacz [Katalogi Commerce dla stron B2B FAQ](catalogs-b2b-sites-FAQ.md).

> [!NOTE]
> Ten artykuł dotyczy Dynamics 365 Commerce w wersji 10.0.27 i późniejszych.

Możesz użyć katalogów Commerce, by zidentyfikować produkty, które chcesz oferować w swoich sklepach internetowych B2B. Kiedy tworzysz katalog, określasz sklepy internetowe, w których oferowane są produkty, dodajesz produkty, które chcesz w nim umieścić, a następnie wzbogacasz ofertę produktów, dodając szczegóły dotyczące merchandisingu. Dla każdego sklepu internetowego B2B można utworzyć wiele katalogów, jak pokazano na poniższej ilustracji.

![Podgląd katalogów produktów Commerce.](./media/Commerce_Catalogs.png)

Katalogi produktów Commerce pozwalają zdefiniować następujące informacje:

- **Typ katalogu** – skonfiguruj wartość jako **B2B**. Możesz zdefiniować właściwości katalogu B2B, takie jak hierarchia nawigacji, hierarchia klientów oraz metadane atrybutów dla katalogu. 
- **Hierarchia nawigacji specyficzna dla danego katalogu** – organizacje mogą stworzyć odrębną strukturę kategorii dla swojego katalogu.
- **Metadane atrybutów specyficznych dla danego katalogu** – atrybuty zawierają szczegóły dotyczące produktu. Przypisując atrybuty do kategorii w hierarchii nawigacji, możesz zdefiniować wartości dla tych atrybutów na poziomie produktów, które są przypisane do tej kategorii. Organizacje mogą wtedy wykonać te zadania:

    - Określać wartości atrybutów specyficznych dla danego katalogu.
    - Kontrolować widoczność atrybutów na poziomie katalogu.
    - Wybierz elementy uściślające, które są specyficzne dla danego katalogu.

- **Kanały** – organizacje mogą powiązać więcej niż jeden kanał internetowy B2B z danym katalogiem. Kompleksowe wsparcie dla katalogów jest obecnie dostępne tylko dla sklepów internetowych B2B.
- **Hierarchie klientów** – dla danego kanału B2B organizacje mogą udostępnić konkretny katalog wybranym partnerom B2B poprzez powiązanie hierarchii klientów z tym katalogiem.
- **Grupy cenowe** – możesz skonfigurować ceny i promocje, które są specyficzne dla danego katalogu. Ta możliwość jest głównym powodem definiowania katalogu dla kanału B2B. Grupy cenowe dla katalogów umożliwiają organizacjom udostępnianie produktów docelowym organizacjom B2B i stosowanie preferowanych przez nie cen i zniżek. Klienci B2B, którzy zamawiają ze skonfigurowanego katalogu, mogą korzystać ze specjalnych cen i promocji po zalogowaniu się na stronie Commerce B2B. Aby skonfigurować ceny określonego katalogu, zaznacz opcję **Grupy cenowe** z karty **Katalogi**, aby połączyć jedną lub więcej grup cen z katalogiem. Wszystkie umowy handlowe, czasopisma korygujące ceny i rabaty zaawansowane, które zostały powiązane z tą samą grupą cenową, będą stosowane, gdy klienci będą zamawiać z tego katalogu. (Zniżki zaawansowane obejmują zniżki progowe, ilościowe oraz typu „Rabat łączony”). Więcej informacji o grupach cenowych znajdziesz w części [Grupy cenowe](price-management.md#price-groups).

> [!NOTE]
> Ta funkcja jest dostępna od wersji 10.0.27 Dynamics 365 Commerce. Aby skonfigurować specyficzne dla katalogu konfiguracje, takie jak hierarchia nawigacji i hierarchia klientów, w centrali Commerce headquarters otwórz przestrzeń roboczą **Zarządzanie funkcjami** (**Administracja systemu \> Obszary robocze \> Zarządzanie funkcjami**), włącz funkcję **Umożliwienie korzystania z wielu katalogów w kanałach sprzedaży detalicznej**, a następnie uruchom zadanie **1110 CDX**. Po włączeniu tej funkcji wszystkie istniejące katalogi, które są używane w punktach sprzedaży lub w call center, zostaną oznaczone jako **Typ katalogu = B2C** na stronie **Katalogi**. Tylko istniejące i nowe katalogi oznaczone jako **Typ katalogu = B2C** mogą być stosowane w punktach sprzedaży i call center. 

## <a name="b2b-catalog-process-flow"></a>Przepływ procesu katalogu B2B

Proces tworzenia i przetwarzania katalogu składa się z czterech ogólnych kroków. Każdy krok jest szczegółowo opisany w następnym rozdziale.

> [!NOTE]
> Zanim przejdziesz dalej, upewnij się, że katalog jest oznaczony jako **Typ katalogu = B2B**.

1. **[Konfiguracja](#configure-the-catalog)**

    - Przyporządkuj hierarchię nawigacyjną.
    - Określ daty obowiązywania i wygaśnięcia, jeśli mają zastosowanie.
    - Dodawaj i kategoryzuj produkty.
    - Skojarz grupy cenowe.
    - Stwórz hierarchię klientów, która jest specyficzna dla twoich organizacji B2B. 
    - Przydziel domyślną grupę atrybutów wymiarów dla rafinerów takich jak rozmiar, styl i kolor.
    - Metadane ustawiania atrybutu.

1. **[Weryfikacja](#validate-the-catalog)** – w tym kroku uruchamiasz reguły walidacji, które wymuszają określone zachowanie. Oto kilka przykładów:

    - Upewnij się, że nie ma tam produktów nieskategoryzowanych.
    - Upewnij się, że wszystkie elementy, które są przypisane do każdego kanału, są powiązane z katalogiem.

1. **[Potwierdzenie](#approve-the-catalog)**
1. **[Publikowanie](#publish-the-catalog)**

## <a name="set-up-the-catalog"></a>Skonfiguruj katalog

Wykorzystaj informacje zawarte w tym rozdziale, by skonfigurować swój katalog.

### <a name="configure-the-catalog"></a>Skonfiguruj katalog

W centrali Commerce przejdź do **Retail i Commerce \> Katalogi i asortymenty \> Wszystkie katalogi**, aby skonfigurować swój katalog.

Kiedy tworzysz nowy katalog, musisz najpierw powiązać go z jednym lub kilkoma kanałami. Podczas tworzenia katalogu mogą być używane tylko te elementy, które są powiązane z wybranym przez ciebie kanałem [asortyment](/dynamics365/unified-operations/retail/assortments). Aby powiązać katalog z jednym lub kilkoma kanałami, wybierz **Dodaj** na karcie **Kanały handlowe** na stronie **Ustawienia katalogu**. Upewnij się, że katalog jest oznaczony jako **Typ katalogu = B2B**.

#### <a name="associate-the-navigation-hierarchy"></a>Przyporządkuj hierarchię nawigacyjną

Aby dodać produkty do katalogu, musisz wybrać hierarchię nawigacji. Hierarchia nawigacji będzie obsługiwać strukturę kategorii dla katalogu. Musisz wybrać jedną z hierarchii nawigacji powiązanych z kanałami, które wybrałeś na skróconej karcie **Kanały handlowe** na stronie **Ustawienia katalogu**. Aby przypisać domyślną hierarchię nawigacji do każdego ze swoich kanałów, przejdź do **Retail i Commerce \> Konfiguracja Channel \> Kategorie kanałów i atrybuty produktów**.

#### <a name="specify-time-effective-and-expiration-dates"></a>Określ daty obowiązywania i wygaśnięcia

Aby określić daty ważności i wygaśnięcia katalogu, wybierz najwyższy węzeł hierarchii katalogów, aby powrócić do widoku nagłówka katalogu głównego. Następnie, na skróconej karcie **Ogólne**, skonfiguruj odpowiednio daty ważności i skuteczności.

#### <a name="add-and-categorize-products"></a>Dodawaj i kategoryzuj produkty

Aby skonfigurować produkty, które mają być dodawane do katalogu, w centrali Commerce przejdź do **Retail i Commerce \> Katalogi i asortymenty \> Wszystkie katalogi**. Następnie w zakładce **Katalogi** wybierz **Dodaj produkty**.

Możesz też wybrać węzeł w hierarchii nawigacji. Będziesz mógł wtedy dodawać produkty bezpośrednio do kategorii w katalogu.

#### <a name="associate-price-groups"></a>Skojarz grupy cenowe

Aby skonfigurować produkty, które mają być dodawane do katalogu, w centrali Commerce przejdź do **Retail i Commerce \> Katalogi i asortymenty \> Wszystkie katalogi**. Następnie w zakładce **Katalogi** wybierz **Dodaj produkty**. 

Produkty, które zostały dodane do katalogu z głównego węzła hierarchii nawigacyjnej przez wybranie **Dodaj produkty** w oknie akcji, będą dziedziczyły swoje kategorie, jeśli źródłowa hierarchia nawigacyjna jest również powiązana z katalogiem. Zmiany kategorii wprowadzone w hierarchii nawigacyjnej źródła zostaną natychmiast odzwierciedlone w katalogach. Aby zaktualizować kanały, musisz ponownie opublikować katalogi.

Możesz też wybrać węzeł w hierarchii nawigacyjnej i dodać produkty bezpośrednio do wybranej kategorii w katalogu. 

Podczas dodawania produktów będzie dostępna opcja **Automatycznie dołączaj wszystkie warianty, gdy wybrana jest tylko matryca produktu**. Aby zapobiec dołączeniu wszystkich wariantów, wybierz przynajmniej jeden wariant dla matrycy produktu. 

> [!NOTE]
> Jeśli zdecydujesz się na automatyczne uwzględnienie wszystkich wariantów w dużym wyborze mistrzów produktu, możesz doświadczyć dłuższego czasu przetwarzania. W przypadku dużych selekcji zalecamy wybranie opcji **Włącz wszystkie warianty** w oknie akcji na stronie katalogów, aby przeprowadzić operację w trybie wsadowym. Jeśli w katalogu zamieściłeś tylko główny produkt, a nie zamieściłeś żadnych wariantów, to przy przechodzeniu do strony ze szczegółami produktu może nie być dostępny selektor wariantów. 

Aby skonfigurować ceny specyficzne dla katalogu, musisz powiązać jedną lub więcej grup cenowych z katalogiem. Aby powiązać grupy cenowe z katalogiem, w centrali Commerce przejdź do **Retail i Commerce \> Katalogi i asortymenty \> Wszystkie katalogi**. Następnie w zakładce **Katalogi**, w sekcji **Ceny**, wybierz **Grupy cenowe**. Wszystkie umowy handlowe, arkusze korekt cen i zaawansowane rabaty detaliczne (progowe, ilościowe, rabaty łączone), które zostały połączone z tą samą grupą cenową, będą stosowane podczas zamawiania z tego katalogu przez odbiorców.

Więcej informacji o grupach cenowych znajdziesz w sekcji [Grupy cenowe](price-management.md#price-groups).

> [!NOTE]
> Nie można utworzyć nowej grupy cenowej ze strony **Wszystkie katalogi**. Zamiast tego musisz utworzyć ją na stronie **Wszystkie grupy cenowe**. Następnie musisz powiązać go z katalogiem na stronie **Wszystkie katalogi**.

#### <a name="associate-a-customer-hierarchy"></a>Utwórz hierarchię klientów

Aby powiązać hierarchie klientów, w centrali Commerce przejdź do **Retail i Commerce \> Katalogi i asortymenty \> Wszystkie katalogi**. Następnie w zakładce **Katalogi**, w sekcji **Hierarchia klientów**, wybierz **Przydziel hierarchie**, aby połączyć jedną lub więcej hierarchii klientów z katalogiem.

> [!NOTE]
> Nie możesz utworzyć nowej hierarchii klientów z poziomu **Wszystkie katalogi**. Zamiast tego musisz utworzyć ją na stronie **Hierarchie klientów**. Następnie musisz powiązać go z katalogiem na stronie **Wszystkie katalogi**.

#### <a name="associate-default-dimension-attribute-group-for-refiners-such-as-size-style-and-color"></a>Przydziel domyślną grupę atrybutów wymiarów dla rafinerów takich jak rozmiar, styl i kolor

Aby przypisać domyślną grupę atrybutów wymiarów dla elementów uściślających, takich jak rozmiar, styl i kolor, w centrali Commerce przejdź do **Retail i Commerce \> Katalogi i asortymenty \> Wszystkie katalogi**. Następnie w zakładce **Katalogi**, w sekcji **Atrybuty** wybierz **Grupy atrybutów**.

#### <a name="set-attribute-metadata"></a>Metadane ustawiania atrybutu

Aby skonfigurować metadane atrybutów, w centrali Commerce przejdź do **Retail i Commerce \> Katalogi i asortymenty \> Wszystkie katalogi**. Następnie w zakładce **Katalogi**, w sekcji **Atrybuty** wybierz **Ustaw metadane atrybutów**. Aby wybrać atrybuty, które powinny być widoczne i redefiniowalne, wybierz kategorię w powiązanej hierarchii nawigacji specyficznej dla danego katalogu, a następnie w zakładce **Atrybuty produktów katalogowych** wybierz atrybut. Następnie wybierz **Pokaż atrybut na kanale**. Domyślnie wszystkie atrybuty, które można przeglądać, można także przeszukiwać. Aby opcjonalnie uczynić atrybuty rafinowalnymi, zaznacz **Mogą być rafinowane**.

### <a name="validate-the-catalog"></a>Weryfikacja katalogu

Zanim nowy katalog będzie dostępny do użytku, musi zostać zatwierdzony i opublikowany.

Aby sprawdzić poprawność katalogu, należy wykonać poniższe kroki.

1. W zakładce **Katalogi** na stronie **Wszystkie katalogi**, pod **Walidacja** wybierz **Waliduj katalog**, aby przeprowadzić walidację. Ten krok jest wymagany. Upewni się, że wymagane ustawienia są prawidłowe.
1. Wybierz **Wyświetl wyniki**, aby zobaczyć szczegóły weryfikacji. Jeśli zostaną wykryte błędy, musisz poprawić dane, a następnie ponownie uruchomić walidację, aż przejdzie ona pozytywnie.

> [!NOTE]
> Jeśli **Typ katalogu = B2B**, weryfikacja nie powiedzie się, jeśli dodasz do katalogu punkty sprzedaży lub call center. Katalogi B2B muszą mieć przypisane wyłącznie kanały internetowe B2B. Walidacja nie powiedzie się także wtedy, gdy do katalogu B2B nie jest przypisana żadna hierarchia klientów. 

### <a name="approve-the-catalog"></a>Zatwierdzenie katalogu

Po zatwierdzeniu katalogu musi on zostać zatwierdzony.

Aby uruchomić przepływ zatwierdzania katalogów, wykonaj poniższe kroki.

1. W okienku akcji na stronie **Wszystkich katalogów** wybierz **Przepływ pracy \> Prześlij**.
1. Przejdź do sekcji **Retail i Commerce \> Konfiguracja centrali \> Przepływy pracy w Commerce**, aby skonfigurować kroki i autoryzowanych użytkowników dla przepływu pracy. Przepływ pracy zdefiniuje kroki, które są wymagane, aby katalog znalazł się w stanie **Zatwierdzony**.

### <a name="publish-the-catalog"></a>Publikowanie katalogu

Gdy katalog ma status **Zatwierdzony**, możesz go opublikować, wybierając **Publikuj** z menu **Katalogi**. Gdy katalog znajdzie się w stanie **Opublikowano**, można go używać w biurze obsługi w procesach wprowadzania zamówień i wysyłania katalogów. Katalog możesz opublikować ręcznie lub za pomocą procesu wsadowego. Data wejścia w życie, którą zdefiniowałeś dla katalogu, określa, od kiedy produkty są dostępne w sklepie internetowym. Zdefiniowana przez ciebie data ważności decyduje o tym, kiedy produkty zostaną usunięte ze sklepu internetowego.

> [!NOTE]
> Możesz opublikować katalog zawierający produkty, które mają ostrzeżenia. Produkty te nie pojawią się jednak w sklepie internetowym.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Wpływ rozszerzalności katalogów Commerce na dostosowanie B2B](catalogs-b2b-sites-dev.md)

[Katalogi Commerce dla B2B FAQ](catalogs-b2b-sites-FAQ.md)

[Moduł selektora katalogów](catalog-picker.md)
