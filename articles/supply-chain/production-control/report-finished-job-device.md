---
title: Zgłaszanie jako gotowych z urządzenia karty zadania
description: W tym temacie opisano sposób konfigurowania systemu w taki sposób, aby użytkownicy urządzenia obsługującego karty zadań mogli zgłaszać produkty gotowe ze zlecenia produkcyjnego do magazynu.
author: johanhoffmann
ms.date: 07/31/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: JmgRegistrationSetupTouch
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-05-18
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 67fa97c938f091c23a41ddd5aaf34a32c5a13c93
ms.sourcegitcommit: fcb8a3419e3597fe855cae9eb21333698518c2c7
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/09/2022
ms.locfileid: "8102833"
---
# <a name="report-as-finished-from-the-job-card-device"></a>Zgłaszanie jako gotowych z urządzenia karty zadania

[!include [banner](../includes/banner.md)]

Pracownicy korzystają z strony **Zgłaszanie postępu** na urządzeniu z kartami zadań w celu raportowania ilości ukończonych dla zadania produkcyjnego. W tym temacie opisano, jak skonfigurować różne opcje, które określają, w jaki sposób pracownicy mogą zgłaszać ukończenie za pomocą tej strony i co dzieje się dalej. Dostępne opcje:

- Umożliwia określenie, czy i jak ilości zgłoszone jako gotowe są dodawane do magazynu.
- Umożliwia określenie, czy i w jaki sposób mają być generowane i stosowane numery partii podczas zgłaszania towarów gotowych.
- Umożliwia określenie, czy i w jaki sposób mają być generowane i stosowane numery seryjne podczas zgłaszania towarów gotowych.
- Kontroluj, czy i jak zgłaszać gotowość do numeru identyfikacyjnego.

## <a name="control-whether-quantities-that-are-reported-as-finished-are-added-to-inventory"></a>Umożliwia określenie, czy ilości zgłoszone jako gotowe są dodawane do magazynu

Aby określić, czy i w jaki sposób ilości zgłoszone jako gotowe w ostatniej operacji powinny zostać dodane do magazynu, należy wykonać następujące kroki.

1. Przejdź do **Kontrola produktu \> Ustawienia \> Wykonywanie produkcji \> Ustawienia domyślne zlecenia produkcyjnego**.
1. Na karcie **Zgłoszenie wyrobów gotowych**, w polu **Aktualizuj raport zakończonych online** określ jedną z następujących wartości:

    - **Nie** — ilość nie zostanie dodana do zapasów w przypadku zgłoszenia ilości w ostatniej operacji. Status zlecenia produkcyjnego nigdy się nie zmieni.
    - **Stan + ilość** — stan zlecenia produkcyjnego zostanie zmieniony na *Zgłoszone jako gotowe*, a ilość zostanie zgłoszona jako gotowa do magazynu.
    - **Ilość** – stan zlecenia produkcyjnego zostanie zmieniony na zgłoszone jako gotowe, ale stan zlecenia produkcyjnego nigdy się nie zmieni.
    - **Stan** – Zmieni się tylko stan zlecenia produkcyjnego.. Żadna ilość nie zostanie dodana do zapasów w przypadku zgłoszenia ilości w ostatniej operacji.

> [!NOTE]
> Ilości nie są śledzone w zapasach, jeśli operacje, które zostały zgłoszone jako zakończone, nie są zdefiniowane jako ostatnia operacja. Jednak te ilości mogą być używane do oglądania postępu. Można je również uwzględnić w regułach, które kontrolują, czy pracownicy mogą rozpoczynać następną operację przed osiągnięciem zdefiniowanego progu zgłoszonych ilości w poprzedniej operacji. Te reguły można zdefiniować na karcie **Sprawdzanie poprawności ilości** na stronie **Ustawienia domyślne zlecenia produkcyjnego**.

Aby uzyskać więcej informacji na temat pracy ze stroną **Ustawienia domyślne zlecenia produkcyjnego**, należy zapoznać się z [Parametry produkcji w module Uruchomienie produkcji](production-parameters-manufacturing-execution.md).

