---
title: Wnioski o nadanie kategorii od dostawców
description: W tym temacie opisano sposób, w jaki dostawcy mogą wnioskować o nadanie kategorii dla swojego konta. Opisano w nim również proces zatwierdzania wykonywany przez agentów ds. zaopatrzenia.
author: GalynaFedorova
ms.date: 04/19/2021
ms.topic: article
ms.search.form: VendRequestNewCategory
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: gfedorova
ms.search.validFrom: 2021-04-19
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 9874151a5d82cc3441741489065877b78bab7bf5
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/03/2022
ms.locfileid: "8671218"
---
# <a name="category-requests-from-vendors"></a>Wnioski o nadanie kategorii od dostawców

[!include [banner](../includes/banner.md)]

Proces wniosku o nadanie kategorii umożliwia dostawcy żądanie, aby nowe kategorie zaopatrzenia skojarzyć z ich kontem. Kategorie zaopatrzenia mogą być następnie używane przez powiązane procesy zaopatrzenia i sourcingu. (Aby uzyskać więcej informacji, zobacz [Omówienie katalogów zaopatrzenia](procurement-catalogs.md)).

Wnioski o nadanie kategorii są inicjowane przez dostawców w obszarze roboczym **Informacje o dostawcy**. Są one następnie przesyłane do agencji w celu ich przejrzenia i zatwierdzenia. Zatwierdzone kategorie są dodawane do listy kategorii zaopatrzenia dla konta dostawcy.

## <a name="turn-the-category-requests-from-vendors-feature-on-or-off"></a>Włączanie lub wyłączanie funkcji wniosków o nadanych dostawcom kategorii

