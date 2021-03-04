---
title: Tworzenie i aktualizowanie przedziałów czasu na potrzeby odbiorów przez odbiorcę
description: W tym temacie opisano sposób tworzenia, konfigurowania i aktualizowania przedziałów czasu odbioru klientów w centrali Commerce.
author: anupamar-ms
manager: AnnBe
ms.date: 11/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rapraj
ms.search.validFrom: 2020-09-20
ms.dyn365.ops.version: Retail 10.0.15 update
ms.openlocfilehash: f86eb47ec64dff230223ed0ecbe792373aca649f
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2020
ms.locfileid: "4681549"
---
# <a name="create-and-update-time-slots-for-customer-pickup"></a>Tworzenie i aktualizowanie przedziałów czasu na potrzeby odbiorów przez odbiorcę

[!include [banner](../../includes/banner.md)]

W tym temacie opisano sposób tworzenia, konfigurowania i aktualizowania przedziałów czasu odbioru klientów w centrali Commerce.

Funkcja przedziału czasowego umożliwia sprzedawcom detalicznym zdefiniowanie przedziału czasowego dla towarów, dla których włączony jest tryb dostawy do klienta. Przedziały czasowe pozwalają detalistom określać dni i godziny, w których można odebrać zamówienia ze sklepu. Sprzedawcy detaliczni mogą również zdefiniować liczbę zamówień, które można odebrać w danym okresie. W ten sposób detaliści mogą ograniczyć liczbę zamówień, które można odebrać w danym dniu io określonej godzinie. Wynikiem tego jest lepsza jakość doświadczenia dla klientów.

> [!NOTE]
> Funkcja przedziału czasowego jest dostępna w Microsoft Dynamics 365 Commerce w wersji 10.0.15 i nowszych.

Poniższa ilustracja przedstawia przykład wyboru przedziału czasu podczas realizacji transakcji w handlu elektronicznym.

![Przykład wyboru przedziału czasu podczas realizacji transakcji w handlu elektronicznym](../dev-itpro/media/Curbside_timeslot_eCommerce.PNG)

## <a name="time-slot-properties"></a>Właściwości przedziału czasu

Przedział czasowy to określony przedział czasu, w którym klient może odebrać zamówienie z określonego sklepu lub lokalizacji. Funkcja zarządzania przedziałami czasowymi jest dostępna tylko wtedy, gdy tryb dostawy do klienta jest skonfigurowany w Dynamics 365 Commerce.

Do definiowania czasu służą następujące właściwości:

- **Metoda dostawy** — umożliwia określenie metody odbioru, do której odnosi się dany przedział czasu.
- **Minimalna liczba dni** i **Maksymalna liczba dni** — Określ najwcześniejszą i najpóźniejszą datę, którą można wybrać do odbioru w stosunku do daty złożenia zamówienia. 

    Właściwość **Minimalna liczba dni** zapewnia sprzedawcy wystarczająco dużo czasu na przetworzenie zamówienia, zanim będzie ono gotowe do odbioru. Właściwość **Maksymalna liczba dni** zapewnia, że użytkownik nie może wybrać zbyt dużej daty w przyszłości. Na przykład, jeśli wartość minimalna jest ustawiona na **1**, a zamówienie zostanie złożone 20 września, najwcześniejszy dzień, w którym zamówienie będzie dostępne do odbioru, to następny kwalifikujący się dzień (21 września). W podobny sposób, ustawiając wartość maksymalną, możesz zdefiniować maksymalną liczbę dni, przez które można odebrać zamówienie. Po zdefiniowaniu wartości minimalnych i maksymalnych użytkownicy witryny mogą wyświetlać i wybierać tylko określony zestaw dni podczas płatności.

    Wartość minimalną można określić jako wartość dziesiętną mniejszą niż 1. Na przykład, jeśli odbiór jest możliwy cztery godziny po złożeniu zamówienia, ustaw wartość minimalną na **0,17** (= 4 ÷ 24, zaokrąglając do dwóch miejsc po przecinku). Jeśli jednak ustawisz wartość minimalną na wartość dziesiętną większą niż 1, jest ona zawsze zaokrąglana do najbliższej liczby całkowitej (w górę lub w dół).

    Jeśli ustawisz wartość maksymalną na wartość dziesiętną, jest ona zawsze zaokrąglana w górę. Na przykład wartość **1,2** będzie zaokrąglana w górę do wartości **2**.

