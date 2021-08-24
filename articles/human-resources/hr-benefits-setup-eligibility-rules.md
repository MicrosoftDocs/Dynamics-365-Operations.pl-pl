---
title: Konfigurowanie reguł i opcji uprawnień
description: Określenie reguł i opcji dotyczących uprawnień w obszarze roboczym Zarządzanie świadczeniami w module Microsoft Dynamics 365 Human Resources.
author: andreabichsel
ms.date: 06/25/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 3aae50b8f7fac6991f187ced44f7d122eb7ed40824bd2d53265fa06bfa87dd6a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6756131"
---
# <a name="configure-eligibility-rules-and-options"></a>Konfigurowanie reguł i opcji uprawnień 

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Po skonfigurowaniu wymaganych parametrów zarządzania świadczeniami można utworzyć reguły, pakiety, okresy i programy uprawnień, które będą kojarzone z planami świadczeń.

Reguły kwalifikacji służą do określenia, czy pracownicy kwalifikują się do planu. Pracownicy muszą spełniać warunek co najmniej jednej zasady, aby zostać uznanymi za kwalifikujących się do świadczenia. Na przykład masz dwie reguły na planie. Pierwsza reguła (wiersz 1) stanowi, że typem pracownika musi być **Pracownik**. Druga zasada (wiersz 2) mówi, że pracownik musi być zatrudniony w pełnym wymiarze czasu pracy. Dlatego pracownicy, którzy spełniają zasadę 1, kwalifikują się, nawet jeśli są zatrudnieni tylko w niepełnym wymiarze godzin.

Możesz jednak skonfigurować pojedynczą regułę, która ma wiele warunków. W takim przypadku pracownicy muszą spełnić wszystkie warunki reguły, aby zostać uznanymi za uprawnionych do świadczenia. Na przykład masz regułę, która nazywa się **Pracownik w pełnym wymiarze godzin**. Ta reguła stanowi, że typ pracownika musi być **pracownikiem**, *a* pracownik musi być zatrudniony w pełnym wymiarze godzin. Dlatego pracownicy muszą spełniać oba warunki reguły, aby się kwalifikować.

> [!IMPORTANT]
> Z każdym programem świadczeń musi być powiązana co najmniej jedna reguła kwalifikacji. Z korzyścią możesz powiązać wiele reguł.

## <a name="create-an-eligibility-rule"></a>Tworzenie reguły uprawnienia

Reguły uprawnień określają, którzy pracownicy mogą się rejestrować w poszczególnych planach świadczeń. Po zdefiniowaniu reguł uprawnień można je przypisywać do planów świadczeń. Następnie można przetwarzać uprawnienia do rejestracji, aby sprawdzić, którzy pracownicy są uprawnieni do poszczególnych planów. 

W czasie otwartej rejestracji pracownicy mogą wybierać plany świadczeń. Jeśli już po zarejestrowaniu przestaną się kwalifikować do planów świadczeń wskutek ustawienia określonych reguł uprawnień, nie zostaną automatycznie wyrejestrowani. Zazwyczaj po zmianie sytuacji życiowej, która wpływa na kwalifikowanie się do planów, jest inicjowany okres rejestracji, w którym pracownik może wybrać plany, do których ma uprawnienia. 

1. W obszarze roboczym **Zarządzanie świadczeniami** w sekcji **Konfiguracja** wybierz opcję **Reguły i opcje uprawnień**.

2. Na karcie **Reguły uprawnienia** wybierz opcję **Nowy**, aby utworzyć regułę uprawnienia. Aby wyświetlić plany skojarzone z regułą uprawnienia, wybierz opcję **Dołączone plany**.

3. Określ wartości dla następujących pól.

   | Pole | opis |
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

