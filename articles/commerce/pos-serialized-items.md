---
title: Praca z pozycjami serializowanymi w punkcie sprzedaży
description: W tym artykule opisano sposób zarządzania pozycjami spersonalizowanymi w aplikacji punktu sprzedaży.
author: boycezhu
ms.date: 01/08/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: global
ms.author: boycez
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.11
ms.openlocfilehash: 8a715a9d025f36656506daeb9e611bfacdafa102
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8880036"
---
# <a name="work-with-serialized-items-in-the-pos"></a>Praca z pozycjami serializowanymi w punkcie sprzedaży

[!include [banner](includes/banner.md)]

Wielu sprzedawców detalicznych sprzedaje produkty wymagające kontroli numerów seryjnych. Te produkty są nazywane *pozycjami serializowanymi*. Niektórzy sprzedawcy detaliczni mogą chcieć zachować numery seryjne w zapasach sklepowych lub magazynowych dla celów związanych ze śledzeniem. Inni sprzedawcy detaliczni mogą przechwytywać numery seryjne podczas procesu sprzedaży dla celów związanych z usługami i gwarancjami. W tym artykule opisano sposób zarządzania pozycjami spersonalizowanymi w aplikacji punktu sprzedaży Microsoft Dynamics 365 Commerce.

## <a name="serial-number-configurations"></a>Konfiguracje numeru seryjnego

Pozycja jest traktowana jako serializowana, jeśli przypisano do niej grupę wymiarów śledzenia skonfigurowaną do zezwalania na numery seryjne. W module Commerce Headquarters, na stronie **Grupy wymiarów śledzenia** wybierz opcję **Aktywne**, aby włączyć numery seryjne dla procesu magazynowego, lub wybierz **Aktywne w module proces sprzedażowych**, aby włączyć numery seryjne dla procesu sprzedaży.

Na skróconej karcie **Wymiary śledzenia**, włącz parametr **Dozwolony pusty przychód**, aby zezwolić na użycie numerów seryjnych jako opcjonalnych danych wejściowych w procesie przyjmowania zapasów. Wyłączenie tego parametru wymusza użycie numeru seryjnego jako wymaganych danych wejściowych. Analogicznie, parametr **Dozwolone puste wydanie** określa, czy numer seryjny jest wymagany podczas procesu wysyłania zapasów do magazynu.

> [!NOTE]
> Aby użyć operacji **Zapasy przychodzące** oraz **Zapasy wychodzące** w punkcie sprzedaży do rejestrowania lub weryfikowania numerów seryjnych pozycji serializowanych, do pozycji musi być przypisana grupa wymiarów śledzenia skonfigurowana do zezwalania na numery seryjne dla opcji **Aktywny**, a nie dla opcji **Aktywny w procesie sprzedaży**.

## <a name="serial-number-management-page"></a>Strona zarządzania numerami seryjnymi

W operacji w punkcie sprzedaży **Zapasy przychodzące** i **Zapasy wychodzące** i gdy towar, który jest wybierany, odebrany lub wysłany, jest towarem serializowanym okienko **Szczegóły** zawiera opcję **Zarządzanie numerem seryjnym**, która łączy ze stroną **Zarządzania numerami seryjnymi**, gdzie można zarejestrować lub sprawdzić numery seryjne dla danego towaru. Można również otworzyć stronę **Zarządzanie numerami seryjnymi**, wybierając działanie **Numer seryjny** na pasku aplikacji w widoku szczegółów zamówienia lub wybierając pozycję **Zarządzaj numerem seryjnym** w oknie dialogowym, które monituje Cię podczas procesu przyjęcia lub wysyłki. 

Strona **Zarządzanie numerami seryjnymi** zawiera listę wszystkich otwartych wierszy numerów seryjnych oczekujących na rejestrację lub weryfikację. Na tej stronie mogą znajdować się dwie karty: jedna dla bieżącej pozycji towaru i inna dla wszystkich pozycji serializowanych w zamówieniu.

Pole **Stan** na stronie **Zarządzanie numerami seryjnymi** zawiera informacje o bieżącym etapie, na którym znajdują się poszczególne numery seryjne:

- **Nie zarejestrowano** — numer seryjny nie został wprowadzony lub wstępnie zarejestrowany numer seryjny nie został jeszcze zweryfikowany (w procesie przyjęcia).
- **Rejestrowanie** — numer seryjny został zarejestrowany i zapisany lokalnie w bazie danych kanału sklepu lub wstępnie zarejestrowany numer seryjny został zweryfikowany. Tylko numery seryjne ze stanem **Rejestrowanie** zostaną przesłane do modułu Commerce Headquarter po zakończeniu przyjęcia lub realizacji.

## <a name="receive-serialized-items"></a>Odbieranie serializowanych towarów

Operacja **Zapasy przychodzące** w aplikacji punktu sprzedaży umożliwia użytkownikom wykonywanie następujących zadań dla pozycji serializowanych:

- Rejestrowanie numerów seryjnych w odniesieniu do pozycji serializowanych, gdy pozycje są przyjmowane w sklepie za pośrednictwem zamówienia zakupu.
- Weryfikowanie wstępnie zarejestrowanych numerów seryjnych w odniesieniu do pozycji serializowanych, gdy pozycje są przyjmowane w sklepie za pośrednictwem zamówienia zakupu lub zamówienia przeniesienia.

### <a name="register-serial-numbers-against-serialized-items"></a>Rejestrowanie numerów seryjnych w odniesieniu do pozycji serializowanych

W przypadku zamówienia zakupu okno dialogowe, które monituje użytkownika podczas procesu przyjęcia pozycji serializowanej, oferuje opcję **Zarządzania numerem seryjnym**. Można wybrać tę opcję, aby otworzyć stronę **Zarządzanie numerami seryjnymi** i rozpocząć rejestrowanie numerów seryjnych. Można również pominąć ten krok podczas procesu przyjęcia i wprowadzić dane wejściowe później, przed zaksięgowaniem przyjęcia.

Domyślnie jest wyświetlana karta dla bieżącej pozycji. Wszystkie wiersze numerów seryjnych mają pustą wartość numeru seryjnego i stan **Nie zarejestrowano**. Można zeskanować kody kreskowe numerów seryjnych lub wybrać pozycję **Numer seryjny** na pasku aplikacji w celu ciągłego wprowadzania numerów seryjnych. Numery seryjne, które wprowadzisz, pojawią się na liście, a stan wierszy tych numerów seryjnych zmieni się na **Rejestrowanie**. Maksymalna liczba numerów seryjnych, które można zarejestrować na liście, jest równa ilości przyjmowanej. W przypadku popełnienia błędu możesz wybrać pozycję **Edytuj** lub **Wyczyść** w okienku **Szczegóły**, aby wprowadzić zmiany wprowadzonych numerów seryjnych.

Numery seryjne można również rejestrować na karcie **Wszystkie pozycje serializowane** na stronie **Zarządzanie numerami seryjnymi**. Na liście wybierz pozycję, względem której chcesz zarejestrować numery seryjne.

### <a name="validate-serial-numbers-on-serialized-items"></a>Weryfikowanie numerów seryjnych dla pozycji serializowanych

W przypadku zamówienia przeniesienia strona wychodząca musi wstępnie zarejestrować numery seryjne w pozycjach serializowanych w trakcie procesu wysyłki. W przypadku zamówienia zakupu dostawca może podać informacje o numerach seryjnych za pośrednictwem wcześniejszego zawiadomienia o wysyłce (ASN), a Ty możesz następnie zarejestrować numery pozycji do wysłania. W obu przypadkach numery seryjne są znane przed przyjęciem. Z tego względu po stronie przychodzącej wystarczy tylko sprawdzić, czy zaplanowane pozycje zostały przyjęte.

Aby zweryfikować numery seryjne, można otworzyć stronę **Zarządzanie numerami seryjnymi** w trakcie procesu przyjęcia lub w dowolnym momencie przed zaksięgowaniem przyjęcia. Dla każdej pozycji serializowanej ze wstępnie zarejestrowanymi numerami seryjnymi wszystkie numery seryjne są automatycznie ustawiane na początkowy stan **Nie zarejestrowano** na tej stronie. Aby zweryfikować numery seryjne, można je zeskanować lub wprowadzić. Podczas wprowadzania numeru seryjnego aplikacja sprawdza, czy odpowiada on wstępnie zarejestrowanemu numerowi seryjnemu. Jeśli numery są zgodne, ich stan zmienia się na **Rejestrowanie**. W przeciwnym razie zostanie wyświetlony komunikat o błędzie. Można również bezpośrednio wybrać numer seryjny, a następnie wybrać opcję **Sprawdź numer seryjny** w okienku **Szczegóły**, aby szybko oznaczyć ten numer seryjny jako sprawdzony. Maksymalna liczba numerów seryjnych, które można zweryfikować na liście, jest równa ilości przyjmowanej.

