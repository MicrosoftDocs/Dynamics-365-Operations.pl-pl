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
# <a name="configure-common-data-service-integration"></a><span data-ttu-id="b1965-104">Konfigurowanie integracji z usługą Common Data Service</span><span class="sxs-lookup"><span data-stu-id="b1965-104">Configure Common Data Service integration</span></span>

<span data-ttu-id="b1965-105">Można włączyć lub wyłączyć integrację między usługą Common Data Service a Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="b1965-105">You can turn integration between Common Data Service and Dynamics 365 Human Resources on or off.</span></span> <span data-ttu-id="b1965-106">Można również wyświetlić szczegóły synchronizacji, wyczyścić dane śledzenia i dokonać ponownej synchronizacji jednostki, aby ułatwić rozwiązywanie problemów z danymi między tymi dwoma środowiskami.</span><span class="sxs-lookup"><span data-stu-id="b1965-106">You can also view the synchronization details, clear tracking data, and resync an entity to help troubleshoot data issues between the two environments.</span></span>

<span data-ttu-id="b1965-107">Po wyłączeniu integracji użytkownicy mogą wprowadzać zmiany w module Human Resources lub usłudze Common Data Service, ale te zmiany nie są synchronizowane między oboma środowiskami.</span><span class="sxs-lookup"><span data-stu-id="b1965-107">When you turn off integration, users can make changes in Human Resources or Common Data Service, but those changes aren't synced between the two environments.</span></span>

<span data-ttu-id="b1965-108">Domyślnie integracja danych między modułem Human Resources a usługą Common Data Service jest wyłączona.</span><span class="sxs-lookup"><span data-stu-id="b1965-108">By default, integration between Human Resources and Common Data Service is turned off.</span></span>

<span data-ttu-id="b1965-109">Wyłączenie integracji może być zalecane w następujących sytuacjach:</span><span class="sxs-lookup"><span data-stu-id="b1965-109">You might want to turn off integration in these situations:</span></span>

- <span data-ttu-id="b1965-110">Wprowadzasz dane za pomocą struktury zarządzania danymi i musisz je zaimportować wielokrotnie, aby osiągnęły poprawny stan.</span><span class="sxs-lookup"><span data-stu-id="b1965-110">You're filling in data through the Data Management Framework and must import the data multiple times to get it into a correct state.</span></span>

- <span data-ttu-id="b1965-111">Istnieją problemy z danymi w module Human Resources lub usłudze Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="b1965-111">There are issues with data in either Human Resources or Common Data Service.</span></span> <span data-ttu-id="b1965-112">Po wyłączeniu integracji można usunąć rekord w jednym środowisku bez usuwania go w drugim.</span><span class="sxs-lookup"><span data-stu-id="b1965-112">If you turn off integration, you can delete a record in one environment without deleting it in the other.</span></span> <span data-ttu-id="b1965-113">Po ponownym włączeniu integracji rekord w środowisku, w którym nie został usunięty, jest zsynchronizowany do środowiska, w którym został usunięty.</span><span class="sxs-lookup"><span data-stu-id="b1965-113">When you turn integration back on, the record in the environment where it wasn't deleted sync to the environment where it was deleted.</span></span> <span data-ttu-id="b1965-114">Synchronizacja rozpocznie się przy następnym uruchomieniu zadania wsadowego **Żądanie synchronizacji pominiętej integracji z usługą Common Data Service**.</span><span class="sxs-lookup"><span data-stu-id="b1965-114">Synchronization begins the next time the **Common Data Service integration missed request sync** batch job runs.</span></span>

> [!WARNING]
> <span data-ttu-id="b1965-115">Po wyłączeniu integracji danych należy się upewnić, że ten sam rekord nie będzie edytowany w obu środowiskach.</span><span class="sxs-lookup"><span data-stu-id="b1965-115">When you turn off data integration, make sure that you don't edit the same record in both environments.</span></span> <span data-ttu-id="b1965-116">Po ponownym włączeniu integracji zostanie zsynchronizowany rekord, który był ostatnio edytowany.</span><span class="sxs-lookup"><span data-stu-id="b1965-116">When you turn integration back on, the record that you last edited will be synced.</span></span> <span data-ttu-id="b1965-117">W związku z tym jeśli nie dokonano takich samych zmian w rekordzie w obu środowiskach, może nastąpić utrata danych.</span><span class="sxs-lookup"><span data-stu-id="b1965-117">Therefore, if you didn't make the same changes to the record in both environments, data loss can occur.</span></span>

## <a name="access-the-common-data-service-integration-page"></a><span data-ttu-id="b1965-118">Dostęp do strony integracji z usługą Common Data Service</span><span class="sxs-lookup"><span data-stu-id="b1965-118">Access the Common Data Service integration page</span></span>