## <a name="report-batch-controlled-items-as-finished"></a>Zgłaszanie towarów kontrolowanych za pomocą partii jako gotowe

Urządzenie karty zadań obsługuje trzy scenariusze tworzenia raportów dotyczących partii towarów. Te scenariusze dotyczą zarówno towarów włączonych dla zaawansowanych procesów magazynowych, jak i dla towarów, które nie są włączone dla zaawansowanych procesów magazynowych.

- **Numery partii przypisane ręcznie** - Pracownicy wprowadzający niestandardowy numer partii. Ten numer partii może pochodzić ze źródła zewnętrznego, które nie jest znane dla systemu.
- **Wstępnie zdefiniowane numery partii** - Pracownik umożliwia wybranie numeru partii na liście numerów partii, które system automatycznie generuje przed zwolnieniem zlecenia produkcyjnego na urządzeniu karty zadań.
- **Trwałe numery partii** - Pracownicy nie wprowadzają ani nie wybierają numeru partii. Zamiast tego system automatycznie przypisuje numer partii do zlecenia produkcyjnego przed jego zwolnieniem.


### <a name="enable-the-feature-on-your-system"></a>Włączanie funkcji w systemie

Aby umożliwić urządzeniom kart produkcyjnych akceptowanie numeru partii podczas zgłaszania wyrobów gotowych, należy skorzystać z [zarządzania funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) w celu włączenia następujących funkcji (w podanej kolejności):

1. Udoskonalone środowisko użytkownika okna dialogowego zgłaszania postępu w menu Urządzenie karty zadań
1. Włącz, aby wprowadzić numery seryjne i partii podczas zgłaszania jako gotowych z urządzenia karty zadań

### <a name="configure-products-that-require-batch-number-reporting"></a>Konfigurowanie produktów wymagających raportowania numerów partii

Aby umożliwić produktowi obsługę dowolnego z dostępnych scenariuszy sterowanych wsadowo, należy wykonać następujące kroki:

1. Przejdź do **Zarządzanie informacjami o produktach\> Produkty \> Zwolnione produkty**.
1. Umożliwia wybranie produktu do konfiguracji.
1. Na skróconej karcie **Zarządzaj zapasami** w polu **Grupa numerów partii** wybierz grupę numerów śledzenia skonfigurowaną w taki sposób, aby obsługiwała dany scenariusz.

> [!NOTE]
> Domyślnie, jeśli grupa numerów partii nie jest przypisana do produktu kontrolowanego przez partię, urządzenie karty zadań zawiera ręczny wpis dla numeru partii podczas zgłaszania wyrobów gotowych.

Poniższe sekcje opisują sposób konfigurowania grup numerów śledzenia w celu obsługi każdego z trzech scenariuszy tworzenia raportów dotyczących partii towarów.

### <a name="set-up-a-tracking-number-group-that-lets-workers-manually-assign-a-batch-number"></a>Ustaw grupę numerów identyfikacyjnych, aby umożliwić pracownikom ręczne przypisanie numeru partii

Aby zezwolić na ręcznie przypisane numery partii, wykonaj następujące kroki, aby skonfigurować grupę numerów śledzenia.

1. Przejdź do **Zarządzanie zapasami \> Konfiguracja \> Wymiary \> Grupy numerów śledzenia**.
1. Utwórz lub wybierz grupę numerów śledzenia do skonfigurowania.
1. Na skróconej karcie **Ogólne** ustaw opcje **Ręcznie** na **Tak**.

    ![Grupa numerów śledzenia dla ręcznych numerów partii.](media/tracking-number-group-manual.png "Grupa numerów śledzenia dla ręcznych numerów partii")

1. Należy określić inne wymagane wartości, a następnie wybrać tę grupę numerów śledzenia jako grupę numerów partii dla zwolnionych produktów, dla których ma być używany ten scenariusz.

