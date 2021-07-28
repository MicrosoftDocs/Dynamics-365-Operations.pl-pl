---
title: Plany konserwacji
description: W tym temacie wyjaśniono analizę plany konserwacji w module Zarządzanie składnikami majątku.
author: johanhoffmann
ms.date: 01/20/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetMaintenancePlan, EntAssetObjectType, EntAssetCounterType, EntAssetWorkOrderLifecycleModel
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 435e4c0b7aac8a8dc179ee8e74b985a4c434b7ea
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/06/2021
ms.locfileid: "6361121"
---
# <a name="maintenance-plans"></a>Plany konserwacji

[!include [banner](../../includes/banner.md)]

Plan konserwacji określa, kiedy należy wykonać wstępnie zaplanowane zadanie obsługi technicznej dotyczące składnika majątku. Plany konserwacji mogą być powiązane ze składnikami majątku, typami składników majątku, lokalizacjami czynności konserwacyjnych lub typami lokalizacji czynności konserwacyjnych, ale najpierw tworzone są plany konserwacji, które mają być używane w firmie.

Plan konserwacji może mieć wiele wierszy planu konserwacji. Typ i interwał zadania konserwacji są określone w wierszu planu konserwacji. Istnieją dwa typy wierszy planu konserwacji:

- Czas
- Licznik

Wiersze planu konserwacji typu „czas” są używane do cyklicznej planowanej konserwacji na podstawie stałego interwału czasu. Wiersze planu konserwacji typu „licznik” są używane do planowanych czynności konserwacyjnych lub reakcyjnych czynności konserwacji na podstawie rejestracji liczników składników majątku. Plan konserwacji może obejmować kilka wierszy planu konserwacji obu typów.

>[!NOTE]
>Jeśli dla danego typu licznika nie zostały zarejestrowane żadne wartości liczników, wiersze planu konserwacji są pomijane.

Najpierw należy utworzyć plany konserwacji, które są wymagane dla zadań konserwacji, oraz wybrać typy składników majątku, składniki majątku, typy lokalizacji czynności konserwacyjnych i lokalizacje czynności konserwacyjnych, które powinny być powiązane z każdym planem konserwacji. W razie potrzeby można również dodać plany konserwacji do składnika majątku lub lokalizacji czynności konserwacyjnych na karcie skróconej poprzez **Wszystkie składniki majątku** \> wybierz składnik majątku \> **Plany konserwacji składnika majątku** lub **Wszystkie lokalizacje czynności konserwacyjnych** \> wybrać lokalizację czynności konserwacyjnych \> skrócona karta **Plany konserwacji**.

W przypadku dodania planu konserwacji do typów składniku majątku lub typów lokalizacji czynności konserwacyjnych oznacza to, że w przypadku tworzenia nowych składników majatku lub lokalizacji czynności konserwacyjnych z tymi typami składników lub typami lokalizacji czynności konserwacyjnych, składnik majątku lub lokalizacja czynności konserwacyjnych zostaną automatycznie dodane do pola Plan konserwacji. Datą początkową w relacji z planem konserwacji jest data bieżąca, która może wymagać skorygowania.

## <a name="set-up-maintenance-plans"></a>Ustawianie planów konserwacji

W tej sekcji opisano sposób konfigurowania wierszy planu konserwacji oraz przykłady sposobów ich używania.

1. Przejdź do obszaru **Zarządzanie składnikami majątku \> Konfiguracja \> Konserwacja zapobiegawcza \> Plany konserwacji**.

1. Wybierz pozycję **Nowy**, aby utworzyć nową sekwencję.

1. Wstaw Identyfikator w polu **Sekwencja konserwacji** oraz nazwę w polu **Nazwa**.

1. W polu **Data planu** wstaw datę początkową, od której planowanie ma być wykonywane na planie konserwacji. Należy zauważyć, że wiersze planu konserwacji oparte na czasie mogą mieć inne daty planowania.

1. Aby uaktywnić plan konserwacji, wybierz wartość „tak” w przycisku przełączania **Aktywne**.

    >[!NOTE]
    >W przypadku dezaktywowania planu konserwacji w harmonogramie konserwacji nie będą tworzone żadne wpisy harmonogramu podczas wykonywania zadania planowania planu konserwacji.

1. Pola **Dni tolerancji przed** i **Dni tolerancji po** odnoszą się do wierszy planu eksploatacji, w których zaznaczone jest pole wyboru **Pomiń nakładające się zadania konserwacyjne** (zobacz krok 17). Pola „Tolerancja” służą do rozszerzania interwału w dniach, w którym, jeśli kilka planów eksploatacji nakłada się na siebie, jest tworzone jako wiersz harmonogramu konserwacji podczas planowania planu konserwacji, a w przypadku wielu nakładających się zadań są pomijane podczas planowania planu konserwacji. Wprowadź liczbę dni w polu **Dni tolerancji przed**, na przykład „2”.

