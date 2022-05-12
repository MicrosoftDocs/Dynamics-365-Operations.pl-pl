---
title: Kody kreskowe GS1
description: W tym temacie opisano sposób konfigurowania kodów kreskowych GS1 i kodów QR, tak aby w magazynie mogły być skanowane etykiety.
author: Mirzaab
ms.date: 03/21/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.25
ms.openlocfilehash: ea928bc8a020035adb36ae2e7873c656e8c3985d
ms.sourcegitcommit: 1050e58e621d9a0454895ed07c286936f8c03320
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/21/2022
ms.locfileid: "8625286"
---
# <a name="gs1-bar-codes"></a>Kody kreskowe GS1

[!include [banner](../includes/banner.md)]

Pracownicy magazynu często muszą wykonywać kilka zadań, gdy używają skanera w urządzeniu przenośnym do rejestrowania ruchów towaru, palety lub kontenera. Te zadania mogą obejmować zarówno skanowanie kodów kreskowych, jak i ręczne wprowadzanie informacji na urządzeniu przenośnym. W kodach kreskowych jest używany format specyficzny dla firmy, który definiuje się w firmie i zarządza za pomocą rozwiązania Microsoft Dynamics 365 Supply Chain Management.

Formaty kodu kreskowego GS1 etykiet wysyłkowych zostały opracowane w celu zapewnienia globalnego standardu wymiany danych między firmami. Są one dostępne zarówno w symbolach liniowych (1D) (formaty kodów kreskowych), takich jak GS1-128, jak i w symbolach 2D, takich jak kody GS1 DataMatrix i GS1 QR. Kody kreskowe GS1 nie tylko kodują dane, ale także umożliwiają korzystanie z predefiniowanej listy *identyfikatorów zastosowania* w celu określenia znaczenia tych danych. Standard GS1 definiuje format danych oraz różne rodzaje danych, które mogą być używane do zakodowania. W przeciwieństwie do starszych standardów kodów kreskowych, kody kreskowe GS1 mogą zawierać wiele elementów danych. Dlatego zeskanowanie jednego kodu kreskowego umożliwia odczytanie informacji o produkcie różnych typów, takich jak data partii i data ważności.

Obsługa formatu GS1 w module Supply Chain Management upraszcza proces skanowania w magazynach, w których palety i kontenery są oznaczone etykietami z kodami kreskowymi w formacie GS1. Pracownicy magazynu mogą odczytać wszystkie wymagane informacje, skanując jeden kod kreskowy GS1. Dzięki wyeliminowaniu potrzeby wielokrotnego skanowania i/lub ręcznego wprowadzania informacji kody kreskowe GS1 pomagają skrócić czas związany z zadaniami. Pomagają one jednocześnie zwiększyć dokładność.

Menedżerowie logistyki muszą skonfigurować wymaganą listę identyfikatorów aplikacji i skojarzyć każdy z nich z odpowiednimi opcjami menu w urządzeniu przenośnym. Identyfikatory aplikacji mogą być następnie używane w różnych magazynach jako globalne ustawienia do celów przenoszenia i pakowania. W związku z tym wszystkie etykiety wysyłkowe przybierają ujednoliconą formę.

Jeśli nie podano inaczej, termin *kod kreskowy* w odniesieniu zarówno do liniowych (1D), jak i dwuwymiarowych kodów kreskowych.

## <a name="the-gs1-bar-code-format"></a>Format kodu słupkowego GS1

