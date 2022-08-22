---
title: Przed zaksięgowaniem w arkuszach udostępnij fizycznie towary gotowe
description: Gdy towar wytworzony zostanie zgłoszony jako gotowy, jest on zarejestrowany jako dostępny do dalszego fizycznego przetwarzania i księgowany jest jeden lub więcej arkuszy. W tym artykule opisano sposób odroczeń księgowania arkuszy przez włączenie ich do przetwarzania przez zadanie wsadowe w kolejce wiadomości.
author: johanhoffmann
ms.date: 08/02/2022
ms.topic: article
ms.search.form: ProdParameters, JmgProdParameters, InventLocation, JmgMES3PMessageProcessorMessage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2022-08-02
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: 7a8327552d9e6c38721fdac9ee1795e61f90f329
ms.sourcegitcommit: 8d072505f66f507aafbaae65bedf3b530eb6cb7b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9266490"
---
# <a name="make-finished-goods-physically-available-before-posting-to-journals"></a>Przed zaksięgowaniem w arkuszach udostępnij fizycznie towary gotowe

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

Gdy pracownik zgłasza wytworzony towar jako gotowy, system rejestruje go jako dostępny do dalszego fizycznego przetwarzania (np. wysyłki lub odłożenia). W czasie tego procesu księgowany jest również jeden lub więcej arkuszy (na przykład arkusz zgłoszenia jako arkusz gotowy, arkusz listy pobrania i arkusz karty marszruty). Jeśli towary mają być fizycznie dostępne przed przetworzeniem wszystkich księgować, można skonfigurować system do odroczeń księgowania arkusza. Księgowanie odroczone jest następnie zarządzane przez zadanie wsadowe, które będzie przetwarzać księgowania zgodnie z zasobami systemowym.

Na poniższej ilustracji pokazano, jak procesy arkuszy księgowania są wywoływane zarówno z księgowaniem odroczonym, jak i bez.

![Proces zgłaszania gotowych z księgowaniem arkusza odroczonego lub bez niego.](media/deferred-posting-flowchart.png "Proces zgłaszania gotowych z księgowaniem arkusza odroczonego lub bez niego")

## <a name="turn-on-deferred-journal-posting-for-your-system"></a>Włącz księgowanie odroczonego arkusza dla systemu

