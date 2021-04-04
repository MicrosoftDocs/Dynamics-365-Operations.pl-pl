---
title: Konfigurowanie reguł i opcji uprawnień
description: Określenie reguł i opcji dotyczących uprawnień w obszarze roboczym Zarządzanie świadczeniami w module Microsoft Dynamics 365 Human Resources.
author: andreabichsel
manager: tfehr
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 872b5cface7af19e2ef970e624c0cb5ce14e75b1
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/17/2021
ms.locfileid: "5466141"
---
# <a name="configure-eligibility-rules-and-options"></a>Konfigurowanie reguł i opcji uprawnień

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Po skonfigurowaniu niezbędnych parametrów zarządzania świadczeniami w module Microsoft Dynamics 365 Human Resources można utworzyć reguły uprawnień, pakiety, okresy i programy, które zostaną skojarzone z planami świadczeń.

## <a name="create-an-eligibility-rule"></a>Tworzenie reguły uprawnienia

Reguły uprawnień określają, którzy pracownicy mogą się rejestrować w poszczególnych planach świadczeń. Po zdefiniowaniu reguł uprawnień można je przypisywać do planów świadczeń. Następnie można przetwarzać uprawnienia do rejestracji, aby sprawdzić, którzy pracownicy są uprawnieni do poszczególnych planów. 

W czasie otwartej rejestracji pracownicy mogą wybierać plany świadczeń. Jeśli już po zarejestrowaniu przestaną się kwalifikować do planów świadczeń wskutek ustawienia określonych reguł uprawnień, nie zostaną automatycznie wyrejestrowani. Zazwyczaj po zmianie sytuacji życiowej, która wpływa na kwalifikowanie się do planów, jest inicjowany okres rejestracji, w którym pracownik może wybrać plany, do których ma uprawnienia. 

1. W obszarze roboczym **Zarządzanie świadczeniami** w sekcji **Konfiguracja** wybierz opcję **Reguły i opcje uprawnień**.

2. Na karcie **Reguły uprawnienia** wybierz opcję **Nowy**, aby utworzyć regułę uprawnienia. Aby wyświetlić plany skojarzone z regułą uprawnienia, wybierz opcję **Dołączone plany**.

3. Określ wartości dla następujących pól:

   | Pole | Opis |
   | --- | --- |
   | **Reguła uprawnienia** | Unikatowy identyfikator reguły uprawnienia. |
   | **Opis** | Opis reguły uprawnienia. |
   | **Data i godzina wejścia w życie** | Data rozpoczęcia obowiązywania reguły uprawnienia. | 
   | **Data i godzina ważności** | Data zakończenia obowiązywania reguły uprawnienia. |
   | **Użyj typu pracownika etatowego** | Określa, czy w regule uprawnienia do świadczeń ma być używane określenie typu pracownika etatowego. |
   | **Typ pracownika** | Typ pracownika, jeśli w przełączniku **Użyj typu pracownika etatowego** ustawiono wartość **Tak**. |
   | **Użyj stanu pracownika etatowego** | Określa, czy w regule uprawnienia do świadczeń ma być używane określenie stanu zatrudnienia pracownika etatowego. |
   | **Stan** | Stan pracownika etatowego, jeśli w przełączniku **Użyj stanu pracownika etatowego** ustawiono wartość **Tak**. Jeżeli w przełączniku **Użyj stanu pracownika etatowego** ustawiono wartość **Nie**, pole nie jest używane. |
   | **Użyj kategorii zatrudnienia** | Określa, czy w regule uprawnienia do świadczeń ma być używana wartość parametru **Kategoria zatrudnienia** dotycząca pracownika etatowego. | 
   | **Kategoria zatrudnienia** | Kategoria zatrudnienia pracownika, jeśli w przełączniku **Użyj kategorii zatrudnienia** ustawiono wartość **Tak**. |
   | **Użyj nowej reguły zatrudnienia** | Określa, czy w regule uprawnienia do świadczeń ma być używana wartość nowego okresu zatrudnienia nowo zatrudnionej osoby. |
   | **Okres rejestracji** | Okres, w którym jest dozwolone rejestrowanie nowo zatrudnionej osoby. Jeśli tę opcję ustawisz również w parametrach, tamto ustawienie ma pierwszeństwo wobec tego. |
   | **Użyj stanu wcześniejszego zatrudnienia** | Określa, czy w regule uprawnienia do świadczeń ma być używany stan zatrudnienia poprzedniego pracownika etatowego. Można na przykład określić regułę uprawnienia, która obejmuje okres oczekiwania na pokrycie dla wszystkich pracowników, którzy przeszli ze stanu **Zwolniono** na **Zatrudniono** w ciągu 90 dni od poprzedniego zatrudnienia. |

