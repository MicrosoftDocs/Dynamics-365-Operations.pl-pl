---
title: Konfigurowanie stawek
description: W programie Microsoft Dynamics 365 Human Resources stawki decydują o tym, jaki udział w finansowaniu świadczeń mają pracodawcy i pracownicy.
author: twheeloc
ms.date: 08/25/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 039b4aa3f044cda29944bcd4f5c42fc35818c58b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8868167"
---
# <a name="configure-rates"></a>Konfigurowanie stawek


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Stawki decydują o tym, jaki udział w finansowaniu świadczeń mają pracodawcy i pracownicy. Wartość może być kwotą lub liczbą kredytów elastycznych, w zależności od konfiguracji.

Stawki służą do określania, ile pracownicy i pracodawcy płacą za każde świadczenie, na podstawie kilku czynników. Stawki za objęcie świadczeniami mają daty obowiązywania, więc można prowadzić historyczny rejestr stawek. 

## <a name="set-up-rates"></a>Ustawianie stawek

1. W obszarze roboczym **Zarządzanie świadczeniami** w sekcji **Konfiguracja** wybierz opcję **Stawki**.

2. Wybierz pozycję **Nowy**.

3. Określ wartości dla następujących pól:

   | Pole | Opis |
   | --- | --- |
   | **Kurs** | Unikatowa nazwa identyfikująca stawkę świadczenia. |
   | **Opis** | Opis stawki świadczenia. |
   | **Weszła w życie** | Data wejścia w życie stawki. Domyślną wartością jest bieżąca data systemowa. Data ta nie powinna być wcześniejsza niż okres świadczenia. Dobrze jest ustawić tę datę jako datę planu świadczeń. |
   | **Data ważności** | Data zakończenia obowiązywania stawki. Wartość domyślna to 31.12.2154, czyli nigdy. |
   | **Użyj warstw** |  Użyj tego pola, jeśli masz logikę, której należy użyć do określenia stawki. Jeśli na przykład stawka musi wzrosnąć na podstawie wieku, wybierz tutaj wartość. Wybierz **Pojedyncza warstwa** dla jednowarstwowej stawki świadczenia lub **Podwójna warstwa** dla dwuwarstwowej stawki świadczenia. Przykładem podwójnej warstwy jest warstwa oparta na płci i wieku. Po wybraniu wartości wybierz opcję **Akcje**, a następnie wybierz **stawki warstw**. Jeśli stawkę ryczałt nie zmieni się, pozostaw to pole puste. |
   | **Częstość płatności** | Określ, jak często stawka składki świadczenia powinna być wypłacana świadczeniodawcy. Stawki wprowadzane na stronie opisanej w dalszej części tego artykułu będą oparte na określonej tutaj częstotliwości płatności. Na przykład po wprowadzeniu w tym polu wartości **Miesięcznie** i wprowadzeniu stawki pracownika **$100** zakłada się, że świadczenie będzie kosztowało pracownika $100 w miesiącu. Jednak pracownik może otrzymywać wypłatę dwa razy w miesiącu, na podstawie częstotliwości wypłaty świadczenia określonej w kartotece pracownika. W takim przypadku, gdy pracownik zaloguje się do modułu **Samoobsługa pracownika etatowego**, kwota, jaką zapłaci, wyniesie 50 USD, ponieważ stawka, którą pokazuje moduł **Samoobsługa pracownika etatowego**, jest oparta na częstotliwości płatności pracownika. |
   | **Zaokrąglanie stawki częstotliwości płac** | Dostępne metody zaokrąglania kursu to: Standardowe, Obcięte, Normalne, W dół oraz Zaokrąglenie w górę. </br></br><ul><li>**Standard** — zawsze zaokrąglaj. Na przykład 10,611 zaokrągli się do 10,62. Zaokrągla się do -10,231 do -10,23. </li><li>**Obcięte** — zawsze zaokrąglaj w dół. Na przykład 10,619 zaokrągli się do 10,61. Zaokrągla się do -10,231 do -10,24. </li><li>**Normalne** — wartości dziesiętne kończące się lub większe niż 5 będą zaokrąglać w 0. Wartości dziesiętne kończące się w lub mniejsze niż 4 będą zaokrąglane w stronę zera. Na przykład 10,615 zaokrągli się do 10,62. Zaokrągla się do -10,235 do -10,24. Zaokrągla się do -10,614 do -10,61. Zaokrągla się do -10,234 do -10,23. </li><li>**W dół** — zaokrąglaj w stronę zera. Na przykład 10,619 zaokrągli się do 10,61. Zaokrągla się do -10,231 do -10,23. </li><li>**Zaokrąglanie w górę** — zaokrąglanie w górę od zera. Na przykład 10,619 zaokrągli się do 10,62. Zaokrągla się do -10,231 do -10,24. |
   | **Kwota pracownika etatowego osoby niepalącej** | Kwota, jakiej dostawca świadczeń żąda za niepalącego pracownika. Jest to kwota płacona dostawcy świadczeń przez pracodawcę i powinna być oparta na częstotliwości płatności określonej w konfiguracji stawki. |
   | **Kwota pracodawcy osoby niepalącej** | Kwota, jakiej dostawca świadczeń żąda za niepalącego pracownika. Jest to kwota płacona dostawcy świadczeń przez pracodawcę i powinna być oparta na częstotliwości płatności określonej w konfiguracji stawki. |
   | **Kwota pracownika etatowego osoby palącej** | Kwota, jakiej dostawca świadczeń żąda za pracownika, który pali papierosy. Jest to kwota płacona dostawcy świadczeń przez pracodawcę i powinna być oparta na częstotliwości płatności określonej w konfiguracji stawki. |
   | **Kwota pracodawcy osoby palącej** | Kwota, jakiej dostawca świadczeń żąda za pracownika, który pali papierosy. Jest to kwota płacona dostawcy świadczeń przez pracodawcę i powinna być oparta na częstotliwości płatności określonej w konfiguracji stawki. |
   | **Kwota administracyjna** | Kwota administracyjna pobierana przez zewnętrznego administratora. Jest to kwota płacona zewnętrznemu administratorowi przez pracodawcę i powinna być oparta na częstotliwości płatności określonej w konfiguracji stawki. |
   | **Stawka kredytu elastycznego** | Liczba elastycznych punktów kredytowych, jakie trzeba wydać na świadczenie. Dotyczy tylko stawek za plany świadczeń powiązane z programami kredytu elastycznego. W przypadku używania stawek warstwowych stawkę elastycznych punktów kredytowych definiuje się w ustawieniu Akcje > Stawki warstwowe. |
   | **Zmień datę wejścia w życie** | Data wejścia w życie zmiany stawki świadczenia. Po wykonaniu przetwarzania aktualizacji zmiany stawki system automatycznie zmieni stawkę świadczenia i zaktualizuje wszystkie plany świadczeń skojarzone z tą stawką. Datę należy ustawiać tylko wtedy, gdy chcesz, aby system automatycznie aktualizował plany świadczeń pracowniczych na podstawie tej stawki. Standardowo automatyczne przetwarzanie stosuje się do przyszłych zmian stawek. **Data obowiązywania zmiany** musi przypadać w granicach dat wejścia w życie i wygaśnięcia stawki świadczenia. |
   | **Zakończono zmienianie stawki** | Pole wyboru **Zakończono zmienianie** stawki zostanie automatycznie zaznaczone, gdy proces przetwarzania aktualizacji zmiany stawki wprowadzi wszystkie zmiany w stawkach za świadczenia. |