- **Data początkowa** i **Data zakończenia** — umożliwia określenie daty rozpoczęcia i zakończenia przedziału czasu. Każdy wpis przedziału czasu ma datę rozpoczęcia i zakończenia. W związku z tym masz możliwość dodawania różnych przedziałów czasowych w ciągu całego roku (na przykład odbiory w godzinach wakacyjnych). Jeśli początek i daty przedziału czasowego zostaną zmienione po złożeniu zamówienia, zmiany nie będą miały zastosowania do tego zamówienia. Definiując daty rozpoczęcia i zakończenia, należy wziąć pod uwagę daty zamknięcia sklepu (na przykład Boże Narodzenie) i upewnić się, że przedziały czasowe nie są zdefiniowane dla tych dni.
- **Aktywne godziny dostawy** — umożliwia określenie okresu, w którym jest dozwolony odbiór. Na przykład, godziny odbioru mogą być codziennie od 14:00 do 17:00. Ta właściwość umożliwia niezależność czasu odbioru od godzin otwarcia sklepu. W związku z tym detalista może skonfigurować czasy odbioru spełniające określone wymagania biznesowe. Podczas definiowania aktywnych godzin odbiór należy wziąć pod uwagę godziny magazynowania i upewnić się, że czasy odbiorów nie są zdefiniowane dla czasu zamknięcia sklepu.

    > [!NOTE]
    > Godziny odbioru sklepu muszą być zdefiniowane w strefie czasowej odpowiedniego sklepu.

- **Interwał przedziału czasu** — Określ czas trwania, który można przydzielić do każdego przedziału czasowego. Na przykład czas trwania każdego przedziału czasowego może być zwiększany o 15 minut, 30 minut lub jedną godzinę.
- **Przedziały na interwał** — umożliwia określenie liczby odbiorców lub zamówień, które mogą być doręczane do pobrania w poszczególnych interwałach czasu. Na przykład wprowadź **1**, **2**, **3** lub dowolną inną liczbę całkowitą.
- **Aktywne dni** — umożliwia określenie dni tygodnia, w których są aktywne przedziały czasu dla odbiorów. Ta właściwość pozwala sprzedawcy określić dni, w których chce obsługiwać zamówienia odbioru.
- **Kanały sprzedaży detalicznej** — umożliwia określenie kanałów sprzedaży detalicznej. Każdy przedział czasu może być powiązany z jednym lub większą liczbą sklepów detalicznych. W zależności od godzin pracy każdego sklepu, można utworzyć jeden lub więcej wpisów przedziałów czasowych i powiązać je z kanałem. 

<!-- ![HQ Timeslot overview](../dev-itpro/media/Curbside_timeslot_Settings_overview.PNG) -->

Na kanał można skonfigurować tylko jeden szablon przedziału czasowego. Te kanały obejmują sklepy fizyczne, biura obsługi, urządzenia przenośne oraz witryny handlu elektronicznego

## <a name="configure-the-time-slot-feature-in-commerce-headquarters"></a>Konfigurowanie funkcji czasu w centrali Commerce

Przedziały czasowe muszą być zdefiniowane dla każdego trybu odbioru dostawy w centrali Commerce, aby punkty sprzedaży (POS) i kanały handlu elektronicznego mogły się do nich odnosić.

- Z każdym sklepem lub kanałem można skojarzyć tylko jeden szablon przedziału czasowego.
- Każdy tworzony przedział czasu powinien być unikalny dla każdego trybu dostarczania w każdym szablonie.
- Po skonfigurowaniu funkcji przedziałów czasu kalendarz przedziałów czasu będzie dostępny dla wybranych sklepów lub grup sklepów. Będzie również widoczny w punkcie sprzedaży w celach informacyjnych.

Aby skonfigurować funkcję przedziału czasu w siedzibie firmy Commerce, wykonaj następujące kroki.

