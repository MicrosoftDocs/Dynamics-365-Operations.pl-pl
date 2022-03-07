---
title: Konfigurowanie metod dostawy i opłat w biurze obsługi
description: W tym temacie opisano sposób konfigurowania metod dostawy i opłat za zlecenia z biura obsługi w Dynamics 365 Commerce.
author: josaw1
ms.date: 04/26/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailMCRChannelDetailPage, MCROrderParameters
audience: Application User
ms.reviewer: josaw
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-04-30
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: bd763082969079de2d68e12483ec25871c332e4067f122c6a845d3acd477af62
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6748578"
---
# <a name="configure-call-center-delivery-modes-and-charges"></a>Konfigurowanie metod dostawy i opłat w biurze obsługi

[!INCLUDE [banner](includes/banner.md)]

Gdy zamówienie sprzedaży jest umieszczone w Dynamics 365 Commerce a osoba, która wprowadziła zamówienie sprzedaży jest połączona z kanałem biura obsługi, logika i reguły są używane do sprawdzania poprawności metody dostawy (metoda dostawy) i obliczenia opłaty dla zamówienia.

Podczas tworzenia zamówienia sprzedaży można wybrać metodę dostawy w nagłówku i wierszach zamówienia sprzedaży. Domyślnie metoda dostawy wybrana w nagłówku jest używana do wszystkich wierszy zamówienia sprzedaży. Można jednak zmienić domyślną metodę dostawy w poszczególnych wierszach sprzedaży zgodnie z potrzebą. Można także zdefiniować metodę dostawy w rekordzie odbiorcy. Następnie, kiedy zamówienia są tworzone dla klienta, ta metoda dostawy jest używana domyślnie w nagłówku zamówienia sprzedaży.

Commerce zawiera funkcje, które pozwalają użytkownikom ograniczać zakres metod dostawy dostępnych do użycia w kanale lub dla produktu oraz dozwolonych dla określonych miejsc docelowych wysyłki. Można również zdefiniować opłaty, tak aby do zamówienia odbiorcy były doliczane opłaty dodatkowe na podstawie metod dostawy wybranych dla zamówienia i na podstawie łącznej wartości zamówienia.

## <a name="define-delivery-modes"></a>Definiowanie metod dostawy

Zanim będzie można określić, które metody dostawy mogą być używane do zamówień w biurze obsługi, oraz zdefiniować powiązane reguły i opłaty, należy zdefiniować metody dostawy. Wybierz kolejno opcje **Sprzedaż i marketing \> Ustawienia \> Dystrybucja \> Metody dostawy**. Wybierz opcję **Nowy**, aby utworzyć nową metodę dostawy. Alternatywnie wybierz istniejącą metodę dostawy z listy, a następnie wybierz opcję **Edytuj**, aby wprowadzić zmiany.

W polu **Metoda dostawy** można wprowadzić dowolną kombinację znaków alfanumerycznych zgodnie z wymaganiami firmy. Następnie można użyć pola **Opis**, aby zapewnić dodatkowy kontekst. Pola **Grupa opłat** i **Przyspieszone** są opcjonalne i zostały dokładniej wyjaśnione w dalszej części tego tematu.

Na skróconej karcie **Kanały Commerce** dodaj wszelkie kanały, w których powinna istnieć możliwość używania metody dostawy podczas tworzenia w nich transakcji sprzedaży.

Na skróconej karcie **Produkty** można określić produkty i/lub kategorie produktów, dla których można i nie można używać metody dostawy. Na przykład jeśli produktu nie można wysłać drogą lotniczą z powodu ograniczeń dotyczących niebezpiecznych materiałów (hazmat), upewnij się, że produkt lub kategoria produktów jest wyłączona ze wszystkich metod dostawy uwzględniających transport lotniczy.

Na skróconej karcie **Adresy** można określić kraje, regiony lub województwa, w których można i nie można używać metody dostawy. Na przykład zamówienia wysyłane do Alaski lub Hawajów nie kwalifikują się do dostawy drogą lądową. Dlatego te stany powinny zostać wykluczone z każdej metody dostawy skojarzonej z naziemną usługą dostawy, ale uwzględnione w każdej metodzie dostawy skojarzonej z powietrzną usługą dostawy.

