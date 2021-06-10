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
# <a name="configure-dataverse-integration"></a><span data-ttu-id="2030d-104">Konfigurowanie integracji z usługą Dataverse</span><span class="sxs-lookup"><span data-stu-id="2030d-104">Configure Dataverse integration</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="2030d-105">Można włączyć lub wyłączyć integrację między usługą Microsoft Dataverse a Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="2030d-105">You can turn integration between Microsoft Dataverse and Dynamics 365 Human Resources on or off.</span></span> <span data-ttu-id="2030d-106">Można również wyświetlić szczegóły synchronizacji, wyczyścić dane śledzenia i dokonać ponownej synchronizacji tabeli, aby ułatwić rozwiązywanie problemów z danymi między tymi dwoma środowiskami.</span><span class="sxs-lookup"><span data-stu-id="2030d-106">You can also view the synchronization details, clear tracking data, and resync a table to help troubleshoot data issues between the two environments.</span></span>

> [!NOTE]
> <span data-ttu-id="2030d-107">Aby uzyskać więcej informacji o Dataverse (poprzednio Common Data Service) i aktualizacjach terminologii, zobacz [Co to jest Microsoft Dataverse?](/powerapps/maker/data-platform/data-platform-intro)</span><span class="sxs-lookup"><span data-stu-id="2030d-107">For more information about Dataverse (formerly Common Data Service) and terminology updates, see [What is Microsoft Dataverse?](/powerapps/maker/data-platform/data-platform-intro)</span></span>

<span data-ttu-id="2030d-108">Po wyłączeniu integracji użytkownicy mogą wprowadzać zmiany w module Human Resources lub usłudze Dataverse, ale te zmiany nie są synchronizowane między oboma środowiskami.</span><span class="sxs-lookup"><span data-stu-id="2030d-108">When you turn off integration, users can make changes in Human Resources or Dataverse, but those changes aren't synced between the two environments.</span></span>

<span data-ttu-id="2030d-109">Domyślnie integracja danych między modułem Human Resources a usługą Dataverse jest wyłączona.</span><span class="sxs-lookup"><span data-stu-id="2030d-109">By default, integration between Human Resources and Dataverse is turned off.</span></span>

<span data-ttu-id="2030d-110">Wyłączenie integracji może być zalecane w następujących sytuacjach:</span><span class="sxs-lookup"><span data-stu-id="2030d-110">You might want to turn off integration in these situations:</span></span>

- <span data-ttu-id="2030d-111">Wprowadzasz dane za pomocą struktury zarządzania danymi i musisz je zaimportować wielokrotnie, aby osiągnęły poprawny stan.</span><span class="sxs-lookup"><span data-stu-id="2030d-111">You're filling in data through the Data Management Framework and must import the data multiple times to get it into a correct state.</span></span>

- <span data-ttu-id="2030d-112">Istnieją problemy z danymi w module Human Resources lub usłudze Dataverse.</span><span class="sxs-lookup"><span data-stu-id="2030d-112">There are issues with data in either Human Resources or Dataverse.</span></span> <span data-ttu-id="2030d-113">Po wyłączeniu integracji można usunąć rekord w jednym środowisku bez usuwania go w drugim.</span><span class="sxs-lookup"><span data-stu-id="2030d-113">If you turn off integration, you can delete a record in one environment without deleting it in the other.</span></span> <span data-ttu-id="2030d-114">Po ponownym włączeniu integracji rekord w środowisku, w którym nie został usunięty, jest zsynchronizowany do środowiska, w którym został usunięty.</span><span class="sxs-lookup"><span data-stu-id="2030d-114">When you turn integration back on, the record in the environment where it wasn't deleted sync to the environment where it was deleted.</span></span> <span data-ttu-id="2030d-115">Synchronizacja rozpocznie się przy następnym uruchomieniu zadania wsadowego **Żądanie synchronizacji pominiętej integracji z usługą Dataverse**.</span><span class="sxs-lookup"><span data-stu-id="2030d-115">Synchronization begins the next time the **Dataverse integration missed request sync** batch job runs.</span></span>

