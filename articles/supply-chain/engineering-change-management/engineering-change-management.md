---
title: Zarządzanie zmianami dotyczącymi produktów inżynieryjnych
description: Ten temat zawiera informacje o zarządzaniu zmianami inżynieryjnymi. Zarządzanie zmianami inżynieryjnymi umożliwia strukturalne procesy zarządzania zmianami produktów inżynierskich, proponowanie, zgłaszanie i Dokonywanie zmian, recenzowanie i zatwierdzanie zmian, ocenianie ich wpływu na istniejące transakcje oraz na dalszych tematach.
author: t-benebo
ms.date: 09/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EngChgEcmRequestSelection,EngChgEcmRequestProducts,EngChgEcmRequestPriorityChart,EngChgEcmRequestListPage,EngChgEcmRequestFilteredPart,EngChgEcmRequestDetails,EngChgEcmReason,EngChgEcmProjTableInformation,EngChgEcmProductRoute,EngChgEcmProductRelease,EngChgEcmProductPreview, EngChgEcmWhereUsed, EngChgEcmInventTrans,EngChgEcmHeaderSelection,EngChgEcmHeaderPreviewPart,EngChgEcmHeaderFilteredPart,EngChgEcmHeaderDetails, EngChgCaseWhereUsedAnalysis, EngChgCaseValidatorMessage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 55952a9b1c25b806ee4a21ef1982c5b15a41adeb9c9bfdf2fccb8c9da242ffdb
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6714337"
---
# <a name="manage-changes-to-engineering-products"></a>Zarządzanie zmianami dotyczącymi produktów inżynieryjnych

[!include [banner](../includes/banner.md)]

Zarządzanie zmianami inżynieryjnymi oferuje strukturalne procesy zarządzania zmianami w produktach inżynierii. Aby zaproponować zmiany i zażądać zmian, a następnie zastosować *proces zmiany technologicznej* w celu faktycznego wprowadzenia tych zmian, można skorzystać z procesu *żądanie zmiany*. Użytkownicy mogą tworzyć techniczne zlecenia zmiany lub inżynierów zmian technologicznych, a następnie przeprowadzają proces ich przeglądania i zatwierdzania, oceniania ich wpływu na istniejące transakcje i odpowiadania na nie.

## <a name="engineering-change-requests"></a>Żądania zmian projektowych

Proces przetwarzania żądania zmiany inżynieryjnego umożliwia przechwytywanie wniosków o zmiany ze wszystkich odpowiednich działów w firmie. Nie ma znaczenia, czy pracujesz jako inżynier, czy w dziale produkcji, pozysku, hurtowni lub sprzedaży. Aby zażądać zmiany, każdy może skorzystać z żądania zmiany inżynieryjnej. Ta zmiana może być pomysłem na nowy produkt, problem wykryty podczas pracy z istniejącym produktem, sugestią poprawy istniejącego produktu lub inną zmianą.

Gdy ktoś prześle żądanie zmiany, proces *recenzowania i zatwierdzania* jest zarządzany przez przepływ pracy określający, kto musi zatwierdzić zmianę (np. właściciela produktu).

Aby skonfigurować przepływ pracy dla zleceń zmiany inżynieryjnej lub żądań zmiany, przejdź do **Zarządzanie zmianami inżynieryjnymi \> Przepływy pracy inżynieryjnej**.  Wybierz opcję **Nowy**, określ, czy przepływ pracy będzie używany do przeglądania zleceń zmiany inżynierów lub technicznych żądań zmiany, a następnie skonfiguruj przepływ pracy.

Więcej informacji na temat pracy z przepływami pracy zawiera temat [Omówienie tworzenia przepływów pracy](../../fin-ops-core/fin-ops/organization-administration/overview-workflow-system.md). Aby uzyskać więcej informacji o własności danych, należy zapoznać się z artykułem [Właściciele produktów](product-owner.md).

### <a name="create-a-new-engineering-change-request"></a>Utwórz nowe żądanie zmiany projektowej

Aby utworzyć inżynieryjne żądanie zmiany, należy wykonać jedną z następujących czynności.

