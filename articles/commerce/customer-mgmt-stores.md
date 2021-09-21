---
title: Zarządzanie klientami w sklepach
description: W tym temacie wyjaśniono, w jaki sposób detaliści mogą włączyć funkcje zarządzania klientami w punkcie sprzedaży (POS) w Microsoft Dynamics 365 Commerce.
author: josaw1
ms.date: 09/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailOperations
audience: Application User, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: shajain
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 09caa7fa8f10d1afc44bb9343550bc633b8ec99a
ms.sourcegitcommit: d420b96d37093c26f0e99c548f036eb49a15ec30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/03/2021
ms.locfileid: "7472232"
---
# <a name="customer-management-in-stores"></a>Zarządzanie klientami w sklepach

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

W tym temacie wyjaśniono, w jaki sposób detaliści mogą włączyć funkcje zarządzania klientami w punkcie sprzedaży (POS) w Microsoft Dynamics 365 Commerce.

Bardzo ważne jest, aby skojarzyć ze sklepem możliwość tworzenia i edytowania rekordów odbiorcy w POS. W ten sposób mogą przechwytywać wszelkie aktualizacje informacji o odbiorcy, takie jak adres e-mail, numer telefonu i adres. Te informacje są pomocne w przypadku systemów przetwarzania od odbiorcy do odbiorcy, takich jak marketing, ponieważ ich efektywność zależy od dokładności danych klientów.

Skojarzenia sprzedaży mogą wyzwalać przepływ pracy tworzenia odbiorcy z dwóch punktów wejścia punktu sprzedaży. Mogą wybrać przycisk zamapowany na operację **Dodawania odbiorcy** lub wybrać pozycję **Utwórz klienta** na pasku aplikacji na stronie wyników wyszukiwania. W obu wypadkach zostanie wyświetlone okno dialogowe **Nowy odbiorca**, w którym skojarzeń ze sprzedażą może wprowadzić wymagane dane odbiorcy, takie jak imię i nazwisko, adres e-mail, numer telefonu, adres oraz wszelkie dodatkowe informacje związane z firmą. Te dodatkowe informacje można przechwytywać przy użyciu atrybutów odbiorcy, które są skojarzone z tym klientem. Aby uzyskać więcej informacji o atrybutach odbiorcy, zobacz temat [Atrybuty odbiorcy](dev-itpro/customer-attributes.md).

Skojarzenia sprzedaży mogą także przechwytywać pomocnicze adresy e-mail i numery telefonów. Ponadto mogą przechwytywać preferencje odbiorcy dotyczące otrzymywania informacji marketingowych za pośrednictwem dowolnego z tych pomocniczych adresów e-mail lub numerów telefonów. Aby włączyć tę funkcję, sprzedawcy detaliczni muszą włączyć funkcję **Przechwytywanie wielu wiadomości e-mail i numerów telefonów oraz zgody na marketing dla tych kontaktów** w obszarze roboczym **Zarządzanie funkcjami** w programie Commerce Headquarters (**Administrowanie systemem \> Obszary robocze \> Zarządzanie funkcjami**).

## <a name="default-customer-properties"></a>Domyślne właściwości odbiorcy

Sprzedawcy detaliczni mogą używać strony **Wszystkie sklepy** w programie Commerce Headquarters (**Retail i Commerce \> Kanały \> Sklepy**), aby skojarzyć domyślnego klienta z każdym sklepem. Następnie program Commerce kopiuje właściwości zdefiniowane dla odbiorcy domyślnego do wszystkich utworzonych rekordów nowych klientów. Na przykład w oknie dialogowym **Tworzenie odbiorcy** są wyświetlane właściwości dziedziczone po domyślnym odbiorcy skojarzonym ze sklepem. Te właściwości obejmują **typ odbiorcy**, **grupę klientów**, **opcje dotyczące paragonu**, **e-mail dla paragonu**, **walutę** i **język**. Wszystkie **przynależności** (grupy odbiorców) są także dziedziczone po odbiorcy domyślnym. **Wymiary finansowe** są jednak dziedziczone po grupie klientów skojarzonej z domyślnym klientem, a nie po samym odbiorcy domyślnym.