> [!WARNING]
> <span data-ttu-id="2030d-116">Po wyłączeniu integracji danych należy się upewnić, że ten sam rekord nie będzie edytowany w obu środowiskach.</span><span class="sxs-lookup"><span data-stu-id="2030d-116">When you turn off data integration, make sure that you don't edit the same record in both environments.</span></span> <span data-ttu-id="2030d-117">Po ponownym włączeniu integracji zostanie zsynchronizowany rekord, który był ostatnio edytowany.</span><span class="sxs-lookup"><span data-stu-id="2030d-117">When you turn integration back on, the record that you last edited will be synced.</span></span> <span data-ttu-id="2030d-118">W związku z tym jeśli nie dokonano takich samych zmian w rekordzie w obu środowiskach, może nastąpić utrata danych.</span><span class="sxs-lookup"><span data-stu-id="2030d-118">Therefore, if you didn't make the same changes to the record in both environments, data loss can occur.</span></span>

## <a name="access-the-dataverse-integration-page"></a><span data-ttu-id="2030d-119">Dostęp do strony integracji z usługą Dataverse</span><span class="sxs-lookup"><span data-stu-id="2030d-119">Access the Dataverse integration page</span></span>

1. <span data-ttu-id="2030d-120">W wystąpieniu modułu Human Resources, w którym chcesz wyświetlić lub skonfigurować ustawienia integracji z usługą Dataverse, wybierz kafelek **Administrowanie systemem**.</span><span class="sxs-lookup"><span data-stu-id="2030d-120">In the Human Resources instance where you want to view or configure settings for the integration with Dataverse, select the **System administration** tile.</span></span>

    <span data-ttu-id="2030d-121">[![Kafelek Administrowanie systemem](./media/hr-select-system-administration.png)](./media/hr-select-system-administration.png)</span><span class="sxs-lookup"><span data-stu-id="2030d-121">[![System administration tile](./media/hr-select-system-administration.png)](./media/hr-select-system-administration.png)</span></span>

2. <span data-ttu-id="2030d-122">Kliknij kartę **Łącza**.</span><span class="sxs-lookup"><span data-stu-id="2030d-122">Select the **Links** tab.</span></span>

    <span data-ttu-id="2030d-123">[![Karta Łącza](./media/hr-system-administration-links.png)](./media/hr-system-administration-links.png)</span><span class="sxs-lookup"><span data-stu-id="2030d-123">[![Links tab](./media/hr-system-administration-links.png)](./media/hr-system-administration-links.png)</span></span>

3. <span data-ttu-id="2030d-124">W obszarze **Integracje** wybierz pozycję **Konfiguracja usługi Dataverse**.</span><span class="sxs-lookup"><span data-stu-id="2030d-124">Under **Integrations**, select **Dataverse configuration**.</span></span>

    <span data-ttu-id="2030d-125">[![Łącze Konfiguracja usługi Dataverse](./media/hr-admin-integration-dataverse-select.png)](./media/hr-admin-integration-dataverse-select.png)</span><span class="sxs-lookup"><span data-stu-id="2030d-125">[![Dataverse configuration link](./media/hr-admin-integration-dataverse-select.png)](./media/hr-admin-integration-dataverse-select.png)</span></span>

## <a name="turn-data-integration-between-human-resources-and-dataverse-on-or-off"></a><span data-ttu-id="2030d-126">Włączenie lub wyłączanie integracji danych między modułem Human Resources a usługą Dataverse</span><span class="sxs-lookup"><span data-stu-id="2030d-126">Turn data integration between Human Resources and Dataverse on or off</span></span>

- <span data-ttu-id="2030d-127">Aby włączyć integrację, w opcji **Włącz integrację z usługą Dataverse** ustaw wartość **Tak** na stronie **integracja Microsoft Dataverse**.</span><span class="sxs-lookup"><span data-stu-id="2030d-127">To turn on integration, set the **Enable Dataverse integration** option to **Yes** on the **Microsoft Dataverse integration** page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2030d-128">Po włączeniu integracji dane zostaną zsynchronizowane przy następnym uruchomieniu zadania wsadowego **Żądanie synchronizacji pominiętej integracji z usługą Dataverse**.</span><span class="sxs-lookup"><span data-stu-id="2030d-128">When you turn on integration, data will be synced the next time that the **Dataverse integration missed request sync** batch job runs.</span></span> <span data-ttu-id="2030d-129">Po zakończeniu zadania wsadowego wszystkie dane powinny być dostępne.</span><span class="sxs-lookup"><span data-stu-id="2030d-129">All data should be available after the batch job is completed.</span></span>

- <span data-ttu-id="2030d-130">Aby wyłączyć integrację, ustaw w opcji wartość **Nie**.</span><span class="sxs-lookup"><span data-stu-id="2030d-130">To turn off integration, set the option to **No**.</span></span>

