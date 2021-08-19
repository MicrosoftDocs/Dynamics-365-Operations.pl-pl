---
title: Pobranie nadmiarowe dla zamówień sprzedaży i zamówień przeniesienia
description: W tym temacie wyjaśniono, jak włączyć pobieranie nadmiarowe dla zamówień sprzedaży i zamówień przeniesienia.
author: GalynaFedorova
ms.date: 07/06/2021
ms.topic: article
ms.search.form: WHSRFMenuItem
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-07-06
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 3c6f9d386f79754edce38e4e2cf4c9bfefbce69bdb252e8754f39d909827fa02
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6722158"
---
# <a name="over-picking-for-sales-orders-and-transfer-orders"></a>Pobranie nadmiarowe dla zamówień sprzedaży i zamówień przeniesienia

[!include [banner](../includes/banner.md)]

W tym temacie przedstawiono scenariusz, który pokazuje, jak włączyć pobranie nadmiarowe dla określonego pracownika lub wszystkich pracowników. Proces pobierania nadmiarowe pozwala na kontrolowane nadmiernego pobierania podczas pracy pobrania.

Pobieranie nadmiarowe z magazynu to prosta koncepcja. System umożliwia pracownikom pobranie większej liczby pozycji niż określono dla zamówienia. Jednak nadal uwzględnia on limit dostawy nadmiarowej, który jest ustawiony na poziomie wiersza dla zamówienia przeniesienia lub zamówienia sprzedaży. Jeśli ten limit zostanie przekroczony, aplikacja Warehouse Management powiadamia pracowników, że przekraczają limit dostawy nadmiarowej.

Funkcja pobrania nadmiarowego pomaga zminimalizować konserwację, a także pomaga zachować elastyczność konfiguracji. Można zdefiniować jeden lub więcej elementów menu urządzenia przenośnego i włączyć pobranie nadmiarowe tylko dla niektórych z nich. Można również uniemożliwić wybranym pracownikom pobranie nadmiarowe zamówień sprzedaży i/lub zamówień przeniesienia bez konieczności zmiany elementów menu. Zamiast tego można wyłączyć jedną lub obie te możliwości w odpowiednich konfiguracjach procesu roboczego.

Funkcja pobrania nadmiarowego może pomóc pracownikom zaoszczędzić czas i wysiłek podczas wybierania i wysyłania przedmiotów. Na przykład funkcja umożliwia pracownikom wykonywanie następujących zadań:

- Kompensuj niedobry podczas pobierania lub wysyłki.
- Unikaj konieczności rozpakowania niektórych materiałów opakowaniowych podczas procesu pobierania.
- Kompensuj za uszkodzenia pozycji podczas transportu.
- Wysyłaj z odchyleniem ilości lub jednostki miary.
- Minimalizuj problemy z ilością dla numerów identyfikacyjnych.
- Unikaj odpadów materiałowych i niedoboru drogich materiałów.
- Zmierz pobraną ilość po pobraniu (na przykład przez ważenie ciężarówki).

> [!IMPORTANT]
> Funkcja pobrania nadmiarowego dotyczy tylko pobierania i przetwarzania zamówień sprzedaży i zamówień przeniesienia. Uzupełnianie zapasów nie obsługuje pobrania nadmiarowego. Po uruchomieniu pracy uzupełniania zapasów system nie pozwoli użytkownikom na pobranie nadmiarowe.

Scenariusz w tym temacie pokazuje sposób konfigurowania funkcji pobrania nadmiarowego i korzystania z niej.

## <a name="scenario-prerequisite-make-demo-data-available"></a>Warunek wstępny scenariusza: udostępnij dane pokazu

Każdy scenariusz w tym temacie zawiera odwołania do wartości i rekordów uwzględnionych w standardowych danych pokazu dostępnych dla rozwiązania Microsoft Dynamics 365 Supply Chain Management. Aby użyć wartości określonych w tym miejscu podczas wykonywania ćwiczeń, upewnij się, że praca odbywa się w środowisku, w którym są zainstalowane dane demonstracyjne, i przed rozpoczęciem ustaw firmę na *USMF*.

## <a name="scenario-setup"></a>Ustawienia scenariusza

Przed rozpoczęciem pracy nad przykładowym scenariuszem należy włączyć pobranie nadmiarowe zarówno dla odpowiedniego pracownika, jak i odpowiedniego elementu menu.

### <a name="set-up-a-worker-to-allow-for-over-picking"></a>Konfigurowanie pracownika w celu umożliwienia pobrania nadmiarowego

