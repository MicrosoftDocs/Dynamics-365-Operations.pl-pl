---
title: Konfigurowanie integracji z usługą Common Data Service
description: Można włączyć lub wyłączyć integrację między usługą Common Data Service a Dynamics 365 Human Resources. Można również wyświetlić szczegóły synchronizacji, wyczyścić dane śledzenia i dokonać ponownej synchronizacji jednostki, aby ułatwić rozwiązywanie problemów z danymi między tymi dwoma środowiskami.
author: andreabichsel
manager: AnnBe
ms.date: 04/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: CDSIntegrationAdministration
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 7aad8217d48917d6855046a6810fe994f5564d94
ms.sourcegitcommit: ba340f836e472f13f263dec46a49847c788fca44
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/04/2020
ms.locfileid: "3431321"
---
# <a name="configure-common-data-service-integration"></a>Konfigurowanie integracji z usługą Common Data Service

Można włączyć lub wyłączyć integrację między usługą Common Data Service a Dynamics 365 Human Resources. Można również wyświetlić szczegóły synchronizacji, wyczyścić dane śledzenia i dokonać ponownej synchronizacji jednostki, aby ułatwić rozwiązywanie problemów z danymi między tymi dwoma środowiskami.

Po wyłączeniu integracji użytkownicy mogą wprowadzać zmiany w module Human Resources lub usłudze Common Data Service, ale te zmiany nie są synchronizowane między oboma środowiskami.

Domyślnie integracja danych między modułem Human Resources a usługą Common Data Service jest wyłączona.

Wyłączenie integracji może być zalecane w następujących sytuacjach:

- Wprowadzasz dane za pomocą struktury zarządzania danymi i musisz je zaimportować wielokrotnie, aby osiągnęły poprawny stan.

- Istnieją problemy z danymi w module Human Resources lub usłudze Common Data Service. Po wyłączeniu integracji można usunąć rekord w jednym środowisku bez usuwania go w drugim. Po ponownym włączeniu integracji rekord w środowisku, w którym nie został usunięty, jest zsynchronizowany do środowiska, w którym został usunięty. Synchronizacja rozpocznie się przy następnym uruchomieniu zadania wsadowego **Żądanie synchronizacji pominiętej integracji z usługą Common Data Service**.

> [!WARNING]
> Po wyłączeniu integracji danych należy się upewnić, że ten sam rekord nie będzie edytowany w obu środowiskach. Po ponownym włączeniu integracji zostanie zsynchronizowany rekord, który był ostatnio edytowany. W związku z tym jeśli nie dokonano takich samych zmian w rekordzie w obu środowiskach, może nastąpić utrata danych.

## <a name="access-the-common-data-service-integration-page"></a>Dostęp do strony integracji z usługą Common Data Service

1. W wystąpieniu modułu Human Resources, w którym chcesz wyświetlić lub skonfigurować ustawienia integracji z usługą Common Data Service, wybierz kafelek **Administrowanie systemem**.

    [![Kafelek Administrowanie systemem](./media/hr-select-system-administration.png)](./media/hr-select-system-administration.png)

2. Kliknij kartę **Łącza**.

    [![Karta Łącza](./media/hr-system-administration-links.png)](./media/hr-system-administration-links.png)

3. W obszarze **Integracje** wybierz pozycję **Konfiguracja usługi Common Data Service**.

    [![Łącze Konfiguracja usługi Common Data Service](./media/hr-select-common-data-service-configuration.png)](./media/hr-select-common-data-service-configuration.png)

## <a name="turn-data-integration-between-human-resources-and-common-data-service-on-or-off"></a>Włączenie lub wyłączanie integracji danych między modułem Human Resources a usługą Common Data Service

- Aby włączyć integrację, w opcji **Włącz integrację z usługą Common Data Service** ustaw wartość **Tak**.

    > [!NOTE]
    > Po włączeniu integracji dane zostaną zsynchronizowane przy następnym uruchomieniu zadania wsadowego **Żądanie synchronizacji pominiętej integracji z usługą Common Data Service**. Po zakończeniu zadania wsadowego wszystkie dane powinny być dostępne.

- Aby wyłączyć integrację, ustaw w opcji wartość **Nie**.