- Przejdź do **Zarządzanie zmianami inżynieryjnymi\> Wspólne \> Zarządzanie zmianą inżynieryjną \> Żądania zmiany inżynieryjnej**, a następnie wybierz opcję **Nowy** w okienku akcji.
- Otwórz stronę **Szczegóły produktu** dla istniejącego produktu inżynierskiego. Następnie, w okienku akcji przejdź do karty **Inżynier** i w grupie **Zarządzanie zmianami inżynieryjnymi** wybierz **Żądania zmiany inżynieryjnej \> Nowe żądanie zmiany inżynieryjnej**.

Zostanie utworzone nowe żądanie zmiany. Możesz teraz na każdej skróconej karcie określić pola opisane w poniższych podsekcjach.

#### <a name="general-fasttab"></a>Skrócona karta Ogólne

Skrócona karta **Ogólne** dostarcza podstawowy opis żądania zmiany. W poniższej tabeli opisano pola znajdujące się na tej skróconej karcie.

| Pole | opis |
|---|---|
| Żądanie zmiany | Służy do wprowadzania nazwy dla żądania zmiany. |
| Nazwa | Wprowadź tekst zwięźle opisujący lub identyfikujący zmiany w żądaniu. |
| Priorytet | Wybierz wartość, aby wskazać, jak wysoki priorytet ma zmiana. W razie potrzeby można dostosować wartości dostępne dla firmy. (Aby uzyskać więcej informacji, przejdź do sekcji [Ustanawianie wspólnych wartości dla zarządzania zmianami inżynieryjnymi](engineering-change-management-setup.md).) |
| Kategoria | Umożliwia wybranie wartości opisującej typ wymaganej zmiany. W razie potrzeby można dostosować wartości dostępne dla firmy. (Aby uzyskać więcej informacji, przejdź do sekcji [Ustanawianie wspólnych wartości dla zarządzania zmianami inżynieryjnymi](engineering-change-management-setup.md).) |
| Priorytet | Umożliwia wybranie wartości wskazującej na ważność usterki, która powinna zostać naprawiona przez wdrożenie żądania. W razie potrzeby można dostosować wartości dostępne dla firmy. (Aby uzyskać więcej informacji, przejdź do sekcji [Ustanawianie wspólnych wartości dla zarządzania zmianami inżynieryjnymi](engineering-change-management-setup.md).) |
| Wnioskodawca | Nazwa użytkownika, który utworzył żądanie. |
| W | Data utworzenia żądania. |
| Stan | Stan żądania. Po utworzeniu wniosku stan zmienia się na *Utworzony*. Po zatwierdzeniu wniosku stan zmienia się na *Zatwierdzony*. Jeśli dla danego wniosku zostało utworzone powiązane zamówienie zmian, stan zmieni się na *Obserwowany*. |
| Zlecenie zmiany | Numer zamówienia zmiany, jeśli zostało spełnione żądanie zmiany w ramach zlecenia zmiany. |

#### <a name="information-fasttab"></a>Skrócona karta informacji

Skrócona karta **Informacje** umożliwia dodanie dodatkowych informacji o żądaniu.

Aby dodać wiersz do siatki, wybierz opcję **Nowy** na pasku narzędzi powyżej siatki, a następnie wybierz jedną z następujących opcji:

- **Plik** – Przesyłanie pliku.
- **Obraz** – Przesyłanie obrazu.
- **Notatka** — umożliwia wprowadzenie notatki bezpośrednio w siatce.
- **URL** – umożliwia wprowadzenie adresu URL bezpośrednio w siatce.

W poniższej tabeli opisano pola znajdujące się w każdym wierszu.

| Pole | opis |
|---|---|
| Data i godzina utworzenia | Data i godzina utworzenia wiersza. |
| Typ | Typ informacji, dla którego utworzono wiersz (plik, obraz, notatka lub adres URL). |
| opis | Wprowadź opis wiersza. |
| Ograniczenia | Wartość wskazująca, czy dodane informacje pochodzą ze źródła wewnętrznego lub zewnętrznego. |
| Powiązany | Zaznaczone pole wyboru wskazuje, że wiersz zawiera załącznik (plik lub obraz). Aby pobrać załącznik, zaznacz wiersz, a następnie wybierz opcję **Otwórz** na pasku narzędzi powyżej siatki. |

#### <a name="products-fasttab"></a>Skrócona karta Produkty

Skrócona karta **Produkty** umożliwia wylistowanie każdego produktu, którego dotyczy żądanie zmiany. Za pomocą przycisków na pasku narzędzi można dodawać produkty do siatki lub usuwać je z siatki.