4. W obszarze **Kryteria dodatkowe** wybierz następujące opcje i w razie potrzeby dodaj informacje.

   | Opcja | opis |
   | --- | --- |
   | **Uprawniony zakres wieku** | Określa zakres lub zakresy wieku wymagane do spełnienia reguły uprawnienia. |
   | **Uprawniony dział** | Określa dział lub działy, do których pracownik musi należeć, aby spełniać regułę uprawnienia. |
   | **Typ kwalifikującego się zatrudnienia** | Określa typ lub typy zatrudnienia, jakie musi mieć ustawione pracownik, aby spełniać regułę uprawnienia. Na przykład Pełny etat lub Część etatu. |
   | **Uprawnione stanowiska pracy** | Określa funkcję lub funkcje spełniające regułę uprawnienia. Funkcje są skojarzone ze stanowiskami, a stanowiska są obsadzane przez pracowników. |
   | **Funkcja stanowiska uprawnienia** | Określa funkcję lub funkcje stanowiska spełniające regułę uprawnienia. Na przykład Sprzedawcy lub Serwisanci. |
   | **Typ zadania uprawnienia** | Określa typ lub typy funkcji spełniające regułę uprawnienia. Na przykład Pracownik biurowy lub Dyrektor. |
   | **Uprawniona firma** | Określa firmę lub firmy, do których ma zastosowanie reguła uprawnienia. Na przykład Contoso Entertainment System USA. |
   | **Uprawniony region wynagrodzenia** | Określa lokalizację pracownika etatowego spełniającą regułę uprawnienia. Na przykład Środkowe stany USA. |
   | **Uprawnione stanowisko** | Określa stanowisko lub stanowiska spełniające regułę uprawnienia. Na przykład Asystent w dziale kadr lub Kierownik działu kadr. |
   | **Typ kwalifikującego się stanowiska** | Określa typ lub typy stanowisk spełniające regułę uprawnienia. Na przykład Pełny etat. |
   | **Stan uprawniony** | Określa stany/województwa/prowincje itd. spełniające regułę uprawnienia. Na przykład Dakota Północna USA lub Kolumbia Brytyjska, Kanada. |
   | **Kwalifikujące się warunki zatrudnienia** | Określa warunki zatrudnienia spełniające regułę uprawnienia. Na przykład Bez gwarancji zatrudnienia lub Umowa zbiorowa. |
   | **Uprawniony związek** | Określa związki zawodowe, do których przynależność spełnia regułę uprawnienia. Na przykład Amerykański związek zawodowy operatorów wózków widłowych.</br></br>W przypadku używania reguły uprawnienia z kryterium związku zawodowego rekord przynależności do związku musi mieć wypełnioną datę końcową. Nie można pozostawić tego pola pustego. |
   | **Uprawniony kod pocztowy** | Określa kody pocztowe spełniające regułę uprawnienia. Na przykład 58104. |

5. W obszarze **Dodatkowe szczegóły** można obejrzeć następujące dodatkowe informacje.

   | Pole | opis |
   | --- | --- |
   | **Pole uprawnionego użytkownika** | Określa dodatkowe reguły uprawnień oparte na polach zdefiniowanych przez klienta. |
   | **Typ uprawnienia** | Określa kategorię kryteriów wybranych w obszarze **Kryteria dodatkowe**. |
   | **Odwołanie do uprawnienia** | Określa wartości wybrane w obszarze **Kryteria dodatkowe**. |
   | **Opis** | Opis wybrany w obszarze **Kryteria dodatkowe**. |

6. Wybierz opcję **Zapisz**.

## <a name="using-custom-fields-in-eligibility-rules"></a>Używanie pól niestandardowych w regułach kwalifikowalności

[Pola niestandardowe](hr-developer-custom-fields.md) można utworzyć w Human Resources, aby śledzić dodatkowe informacje. Pola te mogą być dodawane bezpośrednio do interfejsu użytkownika, a kolumna jest dynamicznie dodawana do tabeli bazowej.  

Pola niestandardowe mogą być używane w procesie kwalifikacji. Reguły kwalifikowalności mogą wykorzystywać jedną lub więcej wartości pól niestandardowych w celu określenia kwalifikowalności pracownika.  Aby dodać niestandardowe pole do istniejącej reguły lub utworzyć nową, przejdź do menu **Zarządzanie świadczeniami > Łącza > Konfiguracja > Reguły uprawnień > Uprawnienia pola niestandardowego**. Na tej stronie można utworzyć regułę, która używa jednego lub wielu pól niestandardowych i można zdefiniować wiele wartości dla każdego pola niestandardowego w celu określenia kwalifikowalności.

