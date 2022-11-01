---
title: Obliczanie dat dostawy zamówień sprzedaży przy użyciu CTP
description: Funkcja Capable-to-promise (CTP) umożliwia podanie klientom realistycznych terminów, w których można obiecać konkretne towary. W tym artykule opisano sposób skonfigurowania i używania protokołu CTP dla każdego aparatu planowania (optymalizacji planowania i wbudowanego aparatu).
author: t-benebo
ms.date: 07/20/2022
ms.topic: article
ms.search.form: SalesAvailableDlvDates, SalesTable, CustParameters, InventItemOrderSetup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2022-07-20
ms.dyn365.ops.version: 10.0.28
ms.openlocfilehash: 3b8e3dc9f0e7aaf019aa4d7284458206e7daadb2
ms.sourcegitcommit: 86c0562ce1ecdf7937125c0f5a6771f178b459e7
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2022
ms.locfileid: "9714868"
---
# <a name="calculate-sales-order-delivery-dates-using-ctp"></a>Obliczanie dat dostawy zamówień sprzedaży przy użyciu CTP

[!include [banner](../../includes/banner.md)]
[!INCLUDE [preview-banner](../../includes/preview-banner.md)]
<!-- KFM: Preview until further notice -->

Funkcja Capable-to-promise (CTP) umożliwia podanie klientom realistycznych terminów, w których można obiecać konkretne towary. Dla każdego wiersza sprzedaży można podać datę z uwzględnieniem istniejących dostępnych zapasów, zdolności produkcyjnych oraz czasów transportu.

CTP rozszerza funkcjonalność [available-to-promise](../../sales-marketing/delivery-dates-available-promise-calculations.md) (ATP) przez uwzględnienie informacji o pojemności. Podczas gdy w atp jest uwzględniana tylko dostępność materiałów i zakłada się nieskończone zasoby zdolności produkcyjnych, w usługach CTP jest uwzględniana dostępność zarówno materiałów, jak i zdolności produkcyjnych. Dzięki temu można uzyskać bardziej realny obraz tego, czy popyt może być zatrzymany w danym czasie.

CTP działa nieco inaczej, w zależności od używanego głównego aparatu planowania (Optymalizacja planowania lub wbudowany aparat). W tym artykule opisano, jak skonfigurować go dla każdego silnika. CTP dla optymalizacji planowania obecnie obsługuje tylko podzestaw scenariuszy CTP, które są obsługiwane przez wbudowany aparat.

## <a name="turn-on-ctp-for-planning-optimization"></a>Włącz CTP w celu optymalizacji planowania