Ta lista jest używana wyłącznie w celach informacyjnych. Dlatego można dodać dowolną liczbę produktów pokrewnych, które uznasz za stosowne. W przypadku utworzenia żądania zmiany ze strony **Szczegóły produktu** dla istniejącego produktu produkt powinien być wymieniony na skróconej karcie **Produkty** po zapisaniu rekordu żądania.

#### <a name="source-fasttab"></a>Skrócona karta Źródło

Skrócona karta **Źródło** umożliwia śledzenie punktu początkowego żądania zmiany. Jest to przydatne na przykład wtedy, gdy użytkownik chce zobaczyć, czy żądanie zmiany zostało utworzone z zamówienia sprzedaży, kto je utworzył, oraz czy firma, w której została utworzona, została utworzona.

### <a name="evaluate-the-business-impact-of-a-change-request-and-send-notifications"></a>Ocenianie wpływu żądania zmiany na biznesowe i wysyłanie powiadomień

Podczas przeglądania żądania zmiany można wyszukiwać zależności. W ten sposób można ocenić wpływ żądanej zmiany transakcji otwartych, takich jak zamówienia sprzedaży, zlecenia produkcyjne i dostępne zapasy. W trakcie przeglądania zgłoszeń zmian można wysyłać powiadomienia do osób odpowiedzialnych za realizację różnych typów powiązanych zleceń.

#### <a name="review-affected-transactions-block-selected-transactions-and-send-notifications"></a>Przeglądanie transakcji, których to dotyczy, blokowanie wybranych transakcji i wysyłanie powiadomień

Aby dokonać przeglądu transakcji, których to dotyczy, zablokować wybrane transakcje i wysłać odpowiednie powiadomienia, wykonaj poniższe kroki.

1. Przejdź do **Zarządzanie zmianami inżynieryjnymi\> Wspólne \> Zarządzanie zmianami inżynieryjnymi \> Żądania zmiany inżynieryjnej**.
1. Należy otworzyć istniejące żądanie zmiany lub wybrać polecenie **Nowy** w okienku akcji, aby utworzyć nowe żądanie zmiany.
1. W okienku akcji na karcie **Żądanie zmiany** w grupie **Wpływ biznesowy** wybierz jeden z następujących przycisków:

    - **Wyszukiwanie** — skanowanie wszystkich otwartych transakcji, a następnie otwarcie okna dialogowego **efekty biznesowe dla otwartych transakcji**, w którym jest wyświetlana lista wszystkich transakcji, na które wpłynie zmiana.
    - **Wyświetl poprzednie wyszukiwanie** — umożliwia otwarcie okna dialogowego **efekty biznesowe dla otwartych transakcji**, w którym znajduje się lista wyników poprzedniego wyszukiwania. (Nowe wyszukiwanie nie zostało wykonane)