Specyfikacje ogólne GS1 określają symbole, które mogą być używane dla kodów kreskowych GS1, oraz sposób zakodowania danych w kodzie kreskowym. Ta sekcja zawiera krótkie wprowadzenie do tego tematu. Aby uzyskać szczegółowe informacje, zobacz ogólne [specyfikacje GS1](https://www.gs1.org/docs/barcodes/GS1_General_Specifications.pdf), które są publikowane przez GS1. Dokument specyfikacji GS1 jest regularnie aktualizowany, a zawarte w nim informacje są na bieżąco aktualizowane za pomocą wersji 22.0 specyfikacji ogólnych GS1.

Kody kreskowe GS1 używają następujących symboli:

- **Liniowe lub 1D** — kody kreskowe GS1-128 i GS1 DataBar
- **Kody kreskowe 2D** — GS1 DataMatrix, GS1 Kod KRESKOWY i GS1 Dotcode

Należy zauważyć, że istnieją specjalne uwagi dotyczące GS1 w GS1-128, która jest specjalną sprawą zwykłego liniowego kodu kreskowych Code-128, GS1 DataMatrix i kodu GS1 HTML. Różnica między wersją GS1 a wersją innych niż GS1 stanowi obecność znaku specjalnego (FNC1) jako pierwszego znaku w danych kodu słupkowego. Obecność znaku FNC1 wskazuje, że dane w kodzie pocztowym powinny być interpretowane zgodnie ze specyfikacją GS1.

Dane w samym kodzie słupkowym składają się z wielu elementów danych, z których każdy jest identyfikowany przez identyfikator aplikacji na początku pola. Zazwyczaj dane są także prezentowane pod kodem pocztowym w czytelnym dla ludzi formacie, gdzie identyfikator aplikacji jest wyświetlany w nawiasie. Oto przykład: `(01) 09521101530001 (17) 210119 (10) AB-123`. Ten kod pocztowy zawiera trzy elementy:

- **Identyfikator zgłoszenia 01** – Globalny numer GTIN towaru handlowego GS1.
- **Identyfikator zgłoszenia 17** — data ważności.
- **Identyfikator zgłoszenia 10** — numer partii.

W przypadku każdego elementu dane mogą mieć wstępnie zdefiniowaną długość lub zmienną długość. Istnieje stała lista identyfikatorów aplikacji o wstępnie zdefiniowanych długościach. Wszystkie inne identyfikatory aplikacji mają zmienną długość, a lista identyfikatorów aplikacji GS1 określa maksymalną długość i format danych. Na przykład identyfikator zastosowania 01 ma predefiniowaną długość 16 znaków (dwa dla samego identyfikatora zastosowania, a następnie 14 dla numeru GTIN), a identyfikator zastosowania 17 ma predefiniowaną długość ośmiu znaków (dwa dla samego identyfikatora zastosowania, a następnie sześć dla daty). Jednak identyfikator aplikacji 10 ma dwa numery dla samego identyfikatora zgłoszenia, a następnie do 20 znaków alfanumerycznych.

Jeśli element jest elementem o zmiennej długości, należy użyć znaku separatora, jeśli elementy są ze sobą połączone. Separatorem tym może być specjalny znak FNC1 lub znak separatora grupy (niedrukowalny znak o kodzie ASCII 29 i kodzie szesnastkowym 1D). Separator nie powinien być używany po ostatnim elemencie. Chociaż separator nie powinien być również używany po elementach o wstępnie zdefiniowanej długości, jego obecność nie jest błędem krytycznym.

W danych kodu kreskowego z poprzedniego przykładu, który zawiera identyfikatory aplikacji 01, 17 i 10, dane w kodzie Code-128, QR Code lub symbolu DataMatrix będą zakodowane jako `<FNC1>`**`01`**`09521101530001`**`17`**`210119`**`10`**`AB-123` (identyfikatory aplikacji są zaznaczone pogrubioną czcionką). Najlepiej, aby każdy element o zmiennej długości był umieszczany na końcu, aby wyeliminować dodatkowe znaki separatora grupy. Jednak kod pocztowy może mieć również inną kolejność elementów, gdzie separator jest obowiązkowy. Oto przykład: `<FNC1>`**`01`**`09521101530001`**`10`**`AB-123<GS>`**`17`**`210119`.

### <a name="dates-and-decimal-numbers"></a>Daty i liczby dziesiętne

Daty są zawsze reprezentowane w formacie *YYMMDD*, gdzie wiek roku jest określony na podstawie specyfikacji GS1. Można przedstawiać tylko daty od 49 lat w przeszłości do 50 lat w przyszłości (w odniesieniu do bieżącego roku).

Niektóre elementy danych zawierają liczby dziesiętne. Na przykład identyfikatory zastosowań 3100, 3101, ... 3105 reprezentują masę netto w kilogramach. Ponieważ identyfikatory tych aplikacji mają wstępnie zdefiniowaną długość 10, dla ilości jest dostępnych sześć numerów. Pozycja separatora dziesiętnego jest określana przez ostatni numer identyfikatora zgłoszenia. W związku z tym ta rodzina identyfikatorów aplikacji może być również przedstawiana jako *310n*. Ponieważ standard GS1 określa, że po lewej stronie kropki dziesiętnej zawsze musi znajdować się co najmniej jedna cyfra, dopuszcza się maksymalnie pięć miejsc po przecinku.

Oto kilka przykładów, na których pokazano, jak numer *123456* będzie interpretowany przez różne identyfikatory aplikacji (pogrubione):

- **`3100`**`123456` &rarr; 123456 (liczba całkowita)
- **`3101`**`123456` &rarr; 12345,6 (jedno miejsce dziesiętne)
- **`3102`**`123456` &rarr; 1234,56 (dwa miejsca dziesiętne)
- **`3103`**`123456` &rarr; 123,456 (trzy miejsca dziesiętne)
- **`3104`**`123456` &rarr; 12,3456 (cztery miejsca po przecinku)
- **`3105`**`123456` &rarr; 1,23456 (pięć miejsc po przecinku)

## <a name="scanning-gs1-bar-codes-in-supply-chain-management"></a>Skanowanie kodów kreskowych GS1 w Supply Chain Management

Aby zeskanować kody kreskowe GS1, pracownicy magazynu używają skanera wbudowanego w urządzenie przenośne lub połączonego z jego urządzeniem przenośnym. Następnie skaner przesyła zeskanowany kod kreskowy do aplikacji mobilnej Warehouse Management w serii zdarzeń klawiaturowych. Ten tryb pracy jest również znany jako *podłączany do klawiatury* lub *podłączany*. Aplikacja mobilna następnie wysyła odebrany tekst w stanie, w stanie w stanie, w stanie w stanie, w ile jest do Supply Chain Management. Gdy system odbiera dane wejściowe, najpierw określa, czy dane rozpoczynają się od jednego ze skonfigurowanych prefiksów wskazujących, że dane są w rzeczywistości kodem słupkowym GS1 ( [zobacz sekcję Ustaw globalne opcje GS1](#set-gs1-options)). Jeśli zeskanowane dane zaczynają się od jednego z tych prefiksów, system używa programu analizy GS1 do analizowania danych i wyodrębniania poszczególnych elementów danych zgodnie z ich identyfikatorami aplikacji. Po analizie danych bieżące pole wejściowe lub wiele pól zostanie wypełnionych zeskanowanych danymi.

### <a name="configuration-of-bar-code-scanner-hardware-and-software"></a>Konfiguracja sprzętu i oprogramowania skanera kodów kreskowych

Aby moduł Supply Chain Management poprawnie rozpoznawał i dekodował kody kreskowe GS1, skaner sprzętu lub oprogramowanie pomocy technicznej musi być skonfigurowane do wykonywania następujących akcji:

- Umożliwia dodanie prefiksu do zeskanowanych kodów kreskowych, dzięki czemu system rozpozna kod kreskowy GS1.
- Umożliwia konwersję niedrukowalnego znaku separatora grupy ASCII (kod ASCII 29 lub kod szesnastkowym 1D) na znak drukowany, na przykładtild (~).

Chociaż do zeskanowanego kodu kreskowego można dodać dowolny prefiks, jedną z opcji jest dodanie identyfikatora symboliki ISO/IEC 15424, znanego również jako *identyfikator AIM*. Ten trzyznakowy identyfikator zaczyna się od `]`, ma jeden znak identyfikujący stosowaną symbolikę, a następnie liczbę, która jest używana jako kolejny modyfikator. Na przykład, identyfikator AIM `]C1` określa kod kreskowy Code 128 (ze względu na znak `C`), a modyfikator `1` określa, że na pierwszej pozycji danych znajduje się znak FNC1. Z drugiej strony `]C0` to kod słupkowy Code 128, który ma dowolny inny znak jako pierwszy znak danych.

Pięć następujących identyfikatorów symboli odpowiada kodom kreskowym GS1, które mają elementy identyfikatora aplikacji:

- `]C1` — kod 128 (`C`) z znakiem FNC1 na pierwszej pozycji (`1`) innym niż GS1-128.
- `]e0` — pasek danych GS1.
- `]d2` — DataMatrix (`d`) z ECC 200 i FNC1 na pierwszej pozycji (`2`), zwanej również GS1 DataMatrix.
- `]Q3` — QR Code (`Q`) Symbol Model 2 z FNC1 na pierwszej pozycji (`3`), znany również jako GS1 QR Code.
- `]J1` — kod GS1 DotCode.

W przypadku używania tych identyfikatorów zgodność z kodami kreskowymi innych niż GS1 wymaga skonfigurowania skanerów lub oprogramowania do skanowania w celu usunięcia wszelkich identyfikatorów, które nie odpowiadają identyfikatorom GS1. Na przykład w przypadku skanowania "normalnego" kodu kreskowego Code 39 zostanie dodany prefiks `]A0`. Ponieważ system nie zrozumiał tego prefiksu jako jednego z prefiksów GS1, zinterpretuje go jako dane i przysyła nieoczekiwane wyniki.

> [!NOTE]
> Dla wygody wersja 2.0.17.0 i nowsza aplikacja mobilna Warehouse Management spowoduje usunięcie wszystkich prefiksów AIM, które nie zostały uwzględnione na poprzedniej liście. Takie działanie dotyczy przypadków, w których można skonfigurować skaner w celu dodania prefiksu AIM, ale nie usuwania niechcianych prefiksów.

### <a name="single-and-multiple-field-scanning"></a>Skanowanie jednego i wielu pól

Po analizie danych z kodu słupkowego zostaną one wczytyne do formantów przepływu urządzenia przenośnego. Są dwie metody przetwarzania z kolei:

- **Skanowanie jednego pola** — ta metoda wypełnia tylko pole, w które został zeskanowany kod kreskowy. Na przykład po zeskanowaniu kodu kreskowego `<FNC1>`**`01`**`09521101530001`**`17`**`210119`**`10`**`AB-123`, gdy kursor znajduje się w polu **Pozycja**, w polu tym zostanie wprowadzony numer GTIN `09521101530001` z kodu kreskowego. W przypadku zeskanowania tego samego kodu kreskowego, gdy kursor znajduje się w polu **Identyfikator zadania wsadowego**, zostanie wprowadzony numer partii `AB-123` z kodu kreskowego. Ten tryb działa dla wszystkich pól we wszystkich przepływach i wymaga jedynie skonfigurowania ogólnej konfiguracji GS1. Jeśli kod kreskowy zawiera wiele elementów, należy go zeskanować wiele razy, ponieważ tylko jedna część kodu kreskowych na raz zostanie wprowadzona do przepływu urządzenia przenośnego. To zachowanie jest kontrolowane przez konfigurację ogólną GS1, [jak opisano w sekcji Ustanawianie ogólnej konfiguracji GS1](#generic-gs1-setup).
- **Skanowanie wielu pól** — Ta metoda wypełnia wiele pól, gdy jest skanowany jeden kod kreskowy, przez wypychanie dodatkowych danych do stanu przepływu urządzenia przenośnego. Na przykład polityka jest skonfigurowana tak, aby identyfikator aplikacji 01 był umieszczany w kontrolce `ItemId`, a identyfikator aplikacji 10 w polu `InventBatchId`. W takim przypadku podczas skanowania kodu słupkowego `<FNC1>`**`01`**`09521101530001`**`17`**`210119`**`10`**`AB-123`, dane obu zmiennych zostaną jednocześnie wypychane. W związku z tym system nie będzie monitował o numer towaru i/lub partii w przepływie. To zachowanie jest kontrolowane przez zasady GS1 połączone z elementami menu, [co opisano w sekcji Konfigurowanie zasad GS1 jako elementów menu urządzenia przenośnego](#policies-for-menus).

> [!WARNING]
> Domyślne zasady GS1 zostały przetestowane, aby działać bez nieoczekiwanego działania. Dostosowanie zasad GS1 połączonych z elementami menu może spowodować nieoczekiwane zachowanie, ponieważ przepływ może nie oczekiwać pewnych danych, które będą dostępne w danym momencie.

## <a name="turn-on-the-gs1-feature"></a>Włączanie funkcji GS1

Aby używać tej funkcji, należy ją włączyć w systemie. Administratorzy mogą skorzystać z ustawień [zarządzania funkcją](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby sprawdzić stan funkcji i włączyć ją. W obszarze roboczym **Zarządzanie funkcjami** ta funkcja widnieje jako:

- **Moduł:** *Zarządzanie magazynem*
- **Nazwa funkcji:** *skanowanie kodów kreskowych GS1*

### <a name="turn-on-the-enhanced-parser-for-gs1-barcodes-feature"></a>Włącz funkcję Enhanced Parser dla kodów kreskowych GS1

W przypadku korzystania z kodów kreskowych GS1 zaleca się również włączenie funkcji *Enhanced Parser dla kodów kreskowych GS1*. Ta funkcja umożliwia poprawioną implementację aplikacji GS1 bar parser. Wprowadzono w nim następujące usprawnienia:

- Następuje zgodnie z algorytmem specyfikacji ogólnej GS1 na podstawie analizy danych symbolu i sprawdza poprawność danych na symbolach zgodnie ze specyfikacją.
- Nie jest wymagane konfigurowanie **maksymalnej długości wartości identyfikatora** i stosowanie najdłuższego uzgadniania prefiksów ze skonfigurowanych identyfikatorów aplikacji.
- Pozwala łatwiej skonfigurować identyfikatory aplikacji dziesiętnych, używając litery *n* w celu dopasowania do dowolnej liczby. Na przykład można skonfigurować tylko jeden identyfikator aplikacji (*310n*) zamiast osobnych identyfikatorów aplikacji (*3101*, *3102*, *3103* itd.).
- Poprawia to problem, w którym niepoprawnie zakodowane dane są interpretowane jako dane pola.
- Jest to osobna klasa, która może być ponownie użyta w innych kontekstach i umożliwia użycie punktu możliwości rozszerzania do operowanie zeskanowanych danych przed wypełnieniami pól przepływu.

## <a name="set-up-global-gs1-options"></a><a name="set-gs1-options"></a>Konfigurowanie globalnych opcji GS1

Strona **Parametry zarządzania magazynem** zawiera kilka ustawień, które ustalają globalne opcje GS1.

Procedura konfigurowania globalnych opcji GS1 jest następująca.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Parametry zarządzania magazynem**.
1. Na skróconej karcie **Kody kreskowe** ustaw następujące pola:

    - **Znak FNC1**, **znak Datamatrix** i **znak kodu QR** — umożliwia określanie znaków, które powinny być interpretowane jako prefiks dla każdego typu kodu kreskowygo GS1.
    - **Separator grupy** — umożliwia określenie znaku, który zastępuje znak separatora grupy ASCII.
    - **Maksymalna długość identyfikatora** — umożliwia określenie maksymalnej dozwolonej liczby znaków identyfikatora aplikacji. To pole nie jest wymagane, jeśli w *systemie jest włączona funkcja Enhanced GS1 Parser*.

> [!NOTE]
> Prefiksy informują system, że kod kreskowy jest zakodowany zgodnie ze standardem GS1. Mogą być używane maksymalnie trzy prefiksy (**Znak FNC1**, **Znak Datamatrix** i **Znak kodu QR**) równocześnie i do różnych celów.

## <a name="gs1-application-identifiers"></a>Identyfikatory aplikacji GS1

Formaty GS1 nie tylko kodują dane, ale pozwalają także na używanie wstępnie zdefiniowanej listy identyfikatorów aplikacji w celu zdefiniowania znaczenia danych. Menedżerowie logistyki muszą skonfigurować wymaganą listę identyfikatorów aplikacji i skojarzyć każdy z nich z odpowiednimi opcjami menu w urządzeniu przenośnym. Identyfikatory mogą być następnie używane w różnych magazynach jako globalne ustawienia do celów przenoszenia i pakowania. W związku z tym wszystkie etykiety wysyłkowe przybierają ujednoliconą formę.

System używa danych, w szczególności wstępnie zdefiniowanych identyfikatorów aplikacji, w celu ustalenia reguł, które powinny być stosowane do odpowiednich sztuk zeskanowanych informacji.

Każdy identyfikator aplikacji wysyła do systemu sygnał, że kolejne znaki w zeskanowanym kodzie kreskowym powinny być traktowane jako blok zaszyfrowanych informacji. Konfiguracja identyfikatorów aplikacji definiuje sposób, w jaki system powinien zinterpretować kod kreskowy i zapisać go jako wartość w systemie.

Menedżerowie logistyki mogą używać standardowych międzynarodowych identyfikatorów aplikacji i/lub tworzyć własne.

### <a name="load-the-standard-application-identifiers"></a>Ładowanie standardowych identyfikatorów aplikacji

Aby szybko rozpocząć, można załadować listę wspólnych międzynarodowych identyfikatorów aplikacji. Później listę można rozszerzać lub edytować stosownie do potrzeb.

Procedura ładowania standardowych identyfikatorów aplikacji jest następująca.

1. Wybierz opcje **Zarządzanie magazynem \> Konfiguracja \> GS1 \> Identyfikatory aplikacji GS1**.
1. W okienku akcji wybierz **Utwórz konfigurację domyślną**.

> [!WARNING]
> Polecenie **Utwórz konfigurację domyślną** powoduje usunięcie wszystkich aktualnie zdefiniowanych identyfikatorów aplikacji i zastąpienie ich listą standardową. Jednak po załadowaniu konfiguracji domyślnej można dostosować listę w wymagany sposób.

### <a name="set-up-custom-application-identifiers"></a>Konfigurowanie niestandardowych identyfikatorów aplikacji

Jeśli niektóre lub wszystkie identyfikatory aplikacji używane przez firmę różnią się od standardowego zestawu, można utworzyć własne kody od początku lub dostosować zestaw standardowy stosownie do potrzeb.

Procedura konfigurowania i dostosowywania własnych identyfikatorów aplikacji GS1 jest następująca.

1. Wybierz opcje **Zarządzanie magazynem \> Konfiguracja \> GS1 \> Identyfikatory aplikacji GS1**.
1. Wykonaj jeden z następujących kroków:

    - Aby utworzyć nowy identyfikator: w okienku akcji wybierz pozycję **Nowy**.
    - Aby zmodyfikować istniejący identyfikator: wybierz identyfikator, a następnie w okienku akcji wybierz pozycję **Edytuj**.

1. Ustaw następujące pola nowego lub wybranego identyfikatora:

    - **Identyfikator aplikacji** — należy wprowadzić kod identyfikacyjny tego identyfikatora aplikacji. Zazwyczaj kod jest dwucyfrową liczbą całkowitą, ale może być dłuższy. W przypadku wartości dziesiętnych ostatnia cyfra wskazuje liczbę miejsc dziesiętnych. Aby uzyskać więcej informacji, zobacz opis pola wyboru **Dziesiętna** dalej na tej liście. Jeśli jest *włączona funkcja Enhanced Parser dla kodów kreskowych GS1*, można utworzyć jeden identyfikator aplikacji dla wszystkich wariantów miejsc dziesiętnych, *używając litery n* jako ostatniego znaku w identyfikatorze aplikacji. Na przykład można skonfigurować tylko jeden identyfikator aplikacji (*310n*) zamiast osobnego identyfikatora aplikacji dla każdej liczby miejsc po przecinku (*3101*, *3102*, *3103* itd.).
    - **Opis** — umożliwia wprowadzanie krótkiego opisu identyfikatora.
    - **Stała długość** — to pole wyboru należy zaznaczyć, jeśli wartości skanowane przy użyciu tego identyfikatora aplikacji mają stałą liczbę znaków. Wyczyść to pole wyboru, jeśli długość wartości jest zmienna. W takim przypadku należy wskazać koniec wartości za pomocą znaku separatora grupy określonego na stronie **Parametry zarządzania magazynem**.
    - **Długość** — umożliwia wprowadzenie maksymalnej liczby znaków, które mogą pojawiać się w wartościach skanowanych przy użyciu tego identyfikatora aplikacji. Jeśli zaznaczono pole wyboru **Stała długość**, oczekiwana jest dokładnie ta liczba znaków.
    - **Typ** — umożliwia wybór typu wartości, która jest skanowana przy użyciu tego identyfikatora aplikacji (*Liczbowa*, *Alfanumeryczna* lub *Data*). Aby uzyskać więcej informacji na temat sposobu reprezentowania dat i numerów w danych kodów barowych, zobacz sekcję [Daty i liczby dziesiętne](#dates-and-decimal-numbers).
    - **Dziesiętna** — to pole wyboru należy zaznaczyć, jeśli wartość zawiera domniemany punkt dziesiętny. Jeśli to pole wyboru jest zaznaczone, system użyje ostatniej cyfry identyfikatora aplikacji do określenia liczby miejsc dziesiętnych. Aby uzyskać więcej informacji na temat sposobu reprezentowania dat i numerów w danych kodów barowych, zobacz sekcję [Daty i liczby dziesiętne](#dates-and-decimal-numbers).

> [!WARNING]
> Chociaż system zezwoli na ustawienie pola wyboru **Stała długość** dla dowolnego identyfikatora aplikacji, należy go używać tylko dla podzestawu identyfikatorów aplikacji, które mają wstępnie zdefiniowaną długość według specyfikacji ogólnych GS1. Rozszerzony program GS1 Parser już zawiera listę wszystkich identyfikatorów aplikacji o wstępnie zdefiniowanych długościach.

> [!NOTE]
> Wartość **separatora Grupa określona** na **stronie Parametry zarządzania magazynem** jest opcjonalna, jeśli wartość, po której następuje identyfikator aplikacji, ma stałą długość.

## <a name="establish-the-generic-gs1-setup"></a><a name="generic-gs1-setup"></a>Ustanawianie ogólnej konfiguracji GS1

Ogólna konfiguracja GS1 tworzy zbiór wspólnych mapowań. Mapowania te dopasowują poszczególne pola wejściowe w aplikacji mobilnej do identyfikatora aplikacji, który określa sposób, w jaki wartości z zeskanowanych kodów kreskowych powinny być interpretowane i przechowywane w tym polu. Domyślnie te ustawienia dotyczą wszystkich skanowań dla wszystkich opcji menu urządzenia przenośnego. Można je jednak zmienić w przypadku jednego lub większej liczby pól za pomocą zasady GS1 przypisanej do określonej opcji menu.

Ogólna konfiguracja GS1 pozwala na skanowanie tylko jednej wartości na raz. Dlatego aby załadować wiele wartości pól z pojedynczego skanowania, należy skonfigurować zasady GS1 dla odpowiednich opcji menu.

Więcej informacji o zasadach GS1 znajdziesz w następnej części.

### <a name="load-the-standard-generic-gs1-setup"></a>Ładowanie standardowej ogólnej konfiguracji GS1

Strona **Ogólna konfiguracja GS1** umożliwia załadowanie standardowego zestawu mapowań między polami urządzenia przenośnego a standardowymi identyfikatorami aplikacji utworzonymi według domyślnej konfiguracji.

Aby ustanowić ogólną konfigurację GS1, wybierz opcje **Zarządzanie magazynem \> Konfiguracja \> GS1 \> Konfiguracja ogólna GS1**. Następnie wybierz opcję **Utwórz konfigurację domyślną**, aby automatycznie przypisać odpowiedni identyfikator aplikacji do poszczególnych pól, które są zwykle używane przez opcje menu urządzenia przenośnego.

> [!WARNING]
> Jeśli jakakolwiek ogólna konfiguracja GS1 już istnieje, polecenie **Utwórz konfigurację domyślną** całkowicie ją usuwa i ładuje konfigurację standardową.

### <a name="customize-the-standard-generic-gs1-setup"></a>Dostosowywanie standardowej ogólnej konfiguracji GS1

Procedura dostosowywania ogólnej konfiguracji GS1 jest następująca.

1. Wybierz opcje **Zarządzanie magazynem \> Konfiguracja \> GS1 \> Ogólna konfiguracja GS1**.
1. Wykonaj jeden z następujących kroków:

    - Aby utworzyć nowe mapowanie: w okienku akcji wybierz opcję **Nowa**.
    - Aby zmodyfikować istniejące mapowanie: wybierz mapowanie, a następnie w okienku akcji wybierz pozycję **Edytuj**.

1. Ustaw następujące pola nowego lub wybranego mapowania:

    - **Pole** — umożliwia wybór lub wprowadzenie pola wejściowego aplikacji mobilnej, do którego ma być przypisana wartość przychodząca. Ta wartość nie jest nazwą wyświetlaną widoczną dla pracowników. Jest to natomiast nazwa klucza przypisana do pola w kodzie źródłowym. Konfiguracja domyślna stanowi zbiór pól, które mogą być przydatne, oraz zawiera intuicyjne nazwy klucza poszczególnych pól i pasującej zaprogramowanej funkcji. W pewnych sytuacjach warto porozmawiać z deweloperami, aby ustalić poprawne opcje w danej implementacji.
    - **Identyfikator aplikacji** — umożliwia wybór odpowiedniego identyfikatora, zgodnie z definicją na stronie **Identyfikatory aplikacji GS1**. Identyfikator określa sposób, w jaki kod będzie interpretowany i przechowywany jako wartość nazwanego pola. Po wybraniu identyfikatora aplikacji w polu **Opis** zostanie pokazany jego opis.

## <a name="set-up-gs1-policies-to-be-to-mobile-device-menu-items"></a><a name="policies-for-menus"></a>Skonfiguruj zasady GS1 tak, aby były dostępne w menu urządzeń przenośnych

Standard GS1 umożliwia pracownikom załadowanie kilku wartości jednorazowo podczas skanowania jednego kodu kreskowego. W tym celu menedżerowie logistyki muszą skonfigurować zasady GS1, które informują system, jak interpretować kody kreskowe o wielu wartościach. Później można przypisać zasady do opcji menu urządzenia przenośnego, aby kontrolować, jak kod kreskowy będzie interpretowany podczas skanowania go przez pracowników korzystających z danej opcji menu.

Jeśli do opcji menu nie jest przypisana żadna zasada GS1, system może przechwytywać tylko pojedynczą wartość. Ta wartość jest stosowana do danych wejściowych aplikacji mobilnej wybranych przez pracownika podczas skanowania, zgodnie z ogólną konfiguracją GS1. Jeśli do opcji menu jest przypisana zasada GS1, w celu mapowania pierwszej wartości kodu kreskowego na wybrane pole system nadal używa ogólnej konfiguracji GS1. Może jednak przechwytywać dodatkowe wartości pól, zgodnie z obowiązującą zasadą.

### <a name="load-the-standard-specific-gs1-policies"></a>Ładowanie standardowych zasad GS1

Aby szybko rozpocząć, można załadować zestaw zasad GS1. Później zasady można rozszerzać lub edytować stosownie do potrzeb.

Procedura ładowania standardowych identyfikatorów aplikacji jest następująca.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> GS1 \> Zasady GS1**.
1. W okienku akcji wybierz **Utwórz konfigurację domyślną**.

> [!WARNING]
> Polecenie **Utwórz konfigurację domyślną** powoduje usunięcie wszystkich aktualnie zdefiniowanych zasad i zastąpienie ich standardowym zestawem zasad. Jednak po załadowaniu konfiguracji domyślnej można dostosować zasady w wymagany sposób.

### <a name="set-up-custom-specific-gs1-policies"></a>Konfigurowanie niestandardowych indywidualnych zasad GS1

> [!WARNING]
> Niektóre zasady GS1 mogą nie działać z każdym przepływem dla urządzeń przenośnych, których używasz. Konfigurując niestandardowe zasady GS1, należy przetestować przepływ urządzenia przenośnego, używając różnych fragmentów informacji, które są skanowane w różnych punktach przepływu. W ten sposób można określić, czy przepływ działa zgodnie z oczekiwaniami.

Procedura konfigurowania i dostosowywania zasad GS1 jest następująca.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> GS1 \> Zasady GS1**.
1. Wykonaj jeden z następujących kroków:

    - Aby utworzyć nowe zasady: w okienku akcji wybierz opcję **Nowe**.
    - Aby zmodyfikować istniejące zasady: wybierz zasady w okienku listy.

1. W nagłówku nowych lub wybranych zasad ustaw następujące pola:

    - **Nazwa zasad** — umożliwia wprowadzenie nazwy zasad.
    - **Opis** — umożliwia wprowadzanie krótkiego opisu zasad.

1. Na skróconej karcie poniżej nagłówka mapuj nazwy pól na identyfikatory aplikacji, zgodnie z potrzebami bieżących zasad. Użyj następujących przycisków na pasku narzędzi, aby dodawać i usuwać wiersze według potrzeb. Dla każdego wiersza ustaw następujące pola:

    - **Pole** — umożliwia wybór lub wprowadzenie pola wejściowego aplikacji mobilnej, do którego ma być przypisana wartość przychodząca. Ta wartość nie jest nazwą wyświetlaną widoczną dla pracowników. Jest to natomiast nazwa klucza przypisana do pola w kodzie źródłowym. Konfiguracja domyślna stanowi zbiór pól, które mogą być przydatne, oraz zawiera intuicyjne nazwy klucza poszczególnych pól i pasującej zaprogramowanej funkcji. W pewnych sytuacjach warto porozmawiać z deweloperami, aby ustalić poprawne opcje w danej implementacji.
    - **Identyfikator aplikacji** — umożliwia wybór odpowiedniego identyfikatora, zgodnie z definicją na stronie **Identyfikatory aplikacji GS1**. Identyfikator określa sposób, w jaki kod będzie interpretowany i przechowywany jako wartość nazwanego pola. Po wybraniu identyfikatora aplikacji w polu **Opis** zostanie pokazany jego opis.
    - **Sortowanie** — każdy kod kreskowy o wielu wartościach zawiera serię identyfikatorów aplikacji, po których następuje wartość. Odpowiednie zasady GS1 określają, który identyfikator aplikacji jest mapowany na poszczególne pola bazy danych. Jeśli jednak kod kreskowy używa tego samego identyfikatora aplikacji więcej niż jeden raz, system używa kolejności, w jakim identyfikatory aplikacji pojawiają się w kodzie, w celu ich mapowania na pola. W przypadku wierszy, które mają identyfikator aplikacji z jednym lub większą liczbą innych wierszy, użyj tego pola, aby ustalić kolejność, w których są przetwarzane pasujące wiersze. Najpierw zostanie przetworzony wiersz z najmniejszą wartością sortowania.

> [!NOTE]
> W przypadku kodów kreskowych, które zawierają więcej niż jeden identyczny identyfikator aplikacji, *musisz* użyć pola **Sortowanie** w celu ustalenia kolejności pól.

## <a name="assign-gs1-policies-to-mobile-device-menu-items"></a>Przypisywanie zasad GS1 do opcji menu urządzenia przenośnego

Domyślnie wszystkie opcje menu urządzenia przenośnego zawierają pola wejściowe, w których pracownicy mogą skanować pojedynczą wartość zgodnie z ogólną konfiguracją GS1. Jeśli chcesz, aby pracownicy mogli skanować więcej niż jedną wartość pola w jednym skanowaniu dla dowolnej opcji menu urządzenia przenośnego, musisz przypisać zasady GS1 w następujący sposób.

1. Przejdź do pozycji **Zarządzanie magazynem \> Ustawienia \> Urządzenie przenośne \> Elementy menu urządzenia przenośnego**.
1. Utwórz lub otwórz opcję menu.
1. Na skróconej karcie **Ogólne** ustaw pole **Zasady GS1** na zasady dotyczące opcji menu.

## <a name="gs1-setup-example"></a>Przykład konfiguracji GS1

Przykład ten ma zastosowanie do systemu, w którym opcje GS1 są ustawione w następujący sposób:

- Na stronie **Parametry zarządzania magazynem** są określone następujące ustawienia globalne:

    - **Znak FNC1:** *\]C1*
    - **Separator grup:** *\~*

- Następujące identyfikatory aplikacji na stronie **Identyfikatory aplikacji GS1** mają zastosowanie w tym przykładzie.

    | Identyfikator aplikacji | opis | Stała długość | Długość | Typ | Dziesiętny |
    |---|---|---|---|---|---|
    | 01 | Numer GTIN | Wybrana | 14 | Liczba | Zaakceptowane |
    | 10 | Numer partii | Zaakceptowane | 20 | Alfanumeryczne | Zaakceptowane |
    | 17 | Data ważności | Wybrana | 6 | Data | Zaakceptowane |
    | 30 | Przyjmowana ilość | Zaakceptowane | 8 | Liczba | Zaakceptowane |

- Następujące ustawienia ogólnych zasad GS na stronie **Ogólna konfiguracja GS1** mają zastosowanie w tym przykładzie.

    | Pole | Identyfikator aplikacji | opis |
    |---|---|---|
    | ItemId | 01 | Numer GTIN |

- Na stronie **Zasady GS1** znajdują się zasady, w których w polu **Nazwa zasad** znajduje się wartość *Przyjęcie zakupu*. Te zasady zawierają następujące wiersze.

    | Pole | Identyfikator aplikacji | opis | Sortowanie |
    |---|---|---|---|
    | ExpDate | 17 | Data ważności | 0 |
    | InventBatchId | 10 | Numer partii | 0 |
    | Ilość | 30 | Przyjmowana ilość | 0 |

- Na stronie **Opcje menu urządzenia przenośnego** znajduje się opcja menu o nazwie *Zakupy otrzymane*. W jego polu **Zasady GS1** znajduje się wartość *Przyjęcie zakupu*.

Gdy towary z zamówienia zakupu docierają do magazynu, pracownik wykonuje następujące kroki.

1. Na urządzeniu przenośnym wybierz opcję menu **Przyjęcie zakupu**.
1. Wprowadź numer zamówienia zakupu.
1. Zaznacz pole **Pozycja** i zeskanuj następujący kod kreskowy: `]C10100000012345678~3030~10b1~17220215`.

Ze względu na ustawienia ustalone w tym przykładzie system w następujący sposób analizuje zeskanowany kod kreskowy.

| Klucz pola | Identyfikator aplikacji | Wartość | Banknot |
|---|---|---|---|
| ItemId | 01 | 00000012345678 | Ponieważ pracownik zeskanował pole **Pozycja**, pierwsza wartość z kodu kreskowego jest mapowana na to pole. Mapowanie pochodzi z ogólnej konfiguracji GS1. |
| Ilość | 30 | 30 | Ponieważ więcej niż jedna wartość pola jest odczytywana w jednym skanowaniu, to mapowanie i wszystkie pozostałe mapowania są brane pod uwagę w zasadach GS1 przypisanych do opcji menu **Przyjęcie zakupu**. Ta wartość jest ilością, która została przyjęta. |
| InventBatchId | 10 | b1 | Ta wartość jest identyfikatorem partii. |
| ExpDate | 17 | 220215 | Format daty to RRMMDD. Data ważności to zatem 15 lutego 2022. |

Następnie przyjęcie zostanie zarejestrowane i po jednym skanowaniu zostaną wprowadzone odpowiednie wartości w bazie danych.
