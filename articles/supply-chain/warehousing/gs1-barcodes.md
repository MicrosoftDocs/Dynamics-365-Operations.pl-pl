---
title: Kody kreskowe GS1 i kody QR
description: W tym temacie opisano sposób konfigurowania kodów kreskowych GS1 i kodów QR, tak aby w magazynie mogły być skanowane etykiety.
author: Mirzaab
ms.date: 08/02/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 8f438e18356a6c16cc75bb59153ae7353d984a5a
ms.sourcegitcommit: ecd4c148287892dcd45656f273401315adb2805e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/18/2021
ms.locfileid: "7500337"
---
# <a name="gs1-bar-codes-and-qr-codes"></a>Kody kreskowe GS1 i kody QR

[!include [banner](../includes/banner.md)]

Pracownicy magazynu często muszą wykonywać kilka zadań, gdy używają skanera w urządzeniu przenośnym do rejestrowania ruchów towaru, palety lub kontenera. Te zadania mogą obejmować zarówno skanowanie kodów kreskowych, jak i ręczne wprowadzanie informacji na urządzeniu przenośnym. W kodach kreskowych jest używany format specyficzny dla firmy, który definiuje się w firmie i zarządza za pomocą rozwiązania Microsoft Dynamics 365 Supply Chain Management.

Formaty kodu kreskowego GS1 i kodu QR etykiet wysyłkowych zostały opracowane w celu zapewnienia globalnego standardu wymiany danych między firmami. Formaty GS1 nie tylko kodują dane, ale pozwalają także na używanie wstępnie zdefiniowanej listy *identyfikatorów aplikacji* w celu zdefiniowania znaczenia danych. Standard GS1 definiuje format danych oraz różne rodzaje danych, które mogą być używane do zakodowania. W przeciwieństwie do starszych kodów kreskowych kody kreskowe GS1 mogą mieć wiele elementów danych. Dlatego zeskanowanie jednego kodu kreskowego umożliwia odczytanie informacji o produkcie różnych typów, takich jak data partii i data ważności.

Obsługa formatu GS1 w module Supply Chain Management upraszcza proces skanowania w magazynach, w których palety i kontenery są oznaczone etykietami z kodami w formacie GS1. Pracownicy magazynu mogą odczytać wszystkie wymagane informacje, skanując jeden kod kreskowy GS1. Dzięki wyeliminowaniu potrzeby wielokrotnego skanowania i/lub ręcznego wprowadzania informacji kody kreskowe GS1 pomagają skrócić czas związany z zadaniami. Pomagają one jednocześnie zwiększyć dokładność.

Menedżerowie logistyki muszą skonfigurować wymaganą listę identyfikatorów aplikacji i skojarzyć każdy z nich z odpowiednimi opcjami menu w urządzeniu przenośnym. Identyfikatory aplikacji mogą być następnie używane w różnych magazynach jako globalne ustawienia do celów przenoszenia i pakowania. W związku z tym wszystkie etykiety wysyłkowe przybierają ujednoliconą formę.

Jeśli nie podano inaczej, termin *kod kreskowy* w tym temacie odnosi się zarówno do kodów kreskowych, jak i kodów QR.

## <a name="turn-on-the-gs1-feature"></a>Włączanie funkcji GS1

