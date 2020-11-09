---
title: Zasady pracy
description: W tym temacie opisano sposób konfigurowania zasad pracy.
author: perlynne
manager: tfehr
ms.date: 07/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWorkPolicy
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-07-31
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: 08c04caeace7b8ced40915ace1561d817426cba3
ms.sourcegitcommit: a36a4f9915ae3eb36bf8220111cf1486387713d9
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/16/2020
ms.locfileid: "4017674"
---
# <a name="work-policies"></a>Zasady pracy

[!include [banner](../includes/banner.md)]

W tym temacie wyjaśniono, jak skonfigurować system i aplikację magazynu, tak aby obsługiwała ona zasady pracy. Funkcji tej można używać do szybkiego rejestrowania zapasów bez tworzenia odkładów w przypadku przyjmowania zamówień zakupu lub przenoszenia lub podczas kończenia procesów produkcyjnych. Ten temat zawiera ogólne informacje. Aby uzyskać szczegółowe informacje związane z otrzymywaniem numeru identyfikacyjnego, zobacz [Odbieranie numerów identyfikacyjnych za pomocą aplikacji magazynowej](warehousing-mobile-device-app-license-plate-receiving.md).

Zasady pracy kontrolują, czy praca magazynowa jest tworzona, gdy wyprodukowany towar jest raportowany jako gotowy, czy gdy towary są przyjmowane za pomocą aplikacji magazynowej. Poszczególne zasady pracy definiuje się, definiując warunki ich zastosowania: typy i procesy zlecenia produkcyjnego, lokalizacja magazynu oraz (opcjonalnie) produkty. Na przykład zamówienie zakupu dotyczące produktu *A0001* musi zostać odebrane w lokalizacji *RECV* w magazynie *24*. Później produkt jest zużywany w innym procesie w lokalizacji *RECV*. W takim przypadku można skonfigurować zasady pracy, aby zapobiec tworzeniu pracy odkładanej, gdy pracownik zgłasza produkt *A0001* otrzymany w lokalizacji *RECV*.

> [!NOTE]
> - Aby zasada pracy była aktywna, należy zdefiniować co najmniej jedną lokalizację na skróconej karcie **Lokalizacji zapasów** na stronie **Zasady pracy**. 
> - Nie można określić tej samej lokalizacji dla wielu zasad pracy.
> - Opcja **Drukuj etykietę** dla elementów menu urządzenia mobilnego nie powoduje wydrukowania etykiety tablicy rejestracyjnej, chyba że utworzono pracę.

## <a name="activate-the-features-in-your-system"></a>Aktywuj funkcje w systemie

Aby wszystkie funkcje opisane w tym temacie były dostępne w systemie, włącz następujące dwie funkcje w [Zarządzaniu funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md):

- Ulepszenia przyjmowania numeru identyfikacyjnego
- Usprawnienia zasad pracy dla pracy przychodzącej

## <a name="the-work-policies-page"></a>Strona Zasady pracy

Aby skonfigurować zasady pracy, przejdź do **Zarządzanie magazynem \> Konfiguracja \> Praca \> Zasady pracy**. Następnie na każdej skróconej karcie należy określić pola opisane w poniższych podsekcjach.

### <a name="the-work-order-types-fasttab"></a>Skrócona karta typy zleceń pracy

Na skróconej karcie **Typy zleceń pracy** dodaj wszystkie typy zleceń i powiązane z nimi procesy pracy, których dotyczy zasada pracy. Dla zasad pracy są obsługiwane następujące typy zleceń pracy i powiązane procesy pracy.

| Typ zlecenia | Proces pracy |
|---|---|
| Pobranie surowca| Wszystkie powiązane procesy |
| Odłożenie produktu ubocznego i produktu towarzyszącego | Wszystkie powiązane procesy |
| Ukończono odkładanie wyrobów | Wszystkie powiązane procesy |
| Przyjęcie przeniesienia | Odbieranie numeru identyfikacyjnego (i odłożenie) |
| Zamówienia zakupu | <ul><li>Odbieranie numeru identyfikacyjnego (i odłożenie)</li><li>Odbierana pozycja ładunku (i odłożona)</li><li>Przyjęcie wiersza zamówienia zakupu (i odłożenie)</li><li>Przyjęcie pozycji z zamówienia zakupu (i odłożenie)</li></ul> |

