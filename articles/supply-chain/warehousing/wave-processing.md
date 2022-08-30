---
title: Tworzenie i przetwarzanie grupy czynności
description: W tym artykule opisano, jak utworzyć, przetwarzać i zwolnić grupę czynności w celu utworzeniu pobrania dla ładunku, wysyłki, zlecenia produkcyjnego lub zamówienia Kanban.
author: Mirzaab
ms.date: 08/09/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSWaveTemplateTable, WHSParameters, whswavetablecreatenew, WHSWaveTable, WHSWaveAttributes, WHSKanbanWaveTable, WHSWaveTableListPage, WHSKanbanWaveTableListPage, WHSProdWaveTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-03-08
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 0466019990773ee93e063a255c15a7d64eecdf78
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/23/2022
ms.locfileid: "9336014"
---
# <a name="wave-creation-and-processing"></a>Tworzenie i przetwarzanie grupy czynności

[!include [banner](../includes/banner.md)]

W tym artykule opisano, jak utworzyć, przetwarzać i zwolnić grupę czynności w celu utworzeniu pobrania dla ładunku, wysyłki, zlecenia produkcyjnego lub zamówienia Kanban. Możliwe jest utworzenie grup czynności następujących zamówień:

- **Zamówienia sprzedaży** — można wykorzystać grupy czynności wysyłkowych, aby uwzględnić wiersze z zamówień sprzedaży. Jeśli zamówienie sprzedaży zostało zwolnione do magazynu, wierszy zamówienia sprzedaży można objąć grupą czynności.
- **Zlecenia produkcyjne** — można użyć grupy czynności produkcyjnych w celu uwzględnienia wierszy z BOM dla produktu.
- **Zamówienia Kanban** — grupy czynności Kanban zawierają wiersze listy pobrania z zamówień Kanban.

W przypadku zamówień sprzedaży i zamówień Kanban zapasy muszą być zarezerwowane przed zwolnieniem zamówienia do magazynu. W przeciwnym razie towary lub wiersze alokacji nie mogą zostać przetworzone w grupie czynności. Zlecenia produkcyjne są jednak nieco bardziej elastyczne. W przypadku zleceń produkcyjnych można wybrać jedną z następujących opcji:

- Określ, czy wszystkie materiały muszą zostać zarezerwowane przed zwolnieniem zamówienia do magazynu.
- Określ, czy wszystkie materiały muszą zostać zarezerwowane przed zwolnieniem zamówienia do magazynu. Jeśli zostanie wybrana ta opcja, należy ręcznie powtórzyć zwolnienia do procesu magazynowego, gdy dodatkowe materiały stają się dostępne. Na przykład jest to przydatne w przypadku materiałów, których produkcję należy uruchomić, i można poczekać, aż materiały dodatkowe stają się dostępne.

Można określić, która z tych opcji zlecenia produkcyjnego będzie domyślnie używać, korzystając z pola **Zapotrzebowanie na rezerwację materiałów** na stronie **Parametry kontroli produkcji**. Można jednak zmienić to ustawienie dla określonego zlecenia produkcyjnego w dowolnym momencie. Aby uzyskać więcej informacji, zobacz [parametry magazynu do przetwarzania grupy czynności](wave-warehouse-parameters.md).

## <a name="create-and-process-a-wave"></a>Tworzenie i przetwarzanie grupy czynności

Na poniższym schemacie przedstawiono przepływ, w jaki są tworzone, przetwarzane i zwalniane przepływy wysyłki. Numery odpowiadają procedurom opisanym w dalszej części.

![Proces tworzenia grupy czynności.](media/wave-processing-diagram.png "Proces tworzneia grupy czynności")

### <a name="prerequisites"></a>Wymagania wstępne

Aby rozpocząć, szablon grupy czynności musi być dostępny dla typu grupy czynności, którą chcesz utworzyć (wysyłka, produkcja lub Kanban). Szablon grupy czynności ustala wiele ustawień dotyczących sposobu generowania i przetwarzania grupy czynności, w tym czynności, które należy wykonać ręcznie i które są wykonywane automatycznie. Aby uzyskać więcej informacji o szablonach, zobacz temat [Szablony grupy czynności](wave-templates.md).

### <a name="create-a-wave"></a>Tworzenie grupy czynności

#### <a name="automatically-create-waves-based-on-warehouse-and-order-type"></a>Automatyczne tworzenie grupy pracy na podstawie magazynu i typu zamówienia