4. W obszarze **Kryteria dodatkowe** wybierz następujące opcje i w razie potrzeby dodaj informacje:

   | Opcja | Opis |
   | --- | --- |
   | **Uprawniony zakres wieku** | Określa zakres lub zakresy wieku wymagane do spełnienia reguły uprawnienia. |
   | **Uprawniony dział** | Określa dział lub działy, do których pracownik musi należeć, aby spełniać regułę uprawnienia. |
   | **Typ kwalifikującego się zatrudnienia** | Określa typ lub typy zatrudnienia, jakie musi mieć ustawione pracownik, aby spełniać regułę uprawnienia. Na przykład Pełny etat lub Część etatu. |
   | **Uprawnione stanowiska pracy** | Określa funkcję lub funkcje spełniające regułę uprawnienia. Funkcje są skojarzone ze stanowiskami, a stanowiska są obsadzane przez pracowników. |
   | **Funkcja stanowiska uprawnienia** | Określa funkcję lub funkcje stanowiska spełniające regułę uprawnienia. Na przykład Sprzedawcy lub Serwisanci. |
   | **Typ zadania uprawnienia** | Określa typ lub typy funkcji spełniające regułę uprawnienia. Na przykład Pracownik biurowy lub Dyrektor. |
   | **Uprawniona firma** | Określa firmę lub firmy, do których ma zastosowanie reguła uprawnienia. Na przykład Contoso Entertainment System USA. |
   | **Region uprawnionego wynagrodzenia** | Określa lokalizację pracownika etatowego spełniającą regułę uprawnienia. Na przykład Środkowe stany USA. |
   | **Uprawnione stanowisko** | Określa stanowisko lub stanowiska spełniające regułę uprawnienia. Na przykład Asystent w dziale kadr lub Kierownik działu kadr. |
   | **Typ kwalifikującego się stanowiska** | Określa typ lub typy stanowisk spełniające regułę uprawnienia. Na przykład Pełny etat. |
   | **Stan uprawniony** | Określa stany/województwa/prowincje itd. spełniające regułę uprawnienia. Na przykład Dakota Północna USA lub Kolumbia Brytyjska, Kanada. |
   | **Kwalifikujące się warunki zatrudnienia** | Określa warunki zatrudnienia spełniające regułę uprawnienia. Na przykład Bez gwarancji zatrudnienia lub Umowa zbiorowa. |
   | **Uprawniony związek** | Określa związki zawodowe, do których przynależność spełnia regułę uprawnienia. Na przykład Amerykański związek zawodowy operatorów wózków widłowych. </br></br>W przypadku używania reguły uprawnienia z kryterium związku zawodowego rekord przynależności do związku musi mieć wypełnioną datę końcową. Nie można pozostawić tego pola pustego. |
   | **Uprawniony kod pocztowy** | Określa kody pocztowe spełniające regułę uprawnienia. Na przykład 58104. |