## <a name="validate-delivery-modes-for-a-call-center-order"></a>Sprawdź poprawność metod dostawy dla zamówienia z biura obsługi

Po zdefiniowaniu są metod dostawy należy wykonać zadanie wsadowe **Metody dostawy dla procesu**. To zadanie udostępnia metody dostawy, tak aby mogły zostać użyte w procesach zamówienia sprzedaży dla kanałów. Do uruchomienia **Przetwarzania metod dostawy** zadania, przejdź do **Retail i Commerce \> Retail i Commerce IT \> Przetwarzanie metod dostawy**. To zadanie powinno być uruchamiane, ilekroć nowe metody dostawy są dodawane do kanału lub kiedy wprowadza się zmiany do istniejących relacji trybu dostawy/kanału.

Po wykonaniu zadania wsadowego **Metody dostawy dla procesu** można przejść do okna **Retail i Commerce \> Kanały \> Biura obsługi \> Wszystkie biura obsługi**. Na stronie **Wszystkie biura obsługi** w okienku akcji na karcie **Ustawienia** wybierz opcję **Metody dostawy**. Na stronie **Metody dostawy** znajduje się lista wszystkich prawidłowych metod dostawy dla wybranego kanału biura obsługi. Aby edytować istniejącą metodę dostawy lub dodać nowe metody dostawy, należy wybrać **Zarządzanie metodami dostawy**. Należy zauważyć, że zadanie **Metody dostawy dla procesu** musi zostać uruchomione po wprowadzeniu jakichkolwiek zmian.

## <a name="define-charges-for-delivery-services"></a>Definiowanie opłat za usługi dostawcze

Podczas tworzenia zamówienia sprzedaży dla odbiorców, firma może dodać koszty, które są naliczane automatycznie w zależności od metody dostawy wybranej dla zamówienia. Opłaty te można skonfigurować tak, aby były takie same dla wszystkich odbiorców i metod dostawy. Alternatywnie opłaty mogą się różnić i zależeć od odbiorcy i/lub metody dostawy wybranych dla zamówienia sprzedaży.

Aby zdefiniować opłaty, przejdź do **Retail i Commerce \> Konfiguracja kanału \> Opłaty \> Automatyczne opłaty**. Wybierz opcję **Nowy**, aby dodać nowe opłaty. Alternatywnie wybierz istniejący wpis, a następnie wybierz opcję **Edytuj**.

Można zdefiniować opłaty, tak aby były obliczane na poziomie nagłówka zamówienia lub wierszy zamówienia. Użyj pola **Poziom**, aby wybrać żądany poziom.

Można zdefiniować opłaty dla określonego odbiorcy, grupy odbiorców lub wszystkich odbiorców. W polu **Kod konta** wybierz opcję **Tabela**, aby zdefiniować opłaty stosowane tylko do określonego odbiorcy. Wybierz opcję **Grupa**, aby zdefiniować opłaty dla określonej grupy odbiorców. Zaznacz opcję **Wszystko**, aby stosować opłaty do każdego odbiorcy, który składa zamówienie sprzedaży wykorzystujące powiązaną metodę dostawy. Jeśli w polu **Kod konta** wybrano opcję **Tabela** lub **Grupa**, wybierz odbiorcę lub grupę odbiorców w polu **Relacja konta**.

