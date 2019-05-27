---
title: Katalogi biura obsługi
description: W tym artykule opisano funkcje katalogów specyficzne dla biur obsługi dostępne w Microsoft Dynamics 365 for Retail.
author: josaw1
manager: AnnBe
ms.date: 05/15/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailMCRChannelDetailPage, RetailCatalogDetails
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 16231
ms.assetid: f28a827c-3a50-4d5e-83eb-e5a768db70a1
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 65c1c3070aa48bf7a2016534071693716fabe831
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1562749"
---
# <a name="call-center-catalogs"></a>Katalogi biura obsługi

[!include [banner](includes/banner.md)]

W tym temacie opisano funkcje powiązane z możliwościami katalogów specyficzne dla biur obsługi dostępne w Microsoft Dynamics 365 for Retail.

Funkcje katalogu w programie Dynamics 365 for Retail mogą służyć do wielu celów. Początkowo funkcje katalogu utworzono do obsługi integracji z systemami handlu elektronicznego innych producentów. W konfiguracji katalogu firmy mogły tworzyć grupy produktów i atrybutów przeznaczonych do opublikowania na zewnątrz, tak aby mogły być wykorzystywane przez systemy handlu elektronicznego innych producentów.

Jeśli do Dynamics 365 for Retail dodano wsparcie biura obsługi, projekt katalogu został rozszerzony w celu dodania dodatkowych możliwości obsługi i zarządzania funkcjami związane z tradycyjnymi katalogami marketingu bezpośredniego. Firma sprzedająca bezpośrednio konsumentom często tworzy drukowane katalogi, które następnie są wysyłane pocztą do klientów z jednego lub więcej segmentów. Te katalogi zazwyczaj będą zawierać specjalne promocje lub oferty, które zostaną zrealizowane, jeśli w czasie tworzenia zamówienia klient przedstawi kod identyfikacyjny katalogu.

Firmy prowadzące działalność marketingową kierowane bezpośrednio do konsumentów bardzo koncentrują się na śledzeniu reakcji na te katalogi, aby mieć pewność, że koszty produkcji i wysyłki tych katalogów pocztą są uzasadnione. Aby śledzić odpowiedzi, na tylnej części katalogu drukowany jest zazwyczaj kod, o którego podanie jest proszony odbiorca katalogu, który dzwoni, aby złożyć zamówienie przez telefon (lub który należy wprowadzić w czasie składania zamówienia przez internet). W branży istnieje wiele różnych terminów na kod śledzenia katalogu (w tym kod klucza, kod promocyjny, kod katalogu, kod źródłowy), w wypadku Dynamics 365 for Retail określamy go mianem **Identyfikatora kodu źródłowego**.

## <a name="basic-catalog-setup"></a>Podstawowa konfiguracja katalogu

Wybierz kolejno opcje **Handel detaliczny** \> **Katalogi i asortymenty** \> **Wszystkie katalogi** i skonfiguruj katalog.