5. W obszarze **Dodatkowe szczegóły** można obejrzeć następujące dodatkowe informacje:

   | Pole | Opis |
   | --- | --- |
   | **Pole uprawnionego użytkownika** | Określa dodatkowe reguły uprawnień oparte na polach zdefiniowanych przez klienta. |
   | **Typ uprawnienia** | Określa kategorię kryteriów wybranych w obszarze **Kryteria dodatkowe**. |
   | **Odwołanie do uprawnienia** | Określa wartości wybrane w obszarze **Kryteria dodatkowe**. |
   | **Opis** | Opis wybrany w obszarze **Kryteria dodatkowe**. |

6. Wybierz opcję **Zapisz**.

## <a name="configure-bundles"></a>Konfigurowanie pakietów

Pakiety to zestawy powiązanych planów świadczeń. Pakietów świadczeń można używać do grupowania planów świadczeń, które pracownik musi wybrać, aby się zarejestrować w niektórych planach świadczeń uzależnionych od rejestracji w innych planach świadczeń. Przykłady sytuacji, kiedy może być konieczne użycie pakietów:

- Pakiet planów opieki zdrowotnej, który obejmuje ubezpieczenie zdrowotne z wysokim udziałem własnym i powiązanym rachunkiem oszczędnościowym (HSA).

- Plan ubezpieczenia na życie, w którym obowiązkowy plan ubezpieczenia na życie pracownika jest powiązany z ubezpieczeniem na życie osoby będącej na utrzymaniu. Pakiet gwarantuje, że pracownik nie będzie mógł wybrać ubezpieczenia na życie dla osoby na utrzymaniu bez równoczesnego zawarcia ubezpieczenia dla siebie.

1. W obszarze roboczym **Zarządzanie świadczeniami** w sekcji **Konfiguracja** wybierz opcję **Reguły i opcje uprawnień**.

2. Na karcie **Pakiety** wybierz opcję **Nowy**, aby utworzyć pakiet. Aby wyświetlić plany skojarzone z pakietem, wybierz opcję **Dołączone plany**.

3. Określ wartości dla następujących pól:

   | Pole | Opis |
   | --- | --- |
   | **Pakiet** | Unikatowy identyfikator pakietu. |
   | **Opis** | Opis pakietu. |
   | **Główna** | Wskazuje, czy jeden z planów w pakiecie musi być oznaczony jako plan główny. Aby administrator świadczeń mógł potwierdzić wybór świadczeń przez pracownika, należy w czasie otwartej rejestracji wybrać plan główny jako część pakietu. |
   | **Data i godzina wejścia w życie** | Data i godzina aktywacji pakietu. |
   | **Obowiązuje do** | Data wygaśnięcia pakietu. Domyślnie to 31.12.2154, czyli nigdy. |

4. Wybierz opcję **Zapisz**.

## <a name="configure-periods"></a>Konfigurowanie okresów

Okresy wskazują, kiedy świadczenia obowiązują i kiedy pracownicy mogą się rejestrować. Można utworzyć dowolną liczbę okresów, aby zarządzać okresami otwartych rejestracji na świadczenia i okresami objęcia świadczeniami. Lata planów świadczeń mogą być zgodne z latami kalendarzowymi, ale nie muszą. 

1. W obszarze roboczym **Zarządzanie świadczeniami** w sekcji **Konfiguracja** wybierz opcję **Reguły i opcje uprawnień**.

2. Na karcie **Okresy** wybierz opcję **Nowy**, aby utworzyć okres. Aby uruchomić proces, który dołączy wszystkie ważne aktywne plany świadczeń do okresu świadczeniowego, wybierz opcję **Dołącz plany**. Aby wyświetlić plany skojarzone z pakietem, wybierz opcję **Dołączone plany**. 

