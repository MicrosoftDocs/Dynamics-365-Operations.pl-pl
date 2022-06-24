---
title: Ustawienia parametrów kosztów z wyładunkiem
description: W tym artykule opisano sposób konfigurowania informacji ogólnych i ustawień konfiguracji, które są używane w module Koszty z wyładunkiem do księgowania, aktualizacji stanu, sekwencji numerów i zachowania.
author: Weijiesa
ms.date: 12/07/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ITMParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2020-12-07
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 99dbe17d4e83c2c75d52ca3fd22a1772d8045355
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8871986"
---
# <a name="landed-cost-parameters-setup"></a>Ustawienia parametrów kosztów z wyładunkiem

[!include [banner](../../includes/banner.md)]

Użyj strony **parametry kosztu z wyładunkiem** do konfigurowania informacji ogólnych i ustawień konfiguracji, które są używane w module **Koszty z wyładunkiem** do księgowania, aktualizacji stanu, sekwencji numerów i zachowania. Ustawienia parametrów są udostępniane w różnych firmach i mogą być modyfikowane przez administratora.

## <a name="open-the-landed-cost-parameters-page"></a>Otwórz stronę Parametry kosztów z wyładunkiem

Aby pracować z parametrami, przejdź do **Koszt z wyładunkiem \> Konfiguracja \> Parametry kosztu z wyładunkiem** i ustaw pola w sposób opisany w poniższych podsekcjach.

![Strona parametrów kosztów z wyładunkiem.](media/landed-cost-parameters.png "Strona parametrów kosztów z wyładunkiem")

## <a name="general-tab"></a>Karta Ogólne

### <a name="general-fasttab"></a>Skrócona karta Ogólne

W poniższej tabeli opisano pola dostępne na skróconej karcie **Ogólne** karty **Ogólne** na stronie **Parametry kosztu z wyładunkiem**.

| Ustawienie | opis |
|---|---|
| Użyj stawki wysyłki | Stawka wysyłki jest ustawiona na określony okres i jest używana do szacowania kosztów towarów, które korzystają z wielu walut. Ustaw tę opcję na wartość *Tak*, aby użyć stawki wysyłki. |
| Typ kursu wymiany | Domyślna kolekcja kursów wymiany używana do obliczeń wielowalutowych dla podróży i kosztów podróży. |
| Aktualizuj ilość zamówienia zakupu | Umożliwia wybór sytuacji, w której użytkownik zmieni ilość w wierszu zamówienia zakupu:<ul><li>**Akceptacja** — ilość dla podróży jest automatycznie korygowana.</li><li>**Ostrzeżenie** — jeśli wiersz jest dołączony do podróży, wyświetlane jest ostrzeżenie, ale jest aktualizowana ilość dla podróży.</li><li>**Błąd** — jeśli wiersz jest dołączony do podróży, wyświetlany jest komunikat o błędzie i nie można zaktualizować zamówienia zakupu. Dlatego wiersz zamówienia musi najpierw zostać usunięty z podróży.</li></ul> |
| Automatycznie aktualizuj liczbę kartonów | Jeśli dla tej opcji jest ustawiona wartość *Tak*, wszystkie kartony są dodawane razem i wyświetlane na poziomie podróży i kontenera. Jeśli ustawiono wartość *Nie*, liczba kartonów jest początkowo ustawiana na 0 (zero) i w razie potrzeby można ją ręcznie edytować. |

### <a name="costing-fasttab"></a>Skrócona karta Wycena

W poniższej tabeli opisano pola dostępne na skróconej karcie **Wycena** karty **Ogólne** na stronie **Parametry kosztu z wyładunkiem**.