W poniższych tabelach znajdują się pola niestandardowe, które mogą być używane w przetwarzaniu kwalifikacji:

- Pracownik (HcmWorker)  
- Zadanie (HcmJob)  
- Stanowisko (HcmPosition)  
- Szczegóły dotyczące stanowiska (HcmPositionDetail)  
- Przypisanie pracownika do stanowiska  
- Zatrudnienie (HcmEmployment)  
- Szczegóły dotyczące zatrudnienia (HcmEmploymentDetails)  
- Szczegóły zadania (HcmJobDetails)  

W procesie kwalifikowania obsługiwane są następujące typy pól niestandardowych:

- Tekst  
- Lista wyboru  
- Identyfikator  
- Dziesiętny  
- Pole wyboru  

Poniższa tabela przedstawia informacje o polu niestandardowym formularza kwalifikującego.

| Pole  | opis |
|--------|-------------|
| Imię i nazwisko | Nazwa tworzonego kryterium. |
| Nazwa tabeli | Nazwa tabeli zawierającej pole własne, które jest używane dla reguły kwalifikacji. |
| Nazwa pola | Pole, które będzie używane dla reguły kwalifikowalności. |
| Typ operatora | Wyświetla operator użyty w konfiguracji kwalifikowalności pola niestandardowego. |
| Wartość | Wyświetla wartość użytą w konfiguracji kwalifikowalności pola niestandardowego. |

## <a name="eligibility-logic"></a>Logika uprawnień

Poniższe sekcje opisują, w jaki sposób przetwarzane są dane dotyczące kwalifikowalności do świadczeń.

### <a name="rules-assigned-to-a-plan"></a>Reguły przypisane do planu 
Jeśli do programu świadczeń przypisanych jest wiele zasad kwalifikowalności, pracownik musi spełnić co najmniej jedną z nich, aby kwalifikować się do udziału w programie świadczeń.  W poniższym przykładzie pracownik musi spełniać wymagania reguły **Typ zadania** lub reguły **Aktywnych pracowników**.

![Pracownik musi spełniać wymagania reguły Typ zadania lub reguły Aktywnych pracowników.](media/RulesAssignedToAPlan.png)
 
### <a name="criteria-within-an-eligibility-rule"></a>Kryteria w ramach zasady kwalifikowalności 
W ramach reguły definiuje się kryteria, które składają się na regułę. W przykładzie powyżej kryteria reguły **Typ stanowiska** to Typ stanowisk = dyrektorzy. W związku z tym pracownik musi być dyrektorem, aby móc się kwalifikować. Jest to reguła, w której występuje tylko jedno kryterium.

Można zdefiniować reguły, które mają wiele kryteriów. W przypadku zdefiniowania wielu kryteriów w ramach reguły kwalifikacji, pracownik musi spełnić każde kryterium w ramach reguły, aby kwalifikować się do planu świadczeń. 

Na przykład powyższa reguła **Aktywni pracownicy** składa się z następujących kryteriów. Aby pracownik był uprawniony na podstawie reguły **Aktywni pracownicy**, musi być zatrudniony w firmie USMF *i* mieć typ stanowiska pełnoetatowego.  

![Kryteria w ramach zasady kwalifikowalności.](media/CriteriaWithinAnEligibilityRule.png) 
 
### <a name="multiple-conditions-within-criteria"></a>Wiele warunków w ramach kryteriów

Reguły mogą być dalej rozbudowywane w celu wykorzystania wielu warunków w ramach jednego kryterium. Pracownik musi spełnić co najmniej jeden warunek, aby się kwalifikować. Aby użyć przykładu powyżej, można dodatkowo rozwinąć regułę **Aktywni pracownicy**, tak aby uwzględnić pracowników, którzy są także pracownikami półetatowymi. W związku z tym pracownik musi być pracownikiem z firmy USMF *oraz* pracownikiem zatrudnionym na pełny etat lub na część etatu.  