Podczas tworzenia nowego katalogu, należy najpierw połączyć katalog z jednym lub kilkoma kanałami sprzedaży detalicznej. Jest to wykonywane na skróconej karcie **Kanały sprzedaży detalicznej** w formularzu **Konfiguracja katalogu**. Kliknij przycisk **Dodaj** i wybierz jeden lub więcej kanałów sprzedaży detalicznej. Podczas tworzenia katalogu można używać tylko elementów połączonych z wybranymi [asortymentami](https://docs.microsoft.com/dynamics365/unified-operations/retail/assortments) kanału.

Aby dodać produkty do katalogu, należy wybrać hierarchię nawigacji. Hierarchia nawigacji będzie obsługiwać strukturę kategorii dla katalogu. Należy wybrać jedną z hierarchii nawigacji połączoną z kanałami sprzedaży wybranymi w skróconej karcie **Kanały sprzedaży** na stronie **Katalog**. Jeśli kanał nawigacji nie był wcześniej połączony z kanałem, wybierz kolejno opcje **Handel detaliczny** \> **Ustawienia kanału** \> **Kategorie kanału sprzedaży i atrybuty produktów** i połącz domyślne wartości hierarchii nawigacji z poszczególnymi kanałami sprzedaży detalicznej.

Na karcie menu **Katalogi** na stronie **Ustawienia katalogu** kliknij przycisk **Dodaj produkty**, aby skonfigurować produkty przeznaczone do dodania do katalogu, lub zaznacz węzeł w hierarchii nawigacji (zaznaczenie węzła spowoduje zmianę wyglądu ekranu i pozwoli dodawać produkty bezpośrednio do kategorii w katalogu).

Kliknij górny węzeł w hierarchii katalogów, aby powrócić do widoku nagłówka katalogu głównego. Skonfiguruj wymagane dany wejścia w życie i ważności na skróconej karcie **Ogólne**.

Zanim katalog będzie dostępny do użycia, należy go opublikować. Kliknij przycisk **Weryfikacja katalogu** w menu **Katalogi**, aby wykonać sprawdzanie poprawności. Jest wymagana akcja, która będzie sprawdzać, czy wymagane ustawienia są prawidłowe. Kliknij przycisk **Wyświetl wyniki**, aby zobaczyć szczegóły weryfikacji. Jeśli zostaną znalezione błędy, należy poprawić dane i ponawiać sprawdzanie poprawności, aż zakończy się ono pomyślnie.

Po potwierdzeniu poprawności weryfikacji kliknij w menu przycisk **Przepływ pracy**, aby rozpocząć przepływ pracy zatwierdzania. Kliknij przycisk **Prześlij** w menu **Przepływ pracy**, aby wykonać proces. Skonfiguruj etapy i autoryzowanych użytkowników przepływu pracy w oknie **Handel detaliczny** \> **Ustawienia centrali** \> **Przepływy pracy sieci sprzedaży**. Przepływ pracy określi czynności do przeniesienia katalogu do stanu **Zatwierdzony**. Kiedy katalog ma status **Zatwierdzony**, klikając opcję **Opublikuj** w menu **Katalogi** można zakończyć proces. Gdy katalog znajdzie się w stanie **Opublikowano**, można go używać w biurze obsługi w procesach wprowadzania zamówień i wysyłania katalogów.

## <a name="use-catalogs-to-drive-sales-order-pricing-and-promotions"></a>Używaj katalogów do zarządzania polityką cenową zamówień sprzedaży i promocjami

Podstawowym powodem definiowania katalogu, który ma być używany w biurze obsługi, jest możliwość konfigurowania określonych cen i promocji dla tego katalogu. Klienci zamawiający z tego katalogu zobaczą te ceny i promocje podczas wprowadzania zamówień w biurze obsługi, jeśli parametr **Identyfikator kodu źródłowego** katalogu jest stosowany do nagłówka lub wierszy zamówienia.

Aby skonfigurować ceny określonego katalogu, zaznacz opcję **Grupy cenowe** z karty **Katalogi**, aby połączyć jedną lub więcej grup cen z katalogiem. Wszystkie umowy handlowe, arkusze korekt cen i zaawansowane rabaty detaliczne (progowe, ilościowe, łączone), które zostały połączone z tą samą grupą cenową, będą stosowane podczas zamawiania z tego katalogu przez odbiorców.

Na skróconej karcie **Kody źródłowe** kliknij przycisk **Dodaj**, aby dodać jeden lub więcej identyfikatorów **Identyfikator kodu źródłowego** do tego katalogu. Jest to kod, który zostanie zastosowany podczas wprowadzania zamówienia sprzedaży do nagłówka zamówienia sprzedaży (i wierszy) w biurze sprzedaży. Ten kod jest używany do łączenia zamówienia sprzedaży z katalogiem i ostatecznie z grupami cen i wszelkimi cenami specjalnymi oraz promocjami, które zostały skonfigurowane.

## <a name="use-the-source-id-to-track-costs-and-response-rates"></a>Użyj identyfikatora źródła do śledzenia kosztów i wskaźników odpowiedzi

Podczas definiowania **Identyfikatora kodu źródłowego**, można opcjonalnie łączyć ten Identyfikator z **Identyfikatorem rynku docelowego**. Ustawienie **Identyfikator rynku docelowego** można zdefiniować w oknie **Handel detaliczny** \> **Odbiorcy** \> **Rynek docelowy**. Rynek docelowy to lista odbiorców i/lub prospektów, którzy należą do segmentu zdefiniowanego przez użytkownika. Połączenie danych odbiorcy lub prospekta z identyfikatorem kodu źródłowego pozwoli na lepszy wgląd w adresatów katalogu. Jeśli klient jest połączony z rynkiem docelowym, a ten rynek docelowy jest połączony z aktywnym identyfikatorem kodu źródłowego/katalogiem, użytkownicy biura obsługi będą mogli zobaczyć, które katalogi otrzymał odbiorca, wybierając opcję menu **Kody źródłowe** na karcie menu **Odbiorcy** na stronie **Obsługa klienta**. Podczas wprowadzania zamówienia użytkownicy biura obsługi widzą również konkretne katalogi, które wysłano odbiorcy, na liście rozwijanej **Źródło** w nagłówku zamówienia sprzedaży. Zmiana filtra z **Wszystkie** na **Docelowe** pozwoli użytkownikowi zobaczyć konkretne aktywne katalogi, które wysłano odbiorcy. Jest to przydatne w sytuacjach, w których odbiorca mógł zapomnieć katalog lub nie może zlokalizować bądź odczytać kodu katalogu, gdy jest wezwany do utworzenia zamówienia sprzedaży.

Można połączyć wiele identyfikatorów kodu źródłowego z katalogiem. Jest to często potrzebne, gdy firma chce śledzić wskaźnik odpowiedzi uzyskanych w różnych segmentach. Firma poda unikatowy kod katalogu do różnych segmentów klientów, co pozwala na śledzenie wskaźnika reakcji nawet na poziomie segmentu, w ramach zdarzenia danego katalogu.

Wybranie określonego rekordu **Identyfikator kodu źródłowego** i kliknięcie opcji **Szczegóły** na skróconej karcie **Kody źródłowe** spowoduje wyświetlenie dodatkowych pól, gdzie można wprowadzić prognozy sprzedaży, koszty korespondencji i daty wysyłania korespondencji. Te dane są przydatne do przeprowadzania szczegółowej analizy skuteczności katalogu. Użytkownicy mogą powrócić do tej strony i użyć przycisków **Analiza kodu źródłowego** i **Porównanie promocji**, aby uruchamiać raporty analityczne na podstawie bieżących danych sprzedaży i porównać koszty i budżetu z wartościami rzeczywistymi.

## <a name="configure-catalog-specific-order-and-item-scripts"></a>Konfigurowanie skryptów zamówień i towarów specyficznych dla katalogu

Gdy użytkownik biura obsługi tworzy zamówienie sprzedaży, może używać skryptów na ekranie. Te skrypty tekstowe mogą dostarczyć dodatkowe informacje, które użytkownik powinien przekazać nabywcy, lub mogą stanowić wewnętrzne uwagi/przypomnienia dotyczące konieczności sprawdzenia i zareagowania przez użytkownika biura obsługi podczas tworzenia zamówienia sprzedaży.

Często warto warto mieć różne zestawy skryptów dla różnych katalogów. Na skróconej karcie **Skrypty** można połączyć wstępnie zdefiniowane skrypty z katalogiem. Użyj pola **Czasu**, aby określić czy skrypt pojawią się na początku zamówienia (jak tylko identyfikator kodu źródłowego jest wprowadzony w nagłówku zamówienia) lub na końcu zamówienia (w formie podsumowania zamówienia sprzedaży).

Po wybraniu węzła w hierarchii katalogu i pracy z danymi w skróconej karcie **Produkty**, użytkownicy mogą też łączyć skrypty, które są specyficzne dla katalogów lub elementów za pomocą akcji **Skrypty**.

## <a name="configure-catalog-specific-up-sell-and-cross-sell-items"></a>Konfigurowanie towarów do sprzedaży dodatkowej i powiązanej specyficznych dla katalogu

Połączenia sugestii sprzedaży dodatkowej/powiązanej z towarem można dokonać w konfiguracji produktów, ale w niektórych przypadkach przedsiębiorstwo może chcieć promowanie szczególne towary dodatkowe/powiązane klientom zamawiającym określony produkt z określonego katalogu. Na skróconej karcie **Produkty** wybierz towar i kliknij opcję **Pozycje w sprzedaży dodatkowej/powiązanej**, aby skonfigurować produkty, które mają być oferowane jako dodatkowe/powiązane odbiorcom kupującym wybrany towar z katalogu. Podczas wprowadzania zamówienia w biurze obsługi na ekranie będą wyświetlane towary przeznaczone do sprzedaży dodatkowej/powiązanej specyficzne dla katalogu zamiast standardowych towarów przeznaczonych do sprzedaży dodatkowej/powiązanej, które być może skonfigurowano dla tego towaru w zwykłym procesie konfiguracji produktu.

Towary sprzedaży dodatkowej up-sell/cross-sell mogą także korzystać z funkcji skryptu do wyświetlania określonej wiadomości, które zostaną wyświetlone podczas wprowadzania towarów sprzedaży dodatkowej up-sell/cross-sell. Skrypty powiązane z produktami sprzedaży dodatkowej/powiązanej skonfigurowane specjalnie dla produktu w katalogu będą wyświetlane dopiero po użyciu kodu źródłowego tego katalogu przy wprowadzaniu zamówień w biurze obsługi.

## <a name="catalog-page-analysis"></a>Analiza strony katalogu

Na karcie **Katalogi** w sekcji **Strony katalogu** są dostępne opcje konfiguracyjne. Ta funkcja umożliwia zdefiniowanie określonych stron i typów stron do drukowanego katalogu i skojarzonych z nimi kosztów.

Podczas konfigurowania produktów w katalogu, użyj akcji **Układ strony produktu** do zdefiniowania określonych stron, wartości procentowej strony i położenie szczegółów dotyczących towaru. Skonfigurowanie danych pozwoli użytkownikom korzystać z **raportu Analiza obszaru katalogu**. Ten raport można znaleźć, przechodząc do raportu **Sprzedaż detaliczna** \> **Raporty biura obsługi** \> **Analiza obszaru katalogu**. Ten raport analizuje sprzedaż w zestawieniu z katalogiem (zamówienia sprzedaży, w których identyfikator źródłowy katalogu został powiązany z nagłówkiem lub wierszem zamówienia) i skojarzony z nimi procent strony oraz koszty, aby sporządzić tradycyjny raport marketingu bezpośredniego **Analiza centymetrów kwadratowych**.

## <a name="catalog-requests"></a>Zapotrzebowania na katalog

Ponieważ katalogi są konfigurowane i publikowane w programie Dynamics 365 for Retail, można używać funkcji **Wyślij katalog**. Ta funkcja jest dostępna na stronach **Wyszukiwanie odbiorcy** i **Obsługa klienta**. Po wybraniu rekordu odbiorcy za pomocą funkcji **Wyszukiwanie odbiorcy** lub podczas wyświetlania wybranych kont odbiorców z okna **Obsługa klienta** użytkownicy mogą wybrać opcję **Wyślij katalog**, co spowoduje otwarcie okna dialogowego pozwalającego użytkownikowi wybierać z listy wszystkich opublikowanych i aktywnych katalogów. Użytkownik może wybrać katalog i ilości oraz konkretny identyfikator kodu źródłowego do wysłania. Po kliknięciu przycisku **Wyślij** zapisywane jest żądanie, którym można zarządzać poprzez drukowanie raportu **Żądania w katalogu**. Ten raport można znaleźć, przechodząc do raportu **Sprzedaż detaliczna** \> **Raporty biura obsługi** \> **Raport zapotrzebowań na katalog**. Wyświetla listę wszystkich wniosków o katalog, w tym nazwy i dane adresowe odbiorców, którzy o niego poprosili. Ten raport może być używany wewnętrznie lub dane mogą być przenoszone do strony trzeciej wpierającej proces zewnętrzny w celu fizycznego wysłania katalogu do odbiorcy.

## <a name="additional-features"></a>Dodatkowe funkcje

Na karcie **Katalogi** znajdują się również sekcje z opcjami konfiguracyjnymi **Harmonogram płatności** i **Produkty bezpłatne**. Jeśli identyfikator kodu źródłowego połączony z katalogiem zostanie zastosowany podczas wprowadzania zamówienia w biurze obsługi, odbiorca będzie uprawniony do bezpłatnych produktów lub do używania określonych zdefiniowanych harmonogramów płatności za zakupy towarów z katalogu. Jeśli trzeba nałożyć ograniczenie na odbiorcę i pozwolić mu tylko wybierać spośród harmonogramów płatności połączonych z jego katalogiem, a nie ze wszystkich aktywnych harmonogramów płatności w systemie, można zaznaczyć pole wyboru **Zezwalaj tylko na plany katalogu** dla jednego lub więcej identyfikatorów kodu źródłowego, aby wymusić to ograniczenie.

## <a name="additional-notes"></a>Dodatkowe notatki

Obecnie gdy identyfikator kodu źródłowego jest stosowany do zamówienia sprzedaży w biurze obsługi, służy do ustalania cen, promocji, skryptów i produktów przeznaczonych do sprzedaży dodatkowej/powiązanej specyficznych dla katalogu. System nie będzie zabraniać ani uniemożliwiać złożenia zamówienia sprzedaży na produkt nieznajdujący się w katalogu. Jeśli zostanie zamówiony towar, który nie jest częścią katalogu, system najpierw użyje **grupy cenowej** zdefiniowanej w kanale biura obsługi (**Handel detaliczny** \> **Kanały** \> **Biura obsługi** \> **Wszystkie biura obsługi**) dla ceny towaru lub promocji. Jeśli nie zostanie znaleziona żadna konkretna cena dla kanału, będzie używana podstawowa cena sprzedaży towaru.