Aby automatycznie tworzyć grupy czynności, skonfiguruj [szablony grupy czynności](wave-templates.md) odpowiednie dla każdego typu zamówienia i magazynu. Upewnij się, że w każdym szablonie ustawienie **Automatyczne tworzenie grupy czynności** ma wartość *Tak*.

#### <a name="manually-create-waves"></a>Ręczne tworzenie grupy czynności

Aby ręcznie utworzyć grupę czynności, należy wykonać następujące czynności:

1. Upewnij się, że odpowiednie [szablony grupy czynności](wave-templates.md) nie są ustawione w taki sposób, aby automatycznie tworzyły grupy czynności dla magazynu i typów zamówień, w których ma to być wykonywane ręcznie.
1. W zależności od typu grupy czynności do utworzenia, kliknij jedną z następujących opcji:

    - Przejdź do **Zarządzanie magazynem** \> **Wychodzące grupy czynności** \> **Grupy czynności wysyłki** \> **Wszystkie grupy czynności**. Na okienku akcji wybierz opcję **Grupa czynności**.
    - Przejdź do **Zarządzanie magazynem** \> **Grupy czynności** \> **Grupy czynności wysyłki** \> **Wszystkie grupy czynności**. Na okienku akcji wybierz opcję **Grupa czynności**.
    - Przejdź do **Zarządzanie magazynem** \> **Grupy czynności** \> **Grupy czynności wysyłki** \> **Wszystkie grupy czynności**. Na okienku akcji wybierz opcję **Grupa czynności**.

1. W polu **Opis** wprowadź krótki opis grupy czynności. Powinien wskazywać, co jest przetwarzane w grupie czynności.

1. W polu **Nazwa szablonu grupy czynności** wybierz szablon grupy czynności dla typu grupy czynności do utworzenia. Szablon grupy czynności zawiera metody grupy czynności, jakie będą wykonywać operacje, takie jak tworzenie pracy dla grupy czynności. Na przykład szablon grupy czynności dla grupy czynności wysyłkowych może zawierać metody tworzenia ładunków, przypisania wierszy do grup czynności, uzupełnienia i tworzenia pobrania pracy dla grupy czynności.

1. Opcjonalnie: jeśli chcesz użyć atrybutów grupy czynności jako dodatkowych kryteriów zapytania dla grupy czynności, wybierz atrybuty w polach **Atrybuty grupy czynności**.

### <a name="specify-what-to-include-in-a-wave"></a>Co powinna zawierać lista kontrolna

Po utworzeniu grupy czynności można rozpocząć dodawanie zawartości do tej grupy.

> [!NOTE]
> W razie potrzeby można dodać wiersze do grupy czynności, nawet jeśli nie została zwolniona.

#### <a name="automatically-specify-what-to-include-in-a-wave"></a>Co powinna zawierać lista kontrolna

Aby automatycznie tworzyć grupy czynności, skonfiguruj [szablony grupy czynności](wave-templates.md) odpowiednie dla każdego typu zamówienia i magazynu. Upewnij się, że w każdym szablonie ustawienie **Automatyczne tworzenie grupy czynności** ma wartość *Tak*. Jeśli w ustawieniach opcji **Przypisz do otwartych grupy czynności** jest ustawiona wartość *Tak*, szablon może automatycznie przypisywać wiersze do wolnej zakwalifikowanej grupy czynności.

#### <a name="manually-specify-what-to-include-in-a-wave"></a>Co powinna zawierać lista kontrolna

Po utworzeniu grupy czynności, która nie została jeszcze zwolniona, można ręcznie określić, co ma w nim zawierać. Aby ręcznie dodać wiersze do grupy czynności:

1. W zależności od typu grupy czynności, dla której chcesz dodać wiersze, wykonaj jedną z następujących czynności:

    - Przejdź do **Zarządzanie magazynem** \> **Wychodzące grupy czynności** \> **Grupy czynności wysyłki** \> **Wszystkie grupy czynności**. Na okienku akcji wybierz opcję **Grupa czynności**.
    - Przejdź do **Zarządzanie magazynem** \> **Grupy czynności** \> **Grupy czynności wysyłki** \> **Wszystkie grupy czynności**. Na okienku akcji wybierz opcję **Grupa czynności**.
    - Przejdź do **Zarządzanie magazynem** \> **Grupy czynności** \> **Grupy czynności wysyłki** \> **Wszystkie grupy czynności**. Na okienku akcji wybierz opcję **Grupa czynności**.

