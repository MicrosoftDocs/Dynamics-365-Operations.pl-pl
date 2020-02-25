---
title: Konfiguruj integrację z programem Common Data Service
description: Można włączyć lub wyłączyć integrację między usługą Common Data Service a wystąpieniem rozwiązania Microsoft Dynamics 365 Human Resources. Można również wyświetlić szczegóły synchronizacji, wyczyścić dane śledzenia i dokonać ponownej synchronizacji jednostki, aby ułatwić rozwiązywanie problemów z danymi między tymi dwoma środowiskami.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 042daf3fdf7a906086af726472da050467d217e3
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/03/2020
ms.locfileid: "3010176"
---
# <a name="configure-common-data-service-integration"></a><span data-ttu-id="7e1da-104">Konfiguruj integrację z programem Common Data Service</span><span class="sxs-lookup"><span data-stu-id="7e1da-104">Configure Common Data Service integration</span></span>

<span data-ttu-id="7e1da-105">Można włączyć lub wyłączyć integrację między usługą Common Data Service a wystąpieniem rozwiązania Microsoft Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="7e1da-105">You can turn integration between Common Data Service and an instance of Microsoft Dynamics 365 Human Resources on or off.</span></span> <span data-ttu-id="7e1da-106">Można również wyświetlić szczegóły synchronizacji, wyczyścić dane śledzenia i dokonać ponownej synchronizacji jednostki, aby ułatwić rozwiązywanie problemów z danymi między tymi dwoma środowiskami.</span><span class="sxs-lookup"><span data-stu-id="7e1da-106">You can also view the synchronization details, clear tracking data, and resync an entity to help troubleshoot data issues between the two environments.</span></span>

<span data-ttu-id="7e1da-107">Po wyłączeniu integracji użytkownicy mogą wprowadzać zmiany w module Human Resources lub usłudze Common Data Service, ale te zmiany nie są synchronizowane między oboma środowiskami.</span><span class="sxs-lookup"><span data-stu-id="7e1da-107">When you turn off integration, users can make changes in Human Resources or Common Data Service, but those changes aren't synced between the two environments.</span></span>

<span data-ttu-id="7e1da-108">Domyślnie integracja między modułem Human Resources i usługą Common Data Service jest wyłączona lub włączona, w zależności od obecności danych demonstracyjnych w środowiskach:</span><span class="sxs-lookup"><span data-stu-id="7e1da-108">By default, integration between Human Resources and Common Data Service is turned either off or on, depending on the presence of demo data in the environments:</span></span>

- <span data-ttu-id="7e1da-109">**Wyłączona** dla nowych środowisk, które nie zawierają danych demonstracyjnych</span><span class="sxs-lookup"><span data-stu-id="7e1da-109">**Off** for new environments that don't include demo data</span></span>
- <span data-ttu-id="7e1da-110">**Włączona** dla nowych środowisk, które zawierają dane demonstracyjne</span><span class="sxs-lookup"><span data-stu-id="7e1da-110">**On** for new environments that include demo data</span></span>

<span data-ttu-id="7e1da-111">Nowe środowiska zawierające dane demonstracyjne rozpoczną synchronizowanie danych, gdy tylko zostaną zainicjowane.</span><span class="sxs-lookup"><span data-stu-id="7e1da-111">New environments that include demo data will start to sync data when they are provisioned.</span></span>

<span data-ttu-id="7e1da-112">Wyłączenie integracji może być zalecane w następujących sytuacjach:</span><span class="sxs-lookup"><span data-stu-id="7e1da-112">You might want to turn off integration in these situations:</span></span>

- <span data-ttu-id="7e1da-113">Wprowadzasz dane za pomocą struktury zarządzania danymi i musisz je zaimportować wielokrotnie, aby osiągnęły poprawny stan.</span><span class="sxs-lookup"><span data-stu-id="7e1da-113">You're filling in data through the Data Management Framework and must import the data multiple times to get it into a correct state.</span></span>