3. Określ wartości dla następujących pól:

   | Pole | Opis |
   | --- | --- |
   | **Okres** | Unikatowy identyfikator okresu. |
   | **Data i godzina wejścia w życie** | Data i godzina, od kiedy okres świadczeniowy jest aktywny. |
   | **Data i godzina ważności** | Data i godzina, kiedy okres świadczeniowy staje się nieaktywny. |
   | **Rozpoczęcie rejestracji** | Data rozpoczęcia otwartej rejestracji. Otwarta rejestracja to sytuacja, kiedy pracownik etatowy może wybierać sobie świadczenia z puli dostępnej do samoobsługi. |
   | **Koniec rejestracji** | Data zakończenia otwartej rejestracji. |
   | **Otwieranie** | Wskazuje, czy okres jest otwarty, w oparciu o datę systemową oraz daty i godziny rozpoczęcia i zakończenia ważności. | 
   | **Poprzedni okres** | Określa okres świadczeniowy poprzedzający wybrany okres świadczeniowy. Ta informacja jest używana podczas rejestrowania uprawnień do świadczeń w celu przypisywania planów, opcji objęcia świadczeniami i osób ubezpieczonych z poprzedniego roku. |
 
4. Wybierz opcję **Zapisz**.

## <a name="use-a-flex-credit-program"></a>Korzystanie z programu kredytu elastycznego

Za pomocą programów kredytu elastycznego można rejestrować pracowników na świadczenia zgodnie z ustaloną wcześniej liczbą elastycznych punktów kredytowych. Pracownicy mogą wybrać sposób przydzielania ich elastycznych punktów kredytowych. Na przykład jeśli pracownik jest objęty planem ubezpieczenia zdrowotnego swojego małżonka, może chcieć wykorzystać punkty kredytowe, które normalnie przeznaczyłby na ubezpieczenie zdrowotne, na inne świadczenia.

1. W obszarze roboczym **Zarządzanie świadczeniami** w sekcji **Konfiguracja** wybierz opcję **Reguły i opcje uprawnień**.

2. Na karcie **Okresy** wybierz opcję **Programy kredytu elastycznego**.

3. Wybierz program kredytu elastycznego, który ma zostać zastosowany. Okno zawiera następujące pola:

   | Pole | Opis |
   | --- | --- |
   | Identyfikator kredytu świadczenia | Unikatowy identyfikator programu kredytu elastycznego. |
   | Opis | Opis programu kredytu elastycznego. | 
   | Data Od | Data i godzina aktywacji programu kredytu elastycznego. |
   | Data Do | Data i godzina zakończenia działania programu kredytu elastycznego. Można pozostawić wartość domyślną (31.12.2154), aby wskazać, że program kredytu elastycznego nie ma zaplanowanego okresu ważności. |
   | Suma wartości kredytu | Liczba punktów kredytowych, jakie będzie miał każdy pracownik na swoje świadczenia. |
   | Reguła naliczania proporcjonalnego | Reguła używana do proporcjonalnego obliczania liczby elastycznych punktów kredytowych, gdy pracownik zostanie zatrudniony w trakcie okresu wykorzystywania elastycznych punktów kredytowych. </br></br><ul><li>**Brak** — pracownik nie otrzymuje żadnych elastycznych punktów kredytowych, jeśli zostanie zatrudniony po rozpoczęciu okresu programu kredytu elastycznego.</li><li>**Pełny kredyt** — pracownik otrzymuje pełną liczbę elastycznych punktów kredytowych, niezależnie od momentu, w którym został zatrudniony.</li><li>**Naliczanie proporcjonalne** — pracownik otrzymuje liczbę elastycznych punktów kredytowych proporcjonalną do daty rozpoczęcia zatrudnienia.</li></ul> |
   | Formuła naliczania proporcjonalnego kredytu elastycznego | Reguła używana do proporcjonalnego obliczania liczby elastycznych punktów kredytowych dla pracowników, którzy zostali zatrudnieni w trakcie okresu świadczeniowego zdefiniowanego w programie kredytu elastycznego. Naliczanie proporcjonalne jest oparte na dacie rozpoczęcia zatrudnienia. To pole jest używane tylko w przypadku zaznaczenia wartości **Naliczanie proporcjonalne** w polu **Reguła naliczania proporcjonalnego**. </br></br><ul><li>**Dziennie** — liczba elastycznych kredytów, które pracownik otrzymuje, odnosi się do poziomu dni. Łączna liczba elastycznych punktów kredytowych jest dzielona przez liczbę dni w okresie. Jeśli na przykład okres świadczeniowy wynosi 400 dni, system podzieli łączną liczbę elastycznych punktów kredytowych przez 400 w celu obliczenia liczby elastycznych punktów kredytowych, jaką pracownicy otrzymują na dzień.</li><li>**Bieżący miesiąc** — liczba elastycznych kredytów, które pracownik otrzymuje, odnosi się do poziomu miesięcy, z zaokrągleniem do bieżącego miesiąca. Łączna liczba elastycznych punktów kredytowych jest dzielona przez liczbę miesięcy w okresie. Jeśli na przykład okres świadczeniowy wynosi 15 miesięcy, system podzieli łączną liczbę elastycznych punktów kredytowych przez 15 w celu obliczenia liczby elastycznych punktów kredytowych, jaką pracownicy otrzymują na miesiąc.</li><li>**Następny miesiąc** — liczba elastycznych kredytów, które pracownik otrzymuje, odnosi się do poziomu miesięcy, z zaokrągleniem do następnego miesiąca. Łączna liczba elastycznych punktów kredytowych jest dzielona przez liczbę miesięcy w okresie. Jeśli na przykład okres świadczeniowy wynosi 15 miesięcy, system podzieli łączną liczbę elastycznych punktów kredytowych przez 15 w celu obliczenia liczby elastycznych punktów kredytowych, jaką pracownicy otrzymują na miesiąc.</li></ul> |
   
   Upewnij się, że każdy plan świadczeń jest zarejestrowany tylko w jednym programie kredytu elastycznego w danym okresie. W przeciwnym razie system nie będzie wiedział, którego programu kredytu elastycznego ma użyć do przypisania elastycznych punktów kredytowych, i wystąpią w nim problemy. 

