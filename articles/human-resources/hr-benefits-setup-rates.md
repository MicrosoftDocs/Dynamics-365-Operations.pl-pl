---
title: Konfigurowanie stawek
description: W programie Microsoft Dynamics 365 Human Resources stawki decydują o tym, jaki udział w finansowaniu świadczeń mają pracodawcy i pracownicy.
author: andreabichsel
manager: AnnBe
ms.date: 06/22/2020
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
ms.openlocfilehash: e397e20b6b6307349020c8dfd238b4b59eeca527
ms.sourcegitcommit: 1e6a7b50596eaf9d965e0155f3f2c50f7f50747e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/22/2020
ms.locfileid: "3497363"
---
# <a name="configure-rates"></a>Konfigurowanie stawek

W programie Microsoft Dynamics 365 Human Resources stawki decydują o tym, jaki udział w finansowaniu świadczeń mają pracodawcy i pracownicy. W zależności od konfiguracji wartość może być kwotą lub elastycznymi punktami kredytowymi.

Stawki służą do określania, ile pracownicy i pracodawcy płacą za każde świadczenie, na podstawie kilku czynników. Stawki za objęcie świadczeniami mają daty obowiązywania, więc można prowadzić historyczny rejestr stawek. 

## <a name="set-up-rates"></a>Ustawianie stawek

1. W obszarze roboczym **Zarządzanie świadczeniami** w sekcji **Konfiguracja** wybierz opcję **Stawki**.

2. Wybierz pozycję **Nowy**.

3. Określ wartości dla następujących pól:

   | Pole | Opis |
   | --- | --- |
   | **Kurs** | Unikatowa nazwa identyfikująca stawkę świadczenia. |
   | **Opis** | Opis stawki świadczenia. |
   | **Weszła w życie** | Data, od której obowiązuje stawka. Domyślną wartością jest bieżąca data systemowa. 
   | **Data ważności** | Data zakończenia obowiązywania stawki. Wartość domyślna to 31.12.2154, czyli nigdy. |
   | **Użyj warstw** | Warstwa, która ma być używana do obliczania stawki świadczenia. Pojedyncza warstwa dla jednowarstwowej stawki świadczenia lub Podwójna warstwa dla dwuwarstwowej stawki świadczenia. Przykładem podwójnej warstwy jest warstwa oparta na płci i wieku. |
   | **Częstotliwość płatności** | Częstotliwość płatności określająca, jak często składka za świadczenie o podanej stawce jest wpłacana dostawcy świadczeń. Jeśli na przykład częstotliwość płatności wynosi Miesięcznie, to stawka świadczenia reprezentuje miesięczną kwotę płatności. |
   | **Zaokrąglanie stawki częstotliwości płac** | Metoda zaokrąglania stawki: Standardowa lub Obcięta. |
   | **Kwota pracownika etatowego osoby niepalącej** | Kwota, jakiej dostawca świadczeń żąda za niepalącego pracownika. Jest to kwota płacona dostawcy świadczeń przez pracodawcę i powinna być oparta na częstotliwości płatności określonej w konfiguracji stawki. |
   | **Kwota pracodawcy osoby niepalącej** | Kwota, jakiej dostawca świadczeń żąda za niepalącego pracownika. Jest to kwota płacona dostawcy świadczeń przez pracodawcę i powinna być oparta na częstotliwości płatności określonej w konfiguracji stawki. |
   | **Kwota pracownika etatowego osoby palącej** | Kwota, jakiej dostawca świadczeń żąda za pracownika, który pali papierosy. Jest to kwota płacona dostawcy świadczeń przez pracodawcę i powinna być oparta na częstotliwości płatności określonej w konfiguracji stawki. |
   | **Kwota pracodawcy osoby palącej** | Kwota, jakiej dostawca świadczeń żąda za pracownika, który pali papierosy. Jest to kwota płacona dostawcy świadczeń przez pracodawcę i powinna być oparta na częstotliwości płatności określonej w konfiguracji stawki. |
   | **Kwota administracyjna** | Kwota administracyjna pobierana przez zewnętrznego administratora. Jest to kwota płacona zewnętrznemu administratorowi przez pracodawcę i powinna być oparta na częstotliwości płatności określonej w konfiguracji stawki. |
   | **Stawka kredytu elastycznego** | Liczba elastycznych punktów kredytowych, jakie trzeba wydać na świadczenie. Dotyczy tylko stawek za plany świadczeń powiązane z programami kredytu elastycznego. W przypadku używania stawek warstwowych stawkę elastycznych punktów kredytowych definiuje się w ustawieniu Akcje > Stawki warstwowe. |
   | **Zmień datę wejścia w życie** | Data wejścia w życie zmiany stawki świadczenia. Po wykonaniu przetwarzania aktualizacji zmiany stawki system automatycznie zmieni stawkę świadczenia i zaktualizuje wszystkie plany świadczeń skojarzone z tą stawką. Datę należy ustawiać tylko wtedy, gdy chcesz, aby system automatycznie aktualizował plany świadczeń pracowniczych na podstawie tej stawki. Standardowo automatyczne przetwarzanie stosuje się do przyszłych zmian stawek. Data obowiązywania zmiany musi przypadać w granicach dat wejścia w życie i wygaśnięcia stawki świadczenia. |
   | **Zakończono zmienianie stawki** | Pole wyboru **Zakończono zmienianie** stawki zostanie automatycznie zaznaczone, gdy proces przetwarzania aktualizacji zmiany stawki wprowadzi wszystkie zmiany w stawkach za świadczenia. |