1. <span data-ttu-id="b1965-119">W wystąpieniu modułu Human Resources, w którym chcesz wyświetlić lub skonfigurować ustawienia integracji z usługą Common Data Service, wybierz kafelek **Administrowanie systemem**.</span><span class="sxs-lookup"><span data-stu-id="b1965-119">In the Human Resources instance where you want to view or configure settings for the integration with Common Data Service, select the **System administration** tile.</span></span>

    <span data-ttu-id="b1965-120">[![Kafelek Administrowanie systemem](./media/hr-select-system-administration.png)](./media/hr-select-system-administration.png)</span><span class="sxs-lookup"><span data-stu-id="b1965-120">[![System administration tile](./media/hr-select-system-administration.png)](./media/hr-select-system-administration.png)</span></span>

2. <span data-ttu-id="b1965-121">Kliknij kartę **Łącza**.</span><span class="sxs-lookup"><span data-stu-id="b1965-121">Select the **Links** tab.</span></span>

    <span data-ttu-id="b1965-122">[![Karta Łącza](./media/hr-system-administration-links.png)](./media/hr-system-administration-links.png)</span><span class="sxs-lookup"><span data-stu-id="b1965-122">[![Links tab](./media/hr-system-administration-links.png)](./media/hr-system-administration-links.png)</span></span>

3. <span data-ttu-id="b1965-123">W obszarze **Integracje** wybierz pozycję **Konfiguracja usługi Common Data Service**.</span><span class="sxs-lookup"><span data-stu-id="b1965-123">Under **Integrations**, select **Common Data Service configuration**.</span></span>

    <span data-ttu-id="b1965-124">[![Łącze Konfiguracja usługi Common Data Service](./media/hr-select-common-data-service-configuration.png)](./media/hr-select-common-data-service-configuration.png)</span><span class="sxs-lookup"><span data-stu-id="b1965-124">[![Common Data Service configuration link](./media/hr-select-common-data-service-configuration.png)](./media/hr-select-common-data-service-configuration.png)</span></span>

## <a name="turn-data-integration-between-human-resources-and-common-data-service-on-or-off"></a><span data-ttu-id="b1965-125">Włączenie lub wyłączanie integracji danych między modułem Human Resources a usługą Common Data Service</span><span class="sxs-lookup"><span data-stu-id="b1965-125">Turn data integration between Human Resources and Common Data Service on or off</span></span>

- <span data-ttu-id="b1965-126">Aby włączyć integrację, w opcji **Włącz integrację z usługą Common Data Service** ustaw wartość **Tak**.</span><span class="sxs-lookup"><span data-stu-id="b1965-126">To turn on integration, set the **Enable the integration to the Common Data Service** option to **Yes**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b1965-127">Po włączeniu integracji dane zostaną zsynchronizowane przy następnym uruchomieniu zadania wsadowego **Żądanie synchronizacji pominiętej integracji z usługą Common Data Service**.</span><span class="sxs-lookup"><span data-stu-id="b1965-127">When you turn on integration, data will be synced the next time that the **Common Data Service integration missed request sync** batch job runs.</span></span> <span data-ttu-id="b1965-128">Po zakończeniu zadania wsadowego wszystkie dane powinny być dostępne.</span><span class="sxs-lookup"><span data-stu-id="b1965-128">All data should be available after the batch job is completed.</span></span>

- <span data-ttu-id="b1965-129">Aby wyłączyć integrację, ustaw w opcji wartość **Nie**.</span><span class="sxs-lookup"><span data-stu-id="b1965-129">To turn off integration, set the option to **No**.</span></span>

<span data-ttu-id="b1965-130">[![Włączanie lub wyłączanie integracji z usługą Common Data Service](./media/hr-enable-or-disable-common-data-service-integration.png)](./media/hr-enable-or-disable-common-data-service-integration.png)</span><span class="sxs-lookup"><span data-stu-id="b1965-130">[![Turning the Common Data Service integration on or off](./media/hr-enable-or-disable-common-data-service-integration.png)](./media/hr-enable-or-disable-common-data-service-integration.png)</span></span>

## <a name="view-data-integration-details"></a><span data-ttu-id="b1965-131">Wyświetlanie szczegółów integracji danych</span><span class="sxs-lookup"><span data-stu-id="b1965-131">View data integration details</span></span>

<span data-ttu-id="b1965-132">Na stronie **Integracja z usługą Common Data Service** na skróconej karcie **Administracja** można zobaczyć, jak rekordy są z sobą połączone między modułem Human Resources a usługą Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="b1965-132">On the **Administration** FastTab of the **Common Data Service integration** page, you can see how records are linked together between Human Resources and Common Data Service.</span></span>