1. Jeśli wcześniej wstawiono wartość **Dni tolerancji przed**, również w polu **Dni tolerancji po** wprowadzić liczbę dni, na przykład „2”.

    >[!NOTE]
    >Przykład opisany w tym i poprzednim kroku oznacza, że jeśli kilka wierszy planu konserwacji nakłada się na siebie, a dla co najmniej jednego wiersza wybrano **Pomiń nakładające się zadania konserwacyjne**, okres pomijania wierszy harmonogramu konserwacji jest rozszerzany łącznie pięć dni (oczekiwana data rozpoczęcia w wierszu harmonogramu konserwacji *i* dwa dni przed *i* dwa dni po tej dacie).

1. Pola w grupie **szczegółów** w skróconej karcie **Szczegóły** pokazują liczbę wierszy planu obsługi skonfigurowanych w planie eksploatacji oraz liczbę składników majątku i lokalizacje czynności konserwacyjnych związanych z planem konserwacji.

1. Na skróconej karcie **Wiersze** wybierz przycisk **Dodaj wiersz czasu** lub **Dodaj wiersz licznika składników majątku**, aby utworzyć nowy wiersz planu konserwacji.

1. Wprowadź opis w pierwszej linii pola **Opis zlecenia pracy**. Opis jest przenoszony do powiązanych zleceń pracy.

1. W polu **typ zadania konserwacji** wybierz typ zadania, które odnosi się do planu konserwacji.

1. W polach **Wariant typu zadania konserwacji** i **Zawód** zadania serwisowego wybierz wariant i zawód związany z typem zadania konserwacji.

1. W polach **Zakończ w ciągu dni** i **Zakończ w ciągu godzin** się w godzinach można wstawić oczekiwaną datę zakończenia w dniach lub godzinach. Oczekiwana data końcowa jest wpisywana w odniesieniu do daty początkowej, która jest obliczana podczas tworzenia wierszy harmonogramu konserwacji. Na przykład można wstawić wartość „7” w polu **Zakończ w ciągu dni**, aby wskazać, że powiązane zadanie powinno zostać wykonane w ciągu tygodnia od przewidywanej daty rozpoczęcia.