W przypadku użycia tego scenariusza pole **Numeru partii**, które znajduje się na stronie **Zgłaszanie postępu** na karcie zadań, jest polem tekstowym, w którym pracownicy mogą wprowadzać dowolną wartość.

![Umożliwia raportowanie strony postępu z polem dla ręcznych numerów partii.](media/job-card-device-batch-manual.png "Umożliwia raportowanie strony postępu z polem dla ręcznych numerów partii")

### <a name="set-up-a-tracking-number-group-that-provides-a-list-of-predefined-batch-numbers"></a>Skonfiguruj grupę numerów śledzenia, która dostarcza listę wstępnie zdefiniowanych numerów partii

Aby podać listę predefiniowanych numerów partii, wykonaj następujące kroki, aby skonfigurować grupę numerów śledzenia.

1. Przejdź do **Zarządzanie zapasami \> Konfiguracja > Wymiary \> Grupy numerów śledzenia**.
1. Utwórz lub wybierz grupę numerów śledzenia do skonfigurowania.
1. Na skróconej karcie **Ogólne** ustaw opcje **Tylko dla transakcji magazynowych** na **Tak**.
1. Pole **Na ilość** służy do dzielenia numerów partii na ilość w zależności od wprowadzonej wartości. Na przykład zlecenie produkcyjne dla dziesięciu sztuk, a pole **Na ilość** jest ustawione na wartość *2*. W takim przypadku do zlecenia produkcyjnego zostanie przypisane pięć numerów partii, które zostały utworzone.

    ![Grupa numerów śledzenia dla zdefiniowanych numerów partii.](media/tracking-number-group-predefined.png "Grupa numerów śledzenia dla zdefiniowanych numerów partii")

1. Należy określić inne wymagane wartości, a następnie wybrać tę grupę numerów śledzenia jako grupę numerów partii dla zwolnionych produktów, dla których ma być używany ten scenariusz.

W przypadku użycia tego scenariusza pole **Numeru partii**, które znajduje się na stronie **Zgłaszanie postępu** na urządzeniu karty zadań, zapewnia listę rozwijaną, na której pracownicy muszą wybrać wcześniej zdefiniowaną wartośc.

![Umożliwia raportowanie strony postępu z polem dla listy wcześniej zdefiniowanych numerów partii.](media/job-card-device-batch-predefined.png "Umożliwia raportowanie strony postępu z polem dla listy wcześniej zdefiniowanych numerów partii")

### <a name="set-up-a-tracking-number-group-that-automatically-assigns-batch-numbers"></a>Skonfiguruj grupę numerów śledzenia, która automatycznie przypisuje numery partii

Jeśli numery partii powinny być przypisywane automatycznie, bez wprowadzania danych pracownika, należy wykonać poniższe kroki w celu skonfigurowania grupy numerów śledzenia.

1. Przejdź do **Zarządzanie zapasami \> Konfiguracja \> Wymiary \> Grupy numerów śledzenia**.
1. Utwórz lub wybierz grupę numerów śledzenia do skonfigurowania.
1. Na skróconej karcie **Ogólne** ustaw opcje **Tylko dla transakcji magazynowych** na **Nie**.
1. W opcji **Ręcznie** określ wartość **Nie**.

    ![Grupa numerów śledzenia dla ustawionych numerów partii.](media/tracking-number-group-fixed.png "Grupa numerów śledzenia dla ustawionych numerów partii")

1. Należy określić inne wymagane wartości, a następnie wybrać tę grupę numerów śledzenia jako grupę numerów partii dla zwolnionych produktów, dla których ma być używany ten scenariusz.

W przypadku użycia tego scenariusza pole **Numeru partii**, które znajduje się na stronie **Zgłaszanie postępu** na karcie zadań, pokazuje wartość, ale pracownicy nie mogą jej edytować.

![Umożliwia raportowanie strony postępu z trwałym numerem partii.](media/job-card-device-batch-fixed.png "Umożliwia raportowanie strony postępu z trwałym numerem partii")