- <span data-ttu-id="b1965-133">Aby wyświetlić rekordy jednostki, wybierz jednostkę w polu **Nazwa jednostki w usłudze CDS**.</span><span class="sxs-lookup"><span data-stu-id="b1965-133">To view the records for an entity, select the entity in the **CDS entity name** field.</span></span> <span data-ttu-id="b1965-134">W siatce zostaną wyświetlone wszystkie rekordy połączone z wybraną jednostką.</span><span class="sxs-lookup"><span data-stu-id="b1965-134">The grid shows all the records that are linked to the selected entity.</span></span>

<span data-ttu-id="b1965-135">[![Wyświetlanie rekordów jednostki](./media/hr-common-data-service-configuration-view-entity.png)](./media/hr-common-data-service-configuration-view-entity.png)</span><span class="sxs-lookup"><span data-stu-id="b1965-135">[![Viewing the records for an entity](./media/hr-common-data-service-configuration-view-entity.png)](./media/hr-common-data-service-configuration-view-entity.png)</span></span>

> [!NOTE]
> <span data-ttu-id="b1965-136">Nie wszystkie jednostki usługi Common Data Service są obecnie wyświetlane.</span><span class="sxs-lookup"><span data-stu-id="b1965-136">Not all Common Data Service entities are currently listed.</span></span> <span data-ttu-id="b1965-137">W siatce widać tylko jednostki, które obsługują używanie pól niestandardowych.</span><span class="sxs-lookup"><span data-stu-id="b1965-137">Only entities that support the use of custom fields appear in the grid.</span></span> <span data-ttu-id="b1965-138">Nowe jednostki są udostępniane w kolejnych wydaniach programu Human Resources.</span><span class="sxs-lookup"><span data-stu-id="b1965-138">New entities become available through continuous releases of Human Resources.</span></span>

<span data-ttu-id="b1965-139">Siatka zawiera następujące pola:</span><span class="sxs-lookup"><span data-stu-id="b1965-139">The grid includes the following fields:</span></span>

- <span data-ttu-id="b1965-140">**Nazwa jednostki w usłudze CDS** — nazwa jednostki w usłudze Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="b1965-140">**CDS entity name** – The name of the entity in Common Data Service.</span></span>
- <span data-ttu-id="b1965-141">**Odwołanie do jednostki w usłudze CDS** — identyfikator wykorzystywany przez usługę Common Data Service do identyfikowania rekordu.</span><span class="sxs-lookup"><span data-stu-id="b1965-141">**CDS entity reference** – The identifier that Common Data Service uses to identify a record.</span></span> <span data-ttu-id="b1965-142">Ta wartość jest równoważna wartości **RecId** w module Human Resources.</span><span class="sxs-lookup"><span data-stu-id="b1965-142">This value is equivalent to a Human Resources **RecId** value.</span></span> <span data-ttu-id="b1965-143">Identyfikator można znaleźć po otwarciu jednostki usługi Common Data Service w programie Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="b1965-143">You can find the identifier when you open the Common Data Service entity in Microsoft Excel.</span></span>
- <span data-ttu-id="b1965-144">**Nazwa jednostki modułu Human Resources** — jednostka, której dane były ostatnio synchronizowane z usługą Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="b1965-144">**Human Resources entity name** – The entity that last synced data to Common Data Service.</span></span> <span data-ttu-id="b1965-145">Jednostka może mieć prefiks usługi Common Data Service lub inny prefiks.</span><span class="sxs-lookup"><span data-stu-id="b1965-145">The entity can have either the Common Data Service prefix or another prefix.</span></span>
- <span data-ttu-id="b1965-146">**Odwołanie do modułu Human Resources** – wartość **RecId** skojarzona z rekordem w module Human Resources.</span><span class="sxs-lookup"><span data-stu-id="b1965-146">**Human Resources reference** – The **RecId** value that is associated with the record in Human Resources.</span></span>
- <span data-ttu-id="b1965-147">**Usunięto z usługi CDS** — wartość wskazująca, czy rekord został usunięty z usługi Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="b1965-147">**Was deleted from CDS** – A value that indicates whether the record was deleted from Common Data Service.</span></span>

## <a name="remove-the-association-of-a-record-in-human-resources-from-common-data-service"></a><span data-ttu-id="b1965-148">Usuwanie skojarzenia rekordu z usługi Common Data Service w module Human Resources</span><span class="sxs-lookup"><span data-stu-id="b1965-148">Remove the association of a record in Human Resources from Common Data Service</span></span>

