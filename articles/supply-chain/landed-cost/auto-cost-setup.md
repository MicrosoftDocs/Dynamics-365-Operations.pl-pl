---
title: Ustawienia kosztów automatycznych
description: W tym temacie opisano sposób skonfigurowania reguł kosztów dla różnych poziomów podróży przychodzącej. Na podstawie tych reguł system oblicza koszty i automatycznie je dodaje. W związku z tym użytkownik nie musi ręcznie dodawać kosztów.
author: Weijiesa
ms.date: 01/21/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ITMCostAutoSetup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2021-01-21
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: ea788ea8d21c4cb6511188e937166bc3df3cd45a
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2022
ms.locfileid: "8695340"
---
# <a name="auto-costs-setup"></a>Ustawienia kosztów automatycznych

[!include [banner](../../includes/banner.md)]

Strona **Koszty automatyczne** umożliwia skonfigurowanie reguł kosztów dla różnych obszarów kosztów (takich jak podróży, kontenery wysyłki, folio, zamówienia zakupu, towary lub wiersze zamówienia przeniesienia). Na podstawie reguł i pól wybranych przez użytkowników podczas tworzenia rekordów dla jednego z obszarów kosztów system automatycznie obliczy koszty i doda je. W związku z tym użytkownik nie musi ręcznie dodawać kosztów.

Aby pracować z kosztami automatycznymi, przejdź do **Koszt z wyładunkiem \> Konfiguracja wyceny \> Koszty automatyczne**. Następnie skonfiguruj automatyczne reguły kosztów zgodnie z opisem w dalszej części tego tematu.

## <a name="work-with-cost-areas"></a>Pracuj z obszarami kosztów

Automatyczne koszty działają jak umowy handlowe czy automatyczne opłaty dodatkowe. Każdy rekord kosztów automatycznych należy do określonego poziomu kosztów. Pole **Obszar kosztów** w okienku listy na stronie **Automatyczne koszty** umożliwia wybór obszaru kosztów, z którym chcesz pracować. W okienku listy są wyświetlona tylko automatyczne koszty, które należą do aktualnie zaznaczonego obszaru kosztów. Tworzyć automatyczne koszty będą należeć do aktualnie zaznaczonego obszaru kosztów.

Obszary kosztów umożliwiają systemowi aplikować koszty w wierszach zamówień zakupu w obszarze kosztów. Na przykład koszt jednego kontenera wysyłkowego spowoduje awersję wartości do wszystkich produktów w tym kontenerze wysyłkowym. Jeśli istnieją co najmniej dwa kontenery wysyłkowe, można określić ten sam typ kosztu dla każdego kontenera wysyłkowego. W związku z tym typ kontenera może być używany do znalezienia poprawnego kosztu automatycznego.

## <a name="buttons-on-the-action-pane"></a>Przyciski w okienku akcji

W poniższej tabeli opisano przyciski, które są dostępne bezpośrednio w okienku akcji na stronie **Automatyczne koszty**.

| Przycisk | opis |
|---|---|
| Edycja | Edytuj istniejący koszt automatyczny. |
| Nowa | Tworzenie automatycznych kosztów. |
| Usuwanie | Usuwanie automatycznych kosztów. |
| Kopiuj z | Utwórz nowy rekord kosztu automatycznego oparty na istniejącym rekordzie. Następnie możesz swobodnie edytować nowy rekord. Ten przycisk pomaga szybko tworzyć nowe automatyczne koszty. |
| Wyświetl wymiary | Otwórz okno dialogowe, w którym można wybrać wymiary magazynowe, które są wyświetlane dla przeglądanych transakcji kosztowych. W przypadku wyczyszczenia pól wyboru dla transakcji kosztowych będzie wyświetlanych mniej wymiarów magazynowych. W związku z tym dla transakcji będzie wyświetlanych mniej szczegółów. Jeśli dla kosztu automatycznego określono wymiar magazynowy, koszt automatyczny będzie stosowany tylko w przypadku, gdy określony wymiar magazynowy jest używany dla towaru w podróży. |

