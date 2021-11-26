---
title: Konfigurowanie urządzenia do uruchamiania interfejsu wykonania hal produkcyjnych
description: Interfejs wykonywania hali produkcyjnej jest ustawiany dla każdego urządzenia w hali produkcyjnej. Firmy zazwyczaj konfigurują poszczególne urządzenia w różny sposób w zależności od przeznaczenia urządzenia. Na przykład firma może mieć jedno urządzenie w recepcji, gdzie pracownicy rejestrują się przyjście i wyjście, a drugie na hali produkcyjnej, gdzie pracownicy zarządzają swoimi zadaniami.
author: johanhoffmann
ms.date: 10/05/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: JmgProductionFloorExecution, HcmWorker, JmgProductionFloorExecutionDeviceConfiguration
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-10-05
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: f0be79b54a279893f93d41981342e42c8880f059
ms.sourcegitcommit: 03fa7556840aa59f825697f6f9edeb58ea673fca
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/04/2021
ms.locfileid: "7752839"
---
# <a name="set-up-a-device-to-run-the-production-floor-execution-interface"></a>Konfigurowanie urządzenia do uruchamiania interfejsu wykonania hal produkcyjnych

[!include [banner](../includes/banner.md)]

Interfejs wykonywania hali produkcyjnej jest ustawiany dla każdego urządzenia w hali produkcyjnej. Firmy zazwyczaj konfigurują poszczególne urządzenia w różny sposób w zależności od przeznaczenia urządzenia. Na przykład firma może mieć jedno urządzenie w recepcji, gdzie pracownicy rejestrują się przyjście i wyjście, a drugie na hali produkcyjnej, gdzie pracownicy zarządzają swoimi zadaniami.

## <a name="set-the-configuration-and-filters-for-a-specific-device"></a>Umożliwia ustawienie konfiguracji i filtrów dla określonego urządzenia

Aby określić konfigurację i filtry zadań dla urządzenia, należy zalogować się na stronie **Tworzenie hal produkcyjnych** przy użyciu konta, które ma rolę zabezpieczeń, która zawiera obowiązki *Utrzymuj nadzór nad czasem*. (Oprócz wbudowanych ról zabezpieczeń, tylko *Kierownik zakładu produkcyjnego* ma takie obowiązki.) Następnie wykonaj następujące kroki.

1. Przejdź do urządzenia, które chcesz skonfigurować, i zaloguj się do rozwiązania Microsoft Dynamics 365 Supply Chain Management jako kierownik zakładu produkcyjnego. (Należy skorzystać z konta, które zawiera obowiązki *Utrzymuj nadzór nad czasem*.)
1. Upewnij się, że dla konfigurowanego urządzenia jest dostępna konfiguracja. Jeśli konfiguracja jeszcze nie istnieje, podano konfigurację domyślną. Aby uzyskać więcej informacji o konfigurowaniu, zapoznaj się z tematem [Konfigurowanie urządzenia do uruchamiania interfejsu wykonywania pomieszczeń produkcyjnego](production-floor-execution-configure.md).
1. Wybierz kolejno opcje **Kontrola produkcji \> Wykonywanie produkcji \> Tworzenie hal produkcyjnych**.

    Jeśli interfejs wykonywania pomieszczeń produkcyjnych został już skonfigurowany co najmniej raz na bieżącym urządzeniu, zostanie wyświetlona strona logowania. W przeciwnym razie zostanie wyświetlona strona powitalna.