4. Aby śledzić zmiany konfiguracji stawki świadczenia i nimi zarządzać, wybierz opcję **Akcje**, a następnie wybierz opcję **Obsługuj wersje**.

5. Wybierz opcję **Zapisz**. 

## <a name="set-up-tier-rates"></a>Ustawianie stawek warstwowych

Jeśli stawka różni się w zależności od różnych czynników, w ustawieniach stawki można stosować stawki warstwowe. Na przykład można skonfigurować stawki warstwowe w taki sposób, że przy wieku do 34,99 roku kwota dla osób niepalących wynosi 2. Przy wieku do 39,99 roku kwota dla osób niepalących wynosi 3.

Można również używać podwójnych warstw. Jeśli w formularzu **Konfiguracja stawki** w ustawieniu **Użyj warstw** zaznaczysz opcję **Podwójna warstwa**, można zdefiniować stawki na podstawie dwóch wymiarów. Na przykład można skonfigurować system dwuwarstwowy w taki sposób, że u mężczyzn przy wieku do 34,99 roku kwota dla osób niepalących wynosi 2. U mężczyzn w wieku do 39,99 roku kwota dla osób niepalących wynosi 3. U kobiet w wieku do 34,99 roku kwota dla osób niepalących wynosi 1,8. U kobiet w wieku do 39,99 roku kwota dla osób niepalących wynosi 2,8.