<span data-ttu-id="2030d-131">[![Włączanie lub wyłączanie integracji z usługą Dataverse](./media/hr-admin-integration-dataverse-enable-disable.png)](./media/hr-admin-integration-dataverse-enable-disable.png)</span><span class="sxs-lookup"><span data-stu-id="2030d-131">[![Turning the Dataverse integration on or off](./media/hr-admin-integration-dataverse-enable-disable.png)](./media/hr-admin-integration-dataverse-enable-disable.png)</span></span>

> [!WARNING]
> <span data-ttu-id="2030d-132">Stanowczo zaleca się wyłączenie integracji Dataverse podczas wykonywania zadań migracji danych.</span><span class="sxs-lookup"><span data-stu-id="2030d-132">We strongly recommend turning off Dataverse integration while performing data migration tasks.</span></span> <span data-ttu-id="2030d-133">Duże operacje przekazywania danych mogą znacząco wpłynąć na wydajność.</span><span class="sxs-lookup"><span data-stu-id="2030d-133">Large data uploads can significantly impact performance.</span></span> <span data-ttu-id="2030d-134">Na przykład przekazywanie 2000 pracowników może potrwać kilka godzin, gdy integracja jest włączona, i mniej niż jedna godzina, gdy jest wyłączona.</span><span class="sxs-lookup"><span data-stu-id="2030d-134">For example, uploading 2000 workers can take several hours when integration is enabled, and less than one hour when it's disabled.</span></span> <span data-ttu-id="2030d-135">Numery podane w tym przykładzie służą tylko do celów demonstracyjnych.</span><span class="sxs-lookup"><span data-stu-id="2030d-135">The numbers provided in this example are for demonstration purposes only.</span></span> <span data-ttu-id="2030d-136">Dokładna ilość czasu importowania rekordów może się znacznie różnić w zależności od wielu czynników.</span><span class="sxs-lookup"><span data-stu-id="2030d-136">The exact amount of time it takes to import records can vary greatly based on many factors.</span></span>

## <a name="view-data-integration-details"></a><span data-ttu-id="2030d-137">Wyświetlanie szczegółów integracji danych</span><span class="sxs-lookup"><span data-stu-id="2030d-137">View data integration details</span></span>

<span data-ttu-id="2030d-138">Na stronie **Integracja z usługą Microsoft Dataverse** na skróconej karcie **Administracja** można zobaczyć, jak wiersze są z sobą połączone między modułem Human Resources a usługą Dataverse.</span><span class="sxs-lookup"><span data-stu-id="2030d-138">On the **Administration** FastTab of the **Microsoft Dataverse integration** page, you can see how rows are linked together between Human Resources and Dataverse.</span></span>

- <span data-ttu-id="2030d-139">Aby wyświetlić wiersze dla tabeli, wybierz tabelę w polu **tabeli Dataverse**.</span><span class="sxs-lookup"><span data-stu-id="2030d-139">To view the rows for a table, select the table in the **Dataverse table** field.</span></span> <span data-ttu-id="2030d-140">W siatce zostaną wyświetlone wszystkie wiersze połączone z wybraną tabelę.</span><span class="sxs-lookup"><span data-stu-id="2030d-140">The grid shows all the rows that are linked to the selected table.</span></span>

> [!NOTE]
> <span data-ttu-id="2030d-141">Nie wszystkie tabele usługi Dataverse są obecnie wyświetlane.</span><span class="sxs-lookup"><span data-stu-id="2030d-141">Not all Dataverse tables are currently listed.</span></span> <span data-ttu-id="2030d-142">W siatce widać tylko tabele, które obsługują używanie pól niestandardowych.</span><span class="sxs-lookup"><span data-stu-id="2030d-142">Only tables that support the use of custom fields appear in the grid.</span></span> <span data-ttu-id="2030d-143">Nowe tabele są udostępniane w kolejnych wydaniach programu Human Resources.</span><span class="sxs-lookup"><span data-stu-id="2030d-143">New tables become available through continuous releases of Human Resources.</span></span>

<span data-ttu-id="2030d-144">Siatka zawiera następujące pola:</span><span class="sxs-lookup"><span data-stu-id="2030d-144">The grid includes the following fields:</span></span>