Aby skonfigurować zasady pracy tak, aby miały zastosowanie do kilku procesów pracy tego samego typu, dodaj do siatki oddzielny wiersz dla każdego procesu pracy.

Dla każdego wiersza w siatce w polu **Metoda tworzenia pracy** należy określić jedną z następujących wartości:

- **Nigdy** – Zasada pracy uniemożliwi tworzenie pracy magazynowej dla wybranego typu zlecenia i powiązane procesy pracy.
- **Przeładunek kompletacyjny** — zasada pracy utworzy pracę przeładunku komplementarnego przy użyciu zasad wybranych w polu **Nazwa zasady przeładunku kompletacyjnego**.

### <a name="the-inventory-locations-fasttab"></a>Skrócona karta lokalizacji zapasów

Na skróconej karcie **Lokalizacji zapasów** dodaj wszystkie lokalizacje, w których ma zostać zastosowana ta zasada pracy. Jeśli żadna lokalizacja nie jest skojarzona z zasadami pracy, zasady pracy nie będą stosowane do żadnego procesu.

Nie można określić tej samej lokalizacji dla wielu zasad pracy.

Możesz użyć lokalizacji magazynu przypisanej do profilu lokalizacji, w której opcja **Śledzenie numerów identyfikacyjnych** nie jest włączona. W takim przypadku pracownicy mogą bezpośrednio rejestrować dostępne zapasy.

### <a name="the-products-fasttab"></a>Skrócona karta produktów

Na karcie **Produkty** zaznacz pole **Wybór produktu** , aby określić, które produkty mają być stosowane w zasadach:

- **Wszystko** — zasady powinny być stosowane do wszystkich produktów.
- **Zaznaczone** — zasady powinny być stosowane tylko w odniesieniu do produktów wymienionych w siatce. Za pomocą paska narzędzi na skróconej karcie **Produkty** można dodawać produkty do siatki lub usuwać je z siatki.

## <a name="default-and-custom-to-locations"></a>Domyślne i niestandardowe lokalizacje „do”

