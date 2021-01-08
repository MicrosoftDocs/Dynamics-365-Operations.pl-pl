---
title: Tworzenie planu świadczeń
description: Konfigurowanie planów świadczeń w module Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitPlanListPage, BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: bcbf4c1a7f136e5563bf1210b6c09228dad95dea
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4420022"
---
# <a name="create-a-benefits-plan"></a>Tworzenie planu świadczeń

W tym artykule przedstawiono sposób konfigurowania planów świadczeń w programie Dynamics 365 Human Resources.

1. W obszarze roboczym **Zarządzanie świadczeniami** w sekcji **Plany** wybierz opcję **Plany świadczeń**.

2. Wybierz pozycję **Nowy**.

3. Na karcie **Ogólne** wprowadź wartości w następujących polach:

   | Pole | Opis |
   | --- | --- |
   | **Plan** | Unikatowy identyfikator planu. |
   | **Opis** | Opis planu. |
   | **Typ planu** | Podczas tworzenia nowego planu należy określić jego typ. Typ planu to nadrzędna grupa konkretnych typów świadczeń. Każdy typ planu określa, czy pracownik może się zarejestrować w wielu planach tego typu, czy kontakty są beneficjentami czy osobami na utrzymaniu, oraz opcje objęcia świadczeniami. Można tworzyć nowe, niestandardowe typy planów w celu zaspokojenia szczególnych potrzeb firmy w zakresie oferowanych świadczeń. Główne typy planów świadczeń: <ul><li>401K</li><li>ADD</li><li>Stomatologiczne</li><li>Sprawność fizyczna</li><li>FSA</li><li>Narodziny</li><li>LTD</li><li>Medyczne</li><li>PTO</li><li>STD</li><li>Wzrok</li></ul> |
   | **Kod typu planu** | Kod typu planu. |
   | **Program** | Określa program, do którego można opcjonalnie przypisać plan. |
   | **Pakiet** | Określa pakiet, do którego można opcjonalnie przypisać plan. |
   | **Główna** | Określa, czy plan jest planem głównym w pakiecie, do którego jest przypisany. |
   | **Stan** | Wskazuje obecny stan planu świadczeń. Domyślną wartość to Aktywny. Zmiana stanu na Nieaktywny spowoduje, że plan nie będzie dostępny do wyboru podczas rejestracji. |
   | **Data i godzina wejścia w życie** | Data i godzina, do której plan zaczyna obowiązywać. Domyślną wartością jest bieżąca data systemu. |
   | **Data i godzina ważności** | Data i godzina zakończenia obowiązywania planu (stan jest ustawiany na Nieaktywny). Wartość domyślna to 31.12.2154, czyli nigdy. |