1. Okno dialogowe **Wpływ biznesowy do otwarcia transakcji** zawiera zestaw kart, z których każda zawiera listę transakcji danego typu (**Zamówienia sprzedaży**, **Zamówienia zakupu**, **Zamówienia produkcyjne**, **Zapasy** itd.). Na każdej zakładce znajduje się również liczba określająca liczbę transakcji danego typu, których dotyczy problem. Wybierz kartę, aby wyświetlić odpowiednią listę.
1. Aby pracować z transakcją na liście, zaznacz ją, a następnie wybierz jeden z poniższych przycisków na pasku narzędzi:

    - **Wyświetl transakcję** — umożliwia otwarcie wybranego rekordu transakcji.
    - **Zablokuj zamówienie** — ten przycisk jest dostępny tylko na karcie **Zamówienia sprzedaży**. Zaznaczenie tego przycisku powoduje zablokowanie wybranego zamówienia sprzedaży.
    - **Zablokuj wiersz** — ten przycisk jest dostępny tylko na karcie **Zamówienia zakupu**. Zaznaczenie tego przycisku powoduje zablokowanie wybranego wiersza zakupów.
    - **Powiadom osoby odpowiedzialne** — ten przycisk jest dostępny tylko na karcie **Zamówienia sprzedaży**. Wybierz go, aby wysłać powiadomienie o zmianie do użytkownika, który jest ustawiony jako odpowiedzialny za wybrane zamówienie sprzedaży.
    - **Powiadom osoby odpowiedzialne** — ten przycisk jest dostępny tylko na karcie **Zamówienia sprzedaży**. Wybierz go, aby wysłać powiadomienie o zmianie do użytkownika, który jest ustawiony jako odpowiedzialny za wybrane zamówienie sprzedaży.
    - **Powiadomienie działu produkcji** — ten przycisk jest dostępny tylko na karcie **Zlecenia produkcyjne**. W przeciwieństwie do zamówień sprzedaży i zamówień zakupu, w zleceniach produkcyjnych nie ma jednego użytkownika, który jest ustawiony jako odpowiedzialny za nie od początku do zakończenia. Zamiast tego, różni nadzorcy lub planiści zazwyczaj przejmują odpowiedzialność za konkretny obiekt lub konkretną część produkcji (na przykład za konkretne zasoby lub grupy zasobów). Dlatego po wybraniu tego przycisku wszyscy użytkownicy, którzy są odpowiedzialni za jakikolwiek zasób związany z wybranym zleceniem produkcyjnym, otrzymują powiadomienie o zmianie.
    - **Powiadom osoby przygotowujące** — ten przycisk jest dostępny tylko na karcie **Zapotrzebowanie na zakup**. Wybierz go, aby wysłać powiadomienie o zmianie do użytkownika, który jest ustawiony jako przygotowujący wybrane zapotrzebowanie na zakup.
    - **Powiadom osoby odpowiedzialne za sprzedaż** — ten przycisk jest dostępny tylko na karcie **Oferty**. Wybierz go, aby wysłać powiadomienie o zmianie do użytkownika, który jest ustawiony jako odpowiedzialny za wybraną ofertę.
    - **Wyrzuć** — ten przycisk jest dostępny tylko na karcie **Zapasy**. Wybierz go w celu likwidacji wybranych zapasów.
    - **Wyświetl historię** — umożliwia otwarcie historii akcji podjętych w związku z wybraną transakcją przy użyciu okna dialogowego **Wpływ biznesowy na otwarte transakcje**. (Historia pokazuje na przykład, czy powiadomienia zostały wysłane lub czy transakcje zostały zablokowane) 
    - **Wyświetl wszystkie transakcje** — umożliwia otwarcie pełnej listy wszystkich transakcji, a nie tylko transakcji otwartych.

#### <a name="review-and-process-change-notifications-for-transactions"></a>Przeglądanie i przetwarzanie powiadomień o zmianach dla transakcji

Wysyłane do ciebie powiadomienia o zmianach możesz odczytywać i przetwarzać w następujący sposób:

- W przypadku zleceń produkcyjnych w centrum akcji należy zmieniać powiadomienia o transakcjach, za które użytkownik jest odpowiedzialny. Przycisk **Pokaż komunikaty** (symbol dzwonka) po prawej stronie paska nawigacji wskazuje, kiedy wiadomość z centrum akcji jest dostępna. Wybierz przycisk **Pokaż wiadomości**, aby otworzyć Centrum akcji i przejrzeć wiadomości.
- Aby wyświetlić wszystkie zlecenia produkcyjne, dla których zostało wysłane powiadomienie inżynierskie, przejdź do **Zlecenia produkcyjne \> Zlecenia produkcyjne \> Wszystkie zlecenia produkcyjne**. Następnie na karcie **Zlecenie produkcyjne**, w grupie **Wniosek o zmianę inżynieryjną** wybierz pozycję **Powiadomienia inżynieryjne**, aby otworzyć stronę **Powiadomienia inżynieryjne**.
- W przypadku zleceń produkcyjnych możesz wybrać przeglądanie tylko tych powiadomień o zmianach, które dotyczą zarządzanych przez Ciebie zasobów produkcyjnych. W obszarze roboczym **Zarządzanie produkcją**, w okienku akcji wybierz pozycję **Konfiguruj mój obszar roboczy**, aby filtrować stronę, tak aby zawierała tylko informacje o jednostkach produkcyjnych, grupach i/lub zasobach, którymi zarządzasz. W sekcji **Podsumowanie** kafelek o nazwie **Zlecenia produkcyjne ze zmienionymi produktami** zawiera liczbę powiadomień zgodnie z ustawieniami filtru. Zaznaczenie tego kafelka umożliwia otwarcie strony **Powiadomienia inżynieryjne**, na której jest wyświetlona pełna lista transakcji spełniających kryteria filtru.