1. Na stronie rejestracji lub na stronie powitalnej wybierz opcję **Konfiguruj**.
1. Z listy należy wybrać konfigurację.
1. Wybierz pozycję **Następny**.
1. Wybierz co najmniej jeden filtr, który zostanie zastosowany do bieżącego urządzenia. Te filtry pomogą zagwarantować, że na urządzeniu będą widoczne tylko odpowiednie zadania. Aby zdefiniować filtr, wybierz typ filtra, aby otworzyć listę wartości, a następnie wybierz wartość, która ma być filtrowana. Dostępne są następujące filtry:

    - **Jednostka produkcyjna** — ten filtr jest filtrem najwyższego poziomu. Zazwyczaj odnosi się do dużego obszaru roboczego, w którym istnieje kilka grup zasobów i pojedynczych zasobów.
    - **Grupa zasobów** — ten filtr jest filtrem na poziomie średnim. Zazwyczaj odwołuje się do kolekcji powiązanych zasobów w ograniczonym obszarze obszaru roboczego. Jeśli najpierw zostanie wybrany filtr **Jednostki produkcyjnej**, lista grup zasobów będzie wyświetlać tylko grupy z tej jednostki. W przeciwnym razie pokazuje on wszystkie dostępne grupy zasobów.
    - **Zasób** — ten filtr jest najbardziej konkretnym filtrem. Zazwyczaj odnosi się do określonej maszyny lub innego pojedynczego zasobu. Jeśli wybierzesz najpierw filtr **Grupa zasobów**  i/lub **Jednostka produkcyjna**, lista zasobów będzie zawierała tylko zasoby z tej grupy i/lub jednostki. W przeciwnym razie pokazuje on wszystkie dostępne zasoby.

1. Kliknij przycisk **OK**.
1. Zostanie wyświetlona strona logowania, a urządzenie jest gotowe do użycia.

## <a name="allow-a-worker-to-override-the-default-filters"></a>Zezwalaj pracownikowi na zastąpienie domyślnych filtrów

Można nadać określonym pracownikom uprawnienia do zmiany ustawień filtru na każdym używanym urządzeniu. Dla pracowników, którzy mają to uprawnienie, interfejs wykonywania produkcji zawiera przycisk **Filtruj** na stronach **Wszystkie zadania** i **Aktywne zadania**.

> [!NOTE]
> Jeśli pracownik zmieni filtr, nowy filtr będzie obowiązywał od tego momentu dla wszystkich użytkowników logujących się do urządzenia.

Aby umożliwić pracownikowi zastąpienie domyślnych filtrów zadań skonfigurowanych dla urządzenia, należy wykonać następujące kroki.

1. Przejdź do **Czas i frekwencja \> Ustawienia \> Pracownicy odpowiedzialni za rejestrację czasu**.
1. Wybierz pracownika z listy, aby otworzyć stronę **Pracownicy odpowiedzialni za rejestrację czasu** pracownika.
1. Na karcie **Rejestracja czasu** określ dla opcji **Ustaw filtry** wartość *Tak*.

## <a name="run-the-interface-in-full-screen-mode"></a>Uruchamianie interfejsu w trybie pełnoekranowym

Często interfejs wykonywania hali produkcyjnej jest uruchamiany na urządzeniu, które jest używane wyłącznie do tego celu. Z tego względu może się zdarzyć, że interfejs jest uruchamiany w trybie pełnoekranowym bez wyświetlania nawigacji i/lub przeglądarki Chrome.

- Aby ukryć okienko nawigacji wyświetlane w Supply Chain Management, należy dodać następujący tekst na końcu adresu URL na pasku adresu przeglądarki: `\&limitednav=true`.
- Aby ukryć pasek adresu przeglądarki, należy skorzystać z macierzystego trybu pełnoekranowego w przeglądarce. (Aby uzyskać instrukcje, zajrzyj do dokumentacji przeglądarki.)

W górnej części pokazanej poniżej pokazano, jak interfejs jest domyślnie przeszukiwany. W dolnej części pokazano sposób wyglądu w trybie pełnoekranowym, gdy okienko nawigacji jest ukryte.

![Interfejs standardowy w porównaniu z pełnym ekranem.](media/pfei-full-screen.png "Interfejs standardowy w porównaniu z pełnym ekranem")

## <a name="extend-the-session-past-12-hours"></a>Rozszerz sesję w ciągu ostatnich 12 godzin

Domyślnie interfejs wykonywania rozkładu pracy automatycznie rejestruje się, jeśli nikt nie używa go przez 12 godzin. Użytkownik Supply Chain Management musi się ponownie zalogować. Można jednak wydłużyć limit czasu do 90 dni.

Aby wydłużyć limit czasu, zaloguj się w module Supply Chain Management i przejdź do **Administrowanie systemem \> Użytkownicy \> Rozszerzenia sesji**. Określ konto użytkownika Supply Chain Management służące do logowania się do urządzenia oraz liczbę godzin, dla których sesja powinna pozostać aktywna.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