1. Wybierz grupę czynności. W okienku akcji kliknij jedną z następujących opcji:

      - **Obsługa wysyłek**
      - **Obsługa produkcji**
      - **Obsługa list pobrania zadania Kanban**

1. W górnej części okna zaznacz wiersz, który ma zostać dodany do grupy czynności, a następnie kliknij przycisk **Dodaj do grupy czynności**. Wiersz jest przenoszony do skróconej karty **Wiersze grupy czynności**.

    Powtórz ten krok dla każdego wiersza do dodania. Aby dodać wszystkie wiersze, wybierz opcję **Dodaj wszystko**.

    > [!TIP]
    > Dla grupy czynności wysyłkowych można szybko znaleźć określoną kolejność, zaznaczając filtr niestandardowy w polu **Kod filtrowania grupy czynności**. Kody filtra grupy czynności zawierają kryteria kwerendy dla wysyłek, które są tworzone w formularzu **Filtry grupy czynności**. To pole nie jest dostępne dla grup czynności produkcyjnych lub grup czynności Kanban.
    > Zielony znacznik wyboru w kolumnie **W grupie czynności** wskazuje, że wysyłka została dodana do grupy czynności.

### <a name="process-the-wave-to-create-the-picking-work"></a>Przetwarzanie grupy czynności do wygenerowania pracy pobrania

Po utworzeniu grupy czynności zawierającej wszystkie wymagane wiersze można ją przetworzyć w celu utworzenia odpowiedniej pracy pobierania.

#### <a name="automatically-process-a-wave"></a>Przetwarzanie automatyczne grupy czynności

Aby automatycznie przetworzyć grupy czynności, skonfiguruj odpowiednie [Szablony grupy czynności](wave-templates.md) tak aby zawierały wymagane opcje automatycznego przetwarzania.

#### <a name="manually-process-a-wave"></a>Ręczne przetwarzanie grupy czynności

Grupy czynności można przetwarzać tylko wtedy, gdy ich **Stan grupy czynności** to *Utworzone*. Po przetwarzaniu grupy czynności **Stan grupy czynności** zostanie zmieniony na *Zatrzymana*.

Aby ręcznie przetworzyć grupy czynności z wymaganą zawartością, wykonaj następujące czynności:

1. W zależności od typu grupy czynności do przetworzenia wykonaj jedną z następujących czynności:

    - Wybierz **Zarządzanie magazynem** \> **Wychodzące grupy czynności** \> **Grupy czynności wysyłki** \> **Wszystkie grupy czynności**. Na okienku akcji wybierz opcję **Grupa czynności**.
    - Wybierz **Zarządzanie magazynem** \> **Grupy czynności** \> **Grupy czynności wysyłki** \> **Wszystkie grupy czynności**. Na okienku akcji wybierz opcję **Grupa czynności**.
    - Wybierz **Zarządzanie magazynem** \> **Wychodzące grupy czynności** \> **Grupy czynności wysyłki** \> **Wszystkie grupy czynności**. Na okienku akcji wybierz opcję **Grupa czynności**.

1. Wybierz grupę czynności do przetworzenia. W okienku akcji wybierz pozycję **Przetwarzanie**.

### <a name="release-the-wave-to-the-warehouse-to-start-picking-and-packing"></a>Zwalnianie grupy czynności do magazynu w celu rozpoczęcia pobierania i dostawy

Grupy czynności muszą zostać przetworzone przed zwolnieniem. Po zwolnieniu grupy czynności praca pobierania jest dostępna w magazynie. Można anulować grupę czynności po zwolnieniu i dodać więcej wierszy, ale nie można zmienić wierszy.

#### <a name="automatically-release-a-wave"></a>Przetwarzanie automatyczne grupy czynności

Aby automatycznie przetworzyć grupy czynności, skonfiguruj odpowiednie [Szablony grupy czynności](wave-templates.md) tak aby zawierały wymagane opcje automatycznego przetwarzania.

#### <a name="manually-release-a-wave"></a>Ręczne przetwarzanie grupy czynności

Aby ręcznie zwolnić grupę czynności, należy wykonać następujące czynności:

1. W zależności od typu grupy czynności do przetworzenia wykonaj jedną z następujących czynności:

      - Wybierz **Zarządzanie magazynem** \> **Wychodzące grupy czynności** \> **Grupy czynności wysyłki** \> **Wszystkie grupy czynności**. Na okienku akcji wybierz opcję **Grupa czynności**.
      - Wybierz **Zarządzanie magazynem** \> **Grupy czynności** \> **Grupy czynności wysyłki** \> **Wszystkie grupy czynności**. Na okienku akcji wybierz opcję **Grupa czynności**.
      - Wybierz **Zarządzanie magazynem** \> **Wychodzące grupy czynności** \> **Grupy czynności wysyłki** \> **Wszystkie grupy czynności**. Na okienku akcji wybierz opcję **Grupa czynności**.

1. Wybierz grupę czynności do zwolnienia. Na okienku akcji wybierz opcję **Zwolnij grupę czynności**.

## <a name="containerize-a-wave"></a>Konteneryzowanie grupy czynności

Automatyczna konteneryzacja tworzy kontenery i pracę pobrania dla wysyłki podczas przetwarzania grupy czynności. Aby uzyskać szczegółowe informacje dotyczące sposobu jej skonfigurowania, zobacz [temat ](wave-containerization.md)Konteneryzacja.

## <a name="work-with-the-scheduled-work-creation"></a>Pracuj z zaplanowanym utworzeniem pracy

Gdy jest włączona funkcja *planowania tworzenia pracy*, przetwarzanie grupy czynności utworzy planowaną pracę, która będzie ostatecznie używana przez nowy proces tworzenia pracy. Podczas tworzenia pracy praca zostanie zablokowana za pomocą funkcji *blokowania pracy w całej organizacji*. Aby uzyskać więcej informacji, zobacz temat [Planowanie tworzenia pracy podczas obsługi grupy czynności](configure-wave-schedule-work-creation.md).

Poniższy schemat blokowy pokazuje, jak planowana praca jest tworzona podczas przetwarzania grupy czynności.

![Planowanie tworzenia pracy.](media/schedule-work-creation-process.png)

### <a name="planned-work"></a>Zaplanowana praca

Strona **szczegółów planowanej pracy** (**Zarządzanie magazynem \> Praca \> Szczegóły planowanej pracy**) zawiera informacje o planowanej pracy, która jest początkowo tworzona podczas przetwarzania grupy czynności. Dostępne są następujące wartości opcji **Stan procesu**:

- **W kolejce** — planowana praca oczekuje na utworzenie pracy.
- **Zakończono** — planowana praca została użyta do utworzenia pracy.
- **Niepowodzenie** — przetwarzanie grupy czynności nie powiodło się. Należy zauważyć, że praca planowana może mieć stan **Niepowodzenie** z rzeczywistą pracą lub bez niej. Jeśli rzeczywisty proces tworzenia pracy nie powiedzie się, rzeczywista praca pozostaje w stanie *Anulowana*.

### <a name="batch-job-for-the-work-creation-process"></a>Zadanie wsadowe dla procesu tworzenia pracy

Aby wyświetlić zadania wsadowe przetwarzania grup czynności, wybierz **Zadania wsadowe** w okienku akcji na stronie **Wszystkie grupy czynności**.

W tym miejscu można wyświetlić wszystkie szczegóły zadania wsadowego dla każdego z identyfikatorów zadań wsadowych.

## <a name="cancel-a-wave"></a>Anulowanie grupy czynności

W razie potrzeby można anulować grupę czynności, która została przetworzona. Aby anulować grupę czynności i pracę pobrania, która została utworzona, należy wykonać następujące czynności:

1. W zależności od typu grupy czynności do anulownaia wykonaj jedną z następujących czynności:

      - Przejdź do **Zarządzanie magazynem** \> **Wychodzące grupy czynności** \> **Grupy czynności wysyłki** \> **Wszystkie grupy czynności**.
      - Przejdź do **Zarządzanie magazynem** \> **Grupy czynności** \> **Grupy czynności wysyłki** \> **Wszystkie grupy czynności**.
      - Przejdź do **Zarządzanie magazynem** \> **Grupy czynności** \> **Grupy czynności wysyłki** \> **Wszystkie grupy czynności**.

1. Wybierz grupę czynności do anulowania. W okienku akcji na karcie **Praca** wybierz opcję **Anuluj**.