4. Na karcie **Konfiguracja** określ wartości następujących pól, w zależności od typu tworzonego planu:

   | Typ planu | Pole | Opis |
   | --- | --- | --- |
   | Medyczny (Medyczny, Stomatologia, Okulistyka, HMO) | COBRA | Określa, czy plan podlega ustawie COBRA (Consolidated Omnibus Budget Reconciliation Act) regulującej ubezpieczenie zdrowotne w razie częściowej lub całkowitej utraty pracy. |
   | Medyczny (Medyczny, Stomatologia, Okulistyka, HMO) | HIPAA | Określa, czy plan podlega ustawie HIPAA (Health Insurance Portability and Accountability Act) regulującej przenośność i ochronę danych w ubezpieczeniach zdrowotnych. |
   | <ul><li>Medyczny (Medyczny, Stomatologia, Okulistyka, HMO)</li><li>Inne (PTO, Sprawność fizyczna)</li><li>Inne</li><li>Długoterminowa niepełnosprawność</li><li>ADD (podstawowe ubezpieczenie na życie, dobrowolne ubezpieczenie na życie)</li><li>Oszczędnościowy (na przykład 401(k))</li><li>FSA</li></ul> | Kwota kwalifikująca się przed opodatkowaniem | Określa, czy można wpłacać środki do planu przed naliczeniem podatków. |
   | <ul><li>Medyczny (Medyczny, Stomatologia, Okulistyka, HMO)</li><li>Inne (PTO, Sprawność fizyczna)</li><li>Długoterminowa niepełnosprawność</li><li>ADD (podstawowe ubezpieczenie na życie, dobrowolne ubezpieczenie na życie)</li><li>Oszczędnościowy (na przykład 401(k))</li><li>FSA</li></ul> | Kwota kwalifikująca się po opodatkowaniu | Określa, czy można wpłacać środki do planu po naliczeniu podatków. |
   | <ul><li>Medyczny (Medyczny, Stomatologia, Okulistyka, HMO)</li><li>Inne (PTO, Sprawność fizyczna)</li><li>Długoterminowa niepełnosprawność</li><li>ADD (podstawowe ubezpieczenie na życie, dobrowolne ubezpieczenie na życie)</li><li>Oszczędnościowy (na przykład 401(k))</li><li>FSA</li></ul> | Osoba wpłacająca | Określa, kto wpłaca środki do plany — pracownik, pracodawca, czy obie strony. |
   | <ul><li>Długoterminowa niepełnosprawność</li><li>ADD (podstawowe ubezpieczenie na życie, dobrowolne ubezpieczenie na życie)</li></ul> | Minimalne objęcie świadczeniem | Minimalna suma ubezpieczenia wymagana w planie. |
   | <ul><li>Długoterminowa niepełnosprawność</li><li>ADD (podstawowe ubezpieczenie na życie, dobrowolne ubezpieczenie na życie)</li></ul> | Maksymalne objęcie świadczeniem | Maksymalna suma ubezpieczenia wymagana w planie. |
   | <ul><li>Długoterminowa niepełnosprawność</li><li>ADD (podstawowe ubezpieczenie na życie, dobrowolne ubezpieczenie na życie)</li></ul> | Użyj przyrostów objęcia świadczeniem | Określa, czy należy sprawdzać, czy kwota ubezpieczenia jest prawidłową kwotą zwiększoną przyrostowo. |
   | <ul><li>Długoterminowa niepełnosprawność</li><li>ADD (podstawowe ubezpieczenie na życie, dobrowolne ubezpieczenie na życie)</li></ul> | Kwota przyrostowa | Przyrostowa suma ubezpieczenia w planie. Na przykład jeśli kwota przyrostowa wynosi 1000, pracownik nie może mieć ubezpieczenia na 200 500 PLN — trzeba je zaokrąglić w górę do 201 000 PLN lub w dół do 200 000 PLN. |
   | <ul><li>Długoterminowa niepełnosprawność</li><li>ADD (podstawowe ubezpieczenie na życie, dobrowolne ubezpieczenie na życie)</li></ul> | Kierunek przyrostowy | Określa kierunek zaokrąglania — w górę lub w dół — jeśli kwota pokrycia nie spełnia wartości kwoty przyrostowej. |
   | ADD (podstawowe ubezpieczenie na życie, dobrowolne ubezpieczenie na życie) | Dowody dotyczące ubezpieczenia | Określa, czy pracownik etatowy musi dostarczyć dowód potwierdzający zdolność ubezpieczeniową. |
   | ADD (podstawowe ubezpieczenie na życie, dobrowolne ubezpieczenie na życie) | Liczba dni | Kwota w walucie rozliczeniowej. To pole jest aktywne tylko po zaznaczeniu pola wyboru Dowody dotyczące ubezpieczenia. |
   | <ul><li>Oszczędnościowy (na przykład 401(k))</li><li>FSA</li></ul> | Minimalny roczny wkład | Minimalna kwota wpłat wymagana w planie. |
   | <ul><li>Oszczędnościowy (na przykład 401(k))</li><li>FSA</li></ul> | Maksymalny roczny wkład | Maksymalna kwota wpłat wymagana w planie. |
   | Oszczędnościowy (na przykład 401(k)) | Maksymalna kwota roczna pracodawcy | Maksymalna kwota, jaką pracodawca może wpłacić do planu oszczędnościowego pracownika w okresie świadczeniowym. Aby można było skorzystać z tego pola, należy zaznaczyć pole wyboru Dopasowanie pracodawcy. |
   | Oszczędnościowy (na przykład 401(k)) | Dopasowanie pracodawcy | Określa, czy pracodawca wpłaca środki do planu oszczędnościowego pracownika. |
   | Oszczędnościowy (na przykład 401(k)) | Procent dopasowania pracodawcy | Procent wkładu pracownika, jaki wpłaci pracodawca. |
   | Oszczędnościowy (na przykład 401(k)) | Ograniczenie dopasowania pracodawcy | Maksymalny procent wkładu pracownika, jaki wpłaci pracodawca. Na przykład jeśli pracodawca wpłaci 100% kwoty wpłaconej przez pracownika aż do poziomu 6% wynagrodzenia pracownika, ograniczenie dopasowania pracodawcy wynosi 6%. |