Przeglądając powiadomienia dotyczące zlecenia produkcyjnego na stronie **Powiadomienia inżynieryjne**, można śledzić łącza do powiązanych zleceń zmian lub zleceń produkcyjnych, wybierając wartości kolumn lub używając powiązanych poleceń w okienku akcji. Po zakończeniu obliczania zmian i po anulowaniu lub zmodyfikowaniu zleceń produkcyjnych w razie potrzeby można oznaczyć powiadomienie jako rozwiązane. Zaznacz powiadomienie, a następnie w okienku akcji wybierz pozycję **Rozwiąż**. Powiadomienie zostanie usunięte z widoków wszystkich użytkowników.

### <a name="create-a-change-order-from-a-change-request"></a>Tworzenie zlecenia zmiany za pomocą żądania zmiany

Inżynier dokonujący przeglądu żądania zmiany może utworzyć inżynieryjne zlecenie zmiany, bezpośrednio na stronie **Żądania zmiany inżynieryjnej**. W okienku akcji, na karcie **żądanie zmiany** w grupie **Zlecenie zmian inżynieryjnych**, wybierz opcję **Kopiuj łącze i produkty**.

## <a name="engineering-change-orders"></a>Zlecenia zmian projektowych

Zlecenia zmian inżynieryjnych oferują ustrukturalizowane procesy wprowadzania zmian w produktach inżynierii. Propozycje zmian można proponować, korzystając z kopii odpowiednich danych technicznych. Nie ma to wpływu na rzeczywiste dane główne. Aby uzyskać więcej informacji na temat danych inżynieryjnych, zapoznaj się z tematem [Wersje inżynieryjne i kategorie produktów inżynieryjnych](engineering-versions-product-category.md).

Można utworzyć zamówienie zmiany inżyniera na podstawie zatwierdzonego technologicznego zlecenia zmiany. Inżynierowie mogą również tworzyć zlecenia zmiany inżynieryjnej od podstaw. W jednym zamówieniu zmiany inżynieryjnej można uwzględnić wiele produktów, wykonując następujące kroki:

- Ręcznie wybierz produkty.
- Użyj BOM, aby umożliwić uwzględnienie produktów znajdujących się niżej w strukturze produktu (w podrzędnych).
- Aby uwzględnić produkty znajdujące się wyżej w strukturze produktu (czyli nadrzędnych), należy użyć wyszukiwania miejsca użycia.

Po zakończeniu propozycji zmian proces przeglądu i zatwierdzania będzie obsługiwany przez przepływ pracy. Istnieje możliwość skonfigurowania różnych przepływów pracy na podstawie priorytetu i ważności.

Aby skonfigurować przepływ pracy dla zleceń zmiany inżynieryjnej lub żądań zmiany, przejdź do **Zarządzanie zmianami inżynieryjnymi \> Przepływy pracy inżynieryjnej**.  Wybierz opcję **Nowy**, określ, czy przepływ pracy będzie używany do przeglądania zleceń zmiany inżynierów lub technicznych żądań zmiany, a następnie skonfiguruj przepływ pracy.

Więcej informacji na temat pracy z przepływami pracy zawiera temat [Omówienie tworzenia przepływów pracy](../../fin-ops-core/fin-ops/organization-administration/overview-workflow-system.md).

Poniżej przedstawiono kilku typowych udziałowców, którzy mogą potrzebować zatwierdzić zlecenia zmiany inżynieryjnej:

- **Właściciele produktu** – Aby uzyskać więcej informacji o własności danych, należy zapoznać się z artykułem [Właściciele produktów](product-owner.md).
- **Odpowiedzialny szef zespołu** — pole **Inżynier** w widoku **Nagłówek** zlecenia zmiany inżynieryjnej pokazuje inżyniera, który utworzył zlecenie zmiany inżynieryjnej. Jeśli inżynier należy do zespołu, który jest zdefiniowany w systemie, pole **Odpowiedzialna osoba** pokazuje lidera tego zespołu.
- **Dział finansowy** — dział finansowy może chcieć przejrzeć sprawy, w których zmiana dotyczy wysokich kosztów.

Można określić, czy kolejność zmian inżynieryjnych ma być przetwarzana bezpośrednio po zaakceptowaniu, jako część przepływu pracy, czy też należy ją wykonać w późniejszym kroku. W trakcie przetwarzania zlecenia zmiany inżynieryjne aktualizowane są dane techniczne dotyczące rzeczywistego produktu.