## <a name="review-wave-batch-job-details"></a>Przegląd szczegółów zadania wsadowego grupy czynności

Strona **Szczegóły zadania wsadowego grupy czynności** zawiera informacje o sprawdzaniu zadań wsadowych i powiązanych z nimi zadań. Jest to szczególnie przydatne do rozwiązywania problemów z grupy czynności, która zakończyła się niepowodzeniem. W przypadku tej funkcji dostęp do szczegółów zadania wsadowego będzie zazwyczaj mieć wyłącznie administratorzy. Strona **Szczegółów zadania wsadowego grupy czynności** może być dostępna dla użytkowników niebędących administratorami i umożliwia wyświetlanie tylko do odczytu zadań wsadowych i powiązanych zadań.

### <a name="turn-the-wave-batch-job-details-page-on-or-off"></a>Włącz lub wyłącz stronę szczegółów zadania wsadowego Wave

Aby używać tej funkcji, należy ją włączyć dla systemu. Od wersji 10.0.25 Supply Chain Management funkcja jest domyślnie włączona. Od wersji 10.0.29 Supply Chain Management funkcja jest obowiązkowa i nie można jej wyłączyć. Jeśli używasz wersji starszej niż 10.0.29, administratorzy mogą włączyć lub wyłączyć tę funkcję, wyszukując funkcję *Szczegóły zadania wsadowego grupy czynności* w obszarze roboczym [Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

### <a name="use-the-wave-batch-job-details-page"></a>Korzystanie ze strony szczegółów zadania wsadowego grupy czynności

**Strona szczegółów zadania wsadowego grupy czynności** łączy zadania wsadowe i zadania wsadowe, co umożliwia sprawdzenie wszystkich etapów grupy czynności bez konieczności przechodzenia w obu tych etapach między jednym zadaniem wsadowym a listą zadań wsadowych. Strona umożliwia także dostęp do dziennika zadań wsadowych oraz, jeśli masz wymagane uprawnienia, łącze do strony **Zadania wsadowe**.

Aby otworzyć tę stronę, wybierz akcję grupy czynności na dowolnej z kilku różnych stron grupy czynności, a następnie wybierz **Szczegóły zadania wsadowego grupy czynności** w okienku akcji.

## <a name="review-load-validation-and-error-messages"></a>Weryfikacja i komunikaty o błędach

Podczas przetwarzania grupy czynności system sprawdza poprawność i wyświetla stan każdego wiersza ładunku w grupy czynności. Jeśli nie występują ostrzeżenia, przejdź do następnego kroku grupy czynności. Jeśli wystąpią ostrzeżenia, po zakończeniu sprawdzania poprawności całej grupy czynności wyświetlany jest następujący błąd:

> Znaleziono nieprawidłowe wiersze ładunku w grupy czynności. Usuń nieprawidłowe wiersze ładunku.

Możesz przejrzeć ostateczny stan każdego wiersza ładunku w grupy czynności i poprawić wszystkie ostrzeżenia przed podjęciem próby ponownie. Dzięki temu można zająć się wszystkimi ostrzeżeniami jednocześnie przed ponownym przetworzeniem grupy czynności. (W poprzednich wersjach system zatrzymał przetwarzanie grupy czynności po pierwszym ostrzeżeniu, więc można było poprawić tylko jedno ostrzeżenie na raz)

Sposób, w jaki system wyświetla komunikaty o stanie przetwarzania grupy czynności, zależy od sposobu ustawienia opcji **Utwórz dziennik historii przetwarzania grupy czynności** na stronie **Parametry zarządzania magazynem**.

- Jeśli w **Dzienniku historii przetwarzania grupy czynności** zostanie ustawiona wartość *Nie*, komunikaty o stanie wiersza ładunku będą wyświetlane w **Dzienniku informacyjny** m.
- Jeśli w **Dzienniku historii przetwarzania grupy czynności** zostanie ustawiona wartość *Tak*, komunikaty o stanie wiersza ładunku będą wyświetlane na stronie **Dziennika historii przetwarzania grup czynności**. Aby wyświetlić dziennik, przejdź do **Zarządzanie magazynem \> Wychodzące grupy czynności \> Dziennik historii przetwarzania grup czynności**.

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Konfigurowanie przetwarzania grupy czynności — przykład](tasks/configure-wave-processing.md)
- [Szablony grupy czynności](wave-templates.md)
- [Konteneryzacja](wave-containerization.md)