| Ustawienie | opis |
|---|---|
| Specyfikacja księgowania | Umożliwia wybór korekty wartości w księdze:<ul><li>**Suma** — wartość całkowita księgowana w księdze.</li><li>**Grupa pozycji** – Korekta jest określona dla każdej grupy pozycji.</li><li>**Numer pozycji** – Korekta jest określona dla każdej pozycji. Ta wartość zapewnia najwięcej szczegółów.</li></ul> |
| Zezwalaj na zerowe koszty | Ustaw tę opcję na wartość *Nie*, aby pokazać błąd, jeśli użytkownik próbuje zaksięgować szacunek kosztów dla faktury za rejs lub zamówienia zakupu, które nie zawiera wartości oczekiwanego kosztu podróży. Komunikat o błędzie informuje, że nie można przypisać kosztu 0 (zero) i księgowanie faktury zakończy się niepowodzeniem. W takim przypadku użytkownik może ręcznie zaktualizować oszacowanie (lub ponownie skonfigurować koszt automatyczny), a następnie pobrać zaktualizowaną wartość lub usunąć koszt, jeśli nie ma on zastosowania.<p>Ustaw tę opcję na wartość *Tak*, aby umożliwić puste koszty podróży. W takim przypadku cena 0 (zero) będzie alokowana zgodnie z obszarem kosztów. Po otrzymaniu podróży faktura kosztów od dostawcy może zostać przetworzona na podstawie kosztu zerowego.</p><p>Zaleca się skonfigurowanie szacowania w rekordzie kosztów automatycznych, aby zapobiec pojawianiu się kosztu o zerowej cenie. To szacowanie nie jest całkowicie dokładne, ale powinno być bardziej dokładne niż zakładany koszt zerowy.</p> |
| Data księgowania korekty | W przypadku zaksięgowania faktury dla kosztów podróży rozrachunków z dostawcami zostanie również zaktualizowana tabela rozliczeń (korekty zapasów). Umożliwia wybór daty, która jest ustawiana domyślnie na stronie **Wybór kosztów podróży**, gdy jest w arkuszu faktur:<ul><li>**Data transakcji** – Użyj daty arkusza (data księgowania).</li><li>**Data faktury zamówienia zakupu** — użyj daty księgowania finansowego dla faktury akcji (zamówienia zakupu).</li><li>**Wybrana data** — użytkownik może określić datę księgowania. Mimo że data może być pusta, to jednak przy księgowana fakturze kosztowej użytkownik otrzyma komunikat o błędzie.</li></ul> |
| Użyj załącznika faktury zakupu | Jeśli dla tej opcji jest ustawiona wartość *Tak*, w transakcjach naliczania kosztów będzie używany ten sam numer załącznika, który jest używany dla faktury zakupu. Gdy jest ustawiona wartość *Nie*, system użyje następnego dostępnego numeru dla sekwencji numerów **Załączników naliczania kosztów**, która jest ustawiona na karcie **Sekwencje numerów** na stronie **Parametry kosztów z wyładunkiem**.<p>Ta opcja daje efekt tylko jeśli opcja **Księgowanie obciążenia konta w księdze** ma wartość *Tak* na karcie **Faktura** na stronie **Parametry rozrachunków z dostawcami**.</p> |
| Blokuj księgowanie ręczne na koncie rozliczeniowym | Ustaw tę opcję na wartość *Tak*, aby uniemożliwić księgowanie na kontach rozrachunkowych, na których transakcja nie została połączona z podróży, wybierając opcję **Funkcje \> Wybierz koszty podróży** w okienku akcji arkusza faktury od dostawcy. Zaleca się, aby dla tej opcji ustawić wartość *Tak*, aby można było poprawnie rozliczyć podróż i konto rozliczeniowe. |
| Użyj konta naliczania opłaty dla typu kosztu | Gdy ta opcja ma wartość *Tak*, do naliczania kosztów jako wydatek będzie używane konto naliczania opłat skonfigurowane dla odpowiedniego **Kodu typu kosztu** na stronie Kody typów kosztów.<p>Ta opcja daje efekt tylko jeśli opcja **Księgowanie obciążenia konta w księdze** ma wartość *Tak* na karcie **Faktura** na stronie **Parametry rozrachunków z dostawcami**. |
| Księguj korekty jako odchylenie | Jeśli dla tej opcji jest ustawiona wartość *Tak*, zastępuje ona standardowe funkcje i wymusza transakcje korekty zapasów związane z odchyleniami między kosztami szacowanymi a kosztami rzeczywistymi, które mają być księgowane na koncie odchylenia.<p>Jeśli dla tej opcji jest ustawiona wartość *Nie*, transakcje korekty zapasów powiązane z odchyleniami są obsługiwane na podstawie konfiguracji metody wyceny i kodu typu kosztu. W przypadku kosztu standardowego odchylenia nadal będą księgowane na koncie odchylenia. W przypadku średniej ważonej ruchomej (WMA) odchylenia są księgowane albo na koncie odchylenia, albo w zapasach.</p><p>Ta opcja daje efekt tylko jeśli opcja **Księgowanie obciążenia konta w księdze** ma wartość *Tak* na karcie **Faktura** na stronie **Parametry rozrachunków z dostawcami**.</p> |