4. Aby śledzić zmiany konfiguracji stawki świadczenia i nimi zarządzać, wybierz opcję **Akcje**, a następnie wybierz opcję **Obsługuj wersje**.

5. Wybierz opcję **Zapisz**. 

## <a name="set-up-tier-rates"></a>Ustawianie stawek warstwowych

Jeśli stawka różni się w zależności od różnych czynników, w ustawieniach stawki można stosować stawki warstwowe. Na przykład można skonfigurować stawki warstwowe w taki sposób, że przy wieku do 34,99 roku kwota dla osób niepalących wynosi 2. Przy wieku do 39,99 roku kwota dla osób niepalących wynosi 3.

Można również używać podwójnych warstw. Jeśli w formularzu **Konfiguracja stawki** w ustawieniu **Użyj warstw** zaznaczysz opcję **Podwójna warstwa**, można zdefiniować stawki na podstawie dwóch wymiarów. Na przykład można skonfigurować system dwuwarstwowy w taki sposób, że u mężczyzn przy wieku do 34,99 roku kwota dla osób niepalących wynosi 2. U mężczyzn w wieku do 39,99 roku kwota dla osób niepalących wynosi 3. U kobiet w wieku do 34,99 roku kwota dla osób niepalących wynosi 1,8. U kobiet w wieku do 39,99 roku kwota dla osób niepalących wynosi 2,8.

1. W obszarze roboczym **Zarządzanie świadczeniami** w sekcji **Konfiguracja** wybierz opcję **Stawki**.

2. Wybierz jedną lub więcej stawek z listy, wybierz opcję **Akcje**, a następnie wybierz opcję **Stawki warstwowe**.

3. Wybierz pozycję **Nowy**.