1. W polu **typ interwału** wybierz typ interwału, który ma być używany w wierszu planu eksploatacji, na przykład „powtórzone”. „ lub „raz...”. Aby uzyskać opis interwałów i typami wierszy, zobacz [Omówienie typów interwałów](#interval-types).

1. Pole **okres** dotyczy tylko typów wierszy opartych na czasie. Umożliwia wybranie typu okresu powiązanego z częstotliwością okresu.

1. W polu **częstotliwość okresu** wstaw, ile razy wiersz ma być używany do planowania zadań obsługi zapobiegawczej. Przykład: Jeśli utworzono wiersz typu „licznik”, a licznik jest ilością produkcji, a w tym polu zostanie wstawiony numer „20 000”, nowe wiersze sekwencji obsługi są tworzone podczas planowania konserwacji przed każdym oczekiwaniem zwiększenia produkcji o 20 000 więcej pozycji.

1. Pole **Pomiń nakładające się zadania konserwacyjne** zadania konserwacji odnosi się do typów wierszy i opartych na licznikach. To pole wyboru należy zaznaczyć, aby usunąć wpisy harmonogramu konserwacji utworzone w tym samym dniu. Ma to zastosowanie, jeśli na przykład utworzono 1-miesięczny wiersz kontroli, 6-miesięczny wiersz kontroli oraz roczny wiersz kontrolny. W przypadku 1-letniej kontroli użytkownik chce wykonać tylko tę inspekcję, a nie inne dwie inspekcje, które również mieszczą się w przedziale czasowym. Aby poprawnie ustawić ten przykład, należy skonfigurować roczny wiersz inspekcji jako pierwszy wiersz, 6-miesięczny wiersz oraz drugi wiersz i 1-miesięczny wiersz w trzecim wierszu, a następnie zaznaczyć pole wyboru **Pomiń nakładające się zadania konserwacyjne** dla 1- wiersze miesiąca i 6 miesięcy. W ten sposób można upewnić się, że po osiągnięciu 1-letniego znaku zostaną pominięte inspekcje o jeden miesiąc i sześć miesięcy, a wiersz harmonogramu konserwacji jest tworzony tylko dla 1-letniego wiersza inspekcji.

    >[!NOTE]
    >W przykładzie opisanym w tym kroku przedstawiono, że najbardziej wszechstronne zadanie, które zawiera największą liczbę zadań i które nie jest często wykonywane, powinno być zawsze wstawiane jako pierwszy wiersz. Bardziej częste zadania są następnie wstawiane jako osobne wiersze w kolejności częstotliwości, przy czym zadanie najczęściej jest umieszczane na dole listy.

1. Pole **Licznki** dotyczy tylko typów wierszy opartych na licznikach. Umożliwia wybranie typu licznika, który będzie używany w wierszu. Jeśli typ licznika nie jest aktywny dla powiązanego środka trwałego, wiersz planu konserwacji zostanie pominięty.

1. Wartość w polu **Ogrodzenie czasowe licznika zasobów w dniach** dotyczy tylko typów wierszy opartych na licznikach. Umożliwia wstawienie numeru określającego, ile dni rejestracji licznika zaległych są sprawdzane po zakończeniu planowania planów konserwacji. Oznacza to, jak daleko wstecz są dane (istniejące rejestracje liczników) używane jako podstawa do obliczania trendu, który określa liczbę wierszy harmonogramu konserwacji.

    >*Przykład:* jeśli oczekuje się, że rejestracje licznika mają być wykonane raz w miesiącu, w tym polu można wstawić numer „365”, ponieważ planowanie planowania obsługi jest zawsze oparte na 12-miesięcznych miesiącach i dlatego można tworzyć wiersze harmonogramu konserwacji na podstawie trendów minionego roku. Z drugiej strony, jeśli w tym polu zostanie wstawiony numer „10”, oczekuje się, że rejestracje liczników będą wykonywane częściej, np. w ujęciu dziennym. Oznacza to, że podczas planowania planowania obsługi, rejestracje licznika dla ostatnich 10 dni są używane jako podstawa planowania wierszy harmonogramu obsługi.

1. Pole **Data planu** dotyczy tylko typów wierszy opartych na czasie. Jeśli wiersz planu eksploatacji ma inną datę planowania niż cały plan obsługi, należy wybrać datę w polu **Data planu** w wierszu.

1. W polu **poziom usług** można wybrać poziom usługi zlecenia produkcyjnego jako dodatkowy ogranicznik w wierszu planu obsługi, który ma być używany jako poziom usług w zleceniach roboczych.

1. Zaznacz pole wyboru **Automatyczne tworzenie**, jeśli chcesz, aby zlecenie produkcyjne było automatycznie tworzone zgodnie z wybranym wierszem planu obsługi podczas planowania planów konserwacji.

1. Jeśli zaznaczono pole wyboru **automatyczne tworzenie**, można wybrać typ zlecenia produkcyjnego dla automatycznie utworzonego zlecenia produkcyjnego w polu **Typ zlecenia pracy**. Jeśli zaznaczono pole wyboru **Automatyczne tworzenie** i nie zostanie wybrany typ zlecenia pracy w tym polu, zostanie użyty typ zlecenia pracy wybrany w obszarze **Zarządzanie składnikami majątku \> Ustawienia \> Parametry zarządzania składnikami majątku \> link Zlecenia pracy** \> pole **Zlecenia pracy działań zapobiegawczych**.

1. Za pomocą pól **Sezon od** i **Sezon do** można utworzyć wiersz planu obsługi dla okresu powtarzania w okresie 12 miesięcy. *Przykład:* sprzęt używany do obsługi obszarów zielonych wymaga obsługi każdego źródła w wstępnie zdefiniowanym okresie. W polu **sezon od** wprowadź datę rozpoczęcia okresu, który ma zostać powtórzony.

1. W polu **sezon dp** wprowadź datę zakończenia okresu, który ma zostać powtórzony.

1. W polu **wynikowy okres** wyświetlany jest bieżący okres, który ma być powtórzony. Po upływie bieżącego okresu i rozpoczęciu nowego roku okres wyświetlany w tym polu zostanie zaktualizowany w celu uwzględnienia następnego okresu w sekwencji powtarzania.

1. Na skróconej karcie **Składniki majątku** wybierz składniki majątku, które powinny być powiązane z planem konserwacji.

1. Na skróconej karcie **typy składników majątku** wybierz typy składników majątku, które powinny być powiązane z planem konserwacji.

1. Na skróconej karcie **Lokalizacje czynności konserwacyjnych** wybierz typy lokalizacje czynności konserwacyjnych, które powinny być powiązane z planem konserwacji. W razie potrzeby można bardziej precyzyjnie ustawić ustawienia, wybierając odpowiedni typ, producenta i model składnika majątku.

1. Na skróconej karcie **Typy lokalizacji czynności konserwacyjnych** wybierz typy lokalizacji czynności konserwacyjnych, które powinny być powiązane z planem konserwacji.

>[!NOTE]
>Jeśli zlecenia produkcyjne są tworzone ręcznie na środkach, które zostały objęte gwarancją dostawcy, wyświetlane jest okno dialogowe, które użytkownik będzie wiedział o gwarancji. Utworzenie zlecenia produkcyjnego może zostać anulowane. Sprawdzanie relacji gwarancji jest pomijane dla automatycznie tworzonych zleceń produkcyjnych.

<a id="interval-types"></a>

## <a name="interval-types-overview"></a>Przegląd typów interwałów

| Typ i opis interwału | Typ wiersza: Czas | Typ wiersza: Licznik |
|---|---|---|
| **Typ interwału: powtórzony z** daty planu. Licznik rozpoczyna się od daty planu użycia. Podczas planowania planów konserwacji wiersze harmonogramu konserwacji są tworzonye po osiągnięciu interwału. | Zostanie użyta **Data planu** w wierszu planu konserwacji. Jeśli w wierszu nie wybrano daty planu, zostanie użyta **Data planu** dla planu konserwacji. Przykład: Jeśli w polu **Częstotliwość okresu** zostanie wstawiona liczba „3”, w polu **okres** zostanie wybrana wartość „rok”, nowy wiersz harmonogramu konserwacji będzie tworzony co 3 lata. | Zostanie użyta **Data planu** w wierszu planu konserwacji. Jeśli licznik został zastąpiony, jako data planu zostanie użyta Ostatnia data zastępcza. |
| **Typ interwału: powtórzony od daty rozpoczęcia** licznik rozpoczyna się od daty początkowej w relacji składnika majątku. Data jest wybierana w widoku szczegółów **Wszystkie składniki majątku** \> skrócona karta **Plany konserwacji składnika majątku** \> pole **Data początkowa** lub w widoku szczegółów **Wszystkie lokalizacje czynności konserwacyjnych** \> skrócona karta **Plany konserwacji** \> pole **Data początkowa**. Podczas planowania planów konserwacji wiersz harmonogramu konserwacji jest tworzony po osiągnięciu interwału. | Jest używana Data początkowa wiersza planu konserwacji składnika majątku lub lokalizacji czynności konserwatorskich. Jeśli to pole jest puste, używana jest **data planu** dla planu konserwacji. | Jest używana Data początkowa wiersza planu konserwacji składnika majątku lub lokalizacji czynności konserwatorskich. Jeśli to pole jest puste, używana jest **data planu** dla planu konserwacji. |
| **Typ interwału: powtarzane z poziomu ostatniego zlecenia pracy** licznik rozpoczyna się od rzeczywistej daty i godziny zakończenia ostatniego zlecenia pracy, które zostało wykonane na składniku, a następnie typu wariantu i kombinacji zawodu. Ta data i godzina jest wyświetlana w polu **zakończenie rzeczywiste** w widoku **Szczegóły zlecenia pracy**. | Rzeczywista data i godzina zakończenia zlecenia produkcyjnego zakończona w środku trwałym oraz na określonym typie zadania konserwacji/zadanie konserwacji typu wariant/kombinacja zawodu. Jeśli nie zostanie znalezione żadne zakończone zlecenie produkcyjne, w zamian zostanie użyty jedenaz dat użyta w polu „powtórzony od daty rozpoczęcia”. | Rzeczywista data i godzina zakończenia zlecenia produkcyjnego zakończona na środku trwałym *oraz* typ zadania obsługi typu/zadanie obsługi technicznej typu wariant/kombinacja zawodu. jest używane. Jeśli data i godzina zakończenia pozostały puste w zleceniu pracy, zamiast tego zostanie użyta jedna z dat użytych w opisanym powyżej typie interwału „Powtarzane od daty rozpoczęcia”. |
| **Typ interwału: raz od daty planu** zob. Opis typu interwału „powtórzony od daty planu” powyżej. Jedyna różnica polega na tym, że ten typ interwału ma być używany tylko raz. | Sprawdź opis „powtórzony względem daty planu” powyżej. Ten interwał jest zazwyczaj używany do jednorazowej obsługi lub zadania serwisowego. | Sprawdź opis „powtórzony względem daty planu” powyżej. Ten interwał jest zazwyczaj używany do jednorazowej obsługi lub zadania serwisowego. **Uwaga 1:** ten typ interwału jest odpowiedni tylko wtedy, gdy licznik jest zastępowany przy każdym wykonywaniu zadania konserwacji lub serwisu. Jeśli z jakiegoś powodu licznik został zastąpiony przed końcem planowanego okresu, nowy czas jest obliczany dla zadania od momentu zastąpienia licznika. **Uwaga 2:** Jeśli licznik zostanie zastąpiony podczas wykonywania zadania konserwacji lub serwisowego, ten typ interwału działa jako typ interwału „powtarzane od daty planu”. |
| **Typ interwału: raz od początkowej daty** zob. Opis typu interwału „powtórzony od początkowej daty” powyżej. Jedyna różnica polega na tym, że ten typ interwału ma być używany tylko raz. | Sprawdź opis „powtórzony względem początkowej daty” powyżej. Ten interwał jest zazwyczaj używany do jednorazowej obsługi lub zadania serwisowego. | Sprawdź opis „powtórzony względem początkowej daty” powyżej. Ten interwał jest zazwyczaj używany do jednorazowej obsługi lub zadania serwisowego. **Uwaga 1** ma również zastosowanie do tego typu interwałów. **Uwaga 3:** Jeśli licznik zostanie zastąpiony podczas wykonywania zadania konserwacji lub serwisowego, ten typ interwału działa jako typ interwału „powtarzane od początkowej daty”. |
| **Typ interwału: raz po osiągnięciu** tego typu interwału odnosi się tylko do liczników i jest używany do wskazywania górnego limitu skonfigurowanego w wierszu planu konserwacji. Wpisy harmonogramu konserwacji będą miały oczekiwaną datę i godzinę rozpoczęcia rejestracji liczników, co oznacza, że te zapisy zostaną utworzone z oczekiwaną datą rozpoczęcia równą lub wcześniejszą od daty systemowej. | Nie dotyczy | Interwał licznika oznacza górny limit. Jeśli ten limit zostanie przekroczony podczas tworzenia rejestracji licznika, podczas planowania obsługi profilaktycznej tworzony jest wiersz harmonogramu konserwacji. |
| **Typ interwału: raz poniżej osiągnięcia** tego typu interwału odnosi się tylko do liczników i jest używany do wskazywania dolnego limitu skonfigurowanego w wierszu planu konserwacji. Wpisy harmonogramu konserwacji będą miały oczekiwaną datę i godzinę rozpoczęcia rejestracji liczników, co oznacza, że te zapisy zostaną utworzone z oczekiwaną datą rozpoczęcia równą lub wcześniejszą od daty systemowej. | Nie dotyczy | Interwał licznika oznacza dolny limit. Jeśli ten limit zostanie przekroczony podczas tworzenia rejestracji licznika, podczas planowania obsługi profilaktycznej tworzony jest wiersz harmonogramu konserwacji. |
| **Typ interwału: połączony od Data** rozpoczęcia ten typ interwału powoduje tylko jednokrotne utworzenie wiersza harmonogramu konserwacji. Połączony od początkowej daty (tylko raz) plan konserwacji może zawierać więcej wierszy z harmonogramu konserwacji i te wiersze są połączone. Zazwyczaj tworzony jest plan konserwacji zawierający tylko wiersze danego typu interwału. Wiersze harmonogramu konserwacji są tworzone przez zidentyfikowanie wiersza planu eksploatacji, który ma pierwszą oczekiwaną datę i godzinę rozpoczęcia. | Sprawdź opis „Raz względem początkowej daty” powyżej. Przykład: dwa wiersze w planie konserwacji dla zadania serwisowego samochodu są tworzone w jednej linii opartej na czasie z rocznym okresem i jedną linią opartą na licznikach z limitem 25 000 km. Wiersz harmonogramu konserwacji jest tworzony dla limitu, który został osiągnięty jako pierwszy. W przypadku tego typu wiersza tworzony jest wiersz zawierający okres 1 roku. | Sprawdź opis „Raz względem początkowej daty” powyżej. Przykład: dwa wiersze w planie konserwacji dla zadania serwisowego samochodu są tworzone w jednej linii opartej na czasie z rocznym okresem i jedną linią opartą na licznikach z limitem 25 000 km. Wiersz harmonogramu konserwacji jest tworzony dla limitu, który został osiągnięty jako pierwszy. W przypadku tego typu wiersza tworzony jest wiersz zawierający limit 25 000 km. Przykład tworzenia dwóch wierszy licznika: można również skonfigurować plan konserwacji z dwoma połączonymi wierszami, w których pierwszy wiersz ma limit 10 000 sztuk towaru, a drugi wiersz odnosi się do stanowiska lub gniazda produkcyjnego wymagającego usługi po działaniu przez 3 000 godzin. |
| **Typ interwału: połączony od ostatniego zlecenia** produkcyjnego ten typ interwału powoduje utworzenie nowych wierszy harmonogramu konserwacji po każdym ukończonym zleceniu produkcyjnym. Plan konserwacji może zawierać więcej wierszy z harmonogramu konserwacji i te wiersze są połączone. Zazwyczaj tworzony jest plan konserwacji zawierający tylko wiersze harmonogramu konserwacji danego typu interwału. Wiersze harmonogramu konserwacji są tworzone przez zidentyfikowanie wiersza planu eksploatacji, który ma pierwszą oczekiwaną datę i godzinę rozpoczęcia. | Ten typ interwału działa jako „połączony od daty rozpoczęcia” opisany powyżej. Tylko różnica to data, w której jest oparty typ interwału. Zastosowana data jest faktyczną datą i godziną ostatniego zlecenia pracy zrealizowanego dla składnika majątku *oraz* typ zadania obsługi typu/zadanie obsługi technicznej typu wariant/kombinacja zawodu. | Ten typ interwału działa jako „połączony od daty rozpoczęcia” opisany powyżej. Tylko różnica to data, w której jest oparty typ interwału. Zastosowana data jest faktyczną datą i godziną ostatniego zlecenia pracy zrealizowanego dla składnika majątku *oraz* typ zadania obsługi typu/zadanie obsługi technicznej typu wariant/kombinacja zawodu. |
| **Typ interwału: powtarzany dla wartości zagregowanej (tylko licznik)** Po uruchomieniu planu konserwacji planowany wiersz konserwacji jest tworzony za każdym razem, gdy wartość skumulowana dla licznika środków trwałych osiąga częstotliwość okresu lub wielokrotność częstotliwości okresu. (Częstotliwość okresu jest definiowana w wierszu planu konserwacji).<p>Aby uzyskać więcej informacji dotyczących sposobu włączania i używania tej funkcji, zobacz sekcję [Rozszerzenia konserwacji opartej na licznikach](#counter-based-maintenance) w dalszej części tego tematu. | Nie dotyczy | **Przykład:** dla składnika majątku AK-101 ustawiono licznik godzin. Dla składnika majątku jest również ustawiony wiersz planu składników majątku. Typ interwału tego wiersza to *Powtarzany przy wartości zagregowanej (tylko licznik)*, a częstotliwość okresu wynosi *1000*. Podczas uruchamiania planu konserwacji wiersz zaplanowanej konserwacji zostanie wygenerowany, gdy wartość zagregowana licznika przekroczy 1000 godzin. Następnie, gdy zagregowana wartość licznika przekroczy 2000 godzin, zostanie wygenerowany kolejny zaplanowany wiersz konserwacji, i tak dalej dla każdego dodatkowego 1000 godzin. |
| **Typ interwału: raz dla wartości zagregowanej (tylko licznik)** Po uruchomieniu planu konserwacji wiersz konserwacji zaplanowanej jest tworzony, gdy wartość skumulowana dla licznika środków trwałych osiąga częstotliwość okresu zdefiniowaną w wierszu planu konserwacji.<p>Aby uzyskać więcej informacji dotyczących sposobu włączania i używania tej funkcji, zobacz sekcję [Rozszerzenia konserwacji opartej na licznikach](#counter-based-maintenance). | Nie dotyczy | **Przykład:** dla składnika majątku AK-101 ustawiono licznik godzin. Dla składnika majątku jest również ustawiony wiersz planu składników majątku. Typ interwału tego wiersza to *Raz przy wartości zagregowanej (tylko licznik)*, a częstotliwość okresu wynosi *1000*. Podczas uruchamiania planu konserwacji wiersz zaplanowanej konserwacji zostanie wygenerowany, gdy wartość zagregowana licznika przekroczy 1000 godzin. |

>[!NOTE]
>W przypadku tworzenia wierszy harmonogramu konserwacji dla wierszy planu eksploatacji opartego na czasie, oczekiwany czas jest zawsze rozpoczynany na początku dnia. W przypadku wierszy planu eksploatacji opartego na licznikach czas oczekiwania może przypadać w dowolnym czasie w ciągu dnia.

Poniżej znajdują się przykłady konfiguracji wierszy planu obsługi na podstawie czasu i licznika:

**Przykład 1 - Wiersz planu obsługi na podstawie czasu:** zadanie smarowania może zostać skonfigurowane w stałym interwale, występującym raz w tygodniu. W tym celu w polu **Typ interwału** wybierz opcję "Powtarzaj od daty planu". Zajrzyj na przykład na poniższej ilustracji.

![Zadanie usługi ustawione w stałym interwale czasu, które ma odbywać się raz w tygodniu.](media/02-preventive-maintenance.png "Zadanie usługi ustawione w stałym interwale czasu, które ma odbywać się raz w tygodniu")

**Przykład 2 - Wiersz planu konserwacji zależne od czasu:** w ciągu tygodnia może zostać utworzone zadanie inspekcyjne. W tym celu w polu **Typ interwału** wybierz opcję "Powtarzaj od daty ostatniego zlecenia pracy". Zajrzyj na przykład na poniższej ilustracji.

![Zadanie inspekcji ustawione tak, aby odbywało się około raz w tygodniu.](media/03-preventive-maintenance.png "Zadanie inspekcji ustawione tak, aby odbywało się około raz w tygodniu")

**Przykład 3 - Wiersz planu konserwacji oparty na licznikach:** Poniższa ilustracja licznika godzin, dla którego tworzony jest nowy wiersz harmonogramu konserwacji, za każdym razem, gdy minął 250 godzin. Typ interwału dla tej linii opartej na licznikach to „powtórzony od daty początkowej”. Data początkowa jest datą początkową powiązanych składników majątku w widoku szczegółów **Wszystkie składniki majątku** \> skrócona karta **Plany konserwacji składnika majątku** \> pole **Data początkowa** lub w widoku szczegółów **Lokalizacja czynności konserwacyjnych** \> skrócona karta **Plany konserwacji** \> pole **Data początkowa**. Jest to przykład planu konserwacji *profilaktycznej*, ponieważ wiersz harmonogramu konserwacji jest tworzony automatycznie za każdym razem, gdy zostanie osiągnięty próg (+ 250).

![Licznik godzinowy, który okresowo tworzy wiersze harmonogramu konserwacji.](media/04-preventive-maintenance.png "Licznik godzinowy, który okresowo tworzy wiersze harmonogramu konserwacji")

**Przykład 4 - Wiersz planu konserwacji oparty na licznikach:** Poniższa ilustracja przedstawiająca spadek wartości licznika, mierząc zużycie podkładki hamulcowej. Wiersz harmonogramu konserwacji jest tworzony, gdy na konsoli hamulcowej jest tworzona Rejestracja licznika znajdująca się poniżej 20 mm. Typ interwału dla tej linii opartej na licznikach to „Po osiągnięciu poniżej" lub „Po ostatniej dacie rozpoczęcia”. Jest to przykład planu konserwacji *reaktywnej*, ponieważ wiersz harmonogramu konserwacji nie jest tworzony automatycznie za każdym razem, gdy zostanie osiągnięty próg 20 mm.

![Zmniejszenie wartości licznika mierzącego zużycie klocków hamulcowych.](media/05-preventive-maintenance.png "Zmniejszenie wartości licznika mierzącego zużycie klocków hamulcowych")

**Przykład 5 - Wiersz planu konserwacji opartego na licznikach:** Poniższa ilustracja licznika o progu -18° Celsjusza. Wiersz harmonogramu konserwacji jest tworzony po przekroczeniu rejestracji licznika -18° Celsjusza. Typ interwału dla tej linii opartej na licznikach to „Po osiągnięciu powyżej”. Jest to przykład planu konserwacji *reaktywnej*, ponieważ wiersz harmonogramu konserwacji nie jest tworzony automatycznie za każdym razem, gdy zostanie osiągnięty próg -18° Celsius.

![Licznik z progiem -18°C.](media/06-preventive-maintenance.png "Licznik z progiem -18°C")

- Podczas tworzenia nowego środka trwałego, który używa typu środka trwałego związanego z planem eksploatacji, plan konserwacji jest automatycznie wstawiany na skróconej karcie **Wszystkie obiekty \> Plany konserwacji składników majątku**. Ponadto w przypadku **Ustawienia domyślne typu składnika majątku** w planach skróconej karcie **Plany konserwacji** zostaną automatycznie wstawione powiązane plany konserwacji.
- W przypadku dodawania lub usuwania typów środków trwałych lub typów lokalizacji czynności konserwacyjnych w **Plany konserwacji**, zmiana ta będzie odzwierciedlać tylko nowe środki trwałe utworzone po dokonaniu zmiany.
- Jeśli w obszarze **Plany konserwacji** zostaną dodane lub usunięte składniki majątku lub lokalizacje czynności konserwacyjnych, zmiana ta zostanie automatycznie zaktualizowana na skróconej karcie **Wszystkie składniki majątku \> Plany konserwacji składnika majątku** lub na skróconej karcie **Wszystkie lokalizacje czynności konserwacyjnych \> Plany konserwacji**.

Na poniższej ilustracji przedstawiono przykład planu eksploatacji „Obsługa samochodów” na stronie **Harmonogramy konserwacji**.

![Przykład planu konserwacji ciężarówki.](media/07-preventive-maintenance.png "Przykład planu konserwacji ciężarówki")

## <a name="add-a-maintenance-plan-to-an-asset"></a>Dodawanie planu konserwacji do składnika majątku

1. Przejdź do obszaru **Zarządzanie składnikami majątku \> Wspólne \> Składniki majątku \> Wszystkie składniki majątku** lub **Aktywne składniki majątku**.

1. Wybierz składnik majątku, dla którego chcesz skonfigurować plan konserwacji, i wybierz przycisk **Edytuj**.

1. Na skróconej karcie **Plany konserwacji składnika majątku** wybierz opcję **Dodaj wiersz**, aby dodać plany konserwacji do wybranego składnika majątku.

1. W polu **Plan konserwacji** wybierz odpowiedni plan konserwacji.

1. W polu **Data początkowa** wstaw datę początkową, od której planowanie ma być wykonywane prewencyjnych prac konserwacji. 

1. Wybierz opcję **Zapisz**. Pole **Aktywne** jest aktualizowane automatycznie.

Na poniższej ilustracji przedstawiono przykład planu konserwacji składnika majątku na stronie **Wszystkie składniki majatku**.

![Przykład planów konserwacji skonfigurowanych dla składnika majątku.](media/08-preventive-maintenance.png "Przykład planów konserwacji skonfigurowanych dla składnika majątku")

<a id="counter-based-maintenance"></a>

## <a name="counter-based-maintenance-enhancements"></a>Ulepszenia konserwacji opartej na licznikach

Funkcja *ulepszeń konserwacji opartej na licznikach* zawiera następujące funkcje:

- Opcja automatycznego wstawiania licznika o wartości *0* (zero) podczas tworzenia środka trwałego. Ta opcja może być użyteczna w przypadku używania konserwacji predykcyjnej opartej na licznikach. Jeśli funkcja *udoskonaleń konserwacji opartej na licznikach* nie jest używana, liczniki o wartości *0* (zero) muszą być wstawiane ręcznie.
- Możliwość konfigurowania licznika, dzięki czemu jest on automatycznie resetowany po zakończeniu zlecenia pracy. Ta funkcja jest przydatna do planowania konserwacji na podstawie zagregowanej wartości od czasu ukończenia ostatniego zlecenia pracy.
- Nowy typ interwału planu konserwacji o nazwie *Powtarzany dla wartości zagregowanej (tylko licznik)*. Ten typ wyzwala obsługę za każdym razem, gdy zagregowany licznik osiągnie wielokrotność określonej wartości. Na przykład konserwacja może być uruchamiana co 10 000 godzin. Aby uzyskać więcej informacji, zobacz sekcję [Omówienie typów interwałów](#interval-types) we wcześniejszej części tego tematu.
- Inny nowy typ interwału planu konserwacji o nazwie *Raz dla wartości zagregowanej (tylko licznik)*. Ten typ wyzwala obsługę, gdy zagregowany licznik osiągnie wielokrotność określonej wartości, np. 8000 godzin. Aby uzyskać więcej informacji, zobacz sekcję [Omówienie typów interwałów](#interval-types).

### <a name="turn-on-the-counter-based-maintenance-enhancements-feature"></a>Włączanie funkcji udoskonaleń konserwacji opartej na licznikach

Aby móc używać tej funkcji, należy ją włączyć w systemie. Administratorzy mogą skorzystać z ustawień [zarządzania funkcją](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby sprawdzić stan funkcji i włączyć ją. W obszarze roboczym **Zarządzanie funkcjami** ta funkcja widnieje jako:

- **Moduł:** *Zarządzanie składnikami majątku*
- **Nazwa funkcji:** *Udoskonalenia konserwacji opartej na licznikach*

### <a name="create-and-initialize-counters-when-an-asset-is-created"></a>Tworzenie i inicjowanie liczników podczas tworzenia składnika majątku

Przy każdym tworzeniu składnika majątku można automatycznie tworzyć powiązane liczniki środków trwałych, których wartość jest równa *0* (zero), pod warunkiem że system jest prawidłowo skonfigurowany, a składnik majątku prawidłowo tworzony.

1. Przejdź do **Zarządzanie składnikami majątku \> Ustawienia \> Typy składników majątku**.
1. Upewnij się, że istnieje typ składnika majątku odpowiedniego dla zaplanowanego nowego składnika majątku. Utwórz wymagany typ składnika majątku. Upewnij się, że na skróconej karcie **Liczniki** zostały wybrane wszystkie odpowiednie liczniki.
1. Przejdź do obszaru **Zarządzanie składnikami majątku \> Ustawienia \> Typy składników majątku \> Liczniki**.
1. Dla każdego odpowiedniego licznika upewnij się, że w polu **Zagregowana suma** jest ustawiona wartość *Suma*.
1. Na stronie **Wszystkie składniki majątku** utwórz składnik majątku.
1. Ustaw w polu **Typ składnika majątku** typ, który zidentyfikowano lub utworzono w kroku 2.
1. Zakończ odpowiednio konfigurowanie nowego składnika majątku.
1. Przejdź do obszaru **Zarządzanie składnikami majątku \> Zapytania \> Składniki majątku \> Liczniki**. Użytkownik powinien mieć możliwość znalezienia zainicjowanych liczników, które są ustawione dla nowego składnika majątku.

> [!NOTE]
> Podczas tworzenia zainicjowanych liczników składników majątku zakłada się, że składnik majątku nigdy nie został użyty przed dodaniem go do systemu. Podczas pierwszego uruchomienia harmonogramu konserwacji w obliczeniach używana jest data i wartość licznika *0* (zero) jako wartość bazowa do obliczania przyszłej konserwacji. Jeśli składniki majątku nie był nowy podczas dodawania do systemu, można ręcznie skorygować wartość licznika, aby był on taki sam, jak rzeczywista wartość licznika. Aby skorygować wartość licznika, otwórz odpowiedni składnik majątku na stronie **Wszystkie składniki majątku**, a następnie w okienku akcji na karcie **Składnik majątku** w grupie **Zapobiegawcza** wybierz pozycję **Liczniki**. Na stronie **Liczniki składników majątku** dla wybranego składnika majątku odpowiednio dostosuj wartość w kolumnie **Wartość** dla początkowego rekordu licznika.

### <a name="automatically-reset-a-counter-value"></a>Automatyczne resetowanie wartości licznika

Można skonfigurować system do automatycznego resetowania licznika za każdym razem, gdy odpowiednie zlecenie pracy osiągnie wybraną wartość stanu.

1. Przejdź do obszaru **Zarządzanie składnikami majątku \> Konfiguracja \> Konserwacja zapobiegawcza \> Plany konserwacji**.
1. W okienku listy wybierz plan konserwacji. Resetowanie licznika będzie dotyczyć wszystkich składników majątku, które używają tego planu.
1. W sekcji **Wiersze** znajdź wiersz licznika składnika majątku, dla którego chcesz zresetować licznik, i zaznacz pole wyboru **Resetuj licznik** dla tego wiersza. (Wiersze licznika składników majątku mają wartość w kolumnie **Licznik**. Licznik określony w tej kolumnie jest licznikiem, który zostanie zresetowany dla odpowiedniego środka trwałego).
1. Przejdź do obszaru **Zarządzanie składnikami majątku \> Ustawienia \> Zlecenia pracy \> Stany cyklu życia**.
1. W okienku listy wybierz stan cyklu życia zlecenia pracy, o którym powinien być resetowany odpowiedni licznik.
1. Na skróconej karcie **Ogólne** ustaw opcję **Resetuj licznik** na *Tak*.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]