### <a name="validation-fasttab"></a>Skrócona karta Weryfikacja

W poniższej tabeli opisano pola dostępne na skróconej karcie **Weryfikacja** karty **Ogólne** na stronie **Parametry kosztu z wyładunkiem**.

| Ustawienie | opis |
|---|---|
| Wiele faktur kosztowych | Umożliwia wybór sytuacji, w której więcej niż jedna faktura jest przetwarzana w związku z podróżą, folio lub kontenerem dla tej samej opłaty dodatkowe<ul><li>**Akceptacja** — system powinien zezwalać na wiele faktur kosztów.</li><li>**Ostrzeżenie** — wyświetlane jest ostrzeżenie.</li><li>**Błąd** – wyświetlany jest komunikat o błędzie.</li></ul> |
| Wielu dostawców na folio | Umożliwia wybór, co będzie się dzieje, jeśli do folio zostanie dodanych więcej niż jedno zamówienie zakupu dostawcy.<ul><li>**Akceptacja** — system powinien zezwolić na akcję.</li><li>**Ostrzeżenie** — wyświetlane jest ostrzeżenie, ale nadal można wykonać akcję.</li><li>**Błąd** — wyświetlany jest komunikat o błędzie i akcja jest blokowana.</li></ul><p>Konto brokera celnego lub przepisy lokalne mogą wymagać określonej wartości w tym polu.</p> |
| Tolerancja dla wielu metod dostawy | Umożliwia wybór, co będzie się dzieje, jeśli do tej podróży zostaną dodane towary z zamówienia zakupu, w których jest używana inna tryb dostawy niż podróży.<ul><li>**Akceptacja** — system powinien zezwolić na akcję.</li><li>**Ostrzeżenie** — wyświetlane jest ostrzeżenie, ale nadal można wykonać akcję.</li><li>**Błąd** — wyświetlany jest komunikat o błędzie i akcja jest blokowana.</li></ul> |
| Tolerancja dla wielu magazynów | Umożliwia wybór, co ma miejsce, jeśli podróż obejmuje kilka wierszy zamówienia, które należy dostarczyć do różnych magazynów. Te wiersze zamówienia mogą się rozłożyć na jednym lub większej liczby zamówień zakupu.<ul><li>**Akceptacja** — system powinien zezwolić na akcję.</li><li>**Ostrzeżenie** — wyświetlane jest ostrzeżenie.</li><li>**Błąd** – wyświetlany jest komunikat o błędzie.</li></ul> |
| Brak objętości | Umożliwia wybór sytuacji, w której użytkownik dodaje towar bez objętości do podróży.<ul><li>**Akceptacja** — system powinien zaakceptować pozycję.</li><li>**Ostrzeżenie** — wyświetlane jest ostrzeżenie.</li><li>**Błąd** – wyświetlany jest komunikat o błędzie.</li></ul><p>Jeśli do obliczania i obliczania kosztów administracyjnych są używane ilości, zalecane jest wybranie opcji *Ostrzeżenie* lub *Błąd*.</p> |
| Dostawca usług bez kosztów podróży | Wybierz, co ma miejsce, gdy użytkownik próbuje przetworzyć fakturę dla dostawcy usług, który nie został połączony z podróży. <ul><li>**Akceptacja** — system powinien zezwolić na akcję.</li><li>**Ostrzeżenie** — wyświetlane jest ostrzeżenie.</li><li>**Błąd** – wyświetlany jest komunikat o błędzie.</li></ul><p>Zalecamy wybranie opcji *Ostrzeżenie*.</p> |

### <a name="defaults-fasttab"></a>Skrócona karta wartości domyślnych

W poniższej tabeli opisano pola dostępne na skróconej karcie **Domyślne** karty **Ogólne** na stronie **Parametry kosztu z wyładunkiem**.