Podczas przeglądania wniosku o zmianę, w okienku akcji, na karcie **Żądanie zmiany** w grupie **Wpływ biznesowy** wybierz opcję **Wyszukaj**, aby ocenić wpływ proponowanej zmiany na otwarte transakcje, takie jak zamówienia sprzedaży, zlecenia produkcyjne i dostępne zapasy. Wyniki są wyświetlane w oknie dialogowym **Wpływ biznesowy na otwarte transakcje**, w którym można wybrać transakcje, a następnie skorzystać z poleceń na pasku narzędzi, aby wyświetlić więcej informacji, powiadomić użytkownika o tym fakcie lub zablokować transakcję.

### <a name="engineering-change-orders-in-engineering-or-operational-companies"></a>Zlecenia zmian inżynieryjnych w firmach inżynieryjnych lub operacyjnych

Jak opisano w sekcji [Firmy inżynierskie i reguły własności danych ](engineering-org-data-ownership-rules.md), dane produktu, które można edytować, różnią się w zależności od typu firmy, w której pracuje użytkownik (firma inżynierska vs. firma operacyjna). Reguły własności danych są również stosowane do zleceń zmian inżynieryjnych. W związku z tym w zależności od firmy, w której tworzone są zmiany inżynieryjne, można wprowadzać różne typy zmian. Oto kilka przykładów:

- W przypadku zleceń zmiany w *firmie inżynierskiej* można wprowadzać podstawowe zmiany w danych inżynierii. Można na przykład utworzyć nowe wersje produktu, zmienić strukturę produktu za pośrednictwem BOM i zmienić wartości atrybutów inżynierii. Dla każdego produktu, którego dotyczy ten problem, wybierz jedną z następujących wartości w polu **Wpływ**:

    - **Brak** — Aktualizacja istniejącej wersji produktu (aktualizacja w wersji).
    - **Nowa wersja** — umożliwia utworzenie nowej wersji opartej na wybranej wersji produktu.
    - **Nowy produkt** — służy do tworzenia zupełnie nowego produktu, który jest oparty na wybranej wersji produktu.
    - **Nowy wariant** — umożliwia utworzenie nowego wariantu opartego na wybranej wersji produktu. Zostaną skopiowane informacje o BOM i marszrucie.

- W przypadku zleceń zmiany inżynierów w *firmie operacyjnej* można zmienić dane logistyczne produktu. Można na przykład wzbogacić istniejący BOM z ustawieniami dotyczącymi pochodzenia, dodać trasy lokalne lub lokalne BOM, a nawet wzbogacać BOM przez dodanie nowych wierszy BOM dla lokalnych materiałów opakowań, płynów smarowych lub instrukcji w języku lokalnym. Wzbogacanie wprowadzane przez użytkowników w firmie operacyjnej zostaną zachowane po wysłaniu nowych aktualizacji z firmy inżynierskiej. Aby uzyskać więcej informacji, zobacz artykuł [Firm inżynierskie i reguły własności danych](engineering-org-data-ownership-rules.md).

    Podczas przetwarzania zleceń zmiany inżynieryjnej w firmie inżynierskiej produkty są tworzone i/lub aktualizowane tylko w firmie inżynierskiej. Dlatego, jeśli dane główne produktu powinny być również aktualizowane, należy również wydawać produkty do firm operacyjnych.

- Produkty można wydawać bezpośrednio z technologicznych zleceń zmiany. Otwórz zamówienie zmiany, a następnie w okienku akcji, na karcie **Zmiana zamówienia** w grupie **Wydania produktów** wybierz pozycję **Wydaj strukturę produktu**. Proces działa tak samo, jak działa po wydawania produktów ze strony **Wydane produkty**. Aby uzyskać więcej informacji, zobacz [Zwalnianie struktur produktu](release-product-structure.md).
- Produkty mogą być automatycznie wydawane z inżynieryjnych zleceń zmiany, na podstawie następujących czynników:

    - Ponowne wydanie do firm, gdzie wydano wcześniej produkty. Wybierz opcję **Wyszukaj**, aby skanować wszystkie poprzednie wydania, a następnie wybierz opcję **Widok**, aby wyświetlić wyniki. Na stronie **Widok** są wyświetlane poprzednie wydania produktów i można wybrać produkty, które mają zostać ponownie wydane. Zamknij stronę **Widok** i wybierz opcję **Proces**, aby ponownie wydać wybrane produkty.
    - Ustawienia automatycznego wydawania w obszarze kontroli wydawania w kategorii produktów inżynierii. Wydanie można wykonać jako część przepływu pracy. Gdy zostanie użyty blok **Zbierz propozycje wydania**, propozycja wydania zostanie wypełniona ponownie wydanymi propozycjami (zobacz poprzednią pozycję listy), a produkty zostaną wydane do firm, jeśli jest zaznaczone pole wyboru **Automatyczne wydawanie** w obszarze kontrola zwolnień w kategorii produktów inżynierii. Można wybrać **Widok**, aby wyświetlić wyniki, zgodnie z opisem w poprzedniej pozycji listy. Produkty zostaną również wydane, gdy zostanie użyty blok **propozycji wydania procesu**. W przypadku wybrania opcji tylko do zbierania propozycji wydania w ramach przepływu pracy można ręcznie rozpocząć wydawanie, wybierając opcję **Proces**, zgodnie z opisem zamieszczonym w poprzednim elemencie listy.