> [!NOTE]
> Wartość **e-mail odbiorcy** zostanie skopiowana z klienta domyślnego tylko w przypadku, gdy dla nowo utworzonych klientów nie zostanie podany identyfikator e-mail paragonu. Oznacza to, że jeśli identyfikator e-mail paragonu jest obecny przy domyślnym kliencie, to wszyscy klienci utworzeni z witryny e-commerce otrzymają ten sam identyfikator e-mail, ponieważ nie ma interfejsu użytkownika do przechwytywania identyfikatora e-mail paragonu od klienta. Zalecamy pozostawienie pola **e-mail dla paragonu** pustego dla domyślnego klienta sklepu i korzystanie z niego tylko w przypadku, gdy proces biznesowy jest uzależniony od obecności adresu e-mail paragonu. 

Skojarzenia sprzedaży mogą przechwytywać wiele adresów dla odbiorcy. Imię i nazwisko odbiorcy oraz numer telefonu są dziedziczone z informacji kontaktowych skojarzonych z każdym adresem. Skrócona karta **Adresy** rekordu odbiorcy zawiera pole **Cel**, które mogą edytować skojarzenia sprzedaży. Jeśli typem odbiorcy jest **Osoba**, domyślną wartością jest **Strona główna**. Jeśli typem odbiorcy jest **Organizacja**, domyślną wartością jest **Biznes**. Inne wartości, które obsługuje to pole, obejmują: **Strona główna**, **Biuro** i **Poczta**. Wartość pola **Kraj** w adresie jest dziedziczona z adresu podstawowego określonego na stronie **Jednostka operacyjna** w Commerce headquarters w **Administrowanie organizacją \> Organizacje \> Jednostki organizacyjne**.

## <a name="sync-customers-and-async-customers"></a>Synchronizuj odbiorców i odbiorców asynchronicznych

> [WAŻNE] Zawsze gdy POS działa w trybie offline, system automatycznie tworzy klientów asynchronicznie, nawet gdy tryb asynchronicznego tworzenia klientów jest wyłączony. Dlatego, niezależnie od wyboru między synchronicznym i asynchronicznym tworzeniem klienta, administratorzy centrali Commerce muszą utworzyć i zaplanować cykliczne zadanie wsadowe dla **zadania P**, czyli **Synchronizowanie odbiorców i partnerów biznesowych z zadania w trybie asynchronicznym** (nazywanego wcześniej zadaniem **synchronizacji klientów i partnerów biznesowych w trybie asynchronicznym**) oraz zadania **1010**, tak aby odbiorcy asynchroniczni byli konwertowani do odbiorców asynchronicznych w centrali Commerce.