| Ustawienie | opis |
|---|---|
| Nazwa arkusza | Wybierz arkusz domyślny, który ma być używany przez funkcję *Utwórz arkusz przybycia*. |
| Stan podróży | Wybierz status, jaki musi mieć podróż, zanim użytkownicy będą mogli skonfigurować w systemie wynajmowany kontener transportowy. Taka akcja zazwyczaj ma miejsce, gdy towary są w drodze lub w doku. |
| Szablon podróży | Wybierz domyślny szablon podróży do użycia dla nowych wynajmowanych kontenerów transportowych. Zwykle wybierany jest szablon podróży, który zawiera koszty wynajmu. |
| Transakcje | Jeśli nadwyżka/niedomiar dla dostawy mieści się w zdefiniowanej tolerancji, dziennik przemieszczenia zostanie automatycznie przetworzony. Umożliwia wybór domyślnego arkusza ruchu. Pole **Konto przeciwstawne** dla wybranej nazwy arkusza przesunięć musi mieć wartość. |
| Przeniesienie | W przypadku przetworzenia niedostatecznej dostawy ilość z niedostateczną dostawą zostanie przeniesiona do magazynu niedoboru w dostawie. Umożliwia wybór domyślnego arkusza przeniesienia. |
| Wyłącz zamówienia zakupu niezwiązane z podróżą | Wyłącz funkcję dostawy nadmiaru/niedoboru kosztu z wyładunkiem dla zamówień, które nie są dołączone do podróży. |
| Wyłącz zamówienia zakupu niezwiązane z towarem w drodze | Wyłącz funkcję dostawy nadmiaru/niedoboru kosztu z wyładunkiem dla zamówień, które nie używają funkcji towarów w transporcie. |
| Okres prolongaty przyjęcia nadmiernej ilości towaru w drodze | Określ liczbę dni po pierwszym otrzymaniu kontenera wysyłkowego, przez które można nadal zrealizować dodatkowe nadliczenia dla tego kontenera wysyłkowego. |

## <a name="status-updates-tab"></a>Karta aktualizacji statusu

W celu wskazania stanu każdej podróży system używa wartości stanu. Wartości stanu podróży mogą być automatycznie stosowane do podróży za pośrednictwem śledzenia podróży lub okresowych zadań wsadowych. Można je także zastosować ręcznie, otwierając podróż, a następnie wybierając stan w grupie **Aktualizacji podróży** na karcie **Zarządzaj** w okienku akcji. 

Możesz utworzyć dowolną liczbę wartości statusu podróży. Jednak cztery z nich należy zdefiniować jako używane w specjalnych celach na karcie **Aktualizacje stanu** na stronie **Parametry kosztów z wyładunkiem**. W poniższej tabeli przedstawiono dostępne pola.

| Ustawienie | opis |
|---|---|
| Wyceniono | Umożliwia wybranie stanu podróży, który określa, że podróż została zakończona. |
| W trakcie przesyłania | Wybierz status podróży, który określa, że podróż jest w drodze. |
| Gotowa do wyceny | Wybierz status podróży, który określa, że podróż jest gotowa do wyceny. Ten stan jest używany, gdy wszystkie faktury zakupu zapasów i faktury kosztów podróży, dla których pole **Kredyt na koszt podróży** ma wartość *Dostawca*, zostały przetworzone w związku z podróżą. Podróży, które nie przejdą do wyceny, będą mieć stan *Gotowe do wyceny*.|
| Wstępnie wycenione | Wybierz status podróży, który określa, że podróż jest wstępnie wyceniana. Ten stan jest używany, gdy nowa transakcja kosztowa jest dodawana do podróży po już wycenie. Nowe transakcje kosztowe mogą zostać dodane do podróży, która była wcześniej wyceniona, po otrzymaniu drugiej faktury za fracht lub nieoczekiwanej opłaty za przestój. Ten stan jest automatycznie stosowany w przypadku dodania nowego kosztu podróży do wycenianych podróży. |

## <a name="voyage-creator-tab"></a>Karta Twórca podróży

W poniższej tabeli opisano sekcje na karcie **Twórca podróży** na stronie **Parametry kosztów z wyładunkiem**.

| Sekcja | opis |
|---|---|
| Przydziały | Pola **Tolerancja objętości zewnętrznej** i **Tolerancja wagi zewnętrznej** definiują progi, powyżej których towary są traktowane jako nadmuchiwne i przeważone. Jeśli użytkownik doda towary na stronie **Edytor podróży**, jeśli objętość lub waga przekroczy ustawioną w tym miejscu wartość, system będzie wyświetlać ostrzeżenie. Wartość każdego pola jest wyrażona jako procent maksymalnej objętości lub wagi ustawionej dla odpowiedniego typu kontenera wysyłkowego. Zaleca się, aby wartość w okresie od 5 do 10 procent maksymalnej objętości lub wagi. |
| Konfiguracja tworzenia folio | W czasie tworzenia podróży system może tworzyć wiele folio. Ta sekcja służy do definiowania, kiedy powinno zostać utworzone nowe folio. W przypadku każdego wiersza w tej sekcji system sprawdza określoną tabelę i pole oraz tworzy folio dla każdej unikatowej wartości pola. |