3. Określ wartości dla następujących pól:

   | Pole | opis |
   | --- | --- | 
   | **Opis** | Wartość w polu **Opis** zostanie zastosowana z opisu w rekordzie konfiguracji stawek. Pomaga to stwierdzić, z którą konfiguracją stawek są powiązane stawki warstwowe. |
   | **Kod warstw** | Wybierz kod warstwy. Kody warstw definiuje się w formularzu Kody warstw. System automatycznie wyświetli opis kodu warstwy w siatce z lewej strony. |
   | **Typ warstwy** | Określa, które pole powinno być używane jako kryterium wyboru dla procesu obliczania stawki warstwowej. Na przykład:</br></br><ul><li>Jeśli zostanie użyte kryterium **Wiek**, system użyje daty urodzenia pracownika w procesie obliczania stawki świadczenia.</li><li>Jeśli zostanie użyte kryterium **Wynagrodzenie**, system użyje rocznego wynagrodzenia z tytułu świadczenia w procesie obliczania stawki świadczenia.</li><li>Jeśli zostanie użyte kryterium **Typ funkcji**, system użyje obecnie aktywnego rekordu stanowiska pracownika w celu określenia typu funkcji na podstawie rekordu powiązanego ze stanowiskiem.</li></ul></br></br>Dostępne typy warstw to **Wiek**, **Wynagrodzenie**, **Fizyczny**, **Płeć**, **W przeliczeniu na pełne etaty**, **Typ funkcji**, **Region wynagrodzenia**oraz **Poziom**. | 
   | **Poziom** | Wartość, która ma być używana w połączeniu z typem warstwy w trakcie procesu obliczania stawki świadczenia. Na przykład:</br></br><ul><li>Jeśli typem warstwy jest **Wiek**, byłaby to wartość wieku.</li><li>Jeśli typem warstwy jest **Wynagrodzenie**, byłaby to kwota wynagrodzenia.</li><li> Jeśli typem warstwy jest **Typ funkcji**, byłby to typ funkcji.</li></ul></br></br>W przypadku warstwy o typie **Wiek** lub **Wynagrodzenie** wartość w polu **Poziom** reprezentuje górną granicę warstwy. Dla warstwy typu **Typ funkcji** system używa dokładnego dopasowania podczas wybierania stawki warstwowej. |
   | **Typ obliczania** | Określa sposób używania kwoty zawartej w polu Obliczona kwota oraz jakie obliczenia matematyczne będą wykonywane w razie potrzeby. Jeśli typem obliczania jest kwota ryczałtowa, system bezpośrednio używa wartości z pól kwot. Jeśli typem obliczania jest kwota w przeliczeniu na 1 jednostkę pieniężną wynagrodzenia lub ubezpieczenia, system w swoich obliczeniach matematycznych używa obliczonej kwoty i kierunku obliczania.</br></br>Jeśli typem obliczania jest kwota w przeliczeniu na 1 jednostkę pieniężną wynagrodzenia, system zastosuje następujące równanie matematyczne:</br></br>Roczne wynagrodzenie z tytułu świadczenia podzielone przez obliczoną kwotę (zaokrągloną w górę lub w dół) razy kwoty płacone przez pracownika lub pracodawcę za osobę palącą lub niepalącą.</br></br>Jeśli typem obliczania jest kwota w przeliczeniu na 1 jednostkę pieniężną ubezpieczenia, system zastosuje następujące równanie matematyczne:</br></br>Kwota ubezpieczenia podzielona przez obliczoną kwotę (zaokrągloną w górę lub w dół) razy kwoty płacone przez pracownika lub pracodawcę za osobę palącą lub niepalącą.</br></br>W obu obliczeniach jest używany kierunek obliczania w celu określenia, czy roczne wynagrodzenie z tytułu świadczenia lub kwota świadczenia podzielona przez obliczoną kwotę ma być zaokrąglana w górę czy w dół. |
   | **Obliczona kwota** | Kwota, która ma być używana w procesie obliczania stawki świadczenia. Będzie ona dzielnikiem podczas matematycznego obliczania stawki warstwowej. |
   | **Kierunek obliczania** | Kierunek, w którym powinna zostać zaokrąglona obliczona kwota wynikowa. System obsługuje trzy kierunki obliczania: puste pole (dokładnie tyle), **Zwiększenie** i **Zmniejszenie**.</br></br><ul><li>Jeśli to pole jest puste, system będzie używał dokładnego obliczenia kwoty wynagrodzenia/ubezpieczenia podzielonej przez obliczoną kwotę. Jeśli wartość zawiera ułamek, system użyje go w swoim obliczeniu.</li><li>W przypadku kierunku **Zwiększenie** system zwiększy wartość matematycznego obliczenia kwoty wynagrodzenia/ubezpieczenia podzielonej przez obliczoną kwotę do następnej liczby całkowitej, co oznacza, że 12,25 wzrośnie do 13.</li><li>W przypadku kierunku **Zmniejszenie** system zmniejszy wartość matematycznego obliczenia kwoty wynagrodzenia/ubezpieczenia podzielonej przez obliczoną kwotę do obecnej liczby całkowitej, co oznacza, że 12,25 zmaleje do 12.</li></ul> |
   | **Kwota pracownika etatowego osoby niepalącej** | Kwota, jakiej dostawca świadczeń żąda za niepalącego pracownika. Jest to kwota płacona dostawcy świadczeń przez pracodawcę i powinna być oparta na częstotliwości płatności określonej w konfiguracji stawki. |
   | **Kwota pracodawcy osoby niepalącej** | Kwota, jakiej dostawca świadczeń żąda za niepalącego pracownika. Jest to kwota płacona dostawcy świadczeń przez pracodawcę i powinna być oparta na częstotliwości płatności określonej w konfiguracji stawki. |
   | **Kwota pracownika etatowego osoby palącej** | Kwota, jakiej dostawca świadczeń żąda za niepalącego pracownika. Jest to kwota płacona dostawcy świadczeń przez pracodawcę i powinna być oparta na częstotliwości płatności określonej w konfiguracji stawki. |
   | **Kwota pracodawcy osoby palącej** | Kwota, jakiej dostawca świadczeń żąda za niepalącego pracownika. Jest to kwota płacona dostawcy świadczeń przez pracodawcę i powinna być oparta na częstotliwości płatności określonej w konfiguracji stawki. |
   | **Kwota administracyjna** | Kwota administracyjna pobierana przez zewnętrznego administratora. Jest to kwota płacona zewnętrznemu administratorowi przez pracodawcę i powinna być oparta na częstotliwości płatności określonej w konfiguracji stawki. |
   | **Wskaźnik osoby niepalącej kredytu elastycznego** | Liczba elastycznych punktów kredytowych, jakie trzeba wydać na świadczenie, oparta na obliczeniu zdefiniowanym dla poziomu warstwy dla osób niepalących. Na przykład jeśli typem obliczania jest **Kwota w przeliczeniu na 1 jednostkę pieniężną ubezpieczenia**, obliczona kwota wynosi 10 000, a stawka elastycznych punktów kredytowych dla osób niepalących wynosi 6, to jeśli pracownik wybierze ubezpieczenia na 10 000, będzie go to kosztowało 6 elastycznych punktów kredytowych. Jeśli wybierze ubezpieczenie na 20 000, zapłaci 12 elastycznych punktów kredytowych itd. |
   | **Wskaźnik osoby palącej kredytu elastycznego** | Liczba elastycznych punktów kredytowych, jakie trzeba wydać na świadczenie, oparta na obliczeniu zdefiniowanym dla poziomu warstwy dla osób palących. |

5. Wybierz opcję **Zapisz**. 