## <a name="follow-up-on-an-engineering-change-request-via-an-engineering-change-order"></a>Działanie następcze na żądanie zmiany w ramach zlecenia zmiany

Gdy żądanie zmiany zostanie zatwierdzone, można obserwować jej na podstawie zatwierdzonego inżynieryjnego zlecenia zmiany. Wiele wniosków o zmiany można połączyć w jedno zamówienie zmiany inżynieryjnej. Jedno zamówienie zmiany może obejmować nawet wiele produktów. (Zazwyczaj takie rozwiązanie należy stosować w przypadku, gdy ta sama zmiana musi zostać zastosowana w przypadku wielu produktów). Nie można jednak utworzyć wielu zleceń zmiany inżynieryjnej za pomocą jednego żądania zmiany inżynieryjnej.

Aby kontynuować żądanie zmiany w ramach zamówienia zmiany, Otwórz żądanie zmiany, a następnie w okienku akcji, na karcie **Zlecenie zmiany**, w grupie **Żądanie zmiany inżynieryjnej** wybierz opcję **Kopiuj łącze i produkty**. Następnie można wybrać istniejący porządek zmian inżynieryjnych, aby połączyć żądanie zmiany, albo utworzyć nowe zlecenie zmiany inżyniera dla tego konkretnego żądania.

## <a name="engineering-change-order-report"></a>Raport zlecenia zmiany projektowej

Raporty dotyczące zamówień zmian inżynieryjnych opisują zmiany wprowadzone w zamówieniu zmian. Są one przydatne zarówno podczas procesu recenzowania, jak i po zatwierdzeniu.

Aby wyświetlić raport o zmianie inżynieryjnej, otwórz odpowiednie zamówienie zmiany, a następnie w okienku akcji na karcie **Zlecenie zmiany** w grupie **Widok** wybierz opcję **Raport zleceń zmian inżynieryjnych**.

## <a name="fields-on-an-engineering-change-order"></a>Pola na zleceniu zmiany inżynieryjnej

Większość pól na zleceniach zmiany technologicznej jest taka sama, jak pola dla wydanych produktów, wersji inżynierii, dokumentów, BOM (wierszy) i marszrut (operacji). Jednak pola w poniższej tabeli są unikatowe w celu zmiany zamówień.

| Pole | opis |
|---|---|
| Przyczyna zmiany projektowej | Wybierz przyczynę zmiany produktu. |
| Opis zmiany | Służy do wprowadzania opisu zmiany. |
| Wymagane narzędzia specjalne | Określ, czy do zastosowania zmiany są wymagane specjalne narzędzia. |
| Dyspozycja materiałów inżynieryjnych | Umożliwia wybór kodu dyspozycji materiału dla odpadów powstających w momencie zastosowania zmiany. |
| Wymagane zatwierdzenie odbiorcy | Określ, czy wymagane jest zatwierdzenie odbiorcy, zanim zmiana będzie mogła zostać zastosowana. |
| Uzyskane zatwierdzenie odbiorcy | Umożliwia określenie stanu zatwierdzenia odbiorcy. |
| BHPiOŚ | Określ, czy zasady dotyczące BHPiOŚ mają być zastosowane do zmiany. W takim przypadku można wybrać odpowiednie reguły. |

Aby skopiować informacje o zmianach dotyczących produktów, których dotyczy problem, można skorzystać z przycisku **Zachowaj/Skopiuj zmiany informacji**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
