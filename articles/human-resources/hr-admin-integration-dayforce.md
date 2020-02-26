---
title: Konfigurowanie integracji z rozwiązaniem Dayforce
description: Integracja między programami Microsoft Dynamics 365 Human Resources i Ceridian Dayforce opiera się na kilku krokach konfiguracji, które opisano w tym artykule. Aby można było przetwarzać sesję płatności, należy skonfigurować integrację w rozwiązaniach Human Resources i Dayforce.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 85e7274b0e9c130e5c3426fd1fff98410f93e49a
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/03/2020
ms.locfileid: "3010158"
---
# <a name="configure-integration-with-dayforce"></a>Konfigurowanie integracji z rozwiązaniem Dayforce

Integracja między programami Microsoft Dynamics 365 Human Resources i Ceridian Dayforce opiera się na kilku krokach konfiguracji, które opisano w tym artykule. Aby można było przetwarzać sesję płatności, należy skonfigurować integrację w rozwiązaniach Human Resources i Dayforce.

Jeśli korzystasz z usługi takiej jak Dayforce do realizowania sesji płatności, należy włączyć integrację w aplikacji Human Resources. Integracja wymaga określonych danych z programu Human Resources. W związku z tym należy sprawdzić, czy dane mapowane do systemu Dayforce są skonfigurowano w aplikacji Human Resources w sposób zapewniający obsługę integracji. Integracja wykorzystuje następujące ogólne kategorie danych:

- Dane kadrowe
- Dane o wynagrodzeniach
- Dane listy płac, takie jak cykle kalkulacji płac, okresy kalkulacji płac i kody zarobków
- Dane pracowników

W tym artykule opisano czynności, które należy wykonać, aby włączyć integrację. Objaśniono tu także typy danych i szczegóły konfiguracji, których wymaga integracja.

## <a name="enable-the-integration"></a>Włączanie integracji

W aplikacji Human Resources należy włączyć funkcję integracji i wprowadzić informacje konfiguracyjne w celu nawiązania połączenia z systemem Dayforce. Jeśli chcesz, aby generowane transakcje księgi głównej były importowane do usługi Microsoft Dynamics 365 Finance, należy także skonfigurować konto magazynu w usłudze Microsoft Azure oraz wprowadzić ciąg połączenia z usługą Azure Storage w aplikacji Finance.

Aby włączyć integrację w aplikacji Human Resources, wykonaj następujące kroki.

1. Na stronie **Administrowanie systemem** wybierz opcję **Konfiguracja integracji**.
2. Wprowadź punkt końcowy objęty bezpiecznym protokołem FTP (File Transfer Protocol) i ścieżkę do folderu objętego bezpiecznym protokołem FTP.
3. Wprowadź nazwę użytkownika i hasło użytkownika, który będzie uzyskiwał dostęp do punktu końcowego i ścieżki folderu objętych bezpiecznym protokołem FTP.
4. Przetestuj połączenie, a w opcji **Włącz integrację listy płac** ustaw wartość **Tak**.

Po włączeniu integracji następuje utworzenie pakietu i plików eksportu danych oraz ustawienie częstotliwości. W razie potrzeby można zmienić tę częstotliwość.

Aby uzyskać więcej informacji o kontach magazynu w usłudze Azure i ciągach połączeń z usługą Azure Storage, zobacz następujące artykuły poświęcone usłudze Azure:

- [Konta magazynu w usłudze Azure — informacje](https://docs.microsoft.com/azure/storage/common/storage-create-storage-account?toc=%2fazure%2fstorage%2ffiles%2ftoc.json)
- [Konfigurowanie ciągów połączeń z usługą Azure Storage](https://docs.microsoft.com/azure/storage/common/storage-configure-connection-string)

### <a name="technical-details-when-payroll-integration-is-enabled"></a>Dane techniczne, gdy integracja listy płac jest włączona

Włączenie integracji listy płac ma dwa główne skutki:

- Zostanie utworzony projekt eksportu danych o nazwie „Eksport integracji list płac”. Ten projekt zawiera podmioty i pola wymagane do integracji listy płac. Aby sprawdzić projekt, przejdź do **Administracja systemu**, wybierz kafelek **Zarządzanie danymi**, a następnie otwórz projekt danych z listy projektów.
- To zadanie wsadowe wykonuje projekt eksportu danych, szyfruje otrzymany pakiet danych i przesyła plik pakietu danych do punktu końcowego SFTP skonfigurowanego na ekranie **Integracja konfiguracji**.

> [!NOTE]
> Pakiet danych przesłany do punktu końcowego SFTP jest szyfrowany przy użyciu klucza unikalnego dla pakietu. Klucz to Azure Key Vault dostępny jedynie przez Ceridian. Nie jest możliwe odszyfrowanie i sprawdzenie zawartości pakietu danych. Jeśli chcesz sprawdzić zawartość pakietu danych, musisz ręcznie wyeksportować projekt danych „Eksportu integracji płac”, pobrać go, a następnie otworzyć. Ręczny eksport nie zastosuje szyfrowania ani nie dokona transferu pakietu.

## <a name="configure-your-data"></a>Konfigurowanie danych 

Aby przetwarzać listę płac, należy skonfigurować dane kadrowe w aplikacji Human Resources. Należy skonfigurować dane organizacyjne, takie jak funkcje i stanowiska, oraz informacje o wynagrodzeniach i świadczeniach. Informacje te stanowią zasób danych o zatrudnieniu, wynagrodzeniach i potrąceniach, które są wymagane do wygenerowania płacy pracownika.

### <a name="human-resource-data"></a>Dane kadrowe

#### <a name="benefits"></a>Świadczenia 

Moduł Zasoby ludzkie oferuje narzędzia do konfigurowania i obsługi świadczeń, potrąceń i planów wynagrodzeń pracowników, które organizacja oferuje swoim pracownikom lub przetwarza w ich imieniu.

Podczas tworzenia świadczeń należy wziąć pod uwagę następujące dane i konfiguracje używane w systemie Dayforce.

##### <a name="benefit-plans"></a>Plany świadczeń

- Plan (wymagane)
- Typ (wymagane)
- Wpływ na listę płac (wymagane)
- Odzyskaj zaległości
- Metoda potrącenia
- Priorytet potrącenia
- Okres limitu
- Kwota limitu

##### <a name="benefits"></a>Świadczenia

- Plan (wymagane)
- Typ (wymagane)
- Opcja (wymagane)
- Identyfikator świadczenia (wymagane)
- Częstotliwość
- Podstawa
- Kwota lub stawka
- Kod zarobków

##### <a name="supported-frequencies"></a>Obsługiwane częstotliwości 

- Tygodniowa
- Co dwa tygodnie
- Co pół miesiąca
- Miesięczne

##### <a name="supported-bases"></a>Obsługiwane podstawy 

- Stała kwota
- Procent zarobków
- Godziny płatne

System Dayforce tworzy następujące potrącenia w oparciu o wpływ na listę płac zdefiniowany w planie świadczeń.

| Przeglądanie zadań w Human Resources        | Wynik w systemie Dayforce                            |
|----------------------------|-----------------------------------------------|
| Brak                       | Nie jest tworzone żadne potrącenie                      |
| Tylko potrącenie             | Jest tworzone potrącenie od pracownika.             |
| Tylko udział          | Jest tworzone potrącenie od pracodawcy.             |
| Potrącenie i udział | Są tworzone potrącenia od pracownika i pracodawcy. |

Aby uzyskać więcej informacji o sposobie definiowania programu świadczeń i zarządzania nim, zobacz następujące artykuły:

- [Dostarczanie programu świadczeń dla pracowników etatowych](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/deliver-employee-benefits-program)
- [Utwórz nowe świadczenie](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/create-new-benefit)
- [Definiowanie zasad i reguł uprawnień do świadczenia](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-benefit-eligibility-rules-policies)
- [Rejestrowanie i usuwanie świadczeń dla pracowników](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-remove-benefits-workers)

#### <a name="compensation"></a>Wynagrodzenie 

Zarządzanie wynagrodzeniami służy do kontrolowania wypłat podstawowego wynagrodzenia i nagród. Stałe podstawowe wynagrodzenie pracownika i podwyżki podstawowego wynagrodzenia są kontrolowane przez plany stałych wynagrodzeń. Płatności motywacyjne, takie jak premie motywacyjne, wypłaty premii, nagrody za wyniki pracy, prawa do nabycia akcji po ustalonej cenie, cesje i nagrody jednorazowe lub okazjonalne są kontrolowane za pomocą systemów wynagrodzeń o zmiennej wysokości.

Program Dayforce wykorzystuje informacje o wynagrodzeniach do obliczania godzinowej lub rocznej stawki pracownika. Określenie systemów stałych wynagrodzeń i konwersji stawek płac jest wymagane. Pracownicy muszą być skojarzeni z systemem stałych wynagrodzeń.

Aby uzyskać więcej informacji o planach wynagrodzeń, zobacz następujące artykuły:

- [Tworzenie planów stałych wynagrodzeń](https://docs.microsoft.com/dynamics365/unified-operations/talent/create-fixed-compensation-plans)
- [Tworzenie planów wynagrodzeń o zmiennej wysokości](https://docs.microsoft.com/dynamics365/unified-operations/talent/create-variable-compensation-plans)
- [Opracowywanie struktury i planu pensji/wynagrodzeń](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/develop-salary-compensation-structure-plan)
- [Przetwarzanie wynagrodzenia](https://docs.microsoft.com/dynamics365/unified-operations/talent/process-compensation)
- [Definiowanie procesu związanego z wynagrodzeniem i obliczanie wyników](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-compensation-process-calculate-results)
- [Zarejestrowanie pracownika w systemie stałych wynagrodzeń](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-fixed-compensation-plan)
- [Zarejestrowanie pracownika w systemie wynagrodzeń o zmiennej wysokości](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-variable-compensation-plan)

#### <a name="jobs"></a>Funkcje 

Funkcja to zbiór zadań i obowiązków, które są wymagane od osoby wykonującej funkcję. Aby uzyskać więcej informacji, zobacz następujące artykuły:

- [Konfigurowanie składników funkcji](https://docs.microsoft.com/dynamics365/unified-operations/talent/create-job)
- [Definiowanie nowych funkcji](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-jobs)

##### <a name="positions"></a>Pozycje

Pozycja jest pojedynczym wystąpieniem zadania. Na przykład stanowisko „Menedżer ds. sprzedaży (Wschód)” jest jednym ze stanowisk skojarzonych z funkcją „Menedżer ds. sprzedaży”. Stanowisko istnieje w dziale. Z każdym stanowiskiem może być skojarzony tylko jeden pracownik.

Podczas konfigurowania stanowisk pamiętaj o następujących danych i konfiguracjach:

- Stanowisko (wymagane)
- Opis (wymagane)
- Funkcja (wymagane)
- Dział (wymagane)
- Typ stanowiska (wymagane)
- W przeliczeniu na pełne etaty
- Zwykłe godziny (rocznie) (wymagane)
- Zapłacone przez firmę (wymagane)
- Cykl kalkulacji płac (wymagane)
- Domyślny wymiar finansowy — Centrum kosztu (wymagane)
- Przypisanie pracownika — Pracownik, rozpoczęcie przypisania, zakończenia przypisania, kod przyczyny

Jeśli z tą samą funkcją jest skojarzonych wiele stanowisk w tym samym dziale, są one konsolidowane w jedno stanowisko w systemie Dayforce.

Aby uzyskać więcej informacji, zobacz następujące artykuły:

- [Organizowanie pracowników za pomocą działów, funkcji i stanowisk](https://docs.microsoft.com/dynamics365/unified-operations/talent/departments-jobs-positions#positions)
- [Konfigurowanie stanowisk](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/set-up-positions)

#### <a name="departments"></a>Działy

Dział to jednostka operacyjna należąca do kategorii lub obszaru funkcjonalnego organizacji. Dział jest odpowiedzialny za określony obszar organizacji, np. sprzedaż, księgowość lub zasoby ludzkie. Działy pozwalają tworzyć raporty dotyczące obszarów funkcyjnych. Działy mogą mieć odpowiedzialność zysków i strat.

Aby uzyskać więcej informacji, zobacz następujące artykuły:

- [Tworzenie działu i kojarzenie go z hierarchią działów](https://docs.microsoft.com/dynamics365/unified-operations/talent/create-department-add-department-hierarchy)
- [Definiowanie nowych działów](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-departments)

#### <a name="pay-cycles-and-pay-periods"></a>Cykle płac i okresy płac

Cykl kalkulacji płac decyduje o częstotliwości wykonywania sesji obliczania listy płac oraz o konkretnych dniach, kiedy pracownicy otrzymują zapłatę. Na przykład cykl kalkulacji płac może być miesięczny, a pracownicy mogą otrzymywać wypłatę w ostatnim dniu miesiąca. Alternatywnie cykl kalkulacji płac może być tygodniowy, a pracownicy dostają wypłatę w każdy wtorek po zakończeniu okresu kalkulacji płac. Cykle kalkulacji płac są przypisywane do stanowisk w celu kontrolowania, kiedy pracownicy na tych stanowiskach otrzymują zapłatę.

Po utworzeniu cykli kalkulacji płac można wygenerować okresy kalkulacji płac dla każdego cyklu. Każdy okres kalkulacji płac zawiera domyślną datę płatności, która bazuje na podanych przez Ciebie informacjach. Można jednak zmodyfikować domyślną datę płatności w okresie kalkulacji płac, co pozwala stosować wyjątki, np. gdy data płatności przypada na dzień wolny od pracy.

Poniższe informacje są używane w programie Dayforce:

- Cykl kalkulacji płac (wymagane)
- Częstotliwość cyklu kalkulacji płac (wymagane)
- Data rozpoczęcia okresu (pierwszy okres kalkulacji płac jest wymagany)
- Domyślna data płatności (pierwszy okres kalkulacji płac jest wymagany)

Te informacje są integrowane z usługą Dayforce jako grupy płac oraz dzielone na kraje lub regiony dla każdego cyklu kalkulacji płac. Przed integracją musi być wygenerowany co najmniej jeden okres kalkulacji płac. System Dayforce generuje kalendarze grup płac i daty płatności na podstawie daty rozpoczęcia pierwszego okresu kalkulacji płac i domyślnej daty płatności ustawionej w aplikacji Human Resources.

#### <a name="earning-codes"></a>Kody zarobków

Kody zarobków jednoznacznie identyfikują każdy rodzaj dochodów, które otrzymują pracownicy. Kody mają różne parametry związane z zarobkami, takie jak reguły księgowania, przepisy podatkowe, wymagania dotyczące raportowania i możliwość zwiększania wartości brutto.

Poniższe informacje są używane w programie Dayforce:

- Kod zarobków (wymagane)
- opis
- Jednostka miary
- Płatne

### <a name="worker-data"></a>Dane pracowników

Dokumenty o różnych typach posiadanych pracowników są ważne dla informatycznych systemów kadrowych i płacowych. Wprowadzone informacje mogą służyć do monitorowania pracowników i danych osobowych.

Można przechowywać następujące informacje o pracownikach:

- **Podstawowe** — Podstawowe informacje o pracowniku, takie jak dane kontaktowe, demograficzne, identyfikacyjne, informacje o rodzinie, stosunek do służby wojskowej, status emigranta oraz dane kontaktowe dla nagłych wypadków.
- **Zatrudnienie** — Informacje o zatrudnieniu pracownika, takie jak przynależność do firmy lub organizacji, przypisanie stanowiska, daty rozpoczęcia i zakończenia, prawo do zatrudnienia, warunki zatrudnienia, emerytura, urlop i informacje o przeniesieniu.
- **Urlopy i nieobecności** — Informacje o nieobecności pracownika, takie jak kalendarze pracy, transakcje nieobecności i ustawienia nieobecności.
- **Wynagrodzenia i płace** — Informacje o planach wynagrodzeń i płacach pracownika, takie jak rejestracja w planie, nagrody, wydajność, prowizje, informacje podatkowe, odejście na emeryturę i potrącenia z wynagrodzenia.

Podczas wprowadzania danych pracownika należy wziąć pod uwagę następujące dane i konfiguracje używane w programie Dayforce.

#### <a name="general-information"></a>Informacje ogólne

- Numer pracownika (wymagane)
- Imię (wymagane)
- Nazwisko (wymagane)
- Drugie imię
- Data stażu pracy
- Znane jako

#### <a name="personal-information"></a>Informacje osobiste

- Stan cywilny (wymagane)
- Data urodzenia (wymagane)
- Płeć (wymagane)
- Osoba niepełnosprawna
- Obywatelstwo (kraj/region) (tylko w przypadku Meksyku)

#### <a name="address-information"></a>Informacje adresowe

- Podstawowy (wymagane)
- Kraj/region (wymagane)
- Kod pocztowy (wymagane)
- Numer domu (wymagane) (jedynie w przypadku Meksyku)
- Dodatkowe określenie budynku (tylko w przypadku Meksyku)
- Miejscowość (wymagane)
- Województwo (wymagane)
- Powiat (wymagane)

#### <a name="contact-information"></a>Informacje o kontakcie 

- Podstawowy (wymagane)
- Nazwa osoby kontaktowej (wymagane)
- Wewnętrzny

#### <a name="payroll-information-and-earning-codes"></a>Informacje płacowe i kody zarobków

Pracownicy mogą mieć przypisane określone zarobki z określoną częstotliwością wypłat oraz mieć ustawioną preferowaną metodę płatności. Następujące pola są używane w usłudze Dayforce w celu zagwarantowania, że te ustawienia i preferencje są wykorzystywane.

##### <a name="earning-codes"></a>Kody zarobków

- Stanowisko (wymagane)
- Kod zarobków (wymagane)
- Częstotliwość (wymagane)
- Kwota (wymagane)

##### <a name="payroll-information"></a>Informacje listy płac

- Metoda płatności
- Region gospodarczy (wymagane)
- Identyfikator świadczeń pracownika etatowego
- Numer dowodu osobistego (wymagane)
- Numer książeczki wojskowej
- Identyfikator zmiany (wymagane)
- Numer identyfikacji podatkowej (wymagane)
- Identyfikator związku (wymagane)
- Identyfikator dnia roboczego (wymagane)
- Numer pozwolenia na pracę

> [!NOTE]
> W Meksyku obsługiwane metody płatności to **Gotówka**, **Czek** (fizyczny czek wystawiany przez firmę) i **Płatność elektroniczna**. Jeśli metoda płatności nie zostanie określona, domyślnie będzie używana metoda **Czek**.

#### <a name="employment-details"></a>Szczegóły zatrudnienia

Historia szczegółów zatrudnienia pełni rolę kluczowych informacji przy ustalaniu statusów zatrudnienia, zwolnienia i ponownego zatrudnienia pracownika etatowego w systemie Dayforce. W rozwiązaniu Dayforce może istnieć tylko jeden aktywny rekord zatrudnienia na raz.

- Data rozpoczęcia zatrudnienia (wymagane)
- Data zakończenia zatrudnienia
- Rozpoczęcie
- Dopasowana data rozpoczęcia.
- Data zakończenia (wymagane po rozwiązaniu stosunku pracy)
- Powód rozwiązania umowy (wymagane po rozwiązaniu stosunku pracy)

Kluczowe daty pracownika są obliczane na podstawie następujących informacji.

| Zasoby ludzkie                | Dayforce                                                                                             |
|-----------------------|------------------------------------------------------------------------------------------------------|
| Ostatnia data zatrudnienia | Rozpoczęcie pracy w bieżącym rekordzie historii niezakończonego zatrudnienia                                 |
| Data zakończenia      | Data zakończenia zatrudnienia w bieżącym rekordzie historii niezakończonego zatrudnienia                                 |
| Rozpoczęcie            | Skorygowana data rozpoczęcia, data rozpoczęcia lub rozpoczęcie zatrudnienia w bieżącym rekordzie historii nieaktywnego zatrudnienia |
| Pierwotna data zatrudnienia    | Rozpoczęcie zatrudnienia w najwcześniejszym rekordzie historii zatrudnienia                                               |

#### <a name="compensation"></a>Wynagrodzenie

Plan stałych wynagrodzeń musi być skojarzony z podstawowym stanowiskiem każdego pracownika w okresie zatrudnienia. Okres ten rozpoczyna się w dniu zatrudnienia pracownika (lub rozpoczęcia zatrudnienia) i trwa do momentu zakończenia zatrudnienia.

- Data obowiązywania (wymagane)
- Data ważności
- Stawka płacy (wymagane)
- Konwersje stawek płacy (wymagane)
- Równowartość roczna (wymagane)
- Równowartość godzinowa (wymagane)

Jeśli pracownik rozliczany godzinowo zajmuje kilka stanowisk, stałe wynagrodzenie na podstawowym stanowisku jest importowane do systemu Dayforce jako podstawowa stawka/wynagrodzenie na poziomie pracownika. Dla stanowisk dodatkowych stawka godzinowa jest zapisywana na odpowiednich stanowiskach w usłudze Dayforce.

Jeśli pracownik na stawce stałej zajmuje kilka stanowisk, skumulowana stawka godzinowa i roczne wynagrodzenie ze wszystkich aktywnych stanowisk są używane jako podstawowa stawka/wynagrodzenie na poziomie pracownika.

#### <a name="identification-numbers"></a>Numery identyfikacyjne

##### <a name="social-security-identifier"></a>Numer ubezpieczenia społecznego 

Każdy pracownik musi mieć jeden identyfikator podstawowy. Identyfikator ten musi być typu **PESEL**. W systemie Dayforce jest on automatycznie interpretowany jako numer ubezpieczenia społecznego wymagany w celu zatrudnienia.

- Podstawowy (wymagane)
- Typ identyfikacji = „PESEL”
- Data wystawienia
- Data ważności

Pracownicy mogą zadeklarować wiele numerów identyfikacyjnych typu **PESEL**. Jednak tylko rekord oznaczony jako **Podstawowy** jest integrowany z rozwiązaniem Dayforce, niezależnie od tego, czy jest on aktywny, czy wygasły.

#### <a name="bank-accounts-and-disbursements"></a>Konta bankowe i wypłaty

Dla każdego pracownika, który wybrał opcję otrzymywania wynagrodzenia przelewami na rachunek bankowy, należy wprowadzić prawidłowe dane konta bankowego.

| Zasoby ludzkie                         | Dayforce                                                                                                    |
|--------------------------------|-------------------------------------------------------------------------------------------------------------|
| Numer konta bankowego (wymagane) |                                                                                                             |
| Kod SWIFT (wymagane)          | Pole **Identyfikator banku** używane w trakcie przetwarzania listy płac w Meksyku.                                                             |
| Numer oddziału (wymagane)       |                                                                                                             |
| Typ konta bankowego (wymagane)   | Pole **Typ konta** używane w trakcie przetwarzania listy płac w Meksyku. Obsługiwane wartości **Czekowe** i **Lista płac**. |

> [!NOTE]
> Pracownicy, którzy wybiorą otrzymywanie wynagrodzeń przelewami na rachunki bankowe, muszą podać łącze do konta pozostałości, które należy do firmy mającej podstawowy adres w Meksyku i jest skojarzone z prawidłowym kontem bankowym w meksykańskim banku. Wszystkie inne konta pozostałości są ignorowane.

#### <a name="address-information"></a>Informacje adresowe

Każdy pracownik musi mieć jedną lokalizację podstawową. W systemie Dayforce ta lokalizacja jest używana do określenia głównego miejsca zamieszkania pracownika w celach podatkowych.

- Podstawowy (wymagane)
- Kraj/region (wymagane)
- Kod pocztowy (wymagane)
- Ulica (wymagane)
- Numer domu (wymagane)
- Dodatkowe określenie budynku
- Miejscowość (wymagane)
- Województwo (wymagane)
- Powiat (wymagane)

## <a name="configure-your-data-to-generate-payroll-in-united-states-and-canada"></a>Konfigurowanie danych w celu generowania listy płac w Stanach Zjednoczonych i Kanadzie

Jeśli generujesz płace dla pracowników na terenie Stanów Zjednoczonych i Kanady, należy skonfigurować następujące elementy:

- Dla stanowisk muszą być określone działy.
- Centra kosztów muszą być ustawione jako wymiary finansowe i muszą być pierwszym elementem w ciągu domyślnych wymiarów finansowych.

> [!NOTE] 
> Można skonfigurować Human Resources tak, aby Stanowiska umożliwiały określenie działu. Aby to zrobić, przejdź do **stanowisk udostępnionych zasobów ludzkich > Stanowisk > wymagają działów stanowisk**. Zaleca się, aby to ustawienie zostało wymuszone dla integracji.

### <a name="job-types"></a>Typy funkcji

Typy funkcji służą do grupowanie podobnych funkcji w kategorie. Typy funkcji są wymagane w celu przetwarzania listy płac w Stanach Zjednoczonych i Kanadzie. Przykłady typów funkcji to zatrudnienie w pełnym i niepełnym wymiarze czasu albo wynagrodzenie za etat i za godziny. Typy funkcji są mapowane do systemu Dayforce jako typy płac, które wskazują, czy pracownik jest na stawce godzinowej, czy stałej pensji.

Następujące typy funkcji i opisy są wymagane.

| Typ funkcji   | opis |
|------------|-------------|
| Co godzinę     | Co godzinę      |
| Stała pensja   | Stała pensja    |

### <a name="position-types"></a>Typy stanowisk 

Typy stanowisk służą do opisywania, czy stanowisko jest w pełnym wymiarze czasu, niepełnym wymiarze czasu lub ma inną konfigurację. Typy stanowisk są mapowane do systemu Dayforce jako klasy płac, które wskazują, czy pracownik jest zatrudniony na pełny etat, czy na część etatu.

Następujące typy stanowisk i opisy są wymagane.

| Typ stanowiska   | opis        |
|-----------------|--------------------|
| Pełny etat       | Pracownik etatowy zatrudniony w pełnym wymiarze czasu |
| Część etatu       | Pracownik etatowy zatrudniony w niepełnym wymiarze czasu |

### <a name="reason-codes"></a>Kody przyczyn

Kody przyczyn informują o stanie pracownika. Kody przyczyn są mapowane do systemu Dayforce jako przyczyny stanu, które wskazują powód zmiany stanowiska lub statusu zatrudnienia pracownika.

Następujące kody przyczyn i opisy są wymagane.

| Kod przyczyny    | opis      | Odpowiednie scenariusze |
|----------------|------------------|----------------------|
| RESIGNATION    | Rezygnacja      | Zwalnianie pracownika     |
| TERMINATION    | Przerwanie      | Zwalnianie pracownika     |
| RETIREMENT     | Emerytura       | Zwalnianie pracownika     |
| INNY          | Inne przyczyny    | Zwalnianie pracownika     |
| DEATH          | Śmierć            | Zwalnianie pracownika     |
| LEAVEOFABSENCE | Nieobecność | Zwalnianie pracownika     |
| CONTRACTEND    | Zakończenie umowy  | Zwalnianie pracownika     |
| SALARYCHANGE   | Zmiana wynagrodzenia | Wynagrodzenie         |

### <a name="marital-status"></a>Stan cywilny

Wartości stanu cywilnego są mapowane do systemu Dayforce i w razie potrzeby tłumaczone na akceptowane wartości podczas integracji.

W poniższej tabeli przedstawiono mapowanie wartości stanu cywilnego do usługi Dayforce.

| Zasoby ludzkie                 | Dayforce             |
|------------------------|----------------------|
| Żonaty/mężatka                | Żonaty/mężatka              |
| Niebędący/niebędąca w związku                 | Niebędący/niebędąca w związku               |
| Wdowiec/wdowa                | Wdowiec/wdowa              |
| Rozwiedziony/rozwiedziona               | Rozwiedziony/rozwiedziona             |
| Związek zarejestrowany | Partnerstwo krajowe |
| None                   | None                 |
| Konkubinat             | Konkubinat           |

### <a name="gender"></a>Rodzaj

Określenia płci są mapowane do systemu Dayforce i w razie potrzeby tłumaczone na akceptowane wartości podczas integracji.

W poniższej tabeli przedstawiono mapowanie określeń płci do usługi Dayforce.

| Zasoby ludzkie       | Dayforce        |
|--------------|-----------------|
| Mężczyzna         | Mężczyzna            |
| Kobieta       | Kobieta          |
| Nieokreślone | *Nieobsługiwane* |

### <a name="earning-codes"></a>Kody zarobków

Kody zarobków jednoznacznie identyfikują każdy rodzaj dochodów, które otrzymują pracownicy. Kody mają różne parametry związane z zarobkami, takie jak reguły księgowania, przepisy podatkowe, wymagania dotyczące raportowania i możliwość zwiększania wartości brutto. W razie ustawienia nieobsługiwanej częstotliwości domyślnie w obliczeniu będzie używana częstotliwość **Każda wypłata**.

#### <a name="supported-frequencies"></a>Obsługiwane częstotliwości

- Wszyscy
- EVERYPAY
- EACHPAYPERIOD
- EVRYOTHRPAYODD
- EVRYOTHRPAYEVN
- 1OFMTH
- LASTOFMTH
- 2OFMTH
- 3OFMTH
- 4OFMTH
- 5OFMTH
- 1N2OFMTH
- 3N4OFMTH
- 1N3OFMTH
- 1N4OFMTH
- 2N3OFMTH
- 2N4OFMTH
- 1N2N3OFMTH
- 1N2N4OFMTH
- 1N3N4OFMTH
- 2N3N4OFMTH
- 1N2N3N4OFMTH – 1N2N3N4OFMTH
- 2N3N4N5OFMth – 2N3N4N5OFMth
- 1OFQTR – 1OFQTR
- LASTOFQTR – LASTOFQTR
- LASTMTHOFQTR – LASTMTHOFQTR
- 1OFYEAR – 1OFYEAR
- LASTOFYEAR – LASTOFYEAR
- NOVNDECOFYEAR – NOVNDECOFYEAR

### <a name="addresses"></a>Adresy

Identyfikacja określonych kodów kraju lub regionu, województwa i powiatu (gminy) wymaga określonych formatów, które potrafi rozpoznać system Dayforce oraz dostawcy wewnątrz krajów/regionów. Co prawda format nazw miejscowości jest elastyczny, ale każda miejscowość musi być skojarzona z województwem.

| Zasoby ludzkie          | Dayforce              |
|-----------------|-----------------------|
| Kraj/region  | Kod kraju          |
| Kod pocztowy | Kod pocztowy           |
| Stanowy           | Kod województwa            |
| Miejscowość            | Miejscowość                  |
| Powiat          | Powiat (gmina) |
| Ulica          | Wiersz adresu 1        |

### <a name="tax-regions"></a>Regiony podatkowe

Regiony podatkowe służą do określania odpowiedniej stawki podatkowej stosowanej podczas generowania listy płac. Regiony podatkowe są mapowane do systemu Dayforce jako adresy lokalizacji. Domyślny region podatkowy musi być skojarzony z aktywnym stanowiskiem pracownika. 

- Region podatkowy (wymagane)
- Kraj/region (wymagane)
- Województwo (wymagane)
- Powiat 
- Miejscowość (wymagane)

## <a name="configure-your-data-to-generate-payroll-in-mexico"></a>Konfigurowanie danych w celu generowania listy płac w Meksyku

Jeśli generujesz płace dla pracowników na terenie Meksyku, należy skonfigurować następujące elementy:

- Dla stanowisk muszą być określone działy.
- Centra kosztów muszą być ustawione jako wymiary finansowe i muszą być pierwszym elementem w ciągu domyślnych wymiarów finansowych.

### <a name="job-types"></a>Typy stanowisk

Typy funkcji służą do grupowanie podobnych funkcji w kategorie. Typy funkcji są wymagane w celu przetwarzania listy płac w Meksyku. Przykłady typów funkcji to zatrudnienie w pełnym i niepełnym wymiarze czasu albo wynagrodzenie za etat i za godziny. Typy funkcji są mapowane do systemu Dayforce jako typy płac, które wskazują, czy pracownik jest na stawce godzinowej, czy stałej pensji.

Następujące typy funkcji i opisy są wymagane.

| Typ funkcji   | opis |
|------------|-------------|
| Co godzinę     | MX Co godzinę   |
| Stała pensja   | MX Stała pensja |

### <a name="position-types"></a>Typy stanowisk 

Typy stanowisk służą do opisywania, czy stanowisko jest w pełnym wymiarze czasu, niepełnym wymiarze czasu lub ma inną konfigurację. Typy stanowisk są mapowane do systemu Dayforce jako klasy płac, które wskazują, czy pracownik jest zatrudniony na pełny etat, czy na część etatu.

Następujące typy stanowisk i opisy są wymagane.

| Typ stanowiska   | opis        |
|-----------------|--------------------|
| Pełny etat       | Pracownik etatowy zatrudniony w pełnym wymiarze czasu |
| Część etatu       | Pracownik etatowy zatrudniony w niepełnym wymiarze czasu |

### <a name="reason-codes"></a>Kody przyczyn

Kody przyczyn informują o stanie pracownika. Kody przyczyn są mapowane do systemu Dayforce jako przyczyny stanu, które wskazują powód zmiany stanowiska lub statusu zatrudnienia pracownika.

Następujące kody przyczyn i opisy są wymagane.

| Kod przyczyny            | opis                    | Odpowiednie scenariusze |
|------------------------|--------------------------------|----------------------|
| DEPARTUREBEFOREPAYMENT | Odejście z pracy przed pierwszą wypłatą | Zwalnianie pracownika     |
| RESIGNATION            | Rezygnacja                    | Zwalnianie pracownika     |
| PENSION                | Emerytura                        | Zwalnianie pracownika     |
| TERMINATION            | Przerwanie                    | Zwalnianie pracownika     |
| RETIREMENT             | Emerytura                     | Zwalnianie pracownika     |
| ABSENTEE               | Absencja                       | Zwalnianie pracownika     |
| INNY                  | Inne przyczyny                  | Zwalnianie pracownika     |
| CLOSURE                | Zaprzestanie działalności przez firmę               | Zwalnianie pracownika     |
| DEATH                  | Śmierć                          | Zwalnianie pracownika     |
| LEAVEOFABSENCE         | Nieobecność               | Zwalnianie pracownika     |
| CONTRACTEND            | Zakończenie umowy                | Zwalnianie pracownika     |
| SALARYCHANGE           | Zmiana wynagrodzenia               | Wynagrodzenie         |

### <a name="terms-of-employment"></a>Warunki zatrudnienia

Warunki zatrudnienia służą do tworzenia kategorii warunków zatrudnienia. Warunki są mapowane do systemu Dayforce jako wartości wskaźnika zatrudnienia.

Następujące warunki zatrudnienia i opisy są wymagane.

| Warunki zatrudnienia   | opis |
|-----------------------|-------------|
| Normalna               | Normalna     |
| Bezpośredni                | Bezpośredni      |
| Staż            | Staż  |
| Stałe             | Stałe   |

### <a name="marital-status"></a>Stan cywilny

Wartości stanu cywilnego są mapowane do systemu Dayforce i w razie potrzeby tłumaczone na akceptowane wartości podczas integracji.

W poniższej tabeli przedstawiono mapowanie wartości stanu cywilnego do usługi Dayforce.

| Zasoby ludzkie                 | Dayforce                  |
|------------------------|---------------------------|
| Żonaty/mężatka                | Żonaty/mężatka                   |
| Niebędący/niebędąca w związku                 | Niebędący/niebędąca w związku                    |
| Wdowiec/wdowa                | Wdowiec/wdowa                   |
| Rozwiedziony/rozwiedziona               | Rozwiedziony/rozwiedziona                  |
| Związek zarejestrowany | Partnerstwo krajowe      |
| None                   | *Nieobsługiwane w Meksyku* |
| Konkubinat             | *Nieobsługiwane w Meksyku* |

### <a name="gender"></a>Rodzaj

Określenia płci są mapowane do systemu Dayforce i w razie potrzeby tłumaczone na akceptowane wartości podczas integracji.

W poniższej tabeli przedstawiono mapowanie określeń płci do usługi Dayforce.

| Zasoby ludzkie       | Dayforce                  |
|--------------|---------------------------|
| Mężczyzna         | Mężczyzna                      |
| Kobieta       | Kobieta                    |
| Nieokreślone | *Nieobsługiwane w Meksyku* |

### <a name="payment-method"></a>Metoda płatności

Funkcja metod płatności oferuje pracownikowi i firmie sposób opisania, jak pracownik będzie otrzymywał zapłatę. Metody płatności są mapowane do systemu Dayforce i w razie potrzeby tłumaczone na akceptowane wartości podczas integracji.

W poniższej tabeli przedstawiono mapowanie metod płatności do usługi Dayforce.

| Zasoby ludzkie             | Dayforce                  |
|--------------------|---------------------------|
| Kasa               | Kasa                      |
| Płatność elektroniczna | Przenoszenie                  |
| Sprawdzanie              | Czek                    |
| Przekaz bankowy         | *Nieobsługiwane w Meksyku* |
| Inna              | *Nieobsługiwane w Meksyku* |

### <a name="bank-account-type"></a>Typ konta bankowego

Typy kont bankowych są wykorzystywane w płatnościach elektronicznych dla pracowników. Typy kont bankowych są mapowane do systemu Dayforce jako informacje o koncie do przelewów. Typy kont bankowych są w razie potrzeby tłumaczone na akceptowane wartości podczas integracji.

| Zasoby ludzkie            | Dayforce                  |
|-------------------|---------------------------|
| Konto czekowe  | CheckingAccount           |
| Konto listy płac   | PayrollAccount            |
| Konto oszczędnościowe   | *Nieobsługiwane w Meksyku* |
| Konto BankGirot | *Nieobsługiwane w Meksyku* |
| Konto PlusGirot | *Nieobsługiwane w Meksyku* |

### <a name="earning-codes"></a>Kody zarobków

Kody zarobków jednoznacznie identyfikują każdy rodzaj dochodów, które otrzymują pracownicy. Kody mają różne parametry związane z zarobkami, takie jak reguły księgowania, przepisy podatkowe, wymagania dotyczące raportowania i możliwość zwiększania wartości brutto. W razie ustawienia nieobsługiwanej częstotliwości domyślnie w obliczeniu będzie używana częstotliwość **Każda wypłata**.

#### <a name="supported-frequencies"></a>Obsługiwane częstotliwości

- Wszyscy
- EVERYPAY
- EACHPAYPERIOD
- EVRYOTHRPAYODD
- EVRYOTHRPAYEVN
- 1OFMTH
- LASTOFMTH
- 2OFMTH
- 3OFMTH
- 4OFMTH
- 5OFMTH
- 1N2OFMTH
- 3N4OFMTH
- 1N3OFMTH
- 1N4OFMTH
- 2N3OFMTH
- 2N4OFMTH
- 1N2N3OFMTH
- 1N2N4OFMTH
- 1N3N4OFMTH
- 2N3N4OFMTH
- 1N2N3N4OFMTH – 1N2N3N4OFMTH
- 2N3N4N5OFMth – 2N3N4N5OFMth
- 1OFQTR – 1OFQTR
- LASTOFQTR – LASTOFQTR
- LASTMTHOFQTR – LASTMTHOFQTR
- 1OFYEAR – 1OFYEAR
- LASTOFYEAR – LASTOFYEAR
- NOVNDECOFYEAR – NOVNDECOFYEAR

### <a name="addresses"></a>Adresy

Identyfikacja określonych kodów kraju lub regionu, województwa i powiatu (gminy) wymaga określonych formatów, które potrafi rozpoznać system Dayforce oraz dostawcy wewnątrz krajów/regionów. Co prawda format nazw miejscowości jest elastyczny, ale każda miejscowość musi być skojarzona z województwem.

| Zasoby ludzkie              | Dayforce              |
|---------------------|-----------------------|
| Kraj/region      | Kod kraju          |
| Kod pocztowy     | Kod pocztowy           |
| Stanowy               | Kod województwa            |
| Miejscowość                | Miejscowość                  |
| Powiat              | Powiat (gmina) |
| Ulica              | Wiersz adresu 1        |
| Numer budynku       | Wiersz adresu 2        |
| Dodatkowe określenie budynku | Wiersz adresu 5        |

### <a name="passport-number"></a>Numer paszportu

Pracownicy mogą podać informacje z paszportów. Te informacje mają typ identyfikacji **Paszport** i są integrowane z systemem Dayforce w ramach danych pracowników specyficznych dla Meksyku.

- Typ identyfikacji = „Paszport”
- Data wystawienia
- Data ważności

Pracownicy mogą zadeklarować wiele numerów identyfikacyjnych typu **Paszport**. Jednak tylko obecnie aktywny wpis paszportu jest integrowany z usługą Dayforce. Jeśli wszystkie wpisy paszportów wygasły, z systemem Dayforce zostanie zintegrowany ostatnio wystawiony paszport.