![Wiele warunków w ramach kryteriów.](media/MultipleConditionsWithinCriteria.png) 
 
### <a name="eligibility-conditions-within-a-custom-field-criterion"></a>Warunki kwalifikowalności w ramach kryterium pola niestandardowego 
Podobnie jak powyżej, pola niestandardowe mogą być używane podczas tworzenia reguł kwalifikowalności i działają w ten sam sposób. Na przykład, możesz chcieć zaoferować zwrot kosztów Internetu pracownikom z Fargo i Kopenhagi, którzy pracują w domu, ponieważ w tych lokalizacjach koszty Internetu są wyższe. W tym celu należy utworzyć dwa niestandardowe pola: **Lokalizacja biura** (lista wyboru) i **Praca z domu** (pole wyboru). Następnie utwórz regułę o nazwie **Pracownicy zdalni**. Kryterium reguły jest **lokalizacja biura = Fargo** lub **Kopenhaga** *oraz* wartość **praca z domu = Tak**.

Należy skonfigurować niestandardowe reguły uprawnienia zgodnie z poniższym obrazem. 

![Warunki kwalifikowalności w ramach kryterium pola niestandardowego.](media/EligibilityConditionsWithinACustomFieldCriterion.png) 
 
## <a name="configure-bundles"></a>Konfigurowanie pakietów

Pakiety to zestawy powiązanych planów świadczeń. Pakietów świadczeń można używać do grupowania planów świadczeń, które pracownik musi wybrać, aby się zarejestrować w niektórych planach świadczeń uzależnionych od rejestracji w innych planach świadczeń. Przykłady sytuacji, kiedy może być konieczne użycie pakietów:

- Pakiet planów opieki zdrowotnej, który obejmuje ubezpieczenie zdrowotne z wysokim udziałem własnym i powiązanym rachunkiem oszczędnościowym (HSA).

- Plan ubezpieczenia na życie, w którym obowiązkowy plan ubezpieczenia na życie pracownika jest powiązany z ubezpieczeniem na życie osoby będącej na utrzymaniu. Pakiet gwarantuje, że pracownik nie będzie mógł wybrać ubezpieczenia na życie dla osoby na utrzymaniu bez równoczesnego zawarcia ubezpieczenia dla siebie.

1. W obszarze roboczym **Zarządzanie świadczeniami** w sekcji **Konfiguracja** wybierz opcję **Reguły i opcje uprawnień**.

2. Na karcie **Pakiety** wybierz opcję **Nowy**, aby utworzyć pakiet. Aby wyświetlić plany skojarzone z pakietem, wybierz opcję **Dołączone plany**.

3. Określ wartości dla następujących pól.

   | Pole | opis |
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

3. Określ wartości dla następujących pól.

   | Pole | opis |
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

