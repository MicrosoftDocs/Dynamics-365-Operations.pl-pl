---
title: Konfigurowanie integracji z usługą Dataverse
description: Można włączyć lub wyłączyć integrację między usługą Microsoft Dataverse a Dynamics 365 Human Resources. Można również wyświetlić szczegóły synchronizacji, wyczyścić dane śledzenia i dokonać ponownej synchronizacji tabeli, aby ułatwić rozwiązywanie problemów z danymi między tymi dwoma środowiskami.
author: andreabichsel
ms.date: 01/25/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CDSIntegrationAdministration
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 721799c9a6fafe0a809f447189ce6814b30ca863
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/18/2021
ms.locfileid: "6052464"
---
# <a name="configure-dataverse-integration"></a>Konfigurowanie integracji z usługą Dataverse

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Można włączyć lub wyłączyć integrację między usługą Microsoft Dataverse a Dynamics 365 Human Resources. Można również wyświetlić szczegóły synchronizacji, wyczyścić dane śledzenia i dokonać ponownej synchronizacji tabeli, aby ułatwić rozwiązywanie problemów z danymi między tymi dwoma środowiskami.

> [!NOTE]
> Aby uzyskać więcej informacji o Dataverse (poprzednio Common Data Service) i aktualizacjach terminologii, zobacz [Co to jest Microsoft Dataverse?](/powerapps/maker/data-platform/data-platform-intro)

Po wyłączeniu integracji użytkownicy mogą wprowadzać zmiany w module Human Resources lub usłudze Dataverse, ale te zmiany nie są synchronizowane między oboma środowiskami.

Domyślnie integracja danych między modułem Human Resources a usługą Dataverse jest wyłączona.

Wyłączenie integracji może być zalecane w następujących sytuacjach:

- Wprowadzasz dane za pomocą struktury zarządzania danymi i musisz je zaimportować wielokrotnie, aby osiągnęły poprawny stan.

- Istnieją problemy z danymi w module Human Resources lub usłudze Dataverse. Po wyłączeniu integracji można usunąć rekord w jednym środowisku bez usuwania go w drugim. Po ponownym włączeniu integracji rekord w środowisku, w którym nie został usunięty, jest zsynchronizowany do środowiska, w którym został usunięty. Synchronizacja rozpocznie się przy następnym uruchomieniu zadania wsadowego **Żądanie synchronizacji pominiętej integracji z usługą Dataverse**.

> [!WARNING]
> Po wyłączeniu integracji danych należy się upewnić, że ten sam rekord nie będzie edytowany w obu środowiskach. Po ponownym włączeniu integracji zostanie zsynchronizowany rekord, który był ostatnio edytowany. W związku z tym jeśli nie dokonano takich samych zmian w rekordzie w obu środowiskach, może nastąpić utrata danych.

## <a name="access-the-dataverse-integration-page"></a>Dostęp do strony integracji z usługą Dataverse

1. W wystąpieniu modułu Human Resources, w którym chcesz wyświetlić lub skonfigurować ustawienia integracji z usługą Dataverse, wybierz kafelek **Administrowanie systemem**.

    [![Kafelek Administrowanie systemem](./media/hr-select-system-administration.png)](./media/hr-select-system-administration.png)

2. Kliknij kartę **Łącza**.

    [![Karta Łącza](./media/hr-system-administration-links.png)](./media/hr-system-administration-links.png)

3. W obszarze **Integracje** wybierz pozycję **Konfiguracja usługi Dataverse**.

    [![Łącze Konfiguracja usługi Dataverse](./media/hr-admin-integration-dataverse-select.png)](./media/hr-admin-integration-dataverse-select.png)

## <a name="turn-data-integration-between-human-resources-and-dataverse-on-or-off"></a>Włączenie lub wyłączanie integracji danych między modułem Human Resources a usługą Dataverse

- Aby włączyć integrację, w opcji **Włącz integrację z usługą Dataverse** ustaw wartość **Tak** na stronie **integracja Microsoft Dataverse**.

    > [!NOTE]
    > Po włączeniu integracji dane zostaną zsynchronizowane przy następnym uruchomieniu zadania wsadowego **Żądanie synchronizacji pominiętej integracji z usługą Dataverse**. Po zakończeniu zadania wsadowego wszystkie dane powinny być dostępne.

- Aby wyłączyć integrację, ustaw w opcji wartość **Nie**.

[![Włączanie lub wyłączanie integracji z usługą Dataverse](./media/hr-admin-integration-dataverse-enable-disable.png)](./media/hr-admin-integration-dataverse-enable-disable.png)