## <a name="settings-on-the-header"></a>Ustawienia w nagłówku

Kombinacja ustawień w sekcji nagłówka określa, kiedy i jak określony automatyczny koszt jest dodawany do podróży. Automatyczny koszt będzie stosowany w podróży, kontenerze wysyłkowym lub folio tylko wtedy, gdy szczegóły automatycznego kosztu są zgodne ze szczegółami w nagłówku tego obszaru kosztów. Suma wszystkich pasujących kosztów automatycznych określa szacowany koszt z wyładunkiem podróży. Ten koszt jest aplikowany we wszystkich pozycjach na statku lub podróży.

W poniższej tabeli opisano wszystkie pola, które mogą pojawić się w sekcji nagłówka. Jednak określone dostępne pola różnią się w zależności od obszaru kosztów i aktualnie wybranych wymiarów.

| Pole | opis |
|---|---|
| **Kod konta** | <p>Należy wybrać jedną z następujących opcji:</p><ul><li>**Tabela** – Reguła kosztów dotyczy tylko określonego dostawcy.</li><li>**Grupa** – Reguła kosztów dotyczy tylko określonej grupy. System będzie szukać [grupy typów kosztów dostawcy](costing-parameters-setup.md) skojarzonej z rekordem dostawcy.</li><li>**Wszyscy** — Reguła kosztów dotyczy wszystkich dostawców. |
| **Firma przewozowa** | Wybierz dostawcę lub grupę dostawców, do których ma zastosowanie reguła kosztów. Pole to jest dostępne tylko w przypadku wybrania opcji *Tabela* lub *Grupa* w polu **Kod konta**. |
| **Broker urzędu celnego** | Wybierz dostawcę lub grupę dostawców, do których ma zastosowanie reguła kosztów. Pole to jest dostępne tylko w przypadku wybrania opcji *Tabela* lub *Grupa* w polu **Kod konta**. |
| **Kod pozycji** | <p>Należy wybrać jedną z następujących opcji:</p><ul><li>**Tabela** – Reguła kosztów dotyczy tylko określonej pozycji.</li><li>**Grupa** – Reguła kosztów dotyczy tylko określonej grupy pozycji. System będzie szukać [grupa typów kosztów towaru](costing-parameters-setup.md) skojarzonej z rekordem pozycji.</li><li>**Wszyscy** — Reguła kosztów dotyczy wszystkich pozycji.|
| **Relacja produktu** | Wybierz pozycję lub grupę pozycji, do których ma zastosowanie reguła kosztów. Pole to jest dostępne tylko w przypadku wybrania opcji *Tabela* lub *Grupa* w polu **Kod pozycji**. |
| **Metoda dostawy** | Umożliwia wybór trybu dostawy (np. lotniczy lub morski), do których ma zastosowanie reguła kosztu. |
| **Typ kontenera** | Typ kontenera wysyłkowego, w który zostaną wysłane towary. Koszt automatyczny można zastosować do podróży tylko wtedy, gdy typ kontenera jest taki sam jak typ kontenera dla podróży. |
| **Z portu** i **Do portu** | Port źródłowy („z”) i port docelowy („do”) podróży. (Niektóre kontenery mogą mieć różne porty „do”, ponieważ podróż może zatrzymywać się w wielu portach.) Koszt automatyczny można zastosować do podróży tylko wtedy, gdy porty „z” i „do” w ustawieniach kosztów automatycznych odpowiadają parametrom „ z „i„ do ”portów rejsu. |
| **Identyfikator kosztu automatycznego** | Unikalny identyfikator reguły kosztu automatycznego. Wartość w tym polu jest generowana automatycznie na podstawie sekwencji numerów ustawionej na stronie **Parametry kosztów z wyładunkiem**. |
| **Wymiary magazynowe** | W niektórych obszarach kosztów można uwzględnić jeden lub więcej wymiarów towaru w nagłówku (na przykład rozmiar, kolor, magazyn i numer partii). Wybierz opcję **Wyświetl wymiary** w okienku akcji, aby wybrać wymiary, które mają zostać uwzględnione. |