[![Włączanie lub wyłączanie integracji z usługą Common Data Service](./media/hr-enable-or-disable-common-data-service-integration.png)](./media/hr-enable-or-disable-common-data-service-integration.png)

## <a name="view-data-integration-details"></a>Wyświetlanie szczegółów integracji danych

Na stronie **Integracja z usługą Common Data Service** na skróconej karcie **Administracja** można zobaczyć, jak rekordy są z sobą połączone między modułem Human Resources a usługą Common Data Service.

- Aby wyświetlić rekordy jednostki, wybierz jednostkę w polu **Nazwa jednostki w usłudze CDS**. W siatce zostaną wyświetlone wszystkie rekordy połączone z wybraną jednostką.

[![Wyświetlanie rekordów jednostki](./media/hr-common-data-service-configuration-view-entity.png)](./media/hr-common-data-service-configuration-view-entity.png)

> [!NOTE]
> Nie wszystkie jednostki usługi Common Data Service są obecnie wyświetlane. W siatce widać tylko jednostki, które obsługują używanie pól niestandardowych. Nowe jednostki są udostępniane w kolejnych wydaniach programu Human Resources.

Siatka zawiera następujące pola:

- **Nazwa jednostki w usłudze CDS** — nazwa jednostki w usłudze Common Data Service.
- **Odwołanie do jednostki w usłudze CDS** — identyfikator wykorzystywany przez usługę Common Data Service do identyfikowania rekordu. Ta wartość jest równoważna wartości **RecId** w module Human Resources. Identyfikator można znaleźć po otwarciu jednostki usługi Common Data Service w programie Microsoft Excel.
- **Nazwa jednostki modułu Human Resources** — jednostka, której dane były ostatnio synchronizowane z usługą Common Data Service. Jednostka może mieć prefiks usługi Common Data Service lub inny prefiks.
- **Odwołanie do modułu Human Resources** – wartość **RecId** skojarzona z rekordem w module Human Resources.
- **Usunięto z usługi CDS** — wartość wskazująca, czy rekord został usunięty z usługi Common Data Service.

## <a name="remove-the-association-of-a-record-in-human-resources-from-common-data-service"></a>Usuwanie skojarzenia rekordu z usługi Common Data Service w module Human Resources

Jeśli występują problemy podczas synchronizacji danych między modułem Human Resources a usługą Common Data Service, można je rozwiązać, czyszcząc dane śledzenia i umożliwiając ponowne zsynchronizowanie tabeli śledzenia. Jeśli usuniesz skojarzenie, a następnie zmienisz lub usuniesz rekord w usłudze Common Data Service, zmiany nie zostaną zsynchronizowane z usługą Human Resources. W przypadku wprowadzenia zmian w module Human Resources zostanie utworzony nowy rekord śledzenia, a rekord danych zostanie zaktualizowany w Common Data Service.

- Aby usunąć powiązanie rekordu między modułem Human Resources a usługą Common Data Service, zaznacz jednostkę w polu **Nazwa jednostki w usłudze CDS**, a następnie wybierz opcję **Wyczyść informacje śledzenia**.

[![Czyszczenie informacji śledzenia](./media/hr-common-data-service-configuration-clear-tracking.png)](./media/hr-common-data-service-configuration-clear-tracking.png)

Aby wykonać pełną synchronizację jednostki po wyczyszczeniu danych śledzenia, skorzystaj z następnej procedury.

## <a name="sync-an-entity-between-human-resources-and-common-data-service"></a>Synchronizowanie jednostki między modułem Human Resources a usługą Common Data Service

Tę procedurę należy wykonać jeśli:

- Zmiany wprowadzone w Common Data Service zbyt wolno pojawiają się w Human Resources.

- Tabelę śledzenia należy odświeżyć po wyczyszczeniu śledzenia.

Aby uruchomić pełną synchronizację jednostki między Human Resources a Common Data Service:

1. W polu **Nazwa jednostki w usłudze CDS** wybierz firmę.

2. Wybierz opcję **Synchronizuj teraz**.

[![Wykonywanie pełnej synchronizacji](./media/hr-common-data-service-configuration-sync-now.png)](./media/hr-common-data-service-configuration-sync-now.png)