Oto ogólna procedura konfigurowania pracownika w celu umożliwienia pobierania nadmiarowego oddzielnie dla zamówień sprzedaży i zamówień przeniesienia. Ta konfiguracja kontroluje, który pracownik zajmujący się pobieraniem może wykonać pobieranie nadmiarowe i czy ten pracownik może wykonać tę operację zarówno dla zamówień przeniesienia, jak i zamówień sprzedaży.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Pracownik**.
1. W panelu zaznacz osobę **Julia Funderburk**.
1. Na skróconej karcie **Użytkownicy** wybierz wiersz z następującymi wartościami. Jeśli żaden istniejący wiersz nie ma tych wartości, utwórz go.

    - **Identyfikator użytkownika:** *24*
    - **Nazwa użytkownika:** *WH 24*
    - **Magazyn domyślny:** *24*
    - **Nazwa menu:** *Główne*

1. Na skróconej karcie **Praca** ustaw następujące wartości dla użytkownika *24*, jeśli jeszcze nie są one ustawione:

    - **Zezwalaj na pobranie nadmiarowe sprzedaży:** *Tak*
    - **Zezwalaj na pobranie nadmiarowe zamówienia przeniesienia:** *Tak*

### <a name="set-up-a-mobile-device-menu-item-to-allow-for-over-picking"></a>Konfigurowanie elementu menu urządzenia przenośnego do zezwalania na pobranie nadmiarowe

Oto ogólna procedura konfigurowania elementu menu urządzenia przenośnego, aby włączyć pobranie nadmiarowe. W zależności od wymagań biznesowych dotyczących poziomu uprawnień pracownika, który będzie korzystał z menu urządzenia przenośnego, niektóre parametry mogą być włączone lub wyłączone.

1. Przejdź do pozycji **Zarządzanie magazynem \> Ustawienia \> Urządzenie przenośne \> Elementy menu urządzenia przenośnego**.
1. W okienku listy wybierz rekord o nazwie *Pobranie sprzedaży*. Jeśli żaden istniejący rekord nie ma tej nazwy, utwórz go. Potwierdź lub ustaw następujące wartości dla rekordu:

    - **Nazwa elementu menu:** *Pobranie sprzedaży*
    - **Tytuł:** *Pobranie sprzedaży*
    - **Tryb:** *Praca*
    - **Używanie istniejącej pracy:** *Tak*
    - **Zarządzane przez:** *Sterowane przez użytkownika*
    - **Zastąp docelowy numer identyfikacyjny:** *Tak*
    - **Zastąp numer identyfikacyjny podczas odłożenia:** *Tak*
    - **Zachowaj pracę zablokowaną przez użytkownika:** *Tak*
    - **Zezwalaj na pobranie nadmiarowe:** *Tak*

> [!IMPORTANT]
> Po włączeniu odpowiednich parametrów zarówno dla pracownika, jak i elementu menu urządzenia przenośnego, pobranie nadmiarowe można przetworzyć tylko za pośrednictwem urządzenia przenośnego.

## <a name="example-scenario"></a>Przykładowy scenariusz

Gdy wymagania wstępne, konfiguracja pracownika i konfiguracja elementu menu są gotowe, można rozpocząć pracę z funkcją.

### <a name="create-a-sales-order-that-allows-for-overdelivery"></a>Tworzenie zamówienia sprzedaży, które umożliwia dostawę nadmiarową

1. Wybierz kolejno opcje **Sprzedaż i marketing \> Zamówienia sprzedaży \> Wszystkie zamówienia sprzedaży**.
1. Wybierz opcję **Nowy**, aby utworzyć nowe zamówienie sprzedaży.
1. W wyświetlonym oknie dialogowym **Utwórz zamówienie sprzedaży** można ustawić następujące wartości:

    - **Konto odbiorcy:** *US-001*
    - **Magazyn:** *24*

1. Kliknij przycisk **OK**.
1. Nowe zamówienie zakupu (PO) zostało otwarte. Na skróconej karcie **Wierszy zamówienia sprzedaży** dodaj wiersz o następujących ustawieniach:

    - **Numer pozycji:** *A0001*
    - **Ilość:** *10*

1. Na skróconej karcie **Szczegółów wiersza** na karcie **Dostawa** należy określić wartość w polu **Nadwyżka** na *10*.
1. Na skróconej karcie **Wiersze zamówienia sprzedaży**, w wybierz **Zapasy \> Rezerwacja**.
1. Na stronie **Rezerwacja**, w okienku akcji, wybierz pozycję **Rezerwacja partii**, aby zarezerwować zapasy.
1. Zamknij stronę **Rezerwacja**.
1. W okienku akcji na karcie **Magazyn** wybierz opcję **Zwolnienie do magazynu**.