- <span data-ttu-id="2030d-145">**Tabele Dataverse** – Nazwa tabeli przemieszczania w Dataverse.</span><span class="sxs-lookup"><span data-stu-id="2030d-145">**Dataverse table** – The name of the table in Dataverse.</span></span>
- <span data-ttu-id="2030d-146">**Odwołanie do tabeli Dataverse** — identyfikator wykorzystywany przez usługę Dataverse do identyfikowania rekordu.</span><span class="sxs-lookup"><span data-stu-id="2030d-146">**Dataverse table reference** – The identifier that Dataverse uses to identify a record.</span></span> <span data-ttu-id="2030d-147">Ta wartość jest równoważna wartości **RecId** w module Human Resources.</span><span class="sxs-lookup"><span data-stu-id="2030d-147">This value is equivalent to a Human Resources **RecId** value.</span></span> <span data-ttu-id="2030d-148">Identyfikator można znaleźć po otwarciu tabeli usługi Dataverse w programie Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="2030d-148">You can find the identifier when you open the Dataverse table in Microsoft Excel.</span></span>
- <span data-ttu-id="2030d-149">**Nazwa jednostki modułu Human Resources** — jednostka Human Resources, której dane były ostatnio synchronizowane z usługą Dataverse.</span><span class="sxs-lookup"><span data-stu-id="2030d-149">**Human Resources entity name** – The Human Resources entity that last synced data to Dataverse.</span></span> <span data-ttu-id="2030d-150">Jednostka może mieć prefiks usługi Dataverse lub inny prefiks.</span><span class="sxs-lookup"><span data-stu-id="2030d-150">The entity can have either the Dataverse prefix or another prefix.</span></span>
- <span data-ttu-id="2030d-151">**Odwołanie do modułu Human Resources** – wartość **RecId** skojarzona z rekordem w module Human Resources.</span><span class="sxs-lookup"><span data-stu-id="2030d-151">**Human Resources reference** – The **RecId** value that is associated with the record in Human Resources.</span></span>
- <span data-ttu-id="2030d-152">**Usunięto z usługi Dataverse** — wartość wskazująca, czy wiersz został usunięty z usługi Dataverse.</span><span class="sxs-lookup"><span data-stu-id="2030d-152">**Deleted from Dataverse** – A value that indicates whether the row was deleted from Dataverse.</span></span>

> [!NOTE]
> <span data-ttu-id="2030d-153">Rekordy w Human Resources odpowiadają wierszom w Dataverse.</span><span class="sxs-lookup"><span data-stu-id="2030d-153">Records in Human Resources correspond to rows in Dataverse.</span></span>

## <a name="remove-the-association-of-a-human-resources-record-from-a-dataverse-row"></a><span data-ttu-id="2030d-154">Usuwanie skojarzenia rekordu Human Resources z wiersza usługi Dataverse</span><span class="sxs-lookup"><span data-stu-id="2030d-154">Remove the association of a Human Resources record from a Dataverse row</span></span>

<span data-ttu-id="2030d-155">Jeśli występują problemy podczas synchronizacji danych między modułem Human Resources a usługą Dataverse, można je rozwiązać, czyszcząc dane śledzenia i umożliwiając ponowne zsynchronizowanie tabeli śledzenia.</span><span class="sxs-lookup"><span data-stu-id="2030d-155">If you experience issues during data synchronization between Human Resources and Dataverse, you might be able to resolve them by clearing the tracking and letting the tracking table be resynced.</span></span> <span data-ttu-id="2030d-156">Jeśli usuniesz skojarzenie, a następnie zmienisz lub usuniesz wiersz w usłudze Dataverse, zmiany nie zostaną zsynchronizowane z usługą Human Resources.</span><span class="sxs-lookup"><span data-stu-id="2030d-156">If you remove the association, and then change or delete a row in Dataverse, the changes won't be synced to Human Resources.</span></span> <span data-ttu-id="2030d-157">W przypadku wprowadzenia zmian w module Human Resources zostanie utworzony nowy rekord śledzenia, a wiersz danych zostanie zaktualizowany w Dataverse.</span><span class="sxs-lookup"><span data-stu-id="2030d-157">If you make changes in Human Resources, a new tracking record is created, and the row is updated in Dataverse.</span></span>

- <span data-ttu-id="2030d-158">Aby usunąć powiązanie rekordu między rekordem Human Resources a wierszem Dataverse, zaznacz tabelę w polu **Tabela Dataverse**, a następnie wybierz opcję **Wyczyść informacje śledzenia**.</span><span class="sxs-lookup"><span data-stu-id="2030d-158">To remove the association of a Human Resources record and a Dataverse row, select the table in the **Dataverse table** field, and then select **Clear tracking information**.</span></span>