Od wersji 10.0.25 Supply Chain Management version ta funkcja jest domyślnie włączona. Administratorzy mogą włączyć lub wyłączyć tę funkcję, *wyszukując funkcję Zezwalaj dostawcom na stosowanie kategorii zaopatrzenia za pośrednictwem funkcji portalu współpracy* z dostawcami w obszarze [roboczym Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

Po włączeniu tej funkcji nadal można ręcznie dodawać kategorie zaopatrzenia do kont dostawców. Aby uzyskać więcej informacji, zobacz [Zatwierdzanie dostawców dla konkretnych kategorii zaopatrzenia](tasks/approve-vendors-specific-procurement-categories.md).

## <a name="vendor-collaboration-requirements"></a>Wymagania portalu współpracy z dostawcami

Aby dostawca mógł wykonywać działania na wnioskach o nadanie kategorii, musi mu zostać skonfigurowany portal współpracy z dostawcami.

Dostawca musi mieć co najmniej jednego użytkownika portalu współpracy z dostawcami. Tylko użytkownicy dostawcy z rolą zabezpieczeń *Administrator dostawcy (zewnętrzny)* mogą tworzyć i przesyłać żądania kategorii.

Aby uzyskać więcej informacji, zobacz temat [Konfigurowanie i obsługa współpracy z dostawcami](set-up-maintain-vendor-collaboration.md).

## <a name="set-up-the-vendor-category-request-workflow"></a>Konfigurowanie przepływu pracy Wniosek o nadanie kategorii dostawcy

Przepływ pracy *Wniosek o nadanie kategorii dostawcy* musi być ustawiony w przepływach pracy zaopatrzenia i sourcingu. Dostawcy będą przesyłać nowe wnioski o nadanie kategorii, które można przeglądać i zatwierdzać. Żądane kategorie zaopatrzenia są dodawane do konta dostawcy po zatwierdzeniu wniosku o nadanie kategorii.

W poniższym przykładzie pokazano, jak skonfigurować prosty przepływ pracy *Wniosek o nadanie kategorii dostawcy* z jedną osobą zatwierdzającą. Należy przejrzeć procesy wewnętrzne, aby określić odpowiednie ustawienia przepływu pracy dla swojej agencji.

1. Przejdź do **Zaopatrzenie i sourcing \> ustawień \> Przepływy pracy modułu Zaopatrzenie i sourcing**.
1. W okienku akcji wybierz opcję **Nowy**.
1. W oknie dialogowym wybierz **Przepływ pracy wniosku o nadanie kategorii dostawcy**, aby otworzyć edytor przepływu pracy.
1. Zaloguj się do edytora przepływu pracy.
1. W okienku akcji kliknij przycisk **Właściwości**.
1. Na stronie **Właściwości** przepływu pracy w polu **Instrukcje przesyłania** wprowadź tekst instrukcji. Instrukcje będą widoczne dla dostawców podczas przesyłania wniosku o nadanie kategorii.
1. Zamknij stronę **Właściwości**.
1. Przeciągnij element przepływu pracy **Zatwierdź nowy wniosek o nadanie kategorii** na kanwę.
1. Przeciągnij łącze z elementu przepływu pracy **Rozpocznij** do elementu przepływu pracy **Zatwierdź nowy wniosek o nadanie kategorii**.
1. Przeciągnij łącze z elementu przepływu pracy **Zatwierdź nowy wniosek o nadanie kategorii** do elementu przepływu pracy **Zakończ**.
1. Kliknij dwukrotnie element przepływu pracy **Zatwierdź nowy wniosek o nadanie kategorii**.
1. Wybierz i przytrzymaj (lub kliknij prawym przyciskiem myszy) element przepływu pracy **Krok 1**, a następnie wybierz **właściwości**.
1. Na stronie **Właściwości** elementu przepływu pracy w polu **Temat elementu pracy** wprowadź tekst tematu. Ten tekst będzie wyświetlany jako wartość pola **Temat** na stronie **Elementy pracy przypisane do mnie**.
1. W polu **Instrukcje dotyczące elementu produkcyjnego** wprowadź tekst instrukcji. Instrukcje będą widoczne dla osób zatwierdzających po wybraniu opcji **Przepływ pracy** w okienku akcji wniosku o nadanie kategorii.
1. W lewym okienku wybierz **Przypisanie**.
1. Na karcie **Typ przypisania** ustaw pozycję **Przypisz użytkowników do tego elementu przepływu pracy** na *użytkownik*.
1. Na karcie **Użytkownik** z listy **Dostępni użytkownicy** wybierz osobę zatwierdzającą. Na przykład wybierz użytkownika w dziale zaopatrzenia.
1. Wybierz przycisk strzałki w prawo (**\>**), aby przenieść osobę zatwierdzającą do listy **Wybrani użytkownicy**.
1. Zamknij stronę **Właściwości**.
1. Wybierz opcję **Zapisz i zamknij**.
1. W polu **Uwagi dotyczące wersji** wprowadź uwagi dotyczące przepływu pracy.
1. Wybierz przycisk **OK**, aby zapisać przepływ pracy.
1. Jeśli wszystko jest gotowe do rozpoczęcia testów przepływu pracy, wybierz opcję **Aktywuj nową wersję**. W przeciwnym razie wybierz opcję **Nie aktywuj nowej wersji**.
1. Naciśnij przycisk **OK**, aby zakończyć konfigurowanie przepływu pracy.

> [!TIP]
> Jeśli agencja nie wymaga zatwierdzania wniosków o nadanie kategorii, należy skonfigurować przepływ pracy do automatycznego zatwierdzania.

Więcej informacji na temat konfigurowania przepływów pracy zawiera temat [Omówienie tworzenia przepływów pracy](../../fin-ops-core/fin-ops/organization-administration/overview-workflow-system.md).

## <a name="create-and-submit-a-category-request"></a>Tworzenie i przesyłanie wniosku o nadanie kategorię

W tej sekcji opisano, w jaki sposób dostawcy mogą używać obszaru roboczego **Informacje o dostawcy** w celu tworzenia, edytowania, wyświetlania i przesyłania wniosków o nadanie kategorii.

### <a name="start-a-new-request"></a>Uruchamianie nowego wniosku

Aby uruchomić nowy wniosek o nadanie kategorii, wykonaj następujące czynności.

1. W obszarze roboczym **Informacje o dostawcy** wybierz kafelek **Wnioski o nadanie kategorii**.
1. Na stronie **Wnioski o nadanie kategorii** w okienku akcji wybierz pozycję **Nowy wniosek o nadanie kategorii**.
1. W oknie dialogowym **Nowy wniosek o nadanie kategorii** znajdź kategorię, o którą chcesz się ubiegać, poruszając się po drzewie i/lub korzystając z filtru u góry listy. Zaznacz pole wyboru dla każdej odpowiedniej kategorii.

    Należy uwzględnić następujące informacje:

    - Kategorie obecnie aktywne na koncie dostawcy są pokazywane jako wybrane i nie można ich usunąć.
    - W jednym wniosku o nadanie kategorii można wnioskować o wiele kategorii zaopatrzenia.

1. Wybierz **OK**, aby utworzyć roboczy wniosek.

    Na stronie **Wnioski o nadanie kategorii** pojawi się nowy wniosek w wersji roboczej.

1. Otwórz nowy wniosek w wersji roboczej, aby go przejrzeć i edytować w razie potrzeby.

    - Aby wyświetlić listę kategorii obecnie uwzględnionych we wniosku, wybierz skróconą kartę **Wnioskowane kategorie**.
    - Aby wyświetlić aktywne kategorie, otwórz pole informacji **Aktywne kategorie** po prawej stronie.
    - Aby dodać kategorię do wniosku, wybierz pozycję **Dodaj** na pasku narzędzi na skróconej karcie **Wnioskowane kategorie**.
    - Aby usunąć kategorię z wniosku, wybierz kategorię na skróconej karcie **Wnioskowane kategorie**, a następnie wybierz pozycję **Usuń** na pasku narzędzi.
    - Aby dołączyć dokument do wniosku, wybierz **załączniki** w okienku akcji. Dołączone dokumenty będą dostępne dla osób zatwierdzających podczas przeglądania wniosku o nadanie kategorii.
    - Aby usunąć dołączony dokument z wniosku, wybierz **załączniki** w okienku akcji. Wybierz dokument do usunięcia, a następnie wybierz polecenie **Usuń** w okienku akcji.

1. Jeśli możesz już przesłać wniosek, wybierz pozycję **Prześlij** w okienku akcji. W przeciwnym razie zamknij stronę i pomiń pozostałe kroki tej procedury. Następnie możesz wrócić do wniosku później.
1. Przeczytaj wyświetlone instrukcje przesyłania, a następnie wybierz polecenie **Prześlij**.
1. W polu **Komentarz** wprowadź dodatkowe informacje, które są wymagane. Następnie naciśnij przycisk **Prześlij**, aby zakończyć wniosek.

### <a name="edit-a-draft-or-recalled-request"></a>Edytowanie wniosku w wersji roboczej lub wycofanego

Aby zmodyfikować wniosek o nadanie kategorii w wersji roboczej lub wycofany, wykonaj poniższe kroki.

1. W obszarze roboczym **Informacje o dostawcy** wybierz kafelek **Wnioski o nadanie kategorii**.
1. Wybierz wniosek w wersji roboczej lub wycofany, aby go otworzyć.
1. Zmodyfikuj wniosek zgodnie z potrzebą, a następnie zamknij lub prześlij go zgodnie z opisem w poprzedniej procedurze.

### <a name="submit-a-draft-or-recalled-request"></a>Przesyłanie wniosku w wersji roboczej lub wycofanego

Aby przesłać wniosek o nadanie kategorii w wersji roboczej lub wycofany, wykonaj poniższe kroki.

1. W obszarze roboczym **Informacje o dostawcy** wybierz kafelek **Wnioski o nadanie kategorii**.
1. Wybierz wniosek w wersji roboczej lub wycofany, który chcesz przesłać.
1. W okienku akcji kliknij przycisk **Prześlij**.
1. Przeczytaj wyświetlone instrukcje przesyłania, a następnie wybierz polecenie **Prześlij**.
1. W polu **Komentarz** wprowadź dodatkowe informacje, które są wymagane. Następnie naciśnij przycisk **Prześlij**, aby zakończyć wniosek.

    Stan wniosku o nadanie kategorii zmienia się na jedną z następujących wartości:

    - _Oczekuje na przegląd_ — Wniosek jest w przepływie pracy.
    - _Oczekuje na zatwierdzenie_ — jest wymagane zatwierdzenie.

### <a name="recall-a-submitted-request-that-hasnt-yet-been-approved"></a>Wycofywanie przesłanego wniosku, który nie został jeszcze zatwierdzony

Aby odwołać wniosek o nadanie kategorię, który został przesłany, ale jeszcze nie został zatwierdzony, wykonaj następujące kroki.

1. W obszarze roboczym **Informacje o dostawcy** wybierz kafelek **Wnioski o nadanie kategorii**.
1. Wybierz oczekujący wniosek, który chcesz odwołać.
1. W okienku akcji kliknij przycisk **Odwołaj**.
1. W polu **Wprowadź komentarz** wprowadź dodatkowe informacje, które są wymagane. Następnie naciśnij przycisk **Prześlij**, aby zakończyć wniosek.

    Stan wniosku o nadanie kategorii zostanie zmieniony na _Anulowany_. Wniosek pozostanie w tym stanie do czasu jego usunięcia lub ponownego przesłania.

### <a name="delete-a-draft-or-recalled-request"></a>Usuwanie wniosku w wersji roboczej lub wycofanego

Aby usunąć wniosek o nadanie kategorii w wersji roboczej lub wycofany, wykonaj poniższe kroki.

1. W obszarze roboczym **Informacje o dostawcy** wybierz kafelek **Wnioski o nadanie kategorii**.
1. Wybierz wniosek w wersji roboczej lub wycofany, który chcesz usunąć.
1. W okienku akcji wybierz opcję **Usuń**.
1. Wybierz **Tak**, aby potwierdzić usunięcie.

### <a name="view-completed-requests"></a>Wyświetlanie zakończonych wniosków

Aby wyświetlić zakończone wnioski, otwórz obszar roboczy **Informacje o dostawcy** i wybierz kafelek **Wnioski o nadanie kategorii**. Zakończone wnioski o nadanie kategorii będą mieć jeden z następujących stanów:

- _Zatwierdzony_ — wniosek został zatwierdzony. Aby wyświetlić nowo dodane kategorie, wróć do obszaru roboczego **Informacje o dostawcy**, otwórz listę rozwijaną **Więcej szczegółów** w lewym okienku, a następnie wybierz pozycję **Kategorie**.
- _Odrzucony_ — wniosek został odrzucony. W razie potrzeby możesz utworzyć nowy wniosek o nadanie kategorii.

## <a name="review-category-requests"></a>Przeglądanie wniosków o nadanie kategorii

W tej sekcji opisano sposób zatwierdzania, odrzucania i delegowania wniosków o nadanie kategorii przesłanych przez dostawców oraz sposobu wyświetlania zakończonych wniosków. Te akcje przepływu pracy są dla całego wniosku o nadanie kategorii.

### <a name="view-category-requests"></a>Wyświetlanie wniosków o nadanie kategorii

Aby wyświetlić wnioski o nadanie kategorii, wykonaj następujące czynności.

1. Przejdź do **Zaopatrzenie i sourcing \> Dostawcy \> Wnioski portalu współpracy z dostawcami \> Wnioski o nadanie kategorii**.

    Zostanie wyświetlona strona **Wnioski o nadanie kategorii**. Domyślny widok strony pokazuje wnioski o nadanie kategorii o stanie *Oczekiwanie na akcję*.

1. Aby wyświetlić wszystkie wnioski, zaznacz opcję *Wszystkie* w polu **Pokaż wnioski**.
1. Otwórz wniosek, aby go przejrzeć i edytować w razie potrzeby.

    - Aby wyświetlić listę kategorii obecnie uwzględnionych we wniosku, wybierz skróconą kartę **Wnioskowane kategorie**.
    - Aby wyświetlić aktywne kategorie, otwórz pole informacji **Aktywne kategorie** po prawej stronie.
    - Jeśli dokumenty zostały przesłane, przycisk **Załączniki** (spinacz do papieru) w okienku akcji pokazuje liczbę dołączonych dokumentów. Aby wyświetlić dołączone dokumenty, wybierz przycisk **Załączniki**. Następnie wybierz dokument, który chcesz wyświetlić, i wybierz opcję **Otwórz**, aby go wyświetlić.
    - Aby dołączyć dokument do wniosku, wybierz **załączniki** w okienku akcji. Dołączone dokumenty będą dostępne dla osób zatwierdzających podczas przeglądania wniosku o nadanie kategorii.
    - Aby usunąć dołączony dokument z wniosku, wybierz **załączniki** w okienku akcji. Wybierz dokument do usunięcia, a następnie wybierz polecenie **Usuń** w okienku akcji.
    - Aby wyświetlić historię przepływu pracy, wybierz **Przepływ pracy** w okienku akcji. W opcjach przepływu pracy wybierz pozycję **Więcej**, a następnie **Historia przepływu pracy**. Zostanie wyświetlona strona **Historia przepływu pracy**.

### <a name="approve-a-pending-category-request"></a>Zatwierdzanie oczekującego wniosku o nadanie kategorii

Aby zatwierdzić oczekujący wniosek o nadanie kategorii, wykonaj następujące czynności.

1. Przejdź do **Zaopatrzenie i sourcing \> Dostawcy \> Wnioski portalu współpracy z dostawcami \> Wnioski o nadanie kategorii**.
1. Wybierz oczekujący wniosek do zatwierdzenia.
1. Przejrzyj wniosek o nadanie kategorii.
1. Opcjonalnie: na skróconej karcie **Ogólne** w polu **Kod przyczyny** wybierz kod przyczyny. Następnie w polu **Komentarz do przyczyny** wprowadź komentarz o kodzie przyczyny.
1. W okienku akcji wybierz opcję **Przepływ pracy**.
1. W opcjach przepływu pracy wybierz pozycję **Zatwierdź**.
1. W polu **Komentarz** wprowadź dodatkowe informacje, które są wymagane. Następnie naciśnij przycisk **Zatwierdź**, aby zakończyć wniosek.

    Stan wniosku o nadanie kategorię zostanie zmieniony na _Zatwierdzone_, a kategorie zaopatrzenia zostaną dodane do konta dostawcy.

### <a name="reject-a-pending-category-request"></a>Odrzucanie oczekującego wniosku o nadanie kategorii

Aby odrzucić oczekujący wniosek o nadanie kategorii, wykonaj następujące czynności.

1. Przejdź do **Zaopatrzenie i sourcing \> Dostawcy \> Wnioski portalu współpracy z dostawcami \> Wnioski o nadanie kategorii**.
1. Wybierz oczekujący wniosek do odrzucenia.
1. Przejrzyj wniosek o nadanie kategorii.
1. W okienku akcji wybierz pozycję **Edytuj**.
1. Na skróconej karcie **Ogólne** w polu **Kod przyczyny** wybierz kod przyczyny. Następnie w polu **Komentarz do przyczyny** wprowadź komentarz o kodzie przyczyny.
1. Na okienku akcji wybierz opcję **Zapisz**.
1. W okienku akcji wybierz opcję **Przepływ pracy**.
1. W opcjach przepływu pracy wybierz pozycję **Więcej**, a następnie **Odrzuć**.
1. W polu **Komentarz** wprowadź dodatkowe informacje, które są wymagane. Następnie naciśnij przycisk **Odrzuć**, aby zakończyć wniosek.

    Stan wniosku o nadanie kategorii zostanie zmieniony na _Odrzucony_. Na tym etapie dostawca może w razie potrzeby utworzyć nowy wniosek o nadanie kategorię.

### <a name="delegate-a-pending-category-request"></a>Delegowanie oczekującego wniosku o nadanie kategorii

Aby delegować oczekujący wniosek o nadanie kategorii do innego użytkownika, wykonaj następujące kroki.

1. Przejdź do **Zaopatrzenie i sourcing \> Dostawcy \> Wnioski portalu współpracy z dostawcami \> Wnioski o nadanie kategorii**.
1. Wybierz oczekujący wniosek, który chcesz zatwierdzić.
1. W okienku akcji wybierz opcję **Przepływ pracy**.
1. W opcjach przepływu pracy wybierz pozycję **Więcej**, a następnie **Deleguj**.
1. W polu **Użytkownik** wybierz użytkownika, któremu ma zostać przypisany wniosek o nadanie kategorii do przeglądu.
1. W polu **Komentarz** wprowadź dodatkowe informacje, które są wymagane.
1. Wybierz opcję **Deleguj**, aby zakończyć delegowanie. Wybrany użytkownik może teraz przejrzeć wniosek o nadanie kategorii.

### <a name="view-procurement-categories-for-a-vendor"></a>Przeglądanie kategorii zaopatrzenia dla dostawcy

Aby wyświetlić kategorie zaopatrzenia dla dostawcy po zatwierdzeniu wniosku o nadanie kategorii, wykonaj następujące czynności.

1. Wybierz kolejno opcje **Zaopatrzenie i sourcing \> Dostawcy \> Wszyscy dostawcy**.
1. Na stronie **Wszyscy dostawcy** wybierz dostawcę, którego kategorie zaopatrzenia chcesz wyświetlić.
1. W okienku akcji otwórz kartę **Ogólne** i z grupy **Ustawienia** wybierz pozycję **Kategorie**.

    Zostanie wyświetlona strona **Kategorie**. Na skróconej karcie **Zaopatrzenie** są pokazane kategorie zaopatrzenia dodane za pomocą wniosku o nadanie kategorii.

1. Na skróconej karcie **Zaopatrzenie** można w razie potrzeby wprowadzać zmiany. Na przykład w polu **Stan kategorii dostawcy** można ustawić wartość _Preferowana_.