> [!IMPORTANT]
> W rekordzie pracownika w sekcji **Dane osobowe** istnieje opcja służąca do wskazania, czy pracownik jest palaczem. Jeśli pracownik jest zarejestrowany jako palacz, zostanie zastosowana stawka palacza. (Oznaczenie nigdy nie jest wyświetlane pracownikowi).
   
1. W obszarze roboczym **Zarządzanie świadczeniami** w sekcji **Konfiguracja** wybierz opcję **Stawki**.

2. Wybierz jedną lub więcej stawek z listy, wybierz opcję **Akcje**, a następnie wybierz opcję **Stawki warstwowe**.

3. Wybierz pozycję **Nowy**.

3. Określ wartości dla następujących pól:

   | Pole | opis |
   | --- | --- | 
   | **Opis** | Wartość w polu **Opis** zostanie zastosowana z opisu w rekordzie konfiguracji stawek. Pomaga to stwierdzić, z którą konfiguracją stawek są powiązane stawki warstwowe. |
   | **Kod warstw** | Wybierz kod warstwy. Kody warstw definiuje się na stronie **Kody warstw**. System automatycznie wyświetli opis kodu warstwy w siatce z lewej strony. |
   | **Typ warstwy** | Określa, które pole powinno być używane jako kryterium wyboru dla procesu obliczania stawki warstwowej. Na przykład:</br></br><ul><li>Jeśli zostanie użyte kryterium **Wiek**, system użyje daty urodzenia pracownika w procesie obliczania stawki świadczenia.</li><li>Jeśli zostanie użyte kryterium **Wynagrodzenie**, system użyje rocznego wynagrodzenia z tytułu świadczenia w procesie obliczania stawki świadczenia.</li><li>Jeśli zostanie użyte kryterium **Typ funkcji**, obecnie aktywny rekord stanowiska pracownika zostanie użyty do określenia typu funkcji na podstawie rekordu powiązanego ze stanowiskiem.</li></ul></br></br>Dostępne typy warstw to **Wiek**, **Wynagrodzenie**, **Fizyczny**, **Płeć**, **W przeliczeniu na pełne etaty**, **Typ funkcji**, **Region wynagrodzenia** oraz **Poziom**. | 
   | **Poziom** | Wartość, która ma być używana w połączeniu z typem warstwy w trakcie procesu obliczania stawki świadczenia. Na przykład:</br></br><ul><li>Jeśli typem warstwy jest **Wiek**, byłaby to wartość wieku.</li><li>Jeśli typem warstwy jest **Wynagrodzenie**, byłaby to kwota wynagrodzenia.</li><li> Jeśli typem warstwy jest **Typ funkcji**, byłby to typ funkcji.</li></ul></br></br>W przypadku warstwy o typie **Wiek** lub **Wynagrodzenie** wartość w polu **Poziom** reprezentuje górną granicę warstwy. Dla warstwy typu **Typ funkcji** dokładne dopasowanie jest używane podczas wybierania stawki warstwowej. |
   | **Typ obliczania** | Określa sposób używania kwoty zawartej w polu Obliczona kwota oraz jakie obliczenia matematyczne będą wykonywane w razie potrzeby. Jeśli typem obliczania jest kwota ryczałtowa, pola kwot są używane w obecnym stanie. Jeśli typem obliczania jest kwota w przeliczeniu na 1 jednostkę pieniężną wynagrodzenia lub ubezpieczenia, w obliczeniach matematycznych jest używana obliczona kwota i kierunek obliczania.</br></br>Jeśli typem obliczania jest kwota w przeliczeniu na 1 jednostkę pieniężną wynagrodzenia, jest używane następujące równanie matematyczne:</br></br>Roczne wynagrodzenie z tytułu świadczenia podzielone przez obliczoną kwotę (zaokrągloną w górę lub w dół) razy kwoty płacone przez pracownika lub pracodawcę za osobę palącą lub niepalącą.</br></br>Jeśli typem obliczania jest kwota w przeliczeniu na 1 jednostkę pieniężną pokrycia, jest używane następujące równanie matematyczne:</br></br>Kwota ubezpieczenia podzielona przez obliczoną kwotę (zaokrągloną w górę lub w dół) razy kwoty płacone przez pracownika lub pracodawcę za osobę palącą lub niepalącą.</br></br>W obu obliczeniach jest używany kierunek obliczania w celu określenia, czy roczne wynagrodzenie z tytułu świadczenia lub kwota świadczenia podzielona przez obliczoną kwotę ma być zaokrąglana w górę czy w dół. |
   | **Obliczona kwota** | Kwota, która ma być używana w procesie obliczania stawki świadczenia. Będzie ona dzielnikiem podczas matematycznego obliczania stawki warstwowej. |
   | **Kierunek obliczania** | Kierunek, w którym powinna zostać zaokrąglona obliczona kwota wynikowa. System obsługuje trzy kierunki obliczania: puste pole (dokładnie tyle), **Zwiększenie** i **Zmniejszenie**.</br></br><ul><li>Jeśli to pole jest puste, system będzie używał dokładnego obliczenia kwoty wynagrodzenia/ubezpieczenia podzielonej przez obliczoną kwotę. Jeśli wartość zawiera ułamek, zostanie on użyty w obliczeniu.</li><li>W przypadku kierunku **Zwiększenie** zostanie zwiększona wartość matematycznego obliczenia kwoty wynagrodzenia/ubezpieczenia podzielonej przez obliczoną kwotę do następnej liczby całkowitej, co oznacza, że 12,25 wzrośnie do 13.</li><li>W przypadku kierunku **Zmniejszenie** zostanie zmniejszona wartość matematycznego obliczenia kwoty wynagrodzenia/ubezpieczenia podzielonej przez obliczoną kwotę do obecnej liczby całkowitej, co oznacza, że 12,25 zmaleje do 12.</li></ul> |
   | **Kwota pracownika etatowego osoby niepalącej** | Kwota, jakiej dostawca świadczeń żąda za niepalącego pracownika. Jest to kwota płacona dostawcy świadczeń przez pracodawcę i powinna być oparta na częstotliwości płatności określonej w konfiguracji stawki. |
   | **Kwota pracodawcy osoby niepalącej** | Kwota, jakiej dostawca świadczeń żąda za niepalącego pracownika. Jest to kwota płacona dostawcy świadczeń przez pracodawcę i powinna być oparta na częstotliwości płatności określonej w konfiguracji stawki. |
   | **Kwota pracownika etatowego osoby palącej** | Kwota, jakiej dostawca świadczeń żąda za niepalącego pracownika. Jest to kwota płacona dostawcy świadczeń przez pracodawcę i powinna być oparta na częstotliwości płatności określonej w konfiguracji stawki. |
   | **Kwota pracodawcy osoby palącej** | Kwota, jakiej dostawca świadczeń żąda za niepalącego pracownika. Jest to kwota płacona dostawcy świadczeń przez pracodawcę i powinna być oparta na częstotliwości płatności określonej w konfiguracji stawki. |
   | **Kwota administracyjna** | Kwota administracyjna pobierana przez zewnętrznego administratora. Jest to kwota płacona zewnętrznemu administratorowi przez pracodawcę i powinna być oparta na częstotliwości płatności określonej w konfiguracji stawki. |
   | **Wskaźnik osoby niepalącej kredytu elastycznego** | Liczba elastycznych punktów kredytowych, jakie trzeba wydać na świadczenie, oparta na obliczeniu zdefiniowanym dla poziomu warstwy dla osób niepalących. Na przykład jeśli typem obliczania jest **Kwota w przeliczeniu na 1 jednostkę pieniężną ubezpieczenia**, obliczona kwota wynosi 10 000, a stawka elastycznych punktów kredytowych dla osób niepalących wynosi 6, to jeśli pracownik wybierze ubezpieczenia na 10 000, będzie go to kosztowało 6 elastycznych punktów kredytowych. Jeśli wybierze ubezpieczenie na 20 000, zapłaci 12 elastycznych punktów kredytowych itd. |
   | **Wskaźnik osoby palącej kredytu elastycznego** | Liczba elastycznych punktów kredytowych, jakie trzeba wydać na świadczenie, oparta na obliczeniu zdefiniowanym dla poziomu warstwy dla osób palących. |

5. Wybierz opcję **Zapisz**. 



[!INCLUDE[footer-include](../includes/footer-banner.md)]