Numery seryjne można również weryfikować na karcie **Wszystkie pozycje serializowane** na stronie **Zarządzanie numerami seryjnymi**. Na liście wybierz pozycję, względem której chcesz weryfikować numery seryjne.

## <a name="ship-serialized-items"></a>Wysyłka towarów serializowanych

Za pomocą operacji w aplikacji punktu sprzedaży **Zapasy wychodzące** można rejestrować numery seryjne na towarach serializowanych podczas wysyłania ich z bieżącego sklepu za pośrednictwem zamówienia przeniesienia.

### <a name="register-serial-numbers-against-serialized-items"></a>Rejestrowanie numerów seryjnych w odniesieniu do pozycji serializowanych

W przypadku zamówienia przeniesienia okno dialogowe, które monituje użytkownika podczas procesu wysyłki pozycji serializowanej, oferuje opcję **Zarządzania numerem seryjnym**. Można wybrać tę opcję, aby otworzyć stronę **Zarządzanie numerami seryjnymi** i rozpocząć rejestrowanie numerów seryjnych. Można również pominąć ten krok podczas procesu wysyłki i wprowadzić dane wejściowe później, przed zaksięgowaniem wysyłki.

Domyślnie jest wyświetlana karta dla bieżącej pozycji. Wszystkie wiersze numerów seryjnych mają pustą wartość numeru seryjnego i stan **Nie zarejestrowano**. Można zeskanować kody kreskowe numerów seryjnych lub wybrać pozycję **Numer seryjny** na pasku aplikacji w celu ciągłego wprowadzania numerów seryjnych. Numery seryjne, które wprowadzisz, pojawią się na liście, a stan wierszy tych numerów seryjnych zmieni się na **Rejestrowanie**. Maksymalna liczba numerów seryjnych, które można zarejestrować na liście, jest równa ilości wysyłanej. W przypadku popełnienia błędu możesz wybrać pozycję **Edytuj** lub **Wyczyść** w okienku **Szczegóły**, aby wprowadzić zmiany wprowadzonych numerów seryjnych.

Numery seryjne można również rejestrować na karcie **Wszystkie pozycje serializowane** na stronie **Zarządzanie numerami seryjnymi**. Na liście wybierz pozycję, względem której chcesz zarejestrować numery seryjne.

Opcjonalnie można włączyć sprawdzanie poprawności dostępności numeru seryjnego podczas rejestracji numeru seryjnego dla zamówienia przeniesienia wychodzącego. Przy takim sprawdzaniu w przypadku próby wysłania numeru seryjnego, który jest niedostępny w zapasach w magazynie wysyłek, zostanie wyświetlony komunikat o błędzie i trzeba podać inny numer.

Aby włączyć taką weryfikację jako wymaganie wstępne, należy zaplanować cykliczne wykonywanie następujących zadań:

- **Retail and Commerce** > **Retail and Commerce — składniki IT** > **Produkty i zapasy** > **Dostępność produktu z wymiarami śledzenia**
- **Retail and Commerce** > **Harmonogramy dystrybucji** > **1130** (**Dostępność produktu**)

## <a name="sell-serialized-items-in-pos"></a>Sprzedawaj towary z numerami seryjnymi w punkcie sprzedaży

Chociaż aplikacja POS zawsze obsługiwała sprzedaż towarów z numerami seryjnymi, w wersji Commerce 10.0.17 i nowszych organizacje mogą włączyć funkcje, które poprawiają logikę biznesową, która jest wyzwalana podczas sprzedaży produktów skonfigurowanych do śledzenia numerów seryjnych.

Gdy jest włączona funkcja **Ulepszone sprawdzanie poprawności numeru seryjnego podczas rejestrowania i realizacji zamówień w punkcie sprzedaży** w punktów sprzedaży, podczas sprzedaży produktów seryjnych w aplikacji POS są oceniane następujące konfiguracje produktów:

- **Ustawienia typu** numeru seryjnego produktu (**aktywne** lub **aktywne w sprzedaży**).
- Ustawienia **Dozwolony jest pusty problem** dla produktu.
- Ustawienia **Fizyczne ujemne zapasy** dla produktu i/lub magazynu sprzedaży.

### <a name="active-serial-configurations"></a>Aktywne konfiguracje numeru seryjnego

Gdy towary są sprzedawane w punkcie sprzedaży, który jest skonfigurowany z wymiarem śledzenia **Aktywny** numer seryjny, punkt sprzedaży inicjuje logikę weryfikacji, która uniemożliwia użytkownikom sfinalizowanie sprzedaży towaru z numerem seryjnym, którego nie można znaleźć w bieżącym stanie magazynu sprzedającego. Istnieją dwa wyjątki od tej reguły sprawdzania poprawności:

- Jeśli dla towaru jest również skonfigurowana opcja **Dozwolony pusty problem**, użytkownicy mogą pominąć wprowadzanie numeru seryjnego i sprzedawać towar bez wyznaczania numeru seryjnego.
- Jeśli towar i / lub magazyn sprzedaży jest skonfigurowany z włączonym **Fizycznie ujemnym stanem magazynowym**, aplikacja akceptuje i sprzedaje numer seryjny, którego nie można potwierdzić, że znajduje się w magazynie w magazynie, dla którego jest sprzedawany. Taka konfiguracja pozwala na ujemną wartość transakcji magazynowej dla tego konkretnego towaru / numeru seryjnego, a zatem system pozwoli na sprzedaż nieznanych numerów seryjnych.

> [!IMPORTANT]
> Aby upewnić się, że aplikacja POS może prawidłowo zweryfikować, czy numery seryjne sprzedawane dla **Aktywnych** towarów typu seryjnego znajdują się na stanie magazynu sprzedaży, organizacje muszą uruchamiać zadanie **Dostępność produktu ze śledzeniem wymiarów** w Commerce headquarters i towarzyszące **1130** zlecenie dystrybucji dostępności produktów za pośrednictwem Commerce headquarters w regularnych odstępach czasu. W miarę przyjmowania nowych serializowanych zapasów do magazynów sprzedaży, aby punkt sprzedaży mógł zweryfikować dostępność zapasów sprzedawanych numerów seryjnych, główny inwentarz musi często aktualizować bazę danych kanału najbardziej aktualnymi danymi o dostępności zapasów. Zadanie **Dostępność produktu z wymiarami śledzenia** zawiera bieżącą migawkę magazynu głównego, w tym numerów seryjnych, dla wszystkich magazynów firmy. W zadaniu dystrybucji **1130** migawka zapasów jest uwzględniana we wszystkich skonfigurowanych bazach danych kanału.

### <a name="active-in-sales-process-serial-configurations"></a>Aktywny w konfiguracjach seryjnych procesu sprzedaży

Pozycje skonfigurowane z wymiarem seryjnym jako **Aktywne w procesie sprzedaży** nie przechodzą przez żadną logikę walidacji zapasów, ponieważ ta konfiguracja oznacza, że numery seryjne zapasów nie są wstępnie rejestrowane w magazynie, a numery seryjne są przechwytywane tylko w momencie sprzedaży .  

Jeśli **Dozwolony jest pusty problem** jest również skonfigurowane dla **Aktywny w procesie sprzedaży** skonfigurowane pozycje, wpis numeru seryjnego można pominąć. Jeśli nie skonfigurowano **Dozwolony jest pusty problem**, aplikacja wymaga, aby użytkownik wprowadzał numer seryjny, nawet jeśli nie będzie on sprawdzany pod względem dostępnych zapasów.

### <a name="apply-serial-numbers-during-creation-of-pos-transactions"></a>Zastosuj numery seryjne podczas tworzenia transakcji POS