5. Na karcie **Konfiguracja** wprowadź wartości w następujących polach:

   | Pole | Opis |
   | --- | --- |
   | **Zezwalaj/kontynuuj rejestrację** | Określa, czy pracownicy mogą się rejestrować w planie, jeśli spełniają wymagania kwalifikacyjne.</br></br>Jeśli opcja ma wartość Nie, plan nie będzie dostępny dla pracowników podczas przetwarzania uprawnień. |
   | **Automatyczne rejestrowanie z poprzedniego roku** | Określa, czy automatycznie rejestrować uprawnionego pracownika etatowego w planie, jeśli zostały one zarejestrowane w poprzednim roku. |
   | **Automatyczna rejestracja jest domyślna** | Określa, czy ma być domyślnie wybierany plan do rejestracji. Plan nie jest obowiązkowy, więc pracownik może zmienić wybór domyślny. |
   | **Zamknięte dla nowych rejestracji** | Określa, czy możliwość korzystania z planu ma być ograniczona tylko do uprawnionych pracowników, którzy byli zarejestrowani w planie w poprzednim roku. |
   | **Plan obowiązkowy** | Określa, czy pracownicy mają być automatycznie rejestrowani w planie. Pracownicy nie mogą zmieniać wyboru rejestracji. |
   | **Data rozpoczęcia** | Dzień utworzenia planu w firmie. |
   | **Konto dostawcy** (dostawca świadczeń) | Dostawca, któremu firma płaci składki za plan. |
   | **Nazwa** (dostawca świadczeń) | Nazwa dostawcy. |
   | **Odwołanie do dostawcy** (dostawca świadczeń) | Odnośnik do dostawcy w planie. Na przykład numer planu grupowego w firmie. |
   | **Alternatywne odwołanie** (dostawca świadczeń) | Alternatywny odnośnik do dostawcy w planie. Na przykład numer konta firmy. |
   | **Waluta** (dostawca świadczeń) | Waluta używana do wpłacania składek do dostawcy. |
   | **Konto wydatków** (dostawca świadczeń) | Konto księgi głównej używane jako konto wydatków dla składek w planie. |
   | **Konto dostawcy** (administrator świadczeń) | Dostawca, któremu firma płaci za administrowanie planem. Jeśli firma sama administruje planem, nie wypełniaj tego pola. |
   | **Nazwa** (administrator świadczeń) | Nazwa dostawcy administrującego świadczeniami. |
   | **Odwołanie do dostawcy** (administrator świadczeń) | Odnośnik do dostawcy administrującego planem. |
   | **Alternatywne odwołanie** (administrator świadczeń) | Alternatywny odnośnik do dostawcy administrującego planem. |
   | **Waluta** (administrator świadczeń) | Waluta używana do płacenia administratorowi świadczeń. |
   | **Konto wydatków** (administrator świadczeń) | Konto księgi głównej używane jako konto wydatków dla kosztów związanych z administrowaniem planem. |

6. Na karcie **Filtry** skonfiguruj potrzebne ustawienia filtrowania. Można filtrować według następujących pól:

   - **Jednostka biznesowa**
   - **Dział**
   - **Firma**
   - **Lokalizacja**
   - **Pozycja**