<span data-ttu-id="2030d-159">[![Czyszczenie informacji śledzenia](./media/hr-admin-integration-dataverse-clear-tracking.png)](./media/hr-admin-integration-dataverse-clear-tracking.png)</span><span class="sxs-lookup"><span data-stu-id="2030d-159">[![Clearing tracking information](./media/hr-admin-integration-dataverse-clear-tracking.png)](./media/hr-admin-integration-dataverse-clear-tracking.png)</span></span>

<span data-ttu-id="2030d-160">Aby wykonać pełną synchronizację tabeli po wyczyszczeniu danych śledzenia, skorzystaj z następnej procedury.</span><span class="sxs-lookup"><span data-stu-id="2030d-160">To run a full synchronization on the table after you clear the tracking, see the next procedure.</span></span>

## <a name="sync-a-table-between-human-resources-and-dataverse"></a><span data-ttu-id="2030d-161">Synchronizowanie tabeli między modułem Human Resources a usługą Dataverse</span><span class="sxs-lookup"><span data-stu-id="2030d-161">Sync a table between Human Resources and Dataverse</span></span>

<span data-ttu-id="2030d-162">Tę procedurę należy wykonać jeśli:</span><span class="sxs-lookup"><span data-stu-id="2030d-162">Use this procedure when:</span></span>

- <span data-ttu-id="2030d-163">Zmiany wprowadzone w Dataverse zbyt wolno pojawiają się w Human Resources.</span><span class="sxs-lookup"><span data-stu-id="2030d-163">Changes from Dataverse take too long to appear in Human Resources.</span></span>

- <span data-ttu-id="2030d-164">Tabelę śledzenia należy odświeżyć po wyczyszczeniu śledzenia.</span><span class="sxs-lookup"><span data-stu-id="2030d-164">You must refresh the tracking table after clearing the tracking.</span></span>

<span data-ttu-id="2030d-165">Aby uruchomić pełną synchronizację tabeli między Human Resources a Dataverse:</span><span class="sxs-lookup"><span data-stu-id="2030d-165">To run a full synchronization on a table between Human Resources and Dataverse:</span></span>

1. <span data-ttu-id="2030d-166">Wybierz tabelę w polu **tabela Dataverse**.</span><span class="sxs-lookup"><span data-stu-id="2030d-166">Select the table in the **Dataverse table** field.</span></span>

2. <span data-ttu-id="2030d-167">Wybierz opcję **Synchronizuj teraz**.</span><span class="sxs-lookup"><span data-stu-id="2030d-167">Select **Sync now**.</span></span>

<span data-ttu-id="2030d-168">[![Wykonywanie pełnej synchronizacji](./media/hr-admin-integration-dataverse-sync-now.png)](./media/hr-admin-integration-dataverse-sync-now.png)</span><span class="sxs-lookup"><span data-stu-id="2030d-168">[![Running a full synchronization](./media/hr-admin-integration-dataverse-sync-now.png)](./media/hr-admin-integration-dataverse-sync-now.png)</span></span>

## <a name="see-also"></a><span data-ttu-id="2030d-169">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="2030d-169">See also</span></span>

[<span data-ttu-id="2030d-170">Tabele Dataverse</span><span class="sxs-lookup"><span data-stu-id="2030d-170">Dataverse tables</span></span>](hr-developer-entities.md)<br>
[<span data-ttu-id="2030d-171">Konfiguruj tabele wirtualne usługi Dataverse</span><span class="sxs-lookup"><span data-stu-id="2030d-171">Configure Dataverse virtual tables</span></span>](hr-admin-integration-common-data-service-virtual-entities.md)<br>
[<span data-ttu-id="2030d-172">Często zadawanych pytań dotyczące tabel wirtualnych dla Human Resources</span><span class="sxs-lookup"><span data-stu-id="2030d-172">Human Resources virtual tables FAQ</span></span>](hr-admin-virtual-entity-faq.md)<br>
[<span data-ttu-id="2030d-173">Co to jest usługa Microsoft Dataverse?</span><span class="sxs-lookup"><span data-stu-id="2030d-173">What is Microsoft Dataverse?</span></span>](/powerapps/maker/data-platform/data-platform-intro)<br>
[<span data-ttu-id="2030d-174">Aktualizacje terminologii</span><span class="sxs-lookup"><span data-stu-id="2030d-174">Terminology updates</span></span>](/powerapps/maker/data-platform/data-platform-intro#terminology-updates)


[!INCLUDE[footer-include](../includes/footer-banner.md)]