## <a name="report-serial-controlled-items-as-finished"></a>Zgłaszanie towarów kontrolowanych za pomocą serii jako gotowe

Urządzenie karty pracy obsługuje trzy scenariusze raportowania towarów kontrolowanych seryjnie. Te scenariusze dotyczą zarówno towarów włączonych dla zaawansowanych procesów magazynowych, jak i dla towarów, które nie są włączone dla zaawansowanych procesów magazynowych.

- **Numery seryjne przypisane ręcznie** - Pracownicy wprowadzający niestandardowy numer seryjny. Ten numer seryjny może pochodzić ze źródła zewnętrznego, które nie jest znane dla systemu.
- **Wstępnie zdefiniowane numery seryjne** - Pracownik umożliwia wybranie numeru sertyjnego na liście numerów seryjnych, które system automatycznie generuje przed zwolnieniem zlecenia produkcyjnego na urządzeniu karty zadań.
- **Trwałe numer seryjny** - Pracownicy nie wprowadzają ani nie wybierają numeru seryjnego. Zamiast tego system automatycznie przypisuje numer seryjny do zlecenia produkcyjnego przed jego zwolnieniem.

### <a name="enable-the-feature-on-your-system"></a>Włączanie funkcji w systemie

Aby umożliwić urządzeniom kart produkcyjnych akceptowanie numeru seryjnego podczas zgłaszania wyrobów gotowych, należy skorzystać z [zarządzania funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) w celu włączenia następujących funkcji (w podanej kolejności):

1. Udoskonalone środowisko użytkownika okna dialogowego zgłaszania postępu w menu Urządzenie karty zadań
1. Włącz, aby wprowadzić numery seryjne i partii podczas zgłaszania jako gotowych z urządzenia karty zadań

### <a name="configure-products-that-require-serial-number-reporting"></a>Konfigurowanie produktów wymagających raportowania numerów seryjnych

Aby umożliwić produktowi obsługę dowolnego z dostępnych scenariuszy sterowanych seryjnie, należy wykonać następujące kroki:

Aby wyłączyć każdy scenariusz, wykonaj następujące kroki.

1. Przejdź do **Zarządzanie informacjami o produktach\> Produkty \> Zwolnione produkty**.
1. Umożliwia wybranie produktu do konfiguracji.
1. Na skróconej karcie **Zarządzaj zapasami** w polu **Grupa numerów seryjnych** wybierz grupę numerów śledzenia skonfigurowaną w taki sposób, aby obsługiwała dany scenariusz.

> [!NOTE]
> Domyślnie, jeśli grupa numerów seryjnych nie jest przypisana do produktu kontrolowanego przez serię, urządzenie karty zadań zawiera ręczny wpis dla numeru seryjnego podczas zgłaszania wyrobów gotowych.

Poniższe sekcje opisują sposób konfigurowania grup numerów śledzenia w celu obsługi każdego z trzech scenariuszy tworzenia raportów dotyczących towarów kontrolowanych przez serię.

### <a name="set-up-a-tracking-number-group-that-lets-workers-manually-assign-a-serial-number"></a>Ustaw grupę numerów identyfikacyjnych, aby umożliwić pracownikom ręczne przypisanie numeru seryjnego

Aby zezwolić na ręcznie przypisane numery seryjne, wykonaj następujące kroki, aby skonfigurować grupę numerów śledzenia.

1. Przejdź do **Zarządzanie zapasami \> Konfiguracja \> Wymiary \> Grupy numerów śledzenia**.
1. Utwórz lub wybierz grupę numerów śledzenia do skonfigurowania.
1. Na skróconej karcie **Ogólne** ustaw opcje **Ręcznie** na **Tak**.

    ![Strony grup numerów śledzenia, numery seryjne.](media/tracking-number-group-manual-serial.png "Strony grup numerów śledzenia, numery seryjne")

