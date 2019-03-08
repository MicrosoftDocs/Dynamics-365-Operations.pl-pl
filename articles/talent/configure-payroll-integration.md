---
title: Konfigurowanie integracji listy płac między rozwiązaniami Talent i Dayforce
description: W tym temacie wyjaśniono sposób konfigurowania integracji między programami Microsoft Dynamics 365 for Talent i Ceridian Dayforce, dzięki czemu można przetwarzać sekcję płatności.
author: jcart1106
manager: AnnBe
ms.date: 07/10/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations, Talent
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: fcddf82cffb9f0ba94b83eb21809b810585ebc9e
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "305763"
---
# <a name="configure-the-payroll-integration-between-talent-and-dayforce"></a><span data-ttu-id="956f8-103">Konfigurowanie integracji listy płac między rozwiązaniami Talent i Dayforce</span><span class="sxs-lookup"><span data-stu-id="956f8-103">Configure the payroll integration between Talent and Dayforce</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="956f8-104">Integracja między programami Microsoft Dynamics 365 for Talent i Ceridian Dayforce opiera się na kilku krokach konfiguracji, które opisano w tym temacie.</span><span class="sxs-lookup"><span data-stu-id="956f8-104">The integration between Microsoft Dynamics 365 for Talent and Ceridian Dayforce relies on several configuration steps that are described in this topic.</span></span> <span data-ttu-id="956f8-105">Aby można było przetwarzać sesję płatności, należy skonfigurować integrację w rozwiązaniach Talent i Dayforce.</span><span class="sxs-lookup"><span data-stu-id="956f8-105">You must configure the integration in both Talent and Dayforce before you can process a pay run.</span></span>

<span data-ttu-id="956f8-106">Jeśli korzystasz z usługi takiej jak Dayforce do realizowania sesji płatności, należy włączyć integrację w aplikacji Talent.</span><span class="sxs-lookup"><span data-stu-id="956f8-106">When you use a service such as Dayforce to complete pay runs, you must enable the integration in Talent.</span></span> <span data-ttu-id="956f8-107">Integracja wymaga określonych danych z programu Talent.</span><span class="sxs-lookup"><span data-stu-id="956f8-107">The integration requires specific data from Talent.</span></span> <span data-ttu-id="956f8-108">W związku z tym należy sprawdzić, czy dane mapowane do systemu Dayforce są skonfigurowano w aplikacji Talent w sposób zapewniający obsługę integracji.</span><span class="sxs-lookup"><span data-stu-id="956f8-108">Therefore, you must verify that data that is mapped to Dayforce is configured in Talent in a manner that supports the integration.</span></span> <span data-ttu-id="956f8-109">Integracja wykorzystuje następujące ogólne kategorie danych:</span><span class="sxs-lookup"><span data-stu-id="956f8-109">The integration uses the following broad categories of data:</span></span>

- <span data-ttu-id="956f8-110">Dane kadrowe</span><span class="sxs-lookup"><span data-stu-id="956f8-110">Human resources data</span></span>
- <span data-ttu-id="956f8-111">Dane o wynagrodzeniach</span><span class="sxs-lookup"><span data-stu-id="956f8-111">Compensation data</span></span>
- <span data-ttu-id="956f8-112">Dane listy płac, takie jak cykle kalkulacji płac, okresy kalkulacji płac i kody zarobków</span><span class="sxs-lookup"><span data-stu-id="956f8-112">Payroll data, such as pay cycles, pay periods, and earning codes</span></span>
- <span data-ttu-id="956f8-113">Dane pracowników</span><span class="sxs-lookup"><span data-stu-id="956f8-113">Worker data</span></span>

<span data-ttu-id="956f8-114">W tym temacie opisano czynności, które należy wykonać, aby włączyć integrację.</span><span class="sxs-lookup"><span data-stu-id="956f8-114">This topic describes the steps that you must follow to enable the integration.</span></span> <span data-ttu-id="956f8-115">Objaśniono tu także typy danych i szczegóły konfiguracji, których wymaga integracja.</span><span class="sxs-lookup"><span data-stu-id="956f8-115">It also explains the types of data and the configuration details that the integration requires.</span></span>

## <a name="enable-the-integration"></a><span data-ttu-id="956f8-116">Włączanie integracji</span><span class="sxs-lookup"><span data-stu-id="956f8-116">Enable the integration</span></span>

<span data-ttu-id="956f8-117">W aplikacji Talent należy włączyć funkcję integracji i wprowadzić informacje konfiguracyjne w celu nawiązania połączenia z systemem Dayforce.</span><span class="sxs-lookup"><span data-stu-id="956f8-117">In Talent, you must turn on the integration and enter the configuration information to connect to Dayforce.</span></span> <span data-ttu-id="956f8-118">Jeśli chcesz, aby generowane transakcje księgi głównej były importowane do programu Microsoft Dynamics 365 for Finance and Operations, należy także skonfigurować konto magazynu w usłudze Microsoft Azure oraz wprowadzić ciąg połączenia z usługą Azure Storage w aplikacji Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="956f8-118">If you want the general ledger transaction that is produced to be imported into Microsoft Dynamics 365 for Finance and Operations, you must also set up a Microsoft Azure storage account and enter the Azure Storage connection string in Finance and Operations.</span></span>

<span data-ttu-id="956f8-119">Aby włączyć integrację w aplikacji Talent, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="956f8-119">To turn on the integration in Talent, follow these steps.</span></span>

1. <span data-ttu-id="956f8-120">Na stronie **Administrowanie systemem** wybierz opcję **Konfiguracja integracji**.</span><span class="sxs-lookup"><span data-stu-id="956f8-120">On the **System administration** page, select **Integration configuration**.</span></span>
2. <span data-ttu-id="956f8-121">Wprowadź punkt końcowy objęty bezpiecznym protokołem FTP (File Transfer Protocol) i ścieżkę do folderu objętego bezpiecznym protokołem FTP.</span><span class="sxs-lookup"><span data-stu-id="956f8-121">Enter the secure File Transfer Protocol (FTP) endpoint and the secure FTP folder path.</span></span>
3. <span data-ttu-id="956f8-122">Wprowadź nazwę użytkownika i hasło użytkownika, który będzie uzyskiwał dostęp do punktu końcowego i ścieżki folderu objętych bezpiecznym protokołem FTP.</span><span class="sxs-lookup"><span data-stu-id="956f8-122">Enter the user name and password of the user who will access the secure FTP endpoint and folder path.</span></span>
4. <span data-ttu-id="956f8-123">Przetestuj połączenie, a w opcji **Włącz integrację listy płac** ustaw wartość **Tak**.</span><span class="sxs-lookup"><span data-stu-id="956f8-123">Test the connection, as required, and set the **Enable payroll integration** option to **Yes**.</span></span>

<span data-ttu-id="956f8-124">Po włączeniu integracji następuje utworzenie pakietu i plików eksportu danych oraz ustawienie częstotliwości.</span><span class="sxs-lookup"><span data-stu-id="956f8-124">When the integration is turned on, the data export package and files are created, and the frequency is set.</span></span> <span data-ttu-id="956f8-125">W razie potrzeby można zmienić tę częstotliwość.</span><span class="sxs-lookup"><span data-stu-id="956f8-125">You can change this frequency as you require.</span></span>

<span data-ttu-id="956f8-126">Aby uzyskać więcej informacji o kontach magazynu w usłudze Azure i ciągach połączeń z usługą Azure Storage, zobacz następujące tematy poświęcone usłudze Azure:</span><span class="sxs-lookup"><span data-stu-id="956f8-126">For more information about Azure storage accounts and Azure Storage connection strings, see the following Azure topics:</span></span>