Po wykonaniu zwolnienia, użytkownik otrzymuje komunikaty informacyjne, które zawierają identyfikator grupy czynności oraz identyfikator wysyłki.

### <a name="get-the-work-id-and-license-plate-number-for-the-new-order"></a>Uzyskaj identyfikator służbowy i numer identyfikacyjny nowego zamówienia

Po zwolnieniu zamówienia sprzedaży do magazynu system powinien był utworzyć nowy identyfikator pracy, który ma jeden wiersz pobrania. Aby znaleźć identyfikator pracy i przypisanie numeru identyfikacyjnego, należy wykonać następujące kroki.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Praca \> Szczegóły pracy**.
1. W siatce **Przegląd** wyszukaj w kolumnie **Numer zamówienia** nowo utworzone zamówienie sprzedaży. Zapisz odpowiednie identyfikatory pracy dla tego zamówienia sprzedaży.
1. Wybierz wiersz dla nowego zamówienia sprzedaży, aby wyświetlić informacje powiązane z siatką **Wiersze**. Umożliwia zanotowanie lokalizacji, z której będzie pobierana pozycja.
1. Wybierz kolejno opcje **Zarządzanie zapasami \> Zapytania i raporty \> Dostępne zapasy**.
1. W Okienku akcji kliknij pozycję **Wymiary**.
1. W oknie dialogowym **Wyświetlanie wymiarów** upewnij się, że pola wyboru **Numer identyfikacyjny**, **Magazyn** i **Identyfikator pozycji** są zaznaczone, a następnie wybierz przycisk **OK**.
1. W okienku **Filtr** należy skonfigurować następujące filtry:

    - **Numer pozycji** — **jeden z** — *A0001*
    - **Magazyn** — **zaczyna się od** – *24*

1. Wybierz opcję **Zastosuj**.
1. Zanotuj wyświetlony **numer identyfikacyjny**.

### <a name="over-pick-the-order-by-using-the-warehouse-management-mobile-app"></a>Pobranie nadmiarowe zamówienia za pomocą aplikacji mobilnej Warehouse Management

1. Zaloguj się do aplikacji Warehouse Management jako użytkownik w magazynie *24*.
1. Przejdź do **Wychodzące \> Pobieranie sprzedaży**.
1. W polu **Skanuj identyfikator pracy lub numer identyfikacyjny** wprowadź identyfikator pracy utworzony dla zamówienia sprzedaży.
1. Wybierz **OK** (symbol znacznika wyboru).
1. Wybierz pozycję **Pobranie nadmiarowe**.
1. Ustaw wartość w polu **Ilość pobrania** na *14*.
1. Wybierz **OK** (symbol znacznika wyboru).

    Na stronie **Pobranie nadmiarowe** zostanie wyświetlony następujący komunikat: „Dostawa nadmiarowa wiersza wynosi 40,00 procent, ale dozwolona dostawa nadmiarowa to tylko 10,00 procent”. Ten komunikat wskazuje, że wprowadzona ilość pobrania przekracza limit dostawy nadmiarowej. Limit dostawy nadmiarowej dla wiersza zamówienia sprzedaży wynosi 10 procent. W związku z tym dla określonej ilości 10 można pobrać nadmiarowo tylko 1, dla całkowitej ilości pobrania 11.

1. Ustaw wartość w polu **Ilość pobrania** na *11*.
1. Wybierz **OK** (symbol znacznika wyboru).
1. W polu **Numer identyfikacyjny** wprowadź numer identyfikacyjny, który został zanotowany w poprzedniej sekcji.
1. W polu **Docelowy numer identyfikacyjny** wprowadź docelowy numer identyfikacyjny. Należy zauważyć, że jest wyświetlana lokalizacja pobrania (*FLOOR 001*), pozycja (*A0001*) oraz ilość (*11 szt.*).
1. Wybierz **OK** (symbol znacznika wyboru).
1. Umożliwia przejrzenie informacji na stronie **Zamówienia sprzedaży - Odłożenie**. Pole **Loc** powinno wskazywać, że pobrane towary przechodzą na lokalizację *BAYDOOR*.
1. Wybierz **OK** (symbol znacznika wyboru).

Na stronie **Skanuj identyfikator pracy / identyfikator numeru identyfikacyjnego** jest wyświetlany komunikat „praca wykonana”. Ten komunikat wskazuje, że identyfikator pracy zamówienia sprzedaży został ukończony, a ilość pobrania nadmiernego nie przekracza limitu dostawy nadmiarowej wynoszącego 10 procent.