## <a name="cost-estimates-tab"></a>Karta oszacowania kosztów

Karta **Szacowanie kosztów** na stronie **Parametry kosztów z wyładunkiem** zawiera tylko jedno pole: **Domyślna wersja ceny**. To pole ma zastosowanie tylko w przypadku, gdy metodą wyceny jest *Wycena standardowa*. Umożliwia wybór domyślnej wersji wyceny do użycia w zadaniu okresowym *Aktualizacji kosztu zakupu towaru*. To ustawienie może być konieczne po każdym rozpoczęciem nowego roku finansowego.

## <a name="inventory-dimensions-tab"></a>Karta Wymiary magazynowe

Karta **Wymiary magazynowe** na stronie **Parametry kosztów z wyładunkiem** umożliwia kontrolowanie, które dostępne wymiary magazynowe powinny być domyślnie wyświetlane na poszczególnych stronach kosztów ziemnych, na których są używane wymiary.

Wybierz wymiar, a następnie ustaw opcje **Wiersze podróży**, **Towary w drodze** i/lub **Szacowanie kosztów** na *Tak* dla każdej strony, na której domyślnie powinien być wyświetlany ten wymiar. W razie potrzeby powtórz ten krok dla innych wymiarów.

Ustawienia na tej karcie ustalają wymiary domyślne dla poszczególnych wyznaczonych stron w różnych firmach. Użytkownicy pracujący na jednej z wyznaczonych stron mogą zastępować domyślne wymiary, wybierając w okienku akcji **Zapasy \> Wyświetl wymiary**.

## <a name="number-sequences-tab"></a>Karta Sekwencje numerów

Na karcie **Sekwencje numerów** na stronie **Parametry kosztów z wyładunkiem** są wszystkie typy sekwencji numerów referencyjnych, których wymaga koszt z wyładunkiem, ale nie są udostępniane w różnych firmach. Dla każdego odniesienia na liście wybierz kod sekwencji numerów.

> [!NOTE]
> W konfiguracji obejmującej wiele firm należy utworzyć różne sekwencje numerów dla każdej firmy (podmiotu prawnego).

## <a name="shared-number-sequences-tab"></a>Karta Wspólne sekwencje numerów

Na karcie **Wspólne sekwencje numerów** strona **Parametry kosztów z wyładunkiem** zawiera listę każdego typu sekwencji numerów referencyjnych, które są wspólne dla firm dla kosztów z wyładunkiem. Obecnie na liście jest tylko jedna sekwencja numerów. Ta sekwencja numerów jest używana dla identyfikatora podróży.

Na stronie **Wszystkie podróże** użytkownicy mogą wyświetlać wszystkie podróże we wszystkich firmach. Aby jednak edytować i przetwarzać podróży, użytkownicy muszą być w firmie wybranego rekordu.

## <a name="feature-visibility-tab"></a>Karta Widoczność funkcji

Koszt ziemski powoduje dodanie funkcji (pól i funkcji) do kilku często używanych stron w Microsoft Dynamics 365 Supply Chain Management. Strony te zawierają strony powiązane z danymi głównymi dostawcy, zwolnionymi produktami, zamówieniami zakupu, zamówieniami przeniesienia i ustawieniami magazynu. Jeśli używasz funkcji Koszt z wyładunkiem, te funkcje muszą być widoczne wszędzie, aby było można z nich korzystać. Jeśli nie używasz kosztu z wyładunkiem, możesz ukryć funkcje, aby nie przeszkadzały.

Na karcie **Widoczność funkcji** na stronie **Parametry kosztów z wyładunkiem** ustaw opcję **Aktywuj** na wartość *Tak*, aby funkcje kosztów ziemnych były widoczne, gdy tylko są dostępne. Ustaw wartość *Nie*, aby ukryć funkcje na wspólnych stronach poza kosztem z wyładunkiem. Jednak nawet jeśli jest ustawiona opcja *Nie*, sam moduł, w tym strona **Parametry kosztów z wyładunkiem**, pozostanie dostępny dla użytkowników, którzy mają odpowiednie uprawnienia dostępu do tego modułu.