- <span data-ttu-id="7e1da-114">Istnieją problemy z danymi w module Human Resources lub usłudze Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="7e1da-114">There are issues with data in either Human Resources or Common Data Service.</span></span> <span data-ttu-id="7e1da-115">Po wyłączeniu integracji można usunąć rekord w jednym środowisku bez usuwania go w drugim.</span><span class="sxs-lookup"><span data-stu-id="7e1da-115">If you turn off integration, you can delete a record in one environment without deleting it in the other.</span></span> <span data-ttu-id="7e1da-116">Po ponownym włączeniu integracji rekord w środowisku, w którym nie został usunięty, zostanie zsynchronizowany z powrotem do środowiska, w którym został usunięty.</span><span class="sxs-lookup"><span data-stu-id="7e1da-116">When you turn integration back on, the record in the environment where it wasn't deleted will be synced back to the environment where it was deleted.</span></span> <span data-ttu-id="7e1da-117">Synchronizacja rozpocznie się przy następnym uruchomieniu zadania wsadowego **Żądanie synchronizacji pominiętej integracji z usługą Common Data Service**.</span><span class="sxs-lookup"><span data-stu-id="7e1da-117">Synchronization begins the next time the **Common Data Service integration missed request sync** batch job runs.</span></span>

> [!WARNING]
> <span data-ttu-id="7e1da-118">Po wyłączeniu integracji danych należy się upewnić, że ten sam rekord nie będzie edytowany w obu środowiskach.</span><span class="sxs-lookup"><span data-stu-id="7e1da-118">When you turn off data integration, make sure that you don't edit the same record in both environments.</span></span> <span data-ttu-id="7e1da-119">Po ponownym włączeniu integracji zostanie zsynchronizowany rekord, który był ostatnio edytowany.</span><span class="sxs-lookup"><span data-stu-id="7e1da-119">When you turn integration back on, the record that you last edited will be synced.</span></span> <span data-ttu-id="7e1da-120">W związku z tym jeśli nie dokonano takich samych zmian w rekordzie w obu środowiskach, może nastąpić utrata danych.</span><span class="sxs-lookup"><span data-stu-id="7e1da-120">Therefore, if you didn't make the same changes to the record in both environments, data loss can occur.</span></span>

## <a name="access-the-common-data-service-integration-page"></a><span data-ttu-id="7e1da-121">Dostęp do strony integracji z usługą Common Data Service</span><span class="sxs-lookup"><span data-stu-id="7e1da-121">Access the Common Data Service integration page</span></span>

1. <span data-ttu-id="7e1da-122">W wystąpieniu modułu Human Resources, w którym chcesz wyświetlić lub skonfigurować ustawienia integracji z usługą Common Data Service, wybierz kafelek **Administrowanie systemem**.</span><span class="sxs-lookup"><span data-stu-id="7e1da-122">In the Human Resources instance where you want to view or configure settings for the integration with Common Data Service, select the **System administration** tile.</span></span>

    <span data-ttu-id="7e1da-123">[![Kafelek Administrowanie systemem](./media/hr-select-system-administration.png)](./media/hr-select-system-administration.png)</span><span class="sxs-lookup"><span data-stu-id="7e1da-123">[![System administration tile](./media/hr-select-system-administration.png)](./media/hr-select-system-administration.png)</span></span>

2. <span data-ttu-id="7e1da-124">Kliknij kartę **Łącza**.</span><span class="sxs-lookup"><span data-stu-id="7e1da-124">Select the **Links** tab.</span></span>

    <span data-ttu-id="7e1da-125">[![Karta Łącza](./media/hr-system-administration-links.png)](./media/hr-system-administration-links.png)</span><span class="sxs-lookup"><span data-stu-id="7e1da-125">[![Links tab](./media/hr-system-administration-links.png)](./media/hr-system-administration-links.png)</span></span>