1. Należy określić inne wymagane wartości, a następnie wybrać tę grupę numerów śledzenia jako grupę numerów seryjnych dla zwolnionych produktów, dla których ma być używany ten scenariusz.

W przypadku użycia tego scenariusza pole **Numer seryjny**, które znajduje się na stronie **Zgłaszanie postępu** na karcie zadań, jest polem tekstowym, w którym pracownicy mogą wprowadzać dowolną wartość dla numeru seryjnego. Po wprowadzeniu wartości jest ona dodawana do listy numerów seryjnych. Na tej liście pracownicy mogą wykonywać następujące czynności:

- Aby oznaczyć numer seryjny jako odpadki, wybierz przycisk **Odpadki** dla odpowiedniego wiersza. Pracownik będzie monitowany o podanie **Przyczyny błędu**.
- Aby usunąć numer seryjny, wybierz przycisk **Usuń** dla odpowiedniego wiersza.

![Umożliwia raportowanie strony postępu z polem dla ręcznych numerów seryjnych.](media/job-card-device-serial-manual.png "Umożliwia raportowanie strony postępu z polem dla ręcznych numerów seryjnych")

### <a name="set-up-a-tracking-number-group-that-provides-a-list-of-predefined-serial-numbers"></a>Skonfiguruj grupę numerów śledzenia, która dostarcza listę wstępnie zdefiniowanych numerów seryjnych

Aby podać listę predefiniowanych numerów seryjnych, wykonaj następujące kroki, aby skonfigurować grupę numerów śledzenia.

1. Przejdź do **Zarządzanie zapasami \> Konfiguracja \> Wymiary \> Grupy numerów śledzenia**.
1. Utwórz lub wybierz grupę numerów śledzenia do skonfigurowania.
1. Na skróconej karcie **Ogólne** ustaw opcje **Tylko dla transakcji magazynowych** na **Tak**.
1. **Pole na ilość** umożliwia podział numerów seryjnych na liczbę z jednej.

    ![Grupa numerów śledzenia dla zdefiniowanych numerów seryjnych.](media/tracking-number-group-predefined-sn.png "Grupa numerów śledzenia dla zdefiniowanych numerów seryjnych")

1. Należy określić inne wymagane wartości, a następnie wybrać tę grupę numerów śledzenia jako grupę numerów seryjnych dla zwolnionych produktów, dla których ma być używany ten scenariusz.

W przypadku użycia tego scenariusza pole **Numer seryjny**, które znajduje się na stronie **Zgłaszanie postępu** na urządzeniu karty zadań, zapewnia listę rozwijaną, na której pracownicy muszą wybrać wcześniej zdefiniowaną wartośc.

![Umożliwia raportowanie strony postępu z polem dla listy wcześniej zdefiniowanych numerów seryjnych.](media/job-card-device-serial-predefined.png "Umożliwia raportowanie strony postępu z polem dla listy wcześniej zdefiniowanych numerów seryjnych")

### <a name="set-up-a-tracking-number-group-that-automatically-assigns-serial-numbers"></a>Skonfiguruj grupę numerów śledzenia, która automatycznie przypisuje numery seryjne

Jeśli numer seryjny powinien być przypisywanye automatycznie, bez wprowadzania danych pracownika, należy wykonać poniższe kroki w celu skonfigurowania grupy numerów śledzenia.

1. Przejdź do **Zarządzanie zapasami \> Konfiguracja \> Wymiary \> Grupy numerów śledzenia**.
1. Utwórz lub wybierz grupę numerów śledzenia do skonfigurowania.
1. Na skróconej karcie **Ogólne** ustaw opcje **Tylko dla transakcji magazynowych** na **Nie**.
1. W opcji **Ręcznie** określ wartość **Nie**.

    ![Grupa numerów śledzenia dla ustawionych numerów seryjnych.](media/tracking-number-group-fixed-sn.png "Grupa numerów śledzenia dla ustawionych numerów seryjnych")

1. Należy określić inne wymagane wartości, a następnie wybrać tę grupę numerów śledzenia jako grupę numerów seryjnych dla zwolnionych produktów, dla których ma być używany ten scenariusz.