## <a name="configure-programs"></a>Konfigurowanie programów

Programy to zbiory planów świadczeń, które mają wspólne reguły uprawnień. Reguły uprawnień można zdefiniować dla całego programu zamiast dla poszczególnych planów. Może to być na przykład program z przeliczeniem na pełne etaty w Contoso Canada albo program dla członków dyrekcji w Contoso Europe. 

1. W obszarze roboczym **Zarządzanie świadczeniami** w sekcji **Konfiguracja** wybierz opcję **Reguły i opcje uprawnień**.

2. Na karcie **Programy** wybierz opcję **Nowy**, aby utworzyć program. Aby wprowadzić wyjątki dla pracowników, którzy nie spełniają wymagań reguł uprawnień, wybierz opcję **Zastąpienie reguły uprawnienia**. Aby wyświetlić plany skojarzone z programem, wybierz opcję **Dołączone plany**.

3. Określ wartości dla następujących pól:

   | Pole | Opis |
   | --- | --- |
   | **Program** | Unikatowy identyfikator programu. |
   | **Opis** | Opis programu. | 
   | **Data i godzina wejścia w życie** | Data i godzina aktywacji programu. |
   | **Data i godzina ważności** | Data i godzina wygaśnięcia programu. Domyślnie to 31.12.2154, czyli nigdy. |
   | **Okres oczekiwania na objęcie świadczeniem** | Okres, przez jaki pracownik musi czekać, zanim zacznie być objęty programem świadczeń. |
   | **Okres oczekiwania na potrącenie** | Okres, po jakim zaczną się potrącenia od pracownika z tytułu objęcia programem świadczeń. |
   | **Reguły uprawnienia** | Wybierz reguły uprawnień, które mają być stosowane do programu świadczeń. Reguły uprawnień definiuje się na karcie **Reguły uprawnienia** na tej stronie. |
   
4. Wybierz opcję **Zapisz**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]