W handlu istnieją dwa tryby tworzenia odbiorcy: Synchroniczny (lub Synchronizuj) i Asynchroniczny (lub Asynchroniczny). Domyślnie odbiorcy są tworzona synchronicznie. Są one tworzone w programie Commerce Headquarters w czasie rzeczywistym. Tryb tworzenia odbiorcy synchronizacji jest korzystne, ponieważ nowi odbiorcy mogą od razu podlegać wyszukiwaniu w różnych kanałach. Ma jednak także minusy. Ponieważ generuje on wywołania usługi [Commerce Data Exchange: Real-time Service](dev-itpro/define-retail-channel-communications-cdx.md#realtime-service) może to mieć wpływ na wydajność, jeśli wywołanych jest wiele równoczesnych wywołań tworzenia klientów.

Jeśli dla opcji **Utwórz odbiorcy w trybie asynchronicznym** jest ustawiona wartość **Tak** w profilu funkcji sklepu (**Retail i Commerce \> Ustawienia kanału \> Ustawienia sklepu online \> Profile funkcji**), wywołania usługi Real-time Service nie są używane do tworzenia rekordów klientów w bazie danych kanału Tryb tworzenia usługi Async Customer nie ma wpływu na wydajność centrali w programie Commerce Headquarters. Tymczasowy unikatowy identyfikator GUID jest przypisywany do każdego nowego rekordu usługi Async Customer i używany jako identyfikator konta odbiorcy. Ten identyfikator GUID nie jest wyświetlany użytkownikom w POS. Zamiast tego ci użytkownicy zobaczą identyfikator konta odbiorcy **Oczekująca synchronizacja**. 

### <a name="convert-async-customers-to-sync-customers"></a>Konwertuj klientów Async na klientów synchronizacji

Aby przekonwertować odbiorców asynchronicznych na odbiorców synchronizacji, należy najpierw uruchomić **zadanie P**, aby wysłać odbiorców asynchronicznych do programu Commerce Headquarters. Następnie uruchom zadanie **Synchronizowanie klientów i partnerów biznesowych z trybu asynchronicznego** (nazywanego wcześniej zadaniem **synchronizacji klientów i partnerów biznesowych w trybie asynchronicznym**), aby utworzyć identyfikatory kont klientów. Na koniec uruchom zadanie **1010**, aby zsynchronizować identyfikatory nowych kont odbiorcy z kanałami.

### <a name="async-customer-limitations"></a>Ograniczenia dotyczące odbiorcy usługi Async

Funkcje usługi Async Customer mają obecnie następujące ograniczenia:

- Nie można edytować rekordów odbiorcy asynchronicznego, jeśli odbiorca nie zostanie utworzony w programie Commerce Headquarters i nowy identyfikator konta odbiorcy zostanie zsynchronizowany z powrotem z kanałem. Dlatego nie można zapisać adresu odbiorcy asynchronicznego, dopóki ten odbiorca nie zostanie zsynchronizowany z centralą Commerce, ponieważ dodanie adresu odbiorcy jest zaimplementowane wewnętrznie jako operacja edycji w profilu odbiorcy. Jeśli jednak jest włączona funkcja **Włącz asynchroniczne tworzenie adresów klientów**, adresy odbiorców mogą być także zapisywane dla odbiorców asynchronicznych.
- Przynależności nie można skojarzyć z klientami asynchronicznym. Dlatego nowi odbiorcy asynchroniczni nie dziedziczą przynależności po odbiorcy domyślnym.
- Nie można wystawiać kart lojalnościowych dla odbiorców asynchronicznych, chyba że nowy identyfikator konta odbiorcy zostanie zsynchronizowany z powrotem z kanałem.
- Nie można przechwycić pomocniczych adresów e-mail i numerów telefonów dla odbiorców asynchronicznych.

Chociaż niektóre z wcześniej wymienionych ograniczeń mogą spowodować, że użytkownik wybrał opcję Synchronizuj klienta dla swojej firmy, zespół Commerce pracuje nad tym, aby możliwości odbiorcy asynchronicznego ściśle odpowiadały możliwościom synchronizacji klientów. Na przykład w wersji 10.0.22 systemu Commerce nowa funkcja **Włącz asynchroniczne tworzenie adresów klientów**, która może zostać włączona w obszarze roboczym **Zarządzanie funkcjami** asynchronicznie zapisuje nowo utworzone adresy odbiorców zarówno dla odbiorców synchronicznych, jak i odbiorców asynchronicznych. Aby zapisać te adresy w profilu klienta w centrali Commerce, musisz tworzyć i planować cykliczne zadanie wsadowe dla **zadania P**, zadanie **Synchronizowanie klientów i partnerów biznesowych z trybu asynchronicznego** oraz zadanie **1010**, aby dowolni odbiorcy asynchroniczni byli konwertowani na odbiorców synchronicznych w centrali Commerce.

### <a name="customer-creation-in-pos-offline-mode"></a>Tworzenie klienta w trybie offline POS

Zawsze gdy POS działa w trybie offline, system automatycznie tworzy klientów asynchronicznie, nawet gdy tryb asynchronicznego tworzenia klientów jest wyłączony. Dlatego, jak wspomniano wcześniej, administratorzy Commerce muszą tworzyć i planować cykliczne zadanie wsadowe dla **zadania P**, zadania **Synchronizowanie klientów i partnerów biznesowych z trybu asynchronicznego** oraz zadanie **1010**, aby dowolni odbiorcy asynchroniczni byli konwertowani na odbiorców synchronicznych w centrali Commerce.

> [!NOTE]
> Jeśli dla opcji **Filtruj udostępnione tabele danych klientów** jest ustawiona wartość **Tak** na stronie **Schematu kanału sprzedaży** (**Retail i Commerce \> ustawienia Headquarters \> Harmonogram handlu \> Grupy baz danych kanału**), rekordy klientów nie są tworzone w trybie offline w punktach sprzedaży. Aby uzyskać więcej informacji, zobacz [Wykluczenie danych offline](dev-itpro/implementation-considerations-cdx.md#offline-data-exclusion).

## <a name="additional-resources"></a>Dodatkowe zasoby

[Atrybuty odbiorcy](dev-itpro/customer-attributes.md)

[Wykluczanie danych w trybie offline](dev-itpro/implementation-considerations-cdx.md#offline-data-exclusion)