> [!NOTE]
> Aby funkcje opisane w tej sekcji były dostępne w systemie, należy włączyć funkcję *Numer identyfikacyjny odbieranający ulepszenia* i *Udoskonalenia zasad pracy dla pracy przychodzącej* w [Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

Poprzednio system obsługiwał odbieranie tylko w lokalizacji domyślnej zdefiniowanej dla każdego magazynu. Jednak elementy menu urządzenia przenośnego, które używają następujących procesów tworzenia pracy, dostarczają obecnie opcji **Zastosuj domyślne dane**. Ta opcja umożliwia przypisanie niestandardowej lokalizacji „do” do jednego lub wielu elementów menu. (Ta opcja jest już dostępna dla innych typów elementów menu.)

- Odbieranie numeru identyfikacyjnego (i odłożenie)
- Odbierana pozycja ładunku (i odłożona)
- Przyjęcie wiersza zamówienia zakupu (i odłożenie)
- Przyjęcie pozycji z zamówienia zakupu (i odłożenie)

Ustawienie **Do lokalizacji** dla elementu menu zastępuje domyślną lokalizację przyjęcia dla magazynu dla wszystkich zamówień, które są przetwarzane przy użyciu tego elementu menu.

Aby skonfigurować element menu urządzenia przenośnego w celu obsługi odbierania w niestandardowym miejscu, wykonaj następujące kroki.

1. Przejdź do pozycji **Zarządzanie magazynem \> Ustawienia \> Urządzenie przenośne \> Elementy menu urządzenia przenośnego**.
1. Wybierz lub utwórz element menu korzystający z jednego z procesów tworzenia pracy wymienionych wcześniej w tej sekcji.
1. Na skróconej karcie **Ogólne** ustaw opcje **Użyj danych domyślnych** na **Tak**.
1. W okienku akcji wybierz **Dane domyślne**.
1. Na stronie **Dane domyślne** ustaw następujące wartości:

    - **Domyślne pole danych:** to pole należy określić jako *Do lokalizacji*.
    - **Magazyn:** Wybierz magazyn docelowy, który ma być używany z tym elementem menu.
    - **Lokalizacja:** W tym polu są wyświetlane wszystkie identyfikatory lokalizacji, które są dostępne dla wybranego magazynu. Jednak ustawienie tego pola nie ma w rzeczywistości żadnego skutku. Dlatego możesz zostawić to pole puste. Niemniej jednak można skorzystać z listy, aby potwierdzić identyfikator, który należy wprowadzić w polu **Wartość zakodowana na stałe**.
    - **Wartość zakodowana na stałe:** należy wprowadzić identyfikator lokalizacji dla lokalizacji przyjęcia, która ma zastosowanie do tego elementu menu.

> [!TIP]
> Zasady pracy można stosować tylko w przypadku, gdy wszystkie lokalizacje przyjęcia są wymienione w odpowiedniej konfiguracji zasad pracy. To wymaganie ma zastosowanie niezależnie od tego, czy używasz domyślnej lokalizacji odbioru magazynu, czy niestandardowej lokalizacji „do”.

## <a name="example-scenario-warehouse-receiving"></a>Przykładowy scenariusz: przyjęcie w magazynie

Wszystkie produkty odbierane przez proces *Odbierania (i odkładania) zamówienia zakupu* muszą być zarejestrowane w lokalizacji *FL-001* i muszą być dostępne w magazynie *24*. Nie należy jednak tworzyć pracy. Produkty odbierane przez inny proces (to znaczy za pomocą innych elementów menu urządzeń przenośnych) powinny być rejestrowane w domyślnej lokalizacji przyjęcia ( *Odbierz* ), a praca powinna być tworzona w zwykły sposób. (W tym scenariuszu nie jest wyświetlana domyślna konfiguracja odbierania.)

Ten scenariusz wymaga następujących elementów:

- Zasada pracy dla procesu *Przyjęcie pozycji z zamówienia zakupu (i odłożenie)* w lokalizacji *FL-001* , dla wszystkich produktów
- Element menu urządzenia przenośnego z danymi domyślnymi, który ustawia pole **Do lokalizacji** na *FL-001*

### <a name="prerequisites"></a>Wymagania wstępne

Aby funkcje opisane w scenariuszu były dostępne w systemie, należy włączyć funkcję *Numer identyfikacyjny odbieranający ulepszenia* i *Udoskonalenia zasad pracy dla pracy przychodzącej* w [Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

W tym scenariuszu używane są standardowe dane demonstracyjne. Dlatego jeśli chcesz przez to przejść, używając podanych tutaj wartości, musisz pracować w systemie, w którym są zainstalowane dane demonstracyjne. Ponadto należy wybrać firmę **USMF**.

### <a name="set-up-a-work-policy"></a>Konfigurowanie zasady pracy

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Praca \> Zasady pracy**.
1. Wybierz pozycję **Nowy**.
1. W polu **Nazwa zasady pracy** wprowadź *Praca odkładania bez pozycji zakupu*.
1. Wybierz opcję **Zapisz**.
1. Na skróconej karcie **Typy zleceń pracy** wybierz opcję **Dodaj** , aby dodać wiersz do siatki, a następnie określ następujące wartości dla nowego wiersza:

    - **Typ zlecenia pracy:** *Zamówienie zakupu*
    - **Proces pracy:** *Przyjęcie pozycji z zamówienia zakupu (i odłożenie)*
    - **Metoda tworzenia pracy:** *Nigdy*
    - **Nazwa zasady przeładunku kompletacyjnego:** Pozostaw to pole puste.

1. Na skróconej karcie **Lokalizacje w magazynie** wybierz opcję **Dodaj** , aby dodać wiersz do siatki, a następnie określ następujące wartości dla nowego wiersza:

    - **Magazyn:** *24*
    - **Lokalizacja:** *FL-001*

1. Na skróconej karcie **Produkty** w polu **Wybór produktu** wybierz wartość *Wszystkie*.
1. Wybierz opcję **Zapisz**.

### <a name="set-up-a-mobile-device-menu-item-to-change-the-receiving-location"></a>Skonfiguruj element menu urządzenia mobilnego, aby zmienić lokalizację odbioru

1. Przejdź do pozycji **Zarządzanie magazynem \> Ustawienia \> Urządzenie przenośne \> Elementy menu urządzenia przenośnego**.
1. W lewym okienku wybierz istniejący element menu **Przyjęcie zakupu**.
1. Na skróconej karcie **Ogólne** ustaw opcje **Użyj danych domyślnych** na *Tak*.
1. Wybierz opcję **Zapisz**.
1. W okienku akcji wybierz **Dane domyślne**.
1. W okienku akcji na stronie **Dane domyślne** wybierz opcję **Nowe** , aby dodać wiersz do siatki, a następnie określ następujące wartości dla nowego wiersza:

    - **Domyślne pole danych:** *Do lokalizacji*
    - **Magazyn:** *24*
    - **Lokalizacja:** Pozostaw to pole puste.
    - **Wartość zakodowana na stałe:** *FL-001*

1. Wybierz opcję **Zapisz**.

### <a name="receive-a-purchase-order-without-creating-work"></a>Odbiór zamówienia zakupu bez tworzenia pracy

W przykładzie w tej sekcji przedstawiono sposób przyjmowania towaru zamówienia zakupu, ale bez tworzenia pracy, w lokalizacji innej niż domyślna lokalizacja przyjęcia skonfigurowana dla danego magazynu. W tym przykładzie użyto elementu zasady pracy i urządzenia przenośnego utworzonego wcześniej w tym scenariuszu.

#### <a name="create-a-purchase-order"></a>Tworzenie zamówienia zakupu

1. Wybierz kolejno opcje **Zaopatrzenie i sourcing \> Zamówienia zakupu \> Wszystkie zamówienia zakupu**.
1. Wybierz pozycję **Nowy**.
1. W wyświetlonym oknie dialogowym **Utwórz zamówienie zakupu** można ustawić następujące wartości:

    - **Konto dostawcy:** *US-101*
    - **Oddział:** *2*
    - **Magazyn:** *24*

1. Naciśnij przycisk **OK** , aby zamknąć okno dialogowe i otworzyć nowe zamówienie zakupu.
1. Na skróconej **Wiersze zamówienia zakupu** określ następujące wartości pustego wiersza:

    - **Numer pozycji:** *A0001*
    - **Ilość:** *1*

1. Wybierz opcję **Zapisz**.
1. Zanotuj numer zamówienia zakupu.

#### <a name="receive-a-purchase-order"></a>Odbiór zamówienia zakupu

1. Na urządzeniu mobilnym zaloguj się do magazynu *24* , używając *24* jako identyfikatora użytkownika i *1* jako hasła.
1. Wybierz opcję **Przychodzące**.
1. Wybierz opcję **Przyjęcie zakupu**. Pole **Lokalizacja** powinno mieć wartość *FL-001*.
1. Umożliwia wprowadzenie numeru zamówienia zakupu dla zamówienia zakupu utworzonego w poprzedniej procedurze.
1. W polu **Numer pozycji** wpisz *A0001*.
1. Kliknij przycisk **OK**.
1. W polu **Ilość** wpisz wartość *1*.
1. Kliknij przycisk **OK**.

Zamówienie zakupu jest teraz otrzymane, ale nie skojarzono z nim żadnej pracy. Dostępne zapasy zostały zaktualizowane, a ilość *1* pozycji *A0001* jest obecnie dostępna w lokalizacji *FL-001*.

## <a name="example-scenario-manufacturing"></a>Przykładowy scenariusz: produkcja

W poniższym przykładzie istnieją dwa zlecenia produkcyjne, *PRD-001* i *PRD-002*. Zlecenie produkcyjne *PRD-001* zawiera operację o nazwie *Montaż* , z której produkt *SC1* jest zgłaszany jako gotowy do lokalizacji *001*. Zlecenie produkcyjne *PRD-002* ma operację o nazwie *Malowanie* i zużywa produkt *SC1* z lokalizacji *001*. Zlecenie produkcyjne *PRD-002* zużywa także surowiec *RM1* z lokalizacji *001*. Surowiec *RM1* jest przechowywany w lokalizacji magazynowej *BULK-001* i zostanie pobrany do lokalizacji *001* za pomocą pracy magazynowej pobrania materiału. Praca pobierania jest generowana po zwolnieniu produkcji *PRD-002*.

[![Zasady pracy magazynowej](./media/warehouse-work-policies.png)](./media/warehouse-work-policies.png)

Planując skonfigurowanie zasad pracy magazynu dla tego scenariusza, należy wziąć pod uwagę następujące kwestie:

- Praca magazynowa odłożenia wyrobów gotowych nie jest wymagana, jeżeli zgłaszasz produkt *SC1* jako gotowy ze zlecenia produkcyjnego *PRD-001* do lokalizacji *001*. Wynika to z faktu, że operacja *Malowanie* dla zlecenia produkcyjnego *PRD-002* zużywa produkt *SC1* w tej samej lokalizacji.
- Praca magazynowa pobrania surowca jest wymagana w celu przeniesienia surowca *RM1* z lokalizacji magazynowej *BULK-001* do lokalizacji *001*.

Oto przykład zasady pracy, którą można skonfigurować z uwzględnieniem powyższych informacji:

- **Nazwa zasady pracy:** *Brak pracy odkładania*
- **Typy zleceń pracy:** *Ukończono odkładanie wyrobów* i *Odłożenie produktu ubocznego i produktu towarzyszącego*
- **Lokalizacje zapasów:** Magazyn *51* i lokalizacja *001*
- **Produkty:** *SC1*

Poniższy przykładowy scenariusz zawiera instrukcje krok po kroku dotyczące konfigurowania zasad pracy magazynu dla tego scenariusza.

## <a name="example-scenario-report-as-finished-to-a-location-that-isnt-license-platecontrolled"></a>Przykładowy scenariusz: Zgłoś jako gotowe do lokalizacji, która nie jest kontrolowana przez tablice rejestracyjne

W tym scenariuszu przedstawiono przykład, w którym zlecenie produkcyjne jest zgłaszane jako gotowe do lokalizacji, która nie jest kontrolowana przez tablice rejestracyjne.

W tym scenariuszu używane są standardowe dane demonstracyjne. Dlatego jeśli chcesz przez to przejść, używając podanych tutaj wartości, musisz pracować w systemie, w którym są zainstalowane dane demonstracyjne. Ponadto należy wybrać firmę **USMF**.

### <a name="set-up-a-warehouse-work-policy"></a>Konfigurowanie zasady pracy magazynowej

Procesy magazynowe nie zawsze obejmują pracę magazynową. Poprzez zdefiniowanie pracy magazynowej można zablokować tworzenie pracy pobierania surowców i odkładania wyrobów gotowych dla zbioru produktów w określonych lokalizacjach.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Praca \> Zasady pracy**.
1. Wybierz pozycję **Nowy**.
1. W polu **Nazwa zasady pracy** wprowadź *Brak pracy odkładania*.
1. Na okienku akcji wybierz opcję **Zapisz**.
1. Na skróconej karcie **Typy zleceń pracy** wybierz opcję **Dodaj** , aby dodać wiersz do siatki, a następnie określ następujące wartości dla nowego wiersza:

    - **Typ zlecenia pracy:** *Odłożenie wyrobów gotowych*
    - **Proces pracy:** *wszystkie powiązane procesy pracy*
    - **Metoda tworzenia pracy:** *Nigdy*
    - **Nazwa zasady przeładunku kompletacyjnego:** Pozostaw to pole puste.

1. Wybierz ponownie opcję **Dodaj** , aby dodać drugi wiersz do siatki, a następnie określ następujące wartości dla nowego wiersza:

    - **Typ zlecenia pracy:** *Odłożenie produktu ubocznego i produktu towarzyszącego*
    - **Proces pracy:** *wszystkie powiązane procesy pracy*
    - **Metoda tworzenia pracy:** *Nigdy*
    - **Nazwa zasady przeładunku kompletacyjnego:** Pozostaw to pole puste.

1. Na skróconej karcie **Lokalizacje w magazynie** wybierz opcję **Dodaj** , aby dodać wiersz do siatki, a następnie określ następujące wartości dla nowego wiersza:

    - **Magazyn:** *51*
    - **Lokalizacja:** *001*

1. Na skróconej karcie **Produkty** w polu **Wybór produktu** wybierz wartość *Wybrane*.
1. Na skróconej karcie **Produkty** wybierz opcję **Dodaj** , aby dodać wiersz do siatki.
1. W nowym wierszu należy określić wartość w polu **Kod towaru** na *L0101*.
1. Na okienku akcji wybierz opcję **Zapisz**.

### <a name="set-up-an-output-location"></a>Konfigurowanie lokalizacji wyjściowej

1. Wybierz kolejno opcje **Administrowanie organizacją \> Zasoby \> Grupy zasobów**.
1. W okienku po lewej zaznacz grupę zasobów **5102**.
1. Na skróconej karcie **Ogólne** ustaw następujące wartości:

    - **Magazyn wyjściowy:** *51*
    - **Lokalizacja wyjściowa:** *001*

1. Na okienku akcji wybierz opcję **Zapisz**.

> [!NOTE]
> Lokalizacja *001* nie jest lokalizacją kontrolowaną przez numer identyfikacyjny. Można skonfigurować lokalizację wyjściową niekontrolowaną za pomocą numeru identyfikacyjnego, ale tylko wtedy, gdy istnieje odpowiednia zasada pracy dla lokalizacji.

### <a name="create-a-production-order-and-report-it-as-finished"></a>Tworzenie zlecenia produkcyjnego i zgłaszanie go jako gotowego

1. Wybierz kolejno opcje **Kontrola produkcji \> Zlecenia produkcyjne \> Wszystkie zlecenia produkcyjne**.
1. W okienku akcji kliknij opcję **Nowe zlecenie produkcyjne**.
1. W oknie dialogowym **Tworzenie zlecenia produkcyjnego** w polu **Kod towaru** określ wartość *L0101*.
1. Naciśnij przycisk **Utwórz** , aby zamknąć okno dialogowe i utworzyć nowe zamówienie.

    Nowe zlecenie produkcyjne zostanie dodane do siatki na stronie **Wszystkie zlecenia produkcyjne**.

    Umożliwia zachowanie nowego wybranego zlecenia produkcyjnego.

1. W okienku akcji na karcie **Zlecenie produkcyjne** w grupie **Proces** wybierz opcję **Szacowanie**.
1. W oknie dialogowym **Szacowanie** zapoznaj się z oszacowaniem, a następnie kliknij przycisk **OK** , aby zamknąć okno dialogowe.
1. W okienku akcji na karcie **Zlecenie produkcyjne** w grupie **Proces** wybierz opcję **Uruchom**.
1. W oknie dialogowym **Uruchom** na karcie **Ogólne** , w polu **Automatyczne zużycie BOM** określ wartość *Nigdy*.
1. Wybierz przycisk **OK** , aby zapisać ustawienie i zamknąć okienko dialogowe.
1. W okienku akcji na karcie **Zlecenie produkcyjne** w grupie **Proces** wybierz opcję **Zgłoszenie jako gotowe**.
1. W oknie dialogowym **Zgłoszenie jako gotowe** na karcie **Ogólne** zaznacz opcję **Akceptacja błędu** na *Tak*.
1. Wybierz przycisk **OK** , aby zapisać ustawienie i zamknąć okienko dialogowe.
1. W okienku akcji, na karcie **Magazyn** , w grupie **Ogólne** wybierz pozycję **Szczegóły pracy**.

Po zgłoszeniu zlecenia produkcyjnego jako gotowego nie została wygenerowana praca do odłożenia. Dzieje się tak, ponieważ zdefiniowano zasadę pracy, która blokuje generowanie pracy, gdy produkt *L0101* jest zgłaszany jako gotowy do lokalizacji *001*.

## <a name="more-information"></a>Więcej informacji

Aby uzyskać więcej informacji o elementach menu urządzeń przenośnych, zapoznaj się z tematem [Konfigurowanie urządzeń przenośnych do pracy magazynowej](configure-mobile-devices-warehouse.md).

Więcej informacji na temat otrzymywania tablic rejestracyjnych i zasad pracy, zobacz [Odbieranie numerów identyfikacyjnych za pomocą aplikacji magazynowej](warehousing-mobile-device-app-license-plate-receiving.md).

Aby uzyskać więcej informacji o zarządzaniu ładunkami przychodzącymi, zajrzyj do [Obsługa magazynów dla ładunków przychodzących dla zamówień zakupu](inbound-load-handling.md).