Aplikacja POS natychmiast monituje użytkowników o przechwycenie numeru seryjnego podczas sprzedaży towaru z numerem seryjnym, ale aplikacja umożliwia użytkownikom pominięcie wprowadzania numerów seryjnych do pewnego momentu w procesie sprzedaży. Kiedy użytkownik zaczyna pobierać płatność, aplikacja wymusza i wymaga wprowadzenia numeru seryjnego dla wszelkich pozycji, które nie są skonfigurowane do realizacji w przyszłych wysyłkach lub odbiorach. Wszelkie pozycje z numerami seryjnymi skonfigurowane do realizacji zamówienia typu kasowych lub zamówienia wymagają od użytkownika przechwycenia numeru seryjnego (lub wyrażenia zgody na pozostawienie go pustego, jeśli pozwala na to konfiguracja przedmiotu) przed zakończeniem sprzedaży.

W przypadku towarów z numerami seryjnymi sprzedawanych do przyszłego odbioru lub wysyłki, użytkownicy POS mogą pominąć wprowadzanie numeru seryjnego i nadal dokończyć tworzenie zamówienia klienta.   

> [!NOTE]
> W przypadku sprzedaży lub realizacji produktów z numerami seryjnymi za pośrednictwem aplikacji POS wymuszana jest ilość „1” dla towarów z numeracją seryjną w transakcji sprzedaży. Jest to wynik śledzenia informacji o numerze seryjnym w wierszu sprzedaży. W przypadku sprzedaży lub realizacji transakcji dla wielu towarów z numerami seryjnymi za pośrednictwem punktu sprzedaży, każdy wiersz sprzedaży musi być skonfigurowany tylko z ilością „1”. 

### <a name="apply-serial-numbers-during-customer-order-fulfillment-or-pickup"></a>Zastosuj numery seryjne podczas realizacji lub odbioru zamówienia klienta

Podczas wypełniania wierszy zamówień klientów dotyczących produktów z numerami seryjnymi za pomocą operacji **Realizacji zamówienia** w punkcie sprzedaży, POS wymusza przechwycenie numeru seryjnego przed ostateczną realizacją. W związku z tym, jeśli numer seryjny nie został podany podczas wstępnego rejestrowania zamówienia, musi zostać zarejestrowany podczas procesów kompletacji, pakowania lub wysyłki w punkcie sprzedaży. Walidacja jest wykonywana na każdym kroku, a użytkownik zostanie poproszony o podanie numeru seryjnego tylko wtedy, gdy go brakuje lub jest już nieaktualny. Na przykład, jeśli użytkownik pominie etapy pobierania lub pakowania i natychmiast zainicjuje wysyłkę, a numer seryjny nie został zarejestrowany dla linii, punkt sprzedaży będzie wymagał wprowadzenia numeru seryjnego przed zakończeniem ostatniego etapu faktury. Podczas wymuszania przechwytywania numeru seryjnego podczas operacji realizacji zamówień w punkcie sprzedaży nadal obowiązują wszystkie zasady wspomniane wcześniej w tym artykule. Tylko serializowane pozycje skonfigurowane jako **Aktywne** są przechodzić przez weryfikację zapasów o numerze seryjnym. Pozycje skonfigurowane jako **Aktywne w procesie sprzedaży** nie będą sprawdzane poprawność. Jeśli **Ujemne wartości magazynu fizycznego** są dozwolone dla **Aktywnych** produktów, będą przyjmowane numery seryjne, niezależnie od dostępności zapasów w magazynie. W przypadku towarów **Aktywnych** i **Aktywne w procesie sprzedaży**, jeśli skonfigurowano **Dozwolony jest pusty problem**, użytkownik może w razie potrzeby pozostawić puste numery seryjne podczas etapów pobrania, pakowania i wysyłki.

Weryfikacje numerów seryjnych będą również miały miejsce, gdy użytkownik wykonuje operacje odbioru zamówień klientów w punkcie sprzedaży. Aplikacja POS nie pozwala na sfinalizowanie odbioru produktu z numerami seryjnymi, chyba że przejdzie weryfikację, jak wspomniano wcześniej. Weryfikacje są zawsze oparte na wymiarze śledzenia produktu i sprzedaży konfiguracji magazynowych. 

## <a name="additional-resources"></a>Dodatkowe zasoby

[Operacja zapasów przychodzących w punkcie sprzedaży](./pos-inbound-inventory-operation.md)

[Operacja zapasów wychodzących w punkcie sprzedaży](./pos-outbound-inventory-operation.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]