## <a name="settings-on-the-lines-fasttab"></a>Ustawienia na skróconej karcie Wiersze

Na skróconej karcie **Wierszy** dodaj wiersz dla każdej waluty, która może być używana, gdy koszt jest stosowany do wiersza zamówienia zakupu w podróży. 

W przypadku towarów i zamówień zakupu system dopasuje walutę każdego wiersza zamówienia zakupu do walut określonych na skróconej karcie **Wiersze**. Zostanie ona zastosować tylko do wartości kosztu ustawionej dla pasującego wiersza lub pozycji. Jeśli nie ustawiono wiersza dla waluty wiersza lub towaru, koszt automatyczny nie będzie stosowany do tego wiersza lub towaru.

W przypadku innych typów obszarów kosztów wszystkie wiersze na skróconej karcie **Wiersze** dotyczą każdej podróży, kontenera wysyłki, folio lub wiersza zamówienia przeniesienia, które są zgodne z wartościami ustalonymi w nagłówku.

W poniższej tabeli opisano wszystkie pola, które mogą pojawić się w każdym wierszu. Jednak konkretne dostępne pola różnią się w zależności od aktualnie wybranego obszaru kosztów.

| Pole | opis |
|---|---|
| **Waluta** | Umożliwia wybranie waluty, do jakiej odnosi się wiersz. Ta waluta jest powiązana z zamówieniem zakupu. Gdy system próbuje znaleźć koszty automatyczne, które powinny zostać zastosowane dla podróży i jej wierszy, wybierze wiersz, który ma tę samą walutę co zamówienie zakupu. To pole jest dostępne tylko wtedy, gdy w polu **Obszar kosztu** jest ustawiona wartość *Zamówienie zakupu* lub *Pozycja*. |
| **Kod typu kosztu** | Typ kosztu. |
| **Metoda przydziału** | <p>Metoda używana do dystrybucji kosztów do wierszy. Dostępne są następujące opcje:</p><ul><li><p>**Procent** — wartość pola **Wartość kosztu** jest wartością procentową, która ma zastosowanie do całkowitej wartości towarów.</p><p>Na przykład, jeśli w polu **Wartość kosztu** jest ustawiona wartość *10*, a łączna wartość towarów jest $800, wartość kosztowa wynosi $80 (= $800 × 10 procent).</p></li><li>**Ilość** — Koszt zostanie podzielony na podstawie ilości towarów.</li><li>**Kwota** — Koszt zostanie podzielony na podstawie wartości towarów.</li><li>**Objętość** — Koszt zostanie podzielony na podstawie objętości towarów. Objętość jest określona w głównym elemencie.</li><li>**Waga** — Koszt zostanie podzielony na podstawie wagi towarów. Waga jest określona w głównym elemencie.</li><li>**Wolumetryczny** — Koszt zostanie podzielony na podstawie objętościowego pomiaru towarów.</li><li><p>**Miara** – Ta opcja umożliwia wyświetlanie miary określonej w module **Koszt z wyładunkiem**. Jest często używane przez organizacje, które nie znają indywidualnej objętości lub wagi towarów, ale wymagają dokładniejszego podziału niż pozwalają na to opcję **Kwota** i **Ilość**. Spedytor lub agent dostarczy organizacji wagę lub wymiary sześcienne na poziomie towaru lub zamówienia.</p><p>Na przykład fracht jest równy $900. Towar A ma wagę 800 kilogramów (kg) i objętość 2 metrów sześciennych (m³). Pozycja B ma wagę 100 kg i objętość 1 m³. Oto wyniki podziału kosztów według wagi:</p><ul><li>Pozycja A = $800</li><li>Pozycja B = $100</li></ul><p>Oto wyniki podziału kosztów według objętości:</p><ul><li>Pozycja A = $600</li><li>Pozycja B = $300</li></ul><p>**Uwaga:** Gdy w polu **Metody obliczania** jest ustawiona wartość *Miara*, system używa miar wprowadzonych zarówno dla obszaru kosztów (kontener wysyłkowy), jak i dla wierszy. Te pomiary niekoniecznie muszą sumować się do oczekiwanej sumy. Jeśli jednak chcesz, aby sumowały się one do oczekiwanej sumy, możesz sprawdzić, korzystając ze statystyk, aby przejrzeć całkowity pomiar. Ustawienie monitu o miarę oraz automatyczna aktualizacja miary na poziomie wysyłki lub kontenera są ustawiane w nagłówku podróży.</p></li></ul> |
| **Data rozpoczęcia** | Umożliwia określenie początku zakresu dat dla wyceny, jeśli istnieje zakres dat. Ta data jest pierwszą datą dla automatycznego kosztu. |
| **Data Do** | Umożliwia określenie końca zakresu dat dla wyceny, jeśli istnieje zakres dat. Ta data jest ostatnią datą dla automatycznego kosztu. |
| **Kategoria** | <p>Wybierz metodę, która ma zostać użyta do obliczenia kosztu. Dostępne są następujące opcje:</p><ul><li>**Stały** — Koszt zostanie podzielony na podstawie metody podziału.</li><li>**Sztuki** — koszt będzie przydzielany na sztukę. W związku z tym metoda obliczania nie będzie używana.</li><li>**Procent** — zostanie dodana wartość procentowa wartości towarów. W związku z tym metoda obliczania nie będzie używana.</li><li>**Stawka** — tę opcję należy wybrać, jeśli występują podziały ilości. W polu **Metoda aplikacji** dla wiersza musi być ustawiona wartość *Miara*.</li><ul> |
| **Podzielone według ilości** | <p>To pole wyboru należy zaznaczyć, aby udostępnić przycisk **Podziały ilości** na skróconej karcie **Wiersze**. Podział ilości umożliwia rozbicie kosztów, a różne koszty mogą się różnić, w zależności od ilości w wierszu zamówienia zakupu dla podróży. Ta funkcja jest często używana, gdy trybem dostawy jest lotniczy. W polu **Kategoria** dla wiersza musi być ustawiona wartość *Stawka*.</p><p>Ilość odnosi się do opcji wybranej w polu **Metody obliczania**. Wartość kosztu jest maksymalną wartością wprowadzona w polu **Wartość kosztu**.<p>Na przykład ilości 45–100 kg dają opłatę w wysokości 6,00 USD za pomiar (np. kg/m³). Ilości przekraczające 100 kg powodują naliczenie opłaty w wysokości 5,50 USD za pomiar (np. kg/m³).</p> |
| **Wartość kosztowa** | Umożliwia wprowadzanie wartości kosztu. |
| **Kod waluty kosztu** | Wybierz walutę kosztu. |
| **Grupa podatków dla pozycji** | Wybierz kod podatkowy dla kosztu. |
| **Koszt minimalny** | <p>To pole jest stosowane tylko w przypadku, gdy zaznaczono pole wyboru **Przerwane przez ilość**. Jeśli miara nie osiągnie tej wartości, zostanie wybrana wartość minimalna, niezależnie od kosztów określonych na stronie **Podział ilości**.<p>Na przykład ilości 0–45 kg dają opłatę w wysokości 6 USD za pomiar (kg/m³). Ilości 46–100 kg dają opłatę w wysokości 5,50 USD za pomiar (kg/m³). Jeśli wysłane zostaną 2 kg, przerwa ilościowa spowoduje powstanie kosztu o wartości 12 USD. Jeśli jednak w polu **Koszt minimalny** zostanie ustawiona wartość *$100*, zostanie $100.</p> |
| **Agreguj** | Zaznaczenie tego pola wyboru umożliwia użytkownikom przeniesienie tego kosztu z poziomu kontenera wysyłkowego do poziomu podróży. W takim przypadku koszty mogą być obliczane automatycznie na poziomie kontenera wysyłkowego. Można je jednak również łączyć i rozdzielać na wszystkie elementy we wszystkich kontenerach podczas podróży, zamiast wszystkich przedmiotów w poszczególnych kontenerach transportowych. |
| **Typ kosztu połączonego** | <p>Umożliwia połączenie bieżącego wiersza z innym wierszem w tym samym rekordzie kosztu automatycznego przez określenie wartości **Kodu typu kosztu** dla wiersza, z którym ma nawiązać połączenie. Ta funkcja jest dostępna tylko wtedy, gdy w polu **Kategoria** dla bieżącego wiersza ustawiono wartość *Procent*. Gdy bieżący wiersz jest połączony z innym wierszem, koszt bieżącego wiersza jest oparty na kosztach innego wiersza.</p><p>Na przykład koszt frachtu $1000, a dopłata za paliwo ma być stanowi 10 procent kosztu frachtu. W takim przypadku wiersz musi mieć wartość **Kategorii** jako *Procent*, **Wartość kosztu** równą *10%* i wartość **Typu kosztu połączonego** jako *Fracht*.</p> |
| **Korekta wartości** i **Kwota korekty** | <p>Za pomocą tych pól można korygować wartości i kwoty dla różnych wartości procentowych. Są one dostępne tylko wtedy, gdy w polu **Obszar kosztu** jest ustawiona wartość *Pozycja*.</p><p>Dla różnych składników towaru można ustawić inną wycenę. Jeden składnik towaru może mieć inną wartość procentową kosztu niż pozostałe składniki tego towaru. Takie podejście jest czasami wymagane, aby wycenić określoną część towarów w różnych stawkach.</p><p>Na przykład cło dla zegara jest obliczane z użyciem dwóch stawek: jeden składnik zegara ma 10-procentową stawkę cła, a drugi składnik — 2 procent stawki cła. W takim przypadku koszty zostaną podzielone na dwa składniki.</p><p>Koszt jest obliczany dla towaru, ale wartość kosztu jest korygowana przez wartość składników, które mają inną kategorię kosztu. Koszt pozostałych składników można następnie obliczyć na podstawie kwoty, o jaką skorygowano poprzednie obliczenie.</p><p>Na przykład składnik A zegarka kosztuje 9,50 USD i cło w wysokości 10%, a składnik B kosztuje 0,50 USD i cło w wysokości 2%. Dlatego całkowity koszt wynosi 10,00 USD. Pierwszy wpis jest dla wiersza 10 procent. Używa następujących wartości:</p><ul><li>**Kategoria:** *Procent*</li><li>**Wartość kosztu:** *10*</li><li>**Skorygowana wartość:** *Skorygowana przez*</li><li>**Skorygowana wartość:** *-0,50*</li></ul><p>Ta konfiguracja określa, że koszt towaru (10 USD) musi zostać zmniejszony o 0,50 USD (cena składnika B) przed obliczeniem 10-procentowego cła. Dlatego 10 procent zostanie zastosowane do 9,50 USD.</p><p>Drugi wpis dotyczy 2-procentowego wiersza (0,50 USD, o który skorygowano poprzedni wpis). Używa następujących wartości:</p><ul><li>**Kategoria:** *Procent*</li><li>**Wartość kosztu:** *2*</li><li>**Skorygowana wartość:** *Wykorzystaj*</li><li>**Korekta:** *0,50*</li></ul><p>Ta konfiguracja umożliwia obliczenie pozostałej kwoty cła należnej w składniku B.</p> |
