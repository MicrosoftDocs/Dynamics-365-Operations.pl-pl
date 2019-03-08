---
title: Wielokanałowe zaawansowane opłaty automatyczne
description: W tym temacie opisano funkcje zarządzania opłatami za dodatkowe zamówienia dla zamówień kanału Retail przy użyciu zaawansowanych funkcji opłat automatycznych.
author: hhaines
manager: annbe
ms.date: 01/22/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: hhaines
ms.search.validFrom: ''
ms.dyn365.ops.version: 10
ms.openlocfilehash: a980ae9571fb47522d3966dc172b2343641b827e
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "345566"
---
# <a name="omni-channel-advanced-auto-charges"></a>Wielokanałowe zaawansowane opłaty automatyczne

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Ten temat zawiera informacje o konfiguracji i wdrażaniu funkcji zaawansowanych opłat automatycznych, które są dostępne w programie Dynamics 365 for Retail w wersji 10.0.

Po włączeniu funkcji zaawansowanych automatycznych opłat zamówienia utworzone w dowolnym obsługiwanym kanale Retail (punkt sprzedaży (POS), biuro obsługi i w trybie online), można korzystać z [automatycznych opłat](https://docs.microsoft.com/en-us/dynamics365/unified-operations/retail/configure-call-center-delivery#define-charges-for-delivery-services) zdefiniowanych w aplikacji ERP dla opłat dotyczących zarówno poziomu nagłówka, jak i wiersza.  

W programie Dynamics 365 for Retail w wersjach wcześniejszych niż 10.0 konfiguracje [opłat automatycznych](https://docs.microsoft.com/en-us/dynamics365/unified-operations/retail/configure-call-center-delivery#define-charges-for-delivery-services) są dostępne tylko dla zamówień utworzonych w kanałach e-commerce i biura obsługi. W wersji 10.0 i nowszej zamówienia utworzone w POS mogą korzystać z konfiguracji opłat automatycznych. W ten sposób dodatkowe opłaty różne mogą być systematycznie dodawane do transakcji sprzedaży.

W wersjach wcześniejszych niż 10.0 użytkownik POS otrzymuje monit o ręczne wprowadzenie opłaty transportowej podczas tworzenia transakcji POS „wyślij wszystko” lub „wyślij wybrane”. Podczas gdy funkcje aplikacji związane z opłatami różnymi są używane w odniesieniu do tego, jak opłaty są zapisywane na zamówieniu, żadne systemowe obliczenia nie są dostarczane — obliczenia polegają na danych podanych przez użytkownika do określenia wartości opłat. Opłaty mogą być dodawane tylko jako jeden kod opłat „transportowych” i nie mogą być łatwo edytowalne ani zmieniane w POS po utworzeniu. 

Ręczne monity do dodawania opłat transportowych są nadal dostępne w wersjach 10.0 i nowszych. Jeśli organizacja nie obsługuje parametru **Zaawansowane opłaty automatyczne**, monity POS o ręczne wprowadzenie zostaną takie same.

Dzięki funkcji zaawansowanych opłat automatycznych użytkownicy POS mogą korzystać z systemowych kalkulacji dla dowolnych zdefiniowanych opłat różnych na podstawie tabel konfiguracji opłat automatycznych. Ponadto użytkownicy będą mieli możliwość dodawania lub edytowania nieograniczonej ilości dodatkowych opłat i płatności do dowolnej transakcji sprzedaży w POS na poziomie nagłówka lub wiersza (dla transakcji kasowych i lub zamówień odbiorcy).

## <a name="enabling-advanced-auto-charges"></a>Włączanie zaawansowanych opłat automatycznych

Na stronie **Handel detaliczny \> Ustawienia centrali \> Parametry \> Parametry sieci sprzedaży** przejdź na kartę **Zamówienia odbiorcy**. Na karcie skróconej **Opłaty** ustaw opcję **Użyj zaawansowanego automatycznego naliczania opłat dodatkowych** na **Tak**.

![Parametr zaawansowanych opłat automatycznych](media/advancedchargesparameter.png)

Po włączeniu zaawansowanych opłaty automatycznych użytkownicy nie są już monitowani o ręczne wprowadzanie opłat transportowych na terminalu POS podczas tworzenia zamówienia odbiorcy „wyślij wszystko” lub „wyślij wybrane”. Opłaty za zamówienie POS są systemowo obliczane i dodawane do transakcji POS (w przypadku znalezienia odpowiedniej tabeli opłat automatycznych pasującej do kryteriów tworzonego zamówienia). Użytkownik może również dodawać i obsługiwać opłaty na poziomie nagłówka lub wiersza ręcznie za pośrednictwem nowo dodanych operacji POS, które mogą być dodane do układów ekranu POS.  

Po włączeniu zaawansowanych opłat automatycznych, istniejące **Parametry sieci sprzedaży** dla **Kodu opłat transportowych** i **Zwrotu opłat transportowych** nie są używane. Parametry te mają zastosowanie tylko wtedy jeśli parametr **Użyj zaawansowanego automatycznego naliczania opłat dodatkowych** ma wartość **Nie**.

Przed włączeniem tej funkcji należy upewnić się, że pracownicy przeszli szkolenie, ponieważ ta funkcja zmienia przepływ procesu biznesowego w odniesieniu do metody obliczania opłat transportowych i innych i ich dodawania do zamówień sprzedaży POS. Upewnij się, że rozumiesz wpływ przepływu procesu na tworzenie transakcji w POS. W przypadku zamówień składanych przez biuro obsługi i w witrynie e-Commerce wpływ włączania zaawansowanych automatycznych opłat dodatkowych jest minimalny. Aplikacje biura obsługi i e-Commerce nadal będą zachowywać się tak samo jak wcześniej w odniesieniu do tabel automatycznych opłat dodatkowych do obliczenia dodatkowych opłat za zamówienia. Użytkownicy kanału biura obsługi będą nadal mieć możliwość ręcznej edycji dowolnych obliczonych przez system automatycznych opłat dodatkowych na poziomie nagłówka lub wiersza lub ręcznego dodawania dodatkowych opłat różnych na poziomie nagłówka lub wiersza.

## <a name="additional-pos-operations"></a>Dodatkowe operacje POS

Aby zaawansowane automatyczne opłaty dodatkowe działały prawidłowo w środowisku aplikacji POS, dodano nowe operacje POS. Te operacje muszą być dodane do [układów ekranu POS](https://docs.microsoft.com/en-us/dynamics365/unified-operations/retail/pos-screen-layouts) i wdrożone na urządzeniach POS razem z zaawansowanymi automatycznymi opłatami dodatkowymi. Jeśli te operacje nie zostaną dodane, użytkownicy nie będzie mogli zarządzać ani obsługiwać opłat dodatkowych w transakcjach POS i nie będą mogli korygować ani zmieniać wartości opłat dodatkowych, które są systematycznie obliczane na podstawie konfiguracji automatycznych opłat dodatkowych Co najmniej zaleca się wdrożenie operacji **Zarządzaj opłatami dodatkowymi** do układu POS.

Oto nowe operacje:

- **142 — Zarządzaj opłatami dodatkowymi** — umożliwia użytkownikom POS wyświetlanie i edytowanie opłat dodatkowych dla transakcji w POS, które zostały dodane ręcznie lub systemowo przy użyciu obliczeń automatycznych opłat dodatkowych.
- **141 — Dodaj opłaty na poziomie nagłówka** — umożliwia użytkownikowi ręcznie dodawanie opłaty dodatkowej na poziomie nagłówka do dowolnej transakcji POS (i wybranie kodu opłaty, który ma zostać użyty).
- **140 — Dodaj opłaty na poziomie wiersza** — umożliwia użytkownikowi ręcznie dodawanie opłaty dodatkowej na poziomie wiersza do dowolnego wiersza transakcji POS (i wybranie kodu opłaty, który ma zostać użyty).
- **143 — Oblicz ponownie opłaty** — umożliwia wykonanie pełnego ponownego obliczania opłat dla transakcji sprzedaży. Wszystkie wcześniej zastąpione przez użytkownika automatyczne opłaty dodatkowe zostaną przeliczone na podstawie bieżącej konfiguracji koszyka.  

Tak jak w przypadku wszystkie operacji POS konfiguracja zabezpieczeń może również wymagać zatwierdzenia menedżera w celu wykonania operacji.

## <a name="use-case-examples"></a>Przykłady zastosowania
W tej sekcji pokazano przykładu zastosowania, które pomogą zrozumieć konfigurację i używać automatycznych opłat dodatkowych i opłat różnych w kontekście zamówień w kanale sieci sprzedaży. Następujące przykłady przedstawiają sposób działania aplikacji po włączeniu parametru **Użyj zaawansowanego automatycznego naliczania opłat dodatkowych**.

### <a name="auto-charges-header-charges-example"></a>Przykład automatycznych opłat dodatkowych na poziomie nagłówka
#### <a name="use-case-scenario"></a>Scenariusz użycia  

Sprzedawca chce automatycznie dodać opłaty za transport podczas tworzenia transakcji w dowolnym kanale sieci sprzedaży, który wymaga wysyłki produktów do odbiorcy.  Sprzedawca oferuje 2 metody dostawy: drogą lądową i powietrzną. Jeśli odbiorca wybierze dostawę drogą lądową, a wartość zamówienia jest mniejsza niż $100, sprzedawca chce naliczać opłatę transportową $10,00. Jeśli wartość zamówienia przekracza $100 i odbiorca wybierz dostawę drogą lądową, odbiorca nie zostanie obciążony żadnymi dodatkowymi opłatami transportowymi.  Jeśli odbiorca zdecyduje się na transport lotniczy dla wszystkich zleceń, niezależnie od ich łącznej wartości zostanie naliczona opłata transportowa w wysokości $20.00.

#### <a name="setup-and-configuration"></a>Instalacja i konfiguracja

Ten scenariusz wymaga wcześniejszego skonfigurowania dwóch tabel automatycznych opłat dodatkowych.   

Wybierz kolejno opcje **Rozrachunki z odbiorcami \> Ustawienia opłat \> Opłaty automatyczne**.  

Konfigurowanie dwóch różnych automatycznych opłat na poziomie nagłówka. Skonfiguruj jedną opłatę dla „dostawy lądowej” i drugą dla „dostawy lotniczej”. W tym scenariuszu skonfigurujemy je do użycia dla „Wszystkich odbiorców”.  

Dla opłaty za dostawę lądową w sekcji wierszy na stronie **Opłaty automatyczne** zdefiniuj opłatę $10.00. , która zostanie zastosowana do zleceń o wartości od $0,01 do $100. Utwórz kolejny wiersz opłaty dla zamówień o wartości powyżej $100.01, dla których nie będą naliczane żaden opłaty.

![Przykład opłat automatycznych](media/headerchargesexample.png)

Dla opłaty za dostawę lotniczą w sekcji wierszy na stronie opłat automatycznych zdefiniuj opłatę $20.00, która zostanie zastosowana do wszystkich zleceń (o wartości od $0,01 to $9 999 999).

Wyślij zmiany do bazy danych serwera/kanału Retail, aby można było używać ich w POS za pomocą zadania **Harmonogram dystrybucji 1040**

#### <a name="sales-processing-for-this-scenario"></a>Przetwarzanie sprzedaży w tym scenariuszu

Po wykonaniu powyższej procedury konfiguracyjnej i zastosowaniu zmian do bazy danych kanału, wszelkie zamówienia odbiorcy lub transakcje sprzedaży utworzone w POS, biurze sprzedaży lub kanałach e-Commerce, które mają dostawę lądową lub lotniczą ustawioną na poziomie nagłówka, będą używać tych opłat i stosować je do sprzedaży.   

Obecnie opłaty będą stosowane do wszystkich transakcji sprzedaży utworzonych w obrębie firmy korzystającej z tych metod dostawy, ponieważ nie ma w tej chwili funkcji, która pozwalałaby przydzielić konfigurację automatycznych opłat dodatkowych tylko do określonego kanału sprzedaży.

W scenariuszach POS i e-Commerce, ponieważ nie istnieje żaden ściśle określony „nagłówek” na tych zamówieniach, opłaty na poziomie nagłówka będą miały zastosowanie tylko jeśli wszystkie wiersze sprzedaży w odniesieniu do transakcji mają identyczną metodą dostawy. W przypadku „mieszanej metody” realizacji transakcji utworzonych w POS lub e-Commerce, tylko automatyczne opłaty na poziomie wiersza będą brane pod uwagę i stosowane.

W scenariuszach biura obsługi użytkownik ma kontrolę nad ustawieniem metody dostawy w nagłówku zamówienia, więc opłaty na poziomie nagłówka będą dotyczyć tych zamówień nawet wtedy, gdy niektóre wiersze sprzedaży zostały skonfigurowane z innym trybem dostawy. Opłaty na poziomie nagłówka dla zamówień w biurze obsługi zawsze będą oparte na trybie dostawy, który jest zdefiniowany na poziomie nagłówka zamówienia sprzedaży.

### <a name="auto-charges-line-charges-example"></a>Przykład automatycznych opłat dodatkowych na poziomie wiersza
#### <a name="use-case-scenario"></a>Scenariusz użycia 
Sprzedawca chce dodać dodatkową opłatę dla odbiorcy za konfigurację, gdy odbiorca kupuje konkretny model komputera. Ten komputer wymaga dodatkowej konfiguracji, która nie jest opcjonalna i którą sprzedawca wykona dla odbiorcy. Sprzedawca poinformował odbiorców, że za tę konfigurację naliczana jest dodatkowa opłata. Sprzedawca woli zarządzać opłatami związanymi z tą opłatą oddzielnie od ceny sprzedaży produktu ze względu na wymagania sprawozdawczości finansowej. Opłata za konfigurację wynosi $19,99 i odbiorca zostania nią obciążony w chwili zakupu tego komputera w dowolnym kanale sieci sprzedaży.

#### <a name="setup-and-configuration"></a>Instalacja i konfiguracja

Ten scenariusz wymaga wcześniejszego skonfigurowania tabeli automatycznych opłat dodatkowych na poziomie wiersza.

Wybierz kolejno opcje **Rozrachunki z odbiorcami \> Ustawienia opłat \> Opłaty automatyczne**.  

W menu rozwijanym **Poziom** wybierz wartość **Wiersz** i utwórz nowy rekord automatycznej opłaty dodatkowej dla wszystkich odbiorców i dla konkretnego produktu lub grupy produktów, w których będzie naliczana opłata konfiguracyjna.

![Przykład opłat automatycznych](media/linechargesexample.png)

Wyślij opłaty do bazy danych serwera/kanału Retail, aby można było używać ich w POS za pomocą zadania **Harmonogram dystrybucji 1040**

#### <a name="sales-processing-for-this-scenario"></a>Przetwarzanie sprzedaży w tym scenariuszu

Po wykonaniu powyższej procedury konfiguracyjnej i zastosowaniu zmian do bazy danych kanału, wszelkie zamówienia odbiorcy lub transakcje sprzedaży utworzone w POS, biurze sprzedaży lub kanałach e-Commerce, które mają tę pozycję na zamówieniu, będą uruchamiały opłatę na poziomie wiersza, która będzie systemowo dodawana do sumy zamówienia.   

Obecnie opłaty będą stosowane do wszystkich wierszy sprzedaży pasujących do konfiguracji automatycznych opłat dodatkowych na poziomie wiersza w obrębie firmy, ponieważ nie ma w tej chwili funkcji, która pozwalałaby skonfigurować automatyczne opłaty dodatkowe w taki sposób, aby miały zastosowanie do określonego kanału sprzedaży.

### <a name="manual-header-charges-example"></a>Przykład opłat ręcznych na poziomie nagłówka
#### <a name="use-case-scenario-description"></a>Opis scenariusza użycia
Sprzedawca robi wyjątek od typowych procesów, oferując specjalną dostawę do domu produktów odbiorcom, którzy zamówili produkty w sklepie. Sprzedawca i odbiorca zgadzają się, odbiorca zapłaci dodatkowe $25 opłaty za tę usługę. Osoba przyjmująca zamówienie musi dodać tę opłatę dodatkową do transakcji. Ponieważ opłata jest opłatą zbiorczą i nie jest związana z żadnym jednym produktem na zamówieniu, zostanie zastosowana opłata na poziomie nagłówka.

#### <a name="setup-and-configuration"></a>Instalacja i konfiguracja

Upewnij się, kod opłat, który będzie używany w tym scenariuszu, został poprawnie skonfigurowany w **Rozrachunki z odbiorcami \> Ustawienia opłat \> Opłaty**, aby zdefiniować odpowiedni kod opłat dla tego scenariusza.

![Przykład opłat](media/chargesexample.png)

Jeśli opłata powinna być traktowana jako opłata związana z „wysyłką” do celów związanych rabatami wysyłkowymi lub promocjami, ustaw **Opłatę wysyłkową** w kodzie opłaty na **Tak**. Jeśli ta opłata jest również dozwolona do systemowego zwrotu podczas przetwarzania transakcji zwrotu w aplikacji POL, ustaw **Zwrot** na **Tak**. Flaga **Zwrot** ma zastosowanie tylko wtedy, gdy parametr **Użyj zaawansowanego automatycznego naliczania opłat dodatkowych** ma wartość **Tak**.   

Wyślij opłaty do bazy danych serwera/kanału Retail, aby można było używać ich w POS za pomocą zadania **Harmonogram dystrybucji 1040**

Operacja **Dodaj opłaty z nagłówka** musi być skonfigurowana w [układzie ekranu POS](https://docs.microsoft.com/en-us/dynamics365/unified-operations/retail/pos-screen-layouts), aby przycisk dostępny dla użytkownika z poziomu POS mógł wywoływać tę operację (operacja 141).  Zmiany układu ekranu muszą być rozdzielone do kanałów sieci sprzedaży, jak również za pomocą funkcji harmonogramu dystrybucji. 

#### <a name="sales-processing-of-manual-header-charges"></a>Przetwarzanie sprzedaży ręcznych opłat na poziomie nagłówka

Do wykonania tego scenariusza w aplikacji POS, użytkownik POS musi utworzyć transakcję sprzedaży w zwykły sposób, dodając produkty i wszelkie inne konfiguracje do sprzedaży. Przed pobraniem płatności użytkownik powinien wykonać operację **Dodaj opłatę na poziomie nagłówka**, która będzie monitować użytkownika o wybranie kodu opłat i wprowadzenie wartości opłat. Gdy użytkownik zakończy ten proces, opłata zostanie dodana do zamówienia sprzedaży jako opłata na poziomie nagłówka.  

Ten proces może być zastosowany w biurze obsługi za pomocą istniejącej funkcji **Opłaty** na karcie **Sprzedaż** na pasku narzędzi. Na karcie **Obsługa opłat** użytkownik może dodać nowy wiersz opłaty do nagłówka zamówienia.

### <a name="manual-line-charges-example"></a>Przykład opłat ręcznych na poziomie wiersza
#### <a name="use-case-scenario"></a>Scenariusz użycia
Odbiorca poprosił o zapakowanie na prezent 2 z 5 towarów z zamówienia sprzedaży. Sprzedawca oferuje taką usługę za opłatą $2,00 za przedmiot. Osoba przyjmująca zamówienie musi dodać te opłaty do określonego towaru, które muszą zostać zapakowane na prezent.

#### <a name="setup-and-configuration"></a>Instalacja i konfiguracja

Upewnij się, kod opłat, który będzie używany w tym scenariuszu, został poprawnie skonfigurowany w **Rozrachunki z odbiorcami \> Ustawienia opłat \> Opłaty**, aby zdefiniować odpowiedni kod opłat dla tego scenariusza.

Jeśli opłata powinna być traktowana jako opłata związana z „wysyłką” do celów związanych rabatami wysyłkowymi lub promocjami, ustaw **Opłatę wysyłkową** w kodzie opłaty na **Tak**. Jeśli ta opłata jest również dozwolona do systemowego zwrotu podczas przetwarzania transakcji zwrotu w aplikacji POL, ustaw **Zwrot** na **Tak**. Flaga **Zwrot** ma zastosowanie tylko wtedy, gdy parametr **Użyj zaawansowanego automatycznego naliczania opłat dodatkowych** ma wartość **Tak**.  

Wyślij opłaty do bazy danych serwera/kanału Retail, aby można było używać ich w POS za pomocą zadania **Harmonogram dystrybucji 1040**

Operacja **Dodaj opłaty z wiersza** musi być skonfigurowana w [układzie ekranu POS](https://docs.microsoft.com/en-us/dynamics365/unified-operations/retail/pos-screen-layouts), aby przycisk dostępny dla użytkownika z poziomu POS mógł wywoływać tę operację (operacja 140).  Zmiany układu ekranu muszą być rozdzielone do kanałów sieci sprzedaży, jak również za pomocą funkcji harmonogramu dystrybucji. 

#### <a name="sales-processing-of-the-manual-line-charge"></a>Przetwarzanie sprzedaży ręcznej opłaty na poziomie wiersza

Do wykonania tego scenariusza w aplikacji POS, użytkownik POS musi utworzyć transakcję sprzedaży w zwykły sposób, dodając produkty i wszelkie inne konfiguracje do sprzedaży. Przed pobieraniem płatności użytkownik powinien wybrać określony wiersz, w którym będą stosowane opłaty z listy pozycji POS i wykonać operację **Dodaj opłatę na poziomie wiersza**. Użytkownik zobaczy monit o wybranie kod opłaty i wprowadzenie wartości opłat. Gdy użytkownik zakończy ten proces, opłata zostanie połączona z wierszem i dodana do sumy zamówienia jako opłata na poziomie wiersza. Użytkownik może powtórzyć ten proces, aby dodać opłaty dodatkowe na poziomie wiersza do innych wierszy towarów w ramach transakcji, jeśli jest taka potrzeba.

Ten sam proces można zastosować w biurze obsługi za pomocą funkcji „Obsługa opłat” dostępnych na liście menu rozwijanego **Finanse** w sekcji **Wiersze zamówienia sprzedaży** na stronie **Zamówienie sprzedaży**.  Spowoduje to otwarcie strony **Obsługa opłat**, na której użytkownik może dodać do transakcji nową opłatę specyficzną dla wiersza.

## <a name="additional-features"></a>Dodatkowe funkcje

### <a name="editing-charges-on-a-pos-sales-transaction"></a>Edytowanie opłat na transakcji sprzedaży POS

Operacja **Zarządzaj opłatami dodatkowymi** (142) powinna zostać dodana do [układu ekranu POS](https://docs.microsoft.com/en-us/dynamics365/unified-operations/retail/pos-screen-layouts), aby umożliwić wyświetlanie i edytowanie lub zastępowanie wszelkich opłat na poziomie nagłówka lub wiersza obliczanych przez system lub ręcznie. Jeśli operacja nie zostanie dodana, użytkownicy nie będą mogli zmienić wartości opłat w transakcji POS ani wyświetlać szczegółów opłat, takich jak typ kodu opłaty powiązany z opłatą.  

Na stronie **Zarządzaj opłatami dodatkowymi** w POS użytkownik może wyświetlić zarówno nagłówek, jak i szczegóły opłaty na poziomie wiersza. Użytkownik może użyć funkcji **Edytuj** na tej stronie, aby wprowadzić zmiany do kwoty pobieranej z konkretnego wiersza opłat. Po ręcznym nadpisaniu wiersza opłat nie będzie on systemowo obliczany ponownie, chyba że użytkownik zainicjuje operację **Ponownie oblicz opłaty**.

Jeśli **Kod przyczyny zastąpienia opłat** został skonfigurowane na stronie konfiguracji **Parametry sieci sprzedaży**, użytkownik będzie monitowany o podanie kodu przyczyny, kiedy opłaty są modyfikowane w aplikacji POS.

Jeśli kod przyczyny został zarejestrowany dla nadpisanych opłat, nowy raport również jest dostępny do sprawdzenia i kontroli tych nadpisań. Raport można znaleźć w menu **Handel detaliczny \> Zapytania i raporty \> Historia zastąpień opłat**.

### <a name="refunding-charges-on-a-pos-return-transaction"></a>Zwracanie opłat w ramach transakcji zwrotu POS

Jeśli parametr **Użyj zaawansowanego automatycznego naliczania opłat dodatkowych** jest ustawiony na **Tak**, istniejący parametr sieci sprzedaży dla **Zwróć opłaty transportowe** nie ma już zastosowania. Aby wskazać, które opłaty mają być systemowo zwracane odbiorcy w kontekście zaawansowanych automatycznych opłat dodatkowych, należy upewnić się, że odpowiedni kod opłat został skonfigurowany jako **Zwrot** na stronie konfiguracji **Kod opłat**. Upewnij się, że ustawienia zostały zsynchronizowane z bazami danych kanału sprzedaży detalicznej za pomocą przetwarzania harmonogramu dystrybucji.

### <a name="refunding-charges-on-a-return-order-transaction"></a>Zwracanie opłat w ramach transakcji zamówienia

Opłaty nie są systemowo zwracane do **Zamówień zwrotu** utworzonych w sieci sprzedaży. Użytkownicy muszą wybrać opcję **Kopiuj opłaty** podczas tworzenia **Zamówienia zwrotu**. Jeśli opcja **Kopiuj opłaty** jest została zaznaczona, opłaty z pierwotnej transakcji sprzedaży nie zostaną automatycznie zwrócone. Jeśli opcja **Kopiuj opłaty** jest zaznaczona, wszystkie opłaty zostaną skopiowane do zamówienia zwrotu, a użytkownik może ręcznie edytować lub usunąć wszelkie opłaty, które nie mają zostać zwrócone. Proces zamówienia zwroty z biura obsługi obecnie nie zatwierdza flagi **Zwrot** w konfiguracji **Kod opłat**.

### <a name="configuring-pos-receipts-to-show-charges"></a>Konfigurowanie przyjęć POS, aby pokazywały opłaty

Dodano następujące elementy przyjęcia do wiersza przyjęcia i stopki do obsługi funkcji zaawansowanych automatycznych opłat dodatkowych.

- **Opłaty transportowe w wierszach** - ten element poziomu wiersza może służyć do podsumowania określonych kodów opłat, które zostały zastosowane do wiersza sprzedaży. Tylko kody opłat, które zostały oflagowane jako opłaty **Transportowe** na stronie **Kod opłat** zostaną tutaj wyświetlone.

- **Inne opłaty w wierszach** - ten element poziomu wiersza może służyć do podsumowania wszelkich kodów opłat niezwiązanych z wysyłką, które zostały zastosowane do wiersza sprzedaży. Są to kody opłat, dla których flaga **Transportowe** na stronie **Kod opłat** nie została włączona.

- **Szczegóły opłat transportowych w zamówieniach** - ten element poziomu stopki wyświetla opisy kodów opłat stosowanych do zamówienia, które zostało oflagowane jako opłaty **Transportowe** na stronie **Kody opłat**.

- **Opłaty transportowe w zamówieniach**  - ten element poziomu stopki pokazuje wartość w dolarach opłat związanych z wysyłką.

- **Szczegóły innych opłat w zamówieniach** - ten element poziomu stopki wyświetla opis kodów opłat stosowanych do zamówienia, które nie zostało oflagowane jako związane z opłatami transportowymi.

- **Inne opłaty w zamówieniach** - ten element poziomu stopki wyświetla wartość w dolarach innych opłat, które nie są związane z wysyłką.

Zalecane jest, aby organizacja także dodała pola dowolnego tekstu do stopki przyjęcia, aby zdefiniować obszary, w których opłaty będą podsumowywane. 

### <a name="preventing-charges-from-being-calculated-until-the-pos-order-is-completed"></a>Uniemożliwienie obliczania opłat aż do zamknięcia zamówienia POS

Niektóre organizacje mogą woleć czekać, aż użytkownik zakończy dodawanie wszystkich wierszy sprzedaży do transakcji POS przed obliczeniem opłat. Aby zapobiec obliczaniu opłat w trakcie dodawania pozycji do transakcji POS, włącz parametr **Ręczne obliczanie opłat** w **Profilu funkcjonalnym** używanym w danym sklepie. Włączenie tego parametru będzie wymagać od użytkownika POS użycia operacji **Oblicz sumy** po zakończeniu dodawania produktów do transakcji POS. Operacja **Oblicz sumy** spowoduje następnie obliczenie wszelkich automatycznych opłat dodatkowych dla nagłówka lub wierszy zamówienia, stosownie do przypadku.