- [<span data-ttu-id="956f8-127">Konta magazynu w usłudze Azure — informacje</span><span class="sxs-lookup"><span data-stu-id="956f8-127">About Azure storage accounts</span></span>](https://docs.microsoft.com/en-us/azure/storage/common/storage-create-storage-account?toc=%2fazure%2fstorage%2ffiles%2ftoc.json)
- [<span data-ttu-id="956f8-128">Konfigurowanie ciągów połączeń z usługą Azure Storage</span><span class="sxs-lookup"><span data-stu-id="956f8-128">Configure Azure Storage connection strings</span></span>](https://docs.microsoft.com/en-us/azure/storage/common/storage-configure-connection-string)

## <a name="configure-your-data"></a><span data-ttu-id="956f8-129">Konfigurowanie danych</span><span class="sxs-lookup"><span data-stu-id="956f8-129">Configure your data</span></span> 

<span data-ttu-id="956f8-130">Aby przetwarzać listę płac, należy skonfigurować dane kadrowe w aplikacji Talent.</span><span class="sxs-lookup"><span data-stu-id="956f8-130">To process payroll, you must configure human resource data in Talent.</span></span> <span data-ttu-id="956f8-131">Należy skonfigurować dane organizacyjne, takie jak funkcje i stanowiska, oraz informacje o wynagrodzeniach i świadczeniach.</span><span class="sxs-lookup"><span data-stu-id="956f8-131">You must set up organizational data, such as jobs and positions, together with benefits and compensation information.</span></span> <span data-ttu-id="956f8-132">Informacje te stanowią zasób danych o zatrudnieniu, wynagrodzeniach i potrąceniach, które są wymagane do wygenerowania płacy pracownika.</span><span class="sxs-lookup"><span data-stu-id="956f8-132">This information provides the employment, pay, and deduction information that is required in order to generate employee pay.</span></span>

### <a name="human-resource-data"></a><span data-ttu-id="956f8-133">Dane kadrowe</span><span class="sxs-lookup"><span data-stu-id="956f8-133">Human resource data</span></span>

#### <a name="benefits"></a><span data-ttu-id="956f8-134">Świadczenia</span><span class="sxs-lookup"><span data-stu-id="956f8-134">Benefits</span></span> 

<span data-ttu-id="956f8-135">Moduł Zasoby ludzkie oferuje narzędzia do konfigurowania i obsługi świadczeń, potrąceń i planów wynagrodzeń pracowników, które organizacja oferuje swoim pracownikom lub przetwarza w ich imieniu.</span><span class="sxs-lookup"><span data-stu-id="956f8-135">Human resources provides tools for the setup and maintenance of the benefits, deductions, and worker compensation plans that an organization offers or processes for its workers.</span></span>

<span data-ttu-id="956f8-136">Podczas tworzenia świadczeń należy wziąć pod uwagę następujące dane i konfiguracje używane w systemie Dayforce.</span><span class="sxs-lookup"><span data-stu-id="956f8-136">When you create benefits, keep in mind the following data and configurations that are used in Dayforce.</span></span>

##### <a name="benefit-plans"></a><span data-ttu-id="956f8-137">Plany świadczeń</span><span class="sxs-lookup"><span data-stu-id="956f8-137">Benefit plans</span></span>

- <span data-ttu-id="956f8-138">Plan (wymagane)</span><span class="sxs-lookup"><span data-stu-id="956f8-138">Plan (required)</span></span>
- <span data-ttu-id="956f8-139">Typ (wymagane)</span><span class="sxs-lookup"><span data-stu-id="956f8-139">Type (required)</span></span>
- <span data-ttu-id="956f8-140">Wpływ na listę płac (wymagane)</span><span class="sxs-lookup"><span data-stu-id="956f8-140">Payroll impact (required)</span></span>
- <span data-ttu-id="956f8-141">Odzyskaj zaległości</span><span class="sxs-lookup"><span data-stu-id="956f8-141">Recover arrears</span></span>
- <span data-ttu-id="956f8-142">Metoda potrącenia</span><span class="sxs-lookup"><span data-stu-id="956f8-142">Deduction method</span></span>
- <span data-ttu-id="956f8-143">Priorytet potrącenia</span><span class="sxs-lookup"><span data-stu-id="956f8-143">Deduction priority</span></span>
- <span data-ttu-id="956f8-144">Okres limitu</span><span class="sxs-lookup"><span data-stu-id="956f8-144">Limit period</span></span>
- <span data-ttu-id="956f8-145">Kwota limitu</span><span class="sxs-lookup"><span data-stu-id="956f8-145">Limit amount</span></span>

##### <a name="benefits"></a><span data-ttu-id="956f8-146">Świadczenia</span><span class="sxs-lookup"><span data-stu-id="956f8-146">Benefits</span></span>

- <span data-ttu-id="956f8-147">Plan (wymagane)</span><span class="sxs-lookup"><span data-stu-id="956f8-147">Plan (required)</span></span>
- <span data-ttu-id="956f8-148">Typ (wymagane)</span><span class="sxs-lookup"><span data-stu-id="956f8-148">Type (required)</span></span>
- <span data-ttu-id="956f8-149">Opcja (wymagane)</span><span class="sxs-lookup"><span data-stu-id="956f8-149">Option (required)</span></span>
- <span data-ttu-id="956f8-150">Identyfikator świadczenia (wymagane)</span><span class="sxs-lookup"><span data-stu-id="956f8-150">Benefit ID (required)</span></span>
- <span data-ttu-id="956f8-151">Częstotliwość</span><span class="sxs-lookup"><span data-stu-id="956f8-151">Frequency</span></span>
- <span data-ttu-id="956f8-152">Podstawa</span><span class="sxs-lookup"><span data-stu-id="956f8-152">Basis</span></span>
- <span data-ttu-id="956f8-153">Kwota lub stawka</span><span class="sxs-lookup"><span data-stu-id="956f8-153">Amount or rate</span></span>
- <span data-ttu-id="956f8-154">Kod zarobków</span><span class="sxs-lookup"><span data-stu-id="956f8-154">Earning code</span></span>

##### <a name="supported-frequencies"></a><span data-ttu-id="956f8-155">Obsługiwane częstotliwości</span><span class="sxs-lookup"><span data-stu-id="956f8-155">Supported frequencies</span></span> 

- <span data-ttu-id="956f8-156">Tygodniowa</span><span class="sxs-lookup"><span data-stu-id="956f8-156">Weekly</span></span>
- <span data-ttu-id="956f8-157">Co dwa tygodnie</span><span class="sxs-lookup"><span data-stu-id="956f8-157">Bi-weekly</span></span>
- <span data-ttu-id="956f8-158">Co pół miesiąca</span><span class="sxs-lookup"><span data-stu-id="956f8-158">Semi-monthly</span></span>
- <span data-ttu-id="956f8-159">Miesięczne</span><span class="sxs-lookup"><span data-stu-id="956f8-159">Monthly</span></span>

##### <a name="supported-bases"></a><span data-ttu-id="956f8-160">Obsługiwane podstawy</span><span class="sxs-lookup"><span data-stu-id="956f8-160">Supported bases</span></span> 

- <span data-ttu-id="956f8-161">Stała kwota</span><span class="sxs-lookup"><span data-stu-id="956f8-161">Fixed amount</span></span>
- <span data-ttu-id="956f8-162">Procent zarobków</span><span class="sxs-lookup"><span data-stu-id="956f8-162">Percent of earnings</span></span>
- <span data-ttu-id="956f8-163">Godziny płatne</span><span class="sxs-lookup"><span data-stu-id="956f8-163">Productive hours</span></span>

<span data-ttu-id="956f8-164">System Dayforce tworzy następujące potrącenia w oparciu o wpływ na listę płac zdefiniowany w planie świadczeń.</span><span class="sxs-lookup"><span data-stu-id="956f8-164">Dayforce creates the following deductions, based on the payroll impact that is defined on the benefit plan.</span></span>

| <span data-ttu-id="956f8-165">Wybór w aplikacji Talent</span><span class="sxs-lookup"><span data-stu-id="956f8-165">Selection in Talent</span></span>        | <span data-ttu-id="956f8-166">Wynik w systemie Dayforce</span><span class="sxs-lookup"><span data-stu-id="956f8-166">Result in Dayforce</span></span>                            |
|----------------------------|-----------------------------------------------|
| <span data-ttu-id="956f8-167">None</span><span class="sxs-lookup"><span data-stu-id="956f8-167">None</span></span>                       | <span data-ttu-id="956f8-168">Nie jest tworzone żadne potrącenie</span><span class="sxs-lookup"><span data-stu-id="956f8-168">No deduction is created.</span></span>                      |
| <span data-ttu-id="956f8-169">Tylko potrącenie</span><span class="sxs-lookup"><span data-stu-id="956f8-169">Deduction only</span></span>             | <span data-ttu-id="956f8-170">Jest tworzone potrącenie od pracownika.</span><span class="sxs-lookup"><span data-stu-id="956f8-170">An employee deduction is created.</span></span>             |
| <span data-ttu-id="956f8-171">Tylko udział</span><span class="sxs-lookup"><span data-stu-id="956f8-171">Contribution only</span></span>          | <span data-ttu-id="956f8-172">Jest tworzone potrącenie od pracodawcy.</span><span class="sxs-lookup"><span data-stu-id="956f8-172">An employer deduction is created.</span></span>             |
| <span data-ttu-id="956f8-173">Potrącenie i udział</span><span class="sxs-lookup"><span data-stu-id="956f8-173">Deduction and contribution</span></span> | <span data-ttu-id="956f8-174">Są tworzone potrącenia od pracownika i pracodawcy.</span><span class="sxs-lookup"><span data-stu-id="956f8-174">Employee and employer deductions are created.</span></span> |

<span data-ttu-id="956f8-175">Aby uzyskać więcej informacji o sposobie definiowania programu świadczeń i zarządzania nim, zobacz następujące tematy:</span><span class="sxs-lookup"><span data-stu-id="956f8-175">For more information about how to define and manage a benefits program, see the following topics:</span></span>

- [<span data-ttu-id="956f8-176">Dostarczanie programu świadczeń dla pracowników</span><span class="sxs-lookup"><span data-stu-id="956f8-176">Deliver an employee benefits program</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/deliver-employee-benefits-program)
- [<span data-ttu-id="956f8-177">Tworzenie nowego świadczenia</span><span class="sxs-lookup"><span data-stu-id="956f8-177">Create a new benefit</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/create-new-benefit)
- [<span data-ttu-id="956f8-178">Definiowanie zasad i reguł uprawnień do świadczenia</span><span class="sxs-lookup"><span data-stu-id="956f8-178">Define benefit eligibility rules and policies</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-benefit-eligibility-rules-policies)
- [<span data-ttu-id="956f8-179">Rejestrowanie i usuwanie świadczeń dla pracowników</span><span class="sxs-lookup"><span data-stu-id="956f8-179">Enroll and remove benefits from workers</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-remove-benefits-workers)

#### <a name="compensation"></a><span data-ttu-id="956f8-180">Wynagrodzenie</span><span class="sxs-lookup"><span data-stu-id="956f8-180">Compensation</span></span> 

<span data-ttu-id="956f8-181">Zarządzanie wynagrodzeniami służy do kontrolowania wypłat podstawowego wynagrodzenia i nagród.</span><span class="sxs-lookup"><span data-stu-id="956f8-181">Compensation management is used to control the delivery of base pay and awards.</span></span> <span data-ttu-id="956f8-182">Stałe podstawowe wynagrodzenie pracownika i podwyżki podstawowego wynagrodzenia są kontrolowane przez plany stałych wynagrodzeń.</span><span class="sxs-lookup"><span data-stu-id="956f8-182">An employee's fixed base pay and merit increases are controlled through fixed compensation plans.</span></span> <span data-ttu-id="956f8-183">Płatności motywacyjne, takie jak premie motywacyjne, wypłaty premii, nagrody za wyniki pracy, prawa do nabycia akcji po ustalonej cenie, cesje i nagrody jednorazowe lub okazjonalne są kontrolowane za pomocą systemów wynagrodzeń o zmiennej wysokości.</span><span class="sxs-lookup"><span data-stu-id="956f8-183">The payment of incentive pay, such as bonus payments, performance awards, stock options, and grants, and also one-time awards, are controlled through variable compensation plans.</span></span>

<span data-ttu-id="956f8-184">Program Dayforce wykorzystuje informacje o wynagrodzeniach do obliczania godzinowej lub rocznej stawki pracownika.</span><span class="sxs-lookup"><span data-stu-id="956f8-184">Dayforce uses compensation information to calculate an employee's hourly or annual rate.</span></span> <span data-ttu-id="956f8-185">Określenie systemów stałych wynagrodzeń i konwersji stawek płac jest wymagane.</span><span class="sxs-lookup"><span data-stu-id="956f8-185">Fixed compensation plans and pay rate conversions are required.</span></span> <span data-ttu-id="956f8-186">Pracownicy muszą być skojarzeni z systemem stałych wynagrodzeń.</span><span class="sxs-lookup"><span data-stu-id="956f8-186">Employees must be associated with a fixed compensation plan.</span></span>

<span data-ttu-id="956f8-187">Aby uzyskać więcej informacji o planach wynagrodzeń, zobacz następujące tematy:</span><span class="sxs-lookup"><span data-stu-id="956f8-187">For more information about compensation plans, see the following topics:</span></span>

- [<span data-ttu-id="956f8-188">Tworzenie planów stałych wynagrodzeń</span><span class="sxs-lookup"><span data-stu-id="956f8-188">Create fixed compensation plans</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/create-fixed-compensation-plans)
- [<span data-ttu-id="956f8-189">Tworzenie planów wynagrodzeń o zmiennej wysokości</span><span class="sxs-lookup"><span data-stu-id="956f8-189">Create variable compensation plans</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/create-variable-compensation-plans)
- [<span data-ttu-id="956f8-190">Opracowywanie struktury i planu pensji/wynagrodzeń</span><span class="sxs-lookup"><span data-stu-id="956f8-190">Develop salary/compensation structure and plans</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/develop-salary-compensation-structure-plan)
- [<span data-ttu-id="956f8-191">Przetwarzanie wynagrodzenia</span><span class="sxs-lookup"><span data-stu-id="956f8-191">Process compensation</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/process-compensation)
- [<span data-ttu-id="956f8-192">Definiowanie procesu związanego z wynagrodzeniem i obliczanie wyników</span><span class="sxs-lookup"><span data-stu-id="956f8-192">Define compensation process and calculate results</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-compensation-process-calculate-results)
- [<span data-ttu-id="956f8-193">Zarejestrowanie pracownika w systemie stałych wynagrodzeń</span><span class="sxs-lookup"><span data-stu-id="956f8-193">Enroll an employee in a fixed compensation plan</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-fixed-compensation-plan)
- [<span data-ttu-id="956f8-194">Zarejestrowanie pracownika w systemie wynagrodzeń o zmiennej wysokości</span><span class="sxs-lookup"><span data-stu-id="956f8-194">Enroll an employee in a variable compensation plan</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-variable-compensation-plan)

#### <a name="jobs"></a><span data-ttu-id="956f8-195">Funkcje</span><span class="sxs-lookup"><span data-stu-id="956f8-195">Jobs</span></span> 

<span data-ttu-id="956f8-196">Funkcja to zbiór zadań i obowiązków, które są wymagane od osoby wykonującej funkcję.</span><span class="sxs-lookup"><span data-stu-id="956f8-196">A job is a collection of the tasks and responsibilities that are required of a person who performs a job.</span></span> <span data-ttu-id="956f8-197">Aby uzyskać więcej informacji, zobacz następujące tematy:</span><span class="sxs-lookup"><span data-stu-id="956f8-197">For more information, see the following topics:</span></span>

- [<span data-ttu-id="956f8-198">Konfigurowanie składników funkcji</span><span class="sxs-lookup"><span data-stu-id="956f8-198">Setting up the components of a job</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/create-job)
- [<span data-ttu-id="956f8-199">Definiowanie nowych zadań</span><span class="sxs-lookup"><span data-stu-id="956f8-199">Define new jobs</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-jobs)

##### <a name="positions"></a><span data-ttu-id="956f8-200">Pozycje</span><span class="sxs-lookup"><span data-stu-id="956f8-200">Positions</span></span>

<span data-ttu-id="956f8-201">Pozycja jest pojedynczym wystąpieniem zadania.</span><span class="sxs-lookup"><span data-stu-id="956f8-201">A position is an individual instance of a job.</span></span> <span data-ttu-id="956f8-202">Na przykład stanowisko „Menedżer ds. sprzedaży (Wschód)” jest jednym ze stanowisk skojarzonych z funkcją „Menedżer ds. sprzedaży”.</span><span class="sxs-lookup"><span data-stu-id="956f8-202">For example, the "Sales manager (East)" position is one of the positions that are associated with the "Sales manager" job.</span></span> <span data-ttu-id="956f8-203">Stanowisko istnieje w dziale.</span><span class="sxs-lookup"><span data-stu-id="956f8-203">A position exists in a department.</span></span> <span data-ttu-id="956f8-204">Z każdym stanowiskiem może być skojarzony tylko jeden pracownik.</span><span class="sxs-lookup"><span data-stu-id="956f8-204">Only one worker can be associated with each position.</span></span>

<span data-ttu-id="956f8-205">Podczas konfigurowania stanowisk pamiętaj o następujących danych i konfiguracjach:</span><span class="sxs-lookup"><span data-stu-id="956f8-205">Keep the following data and configuration in mind when you set up positions:</span></span>

- <span data-ttu-id="956f8-206">Stanowisko (wymagane)</span><span class="sxs-lookup"><span data-stu-id="956f8-206">Position (required)</span></span>
- <span data-ttu-id="956f8-207">Opis (wymagane)</span><span class="sxs-lookup"><span data-stu-id="956f8-207">Description (required)</span></span>
- <span data-ttu-id="956f8-208">Funkcja (wymagane)</span><span class="sxs-lookup"><span data-stu-id="956f8-208">Job (required)</span></span>
- <span data-ttu-id="956f8-209">Dział (wymagane)</span><span class="sxs-lookup"><span data-stu-id="956f8-209">Department (required)</span></span>
- <span data-ttu-id="956f8-210">Typ stanowiska (wymagane)</span><span class="sxs-lookup"><span data-stu-id="956f8-210">Position type (required)</span></span>
- <span data-ttu-id="956f8-211">W przeliczeniu na pełne etaty</span><span class="sxs-lookup"><span data-stu-id="956f8-211">Full-time equivalent</span></span>
- <span data-ttu-id="956f8-212">Zwykłe godziny (rocznie) (wymagane)</span><span class="sxs-lookup"><span data-stu-id="956f8-212">Annual regular hours (required)</span></span>
- <span data-ttu-id="956f8-213">Zapłacone przez firmę (wymagane)</span><span class="sxs-lookup"><span data-stu-id="956f8-213">Paid by legal entity (required)</span></span>
- <span data-ttu-id="956f8-214">Cykl kalkulacji płac (wymagane)</span><span class="sxs-lookup"><span data-stu-id="956f8-214">Pay cycle (required)</span></span>
- <span data-ttu-id="956f8-215">Domyślny wymiar finansowy — Centrum kosztu (wymagane)</span><span class="sxs-lookup"><span data-stu-id="956f8-215">Default financial dimension – Cost center (required)</span></span>
- <span data-ttu-id="956f8-216">Przypisanie pracownika — Pracownik, rozpoczęcie przypisania, zakończenia przypisania, kod przyczyny</span><span class="sxs-lookup"><span data-stu-id="956f8-216">Worker assignment – Worker, assignment start, assignment end, reason code</span></span>

<span data-ttu-id="956f8-217">Jeśli z tą samą funkcją jest skojarzonych wiele stanowisk w tym samym dziale, są one konsolidowane w jedno stanowisko w systemie Dayforce.</span><span class="sxs-lookup"><span data-stu-id="956f8-217">If multiple positions in the same department are associated with the same job, they are consolidated into a single position in Dayforce.</span></span>

<span data-ttu-id="956f8-218">Aby uzyskać więcej informacji, zobacz następujące tematy:</span><span class="sxs-lookup"><span data-stu-id="956f8-218">For more information, see the following topics:</span></span>

- [<span data-ttu-id="956f8-219">Organizowanie pracowników za pomocą działów, funkcji i stanowisk</span><span class="sxs-lookup"><span data-stu-id="956f8-219">Organize your workforce using departments, jobs, and positions</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/departments-jobs-positions#positions)
- [<span data-ttu-id="956f8-220">Konfigurowanie stanowisk</span><span class="sxs-lookup"><span data-stu-id="956f8-220">Set up positions</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/set-up-positions)

#### <a name="departments"></a><span data-ttu-id="956f8-221">Działy</span><span class="sxs-lookup"><span data-stu-id="956f8-221">Departments</span></span>

<span data-ttu-id="956f8-222">Dział to jednostka operacyjna należąca do kategorii lub obszaru funkcjonalnego organizacji.</span><span class="sxs-lookup"><span data-stu-id="956f8-222">A department is an operating unit that represents a category or functional area of an organization.</span></span> <span data-ttu-id="956f8-223">Dział jest odpowiedzialny za określony obszar organizacji, np. sprzedaż, księgowość lub zasoby ludzkie.</span><span class="sxs-lookup"><span data-stu-id="956f8-223">A department is responsible for a specific area of the organization, such as sales, accounting, or human resources.</span></span> <span data-ttu-id="956f8-224">Działy pozwalają tworzyć raporty dotyczące obszarów funkcyjnych.</span><span class="sxs-lookup"><span data-stu-id="956f8-224">You can use departments to report on functional areas.</span></span> <span data-ttu-id="956f8-225">Działy mogą mieć odpowiedzialność zysków i strat.</span><span class="sxs-lookup"><span data-stu-id="956f8-225">Departments might have profit and loss responsibility.</span></span>

<span data-ttu-id="956f8-226">Aby uzyskać więcej informacji, zobacz następujące tematy:</span><span class="sxs-lookup"><span data-stu-id="956f8-226">For more information, see the following topics:</span></span>

- [<span data-ttu-id="956f8-227">Tworzenie działu i kojarzenie go z hierarchią działów</span><span class="sxs-lookup"><span data-stu-id="956f8-227">Create a department and associate it with the department hierarchy</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/create-department-add-department-hierarchy)
- [<span data-ttu-id="956f8-228">Definiowanie nowych działów</span><span class="sxs-lookup"><span data-stu-id="956f8-228">Define new departments</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-departments)

#### <a name="pay-cycles-and-pay-periods"></a><span data-ttu-id="956f8-229">Cykle płac i okresy płac</span><span class="sxs-lookup"><span data-stu-id="956f8-229">Pay cycles and pay periods</span></span>

<span data-ttu-id="956f8-230">Cykl kalkulacji płac decyduje o częstotliwości wykonywania sesji obliczania listy płac oraz o konkretnych dniach, kiedy pracownicy otrzymują zapłatę.</span><span class="sxs-lookup"><span data-stu-id="956f8-230">A pay cycle determines how often payroll is run and the specific days when workers are paid.</span></span> <span data-ttu-id="956f8-231">Na przykład cykl kalkulacji płac może być miesięczny, a pracownicy mogą otrzymywać wypłatę w ostatnim dniu miesiąca.</span><span class="sxs-lookup"><span data-stu-id="956f8-231">For example, a pay cycle might be monthly, and employees might be paid on the last day of the month.</span></span> <span data-ttu-id="956f8-232">Alternatywnie cykl kalkulacji płac może być tygodniowy, a pracownicy dostają wypłatę w każdy wtorek po zakończeniu okresu kalkulacji płac.</span><span class="sxs-lookup"><span data-stu-id="956f8-232">Alternatively, a pay cycle might be weekly, and employees might be paid on the Tuesday after the end of the pay period.</span></span> <span data-ttu-id="956f8-233">Cykle kalkulacji płac są przypisywane do stanowisk w celu kontrolowania, kiedy pracownicy na tych stanowiskach otrzymują zapłatę.</span><span class="sxs-lookup"><span data-stu-id="956f8-233">Pay cycles are assigned to positions to control when workers in those positions are paid.</span></span>

<span data-ttu-id="956f8-234">Po utworzeniu cykli kalkulacji płac można wygenerować okresy kalkulacji płac dla każdego cyklu.</span><span class="sxs-lookup"><span data-stu-id="956f8-234">After you create pay cycles, you can generate pay periods for each cycle.</span></span> <span data-ttu-id="956f8-235">Każdy okres kalkulacji płac zawiera domyślną datę płatności, która bazuje na podanych przez Ciebie informacjach.</span><span class="sxs-lookup"><span data-stu-id="956f8-235">Each pay period includes a default payment date that is based on information that you provide.</span></span> <span data-ttu-id="956f8-236">Można jednak zmodyfikować domyślną datę płatności w okresie kalkulacji płac, co pozwala stosować wyjątki, np. gdy data płatności przypada na dzień wolny od pracy.</span><span class="sxs-lookup"><span data-stu-id="956f8-236">However, you can modify the default payment date in a pay period to allow for exceptions, such as when the payment date falls on a holiday.</span></span>

<span data-ttu-id="956f8-237">Poniższe informacje są używane w programie Dayforce:</span><span class="sxs-lookup"><span data-stu-id="956f8-237">The following information is used in Dayforce:</span></span>

- <span data-ttu-id="956f8-238">Cykl kalkulacji płac (wymagane)</span><span class="sxs-lookup"><span data-stu-id="956f8-238">Pay cycle (required)</span></span>
- <span data-ttu-id="956f8-239">Częstotliwość cyklu kalkulacji płac (wymagane)</span><span class="sxs-lookup"><span data-stu-id="956f8-239">Pay cycle frequency (required)</span></span>
- <span data-ttu-id="956f8-240">Data rozpoczęcia okresu (pierwszy okres kalkulacji płac jest wymagany)</span><span class="sxs-lookup"><span data-stu-id="956f8-240">Period start date (first pay period required)</span></span>
- <span data-ttu-id="956f8-241">Domyślna data płatności (pierwszy okres kalkulacji płac jest wymagany)</span><span class="sxs-lookup"><span data-stu-id="956f8-241">Default payment date (first pay period required)</span></span>

<span data-ttu-id="956f8-242">Te informacje są integrowane z usługą Dayforce jako grupy płac oraz dzielone na kraje lub regiony dla każdego cyklu kalkulacji płac.</span><span class="sxs-lookup"><span data-stu-id="956f8-242">This information is integrated with Dayforce as pay groups, and is separated by country or region for each pay cycle.</span></span> <span data-ttu-id="956f8-243">Przed integracją musi być wygenerowany co najmniej jeden okres kalkulacji płac.</span><span class="sxs-lookup"><span data-stu-id="956f8-243">At least one pay period must be generated before integration.</span></span> <span data-ttu-id="956f8-244">System Dayforce generuje kalendarze grup płac i daty płatności na podstawie daty rozpoczęcia pierwszego okresu kalkulacji płac i domyślnej daty płatności ustawionej w aplikacji Talent.</span><span class="sxs-lookup"><span data-stu-id="956f8-244">Dayforce generates pay group calendars and payment dates, based on the start date of the first pay period and the default payment date that is set up in Talent.</span></span>

#### <a name="earning-codes"></a><span data-ttu-id="956f8-245">Kody zarobków</span><span class="sxs-lookup"><span data-stu-id="956f8-245">Earning codes</span></span>

<span data-ttu-id="956f8-246">Kody zarobków jednoznacznie identyfikują każdy rodzaj dochodów, które otrzymują pracownicy.</span><span class="sxs-lookup"><span data-stu-id="956f8-246">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="956f8-247">Kody mają różne parametry związane z zarobkami, takie jak reguły księgowania, przepisy podatkowe, wymagania dotyczące raportowania i możliwość zwiększania wartości brutto.</span><span class="sxs-lookup"><span data-stu-id="956f8-247">The codes have various parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span>

<span data-ttu-id="956f8-248">Poniższe informacje są używane w programie Dayforce:</span><span class="sxs-lookup"><span data-stu-id="956f8-248">The following information is used in Dayforce:</span></span>

- <span data-ttu-id="956f8-249">Kod zarobków (wymagane)</span><span class="sxs-lookup"><span data-stu-id="956f8-249">Earning Code (required)</span></span>
- <span data-ttu-id="956f8-250">opis</span><span class="sxs-lookup"><span data-stu-id="956f8-250">Description</span></span>
- <span data-ttu-id="956f8-251">Jednostka miary</span><span class="sxs-lookup"><span data-stu-id="956f8-251">Unit of measure</span></span>
- <span data-ttu-id="956f8-252">Płatne</span><span class="sxs-lookup"><span data-stu-id="956f8-252">Productive</span></span>

### <a name="worker-data"></a><span data-ttu-id="956f8-253">Dane pracowników</span><span class="sxs-lookup"><span data-stu-id="956f8-253">Worker data</span></span>

<span data-ttu-id="956f8-254">Dokumenty o różnych typach posiadanych pracowników są ważne dla informatycznych systemów kadrowych i płacowych.</span><span class="sxs-lookup"><span data-stu-id="956f8-254">Records for the various types of workers that you have are important to your human resources and payroll systems.</span></span> <span data-ttu-id="956f8-255">Wprowadzone informacje mogą służyć do monitorowania pracowników i danych osobowych.</span><span class="sxs-lookup"><span data-stu-id="956f8-255">The information that you enter can be used to track workers and personal information.</span></span>

<span data-ttu-id="956f8-256">Można przechowywać następujące informacje o pracownikach:</span><span class="sxs-lookup"><span data-stu-id="956f8-256">You can maintain the following information for workers:</span></span>

- <span data-ttu-id="956f8-257">**Podstawowe** — Podstawowe informacje o pracowniku, takie jak dane kontaktowe, demograficzne, identyfikacyjne, informacje o rodzinie, stosunek do służby wojskowej, status emigranta oraz dane kontaktowe dla nagłych wypadków.</span><span class="sxs-lookup"><span data-stu-id="956f8-257">**Basic** – Maintain basic information about a worker, such as contact information, demographic information, identification information, family information, military service status, expatriate information, and personal and emergency contacts.</span></span>
- <span data-ttu-id="956f8-258">**Zatrudnienie** — Informacje o zatrudnieniu pracownika, takie jak przynależność do firmy lub organizacji, przypisanie stanowiska, daty rozpoczęcia i zakończenia, prawo do zatrudnienia, warunki zatrudnienia, emerytura, urlop i informacje o przeniesieniu.</span><span class="sxs-lookup"><span data-stu-id="956f8-258">**Employment** – Maintain information about a worker's employment, such as company or organization affiliation, position assignment, start and end dates, work eligibility, terms of employment, pension, vacation, and relocation information.</span></span>
- <span data-ttu-id="956f8-259">**Urlopy i nieobecności** — Informacje o nieobecności pracownika, takie jak kalendarze pracy, transakcje nieobecności i ustawienia nieobecności.</span><span class="sxs-lookup"><span data-stu-id="956f8-259">**Leave and absence** – Maintain information about a worker's absences, such as working calendars, absence transactions, and absence setup.</span></span>
- <span data-ttu-id="956f8-260">**Wynagrodzenia i płace** — Informacje o planach wynagrodzeń i płacach pracownika, takie jak rejestracja w planie, nagrody, wydajność, prowizje, informacje podatkowe, odejście na emeryturę i potrącenia z wynagrodzenia.</span><span class="sxs-lookup"><span data-stu-id="956f8-260">**Compensation and payroll** – Maintain information about a worker's compensation plans and payroll information, such as plan enrollment, awards, performance, commission, tax information, retirement, and salary deductions.</span></span>

<span data-ttu-id="956f8-261">Podczas wprowadzania danych pracownika należy wziąć pod uwagę następujące dane i konfiguracje używane w programie Dayforce.</span><span class="sxs-lookup"><span data-stu-id="956f8-261">When you enter worker information, keep in mind the following data and configurations that are used in Dayforce.</span></span>

#### <a name="general-information"></a><span data-ttu-id="956f8-262">Informacje ogólne</span><span class="sxs-lookup"><span data-stu-id="956f8-262">General information</span></span>

- <span data-ttu-id="956f8-263">Numer pracownika (wymagane)</span><span class="sxs-lookup"><span data-stu-id="956f8-263">Personnel number (required)</span></span>
- <span data-ttu-id="956f8-264">Imię (wymagane)</span><span class="sxs-lookup"><span data-stu-id="956f8-264">First name (required)</span></span>
- <span data-ttu-id="956f8-265">Nazwisko (wymagane)</span><span class="sxs-lookup"><span data-stu-id="956f8-265">Last name (required)</span></span>
- <span data-ttu-id="956f8-266">Drugie imię</span><span class="sxs-lookup"><span data-stu-id="956f8-266">Middle name</span></span>
- <span data-ttu-id="956f8-267">Data stażu pracy</span><span class="sxs-lookup"><span data-stu-id="956f8-267">Seniority date</span></span>
- <span data-ttu-id="956f8-268">Znane jako</span><span class="sxs-lookup"><span data-stu-id="956f8-268">Known as</span></span>

#### <a name="personal-information"></a><span data-ttu-id="956f8-269">Informacje osobiste</span><span class="sxs-lookup"><span data-stu-id="956f8-269">Personal information</span></span>

- <span data-ttu-id="956f8-270">Stan cywilny (wymagane)</span><span class="sxs-lookup"><span data-stu-id="956f8-270">Marital status (required)</span></span>
- <span data-ttu-id="956f8-271">Data urodzenia (wymagane)</span><span class="sxs-lookup"><span data-stu-id="956f8-271">Birth date (required)</span></span>
- <span data-ttu-id="956f8-272">Płeć (wymagane)</span><span class="sxs-lookup"><span data-stu-id="956f8-272">Gender (required)</span></span>
- <span data-ttu-id="956f8-273">Osoba niepełnosprawna</span><span class="sxs-lookup"><span data-stu-id="956f8-273">Person with disabilities</span></span>
- <span data-ttu-id="956f8-274">Obywatelstwo (kraj/region) (tylko w przypadku Meksyku)</span><span class="sxs-lookup"><span data-stu-id="956f8-274">Nationality country region (only for Mexico)</span></span>

#### <a name="address-information"></a><span data-ttu-id="956f8-275">Informacje adresowe</span><span class="sxs-lookup"><span data-stu-id="956f8-275">Address information</span></span>

- <span data-ttu-id="956f8-276">Podstawowy (wymagane)</span><span class="sxs-lookup"><span data-stu-id="956f8-276">Primary (required)</span></span>
- <span data-ttu-id="956f8-277">Kraj/region (wymagane)</span><span class="sxs-lookup"><span data-stu-id="956f8-277">Country/region (required)</span></span>
- <span data-ttu-id="956f8-278">Kod pocztowy (wymagane)</span><span class="sxs-lookup"><span data-stu-id="956f8-278">Postal code (required)</span></span>
- <span data-ttu-id="956f8-279">Numer domu (wymagane) (jedynie w przypadku Meksyku)</span><span class="sxs-lookup"><span data-stu-id="956f8-279">Street Number (required) (Only for Mexico)</span></span>
- <span data-ttu-id="956f8-280">Dodatkowe określenie budynku (tylko w przypadku Meksyku)</span><span class="sxs-lookup"><span data-stu-id="956f8-280">Building Complement (Only for Mexico)</span></span>
- <span data-ttu-id="956f8-281">Miejscowość (wymagane)</span><span class="sxs-lookup"><span data-stu-id="956f8-281">City (required)</span></span>
- <span data-ttu-id="956f8-282">Województwo (wymagane)</span><span class="sxs-lookup"><span data-stu-id="956f8-282">State (required)</span></span>
- <span data-ttu-id="956f8-283">Powiat (wymagane)</span><span class="sxs-lookup"><span data-stu-id="956f8-283">County (required)</span></span>

#### <a name="contact-information"></a><span data-ttu-id="956f8-284">Informacje o kontakcie</span><span class="sxs-lookup"><span data-stu-id="956f8-284">Contact information</span></span> 

- <span data-ttu-id="956f8-285">Podstawowy (wymagane)</span><span class="sxs-lookup"><span data-stu-id="956f8-285">Primary (required)</span></span>
- <span data-ttu-id="956f8-286">Nazwa osoby kontaktowej (wymagane)</span><span class="sxs-lookup"><span data-stu-id="956f8-286">Contact number (required)</span></span>
- <span data-ttu-id="956f8-287">Wewnętrzny</span><span class="sxs-lookup"><span data-stu-id="956f8-287">Extension</span></span>

#### <a name="payroll-information-and-earning-codes"></a><span data-ttu-id="956f8-288">Informacje płacowe i kody zarobków</span><span class="sxs-lookup"><span data-stu-id="956f8-288">Payroll information and earning codes</span></span>

<span data-ttu-id="956f8-289">Pracownicy mogą mieć przypisane określone zarobki z określoną częstotliwością wypłat oraz mieć ustawioną preferowaną metodę płatności.</span><span class="sxs-lookup"><span data-stu-id="956f8-289">Employees may be assigned specific earnings at a given frequency of payment and have a preferred payment method.</span></span> <span data-ttu-id="956f8-290">Następujące pola są używane w usłudze Dayforce w celu zagwarantowania, że te ustawienia i preferencje są wykorzystywane.</span><span class="sxs-lookup"><span data-stu-id="956f8-290">The following fields are used in Dayforce to help guarantee that those preferences and settings are used.</span></span>

##### <a name="earning-codes"></a><span data-ttu-id="956f8-291">Kody zarobków</span><span class="sxs-lookup"><span data-stu-id="956f8-291">Earning codes</span></span>

- <span data-ttu-id="956f8-292">Stanowisko (wymagane)</span><span class="sxs-lookup"><span data-stu-id="956f8-292">Position (required)</span></span>
- <span data-ttu-id="956f8-293">Kod zarobków (wymagane)</span><span class="sxs-lookup"><span data-stu-id="956f8-293">Earning Code (required)</span></span>
- <span data-ttu-id="956f8-294">Częstotliwość (wymagane)</span><span class="sxs-lookup"><span data-stu-id="956f8-294">Frequency (required)</span></span>
- <span data-ttu-id="956f8-295">Kwota (wymagane)</span><span class="sxs-lookup"><span data-stu-id="956f8-295">Amount (required)</span></span>

##### <a name="payroll-information"></a><span data-ttu-id="956f8-296">Informacje listy płac</span><span class="sxs-lookup"><span data-stu-id="956f8-296">Payroll information</span></span>

- <span data-ttu-id="956f8-297">Metoda płatności</span><span class="sxs-lookup"><span data-stu-id="956f8-297">Payment Method</span></span>
- <span data-ttu-id="956f8-298">Region gospodarczy (wymagane)</span><span class="sxs-lookup"><span data-stu-id="956f8-298">Economic Region (required)</span></span>
- <span data-ttu-id="956f8-299">Identyfikator świadczeń pracownika etatowego</span><span class="sxs-lookup"><span data-stu-id="956f8-299">Employee Benefits ID</span></span>
- <span data-ttu-id="956f8-300">Numer dowodu osobistego (wymagane)</span><span class="sxs-lookup"><span data-stu-id="956f8-300">National ID Number (required)</span></span>
- <span data-ttu-id="956f8-301">Numer książeczki wojskowej</span><span class="sxs-lookup"><span data-stu-id="956f8-301">Military Service Number</span></span>
- <span data-ttu-id="956f8-302">Identyfikator zmiany (wymagane)</span><span class="sxs-lookup"><span data-stu-id="956f8-302">Shift ID (required)</span></span>
- <span data-ttu-id="956f8-303">Numer identyfikacji podatkowej (wymagane)</span><span class="sxs-lookup"><span data-stu-id="956f8-303">Tax Number (required)</span></span>
- <span data-ttu-id="956f8-304">Identyfikator związku (wymagane)</span><span class="sxs-lookup"><span data-stu-id="956f8-304">Union ID (required)</span></span>
- <span data-ttu-id="956f8-305">Identyfikator dnia roboczego (wymagane)</span><span class="sxs-lookup"><span data-stu-id="956f8-305">Work Day ID (required)</span></span>
- <span data-ttu-id="956f8-306">Numer pozwolenia na pracę</span><span class="sxs-lookup"><span data-stu-id="956f8-306">Work Permit Number</span></span>

> [!NOTE]
> <span data-ttu-id="956f8-307">W Meksyku obsługiwane metody płatności to **Gotówka**, **Czek** (fizyczny czek wystawiany przez firmę) i **Płatność elektroniczna**.</span><span class="sxs-lookup"><span data-stu-id="956f8-307">For the payment method, Mexico supports **Cash**, **Check** (the company's physical check), and **Electronic Payment**.</span></span> <span data-ttu-id="956f8-308">Jeśli metoda płatności nie zostanie określona, domyślnie będzie używana metoda **Czek**.</span><span class="sxs-lookup"><span data-stu-id="956f8-308">If np payment method is specified, **Check** is used by default.</span></span>

#### <a name="employment-details"></a><span data-ttu-id="956f8-309">Szczegóły zatrudnienia</span><span class="sxs-lookup"><span data-stu-id="956f8-309">Employment details</span></span>

<span data-ttu-id="956f8-310">Historia szczegółów zatrudnienia pełni rolę kluczowych informacji przy ustalaniu statusów zatrudnienia, zwolnienia i ponownego zatrudnienia pracownika etatowego w systemie Dayforce.</span><span class="sxs-lookup"><span data-stu-id="956f8-310">Employment detail history is used as key information to derive an employee's hire, termination, and rehire statuses in Dayforce.</span></span> <span data-ttu-id="956f8-311">W rozwiązaniu Dayforce może istnieć tylko jeden aktywny rekord zatrudnienia na raz.</span><span class="sxs-lookup"><span data-stu-id="956f8-311">Dayforce supports only one active employment record at a time.</span></span>

- <span data-ttu-id="956f8-312">Data rozpoczęcia zatrudnienia (wymagane)</span><span class="sxs-lookup"><span data-stu-id="956f8-312">Employment start date (required)</span></span>
- <span data-ttu-id="956f8-313">Data zakończenia zatrudnienia</span><span class="sxs-lookup"><span data-stu-id="956f8-313">Employment end date</span></span>
- <span data-ttu-id="956f8-314">Rozpoczęcie</span><span class="sxs-lookup"><span data-stu-id="956f8-314">Start date</span></span>
- <span data-ttu-id="956f8-315">Dopasowana data rozpoczęcia.</span><span class="sxs-lookup"><span data-stu-id="956f8-315">Adjusted start date</span></span>
- <span data-ttu-id="956f8-316">Data zakończenia (wymagane po rozwiązaniu stosunku pracy)</span><span class="sxs-lookup"><span data-stu-id="956f8-316">Termination date (required upon termination)</span></span>
- <span data-ttu-id="956f8-317">Powód rozwiązania umowy (wymagane po rozwiązaniu stosunku pracy)</span><span class="sxs-lookup"><span data-stu-id="956f8-317">Termination reason (required upon termination)</span></span>

<span data-ttu-id="956f8-318">Kluczowe daty pracownika są obliczane na podstawie następujących informacji.</span><span class="sxs-lookup"><span data-stu-id="956f8-318">An employee's key dates are derived by using the following information.</span></span>

| <span data-ttu-id="956f8-319">Talent</span><span class="sxs-lookup"><span data-stu-id="956f8-319">Talent</span></span>                | <span data-ttu-id="956f8-320">Dayforce</span><span class="sxs-lookup"><span data-stu-id="956f8-320">Dayforce</span></span>                                                                                             |
|-----------------------|------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="956f8-321">Ostatnia data zatrudnienia</span><span class="sxs-lookup"><span data-stu-id="956f8-321">Most recent hire date</span></span> | <span data-ttu-id="956f8-322">Rozpoczęcie pracy w bieżącym rekordzie historii niezakończonego zatrudnienia</span><span class="sxs-lookup"><span data-stu-id="956f8-322">Employment start of current non-terminated employment history record</span></span>                                 |
| <span data-ttu-id="956f8-323">Data zakończenia</span><span class="sxs-lookup"><span data-stu-id="956f8-323">Termination date</span></span>      | <span data-ttu-id="956f8-324">Data zakończenia zatrudnienia w bieżącym rekordzie historii niezakończonego zatrudnienia</span><span class="sxs-lookup"><span data-stu-id="956f8-324">Termination date of current non-terminated employment history record</span></span>                                 |
| <span data-ttu-id="956f8-325">Rozpoczęcie</span><span class="sxs-lookup"><span data-stu-id="956f8-325">Start date</span></span>            | <span data-ttu-id="956f8-326">Skorygowana data rozpoczęcia, data rozpoczęcia lub rozpoczęcie zatrudnienia w bieżącym rekordzie historii nieaktywnego zatrudnienia</span><span class="sxs-lookup"><span data-stu-id="956f8-326">Adjusted start date, start date, or employment start of current non-active employment history record</span></span> |
| <span data-ttu-id="956f8-327">Pierwotna data zatrudnienia</span><span class="sxs-lookup"><span data-stu-id="956f8-327">Original hire date</span></span>    | <span data-ttu-id="956f8-328">Rozpoczęcie zatrudnienia w najwcześniejszym rekordzie historii zatrudnienia</span><span class="sxs-lookup"><span data-stu-id="956f8-328">Employment start of earliest employment history record</span></span>                                               |

#### <a name="compensation"></a><span data-ttu-id="956f8-329">Wynagrodzenie</span><span class="sxs-lookup"><span data-stu-id="956f8-329">Compensation</span></span>

<span data-ttu-id="956f8-330">Plan stałych wynagrodzeń musi być skojarzony z podstawowym stanowiskiem każdego pracownika w okresie zatrudnienia.</span><span class="sxs-lookup"><span data-stu-id="956f8-330">A fixed compensation plan must be associated with every employee's primary position throughout an employment period.</span></span> <span data-ttu-id="956f8-331">Okres ten rozpoczyna się w dniu zatrudnienia pracownika (lub rozpoczęcia zatrudnienia) i trwa do momentu zakończenia zatrudnienia.</span><span class="sxs-lookup"><span data-stu-id="956f8-331">This period starts on the date that the employee was hired (or the employment start date) and continues until termination.</span></span>

- <span data-ttu-id="956f8-332">Data obowiązywania (wymagane)</span><span class="sxs-lookup"><span data-stu-id="956f8-332">Effective Date (required)</span></span>
- <span data-ttu-id="956f8-333">Data ważności</span><span class="sxs-lookup"><span data-stu-id="956f8-333">Expiration date</span></span>
- <span data-ttu-id="956f8-334">Stawka płacy (wymagane)</span><span class="sxs-lookup"><span data-stu-id="956f8-334">Pay Rate (required)</span></span>
- <span data-ttu-id="956f8-335">Konwersje stawek płacy (wymagane)</span><span class="sxs-lookup"><span data-stu-id="956f8-335">Pay Rate Conversions (required)</span></span>
- <span data-ttu-id="956f8-336">Równowartość roczna (wymagane)</span><span class="sxs-lookup"><span data-stu-id="956f8-336">Annual equivalent (required)</span></span>
- <span data-ttu-id="956f8-337">Równowartość godzinowa (wymagane)</span><span class="sxs-lookup"><span data-stu-id="956f8-337">Hourly equivalent (required)</span></span>

<span data-ttu-id="956f8-338">Jeśli pracownik rozliczany godzinowo zajmuje kilka stanowisk, stałe wynagrodzenie na podstawowym stanowisku jest importowane do systemu Dayforce jako podstawowa stawka/wynagrodzenie na poziomie pracownika.</span><span class="sxs-lookup"><span data-stu-id="956f8-338">If an hourly employee has multiple positions, the fixed compensation of the primary position is imported into Dayforce as the employee-level base rate/salary.</span></span> <span data-ttu-id="956f8-339">Dla stanowisk dodatkowych stawka godzinowa jest zapisywana na odpowiednich stanowiskach w usłudze Dayforce.</span><span class="sxs-lookup"><span data-stu-id="956f8-339">For non-primary positions, the hourly rate is saved to the corresponding position in Dayforce.</span></span>

<span data-ttu-id="956f8-340">Jeśli pracownik na stawce stałej zajmuje kilka stanowisk, skumulowana stawka godzinowa i roczne wynagrodzenie ze wszystkich aktywnych stanowisk są używane jako podstawowa stawka/wynagrodzenie na poziomie pracownika.</span><span class="sxs-lookup"><span data-stu-id="956f8-340">If a salaried employee has multiple positions, the cumulative hour rate and annual salary across all active positions are derived and used as the employee-level base rate/salary.</span></span>

#### <a name="identification-numbers"></a><span data-ttu-id="956f8-341">Numery identyfikacyjne</span><span class="sxs-lookup"><span data-stu-id="956f8-341">Identification numbers</span></span>

##### <a name="social-security-identifier"></a><span data-ttu-id="956f8-342">Numer ubezpieczenia społecznego</span><span class="sxs-lookup"><span data-stu-id="956f8-342">Social Security identifier</span></span> 

<span data-ttu-id="956f8-343">Każdy pracownik musi mieć jeden identyfikator podstawowy.</span><span class="sxs-lookup"><span data-stu-id="956f8-343">Every employee must have one primary identifier.</span></span> <span data-ttu-id="956f8-344">Identyfikator ten musi być typu **PESEL**.</span><span class="sxs-lookup"><span data-stu-id="956f8-344">This identifier must be of **SSN** identification type.</span></span> <span data-ttu-id="956f8-345">W systemie Dayforce jest on automatycznie interpretowany jako numer ubezpieczenia społecznego wymagany w celu zatrudnienia.</span><span class="sxs-lookup"><span data-stu-id="956f8-345">In Dayforce, it's automatically derived as the employee's Social Security identifier that is required for hire.</span></span>

- <span data-ttu-id="956f8-346">Podstawowy (wymagane)</span><span class="sxs-lookup"><span data-stu-id="956f8-346">Primary (required)</span></span>
- <span data-ttu-id="956f8-347">Typ identyfikacji = „PESEL”</span><span class="sxs-lookup"><span data-stu-id="956f8-347">Identification Type = "SSN"</span></span>
- <span data-ttu-id="956f8-348">Data wystawienia</span><span class="sxs-lookup"><span data-stu-id="956f8-348">Issued Date</span></span>
- <span data-ttu-id="956f8-349">Data ważności</span><span class="sxs-lookup"><span data-stu-id="956f8-349">Expiration Date</span></span>

<span data-ttu-id="956f8-350">Pracownicy mogą zadeklarować wiele numerów identyfikacyjnych typu **PESEL**.</span><span class="sxs-lookup"><span data-stu-id="956f8-350">Employees can declare multiple identification numbers of the **SSN** identification type.</span></span> <span data-ttu-id="956f8-351">Jednak tylko rekord oznaczony jako **Podstawowy** jest integrowany z rozwiązaniem Dayforce, niezależnie od tego, czy jest on aktywny, czy wygasły.</span><span class="sxs-lookup"><span data-stu-id="956f8-351">However, only the record that is marked as **Primary** is integrated into Dayforce, regardless of whether the number is active or expired.</span></span>

#### <a name="bank-accounts-and-disbursements"></a><span data-ttu-id="956f8-352">Konta bankowe i wypłaty</span><span class="sxs-lookup"><span data-stu-id="956f8-352">Bank accounts and disbursements</span></span>

<span data-ttu-id="956f8-353">Dla każdego pracownika, który wybrał opcję otrzymywania wynagrodzenia przelewami na rachunek bankowy, należy wprowadzić prawidłowe dane konta bankowego.</span><span class="sxs-lookup"><span data-stu-id="956f8-353">Valid bank account information must be entered for any employee who chooses to be paid via bank account transfers.</span></span>

| <span data-ttu-id="956f8-354">Talent</span><span class="sxs-lookup"><span data-stu-id="956f8-354">Talent</span></span>                         | <span data-ttu-id="956f8-355">Dayforce</span><span class="sxs-lookup"><span data-stu-id="956f8-355">Dayforce</span></span>                                                                                                    |
|--------------------------------|-------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="956f8-356">Numer konta bankowego (wymagane)</span><span class="sxs-lookup"><span data-stu-id="956f8-356">Bank account number (required)</span></span> |                                                                                                             |
| <span data-ttu-id="956f8-357">Kod SWIFT (wymagane)</span><span class="sxs-lookup"><span data-stu-id="956f8-357">SWIFT code (required)</span></span>          | <span data-ttu-id="956f8-358">Pole **Identyfikator banku** używane w trakcie przetwarzania listy płac w Meksyku.</span><span class="sxs-lookup"><span data-stu-id="956f8-358">**Bank ID** field used when processing payroll in Mexico.</span></span>                                                             |
| <span data-ttu-id="956f8-359">Numer oddziału (wymagane)</span><span class="sxs-lookup"><span data-stu-id="956f8-359">Branch number (required)</span></span>       |                                                                                                             |
| <span data-ttu-id="956f8-360">Typ konta bankowego (wymagane)</span><span class="sxs-lookup"><span data-stu-id="956f8-360">Bank account type (required)</span></span>   | <span data-ttu-id="956f8-361">Pole **Typ konta** używane w trakcie przetwarzania listy płac w Meksyku.</span><span class="sxs-lookup"><span data-stu-id="956f8-361">**Account type** field used when processing payroll in Mexico.</span></span> <span data-ttu-id="956f8-362">Obsługiwane wartości **Czekowe** i **Lista płac**.</span><span class="sxs-lookup"><span data-stu-id="956f8-362">Supported values include **Checking** and **Payroll**.</span></span> |

> [!NOTE]
> <span data-ttu-id="956f8-363">Pracownicy, którzy wybiorą otrzymywanie wynagrodzeń przelewami na rachunki bankowe, muszą podać łącze do konta pozostałości, które należy do firmy mającej podstawowy adres w Meksyku i jest skojarzone z prawidłowym kontem bankowym w meksykańskim banku.</span><span class="sxs-lookup"><span data-stu-id="956f8-363">Employees who choose to be paid via bank account transfers must provide a link to a remainder account that is under a legal entity that has its primary address in Mexico and associated with a valid bank account from a Mexican bank.</span></span> <span data-ttu-id="956f8-364">Wszystkie inne konta pozostałości są ignorowane.</span><span class="sxs-lookup"><span data-stu-id="956f8-364">All other non-remainder accounts are ignored.</span></span>

#### <a name="address-information"></a><span data-ttu-id="956f8-365">Informacje adresowe</span><span class="sxs-lookup"><span data-stu-id="956f8-365">Address information</span></span>

<span data-ttu-id="956f8-366">Każdy pracownik musi mieć jedną lokalizację podstawową.</span><span class="sxs-lookup"><span data-stu-id="956f8-366">Every employee must have one primary location.</span></span> <span data-ttu-id="956f8-367">W systemie Dayforce ta lokalizacja jest używana do określenia głównego miejsca zamieszkania pracownika w celach podatkowych.</span><span class="sxs-lookup"><span data-stu-id="956f8-367">In Dayforce, this location is used to determine the employee's primary residence for tax purposes.</span></span>

- <span data-ttu-id="956f8-368">Podstawowy (wymagane)</span><span class="sxs-lookup"><span data-stu-id="956f8-368">Primary (required)</span></span>
- <span data-ttu-id="956f8-369">Kraj/region (wymagane)</span><span class="sxs-lookup"><span data-stu-id="956f8-369">Country/region (required)</span></span>
- <span data-ttu-id="956f8-370">Kod pocztowy (wymagane)</span><span class="sxs-lookup"><span data-stu-id="956f8-370">Zip/postal code (required)</span></span>
- <span data-ttu-id="956f8-371">Ulica (wymagane)</span><span class="sxs-lookup"><span data-stu-id="956f8-371">Street (required)</span></span>
- <span data-ttu-id="956f8-372">Numer domu (wymagane)</span><span class="sxs-lookup"><span data-stu-id="956f8-372">Street Number (required)</span></span>
- <span data-ttu-id="956f8-373">Dodatkowe określenie budynku</span><span class="sxs-lookup"><span data-stu-id="956f8-373">Building Complement</span></span>
- <span data-ttu-id="956f8-374">Miejscowość (wymagane)</span><span class="sxs-lookup"><span data-stu-id="956f8-374">City (required)</span></span>
- <span data-ttu-id="956f8-375">Województwo (wymagane)</span><span class="sxs-lookup"><span data-stu-id="956f8-375">State (required)</span></span>
- <span data-ttu-id="956f8-376">Powiat (wymagane)</span><span class="sxs-lookup"><span data-stu-id="956f8-376">County (required)</span></span>

## <a name="configure-your-data-to-generate-payroll-in-united-states-and-canada"></a><span data-ttu-id="956f8-377">Konfigurowanie danych w celu generowania listy płac w Stanach Zjednoczonych i Kanadzie</span><span class="sxs-lookup"><span data-stu-id="956f8-377">Configure your data to generate payroll in United States and Canada</span></span>

<span data-ttu-id="956f8-378">Jeśli generujesz płace dla pracowników na terenie Stanów Zjednoczonych i Kanady, należy skonfigurować następujące elementy:</span><span class="sxs-lookup"><span data-stu-id="956f8-378">If you're generating pay for employees in the United States and Canada, the following elements must be configured:</span></span>

- <span data-ttu-id="956f8-379">Dla stanowisk muszą być określone działy.</span><span class="sxs-lookup"><span data-stu-id="956f8-379">Departments are required on positions.</span></span>
- <span data-ttu-id="956f8-380">Centra kosztów muszą być ustawione jako wymiary finansowe i muszą być pierwszym elementem w ciągu domyślnych wymiarów finansowych.</span><span class="sxs-lookup"><span data-stu-id="956f8-380">Cost centers must be set as financial dimensions and must be the first element in the default financial dimension string.</span></span>

### <a name="job-types"></a><span data-ttu-id="956f8-381">Typy stanowisk</span><span class="sxs-lookup"><span data-stu-id="956f8-381">Job types</span></span>

<span data-ttu-id="956f8-382">Typy funkcji służą do grupowanie podobnych funkcji w kategorie.</span><span class="sxs-lookup"><span data-stu-id="956f8-382">Job types are used to group similar jobs into categories.</span></span> <span data-ttu-id="956f8-383">Typy funkcji są wymagane w celu przetwarzania listy płac w Stanach Zjednoczonych i Kanadzie.</span><span class="sxs-lookup"><span data-stu-id="956f8-383">Job types are required in order to process payroll in the United States and Canada.</span></span> <span data-ttu-id="956f8-384">Przykłady typów funkcji to zatrudnienie w pełnym i niepełnym wymiarze czasu albo wynagrodzenie za etat i za godziny.</span><span class="sxs-lookup"><span data-stu-id="956f8-384">Examples of job types include full-time and part-time, or salary and hourly pay.</span></span> <span data-ttu-id="956f8-385">Typy funkcji są mapowane do systemu Dayforce jako typy płac, które wskazują, czy pracownik jest na stawce godzinowej, czy stałej pensji.</span><span class="sxs-lookup"><span data-stu-id="956f8-385">Job types are mapped to Dayforce as pay types that indicate whether an employee is hourly or salaried.</span></span>

<span data-ttu-id="956f8-386">Następujące typy funkcji i opisy są wymagane.</span><span class="sxs-lookup"><span data-stu-id="956f8-386">The following job types and descriptions are required.</span></span>

| <span data-ttu-id="956f8-387">Typ funkcji</span><span class="sxs-lookup"><span data-stu-id="956f8-387">Job type</span></span>   | <span data-ttu-id="956f8-388">opis</span><span class="sxs-lookup"><span data-stu-id="956f8-388">Description</span></span> |
|------------|-------------|
| <span data-ttu-id="956f8-389">Co godzinę</span><span class="sxs-lookup"><span data-stu-id="956f8-389">Hourly</span></span>     | <span data-ttu-id="956f8-390">Co godzinę</span><span class="sxs-lookup"><span data-stu-id="956f8-390">Hourly</span></span>      |
| <span data-ttu-id="956f8-391">Stała pensja</span><span class="sxs-lookup"><span data-stu-id="956f8-391">Salaried</span></span>   | <span data-ttu-id="956f8-392">Stała pensja</span><span class="sxs-lookup"><span data-stu-id="956f8-392">Salaried</span></span>    |

### <a name="position-types"></a><span data-ttu-id="956f8-393">Typy stanowisk</span><span class="sxs-lookup"><span data-stu-id="956f8-393">Position types</span></span> 

<span data-ttu-id="956f8-394">Typy stanowisk służą do opisywania, czy stanowisko jest w pełnym wymiarze czasu, niepełnym wymiarze czasu lub ma inną konfigurację.</span><span class="sxs-lookup"><span data-stu-id="956f8-394">You use position types to describe whether the position is full-time, part-time, or something else.</span></span> <span data-ttu-id="956f8-395">Typy stanowisk są mapowane do systemu Dayforce jako klasy płac, które wskazują, czy pracownik jest zatrudniony na pełny etat, czy na część etatu.</span><span class="sxs-lookup"><span data-stu-id="956f8-395">Position types are mapped to Dayforce as pay classes that indicate whether an employee is full-time or part-time.</span></span>

<span data-ttu-id="956f8-396">Następujące typy stanowisk i opisy są wymagane.</span><span class="sxs-lookup"><span data-stu-id="956f8-396">The following position types and descriptions are required.</span></span>

| <span data-ttu-id="956f8-397">Typ stanowiska</span><span class="sxs-lookup"><span data-stu-id="956f8-397">Position type</span></span>   | <span data-ttu-id="956f8-398">opis</span><span class="sxs-lookup"><span data-stu-id="956f8-398">Description</span></span>        |
|-----------------|--------------------|
| <span data-ttu-id="956f8-399">Pełny etat</span><span class="sxs-lookup"><span data-stu-id="956f8-399">Full-time</span></span>       | <span data-ttu-id="956f8-400">Pracownik etatowy zatrudniony w pełnym wymiarze czasu</span><span class="sxs-lookup"><span data-stu-id="956f8-400">Full time employee</span></span> |
| <span data-ttu-id="956f8-401">Część etatu</span><span class="sxs-lookup"><span data-stu-id="956f8-401">Part-time</span></span>       | <span data-ttu-id="956f8-402">Pracownik etatowy zatrudniony w niepełnym wymiarze czasu</span><span class="sxs-lookup"><span data-stu-id="956f8-402">Part time employee</span></span> |

### <a name="reason-codes"></a><span data-ttu-id="956f8-403">Kody przyczyn</span><span class="sxs-lookup"><span data-stu-id="956f8-403">Reason codes</span></span>

<span data-ttu-id="956f8-404">Kody przyczyn informują o stanie pracownika.</span><span class="sxs-lookup"><span data-stu-id="956f8-404">Reason codes provide information about the status of an employee.</span></span> <span data-ttu-id="956f8-405">Kody przyczyn są mapowane do systemu Dayforce jako przyczyny stanu, które wskazują powód zmiany stanowiska lub statusu zatrudnienia pracownika.</span><span class="sxs-lookup"><span data-stu-id="956f8-405">Reason codes are mapped to Dayforce as status reasons that indicate the reason for changes to an employee's position or employment status.</span></span>

<span data-ttu-id="956f8-406">Następujące kody przyczyn i opisy są wymagane.</span><span class="sxs-lookup"><span data-stu-id="956f8-406">The following reason codes and descriptions are required.</span></span>

| <span data-ttu-id="956f8-407">Kod przyczyny</span><span class="sxs-lookup"><span data-stu-id="956f8-407">Reason code</span></span>    | <span data-ttu-id="956f8-408">opis</span><span class="sxs-lookup"><span data-stu-id="956f8-408">Description</span></span>      | <span data-ttu-id="956f8-409">Odpowiednie scenariusze</span><span class="sxs-lookup"><span data-stu-id="956f8-409">Applicable scenarios</span></span> |
|----------------|------------------|----------------------|
| <span data-ttu-id="956f8-410">RESIGNATION</span><span class="sxs-lookup"><span data-stu-id="956f8-410">RESIGNATION</span></span>    | <span data-ttu-id="956f8-411">Rezygnacja</span><span class="sxs-lookup"><span data-stu-id="956f8-411">Resignation</span></span>      | <span data-ttu-id="956f8-412">Zwalnianie pracownika</span><span class="sxs-lookup"><span data-stu-id="956f8-412">Terminate worker</span></span>     |
| <span data-ttu-id="956f8-413">TERMINATION</span><span class="sxs-lookup"><span data-stu-id="956f8-413">TERMINATION</span></span>    | <span data-ttu-id="956f8-414">Przerwanie</span><span class="sxs-lookup"><span data-stu-id="956f8-414">Termination</span></span>      | <span data-ttu-id="956f8-415">Zwalnianie pracownika</span><span class="sxs-lookup"><span data-stu-id="956f8-415">Terminate worker</span></span>     |
| <span data-ttu-id="956f8-416">RETIREMENT</span><span class="sxs-lookup"><span data-stu-id="956f8-416">RETIREMENT</span></span>     | <span data-ttu-id="956f8-417">Emerytura</span><span class="sxs-lookup"><span data-stu-id="956f8-417">Retirement</span></span>       | <span data-ttu-id="956f8-418">Zwalnianie pracownika</span><span class="sxs-lookup"><span data-stu-id="956f8-418">Terminate worker</span></span>     |
| <span data-ttu-id="956f8-419">INNY</span><span class="sxs-lookup"><span data-stu-id="956f8-419">OTHER</span></span>          | <span data-ttu-id="956f8-420">Inne przyczyny</span><span class="sxs-lookup"><span data-stu-id="956f8-420">Other Reasons</span></span>    | <span data-ttu-id="956f8-421">Zwalnianie pracownika</span><span class="sxs-lookup"><span data-stu-id="956f8-421">Terminate worker</span></span>     |
| <span data-ttu-id="956f8-422">DEATH</span><span class="sxs-lookup"><span data-stu-id="956f8-422">DEATH</span></span>          | <span data-ttu-id="956f8-423">Śmierć</span><span class="sxs-lookup"><span data-stu-id="956f8-423">Death</span></span>            | <span data-ttu-id="956f8-424">Zwalnianie pracownika</span><span class="sxs-lookup"><span data-stu-id="956f8-424">Terminate worker</span></span>     |
| <span data-ttu-id="956f8-425">LEAVEOFABSENCE</span><span class="sxs-lookup"><span data-stu-id="956f8-425">LEAVEOFABSENCE</span></span> | <span data-ttu-id="956f8-426">Nieobecność</span><span class="sxs-lookup"><span data-stu-id="956f8-426">Leave of Absence</span></span> | <span data-ttu-id="956f8-427">Zwalnianie pracownika</span><span class="sxs-lookup"><span data-stu-id="956f8-427">Terminate worker</span></span>     |
| <span data-ttu-id="956f8-428">CONTRACTEND</span><span class="sxs-lookup"><span data-stu-id="956f8-428">CONTRACTEND</span></span>    | <span data-ttu-id="956f8-429">Zakończenie umowy</span><span class="sxs-lookup"><span data-stu-id="956f8-429">End of Contract</span></span>  | <span data-ttu-id="956f8-430">Zwalnianie pracownika</span><span class="sxs-lookup"><span data-stu-id="956f8-430">Terminate worker</span></span>     |
| <span data-ttu-id="956f8-431">SALARYCHANGE</span><span class="sxs-lookup"><span data-stu-id="956f8-431">SALARYCHANGE</span></span>   | <span data-ttu-id="956f8-432">Zmiana wynagrodzenia</span><span class="sxs-lookup"><span data-stu-id="956f8-432">Change of Salary</span></span> | <span data-ttu-id="956f8-433">Wynagrodzenie</span><span class="sxs-lookup"><span data-stu-id="956f8-433">Compensation</span></span>         |

### <a name="marital-status"></a><span data-ttu-id="956f8-434">Stan cywilny</span><span class="sxs-lookup"><span data-stu-id="956f8-434">Marital status</span></span>

<span data-ttu-id="956f8-435">Wartości stanu cywilnego są mapowane do systemu Dayforce i w razie potrzeby tłumaczone na akceptowane wartości podczas integracji.</span><span class="sxs-lookup"><span data-stu-id="956f8-435">Marital status values are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="956f8-436">W poniższej tabeli przedstawiono mapowanie wartości stanu cywilnego do usługi Dayforce.</span><span class="sxs-lookup"><span data-stu-id="956f8-436">The following table shows how marital status values are mapped to Dayforce.</span></span>

| <span data-ttu-id="956f8-437">Talent</span><span class="sxs-lookup"><span data-stu-id="956f8-437">Talent</span></span>                 | <span data-ttu-id="956f8-438">Dayforce</span><span class="sxs-lookup"><span data-stu-id="956f8-438">Dayforce</span></span>             |
|------------------------|----------------------|
| <span data-ttu-id="956f8-439">Żonaty/mężatka</span><span class="sxs-lookup"><span data-stu-id="956f8-439">Married</span></span>                | <span data-ttu-id="956f8-440">Żonaty/mężatka</span><span class="sxs-lookup"><span data-stu-id="956f8-440">Married</span></span>              |
| <span data-ttu-id="956f8-441">Jedno</span><span class="sxs-lookup"><span data-stu-id="956f8-441">Single</span></span>                 | <span data-ttu-id="956f8-442">Jedno</span><span class="sxs-lookup"><span data-stu-id="956f8-442">Single</span></span>               |
| <span data-ttu-id="956f8-443">Wdowiec/wdowa</span><span class="sxs-lookup"><span data-stu-id="956f8-443">Widowed</span></span>                | <span data-ttu-id="956f8-444">Wdowiec/wdowa</span><span class="sxs-lookup"><span data-stu-id="956f8-444">Widowed</span></span>              |
| <span data-ttu-id="956f8-445">Rozwiedziony/rozwiedziona</span><span class="sxs-lookup"><span data-stu-id="956f8-445">Divorced</span></span>               | <span data-ttu-id="956f8-446">Rozwiedziony/rozwiedziona</span><span class="sxs-lookup"><span data-stu-id="956f8-446">Divorced</span></span>             |
| <span data-ttu-id="956f8-447">Związek zarejestrowany</span><span class="sxs-lookup"><span data-stu-id="956f8-447">Registered Partnership</span></span> | <span data-ttu-id="956f8-448">Partnerstwo krajowe</span><span class="sxs-lookup"><span data-stu-id="956f8-448">Domestic Partnership</span></span> |
| <span data-ttu-id="956f8-449">None</span><span class="sxs-lookup"><span data-stu-id="956f8-449">None</span></span>                   | <span data-ttu-id="956f8-450">None</span><span class="sxs-lookup"><span data-stu-id="956f8-450">None</span></span>                 |
| <span data-ttu-id="956f8-451">Konkubinat</span><span class="sxs-lookup"><span data-stu-id="956f8-451">Cohabiting</span></span>             | <span data-ttu-id="956f8-452">Konkubinat</span><span class="sxs-lookup"><span data-stu-id="956f8-452">Cohabiting</span></span>           |

### <a name="gender"></a><span data-ttu-id="956f8-453">Rodzaj</span><span class="sxs-lookup"><span data-stu-id="956f8-453">Gender</span></span>

<span data-ttu-id="956f8-454">Określenia płci są mapowane do systemu Dayforce i w razie potrzeby tłumaczone na akceptowane wartości podczas integracji.</span><span class="sxs-lookup"><span data-stu-id="956f8-454">Gender designations are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="956f8-455">W poniższej tabeli przedstawiono mapowanie określeń płci do usługi Dayforce.</span><span class="sxs-lookup"><span data-stu-id="956f8-455">The following table shows how gender designations are mapped to Dayforce.</span></span>

| <span data-ttu-id="956f8-456">Talent</span><span class="sxs-lookup"><span data-stu-id="956f8-456">Talent</span></span>       | <span data-ttu-id="956f8-457">Dayforce</span><span class="sxs-lookup"><span data-stu-id="956f8-457">Dayforce</span></span>        |
|--------------|-----------------|
| <span data-ttu-id="956f8-458">Mężczyzna</span><span class="sxs-lookup"><span data-stu-id="956f8-458">Male</span></span>         | <span data-ttu-id="956f8-459">Mężczyzna</span><span class="sxs-lookup"><span data-stu-id="956f8-459">Male</span></span>            |
| <span data-ttu-id="956f8-460">Kobieta</span><span class="sxs-lookup"><span data-stu-id="956f8-460">Female</span></span>       | <span data-ttu-id="956f8-461">Kobieta</span><span class="sxs-lookup"><span data-stu-id="956f8-461">Female</span></span>          |
| <span data-ttu-id="956f8-462">Nieokreślone</span><span class="sxs-lookup"><span data-stu-id="956f8-462">Non-specific</span></span> | <span data-ttu-id="956f8-463">*Nieobsługiwane*</span><span class="sxs-lookup"><span data-stu-id="956f8-463">*Not supported*</span></span> |

### <a name="earning-codes"></a><span data-ttu-id="956f8-464">Kody zarobków</span><span class="sxs-lookup"><span data-stu-id="956f8-464">Earning codes</span></span>

<span data-ttu-id="956f8-465">Kody zarobków jednoznacznie identyfikują każdy rodzaj dochodów, które otrzymują pracownicy.</span><span class="sxs-lookup"><span data-stu-id="956f8-465">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="956f8-466">Kody mają różne parametry związane z zarobkami, takie jak reguły księgowania, przepisy podatkowe, wymagania dotyczące raportowania i możliwość zwiększania wartości brutto.</span><span class="sxs-lookup"><span data-stu-id="956f8-466">The codes cover several parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span> <span data-ttu-id="956f8-467">W razie ustawienia nieobsługiwanej częstotliwości domyślnie w obliczeniu będzie używana częstotliwość **Każda wypłata**.</span><span class="sxs-lookup"><span data-stu-id="956f8-467">If an unsupported frequency is used, the **Every Pay** frequency is used by default for the calculation.</span></span>

#### <a name="supported-frequencies"></a><span data-ttu-id="956f8-468">Obsługiwane częstotliwości</span><span class="sxs-lookup"><span data-stu-id="956f8-468">Supported frequencies</span></span>

- <span data-ttu-id="956f8-469">Wszyscy</span><span class="sxs-lookup"><span data-stu-id="956f8-469">All</span></span>
- <span data-ttu-id="956f8-470">EVERYPAY</span><span class="sxs-lookup"><span data-stu-id="956f8-470">EVERYPAY</span></span>
- <span data-ttu-id="956f8-471">EACHPAYPERIOD</span><span class="sxs-lookup"><span data-stu-id="956f8-471">EACHPAYPERIOD</span></span>
- <span data-ttu-id="956f8-472">EVRYOTHRPAYODD</span><span class="sxs-lookup"><span data-stu-id="956f8-472">EVRYOTHRPAYODD</span></span>
- <span data-ttu-id="956f8-473">EVRYOTHRPAYEVN</span><span class="sxs-lookup"><span data-stu-id="956f8-473">EVRYOTHRPAYEVN</span></span>
- <span data-ttu-id="956f8-474">1OFMTH</span><span class="sxs-lookup"><span data-stu-id="956f8-474">1OFMTH</span></span>
- <span data-ttu-id="956f8-475">LASTOFMTH</span><span class="sxs-lookup"><span data-stu-id="956f8-475">LASTOFMTH</span></span>
- <span data-ttu-id="956f8-476">2OFMTH</span><span class="sxs-lookup"><span data-stu-id="956f8-476">2OFMTH</span></span>
- <span data-ttu-id="956f8-477">3OFMTH</span><span class="sxs-lookup"><span data-stu-id="956f8-477">3OFMTH</span></span>
- <span data-ttu-id="956f8-478">4OFMTH</span><span class="sxs-lookup"><span data-stu-id="956f8-478">4OFMTH</span></span>
- <span data-ttu-id="956f8-479">5OFMTH</span><span class="sxs-lookup"><span data-stu-id="956f8-479">5OFMTH</span></span>
- <span data-ttu-id="956f8-480">1N2OFMTH</span><span class="sxs-lookup"><span data-stu-id="956f8-480">1N2OFMTH</span></span>
- <span data-ttu-id="956f8-481">3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="956f8-481">3N4OFMTH</span></span>
- <span data-ttu-id="956f8-482">1N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="956f8-482">1N3OFMTH</span></span>
- <span data-ttu-id="956f8-483">1N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="956f8-483">1N4OFMTH</span></span>
- <span data-ttu-id="956f8-484">2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="956f8-484">2N3OFMTH</span></span>
- <span data-ttu-id="956f8-485">2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="956f8-485">2N4OFMTH</span></span>
- <span data-ttu-id="956f8-486">1N2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="956f8-486">1N2N3OFMTH</span></span>
- <span data-ttu-id="956f8-487">1N2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="956f8-487">1N2N4OFMTH</span></span>
- <span data-ttu-id="956f8-488">1N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="956f8-488">1N3N4OFMTH</span></span>
- <span data-ttu-id="956f8-489">2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="956f8-489">2N3N4OFMTH</span></span>
- <span data-ttu-id="956f8-490">1N2N3N4OFMTH – 1N2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="956f8-490">1N2N3N4OFMTH - 1N2N3N4OFMTH</span></span>
- <span data-ttu-id="956f8-491">2N3N4N5OFMth – 2N3N4N5OFMth</span><span class="sxs-lookup"><span data-stu-id="956f8-491">2N3N4N5OFMth - 2N3N4N5OFMth</span></span>
- <span data-ttu-id="956f8-492">1OFQTR – 1OFQTR</span><span class="sxs-lookup"><span data-stu-id="956f8-492">1OFQTR - 1OFQTR</span></span>
- <span data-ttu-id="956f8-493">LASTOFQTR – LASTOFQTR</span><span class="sxs-lookup"><span data-stu-id="956f8-493">LASTOFQTR – LASTOFQTR</span></span>
- <span data-ttu-id="956f8-494">LASTMTHOFQTR – LASTMTHOFQTR</span><span class="sxs-lookup"><span data-stu-id="956f8-494">LASTMTHOFQTR – LASTMTHOFQTR</span></span>
- <span data-ttu-id="956f8-495">1OFYEAR – 1OFYEAR</span><span class="sxs-lookup"><span data-stu-id="956f8-495">1OFYEAR - 1OFYEAR</span></span>
- <span data-ttu-id="956f8-496">LASTOFYEAR – LASTOFYEAR</span><span class="sxs-lookup"><span data-stu-id="956f8-496">LASTOFYEAR – LASTOFYEAR</span></span>
- <span data-ttu-id="956f8-497">NOVNDECOFYEAR – NOVNDECOFYEAR</span><span class="sxs-lookup"><span data-stu-id="956f8-497">NOVNDECOFYEAR - NOVNDECOFYEAR</span></span>

### <a name="addresses"></a><span data-ttu-id="956f8-498">Adresy</span><span class="sxs-lookup"><span data-stu-id="956f8-498">Addresses</span></span>

<span data-ttu-id="956f8-499">Identyfikacja określonych kodów kraju lub regionu, województwa i powiatu (gminy) wymaga określonych formatów, które potrafi rozpoznać system Dayforce oraz dostawcy wewnątrz krajów/regionów.</span><span class="sxs-lookup"><span data-stu-id="956f8-499">The identification of specific country or region, state, and county (municipality) codes requires specific formats that Dayforce and in-country/in-region providers can recognize.</span></span> <span data-ttu-id="956f8-500">Co prawda format nazw miejscowości jest elastyczny, ale każda miejscowość musi być skojarzona z województwem.</span><span class="sxs-lookup"><span data-stu-id="956f8-500">Although the format for cities is flexible, every city must be associated with a state.</span></span>

| <span data-ttu-id="956f8-501">Talent</span><span class="sxs-lookup"><span data-stu-id="956f8-501">Talent</span></span>          | <span data-ttu-id="956f8-502">Dayforce</span><span class="sxs-lookup"><span data-stu-id="956f8-502">Dayforce</span></span>              |
|-----------------|-----------------------|
| <span data-ttu-id="956f8-503">Kraj/region</span><span class="sxs-lookup"><span data-stu-id="956f8-503">Country/Region</span></span>  | <span data-ttu-id="956f8-504">Kod kraju</span><span class="sxs-lookup"><span data-stu-id="956f8-504">Country Code</span></span>          |
| <span data-ttu-id="956f8-505">Kod pocztowy</span><span class="sxs-lookup"><span data-stu-id="956f8-505">Zip/Postal Code</span></span> | <span data-ttu-id="956f8-506">Kod pocztowy</span><span class="sxs-lookup"><span data-stu-id="956f8-506">Postal Code</span></span>           |
| <span data-ttu-id="956f8-507">Stanowy</span><span class="sxs-lookup"><span data-stu-id="956f8-507">State</span></span>           | <span data-ttu-id="956f8-508">Kod województwa</span><span class="sxs-lookup"><span data-stu-id="956f8-508">State Code</span></span>            |
| <span data-ttu-id="956f8-509">Miejscowość</span><span class="sxs-lookup"><span data-stu-id="956f8-509">City</span></span>            | <span data-ttu-id="956f8-510">Miejscowość</span><span class="sxs-lookup"><span data-stu-id="956f8-510">City</span></span>                  |
| <span data-ttu-id="956f8-511">Powiat</span><span class="sxs-lookup"><span data-stu-id="956f8-511">County</span></span>          | <span data-ttu-id="956f8-512">Powiat (gmina)</span><span class="sxs-lookup"><span data-stu-id="956f8-512">County (Municipality)</span></span> |
| <span data-ttu-id="956f8-513">Ulica</span><span class="sxs-lookup"><span data-stu-id="956f8-513">Street</span></span>          | <span data-ttu-id="956f8-514">Wiersz adresu 1</span><span class="sxs-lookup"><span data-stu-id="956f8-514">Address Line 1</span></span>        |

### <a name="tax-regions"></a><span data-ttu-id="956f8-515">Regiony podatkowe</span><span class="sxs-lookup"><span data-stu-id="956f8-515">Tax regions</span></span>

<span data-ttu-id="956f8-516">Regiony podatkowe służą do określania odpowiedniej stawki podatkowej stosowanej podczas generowania listy płac.</span><span class="sxs-lookup"><span data-stu-id="956f8-516">Tax regions are used to determine the appropriate tax that should be applied during payroll generation.</span></span> <span data-ttu-id="956f8-517">Regiony podatkowe są mapowane do systemu Dayforce jako adresy lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="956f8-517">Tax regions are mapped to Dayforce as location addresses.</span></span> <span data-ttu-id="956f8-518">Domyślny region podatkowy musi być skojarzony z aktywnym stanowiskiem pracownika.</span><span class="sxs-lookup"><span data-stu-id="956f8-518">The default tax region must be associated with the worker's active position.</span></span> 

- <span data-ttu-id="956f8-519">Region podatkowy (wymagane)</span><span class="sxs-lookup"><span data-stu-id="956f8-519">Tax region (required)</span></span>
- <span data-ttu-id="956f8-520">Kraj/region (wymagane)</span><span class="sxs-lookup"><span data-stu-id="956f8-520">Country/Region (required)</span></span>
- <span data-ttu-id="956f8-521">Województwo (wymagane)</span><span class="sxs-lookup"><span data-stu-id="956f8-521">State (required)</span></span>
- <span data-ttu-id="956f8-522">Powiat</span><span class="sxs-lookup"><span data-stu-id="956f8-522">County</span></span> 
- <span data-ttu-id="956f8-523">Miejscowość (wymagane)</span><span class="sxs-lookup"><span data-stu-id="956f8-523">City (required)</span></span>

## <a name="configure-your-data-to-generate-payroll-in-mexico"></a><span data-ttu-id="956f8-524">Konfigurowanie danych w celu generowania listy płac w Meksyku</span><span class="sxs-lookup"><span data-stu-id="956f8-524">Configure your data to generate payroll in Mexico</span></span>

<span data-ttu-id="956f8-525">Jeśli generujesz płace dla pracowników na terenie Meksyku, należy skonfigurować następujące elementy:</span><span class="sxs-lookup"><span data-stu-id="956f8-525">If you're generating pay for employees in Mexico, the following elements must be configured:</span></span>

- <span data-ttu-id="956f8-526">Dla stanowisk muszą być określone działy.</span><span class="sxs-lookup"><span data-stu-id="956f8-526">Departments are required on positions.</span></span>
- <span data-ttu-id="956f8-527">Centra kosztów muszą być ustawione jako wymiary finansowe i muszą być pierwszym elementem w ciągu domyślnych wymiarów finansowych.</span><span class="sxs-lookup"><span data-stu-id="956f8-527">Cost centers must be set as financial dimensions and must be the first element in the Default Financial Dimension string.</span></span>

### <a name="job-types"></a><span data-ttu-id="956f8-528">Typy stanowisk</span><span class="sxs-lookup"><span data-stu-id="956f8-528">Job types</span></span>

<span data-ttu-id="956f8-529">Typy funkcji służą do grupowanie podobnych funkcji w kategorie.</span><span class="sxs-lookup"><span data-stu-id="956f8-529">Job types are used to group similar jobs into categories.</span></span> <span data-ttu-id="956f8-530">Typy funkcji są wymagane w celu przetwarzania listy płac w Meksyku.</span><span class="sxs-lookup"><span data-stu-id="956f8-530">Job types are required in order to process payroll in Mexico.</span></span> <span data-ttu-id="956f8-531">Przykłady typów funkcji to zatrudnienie w pełnym i niepełnym wymiarze czasu albo wynagrodzenie za etat i za godziny.</span><span class="sxs-lookup"><span data-stu-id="956f8-531">Examples of job types include full-time and part-time, or salary and hourly pay.</span></span> <span data-ttu-id="956f8-532">Typy funkcji są mapowane do systemu Dayforce jako typy płac, które wskazują, czy pracownik jest na stawce godzinowej, czy stałej pensji.</span><span class="sxs-lookup"><span data-stu-id="956f8-532">Job types are mapped to Dayforce as pay types that indicate whether an employee is hourly or salaried.</span></span>

<span data-ttu-id="956f8-533">Następujące typy funkcji i opisy są wymagane.</span><span class="sxs-lookup"><span data-stu-id="956f8-533">The following job types and descriptions are required.</span></span>

| <span data-ttu-id="956f8-534">Typ funkcji</span><span class="sxs-lookup"><span data-stu-id="956f8-534">Job type</span></span>   | <span data-ttu-id="956f8-535">opis</span><span class="sxs-lookup"><span data-stu-id="956f8-535">Description</span></span> |
|------------|-------------|
| <span data-ttu-id="956f8-536">Co godzinę</span><span class="sxs-lookup"><span data-stu-id="956f8-536">Hourly</span></span>     | <span data-ttu-id="956f8-537">MX Co godzinę</span><span class="sxs-lookup"><span data-stu-id="956f8-537">MX Hourly</span></span>   |
| <span data-ttu-id="956f8-538">Stała pensja</span><span class="sxs-lookup"><span data-stu-id="956f8-538">Salaried</span></span>   | <span data-ttu-id="956f8-539">MX Stała pensja</span><span class="sxs-lookup"><span data-stu-id="956f8-539">MX Salaried</span></span> |

### <a name="position-types"></a><span data-ttu-id="956f8-540">Typy stanowisk</span><span class="sxs-lookup"><span data-stu-id="956f8-540">Position types</span></span> 

<span data-ttu-id="956f8-541">Typy stanowisk służą do opisywania, czy stanowisko jest w pełnym wymiarze czasu, niepełnym wymiarze czasu lub ma inną konfigurację.</span><span class="sxs-lookup"><span data-stu-id="956f8-541">You use position types to describe whether the position is full-time, part-time, or something else.</span></span> <span data-ttu-id="956f8-542">Typy stanowisk są mapowane do systemu Dayforce jako klasy płac, które wskazują, czy pracownik jest zatrudniony na pełny etat, czy na część etatu.</span><span class="sxs-lookup"><span data-stu-id="956f8-542">Position types are mapped to Dayforce as pay classes that indicate whether an employee is full-time or part-time.</span></span>

<span data-ttu-id="956f8-543">Następujące typy stanowisk i opisy są wymagane.</span><span class="sxs-lookup"><span data-stu-id="956f8-543">The following position types and descriptions are required.</span></span>

| <span data-ttu-id="956f8-544">Typ stanowiska</span><span class="sxs-lookup"><span data-stu-id="956f8-544">Position type</span></span>   | <span data-ttu-id="956f8-545">opis</span><span class="sxs-lookup"><span data-stu-id="956f8-545">Description</span></span>        |
|-----------------|--------------------|
| <span data-ttu-id="956f8-546">Pełny etat</span><span class="sxs-lookup"><span data-stu-id="956f8-546">Full-time</span></span>       | <span data-ttu-id="956f8-547">Pracownik etatowy zatrudniony w pełnym wymiarze czasu</span><span class="sxs-lookup"><span data-stu-id="956f8-547">Full time employee</span></span> |
| <span data-ttu-id="956f8-548">Część etatu</span><span class="sxs-lookup"><span data-stu-id="956f8-548">Part-time</span></span>       | <span data-ttu-id="956f8-549">Pracownik etatowy zatrudniony w niepełnym wymiarze czasu</span><span class="sxs-lookup"><span data-stu-id="956f8-549">Part time employee</span></span> |

### <a name="reason-codes"></a><span data-ttu-id="956f8-550">Kody przyczyn</span><span class="sxs-lookup"><span data-stu-id="956f8-550">Reason codes</span></span>

<span data-ttu-id="956f8-551">Kody przyczyn informują o stanie pracownika.</span><span class="sxs-lookup"><span data-stu-id="956f8-551">Reason codes provide information about the status of an employee.</span></span> <span data-ttu-id="956f8-552">Kody przyczyn są mapowane do systemu Dayforce jako przyczyny stanu, które wskazują powód zmiany stanowiska lub statusu zatrudnienia pracownika.</span><span class="sxs-lookup"><span data-stu-id="956f8-552">Reason codes are mapped to Dayforce as status reasons that indicate the reason for changes to an employee's position or employment status.</span></span>

<span data-ttu-id="956f8-553">Następujące kody przyczyn i opisy są wymagane.</span><span class="sxs-lookup"><span data-stu-id="956f8-553">The following reason codes and descriptions are required.</span></span>

| <span data-ttu-id="956f8-554">Kod przyczyny</span><span class="sxs-lookup"><span data-stu-id="956f8-554">Reason code</span></span>            | <span data-ttu-id="956f8-555">opis</span><span class="sxs-lookup"><span data-stu-id="956f8-555">Description</span></span>                    | <span data-ttu-id="956f8-556">Odpowiednie scenariusze</span><span class="sxs-lookup"><span data-stu-id="956f8-556">Applicable scenarios</span></span> |
|------------------------|--------------------------------|----------------------|
| <span data-ttu-id="956f8-557">DEPARTUREBEFOREPAYMENT</span><span class="sxs-lookup"><span data-stu-id="956f8-557">DEPARTUREBEFOREPAYMENT</span></span> | <span data-ttu-id="956f8-558">Odejście z pracy przed pierwszą wypłatą</span><span class="sxs-lookup"><span data-stu-id="956f8-558">Departure before first payroll</span></span> | <span data-ttu-id="956f8-559">Zwalnianie pracownika</span><span class="sxs-lookup"><span data-stu-id="956f8-559">Terminate worker</span></span>     |
| <span data-ttu-id="956f8-560">RESIGNATION</span><span class="sxs-lookup"><span data-stu-id="956f8-560">RESIGNATION</span></span>            | <span data-ttu-id="956f8-561">Rezygnacja</span><span class="sxs-lookup"><span data-stu-id="956f8-561">Resignation</span></span>                    | <span data-ttu-id="956f8-562">Zwalnianie pracownika</span><span class="sxs-lookup"><span data-stu-id="956f8-562">Terminate worker</span></span>     |
| <span data-ttu-id="956f8-563">PENSION</span><span class="sxs-lookup"><span data-stu-id="956f8-563">PENSION</span></span>                | <span data-ttu-id="956f8-564">Emerytura</span><span class="sxs-lookup"><span data-stu-id="956f8-564">Pension</span></span>                        | <span data-ttu-id="956f8-565">Zwalnianie pracownika</span><span class="sxs-lookup"><span data-stu-id="956f8-565">Terminate worker</span></span>     |
| <span data-ttu-id="956f8-566">TERMINATION</span><span class="sxs-lookup"><span data-stu-id="956f8-566">TERMINATION</span></span>            | <span data-ttu-id="956f8-567">Przerwanie</span><span class="sxs-lookup"><span data-stu-id="956f8-567">Termination</span></span>                    | <span data-ttu-id="956f8-568">Zwalnianie pracownika</span><span class="sxs-lookup"><span data-stu-id="956f8-568">Terminate worker</span></span>     |
| <span data-ttu-id="956f8-569">RETIREMENT</span><span class="sxs-lookup"><span data-stu-id="956f8-569">RETIREMENT</span></span>             | <span data-ttu-id="956f8-570">Emerytura</span><span class="sxs-lookup"><span data-stu-id="956f8-570">Retirement</span></span>                     | <span data-ttu-id="956f8-571">Zwalnianie pracownika</span><span class="sxs-lookup"><span data-stu-id="956f8-571">Terminate worker</span></span>     |
| <span data-ttu-id="956f8-572">ABSENTEE</span><span class="sxs-lookup"><span data-stu-id="956f8-572">ABSENTEE</span></span>               | <span data-ttu-id="956f8-573">Absencja</span><span class="sxs-lookup"><span data-stu-id="956f8-573">Absentee</span></span>                       | <span data-ttu-id="956f8-574">Zwalnianie pracownika</span><span class="sxs-lookup"><span data-stu-id="956f8-574">Terminate worker</span></span>     |
| <span data-ttu-id="956f8-575">INNY</span><span class="sxs-lookup"><span data-stu-id="956f8-575">OTHER</span></span>                  | <span data-ttu-id="956f8-576">Inne przyczyny</span><span class="sxs-lookup"><span data-stu-id="956f8-576">Other Reasons</span></span>                  | <span data-ttu-id="956f8-577">Zwalnianie pracownika</span><span class="sxs-lookup"><span data-stu-id="956f8-577">Terminate worker</span></span>     |
| <span data-ttu-id="956f8-578">CLOSURE</span><span class="sxs-lookup"><span data-stu-id="956f8-578">CLOSURE</span></span>                | <span data-ttu-id="956f8-579">Zaprzestanie działalności przez firmę</span><span class="sxs-lookup"><span data-stu-id="956f8-579">Business Closure</span></span>               | <span data-ttu-id="956f8-580">Zwalnianie pracownika</span><span class="sxs-lookup"><span data-stu-id="956f8-580">Terminate worker</span></span>     |
| <span data-ttu-id="956f8-581">DEATH</span><span class="sxs-lookup"><span data-stu-id="956f8-581">DEATH</span></span>                  | <span data-ttu-id="956f8-582">Śmierć</span><span class="sxs-lookup"><span data-stu-id="956f8-582">Death</span></span>                          | <span data-ttu-id="956f8-583">Zwalnianie pracownika</span><span class="sxs-lookup"><span data-stu-id="956f8-583">Terminate worker</span></span>     |
| <span data-ttu-id="956f8-584">LEAVEOFABSENCE</span><span class="sxs-lookup"><span data-stu-id="956f8-584">LEAVEOFABSENCE</span></span>         | <span data-ttu-id="956f8-585">Nieobecność</span><span class="sxs-lookup"><span data-stu-id="956f8-585">Leave of Absence</span></span>               | <span data-ttu-id="956f8-586">Zwalnianie pracownika</span><span class="sxs-lookup"><span data-stu-id="956f8-586">Terminate worker</span></span>     |
| <span data-ttu-id="956f8-587">CONTRACTEND</span><span class="sxs-lookup"><span data-stu-id="956f8-587">CONTRACTEND</span></span>            | <span data-ttu-id="956f8-588">Zakończenie umowy</span><span class="sxs-lookup"><span data-stu-id="956f8-588">End of Contract</span></span>                | <span data-ttu-id="956f8-589">Zwalnianie pracownika</span><span class="sxs-lookup"><span data-stu-id="956f8-589">Terminate worker</span></span>     |
| <span data-ttu-id="956f8-590">SALARYCHANGE</span><span class="sxs-lookup"><span data-stu-id="956f8-590">SALARYCHANGE</span></span>           | <span data-ttu-id="956f8-591">Zmiana wynagrodzenia</span><span class="sxs-lookup"><span data-stu-id="956f8-591">Change of Salary</span></span>               | <span data-ttu-id="956f8-592">Wynagrodzenie</span><span class="sxs-lookup"><span data-stu-id="956f8-592">Compensation</span></span>         |

### <a name="terms-of-employment"></a><span data-ttu-id="956f8-593">Warunki zatrudnienia</span><span class="sxs-lookup"><span data-stu-id="956f8-593">Terms of employment</span></span>

<span data-ttu-id="956f8-594">Warunki zatrudnienia służą do tworzenia kategorii warunków zatrudnienia.</span><span class="sxs-lookup"><span data-stu-id="956f8-594">Terms of employment are used to create categories of employment terms.</span></span> <span data-ttu-id="956f8-595">Warunki są mapowane do systemu Dayforce jako wartości wskaźnika zatrudnienia.</span><span class="sxs-lookup"><span data-stu-id="956f8-595">The terms are mapped to Dayforce as employment indicator values.</span></span>

<span data-ttu-id="956f8-596">Następujące warunki zatrudnienia i opisy są wymagane.</span><span class="sxs-lookup"><span data-stu-id="956f8-596">The following terms of employment and descriptions are required.</span></span>

| <span data-ttu-id="956f8-597">Warunki zatrudnienia</span><span class="sxs-lookup"><span data-stu-id="956f8-597">Terms of employment</span></span>   | <span data-ttu-id="956f8-598">opis</span><span class="sxs-lookup"><span data-stu-id="956f8-598">Description</span></span> |
|-----------------------|-------------|
| <span data-ttu-id="956f8-599">Normalna</span><span class="sxs-lookup"><span data-stu-id="956f8-599">Regular</span></span>               | <span data-ttu-id="956f8-600">Normalna</span><span class="sxs-lookup"><span data-stu-id="956f8-600">Regular</span></span>     |
| <span data-ttu-id="956f8-601">Bezpośredni</span><span class="sxs-lookup"><span data-stu-id="956f8-601">Direct</span></span>                | <span data-ttu-id="956f8-602">Bezpośredni</span><span class="sxs-lookup"><span data-stu-id="956f8-602">Direct</span></span>      |
| <span data-ttu-id="956f8-603">Staż</span><span class="sxs-lookup"><span data-stu-id="956f8-603">Internship</span></span>            | <span data-ttu-id="956f8-604">Staż</span><span class="sxs-lookup"><span data-stu-id="956f8-604">Internship</span></span>  |
| <span data-ttu-id="956f8-605">Stałe</span><span class="sxs-lookup"><span data-stu-id="956f8-605">Permanent</span></span>             | <span data-ttu-id="956f8-606">Stałe</span><span class="sxs-lookup"><span data-stu-id="956f8-606">Permanent</span></span>   |

### <a name="marital-status"></a><span data-ttu-id="956f8-607">Stan cywilny</span><span class="sxs-lookup"><span data-stu-id="956f8-607">Marital status</span></span>

<span data-ttu-id="956f8-608">Wartości stanu cywilnego są mapowane do systemu Dayforce i w razie potrzeby tłumaczone na akceptowane wartości podczas integracji.</span><span class="sxs-lookup"><span data-stu-id="956f8-608">Marital status values are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="956f8-609">W poniższej tabeli przedstawiono mapowanie wartości stanu cywilnego do usługi Dayforce.</span><span class="sxs-lookup"><span data-stu-id="956f8-609">The following table shows how marital status values are mapped to Dayforce.</span></span>

| <span data-ttu-id="956f8-610">Talent</span><span class="sxs-lookup"><span data-stu-id="956f8-610">Talent</span></span>                 | <span data-ttu-id="956f8-611">Dayforce</span><span class="sxs-lookup"><span data-stu-id="956f8-611">Dayforce</span></span>                  |
|------------------------|---------------------------|
| <span data-ttu-id="956f8-612">Żonaty/mężatka</span><span class="sxs-lookup"><span data-stu-id="956f8-612">Married</span></span>                | <span data-ttu-id="956f8-613">Żonaty/mężatka</span><span class="sxs-lookup"><span data-stu-id="956f8-613">Married</span></span>                   |
| <span data-ttu-id="956f8-614">Jedno</span><span class="sxs-lookup"><span data-stu-id="956f8-614">Single</span></span>                 | <span data-ttu-id="956f8-615">Jedno</span><span class="sxs-lookup"><span data-stu-id="956f8-615">Single</span></span>                    |
| <span data-ttu-id="956f8-616">Wdowiec/wdowa</span><span class="sxs-lookup"><span data-stu-id="956f8-616">Widowed</span></span>                | <span data-ttu-id="956f8-617">Wdowiec/wdowa</span><span class="sxs-lookup"><span data-stu-id="956f8-617">Widowed</span></span>                   |
| <span data-ttu-id="956f8-618">Rozwiedziony/rozwiedziona</span><span class="sxs-lookup"><span data-stu-id="956f8-618">Divorced</span></span>               | <span data-ttu-id="956f8-619">Rozwiedziony/rozwiedziona</span><span class="sxs-lookup"><span data-stu-id="956f8-619">Divorced</span></span>                  |
| <span data-ttu-id="956f8-620">Związek zarejestrowany</span><span class="sxs-lookup"><span data-stu-id="956f8-620">Registered Partnership</span></span> | <span data-ttu-id="956f8-621">Partnerstwo krajowe</span><span class="sxs-lookup"><span data-stu-id="956f8-621">Domestic Partnership</span></span>      |
| <span data-ttu-id="956f8-622">None</span><span class="sxs-lookup"><span data-stu-id="956f8-622">None</span></span>                   | <span data-ttu-id="956f8-623">*Nieobsługiwane w Meksyku*</span><span class="sxs-lookup"><span data-stu-id="956f8-623">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="956f8-624">Konkubinat</span><span class="sxs-lookup"><span data-stu-id="956f8-624">Cohabiting</span></span>             | <span data-ttu-id="956f8-625">*Nieobsługiwane w Meksyku*</span><span class="sxs-lookup"><span data-stu-id="956f8-625">*Not supported by Mexico*</span></span> |

### <a name="gender"></a><span data-ttu-id="956f8-626">Rodzaj</span><span class="sxs-lookup"><span data-stu-id="956f8-626">Gender</span></span>

<span data-ttu-id="956f8-627">Określenia płci są mapowane do systemu Dayforce i w razie potrzeby tłumaczone na akceptowane wartości podczas integracji.</span><span class="sxs-lookup"><span data-stu-id="956f8-627">Gender designations are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="956f8-628">W poniższej tabeli przedstawiono mapowanie określeń płci do usługi Dayforce.</span><span class="sxs-lookup"><span data-stu-id="956f8-628">The following table shows how gender designations are mapped to Dayforce.</span></span>

| <span data-ttu-id="956f8-629">Talent</span><span class="sxs-lookup"><span data-stu-id="956f8-629">Talent</span></span>       | <span data-ttu-id="956f8-630">Dayforce</span><span class="sxs-lookup"><span data-stu-id="956f8-630">Dayforce</span></span>                  |
|--------------|---------------------------|
| <span data-ttu-id="956f8-631">Mężczyzna</span><span class="sxs-lookup"><span data-stu-id="956f8-631">Male</span></span>         | <span data-ttu-id="956f8-632">Mężczyzna</span><span class="sxs-lookup"><span data-stu-id="956f8-632">Male</span></span>                      |
| <span data-ttu-id="956f8-633">Kobieta</span><span class="sxs-lookup"><span data-stu-id="956f8-633">Female</span></span>       | <span data-ttu-id="956f8-634">Kobieta</span><span class="sxs-lookup"><span data-stu-id="956f8-634">Female</span></span>                    |
| <span data-ttu-id="956f8-635">Nieokreślone</span><span class="sxs-lookup"><span data-stu-id="956f8-635">Non-specific</span></span> | <span data-ttu-id="956f8-636">*Nieobsługiwane w Meksyku*</span><span class="sxs-lookup"><span data-stu-id="956f8-636">*Not supported by Mexico*</span></span> |

### <a name="payment-method"></a><span data-ttu-id="956f8-637">Metoda płatności</span><span class="sxs-lookup"><span data-stu-id="956f8-637">Payment method</span></span>

<span data-ttu-id="956f8-638">Funkcja metod płatności oferuje pracownikowi i firmie sposób opisania, jak pracownik będzie otrzymywał zapłatę.</span><span class="sxs-lookup"><span data-stu-id="956f8-638">Payment methods give the employee and the company a way to describe how employees will be paid.</span></span> <span data-ttu-id="956f8-639">Metody płatności są mapowane do systemu Dayforce i w razie potrzeby tłumaczone na akceptowane wartości podczas integracji.</span><span class="sxs-lookup"><span data-stu-id="956f8-639">Payment methods are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="956f8-640">W poniższej tabeli przedstawiono mapowanie metod płatności do usługi Dayforce.</span><span class="sxs-lookup"><span data-stu-id="956f8-640">The following table shows how payment methods are mapped to Dayforce.</span></span>

| <span data-ttu-id="956f8-641">Talent</span><span class="sxs-lookup"><span data-stu-id="956f8-641">Talent</span></span>             | <span data-ttu-id="956f8-642">Dayforce</span><span class="sxs-lookup"><span data-stu-id="956f8-642">Dayforce</span></span>                  |
|--------------------|---------------------------|
| <span data-ttu-id="956f8-643">Kasa</span><span class="sxs-lookup"><span data-stu-id="956f8-643">Cash</span></span>               | <span data-ttu-id="956f8-644">Kasa</span><span class="sxs-lookup"><span data-stu-id="956f8-644">Cash</span></span>                      |
| <span data-ttu-id="956f8-645">Płatność elektroniczna</span><span class="sxs-lookup"><span data-stu-id="956f8-645">Electronic Payment</span></span> | <span data-ttu-id="956f8-646">Przenoszenie</span><span class="sxs-lookup"><span data-stu-id="956f8-646">Transfer</span></span>                  |
| <span data-ttu-id="956f8-647">Sprawdzanie</span><span class="sxs-lookup"><span data-stu-id="956f8-647">Check</span></span>              | <span data-ttu-id="956f8-648">Czek</span><span class="sxs-lookup"><span data-stu-id="956f8-648">Cheque</span></span>                    |
| <span data-ttu-id="956f8-649">Przekaz bankowy</span><span class="sxs-lookup"><span data-stu-id="956f8-649">Bank Draft</span></span>         | <span data-ttu-id="956f8-650">*Nieobsługiwane w Meksyku*</span><span class="sxs-lookup"><span data-stu-id="956f8-650">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="956f8-651">Inna</span><span class="sxs-lookup"><span data-stu-id="956f8-651">Other</span></span>              | <span data-ttu-id="956f8-652">*Nieobsługiwane w Meksyku*</span><span class="sxs-lookup"><span data-stu-id="956f8-652">*Not supported by Mexico*</span></span> |

### <a name="bank-account-type"></a><span data-ttu-id="956f8-653">Typ konta bankowego</span><span class="sxs-lookup"><span data-stu-id="956f8-653">Bank account type</span></span>

<span data-ttu-id="956f8-654">Typy kont bankowych są wykorzystywane w płatnościach elektronicznych dla pracowników.</span><span class="sxs-lookup"><span data-stu-id="956f8-654">Bank account types are used for electronic payments to employees.</span></span> <span data-ttu-id="956f8-655">Typy kont bankowych są mapowane do systemu Dayforce jako informacje o koncie do przelewów.</span><span class="sxs-lookup"><span data-stu-id="956f8-655">Bank account types are mapped to Dayforce as transfer account information.</span></span> <span data-ttu-id="956f8-656">Typy kont bankowych są w razie potrzeby tłumaczone na akceptowane wartości podczas integracji.</span><span class="sxs-lookup"><span data-stu-id="956f8-656">The bank account types are translated, as appropriate, to the accepted values upon integration.</span></span>

| <span data-ttu-id="956f8-657">Talent</span><span class="sxs-lookup"><span data-stu-id="956f8-657">Talent</span></span>            | <span data-ttu-id="956f8-658">Dayforce</span><span class="sxs-lookup"><span data-stu-id="956f8-658">Dayforce</span></span>                  |
|-------------------|---------------------------|
| <span data-ttu-id="956f8-659">Konto czekowe</span><span class="sxs-lookup"><span data-stu-id="956f8-659">Checking Account</span></span>  | <span data-ttu-id="956f8-660">CheckingAccount</span><span class="sxs-lookup"><span data-stu-id="956f8-660">CheckingAccount</span></span>           |
| <span data-ttu-id="956f8-661">Konto listy płac</span><span class="sxs-lookup"><span data-stu-id="956f8-661">Payroll Account</span></span>   | <span data-ttu-id="956f8-662">PayrollAccount</span><span class="sxs-lookup"><span data-stu-id="956f8-662">PayrollAccount</span></span>            |
| <span data-ttu-id="956f8-663">Konto oszczędnościowe</span><span class="sxs-lookup"><span data-stu-id="956f8-663">Savings Account</span></span>   | <span data-ttu-id="956f8-664">*Nieobsługiwane w Meksyku*</span><span class="sxs-lookup"><span data-stu-id="956f8-664">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="956f8-665">Konto BankGirot</span><span class="sxs-lookup"><span data-stu-id="956f8-665">BankGirot account</span></span> | <span data-ttu-id="956f8-666">*Nieobsługiwane w Meksyku*</span><span class="sxs-lookup"><span data-stu-id="956f8-666">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="956f8-667">Konto PlusGirot</span><span class="sxs-lookup"><span data-stu-id="956f8-667">PlusGirot account</span></span> | <span data-ttu-id="956f8-668">*Nieobsługiwane w Meksyku*</span><span class="sxs-lookup"><span data-stu-id="956f8-668">*Not supported by Mexico*</span></span> |

### <a name="earning-codes"></a><span data-ttu-id="956f8-669">Kody zarobków</span><span class="sxs-lookup"><span data-stu-id="956f8-669">Earning codes</span></span>

<span data-ttu-id="956f8-670">Kody zarobków jednoznacznie identyfikują każdy rodzaj dochodów, które otrzymują pracownicy.</span><span class="sxs-lookup"><span data-stu-id="956f8-670">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="956f8-671">Kody mają różne parametry związane z zarobkami, takie jak reguły księgowania, przepisy podatkowe, wymagania dotyczące raportowania i możliwość zwiększania wartości brutto.</span><span class="sxs-lookup"><span data-stu-id="956f8-671">The codes cover several parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span> <span data-ttu-id="956f8-672">W razie ustawienia nieobsługiwanej częstotliwości domyślnie w obliczeniu będzie używana częstotliwość **Każda wypłata**.</span><span class="sxs-lookup"><span data-stu-id="956f8-672">If an unsupported frequency is used, the **Every Pay** frequency is used by default for the calculation.</span></span>

#### <a name="supported-frequencies"></a><span data-ttu-id="956f8-673">Obsługiwane częstotliwości</span><span class="sxs-lookup"><span data-stu-id="956f8-673">Supported frequencies</span></span>

- <span data-ttu-id="956f8-674">Wszyscy</span><span class="sxs-lookup"><span data-stu-id="956f8-674">All</span></span>
- <span data-ttu-id="956f8-675">EVERYPAY</span><span class="sxs-lookup"><span data-stu-id="956f8-675">EVERYPAY</span></span>
- <span data-ttu-id="956f8-676">EACHPAYPERIOD</span><span class="sxs-lookup"><span data-stu-id="956f8-676">EACHPAYPERIOD</span></span>
- <span data-ttu-id="956f8-677">EVRYOTHRPAYODD</span><span class="sxs-lookup"><span data-stu-id="956f8-677">EVRYOTHRPAYODD</span></span>
- <span data-ttu-id="956f8-678">EVRYOTHRPAYEVN</span><span class="sxs-lookup"><span data-stu-id="956f8-678">EVRYOTHRPAYEVN</span></span>
- <span data-ttu-id="956f8-679">1OFMTH</span><span class="sxs-lookup"><span data-stu-id="956f8-679">1OFMTH</span></span>
- <span data-ttu-id="956f8-680">LASTOFMTH</span><span class="sxs-lookup"><span data-stu-id="956f8-680">LASTOFMTH</span></span>
- <span data-ttu-id="956f8-681">2OFMTH</span><span class="sxs-lookup"><span data-stu-id="956f8-681">2OFMTH</span></span>
- <span data-ttu-id="956f8-682">3OFMTH</span><span class="sxs-lookup"><span data-stu-id="956f8-682">3OFMTH</span></span>
- <span data-ttu-id="956f8-683">4OFMTH</span><span class="sxs-lookup"><span data-stu-id="956f8-683">4OFMTH</span></span>
- <span data-ttu-id="956f8-684">5OFMTH</span><span class="sxs-lookup"><span data-stu-id="956f8-684">5OFMTH</span></span>
- <span data-ttu-id="956f8-685">1N2OFMTH</span><span class="sxs-lookup"><span data-stu-id="956f8-685">1N2OFMTH</span></span>
- <span data-ttu-id="956f8-686">3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="956f8-686">3N4OFMTH</span></span>
- <span data-ttu-id="956f8-687">1N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="956f8-687">1N3OFMTH</span></span>
- <span data-ttu-id="956f8-688">1N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="956f8-688">1N4OFMTH</span></span>
- <span data-ttu-id="956f8-689">2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="956f8-689">2N3OFMTH</span></span>
- <span data-ttu-id="956f8-690">2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="956f8-690">2N4OFMTH</span></span>
- <span data-ttu-id="956f8-691">1N2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="956f8-691">1N2N3OFMTH</span></span>
- <span data-ttu-id="956f8-692">1N2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="956f8-692">1N2N4OFMTH</span></span>
- <span data-ttu-id="956f8-693">1N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="956f8-693">1N3N4OFMTH</span></span>
- <span data-ttu-id="956f8-694">2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="956f8-694">2N3N4OFMTH</span></span>
- <span data-ttu-id="956f8-695">1N2N3N4OFMTH – 1N2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="956f8-695">1N2N3N4OFMTH - 1N2N3N4OFMTH</span></span>
- <span data-ttu-id="956f8-696">2N3N4N5OFMth – 2N3N4N5OFMth</span><span class="sxs-lookup"><span data-stu-id="956f8-696">2N3N4N5OFMth - 2N3N4N5OFMth</span></span>
- <span data-ttu-id="956f8-697">1OFQTR – 1OFQTR</span><span class="sxs-lookup"><span data-stu-id="956f8-697">1OFQTR - 1OFQTR</span></span>
- <span data-ttu-id="956f8-698">LASTOFQTR – LASTOFQTR</span><span class="sxs-lookup"><span data-stu-id="956f8-698">LASTOFQTR – LASTOFQTR</span></span>
- <span data-ttu-id="956f8-699">LASTMTHOFQTR – LASTMTHOFQTR</span><span class="sxs-lookup"><span data-stu-id="956f8-699">LASTMTHOFQTR – LASTMTHOFQTR</span></span>
- <span data-ttu-id="956f8-700">1OFYEAR – 1OFYEAR</span><span class="sxs-lookup"><span data-stu-id="956f8-700">1OFYEAR - 1OFYEAR</span></span>
- <span data-ttu-id="956f8-701">LASTOFYEAR – LASTOFYEAR</span><span class="sxs-lookup"><span data-stu-id="956f8-701">LASTOFYEAR – LASTOFYEAR</span></span>
- <span data-ttu-id="956f8-702">NOVNDECOFYEAR – NOVNDECOFYEAR</span><span class="sxs-lookup"><span data-stu-id="956f8-702">NOVNDECOFYEAR - NOVNDECOFYEAR</span></span>

### <a name="addresses"></a><span data-ttu-id="956f8-703">Adresy</span><span class="sxs-lookup"><span data-stu-id="956f8-703">Addresses</span></span>

<span data-ttu-id="956f8-704">Identyfikacja określonych kodów kraju lub regionu, województwa i powiatu (gminy) wymaga określonych formatów, które potrafi rozpoznać system Dayforce oraz dostawcy wewnątrz krajów/regionów.</span><span class="sxs-lookup"><span data-stu-id="956f8-704">The identification of specific country or region, state, and county (municipality) codes requires specific formats that Dayforce and in-country/in-region providers can recognize.</span></span> <span data-ttu-id="956f8-705">Co prawda format nazw miejscowości jest elastyczny, ale każda miejscowość musi być skojarzona z województwem.</span><span class="sxs-lookup"><span data-stu-id="956f8-705">Although the format for cities is flexible, every city must be associated with a state.</span></span>

| <span data-ttu-id="956f8-706">Talent</span><span class="sxs-lookup"><span data-stu-id="956f8-706">Talent</span></span>              | <span data-ttu-id="956f8-707">Dayforce</span><span class="sxs-lookup"><span data-stu-id="956f8-707">Dayforce</span></span>              |
|---------------------|-----------------------|
| <span data-ttu-id="956f8-708">Kraj/region</span><span class="sxs-lookup"><span data-stu-id="956f8-708">Country/Region</span></span>      | <span data-ttu-id="956f8-709">Kod kraju</span><span class="sxs-lookup"><span data-stu-id="956f8-709">Country Code</span></span>          |
| <span data-ttu-id="956f8-710">Kod pocztowy</span><span class="sxs-lookup"><span data-stu-id="956f8-710">Zip/Postal Code</span></span>     | <span data-ttu-id="956f8-711">Kod pocztowy</span><span class="sxs-lookup"><span data-stu-id="956f8-711">Postal Code</span></span>           |
| <span data-ttu-id="956f8-712">Stanowy</span><span class="sxs-lookup"><span data-stu-id="956f8-712">State</span></span>               | <span data-ttu-id="956f8-713">Kod województwa</span><span class="sxs-lookup"><span data-stu-id="956f8-713">State Code</span></span>            |
| <span data-ttu-id="956f8-714">Miejscowość</span><span class="sxs-lookup"><span data-stu-id="956f8-714">City</span></span>                | <span data-ttu-id="956f8-715">Miejscowość</span><span class="sxs-lookup"><span data-stu-id="956f8-715">City</span></span>                  |
| <span data-ttu-id="956f8-716">Powiat</span><span class="sxs-lookup"><span data-stu-id="956f8-716">County</span></span>              | <span data-ttu-id="956f8-717">Powiat (gmina)</span><span class="sxs-lookup"><span data-stu-id="956f8-717">County (Municipality)</span></span> |
| <span data-ttu-id="956f8-718">Ulica</span><span class="sxs-lookup"><span data-stu-id="956f8-718">Street</span></span>              | <span data-ttu-id="956f8-719">Wiersz adresu 1</span><span class="sxs-lookup"><span data-stu-id="956f8-719">Address Line 1</span></span>        |
| <span data-ttu-id="956f8-720">Numer budynku</span><span class="sxs-lookup"><span data-stu-id="956f8-720">Street Number</span></span>       | <span data-ttu-id="956f8-721">Wiersz adresu 2</span><span class="sxs-lookup"><span data-stu-id="956f8-721">Address Line 2</span></span>        |
| <span data-ttu-id="956f8-722">Dodatkowe określenie budynku</span><span class="sxs-lookup"><span data-stu-id="956f8-722">Building Complement</span></span> | <span data-ttu-id="956f8-723">Wiersz adresu 5</span><span class="sxs-lookup"><span data-stu-id="956f8-723">Address Line 5</span></span>        |

### <a name="passport-number"></a><span data-ttu-id="956f8-724">Numer paszportu</span><span class="sxs-lookup"><span data-stu-id="956f8-724">Passport number</span></span>

<span data-ttu-id="956f8-725">Pracownicy mogą podać informacje z paszportów.</span><span class="sxs-lookup"><span data-stu-id="956f8-725">Employees can declare passport information.</span></span> <span data-ttu-id="956f8-726">Te informacje mają typ identyfikacji **Paszport** i są integrowane z systemem Dayforce w ramach danych pracowników specyficznych dla Meksyku.</span><span class="sxs-lookup"><span data-stu-id="956f8-726">This information is of the **Passport** identification type and is integrated into Dayforce as part of an employee's Mexico-specific information.</span></span>

- <span data-ttu-id="956f8-727">Typ identyfikacji = „Paszport”</span><span class="sxs-lookup"><span data-stu-id="956f8-727">Identification Type = "Passport"</span></span>
- <span data-ttu-id="956f8-728">Data wystawienia</span><span class="sxs-lookup"><span data-stu-id="956f8-728">Issued Date</span></span>
- <span data-ttu-id="956f8-729">Data ważności</span><span class="sxs-lookup"><span data-stu-id="956f8-729">Expiration Date</span></span>

<span data-ttu-id="956f8-730">Pracownicy mogą zadeklarować wiele numerów identyfikacyjnych typu **Paszport**.</span><span class="sxs-lookup"><span data-stu-id="956f8-730">Employees can declare multiple identification numbers of the **Passport** identification type.</span></span> <span data-ttu-id="956f8-731">Jednak tylko obecnie aktywny wpis paszportu jest integrowany z usługą Dayforce.</span><span class="sxs-lookup"><span data-stu-id="956f8-731">However, only the current active passport entry is integrated into Dayforce.</span></span> <span data-ttu-id="956f8-732">Jeśli wszystkie wpisy paszportów wygasły, z systemem Dayforce zostanie zintegrowany ostatnio wystawiony paszport.</span><span class="sxs-lookup"><span data-stu-id="956f8-732">If all passport entries are expired, the passport that was most recently issued is integrated into Dayforce.</span></span>