3. Wybierz program kredytu elastycznego, który ma zostać zastosowany. Okno zawiera następujące pola.

   | Pole | opis |
   | --- | --- |
   | Identyfikator kredytu świadczenia | Unikatowy identyfikator programu kredytu elastycznego. |
   | Opis | Opis programu kredytu elastycznego. | 
   | Data Od | Data i godzina aktywacji programu kredytu elastycznego. |
   | Data Do | Data i godzina zakończenia działania programu kredytu elastycznego. Można pozostawić wartość domyślną (12/31/2154), aby wskazać, że program kredytu elastycznego nie ma zaplanowanego okresu ważności. |
   | Suma wartości kredytu | Liczba punktów kredytowych, jakie będzie miał każdy pracownik na swoje świadczenia. |
   | Reguła naliczania proporcjonalnego | Reguła używana do proporcjonalnego obliczania liczby elastycznych punktów kredytowych, gdy pracownik zostanie zatrudniony w trakcie okresu wykorzystywania elastycznych punktów kredytowych. </br></br><ul><li>**Brak** — pracownik nie otrzymuje żadnych elastycznych punktów kredytowych, jeśli zostanie zatrudniony po rozpoczęciu okresu programu kredytu elastycznego.</li><li>**Pełny kredyt** — pracownik otrzymuje pełną liczbę elastycznych punktów kredytowych, niezależnie od momentu, w którym został zatrudniony.</li><li>**Naliczanie proporcjonalne** — pracownik otrzymuje liczbę elastycznych punktów kredytowych proporcjonalną do daty rozpoczęcia zatrudnienia.</li></ul> |
   | Formuła naliczania proporcjonalnego kredytu elastycznego | Reguła używana do proporcjonalnego obliczania liczby elastycznych punktów kredytowych dla pracowników, którzy zostali zatrudnieni w trakcie okresu świadczeniowego zdefiniowanego w programie kredytu elastycznego. Naliczanie proporcjonalne jest oparte na dacie rozpoczęcia zatrudnienia. To pole jest używane tylko w przypadku zaznaczenia wartości **Naliczanie proporcjonalne** w polu **Reguła naliczania proporcjonalnego**. </br></br><ul><li>**Dziennie** — liczba elastycznych kredytów, które pracownik otrzymuje, odnosi się do poziomu dni. Łączna liczba elastycznych punktów kredytowych jest dzielona przez liczbę dni w okresie. Jeśli na przykład okres świadczeniowy wynosi 400 dni, system podzieli łączną liczbę elastycznych punktów kredytowych przez 400 w celu obliczenia liczby elastycznych punktów kredytowych, jaką pracownicy otrzymują na dzień.</li><li>**Bieżący miesiąc** — liczba elastycznych kredytów, które pracownik otrzymuje, odnosi się do poziomu miesięcy, z zaokrągleniem do bieżącego miesiąca. Łączna liczba elastycznych punktów kredytowych jest dzielona przez liczbę miesięcy w okresie. Jeśli na przykład okres świadczeniowy wynosi 15 miesięcy, system podzieli łączną liczbę elastycznych punktów kredytowych przez 15 w celu obliczenia liczby elastycznych punktów kredytowych, jaką pracownicy otrzymują na miesiąc.</li><li>**Następny miesiąc** — liczba elastycznych kredytów, które pracownik otrzymuje, odnosi się do poziomu miesięcy, z zaokrągleniem do następnego miesiąca. Łączna liczba elastycznych punktów kredytowych jest dzielona przez liczbę miesięcy w okresie. Jeśli na przykład okres świadczeniowy wynosi 15 miesięcy, system podzieli łączną liczbę elastycznych punktów kredytowych przez 15 w celu obliczenia liczby elastycznych punktów kredytowych, jaką pracownicy otrzymują na miesiąc.</li></ul> |
   
   Upewnij się, że każdy plan świadczeń jest zarejestrowany tylko w jednym programie kredytu elastycznego w danym okresie. W przeciwnym razie system nie będzie wiedział, którego programu kredytu elastycznego ma użyć do przypisania elastycznych punktów kredytowych, i wystąpią w nim problemy. 

## <a name="configure-programs"></a>Konfigurowanie programów

Programy to zbiory planów świadczeń, które mają wspólne reguły uprawnień. Reguły uprawnień można zdefiniować dla całego programu zamiast dla poszczególnych planów. Na przykład program Contoso Canada FTE lub Contoso Europe na poziomie kierowników. 

1. W obszarze roboczym **Zarządzanie świadczeniami** w sekcji **Konfiguracja** wybierz opcję **Reguły i opcje uprawnień**.

2. Na karcie **Programy** wybierz opcję **Nowy**, aby utworzyć program. Aby wprowadzić wyjątki dla pracowników, którzy nie spełniają wymagań reguł uprawnień, wybierz opcję **Zastąpienie reguły uprawnienia**. Aby wyświetlić plany skojarzone z programem, wybierz opcję **Dołączone plany**.

3. Określ wartości dla następujących pól.

   | Pole | opis |
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