Można skonfigurować opłaty, tak aby były stosowane do określonej metody dostawy, grupy metod dostawy lub wszystkich metod dostawy. Jeśli w polu **Kod metody dostawy** wybierzesz opcję **Tabela**, należy wybrać konkretną metodę dostawy w polu **Relacja metody dostawy**. W przypadku wybrania opcji **Grupa** należy wybrać grupę metod dostawy w polu **Relacja metody dostawy**. Grupy metod dostawy są definiowane w oknie **Retail i Commerce \> Ustawienia kanału \> Opłaty \> Grupy opłat za dostawę**. Następnie mogą zostać połączone z co najmniej jedną metodą dostawy na stronie **Metody dostawy**. Jeśli podczas definiowania opłat wybierzesz grupę, każda metoda dostawy połączona z wybraną grupą dostawy będzie używać tych opłat. Ponadto jeśli wybierzesz opcję **Wszystko** w polu **Kod metody dostawy**, wszystkie metody dostawy będą używały opłat. Dlatego nie wybiera się wartości w polu **Relacja metody dostawy**.

W sekcji **Wiersze** można zdefiniować jedną lub więcej opłat z podziałem na waluty, zgodnie z potrzebami. Opłaty muszą być połączone z kodem opłaty, który określa reguły księgowania finansowego opłat. Pole **Kategoria** jest używane do definiowania sposobu obliczania opłat. Na przykład jeśli odbiorcy powinni być obciążani stałą stawką 9,95 USD, aby zamówienie zostało wysłane określoną metodą dostawy, użyj kategorii **Stałe**. Jeśli firma postanowi obciążyć odbiorców procentem sumy zamówienia w celu pokrycia opłat za dostawę, należy użyć kategorii **Procent**. Rzeczywiste obciążenie klientów jest zdefiniowane w polu **Wartość opłat**.

Firmy często konfigurują opłaty warstwowe. W takim przypadku kwota płacona przez odbiorcę za dostawę zależy od wartości zamówienia. Aby skonfigurować opłaty warstwowe, wprowadź wartości w polach **Od kwoty** i **Do kwoty** oprócz definiowania samej opłaty w polu **Wartość opłat**. Na przykład dla zamówień mających wartość mniejszą niż 50 USD sprzedawca detaliczny nalicza opłatę 5,95 USD za wysyłkę drogą lądową. Dla zamówień, które mają wartość równą lub wyższą niż 50 USD, ale niższą niż 50 USD, sprzedawca detaliczny nalicza opłatę 7,95 USD. Na koniec dla zamówień, które mają wartość równą lub wyższą niż 100 USD, sprzedawca detaliczny oferuje bezpłatną wysyłkę. Na poniższej ilustracji przedstawiono konfigurację tych opłat.

![Przykład stałych opłat warstwowych.](media/fixedtieredcharges.png)

Można korzystać z kombinacji kategorii opłat w zależności od potrzeb biznesowych. Na przykład dla wszystkich zamówień mających wartość mniejszą niż 100 USD istnieje stała opłata 9,95 USD za wysyłkę. Następnie, w przypadku zamówień, których wartość jest równa lub większa niż 100 zł, opłaty za dostawę są obliczane w wysokości 5% wartości zamówienia. Na poniższej ilustracji przedstawiono konfigurację tych opłat.

![Przykład mieszanych opłat warstwowych.](media/mixedtieredcharges.png)

## <a name="apply-delivery-modes-during-order-entry-in-a-call-center"></a>Stosowanie metod dostawy podczas wprowadzania zamówień w biurze obsługi

W czasie tworzenia nowego zamówienia sprzedaży, wartość **Metody dostawy** musi być określona w skróconej karcie **Dostawa** nagłówka zamówienia sprzedaży. To pole może być wypełnione automatycznie, na podstawie wartości domyślnych z poziomu rekordu klienta.

Metoda dostawy, która jest określona w nagłówku zamówienia, jest automatycznie kopiowana do wierszy zamówienia sprzedaży przy ich tworzeniu. Można jednak zmienić konfigurację metody dostawy dla określonej pozycji wiersza na karcie **Dostawa** w sekcji **Szczegóły wiersza** na stronie wprowadzania zamówienia sprzedaży.

Jeśli wybrana metoda dostawy jest nieprawidłowa dla produktu albo adresu dostawy zdefiniowanego dla zamówienia lub wiersza zamówienia, pojawi się komunikat o błędzie. Następnie należy wybrać tryb dostawy zdefiniowany do obsługi danej konfiguracji produktu lub adresu.