7. Na karcie **Reguły uprawnienia** wprowadź wartości w następujących polach:

   | Pole | Opis |
   | --- | --- |
   | **Numer wiersza** | Numer wiersza reguły uprawnienia. |
   | **Reguła uprawnienia** | Reguła uprawnienia do zastosowania do planu świadczeń. Ta reguła uprawnienia zostanie zastosowana do odpowiedniego typu akcji oraz skojarzona ze wskazanym okresem oczekiwania na świadczenia i potrąceniami. |
   | **Typ akcji** | Akcja, do której ma zostać zastosowana reguła uprawnienia: zapisywanie na świadczenia lub wygaśnięcie świadczeń. |
   | **Okres oczekiwania na objęcie świadczeniem** | Wartość z formularza Okresy oczekiwania. Okres oczekiwania na świadczenia określa liczbę dni lub miesięcy, jaką pracownik czeka na objęcie świadczeniami lub wygaśnięcie świadczeń na podstawie kryteriów określonych w regule uprawnienia i typie akcji. |
   | **Okres oczekiwania na potrącenie** | Wartość z formularza Okresy oczekiwania. Okres oczekiwania na potrącenie określa liczbę dni lub miesięcy, jaką pracownik czeka na potrącenie z tytułu świadczeń z jego wypłaty na podstawie kryteriów określonych w regule uprawnienia i typie akcji. |

8. Wybierz opcję **Zapisz**.

## <a name="view-enrolled-workers"></a>Wyświetl zarejestrowanych pracowników

Możesz wyświetlić pracowników, którzy są zarejestrowani w wybranym planie świadczeń.

1. W obszarze roboczym **Zarządzanie świadczeniami** w sekcji **Plany** wybierz opcję **Plany świadczeń**.

2. Wybierz opcję **Zarejestrowani pracownicy**.

## <a name="attach-coverage-options"></a>Dołącz opcje objęcia świadczeniem

Do wybranego planu świadczeń można dodać opcje objęcia świadczeniami. Dołączenie opcji objęcia świadczeniami spowoduje zintegrowanie w niej konfiguracji stawek i potrąceń.  Przykład: w planie medycznym użytkownik wybiera opcję Ubezpieczenie rodzinne.  Wtedy musiałby wybrać stawkę rodzinną w powiązanym planie (ustawianą w formularzu Konfiguracja stawki) oraz potrącenie w powiązanym planie (ustawiane w formularzu Konfiguracja stawki). W ten sposób zostaną wyliczone koszty dla pracodawcy i pracownika za wybrany zakres świadczeń. Następnie należy powtórzyć proces dla objęcia świadczeniami pracownika etatowego+1 lub pracownika etatowego.

1. W obszarze roboczym **Zarządzanie świadczeniami** w sekcji **Plany** wybierz opcję **Plany świadczeń**.

2. Wybierz opcję **Dołącz opcje objęcia świadczeniem**.

## <a name="override-eligibility-rules"></a>Zastąp reguły uprawnień

Pracowników można dodawać do planu jako wyjątki od reguł uprawnień. Każdy dodany pracownik będzie uprawniony do planu świadczeń.

1. W obszarze roboczym **Zarządzanie świadczeniami** w sekcji **Plany** wybierz opcję **Plany świadczeń**.

2. Wybierz opcję **Zastąpienie reguły uprawnienia**.

## <a name="view-attached-periods"></a>Wyświetlanie dołączonych okresów

Istnieje możliwość wyświetlenia listy dostępnych okresów świadczeniowych.

1. W obszarze roboczym **Zarządzanie świadczeniami** w sekcji **Plany** wybierz opcję **Plany świadczeń**.

2. Wybierz opcję **Okresy**.

## <a name="view-plan-information"></a>Wyświetlanie informacji o planie

Można dodać opis planu, aby pomóc pracownikom w wyborze świadczeń. Wprowadzone tutaj informacje o planie są wyświetlane w obszarze Samoobsługa pracownika etatowego po umieszczeniu wskaźnika myszy na planie na liście opcji objęcia świadczeniami.

1. W obszarze roboczym **Zarządzanie świadczeniami** w sekcji **Plany** wybierz opcję **Plany świadczeń**.

2. Wybierz opcję **Informacje o planie**.

## <a name="view-flex-credit-programs"></a>Wyświetl programy kredytu elastycznego

1. W obszarze roboczym **Zarządzanie świadczeniami** w sekcji **Plany** wybierz opcję **Plany świadczeń**.

2. Wybierz opcję **Programy kredytu elastycznego**.