3. <span data-ttu-id="7e1da-126">W obszarze **Integracje** wybierz pozycję **Konfiguracja usługi Common Data Service**.</span><span class="sxs-lookup"><span data-stu-id="7e1da-126">Under **Integrations**, select **Common Data Service configuration**.</span></span>

    <span data-ttu-id="7e1da-127">[![Łącze Konfiguracja usługi Common Data Service](./media/hr-select-common-data-service-configuration.png)](./media/hr-select-common-data-service-configuration.png)</span><span class="sxs-lookup"><span data-stu-id="7e1da-127">[![Common Data Service configuration link](./media/hr-select-common-data-service-configuration.png)](./media/hr-select-common-data-service-configuration.png)</span></span>

## <a name="turn-data-integration-between-human-resources-and-common-data-service-on-or-off"></a><span data-ttu-id="7e1da-128">Włączenie lub wyłączanie integracji danych między modułem Human Resources a usługą Common Data Service</span><span class="sxs-lookup"><span data-stu-id="7e1da-128">Turn data integration between Human Resources and Common Data Service on or off</span></span>

- <span data-ttu-id="7e1da-129">Aby włączyć integrację, w opcji **Włącz integrację z usługą Common Data Service** ustaw wartość **Tak**.</span><span class="sxs-lookup"><span data-stu-id="7e1da-129">To turn on integration, set the **Enable the integration to the Common Data Service** option to **Yes**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="7e1da-130">Po włączeniu integracji dane zostaną zsynchronizowane przy następnym uruchomieniu zadania wsadowego **Żądanie synchronizacji pominiętej integracji z usługą Common Data Service**.</span><span class="sxs-lookup"><span data-stu-id="7e1da-130">When you turn on integration, data will be synced the next time that the **Common Data Service integration missed request sync** batch job runs.</span></span> <span data-ttu-id="7e1da-131">Po zakończeniu zadania wsadowego wszystkie dane powinny być dostępne.</span><span class="sxs-lookup"><span data-stu-id="7e1da-131">All data should be available after the batch job is completed.</span></span>

- <span data-ttu-id="7e1da-132">Aby wyłączyć integrację, ustaw w opcji wartość **Nie**.</span><span class="sxs-lookup"><span data-stu-id="7e1da-132">To turn off integration, set the option to **No**.</span></span>

<span data-ttu-id="7e1da-133">[![Włączanie lub wyłączanie integracji z usługą Common Data Service](./media/hr-enable-or-disable-common-data-service-integration.png)](./media/hr-enable-or-disable-common-data-service-integration.png)</span><span class="sxs-lookup"><span data-stu-id="7e1da-133">[![Turning the Common Data Service integration on or off](./media/hr-enable-or-disable-common-data-service-integration.png)](./media/hr-enable-or-disable-common-data-service-integration.png)</span></span>

## <a name="view-data-integration-details"></a><span data-ttu-id="7e1da-134">Wyświetlanie szczegółów integracji danych</span><span class="sxs-lookup"><span data-stu-id="7e1da-134">View data integration details</span></span>

<span data-ttu-id="7e1da-135">Na stronie **Integracja z usługą Common Data Service** na skróconej karcie **Administracja** można zobaczyć, jak rekordy są z sobą połączone między modułem Human Resources a usługą Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="7e1da-135">On the **Administration** FastTab of the **Common Data Service integration** page, you can see how records are linked together between Human Resources and Common Data Service.</span></span>

- <span data-ttu-id="7e1da-136">Aby wyświetlić rekordy jednostki, wybierz jednostkę w polu **Nazwa jednostki w usłudze CDS**.</span><span class="sxs-lookup"><span data-stu-id="7e1da-136">To view the records for an entity, select the entity in the **CDS entity name** field.</span></span> <span data-ttu-id="7e1da-137">W siatce zostaną wyświetlone wszystkie rekordy połączone z wybraną jednostką.</span><span class="sxs-lookup"><span data-stu-id="7e1da-137">The grid shows all the records that are linked to the selected entity.</span></span>

<span data-ttu-id="7e1da-138">[![Wyświetlanie rekordów jednostki](./media/hr-common-data-service-configuration-view-entity.png)](./media/hr-common-data-service-configuration-view-entity.png)</span><span class="sxs-lookup"><span data-stu-id="7e1da-138">[![Viewing the records for an entity](./media/hr-common-data-service-configuration-view-entity.png)](./media/hr-common-data-service-configuration-view-entity.png)</span></span>