W przypadku użycia tego scenariusza pole **Numer seryjny**, które znajduje się na stronie **Zgłaszanie postępu** na karcie zadań, pokazuje wartość, ale pracownicy nie mogą jej edytować. Ten scenariusz ma zastosowanie tylko w przypadku, gdy tworzone jest zlecenie produkcyjne dla ilości jednej sztuki towaru kontrolowanego numerem seryjnym.

![Umożliwia raportowanie strony postępu z trwałym numerem seryjnym.](media/job-card-device-serial-fixed.png "Umożliwia raportowanie strony postępu z trwałym numerami seryjnymi")

## <a name="report-as-finished-to-a-license-plate"></a>Zgłaszanie wyrobów jako gotowych do numeru identyfikacyjnego

W przypadku zaawansowanych procesów magazynowych może być używany wymiar numer identyfikacyjny w celu śledzenia zapasów w lokalizacjach magazynów, które zostały skonfigurowane w tym celu. W takim przypadku numer identyfikacyjny jest wymagany, gdy pracownik zgłasza ilości jako gotowe.

### <a name="enable-license-plate-reporting-and-label-printing"></a>Włączanie zgłaszania i drukowania etykiet numeru identyfikacyjnego

Aby móc stosować funkcje opisane w tej sekcji, należy skorzystać z [zarządzania funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) w celu włączenia następujących funkcji (w podanej kolejności):

1. *Numer identyfikacyjny do zgłoszenia wyrobów gotowych został dodany do urządzenia karty zadań*<br>(Od wersji 10.0.21 Supply Chain Management version ta funkcja jest domyślnie włączona. Od wersji 10.0.25 Supply Chain Management version ta funkcja jest wymagana).
1. *Włącz automatyczną generację numeru identyfikacyjnego podczas zgłaszania wyrobów gotowych w urządzeniu karty zadań*<br>(Od wersji 10.0.25 Supply Chain Management version ta funkcja jest wymagana).
1. *Drukowanie etykiety z menu Urządzenie karty zadań*<br>(Od wersji 10.0.25 Supply Chain Management version ta funkcja jest wymagana).

### <a name="set-up-reporting-as-finished-to-a-license-plate"></a>Ustawianie zgłaszania wyrobów jako gotowych do numeru identyfikacyjnego

Aby określić, czy pracownicy powinni ponownie używać istniejącego numeru identyfikacyjnego, czy generować nowy numer identyfikacyjny, gdy zgłaszają ilości jako gotowe, należy wykonać następujące kroki.

1. Wybierz kolejno opcje **Kontrola produkcji \> Ustawienia \> Wykonywanie produkcji \> Konfiguruj kartę zadań dla urządzeń**.
2. Ustaw następujące opcje dla każdego urządzenia:

    - **Generowanie numeru identyfikacyjnego** – ustawienie tej opcji na wartość **Tak** powoduje generowanie nowego numeru identyfikacyjnego dla każdego zgłoszenia jako gotowego. Należy ustawić wartość **Nie**, jeśli dla każdego zgłoszenia jako gotowego ma być używany istniejący numer identyfikacyjny.
    - **Drukuj etykietę**  – ustawienie tej opcji na wartość **Tak**, jeśli pracownik musi wydrukować etykieę numeru identyfikacyjnego dla każdego zgłoszenia jako gotowej. Wartość **Nie** należy ustawić, jeśli etykieta nie jest wymagana. 

![Konfiguruj kartę zadania dla urządzeń.](media/config-job-card-raf.png "Konfiguruj kartę zadania dla urządzeń")

> [!NOTE]
> Aby skonfigurować etykietę, wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Wybór trasy dokumentów \> Układy wyboru trasy dokumentów**. Aby uzyskać więcej informacji, zajrzyj do [Włącz drukowanie etykiet numerów identyfikacyjnych](../warehousing/tasks/license-plate-label-printing.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]