<span data-ttu-id="b1965-149">Jeśli występują problemy podczas synchronizacji danych między modułem Human Resources a usługą Common Data Service, można je rozwiązać, czyszcząc dane śledzenia i umożliwiając ponowne zsynchronizowanie tabeli śledzenia.</span><span class="sxs-lookup"><span data-stu-id="b1965-149">If you experience issues during data synchronization between Human Resources and Common Data Service, you might be able to resolve them by clearing the tracking and letting the tracking table be resynced.</span></span> <span data-ttu-id="b1965-150">Jeśli usuniesz skojarzenie, a następnie zmienisz lub usuniesz rekord w usłudze Common Data Service, zmiany nie zostaną zsynchronizowane z usługą Human Resources.</span><span class="sxs-lookup"><span data-stu-id="b1965-150">If you remove the association, and then change or delete a record in Common Data Service, the changes won't be synced to Human Resources.</span></span> <span data-ttu-id="b1965-151">W przypadku wprowadzenia zmian w module Human Resources zostanie utworzony nowy rekord śledzenia, a rekord danych zostanie zaktualizowany w Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="b1965-151">If you make changes in Human Resources, a new tracking record is created, and the record is updated in Common Data Service.</span></span>

- <span data-ttu-id="b1965-152">Aby usunąć powiązanie rekordu między modułem Human Resources a usługą Common Data Service, zaznacz jednostkę w polu **Nazwa jednostki w usłudze CDS**, a następnie wybierz opcję **Wyczyść informacje śledzenia**.</span><span class="sxs-lookup"><span data-stu-id="b1965-152">To remove the association of a record between Human Resources and Common Data Service, select the entity in the **CDS entity name** field, and then select **Clear tracking information**.</span></span>

<span data-ttu-id="b1965-153">[![Czyszczenie informacji śledzenia](./media/hr-common-data-service-configuration-clear-tracking.png)](./media/hr-common-data-service-configuration-clear-tracking.png)</span><span class="sxs-lookup"><span data-stu-id="b1965-153">[![Clearing tracking information](./media/hr-common-data-service-configuration-clear-tracking.png)](./media/hr-common-data-service-configuration-clear-tracking.png)</span></span>

<span data-ttu-id="b1965-154">Aby wykonać pełną synchronizację jednostki po wyczyszczeniu danych śledzenia, skorzystaj z następnej procedury.</span><span class="sxs-lookup"><span data-stu-id="b1965-154">To run a full synchronization on the entity after you clear the tracking, see the next procedure.</span></span>

## <a name="sync-an-entity-between-human-resources-and-common-data-service"></a><span data-ttu-id="b1965-155">Synchronizowanie jednostki między modułem Human Resources a usługą Common Data Service</span><span class="sxs-lookup"><span data-stu-id="b1965-155">Sync an entity between Human Resources and Common Data Service</span></span>

<span data-ttu-id="b1965-156">Tę procedurę należy wykonać jeśli:</span><span class="sxs-lookup"><span data-stu-id="b1965-156">Use this procedure when:</span></span>

- <span data-ttu-id="b1965-157">Zmiany wprowadzone w Common Data Service zbyt wolno pojawiają się w Human Resources.</span><span class="sxs-lookup"><span data-stu-id="b1965-157">Changes from Common Data Service take too long to appear in Human Resources.</span></span>

- <span data-ttu-id="b1965-158">Tabelę śledzenia należy odświeżyć po wyczyszczeniu śledzenia.</span><span class="sxs-lookup"><span data-stu-id="b1965-158">You must refresh the tracking table after clearing the tracking.</span></span>

<span data-ttu-id="b1965-159">Aby uruchomić pełną synchronizację jednostki między Human Resources a Common Data Service:</span><span class="sxs-lookup"><span data-stu-id="b1965-159">To run a full synchronization on an entity between Human Resources and Common Data Service:</span></span>

1. <span data-ttu-id="b1965-160">W polu **Nazwa jednostki w usłudze CDS** wybierz firmę.</span><span class="sxs-lookup"><span data-stu-id="b1965-160">Select the entity in the **CDS entity name** field.</span></span>

2. <span data-ttu-id="b1965-161">Wybierz opcję **Synchronizuj teraz**.</span><span class="sxs-lookup"><span data-stu-id="b1965-161">Select **Sync now**.</span></span>

<span data-ttu-id="b1965-162">[![Wykonywanie pełnej synchronizacji](./media/hr-common-data-service-configuration-sync-now.png)](./media/hr-common-data-service-configuration-sync-now.png)</span><span class="sxs-lookup"><span data-stu-id="b1965-162">[![Running a full synchronization](./media/hr-common-data-service-configuration-sync-now.png)](./media/hr-common-data-service-configuration-sync-now.png)</span></span>