> [!NOTE]
> <span data-ttu-id="7e1da-139">Nie wszystkie jednostki usługi Common Data Service są obecnie wyświetlane.</span><span class="sxs-lookup"><span data-stu-id="7e1da-139">Not all Common Data Service entities are currently listed.</span></span> <span data-ttu-id="7e1da-140">W siatce widać tylko jednostki, które obsługują używanie pól niestandardowych.</span><span class="sxs-lookup"><span data-stu-id="7e1da-140">Only entities that support the use of custom fields appear in the grid.</span></span> <span data-ttu-id="7e1da-141">Nowe jednostki są udostępniane w kolejnych wydaniach programu Human Resources.</span><span class="sxs-lookup"><span data-stu-id="7e1da-141">New entities become available through continuous releases of Human Resources.</span></span>

<span data-ttu-id="7e1da-142">Siatka zawiera następujące pola:</span><span class="sxs-lookup"><span data-stu-id="7e1da-142">The grid includes the following fields:</span></span>

- <span data-ttu-id="7e1da-143">**Nazwa jednostki w usłudze CDS** — nazwa jednostki w usłudze Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="7e1da-143">**CDS entity name** – The name of the entity in Common Data Service.</span></span>
- <span data-ttu-id="7e1da-144">**Odwołanie do jednostki w usłudze CDS** — identyfikator wykorzystywany przez usługę Common Data Service do identyfikowania rekordu.</span><span class="sxs-lookup"><span data-stu-id="7e1da-144">**CDS entity reference** – The identifier that Common Data Service uses to identify a record.</span></span> <span data-ttu-id="7e1da-145">Ta wartość jest równoważna wartości **RecId** w module Human Resources.</span><span class="sxs-lookup"><span data-stu-id="7e1da-145">This value is equivalent to a Human Resources **RecId** value.</span></span> <span data-ttu-id="7e1da-146">Identyfikator można znaleźć po otwarciu jednostki usługi Common Data Service w programie Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="7e1da-146">You can find the identifier when you open the Common Data Service entity in Microsoft Excel.</span></span>
- <span data-ttu-id="7e1da-147">**Nazwa jednostki modułu Human Resources** — jednostka, której dane były ostatnio synchronizowane z usługą Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="7e1da-147">**Human Resources entity name** – The entity that last synced data to Common Data Service.</span></span> <span data-ttu-id="7e1da-148">Jednostka może mieć prefiks usługi Common Data Service lub inny prefiks.</span><span class="sxs-lookup"><span data-stu-id="7e1da-148">The entity can have either the Common Data Service prefix or another prefix.</span></span>
- <span data-ttu-id="7e1da-149">**Odwołanie do modułu Human Resources** – wartość **RecId** skojarzona z rekordem w module Human Resources.</span><span class="sxs-lookup"><span data-stu-id="7e1da-149">**Human Resources reference** – The **RecId** value that is associated with the record in Human Resources.</span></span>
- <span data-ttu-id="7e1da-150">**Usunięto z usługi CDS** — wartość wskazująca, czy rekord został usunięty z usługi Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="7e1da-150">**Was deleted from CDS** – A value that indicates whether the record was deleted from Common Data Service.</span></span>

## <a name="remove-the-association-of-a-record-in-human-resources-from-common-data-service"></a><span data-ttu-id="7e1da-151">Usuwanie skojarzenia rekordu z usługi Common Data Service w module Human Resources</span><span class="sxs-lookup"><span data-stu-id="7e1da-151">Remove the association of a record in Human Resources from Common Data Service</span></span>