## <a name="calculation-of-delivery-charges-during-entry-of-order"></a>Obliczanie opłat za dostawę podczas wprowadzania zamówienia

Jeśli ustawienie **Włącz kończenie zamówienia** jest włączone w kanale biura obsługi, opłaty za wysyłkę są obliczane automatycznie dla zamówień sprzedaży, gdy użytkownicy wybierają opcję **Zakończ**. Komunikat jest wyświetlany w górnej części strony **Podsumowanie zamówienia sprzedaży**: „Obliczono opłaty warstwowe”. Opłaty obliczane są dodawane do wartości pola **Suma sprzedaży**. Na skróconej karcie **Kwota** pole **Opłaty** pokazuje łączną kwotę wszystkich opłat, które zostały obliczone dla zamówienia i wierszy. Aby wyświetlić bardziej szczegółowy podział opłat, zaznacz **Zamówienie** na stronie **Podsumowaniu zamówienia sprzedaży**, a następnie wybierz opcję **Opłaty**, aby przeglądać, dodawać lub edytować opłaty. Należy zwrócić uwagę, że obliczanie opłat za dostawę w nagłówku zamówienia jest oparte na metodzie dostawy powiązanej z nagłówkiem. Opłaty za dostawy na poziomie wiersza są obliczane zgodnie z metodą dostawy skonfigurowaną w wierszu sprzedaży. W przypadku używania wielu metod dostawy w różnych wierszach można zastosować wiele opłat i dodać je razem. Łączna kwota zostanie wyświetlona w polu **Opłaty** na stronie **Podsumowanie zamówienia sprzedaży**.

Jeśli ustawienie **Włącz kończenie zamówienia** jest wyłączone, użytkownicy muszą ręcznie inicjować obliczanie opłat. Na stronie **Zamówienie sprzedaży** w okienku akcji na karcie **Sprzedaż** w grupie **Obliczanie** wybierz opcję **Opłaty warstwowe**. Pojawi się komunikat „Obliczono opłaty warstwowe”. Można wybrać opcję **Opłaty** na karcie **Sprzedaż**, aby wyświetlić, edytować lub usuwać obliczone opłaty.

## <a name="use-expedited-delivery-modes-on-call-center-orders"></a>Użyj metody dostawy przyspieszonej dla zamówień z biura obsługi

Opcjonalnie można dołączyć kod przyspieszenia do wszelkich metod dostawy skonfigurowanych przez użytkownika. Ten kod jest używany jako priorytetyzacja narzędzia do sortowania i raportowania. Obecnie nie powoduje stosowania opłat dodatkowych do zamówienia. Aby ustawić kody wysyłkowe, przejdź do modułu **Sprzedaż i marketing \> Ustawienia \> Dystrybucja \> Kody wysyłki**.

Na przykład dla zamówień, które zostaną wysłane w następnym dniu pocztą lotniczą, pobranie musi zostać wykonane w magazynie do 13.00. W takim przypadku można utworzyć kod przyspieszenia, a następnie połączyć go z dowolną metodą dostawy w następnym dniu skonfigurowanym w systemie. Gdy magazyn tworzy grupę czynności, właściwy kod przyspieszenia w polu **Przyspieszeń** może być używany jako filtr, tak aby pobranie było wykonywane tylko dla zamówień, które mają metodę dostawy połączoną z tym kodem.

Ponadto podczas wprowadzania zamówienia w biurze obsługi można ręcznie zastosować kod przyspieszenia do nagłówka zamówienia sprzedaży lub indywidualnego wiersza zamówienia sprzedaży. Tu również kod może służyć do sortowania lub raportowania. Czasami zamówienie wymaga szczególnego obchodzenia się ze względu na problemy z obsługą klienta. W takim wypadku można zastosować określony kod przyspieszenia do nagłówka lub wierszy zamówienia, aby ułatwić identyfikację i priorytetyzację zamówienia w procesie realizacji.


[!INCLUDE[footer-include](../includes/footer-banner.md)]