CTP dla wbudowanego głównego mechanizmu planowania jest zawsze dostępny. Jeśli jednak chcesz używać CTP do optymalizacji planowania, musisz je wyłączyć dla systemu. Administratorzy mogą skorzystać z ustawień [zarządzania funkcją](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby sprawdzić stan funkcji i włączyć ją. W obszarze roboczym **Zarządzanie funkcjami** ta funkcja widnieje jako:

- **Moduł:** *Planowanie główne*
- **Nazwa funkcji:** *(Wersja zapoznawcza) CTP dla optymalizacji planowania*

## <a name="how-ctp-compares-to-atp"></a>W jaki sposób CTP porównuje się z ATP

CTP i ATP są podobne, ale CTP często zapewnia dokładniejsze wyniki, jak pokazano w poniższym przykładzie.

Towar A składa się z towarów B i C, a dostępna ilość towaru A wynosi 0 (zero). W przypadku sprawdzenia ATP z uwzględnieniem tylko materiałów ilość ATP będzie także równa 0 (zero). Jednak w przypadku sprawdzenia CTP system sprawdza dostępność towarów B i C, sprawdza zasoby wymagane do ich uwzględnienia w towarze A i oblicza liczbę towarów A, które mogą zostać wykonane. Ponadto obliczanie CTP może sprawdzać zasoby i materiały wymagane do produkcji większej liczby towarów B i C oraz używać ich do produkcji większej liczby towarów A.

Obliczenie CTP, w którym są rozważane zarówno materiały, jak i zasoby, może wykazać większą ilość niż obliczenie, w którym sprawdzane są tylko materiały, zwłaszcza w przypadku, gdy towar, który jest sprawdzany, jest towarem typu „składanie do zamówienia”. Innymi słowy, funkcja CTP jest oparta na funkcji rozłożenia i może być uruchamiana dla wybranego wiersza zamówienia sprzedaży w celu obliczenia oczekiwanej daty dostawy.

## <a name="how-ctp-differs-depending-on-the-master-planning-engine-that-you-use"></a>Różnice CTP w zależności od wybranego aparatu planowania głównego

W poniższej tabeli podsumowano różnice między CTP dla optymalizacji planowania a CTP dla wbudowanego aparatu planowania głównego.

| Element | Optymalizacja planowania | Wbudowany aparat planowania głównego |
|---|---|---|
| **Ustawienie kontroli daty dostawy** dla zamówień, wierszy zamówień i produktów | *CTP dla optymalizacji planowania* | *CTP* |
| Godzina obliczania | Obliczanie jest wyzwalane przez uruchomienie planu dynamicznego jako zaplanowanego zadania. | Obliczenie jest natychmiast wyzwalane po każdym wprowadzeniu lub zaktualizowaniu wiersza zamówienia sprzedaży. |
| Wartość pola **Stan CTP dla optymalizacji planowania** | <p>Wartość Nie gotowe *jest wyświetlana* dla zamówień i wierszy zamówienia, w których plan dynamiczny nie został uruchomiony od czasu utworzenia lub ostatniej aktualizacji zamówień i wierszy.</p><p>Wartość *Gotowa* jest wyświetlana dla zamówień i wierszy, w których CTP zostało użyte do obliczenia potwierdzonych dat dostawy przez uruchomienie planu dynamicznego.</p> | Zawsze jest wyświetlana *wartość Gotowe*. |

## <a name="set-default-delivery-date-control-methods"></a><a name="default-methods"></a>Ustaw domyślne metody kontroli daty dostawy

System może używać dowolnej z kilku metod do obliczania szacunków daty dostawy dla każdego zamówienia i wiersza zamówienia. Należy ustawić metodę kontroli daty dostawy, która ma być najczęściej używaną jako globalna metoda domyślna. Możesz również ustawić indywidualne nadpisania dla każdego produktu. Później będzie można zastąpić domyślne metody dla każdego zamówienia i/lub wiersza zamówienia zgodnie z jego wymogami.

### <a name="set-the-global-default-delivery-date-control"></a><a name="global-default"></a>Ustaw globalną domyślną kontrolę daty dostawy

Domyślna metoda kontroli daty dostawy zostanie zastosowana do wszystkich nowych wierszy zamówienia, w których nie ma zastosowania zastąpienie. Aby wybrać jeden, wykonaj następujące kroki.

1. Wybierz kolejno pozycje **Rozrachunki z odbiorcami \> Ustawienia \> Parametry modułu rozrachunków z odbiorcami**.
1. Na karcie **Wysyłki**, na skróconej karcie **Kontrola dostawy** w polu **Kontrola daty dostawy** wybierz metodę, która ma być stosowana jako domyślna metoda dla firmy:

    - *Brak* – Nie obliczaj terminów dostaw.
    - *Czas realizacji sprzedaży* — Czas realizacji sprzedaży to okres od utworzenia zamówienia sprzedaży do wysyłki towarów. Obliczenie daty dostawy opiera się na domyślne liczbie dni i nie uwzględnia dostępności zapasu, znanego popytu ani planowanej podaży.
    - *ATP* — ATP to dostępna ilość towaru, która może zostać zarezerwowana dla odbiorcy na konkretny dzień. Obliczanie ATP obejmuje niezatwierdzone zapasy, czasy realizacji, planowane przychody i rozchody.
    - *ATP + Zapas czasu dla rozchodu* — data wysyłki jest równa dacie ATP plus zapas czasu dla rozchodu w odniesieniu do towaru. Jest to czas potrzebny na przygotowanie towaru do wysyłki.
    - *CTP* — użyj obliczenia CTP dostarczanego przez wbudowany aparat planowania głównego. Jeśli używasz optymalizacji planowania, *metoda kontroli daty dostawy CTP* jest niedozwolone i jeśli jest zaznaczona, spowoduje błąd podczas wykonywania obliczeń.
    - *CTP dla optymalizacji planowania* — użyj obliczenia CTP dostarczanego przez optymalizację planowania. Ta opcja nie ma wpływu, jeśli używasz wbudowanego głównego aparatu planowania.

### <a name="set-delivery-date-control-overrides-for-individual-products"></a>Ustawienie zastąpień kontroli daty dostawy dla poszczególnych produktów

Można przypisać zastąpienia określonych produktów, dla których ma być stosowana metoda kontroli daty dostawy inna niż metoda ustawiona jako globalna metoda domyślna.

1. Przejdź do **Zarządzanie informacjami o produktach\> Produkty \> Zwolnione produkty**.
1. Wybierz produkt, który chcesz skonfigurować.
1. W okienku akcji na karcie **Zarządzaj zapasami** w grupie **Ustawienia zamówienia** wybierz opcję **Ustawienia domyślne zamówień**.
1. Na stronie **Ustawienia domyślne zamówienia** na skróconej karcie **Zamówienie sprzedaży** ustaw opcję **Kontroli zastępowania dostawy** o wartości *Tak*.
1. W polu **Kontrola daty dostawy** wybierz metodę, która ma być stosowana dla wybranego produktu. Dostępne są te same opcje, które opisano w sekcji [Ustawianie globalnej domyślnej](#global-default) kontroli daty dostawy.

## <a name="schedule-ctp-for-planning-optimization-calculations"></a><a name="batch-job"></a>Planowanie CTP dla obliczeń optymalizacji planowania

Jeśli do optymalizacji planowania jest używać protokołu CTP, należy uruchomić plan dynamiczny, aby wyzwolić system do obliczeń CTP, a następnie ustawić potwierdzone daty wysyłki i przyjęcia dla wszystkich odpowiednich zamówień. Plan musi obejmować wszystkie pozycje, dla których są wymagane potwierdzone daty wysyłki i przyjęcia. (Gdy do korzystania z CTP jest wbudowany aparat planowania, obliczenia CTP są natychmiast wykonywane lokalnie. Z tego powodu nie trzeba uruchamiać planu dynamicznego, aby zobaczyć wyniki CTP)

Aby zapewnić, że daty będą dostępne w odpowiednim czasie dla wszystkich użytkowników, zaleca się cykliczne konfigurowanie zadań wsadowych. Na przykład zadanie wsadowe, w przypadku których plan dynamiczny jest uruchamiany co 30 minut, spowoduje ustawienie potwierdzonych dat wysyłki i odbioru co 30 minut. Dlatego użytkownicy, którzy wprowadzają i importują zamówienia, muszą czekać maksymalnie 30 minut na otrzymanie potwierdzonych dat wysyłki i odbioru.

Aby skonfigurować zadanie wsadowe do uruchamiania planu dynamicznego zgodnie z harmonogramem regularnym, należy wykonać następujące kroki.

1. Wybierz kolejno opcje **Planowanie główne \> Planowanie główne \> Uruchom \> Planowanie główne**.
1. W oknie dialogowym **Planowanie główne**, na skróconej **karcie Parametry** ustaw w polu **Plan główny** na plan dynamiczny, który ma zostać uruchomiony.
1. Na karcie skróconej **Uruchom w tle** należy skonfigurować opcję **Przetwarzanie wsadowe** na wartość *Tak*.
1. Wybierz **opcję Powtarzaj** i w razie potrzeby skonfiguruj harmonogram.
1. Wybierz przycisk **OK**, aby zapisać harmonogram.
1. Naciśnij przycisk **OK**, aby utworzyć zadanie wsadowe i zamknąć okno dialogowe.

## <a name="use-ctp-for-built-in-master-planning"></a>Użyj CTP do wbudowanego planowania głównego

### <a name="create-a-new-order-by-using-ctp-for-built-in-master-planning"></a>Tworzenie nowego zamówienia przy użyciu protokołu CTP dla wbudowanego planowania głównego

Po każdym dodaniu nowego zamówienia sprzedaży lub wiersza zamówienia system przypisuje do niego domyślną metodę kontroli daty dostawy. Nagłówek zamówienia zawsze zaczyna się od globalnej metody domyślnej. Jeśli zamówiony towar zostanie przypisany do zastąpienia, zastąpienia będą używać w nowym wierszu zamówienia. W przeciwnym razie nowy wiersz zamówienia użyje także globalnej metody domyślnej. Dlatego należy ustawić metody domyślne tak, aby były zgodne z najczęściej używaną metodą kontroli daty dostawy. Po utworzeniu zamówienia można zastąpić domyślną metodę na poziomie nagłówka i/lub wiersza zamówienia. Aby uzyskać więcej informacji, zobacz temat [Ustaw domyślne metody kontroli daty dostawy](#default-methods) i [Zmień istniejące zamówienia sprzedaży, aby używać CTP](#change-orders).

### <a name="view-confirmed-delivery-dates-when-you-use-ctp-for-built-in-master-planning"></a>Wyświetlanie potwierdzonych dat dostawy przy używaniu CTP dla wbudowanego planowania głównego

Jeśli używasz wbudowanego aparatu planowania głównego, obliczenia CTP są stosowane do zamówień lub wierszy zamówień, w których w polu **kontroli daty dostawy** jest ustawiona wartość *CTP*.

W przypadku wierszy sprzedaży, które używają CTP do wbudowanego planowania głównego, system automatycznie ustawia pola **Potwierdzona data wysyłki** i **Potwierdzona data przyjęcia** za każdym razem, gdy zapisywany jest wiersz sprzedaży. Jeśli później dokonasz odpowiedniej zmiany w wierszu sprzedaży (na przykład przez zmianę ilości lub działu), daty zostaną natychmiast ponownie przeliczone.

- Aby wyświetlić potwierdzone daty dostawy dla wiersza zamówienia sprzedaży, otwórz zamówienie sprzedaży i wybierz wiersz sprzedaży. Następnie w **Szczegóły wiersza** skróconej karcie **Dostawa** sprawdź wartości **Potwierdzona data wysyłki** **Potwierdzona data odbioru**.
- Aby wyświetlić potwierdzone daty dostawy dla całego zamówienia, otwórz zamówienie sprzedaży i wybierz widok **Nagłówek**. Następnie w Szczegóły wiersza skróconej karcie **Dostawa** sprawdź wartości **Potwierdzona data wysyłki** i **Potwierdzona data odbioru**.

## <a name="use-ctp-for-planning-optimization"></a>Użyj CTP dla optymalizacji planowania

### <a name="create-a-new-order-by-using-ctp-for-planning-optimization"></a>Utwórz nowe zamówienie za pomocą CTP do optymalizacji planowania

Po każdym dodaniu nowego zamówienia sprzedaży lub wiersza zamówienia system przypisuje do niego domyślną metodę kontroli daty dostawy. Nagłówek zamówienia zawsze zaczyna się od globalnej metody domyślnej. Jeśli zamówiony towar zostanie przypisany do zastąpienia, zastąpienia będą używać w nowym wierszu zamówienia. W przeciwnym razie nowy wiersz zamówienia użyje także globalnej metody domyślnej. Dlatego należy ustawić metody domyślne tak, aby były zgodne z najczęściej używaną metodą kontroli daty dostawy. Po utworzeniu zamówienia można zastąpić domyślną metodę na poziomie nagłówka i/lub wiersza zamówienia. Aby uzyskać więcej informacji, zobacz temat [Ustaw domyślne metody kontroli daty dostawy](#default-methods) i [Zmień istniejące zamówienia sprzedaży, aby używać CTP](#change-orders).

### <a name="view-confirmed-delivery-dates-when-using-ctp-for-planning-optimization"></a>Wyświetlanie potwierdzonych dat dostawy przy używaniu CTP do optymalizacji planowania

Jeśli korzystasz z Optymalizacji planowania, obliczenia CTP są stosowane do zamówień lub wierszy zamówień, w których w polu **kontroli daty dostawy** jest ustawiona wartość *CTP dla Optymalizacji planowania*.

W przypadku wierszy sprzedaży korzystających z CTP w celu optymalizacji planowania pola **Potwierdzona data wysyłki** i **Potwierdzona data przyjęcia** będą puste, dopóki nie zostanie uruchomiony odpowiedni plan dynamiczny (zazwyczaj za pomocą okresowego zadania wsadowego). Są one ustawiane automatycznie. Aby uzyskać więcej informacji, zobacz temat [Harmonogram CTP dla obliczeń optymalizacji planowania](#batch-job).

Pole Stan **CTP optymalizacji planowania** wskazuje, czy potwierdzone daty zostały jeszcze obliczone dla każdego wiersza, w przypadku których jest używany CTP do optymalizacji planowania. W tym polu jest przedstawiana wartość *Nie gotowe* dla wierszy i zamówień, w których potwierdzone daty dostawy nie zostały jeszcze obliczone lub nie są już ważne z powodu innych zmian. Pokazuje wartość *Gotowe* dla wierszy i zamówień, które zostały obliczone. Można wyświetlić stan każdego wiersza i całego zamówienia.

- Aby wyświetlić stan dla wiersza zamówienia sprzedaży, otwórz zamówienie sprzedaży i wybierz wiersz sprzedaży. Następnie na skróconej **karcie Szczegóły wiersza**, na karcie **Dostawa**, sprawdź **wartość stanu optymalizacji planowania CTP**. Pola **Potwierdzona data wysyłki** i **Potwierdzona data przyjęcia** dla wiersza są także wyświetlane na tej karcie po ich obliczeniu.
- Aby wyświetlić stan dla całego zamówienia, otwórz zamówienie sprzedaży i wybierz widok **Nagłówek**. Następnie na karcie **Dostawa**, sprawdź wartość stanu **optymalizacji planowania CTP**. Pola **Potwierdzona data wysyłki** i **Potwierdzona data przyjęcia** dla zamówienia są również wyświetlane na tej karcie po ich obliczeniu.

<!-- KFM: The following text may be untrue and needs to be reviewed with the PM for next revision:

The sales orders that are *Ready* or *Not ready* are shown in the **All sales orders** list page. You can check the sales order that are *Ready* or *Not ready* from the sales order list page by filtering on this new status field.

-->

> [!NOTE]
> - Jeśli wiersz zamówienia sprzedaży zostanie uaktualniony po obliczeniu dla niego potwierdzonych dat przez CTP dla optymalizacji planowania, system wyczyści te daty do czasu następnego uruchomienia odpowiedniego planu dynamicznego.
> - W przypadku edytowania powiązanego ustawienia, które może mieć wpływ na istniejące potwierdzone daty (na przykład przez zmianę czasów realizacji, rezerwacji lub oznaczeń), należy wyczyścić potwierdzone daty odpowiednich istniejących zamówień. Ta akcja spowoduje, że stan każdego odpowiedniego wiersza zostanie zmieniony na *Nie gotowy*. Ta zmiana z kolei spowoduje ponowne obliczanie przez system potwierdzonych dat przy kolejnym uruchamiania planu dynamicznego.

## <a name="change-existing-sales-orders-so-that-they-use-ctp"></a><a name="change-orders"></a>Zmień istniejące zamówienia sprzedaży, tak aby były one używać CTP

W dowolnym momencie można **zmienić wartość kontroli daty** dostawy dla dowolnego otwartego zamówienia. W wymaganym przypadku można zmienić wartość na poziomie nagłówka i/lub dla każdego wiersza.

### <a name="change-to-ctp-at-the-order-header-level"></a>Zmień na CTP na poziomie nagłówka zamówienia

<!-- KFM: Would be nice to mention how changing this setting on the header affects the individual lines. -->

Aby zmienić zamówienie, tak aby na poziomie nagłówka zamówienia były używane CTP, należy wykonać następujące kroki.

1. Przejdź do pozycji **Rozrachunki z odbiorcami \> Zamówienia \> Wszystkie zamówienia sprzedaży**.
1. Otwórz zamówienie sprzedaży, które chcesz skonfigurować, lub utwórz nowe.
1. Wybierz opcję **Nagłówek**, aby wyświetlić nagłówek zamówienia na stronie **nowego zamówienia sprzedaży**.
1. Na skróconej **karcie Dostawa** ustaw w polu **Kontrola daty dostawy** jedną z następujących wartości, w zależności od wybranego aparatu planowania:

    - *CTP* — użyj obliczenia CTP dostarczanego przez wbudowany aparat planowania głównego. Jeśli używasz optymalizacji planowania, nie jest dozwolona metoda kontroli daty dostawy *CTP*. W przypadku wybrania tej wartości podczas wykonywania obliczeń wystąpi błąd.
    - *CTP dla optymalizacji planowania* — użyj obliczenia CTP dostarczanego przez optymalizację planowania. Ta opcja nie ma wpływu, jeśli używasz wbudowanego głównego aparatu planowania.

<!-- KFM: Additional dialogs are shown here. Review these with the PM and expand this procedure at next revision. -->
1. Wybierz **OK**, aby zastosować zmiany.

### <a name="change-to-ctp-at-the-order-line-level"></a>Zmień na CTP na poziomie wiersza zamówienia

Jeśli wiersz zamówienia utworzono przy użyciu innej metody kontroli daty dostawy, w dowolnym momencie można zmienić na CTP. Zmiany wprowadzone na poziomie wiersza nie mają wpływu na żadne inne wiersze. W zależności od zmian wprowadzonych w obliczeniach poszczególnych zaktualizowanych wierszach zmiany mogą jednak spowodować przesuwanie się do przodu lub wstecz ogólnych dat dostawy zamówień. <!-- KFM: Confirm this intro at next revision -->

Aby zmienić zamówienie tak, aby używało CTP do wbudowanego planowania głównego na poziomie wiersza, wykonaj następujące kroki.

1. Przejdź do pozycji **Rozrachunki z odbiorcami \> Zamówienia \> Wszystkie zamówienia sprzedaży**.
1. Otwórz zamówienie sprzedaży, które chcesz skonfigurować, lub utwórz nowe.
1. Na stronie **Szczegóły zamówienia** sprzedaży, na skróconej karcie **Wiersz zamówienia sprzedaży** zaznacz wiersz zamówienia sprzedaży, który chcesz skonfigurować.
1. Na **Szczegóły wiersza** skrócona karta na karcie **Delivery** ustaw w polu **Kontrola daty dostawy** jedną z następujących wartości, w zależności od używanego mechanizmu planowania:

    - *CTP* — użyj obliczenia CTP dostarczanego przez wbudowany aparat planowania głównego. Jeśli używasz optymalizacji planowania, nie jest dozwolona metoda kontroli daty dostawy *CTP*. W przypadku wybrania tej wartości podczas wykonywania obliczeń wystąpi błąd.
    - *CTP dla optymalizacji planowania* — użyj obliczenia CTP dostarczanego przez optymalizację planowania. Ta opcja nie ma wpływu, jeśli używasz wbudowanego głównego aparatu planowania.

    Zostanie **wyświetlone okno dialogowe Dostępne** daty wysyłki i przyjęcia, w których są wyświetlane dostępne daty wysyłki i przyjęcia. To okno dialogowe działa w taki sam sposób, jak wiersze zamówienia w nagłówku zamówienia, jak to opisano w poprzedniej sekcji.

1. Na okienku akcji wybierz opcję **Zapisz**.