Zanim będzie można korzystać z odroczonego księgowania dziennika, należy je włączyć w systemie. Administratorzy mogą skorzystać z obszaru roboczego [Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby sprawdzić stan funkcji i włączyć ją. W obszarze roboczym **Zarządzanie funkcjami** ta funkcja widnieje jako:

- **Moduł:** *Kontrola produkcji*
- **Nazwa funkcji:** *(Wersja zapoznawcza) Przed zaksięgowaniem w arkuszach udostępnij fizycznie towary gotowe*

## <a name="set-up-journal-posting-options-for-reporting-as-finished"></a>Ustaw opcje księgowania arkusza do zgłaszania jako gotowe

Pracownicy mogą zgłaszać towary jako gotowe za pomocą dowolnego z następujących klientów:

- Klient sieci Web
- Aplikacja mobilna Warehouse Management
- Interfejs wykonania hal produkcyjnych

Klient sieci web używa tej samej konfiguracji metody księgowania, co aplikacja mobilna Warehouse Management. Jednak metoda księgowania, z których korzysta interfejs wykonywania produkcji, musi być skonfigurowana osobno.

### <a name="set-journal-posting-options-for-the-web-client-and-the-warehouse-management-mobile-app"></a>Ustaw opcje księgowania arkusza dla klienta sieci web i aplikacji mobilnej Warehouse Management

W aplikacji mobilnej pracownicy zgłaszają elementy jako zakończone, otwierając pozycję menu urządzenia mobilnego, w której wartość **Proces tworzenia pracy** to *Zgłoś jako ukończone* lub *Zgłoś jako ukończone i odłożone*. W kliencie sieci web pracownicy zgłaszają towary jako gotowe ze strony listy **Wszystkie zlecenia produkcyjne** lub strony **szczegółów zlecenia produkcyjnego**. Można konfigurować metodę domyślną dla całej firmy, a także odpowiednio do potrzeb konfigurować zastąpienia specyficzne dla magazynu.

Użyj poniższej procedury, aby skonfigurować domyślną metodę księgowania w całej firmie na potrzeby raportowania towarów jako gotowych z klienta WWW lub aplikacji mobilnej Warehouse Management.

1. Wybierz kolejno opcje **Kontrola produkcji \> Ustawienia \> Wybierz kolejno opcje Kontrola produkcji**.
1. Na karcie **Arkusze** w sekcji **Arkusz zgłoszonych wyrobów gotowych** określ wartość w polu **Metoda księgowania** na jedną z następujących wartości:

    - *Natychmiastowe* — gdy towar zostanie zgłoszony jako gotowy, system w pełni przeprocesowuje wszystkie powiązane księgowania arkusza, zanim będzie oznaczał towar gotowy jako fizycznie dostępny.
    - *Odroczony* — Gdy towar zostanie zgłoszony jako gotowy, system oznacza gotowy towar jako fizycznie dostępny i dodaje księgowania dziennika do kolejki komunikatów. System nie czeka, dopóki księgowanie nie zostanie w pełni przetworzone, zanim stanie się gotowym towarem jako fizycznie dostępnym.

Użyj poniższej procedury, aby skonfigurować nadpisania specyficzne dla magazynu dla domyślnej metody księgowania skonfigurowanej na stronie **Parametry kontroli produkcji**.

1. Przejdź do pozycji **Warehouse management \> Konfiguracja \> Podział magazynu \> Magazyny**.
1. Wybierz magazyn, który chcesz skonfigurować.
1. W okienku akcji wybierz pozycję **Edytuj**.
1. Na karcie **Warehouse** w sekcji **Zlecenia produkcyjne** określ wartość w polu **Metoda księgowania** na jedną z następujących wartości:

    - *Dziedzicz* — wybrany magazyn dziedziczy ustawienie ze strony **Parametry kontroli** produkcji.
    - *Natychmiastowe* — gdy towar zostanie zgłoszony jako gotowy, system w pełni przeprocesowuje wszystkie powiązane księgowania arkusza, zanim będzie oznaczał towar gotowy jako fizycznie dostępny.
    - *Odroczony* — Gdy towar zostanie zgłoszony jako gotowy, system oznacza gotowy towar jako fizycznie dostępny i dodaje księgowania dziennika do kolejki komunikatów. System nie czeka, dopóki księgowanie nie zostanie w pełni przetworzone, zanim stanie się gotowym towarem jako fizycznie dostępnym.

### <a name="set-journal-posting-options-for-the-production-floor-execution-interface"></a>Ustaw opcje księgowania dziennika dla interfejsu wykonawczego hali produkcyjnej

Aby skonfigurować metodę księgowania, która jest używana, gdy towary są zgłoszone jako gotowe z interfejsu wykonywania produkcji, należy skorzystać z następującej procedury.

1. Przejdź do **Kontrola produkcji \> Ustawienia \> Wykonywanie produkcji \> Ustawienia domyślne zlecenia produkcyjnego**.
1. Na karcie **Zgłoś jako gotowe** w sekcji **Arkusz zgłoszonych wyrobów gotowych** określ wartość w polu **Metoda księgowania** na jedną z następujących wartości:

    - *Natychmiastowe* — gdy towar zostanie zgłoszony jako gotowy, system w pełni przeprocesowuje wszystkie powiązane księgowania arkusza, zanim będzie oznaczał towar gotowy jako fizycznie dostępny.
    - *Odroczony* — Gdy towar zostanie zgłoszony jako gotowy, system oznacza gotowy towar jako fizycznie dostępny i dodaje księgowania dziennika do kolejki komunikatów. System nie czeka, dopóki księgowanie nie zostanie w pełni przetworzone, zanim stanie się gotowym towarem jako fizycznie dostępnym.

## <a name="schedule-the-message-processor-batch-job-to-process-deferred-postings"></a>Planowanie zadania wsadowego procesora komunikatów w celu przetwarzania odroczonych księgować

Zadanie wsadowe procesora komunikatów jest odpowiedzialne za przetwarzanie księgowanie arkusza po ich przetworzeniu w kolejce. Aby zapewnić, że księgowanie arkusza jest przetwarzane, należy skonfigurować to zadanie do uruchamiania w regularnych interwałach. Użyj poniższej procedury, aby skonfigurować wymagane zadanie wsadowe.

1. Przejdź do **Administracja systemu \> Procesor wiadomości \> Procesor wiadomości**.
1. Na skróconej **karcie** Parametry ustaw w polu **Kolejka komunikatów** wartość *Produkcja*.
1. Na karcie skróconej **Uruchom w tle** należy skonfigurować opcję **Przetwarzanie wsadowe** na wartość *Tak*. Następnie ustaw harmonogram cykliczny i w razie potrzeby skonfiguruj inne ustawienia. Ustawienia działają tak samo, jak w przypadku innych typów [zadań w tle](../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md) w firmie Microsoft Dynamics 365 Supply Chain Management.

## <a name="track-the-progress-of-your-deferred-postings"></a>Śledzenie postępu księgowania odroczonego

Odroczone księgowania arkusza są kolejkowane w kolejce jako *wiadomości* procesora komunikatów, które czekają na ich przetworzenie przez procesor *komunikatów*. Procesor komunikatów powinien być tak ustawiony, aby był uruchamiany jako zaplanowane zadanie wsadowe. Aby wyświetlić wiadomości odroczonego księgowania, które zostały lub zostaną przetworzone przez procesor komunikatów, przejdź do **Kontrola produkcji \> Zlecenia produkcyjne \> Odroczone księgowanie zlecenia produkcyjnego**.

### <a name="message-grid-columns-and-filters"></a>Kolumny i filtry siatki komunikatów

Pól w górnej części strony **Odroczone księgowanie zlecenia produkcyjnego** można używać do wyszukiwania określonych komunikatów.

Dostępne są następujące filtry:

- **Typ komunikatu** — umożliwia określenie typu wiadomości wyświetlanych w siatce.
- **Stan komunikatu** — Określ stan komunikatów wyświetlanych w siatce. Istnieją następujące stany:

    - *W kolejce* — komunikat jest gotowy do przetworzenia przez procesor komunikatów.
    - *Przetworzony* — komunikat został przetworzony przez procesor komunikatów.
    - *Anulowano* — wiadomość nie została przetworzona podczas ostatniej próby, a następnie została anulowana przez użytkownika.
    - *Nieudane* – komunikat nie został przetworzony podczas ostatniej próby. System będzie trzy razy ponawiać próby wykonania komunikatów o błędach. Następnie podda się i pozostawi komunikat w *stanie Niepowodzenie*. Należy zauważyć, że nie można ręcznie anulować ani edytować wiadomości do momentu po ostatniej z tych trzech prób.

- **Zawartość komunikatu** — ten filtr umożliwia przeprowadzanie wyszukiwania pełnotekstowego w treści komunikatu. (Treść wiadomości nie jest wyświetlana w siatce). Filtr traktuje większość symboli specjalnych (takich jak łączniki) jako znaki spacji, a wszystkie znaki spacji traktuje jako logiczne operatory OR. Na przykład, jeśli wyszukasz konkretną wartość `journalid` równą *USMF-123456*, system znajdzie wszystkie wiadomości zawierające „USMF” lub „123456”. W tym przypadku lista wyników może być długa. W związku z tym lepiej jest wpisać tylko wartość *123456*, ponieważ spowoduje to zwrócenie bardziej precyzyjnych wyników.

Listę można także sortować i filtrować, wybierając dowolny nagłówek kolumn i wprowadzając kryteria w oknie dialogowym.

### <a name="view-the-message-log-message-content-and-details"></a>Wyświetlanie dziennika komunikatów, zawartości komunikatu i szczegółów

Szczegółowe informacje o komunikacie można znaleźć, zaznaczając go w siatce, a następnie otwierając karty **Dziennik** lub **Surowa zawartość** w siatce komunikatów, na których są wyświetlane poszczególne zdarzenia przetwarzania.

Pasek narzędzi na karcie **Dziennik** zawiera następujące przyciski:

- **Dziennik** — wybranie tego przycisku powoduje wyświetlanie wyników przetwarzania. Ten przycisk jest szczególnie przydatny, gdy **wartością wyniku przetwarzania wiadomości** jest *Niepowodzenie*, a użytkownik chce poznać przyczyny niepowodzenia przetwarzania.
- **Pakiet** — wiele operacji przetwarzania wiadomości może być uruchomionych w ramach tego samego procesu wsadowego. Ten przycisk należy nacisnąć, aby wyświetlić te szczegółowe dane. Możesz na przykład sprawdzić, czy istnieją zależności wymagające określonej kolejności przetwarzania dla niektórych komunikatów.

### <a name="manually-process-or-cancel-a-message"></a>Ręczne przetwarzanie lub anulowanie komunikatu

Możesz ręcznie przetworzyć lub anulować wiadomość zgodnie z potrzebami, w zależności od jej aktualnego stanu. W tym celu zaznacz komunikat w siatce, a następnie wybierz opcję **Przetwórz** lub **Anuluj** w okienku akcji.

### <a name="set-up-business-events-to-deliver-alerts-for-failed-processing-results"></a>Konfigurowanie zdarzeń biznesowych w celu dostarczania alertów o nieudanym przetwarzaniu

Możesz skonfigurować [zdarzenia biznesowe](../../fin-ops-core/dev-itpro/business-events/home-page.md), które będą ostrzegać o wynikach przetwarzania, które nie powiodły się. Przejdź do **Administracja systemu \> Konfiguracja \> Zdarzenia biznesowe \> Katalog zdarzeń biznesowych** i aktywuj zdarzenie biznesowe o nazwie *Przetworzony komunikat procesora wiadomości*.

W trakcie procesu aktywacji zostanie wyświetlony monit o określenie, czy zdarzenie jest specyficzne dla jednej firmy czy dotyczy wszystkich firm. Zostanie także wyświetlony monit o podanie wartości nazwy **punktu końcowego**. Ta wartość musi być zdefiniowana jako pierwsza.

> [!NOTE]
> Jeśli w polu **w przypadku wystąpienia zdarzenia biznesowego** jest wybrane ustawienie *Microsoft Power Automate* (a nie na przykład *HTTPS*), **nazwa punktu końcowego** zostanie automatycznie utworzona w module Supply Chain Management na podstawie ustawień *Microsoft Power Automate*.