Aby móc używać tej funkcji, należy ją włączyć w systemie. Administratorzy mogą skorzystać z ustawień [zarządzania funkcją](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby sprawdzić stan funkcji i włączyć ją. W obszarze roboczym **Zarządzanie funkcjami** ta funkcja widnieje jako:

- **Moduł:** *Zarządzanie magazynem*
- **Nazwa funkcji:** *skanowanie kodów kreskowych GS1*

## <a name="set-up-global-gs1-options"></a>Konfigurowanie globalnych opcji GS1

Strona **Parametry zarządzania magazynem** zawiera kilka ustawień, które ustalają globalne opcje GS1.

Procedura konfigurowania globalnych opcji GS1 jest następująca.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Parametry zarządzania magazynem**.
1. Na skróconej karcie **Kody kreskowe** ustaw następujące pola:

    - **Znak FNC1** — umożliwia określanie znaków, które powinny być interpretowane jako prefiks podczas analizowania kodu kreskowego.
    - **Znak Datamatrix** — umożliwia określanie znaków, które powinny być interpretowane jako prefiks podczas analizowania Datamatrix.
    - **Znak kodu QR** — umożliwia określanie znaków, które powinny być interpretowane jako prefiks podczas analizowania kodu QR.
    - **Separator grupy** — umożliwia określenie znaku identyfikującego osobne części kodu kreskowego lub kodu QR.
    - **Maksymalna długość identyfikatora** — umożliwia określenie maksymalnej dozwolonej liczby znaków identyfikatora aplikacji.

> [!NOTE]
> Prefiksy informują system, że kod kreskowy jest szyfrowany zgodnie ze standardem GS1. Mogą być używane maksymalnie trzy prefiksy (**Znak FNC1**, **Znak Datamatrix** i **Znak kodu QR**) równocześnie i do różnych celów.

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

    - **Identyfikator aplikacji** — należy wprowadzić kod identyfikacyjny tego identyfikatora aplikacji. Zazwyczaj kod jest dwucyfrową liczbą całkowitą, ale może być dłuższy. W przypadku wartości dziesiętnych ostatnia cyfra wskazuje liczbę miejsc dziesiętnych. Aby uzyskać więcej informacji, zobacz opis pola wyboru **Dziesiętna** dalej na tej liście.
    - **Opis** — umożliwia wprowadzanie krótkiego opisu identyfikatora.
    - **Stała długość** — to pole wyboru należy zaznaczyć, jeśli wartości skanowane przy użyciu tego identyfikatora aplikacji mają stałą liczbę znaków. Wyczyść to pole wyboru, jeśli długość wartości jest zmienna. W takim przypadku należy wskazać koniec wartości za pomocą znaku separatora grupy określonego na stronie **Parametry zarządzania magazynem**.
    - **Długość** — umożliwia wprowadzenie maksymalnej liczby znaków, które mogą pojawiać się w wartościach skanowanych przy użyciu tego identyfikatora aplikacji. Jeśli zaznaczono pole wyboru **Stała długość**, oczekiwana jest dokładnie ta liczba znaków.
    - **Typ** — umożliwia wybór typu wartości, która jest skanowana przy użyciu tego identyfikatora aplikacji (*Liczbowa*, *Alfanumeryczna* lub *Data*). W przypadku dat oczekiwany format to YYMMDD (bez spacji i łączników).
    - **Dziesiętna** — to pole wyboru należy zaznaczyć, jeśli wartość zawiera domniemany punkt dziesiętny. Jeśli to pole wyboru jest zaznaczone, system użyje ostatniej cyfry identyfikatora aplikacji do określenia liczby miejsc dziesiętnych. Jeśli na przykład identyfikator aplikacji to *3205*, ostatnie pięć cyfr wartości będzie interpretowane jako cyfry po separatorze dziesiętnym.

> [!NOTE]
> Separator grup określony na stronie **Parametry zarządzania magazynem** jest opcjonalny, jeśli wartość, po której następuje identyfikator aplikacji, ma stałą długość lub jeśli jej długość jest maksymalna (to oznacza, że długość jest równa wartości **Długość** ustawionej dla identyfikatora aplikacji).

## <a name="establish-the-generic-gs1-setup"></a>Ustanawianie ogólnej konfiguracji GS1

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

## <a name="set-up-gs1-policies-that-you-can-assign-to-mobile-device-menu-items"></a>Konfigurowanie zasad GS1, które można przypisać do opcji menu urządzenia przenośnego

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
1. Zaznacz pole **Pozycja** i zeskanuj następujący kod kreskowy: *\]C10100000012345678\~3030\~10b1\~17220215*.

Ze względu na ustawienia ustalone w tym przykładzie system w następujący sposób analizuje zeskanowany kod kreskowy.

| Klucz pola | Identyfikator aplikacji | Wartość | Banknot |
|---|---|---|---|
| ItemId | 01 | 00000012345678 | Ponieważ pracownik zeskanował pole **Pozycja**, pierwsza wartość z kodu kreskowego jest mapowana na to pole. Mapowanie pochodzi z ogólnej konfiguracji GS1. |
| Ilość | 30 | 30 | Ponieważ więcej niż jedna wartość pola jest odczytywana w jednym skanowaniu, to mapowanie i wszystkie pozostałe mapowania są brane pod uwagę w zasadach GS1 przypisanych do opcji menu **Przyjęcie zakupu**. Ta wartość jest ilością, która została przyjęta. |
| InventBatchId | 10 | b1 | Ta wartość jest identyfikatorem partii. |
| ExpDate | 17 | 220215 | Format daty to RRMMDD. Data ważności to zatem 15 lutego 2022. |

Następnie przyjęcie zostanie zarejestrowane i po jednym skanowaniu zostaną wprowadzone odpowiednie wartości w bazie danych.