1. Przejdź do **Commerce** \> **Ustawienia kanału** \> **Przedział czasu odbioru w sklepie**.
1. Wybierz pozycję **Nowy**, aby utworzyć nowy przedział czasu. Aby skorzystać z istniejącego szablonu, wybierz szablon w lewym okienku.
1. Wprowadź wartości w polach **Identyfikator przedziału czasu** i **Opis**.
1. Na skróconej karcie **Odbiór zamówienia - Ustawienia czasu** wybierz opcję **Dodaj**.
1. W oknie dialogowym **Odbiór zamówienia - Ustawienia czasu** określ zakres dat, metodę dostawy, aktywne godziny dostawy, aktywne dni, interwały czasu, przedziały na interwał oraz inne ustawienia.

    Jeśli przedziały czasowe w dającej się przewidzieć przyszłości będą statyczne, pozostaw pole **Data końcowa** puste.

    > [!NOTE]
    > Możesz utworzyć wiele szablonów, ale tylko jeden szablon może być powiązany z pojedynczym kanałem lub sklepem.

    ![Okno dialogowe Odbiór zamówienia - Ustawienia czasu](../dev-itpro/media/Curbside_timeslot_Settings_Page.PNG)

1. Po zakończeniu wybierz przycisk **OK**.
1. Jeśli przedziały czasowe w ciągu dnia będą się różnić, utwórz dodatkowe wpisy na skróconej karcie **Odbiór zamówienia - Ustawienia czasu**, aby zapewnić, że daty i godziny nie pokrywają się.
1. Na skróconej karcie **Kanały sprzedaży detalicznej** wybierz opcję **Dodaj**, aby skojarzyć szablon przedziałów czasu z sklepami lub kanałami, w których będzie używany.
1. W oknie dialogowym **Wybieranie węzłów organizacji** użyj przycisków strzałek, aby zaznaczyć (lub wyczyścić zaznaczenie) sklepy, regiony i organizacje, z którymi szablon ma być powiązany.

    <!-- ![HQ Timeslot overview](../dev-itpro/media/Curbside_timeslot_Settings_overview.PNG) -->

1. Po zakończeniu wybierz przycisk **OK**.
1. Na stronie **Harmonogram dystrybucji** uruchom zadania **1070** i **1135**, aby zsynchronizować dane z kanałami.

## <a name="time-slot-selection-for-pos-orders"></a>Wybór przedziału czasowego dla zamówień POS

W punkcie sprzedaży, gdy zamówienie lub linia zamówienia zostanie zidentyfikowana do odbioru, kasjer może wybrać punkt odbioru lub lokalizację oraz datę i godzinę. Jeśli odbiorca ma zamówienie pobrania dla innego sklepu, kasjer może wybrać daty, kiedy pobranie będzie dostępne w tym sklepie. Wyszukiwanie w sklepie będzie zawierać odwołanie do dat i godzin przechowywania.

Poniższa ilustracja przedstawia przykład wyboru przedziału czasu dla zamówienia POS.

![Przykład wyboru przedziału czasowego dla zamówienia POS](../dev-itpro/media/Curbside_timeslot_POS.png)

## <a name="time-slot-selection-for-e-commerce-orders"></a>Wybór przedziału czasowego dla zamówień handlu elektronicznego

Aby uzyskać informacje o tym, jak udostępnić wybór przedziału czasowego dla zamówień w handlu elektronicznym, zapoznaj się z [Moduł informacji o odbiorze](../pickup-info-module.md).

> [!NOTE]
> Użytkownicy mogą wyświetlać lub edytować przedziały czasu odbioru na stronie realizacji transakcji w witrynie Commerce tylko wtedy, gdy moduł informacji o odbiorze został dodany do tej strony. Jeśli strona kasy nie zawiera modułu informacji o odbiorze, zamówienia będą składane bez umożliwienia użytkownikom określania lub przeglądania informacji o przedziale czasowym.

Na poniższej ilustracji przedstawiono przykład zamówienia w handlu elektronicznym, w którym wybrano przedział czasu odbioru.

![Przykład zamówienia w handlu elektronicznym, w którym wybrano przedział czasu odbioru](../dev-itpro/media/Curbside_timeslot_eCommerce_checkoutsummary.PNG)

## <a name="additional-resources"></a>Dodatkowe zasoby

[Moduł informacji o odbiorze](../pickup-info-module.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]