> [!WARNING]
> Stanowczo zaleca się wyłączenie integracji Dataverse podczas wykonywania zadań migracji danych. Duże operacje przekazywania danych mogą znacząco wpłynąć na wydajność. Na przykład przekazywanie 2000 pracowników może potrwać kilka godzin, gdy integracja jest włączona, i mniej niż jedna godzina, gdy jest wyłączona. Numery podane w tym przykładzie służą tylko do celów demonstracyjnych. Dokładna ilość czasu importowania rekordów może się znacznie różnić w zależności od wielu czynników.

## <a name="view-data-integration-details"></a>Wyświetlanie szczegółów integracji danych

Na stronie **Integracja z usługą Microsoft Dataverse** na skróconej karcie **Administracja** można zobaczyć, jak wiersze są z sobą połączone między modułem Human Resources a usługą Dataverse.

- Aby wyświetlić wiersze dla tabeli, wybierz tabelę w polu **tabeli Dataverse**. W siatce zostaną wyświetlone wszystkie wiersze połączone z wybraną tabelę.

> [!NOTE]
> Nie wszystkie tabele usługi Dataverse są obecnie wyświetlane. W siatce widać tylko tabele, które obsługują używanie pól niestandardowych. Nowe tabele są udostępniane w kolejnych wydaniach programu Human Resources.

Siatka zawiera następujące pola:

- **Tabele Dataverse** – Nazwa tabeli przemieszczania w Dataverse.
- **Odwołanie do tabeli Dataverse** — identyfikator wykorzystywany przez usługę Dataverse do identyfikowania rekordu. Ta wartość jest równoważna wartości **RecId** w module Human Resources. Identyfikator można znaleźć po otwarciu tabeli usługi Dataverse w programie Microsoft Excel.
- **Nazwa jednostki modułu Human Resources** — jednostka Human Resources, której dane były ostatnio synchronizowane z usługą Dataverse. Jednostka może mieć prefiks usługi Dataverse lub inny prefiks.
- **Odwołanie do modułu Human Resources** – wartość **RecId** skojarzona z rekordem w module Human Resources.
- **Usunięto z usługi Dataverse** — wartość wskazująca, czy wiersz został usunięty z usługi Dataverse.

> [!NOTE]
> Rekordy w Human Resources odpowiadają wierszom w Dataverse.

## <a name="remove-the-association-of-a-human-resources-record-from-a-dataverse-row"></a>Usuwanie skojarzenia rekordu Human Resources z wiersza usługi Dataverse

Jeśli występują problemy podczas synchronizacji danych między modułem Human Resources a usługą Dataverse, można je rozwiązać, czyszcząc dane śledzenia i umożliwiając ponowne zsynchronizowanie tabeli śledzenia. Jeśli usuniesz skojarzenie, a następnie zmienisz lub usuniesz wiersz w usłudze Dataverse, zmiany nie zostaną zsynchronizowane z usługą Human Resources. W przypadku wprowadzenia zmian w module Human Resources zostanie utworzony nowy rekord śledzenia, a wiersz danych zostanie zaktualizowany w Dataverse.

- Aby usunąć powiązanie rekordu między rekordem Human Resources a wierszem Dataverse, zaznacz tabelę w polu **Tabela Dataverse**, a następnie wybierz opcję **Wyczyść informacje śledzenia**.

[![Czyszczenie informacji śledzenia](./media/hr-admin-integration-dataverse-clear-tracking.png)](./media/hr-admin-integration-dataverse-clear-tracking.png)

Aby wykonać pełną synchronizację tabeli po wyczyszczeniu danych śledzenia, skorzystaj z następnej procedury.

## <a name="sync-a-table-between-human-resources-and-dataverse"></a>Synchronizowanie tabeli między modułem Human Resources a usługą Dataverse

Tę procedurę należy wykonać jeśli:

- Zmiany wprowadzone w Dataverse zbyt wolno pojawiają się w Human Resources.

- Tabelę śledzenia należy odświeżyć po wyczyszczeniu śledzenia.

Aby uruchomić pełną synchronizację tabeli między Human Resources a Dataverse:

1. Wybierz tabelę w polu **tabela Dataverse**.

2. Wybierz opcję **Synchronizuj teraz**.

[![Wykonywanie pełnej synchronizacji](./media/hr-admin-integration-dataverse-sync-now.png)](./media/hr-admin-integration-dataverse-sync-now.png)

## <a name="see-also"></a>Informacje dodatkowe

[Tabele Dataverse](hr-developer-entities.md)<br>
[Konfiguruj tabele wirtualne usługi Dataverse](hr-admin-integration-common-data-service-virtual-entities.md)<br>
[Często zadawanych pytań dotyczące tabel wirtualnych dla Human Resources](hr-admin-virtual-entity-faq.md)<br>
[Co to jest usługa Microsoft Dataverse?](/powerapps/maker/data-platform/data-platform-intro)<br>
[Aktualizacje terminologii](/powerapps/maker/data-platform/data-platform-intro#terminology-updates)


[!INCLUDE[footer-include](../includes/footer-banner.md)]