<span data-ttu-id="7e1da-152">Jeśli występują problemy podczas synchronizacji danych między modułem Human Resources a usługą Common Data Service, można je rozwiązać, czyszcząc dane śledzenia i umożliwiając ponowne zsynchronizowanie tabeli śledzenia.</span><span class="sxs-lookup"><span data-stu-id="7e1da-152">If you experience issues during data synchronization between Human Resources and Common Data Service, you might be able to resolve them by clearing the tracking and letting the tracking table be resynced.</span></span> <span data-ttu-id="7e1da-153">Jeśli usuniesz skojarzenie, a następnie zmienisz lub usuniesz rekord w usłudze Common Data Service, zmiany nie zostaną zsynchronizowane z usługą Human Resources.</span><span class="sxs-lookup"><span data-stu-id="7e1da-153">If you remove the association, and then change or delete a record in Common Data Service, the changes won't be synced to Human Resources.</span></span> <span data-ttu-id="7e1da-154">W przypadku wprowadzenia zmian w module Human Resources zostanie utworzony nowy rekord śledzenia, a rekord danych zostanie zaktualizowany w Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="7e1da-154">If you make changes in Human Resources, a new tracking record is created, and the record is updated in Common Data Service.</span></span>

- <span data-ttu-id="7e1da-155">Aby usunąć powiązanie rekordu między modułem Human Resources a usługą Common Data Service, zaznacz jednostkę w polu **Nazwa jednostki w usłudze CDS**, a następnie wybierz opcję **Wyczyść informacje śledzenia**.</span><span class="sxs-lookup"><span data-stu-id="7e1da-155">To remove the association of a record between Human Resources and Common Data Service, select the entity in the **CDS entity name** field, and then select **Clear tracking information**.</span></span>

<span data-ttu-id="7e1da-156">[![Czyszczenie informacji śledzenia](./media/hr-common-data-service-configuration-clear-tracking.png)](./media/hr-common-data-service-configuration-clear-tracking.png)</span><span class="sxs-lookup"><span data-stu-id="7e1da-156">[![Clearing tracking information](./media/hr-common-data-service-configuration-clear-tracking.png)](./media/hr-common-data-service-configuration-clear-tracking.png)</span></span>

<span data-ttu-id="7e1da-157">Aby wykonać pełną synchronizację jednostki po wyczyszczeniu danych śledzenia, skorzystaj z następnej procedury.</span><span class="sxs-lookup"><span data-stu-id="7e1da-157">To run a full synchronization on the entity after you clear the tracking, see the next procedure.</span></span>

## <a name="sync-an-entity-between-human-resources-and-common-data-service"></a><span data-ttu-id="7e1da-158">Synchronizowanie jednostki między modułem Human Resources a usługą Common Data Service</span><span class="sxs-lookup"><span data-stu-id="7e1da-158">Sync an entity between Human Resources and Common Data Service</span></span>

<span data-ttu-id="7e1da-159">Tę procedurę należy wykonać, jeśli zmiany wprowadzone w usłudze Common Data Service pojawiają się po zbyt długim czasie w usłudze Human Resources lub jeśli trzeba odświeżyć tabelę śledzenia po wyczyszczeniu danych śledzenia.</span><span class="sxs-lookup"><span data-stu-id="7e1da-159">Use this procedure if changes from Common Data Service are taking too long to appear in Human Resources, or if you must refresh the tracking table after you clear the tracking.</span></span>

- <span data-ttu-id="7e1da-160">Aby wykonać pełną synchronizację jednostki między modułem Human Resources a usługą Common Data Service, wybierz jednostkę w polu **Nazwa jednostki w usłudze CDS**, a następnie wybierz opcję **Synchronizuj teraz**.</span><span class="sxs-lookup"><span data-stu-id="7e1da-160">To run a full synchronization on an entity between Human Resources and Common Data Service, select the entity in the **CDS entity name** field, and then select **Sync now**.</span></span>

<span data-ttu-id="7e1da-161">[![Wykonywanie pełnej synchronizacji](./media/hr-common-data-service-configuration-sync-now.png)](./media/hr-common-data-service-configuration-sync-now.png)</span><span class="sxs-lookup"><span data-stu-id="7e1da-161">[![Running a full synchronization](./media/hr-common-data-service-configuration-sync-now.png)](./media/hr-common-data-service-configuration-sync-now.png)</span></span>


