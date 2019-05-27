---
title: Konfigurowanie integracji listy płac między rozwiązaniami Talent i Dayforce
description: W tym temacie wyjaśniono sposób konfigurowania integracji między programami Microsoft Dynamics 365 for Talent i Ceridian Dayforce, dzięki czemu można przetwarzać sekcję płatności.
author: andreabichsel
manager: AnnBe
ms.date: 03/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 9a88bf61dbb12520b555ceb7363b1c646d95386e
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/07/2019
ms.locfileid: "1518796"
---
# <a name="configure-the-payroll-integration-between-talent-and-dayforce"></a><span data-ttu-id="dbd3f-103">Konfigurowanie integracji listy płac między rozwiązaniami Talent i Dayforce</span><span class="sxs-lookup"><span data-stu-id="dbd3f-103">Configure the payroll integration between Talent and Dayforce</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="dbd3f-104">Integracja między programami Microsoft Dynamics 365 for Talent i Ceridian Dayforce opiera się na kilku krokach konfiguracji, które opisano w tym temacie.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-104">The integration between Microsoft Dynamics 365 for Talent and Ceridian Dayforce relies on several configuration steps that are described in this topic.</span></span> <span data-ttu-id="dbd3f-105">Aby można było przetwarzać sesję płatności, należy skonfigurować integrację w rozwiązaniach Talent i Dayforce.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-105">You must configure the integration in both Talent and Dayforce before you can process a pay run.</span></span>

<span data-ttu-id="dbd3f-106">Jeśli korzystasz z usługi takiej jak Dayforce do realizowania sesji płatności, należy włączyć integrację w aplikacji Talent.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-106">When you use a service such as Dayforce to complete pay runs, you must enable the integration in Talent.</span></span> <span data-ttu-id="dbd3f-107">Integracja wymaga określonych danych z programu Talent.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-107">The integration requires specific data from Talent.</span></span> <span data-ttu-id="dbd3f-108">W związku z tym należy sprawdzić, czy dane mapowane do systemu Dayforce są skonfigurowano w aplikacji Talent w sposób zapewniający obsługę integracji.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-108">Therefore, you must verify that data that is mapped to Dayforce is configured in Talent in a manner that supports the integration.</span></span> <span data-ttu-id="dbd3f-109">Integracja wykorzystuje następujące ogólne kategorie danych:</span><span class="sxs-lookup"><span data-stu-id="dbd3f-109">The integration uses the following broad categories of data:</span></span>

- <span data-ttu-id="dbd3f-110">Dane kadrowe</span><span class="sxs-lookup"><span data-stu-id="dbd3f-110">Human resources data</span></span>
- <span data-ttu-id="dbd3f-111">Dane o wynagrodzeniach</span><span class="sxs-lookup"><span data-stu-id="dbd3f-111">Compensation data</span></span>
- <span data-ttu-id="dbd3f-112">Dane listy płac, takie jak cykle kalkulacji płac, okresy kalkulacji płac i kody zarobków</span><span class="sxs-lookup"><span data-stu-id="dbd3f-112">Payroll data, such as pay cycles, pay periods, and earning codes</span></span>
- <span data-ttu-id="dbd3f-113">Dane pracowników</span><span class="sxs-lookup"><span data-stu-id="dbd3f-113">Worker data</span></span>

<span data-ttu-id="dbd3f-114">W tym temacie opisano czynności, które należy wykonać, aby włączyć integrację.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-114">This topic describes the steps that you must follow to enable the integration.</span></span> <span data-ttu-id="dbd3f-115">Objaśniono tu także typy danych i szczegóły konfiguracji, których wymaga integracja.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-115">It also explains the types of data and the configuration details that the integration requires.</span></span>

## <a name="enable-the-integration"></a><span data-ttu-id="dbd3f-116">Włączanie integracji</span><span class="sxs-lookup"><span data-stu-id="dbd3f-116">Enable the integration</span></span>

<span data-ttu-id="dbd3f-117">W aplikacji Talent należy włączyć funkcję integracji i wprowadzić informacje konfiguracyjne w celu nawiązania połączenia z systemem Dayforce.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-117">In Talent, you must turn on the integration and enter the configuration information to connect to Dayforce.</span></span> <span data-ttu-id="dbd3f-118">Jeśli chcesz, aby generowane transakcje księgi głównej były importowane do programu Microsoft Dynamics 365 for Finance and Operations, należy także skonfigurować konto magazynu w usłudze Microsoft Azure oraz wprowadzić ciąg połączenia z usługą Azure Storage w aplikacji Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-118">If you want the general ledger transaction that is produced to be imported into Microsoft Dynamics 365 for Finance and Operations, you must also set up a Microsoft Azure storage account and enter the Azure Storage connection string in Finance and Operations.</span></span>

<span data-ttu-id="dbd3f-119">Aby włączyć integrację w aplikacji Talent, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-119">To turn on the integration in Talent, follow these steps.</span></span>

1. <span data-ttu-id="dbd3f-120">Na stronie **Administrowanie systemem** wybierz opcję **Konfiguracja integracji**.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-120">On the **System administration** page, select **Integration configuration**.</span></span>
2. <span data-ttu-id="dbd3f-121">Wprowadź punkt końcowy objęty bezpiecznym protokołem FTP (File Transfer Protocol) i ścieżkę do folderu objętego bezpiecznym protokołem FTP.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-121">Enter the secure File Transfer Protocol (FTP) endpoint and the secure FTP folder path.</span></span>
3. <span data-ttu-id="dbd3f-122">Wprowadź nazwę użytkownika i hasło użytkownika, który będzie uzyskiwał dostęp do punktu końcowego i ścieżki folderu objętych bezpiecznym protokołem FTP.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-122">Enter the user name and password of the user who will access the secure FTP endpoint and folder path.</span></span>
4. <span data-ttu-id="dbd3f-123">Przetestuj połączenie, a w opcji **Włącz integrację listy płac** ustaw wartość **Tak**.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-123">Test the connection, as required, and set the **Enable payroll integration** option to **Yes**.</span></span>

<span data-ttu-id="dbd3f-124">Po włączeniu integracji następuje utworzenie pakietu i plików eksportu danych oraz ustawienie częstotliwości.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-124">When the integration is turned on, the data export package and files are created, and the frequency is set.</span></span> <span data-ttu-id="dbd3f-125">W razie potrzeby można zmienić tę częstotliwość.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-125">You can change this frequency as you require.</span></span>

<span data-ttu-id="dbd3f-126">Aby uzyskać więcej informacji o kontach magazynu w usłudze Azure i ciągach połączeń z usługą Azure Storage, zobacz następujące tematy poświęcone usłudze Azure:</span><span class="sxs-lookup"><span data-stu-id="dbd3f-126">For more information about Azure storage accounts and Azure Storage connection strings, see the following Azure topics:</span></span>

- [<span data-ttu-id="dbd3f-127">Konta magazynu w usłudze Azure — informacje</span><span class="sxs-lookup"><span data-stu-id="dbd3f-127">About Azure storage accounts</span></span>](https://docs.microsoft.com/en-us/azure/storage/common/storage-create-storage-account?toc=%2fazure%2fstorage%2ffiles%2ftoc.json)
- [<span data-ttu-id="dbd3f-128">Konfigurowanie ciągów połączeń z usługą Azure Storage</span><span class="sxs-lookup"><span data-stu-id="dbd3f-128">Configure Azure Storage connection strings</span></span>](https://docs.microsoft.com/en-us/azure/storage/common/storage-configure-connection-string)

## <a name="configure-your-data"></a><span data-ttu-id="dbd3f-129">Konfigurowanie danych</span><span class="sxs-lookup"><span data-stu-id="dbd3f-129">Configure your data</span></span> 

<span data-ttu-id="dbd3f-130">Aby przetwarzać listę płac, należy skonfigurować dane kadrowe w aplikacji Talent.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-130">To process payroll, you must configure human resource data in Talent.</span></span> <span data-ttu-id="dbd3f-131">Należy skonfigurować dane organizacyjne, takie jak funkcje i stanowiska, oraz informacje o wynagrodzeniach i świadczeniach.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-131">You must set up organizational data, such as jobs and positions, together with benefits and compensation information.</span></span> <span data-ttu-id="dbd3f-132">Informacje te stanowią zasób danych o zatrudnieniu, wynagrodzeniach i potrąceniach, które są wymagane do wygenerowania płacy pracownika.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-132">This information provides the employment, pay, and deduction information that is required in order to generate employee pay.</span></span>

### <a name="human-resource-data"></a><span data-ttu-id="dbd3f-133">Dane kadrowe</span><span class="sxs-lookup"><span data-stu-id="dbd3f-133">Human resource data</span></span>

#### <a name="benefits"></a><span data-ttu-id="dbd3f-134">Świadczenia</span><span class="sxs-lookup"><span data-stu-id="dbd3f-134">Benefits</span></span> 

<span data-ttu-id="dbd3f-135">Moduł Zasoby ludzkie oferuje narzędzia do konfigurowania i obsługi świadczeń, potrąceń i planów wynagrodzeń pracowników, które organizacja oferuje swoim pracownikom lub przetwarza w ich imieniu.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-135">Human resources provides tools for the setup and maintenance of the benefits, deductions, and worker compensation plans that an organization offers or processes for its workers.</span></span>

<span data-ttu-id="dbd3f-136">Podczas tworzenia świadczeń należy wziąć pod uwagę następujące dane i konfiguracje używane w systemie Dayforce.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-136">When you create benefits, keep in mind the following data and configurations that are used in Dayforce.</span></span>

##### <a name="benefit-plans"></a><span data-ttu-id="dbd3f-137">Plany świadczeń</span><span class="sxs-lookup"><span data-stu-id="dbd3f-137">Benefit plans</span></span>

- <span data-ttu-id="dbd3f-138">Plan (wymagane)</span><span class="sxs-lookup"><span data-stu-id="dbd3f-138">Plan (required)</span></span>
- <span data-ttu-id="dbd3f-139">Typ (wymagane)</span><span class="sxs-lookup"><span data-stu-id="dbd3f-139">Type (required)</span></span>
- <span data-ttu-id="dbd3f-140">Wpływ na listę płac (wymagane)</span><span class="sxs-lookup"><span data-stu-id="dbd3f-140">Payroll impact (required)</span></span>
- <span data-ttu-id="dbd3f-141">Odzyskaj zaległości</span><span class="sxs-lookup"><span data-stu-id="dbd3f-141">Recover arrears</span></span>
- <span data-ttu-id="dbd3f-142">Metoda potrącenia</span><span class="sxs-lookup"><span data-stu-id="dbd3f-142">Deduction method</span></span>
- <span data-ttu-id="dbd3f-143">Priorytet potrącenia</span><span class="sxs-lookup"><span data-stu-id="dbd3f-143">Deduction priority</span></span>
- <span data-ttu-id="dbd3f-144">Okres limitu</span><span class="sxs-lookup"><span data-stu-id="dbd3f-144">Limit period</span></span>
- <span data-ttu-id="dbd3f-145">Kwota limitu</span><span class="sxs-lookup"><span data-stu-id="dbd3f-145">Limit amount</span></span>

##### <a name="benefits"></a><span data-ttu-id="dbd3f-146">Świadczenia</span><span class="sxs-lookup"><span data-stu-id="dbd3f-146">Benefits</span></span>

- <span data-ttu-id="dbd3f-147">Plan (wymagane)</span><span class="sxs-lookup"><span data-stu-id="dbd3f-147">Plan (required)</span></span>
- <span data-ttu-id="dbd3f-148">Typ (wymagane)</span><span class="sxs-lookup"><span data-stu-id="dbd3f-148">Type (required)</span></span>
- <span data-ttu-id="dbd3f-149">Opcja (wymagane)</span><span class="sxs-lookup"><span data-stu-id="dbd3f-149">Option (required)</span></span>
- <span data-ttu-id="dbd3f-150">Identyfikator świadczenia (wymagane)</span><span class="sxs-lookup"><span data-stu-id="dbd3f-150">Benefit ID (required)</span></span>
- <span data-ttu-id="dbd3f-151">Częstotliwość</span><span class="sxs-lookup"><span data-stu-id="dbd3f-151">Frequency</span></span>
- <span data-ttu-id="dbd3f-152">Podstawa</span><span class="sxs-lookup"><span data-stu-id="dbd3f-152">Basis</span></span>
- <span data-ttu-id="dbd3f-153">Kwota lub stawka</span><span class="sxs-lookup"><span data-stu-id="dbd3f-153">Amount or rate</span></span>
- <span data-ttu-id="dbd3f-154">Kod zarobków</span><span class="sxs-lookup"><span data-stu-id="dbd3f-154">Earning code</span></span>

##### <a name="supported-frequencies"></a><span data-ttu-id="dbd3f-155">Obsługiwane częstotliwości</span><span class="sxs-lookup"><span data-stu-id="dbd3f-155">Supported frequencies</span></span> 

- <span data-ttu-id="dbd3f-156">Tygodniowa</span><span class="sxs-lookup"><span data-stu-id="dbd3f-156">Weekly</span></span>
- <span data-ttu-id="dbd3f-157">Co dwa tygodnie</span><span class="sxs-lookup"><span data-stu-id="dbd3f-157">Bi-weekly</span></span>
- <span data-ttu-id="dbd3f-158">Co pół miesiąca</span><span class="sxs-lookup"><span data-stu-id="dbd3f-158">Semi-monthly</span></span>
- <span data-ttu-id="dbd3f-159">Miesięczne</span><span class="sxs-lookup"><span data-stu-id="dbd3f-159">Monthly</span></span>

##### <a name="supported-bases"></a><span data-ttu-id="dbd3f-160">Obsługiwane podstawy</span><span class="sxs-lookup"><span data-stu-id="dbd3f-160">Supported bases</span></span> 

- <span data-ttu-id="dbd3f-161">Stała kwota</span><span class="sxs-lookup"><span data-stu-id="dbd3f-161">Fixed amount</span></span>
- <span data-ttu-id="dbd3f-162">Procent zarobków</span><span class="sxs-lookup"><span data-stu-id="dbd3f-162">Percent of earnings</span></span>
- <span data-ttu-id="dbd3f-163">Godziny płatne</span><span class="sxs-lookup"><span data-stu-id="dbd3f-163">Productive hours</span></span>

<span data-ttu-id="dbd3f-164">System Dayforce tworzy następujące potrącenia w oparciu o wpływ na listę płac zdefiniowany w planie świadczeń.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-164">Dayforce creates the following deductions, based on the payroll impact that is defined on the benefit plan.</span></span>

| <span data-ttu-id="dbd3f-165">Wybór w aplikacji Talent</span><span class="sxs-lookup"><span data-stu-id="dbd3f-165">Selection in Talent</span></span>        | <span data-ttu-id="dbd3f-166">Wynik w systemie Dayforce</span><span class="sxs-lookup"><span data-stu-id="dbd3f-166">Result in Dayforce</span></span>                            |
|----------------------------|-----------------------------------------------|
| <span data-ttu-id="dbd3f-167">None</span><span class="sxs-lookup"><span data-stu-id="dbd3f-167">None</span></span>                       | <span data-ttu-id="dbd3f-168">Nie jest tworzone żadne potrącenie</span><span class="sxs-lookup"><span data-stu-id="dbd3f-168">No deduction is created.</span></span>                      |
| <span data-ttu-id="dbd3f-169">Tylko potrącenie</span><span class="sxs-lookup"><span data-stu-id="dbd3f-169">Deduction only</span></span>             | <span data-ttu-id="dbd3f-170">Jest tworzone potrącenie od pracownika.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-170">An employee deduction is created.</span></span>             |
| <span data-ttu-id="dbd3f-171">Tylko udział</span><span class="sxs-lookup"><span data-stu-id="dbd3f-171">Contribution only</span></span>          | <span data-ttu-id="dbd3f-172">Jest tworzone potrącenie od pracodawcy.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-172">An employer deduction is created.</span></span>             |
| <span data-ttu-id="dbd3f-173">Potrącenie i udział</span><span class="sxs-lookup"><span data-stu-id="dbd3f-173">Deduction and contribution</span></span> | <span data-ttu-id="dbd3f-174">Są tworzone potrącenia od pracownika i pracodawcy.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-174">Employee and employer deductions are created.</span></span> |

<span data-ttu-id="dbd3f-175">Aby uzyskać więcej informacji o sposobie definiowania programu świadczeń i zarządzania nim, zobacz następujące tematy:</span><span class="sxs-lookup"><span data-stu-id="dbd3f-175">For more information about how to define and manage a benefits program, see the following topics:</span></span>

- [<span data-ttu-id="dbd3f-176">Dostarczanie programu świadczeń dla pracowników</span><span class="sxs-lookup"><span data-stu-id="dbd3f-176">Deliver an employee benefits program</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/deliver-employee-benefits-program)
- [<span data-ttu-id="dbd3f-177">Tworzenie nowego świadczenia</span><span class="sxs-lookup"><span data-stu-id="dbd3f-177">Create a new benefit</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/create-new-benefit)
- [<span data-ttu-id="dbd3f-178">Definiowanie zasad i reguł uprawnień do świadczenia</span><span class="sxs-lookup"><span data-stu-id="dbd3f-178">Define benefit eligibility rules and policies</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-benefit-eligibility-rules-policies)
- [<span data-ttu-id="dbd3f-179">Rejestrowanie i usuwanie świadczeń dla pracowników</span><span class="sxs-lookup"><span data-stu-id="dbd3f-179">Enroll and remove benefits from workers</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-remove-benefits-workers)

#### <a name="compensation"></a><span data-ttu-id="dbd3f-180">Wynagrodzenie</span><span class="sxs-lookup"><span data-stu-id="dbd3f-180">Compensation</span></span> 

<span data-ttu-id="dbd3f-181">Zarządzanie wynagrodzeniami służy do kontrolowania wypłat podstawowego wynagrodzenia i nagród.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-181">Compensation management is used to control the delivery of base pay and awards.</span></span> <span data-ttu-id="dbd3f-182">Stałe podstawowe wynagrodzenie pracownika i podwyżki podstawowego wynagrodzenia są kontrolowane przez plany stałych wynagrodzeń.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-182">An employee's fixed base pay and merit increases are controlled through fixed compensation plans.</span></span> <span data-ttu-id="dbd3f-183">Płatności motywacyjne, takie jak premie motywacyjne, wypłaty premii, nagrody za wyniki pracy, prawa do nabycia akcji po ustalonej cenie, cesje i nagrody jednorazowe lub okazjonalne są kontrolowane za pomocą systemów wynagrodzeń o zmiennej wysokości.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-183">The payment of incentive pay, such as bonus payments, performance awards, stock options, and grants, and also one-time awards, are controlled through variable compensation plans.</span></span>

<span data-ttu-id="dbd3f-184">Program Dayforce wykorzystuje informacje o wynagrodzeniach do obliczania godzinowej lub rocznej stawki pracownika.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-184">Dayforce uses compensation information to calculate an employee's hourly or annual rate.</span></span> <span data-ttu-id="dbd3f-185">Określenie systemów stałych wynagrodzeń i konwersji stawek płac jest wymagane.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-185">Fixed compensation plans and pay rate conversions are required.</span></span> <span data-ttu-id="dbd3f-186">Pracownicy muszą być skojarzeni z systemem stałych wynagrodzeń.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-186">Employees must be associated with a fixed compensation plan.</span></span>

<span data-ttu-id="dbd3f-187">Aby uzyskać więcej informacji o planach wynagrodzeń, zobacz następujące tematy:</span><span class="sxs-lookup"><span data-stu-id="dbd3f-187">For more information about compensation plans, see the following topics:</span></span>

- [<span data-ttu-id="dbd3f-188">Tworzenie planów stałych wynagrodzeń</span><span class="sxs-lookup"><span data-stu-id="dbd3f-188">Create fixed compensation plans</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/create-fixed-compensation-plans)
- [<span data-ttu-id="dbd3f-189">Tworzenie planów wynagrodzeń o zmiennej wysokości</span><span class="sxs-lookup"><span data-stu-id="dbd3f-189">Create variable compensation plans</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/create-variable-compensation-plans)
- [<span data-ttu-id="dbd3f-190">Opracowywanie struktury i planu pensji/wynagrodzeń</span><span class="sxs-lookup"><span data-stu-id="dbd3f-190">Develop salary/compensation structure and plans</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/develop-salary-compensation-structure-plan)
- [<span data-ttu-id="dbd3f-191">Przetwarzanie wynagrodzenia</span><span class="sxs-lookup"><span data-stu-id="dbd3f-191">Process compensation</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/process-compensation)
- [<span data-ttu-id="dbd3f-192">Definiowanie procesu związanego z wynagrodzeniem i obliczanie wyników</span><span class="sxs-lookup"><span data-stu-id="dbd3f-192">Define compensation process and calculate results</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-compensation-process-calculate-results)
- [<span data-ttu-id="dbd3f-193">Zarejestrowanie pracownika w systemie stałych wynagrodzeń</span><span class="sxs-lookup"><span data-stu-id="dbd3f-193">Enroll an employee in a fixed compensation plan</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-fixed-compensation-plan)
- [<span data-ttu-id="dbd3f-194">Zarejestrowanie pracownika w systemie wynagrodzeń o zmiennej wysokości</span><span class="sxs-lookup"><span data-stu-id="dbd3f-194">Enroll an employee in a variable compensation plan</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-variable-compensation-plan)

#### <a name="jobs"></a><span data-ttu-id="dbd3f-195">Funkcje</span><span class="sxs-lookup"><span data-stu-id="dbd3f-195">Jobs</span></span> 

<span data-ttu-id="dbd3f-196">Funkcja to zbiór zadań i obowiązków, które są wymagane od osoby wykonującej funkcję.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-196">A job is a collection of the tasks and responsibilities that are required of a person who performs a job.</span></span> <span data-ttu-id="dbd3f-197">Aby uzyskać więcej informacji, zobacz następujące tematy:</span><span class="sxs-lookup"><span data-stu-id="dbd3f-197">For more information, see the following topics:</span></span>

- [<span data-ttu-id="dbd3f-198">Konfigurowanie składników funkcji</span><span class="sxs-lookup"><span data-stu-id="dbd3f-198">Setting up the components of a job</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/create-job)
- [<span data-ttu-id="dbd3f-199">Definiowanie nowych zadań</span><span class="sxs-lookup"><span data-stu-id="dbd3f-199">Define new jobs</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-jobs)

##### <a name="positions"></a><span data-ttu-id="dbd3f-200">Pozycje</span><span class="sxs-lookup"><span data-stu-id="dbd3f-200">Positions</span></span>

<span data-ttu-id="dbd3f-201">Pozycja jest pojedynczym wystąpieniem zadania.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-201">A position is an individual instance of a job.</span></span> <span data-ttu-id="dbd3f-202">Na przykład stanowisko „Menedżer ds. sprzedaży (Wschód)” jest jednym ze stanowisk skojarzonych z funkcją „Menedżer ds. sprzedaży”.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-202">For example, the "Sales manager (East)" position is one of the positions that are associated with the "Sales manager" job.</span></span> <span data-ttu-id="dbd3f-203">Stanowisko istnieje w dziale.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-203">A position exists in a department.</span></span> <span data-ttu-id="dbd3f-204">Z każdym stanowiskiem może być skojarzony tylko jeden pracownik.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-204">Only one worker can be associated with each position.</span></span>

<span data-ttu-id="dbd3f-205">Podczas konfigurowania stanowisk pamiętaj o następujących danych i konfiguracjach:</span><span class="sxs-lookup"><span data-stu-id="dbd3f-205">Keep the following data and configuration in mind when you set up positions:</span></span>

- <span data-ttu-id="dbd3f-206">Stanowisko (wymagane)</span><span class="sxs-lookup"><span data-stu-id="dbd3f-206">Position (required)</span></span>
- <span data-ttu-id="dbd3f-207">Opis (wymagane)</span><span class="sxs-lookup"><span data-stu-id="dbd3f-207">Description (required)</span></span>
- <span data-ttu-id="dbd3f-208">Funkcja (wymagane)</span><span class="sxs-lookup"><span data-stu-id="dbd3f-208">Job (required)</span></span>
- <span data-ttu-id="dbd3f-209">Dział (wymagane)</span><span class="sxs-lookup"><span data-stu-id="dbd3f-209">Department (required)</span></span>
- <span data-ttu-id="dbd3f-210">Typ stanowiska (wymagane)</span><span class="sxs-lookup"><span data-stu-id="dbd3f-210">Position type (required)</span></span>
- <span data-ttu-id="dbd3f-211">W przeliczeniu na pełne etaty</span><span class="sxs-lookup"><span data-stu-id="dbd3f-211">Full-time equivalent</span></span>
- <span data-ttu-id="dbd3f-212">Zwykłe godziny (rocznie) (wymagane)</span><span class="sxs-lookup"><span data-stu-id="dbd3f-212">Annual regular hours (required)</span></span>
- <span data-ttu-id="dbd3f-213">Zapłacone przez firmę (wymagane)</span><span class="sxs-lookup"><span data-stu-id="dbd3f-213">Paid by legal entity (required)</span></span>
- <span data-ttu-id="dbd3f-214">Cykl kalkulacji płac (wymagane)</span><span class="sxs-lookup"><span data-stu-id="dbd3f-214">Pay cycle (required)</span></span>
- <span data-ttu-id="dbd3f-215">Domyślny wymiar finansowy — Centrum kosztu (wymagane)</span><span class="sxs-lookup"><span data-stu-id="dbd3f-215">Default financial dimension – Cost center (required)</span></span>
- <span data-ttu-id="dbd3f-216">Przypisanie pracownika — Pracownik, rozpoczęcie przypisania, zakończenia przypisania, kod przyczyny</span><span class="sxs-lookup"><span data-stu-id="dbd3f-216">Worker assignment – Worker, assignment start, assignment end, reason code</span></span>

<span data-ttu-id="dbd3f-217">Jeśli z tą samą funkcją jest skojarzonych wiele stanowisk w tym samym dziale, są one konsolidowane w jedno stanowisko w systemie Dayforce.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-217">If multiple positions in the same department are associated with the same job, they are consolidated into a single position in Dayforce.</span></span>

<span data-ttu-id="dbd3f-218">Aby uzyskać więcej informacji, zobacz następujące tematy:</span><span class="sxs-lookup"><span data-stu-id="dbd3f-218">For more information, see the following topics:</span></span>

- [<span data-ttu-id="dbd3f-219">Organizowanie pracowników za pomocą działów, funkcji i stanowisk</span><span class="sxs-lookup"><span data-stu-id="dbd3f-219">Organize your workforce using departments, jobs, and positions</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/departments-jobs-positions#positions)
- [<span data-ttu-id="dbd3f-220">Konfigurowanie stanowisk</span><span class="sxs-lookup"><span data-stu-id="dbd3f-220">Set up positions</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/set-up-positions)

#### <a name="departments"></a><span data-ttu-id="dbd3f-221">Działy</span><span class="sxs-lookup"><span data-stu-id="dbd3f-221">Departments</span></span>

<span data-ttu-id="dbd3f-222">Dział to jednostka operacyjna należąca do kategorii lub obszaru funkcjonalnego organizacji.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-222">A department is an operating unit that represents a category or functional area of an organization.</span></span> <span data-ttu-id="dbd3f-223">Dział jest odpowiedzialny za określony obszar organizacji, np. sprzedaż, księgowość lub zasoby ludzkie.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-223">A department is responsible for a specific area of the organization, such as sales, accounting, or human resources.</span></span> <span data-ttu-id="dbd3f-224">Działy pozwalają tworzyć raporty dotyczące obszarów funkcyjnych.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-224">You can use departments to report on functional areas.</span></span> <span data-ttu-id="dbd3f-225">Działy mogą mieć odpowiedzialność zysków i strat.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-225">Departments might have profit and loss responsibility.</span></span>

<span data-ttu-id="dbd3f-226">Aby uzyskać więcej informacji, zobacz następujące tematy:</span><span class="sxs-lookup"><span data-stu-id="dbd3f-226">For more information, see the following topics:</span></span>

- [<span data-ttu-id="dbd3f-227">Tworzenie działu i kojarzenie go z hierarchią działów</span><span class="sxs-lookup"><span data-stu-id="dbd3f-227">Create a department and associate it with the department hierarchy</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/create-department-add-department-hierarchy)
- [<span data-ttu-id="dbd3f-228">Definiowanie nowych działów</span><span class="sxs-lookup"><span data-stu-id="dbd3f-228">Define new departments</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-departments)

#### <a name="pay-cycles-and-pay-periods"></a><span data-ttu-id="dbd3f-229">Cykle płac i okresy płac</span><span class="sxs-lookup"><span data-stu-id="dbd3f-229">Pay cycles and pay periods</span></span>

<span data-ttu-id="dbd3f-230">Cykl kalkulacji płac decyduje o częstotliwości wykonywania sesji obliczania listy płac oraz o konkretnych dniach, kiedy pracownicy otrzymują zapłatę.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-230">A pay cycle determines how often payroll is run and the specific days when workers are paid.</span></span> <span data-ttu-id="dbd3f-231">Na przykład cykl kalkulacji płac może być miesięczny, a pracownicy mogą otrzymywać wypłatę w ostatnim dniu miesiąca.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-231">For example, a pay cycle might be monthly, and employees might be paid on the last day of the month.</span></span> <span data-ttu-id="dbd3f-232">Alternatywnie cykl kalkulacji płac może być tygodniowy, a pracownicy dostają wypłatę w każdy wtorek po zakończeniu okresu kalkulacji płac.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-232">Alternatively, a pay cycle might be weekly, and employees might be paid on the Tuesday after the end of the pay period.</span></span> <span data-ttu-id="dbd3f-233">Cykle kalkulacji płac są przypisywane do stanowisk w celu kontrolowania, kiedy pracownicy na tych stanowiskach otrzymują zapłatę.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-233">Pay cycles are assigned to positions to control when workers in those positions are paid.</span></span>

<span data-ttu-id="dbd3f-234">Po utworzeniu cykli kalkulacji płac można wygenerować okresy kalkulacji płac dla każdego cyklu.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-234">After you create pay cycles, you can generate pay periods for each cycle.</span></span> <span data-ttu-id="dbd3f-235">Każdy okres kalkulacji płac zawiera domyślną datę płatności, która bazuje na podanych przez Ciebie informacjach.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-235">Each pay period includes a default payment date that is based on information that you provide.</span></span> <span data-ttu-id="dbd3f-236">Można jednak zmodyfikować domyślną datę płatności w okresie kalkulacji płac, co pozwala stosować wyjątki, np. gdy data płatności przypada na dzień wolny od pracy.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-236">However, you can modify the default payment date in a pay period to allow for exceptions, such as when the payment date falls on a holiday.</span></span>

<span data-ttu-id="dbd3f-237">Poniższe informacje są używane w programie Dayforce:</span><span class="sxs-lookup"><span data-stu-id="dbd3f-237">The following information is used in Dayforce:</span></span>

- <span data-ttu-id="dbd3f-238">Cykl kalkulacji płac (wymagane)</span><span class="sxs-lookup"><span data-stu-id="dbd3f-238">Pay cycle (required)</span></span>
- <span data-ttu-id="dbd3f-239">Częstotliwość cyklu kalkulacji płac (wymagane)</span><span class="sxs-lookup"><span data-stu-id="dbd3f-239">Pay cycle frequency (required)</span></span>
- <span data-ttu-id="dbd3f-240">Data rozpoczęcia okresu (pierwszy okres kalkulacji płac jest wymagany)</span><span class="sxs-lookup"><span data-stu-id="dbd3f-240">Period start date (first pay period required)</span></span>
- <span data-ttu-id="dbd3f-241">Domyślna data płatności (pierwszy okres kalkulacji płac jest wymagany)</span><span class="sxs-lookup"><span data-stu-id="dbd3f-241">Default payment date (first pay period required)</span></span>

<span data-ttu-id="dbd3f-242">Te informacje są integrowane z usługą Dayforce jako grupy płac oraz dzielone na kraje lub regiony dla każdego cyklu kalkulacji płac.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-242">This information is integrated with Dayforce as pay groups, and is separated by country or region for each pay cycle.</span></span> <span data-ttu-id="dbd3f-243">Przed integracją musi być wygenerowany co najmniej jeden okres kalkulacji płac.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-243">At least one pay period must be generated before integration.</span></span> <span data-ttu-id="dbd3f-244">System Dayforce generuje kalendarze grup płac i daty płatności na podstawie daty rozpoczęcia pierwszego okresu kalkulacji płac i domyślnej daty płatności ustawionej w aplikacji Talent.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-244">Dayforce generates pay group calendars and payment dates, based on the start date of the first pay period and the default payment date that is set up in Talent.</span></span>

#### <a name="earning-codes"></a><span data-ttu-id="dbd3f-245">Kody zarobków</span><span class="sxs-lookup"><span data-stu-id="dbd3f-245">Earning codes</span></span>

<span data-ttu-id="dbd3f-246">Kody zarobków jednoznacznie identyfikują każdy rodzaj dochodów, które otrzymują pracownicy.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-246">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="dbd3f-247">Kody mają różne parametry związane z zarobkami, takie jak reguły księgowania, przepisy podatkowe, wymagania dotyczące raportowania i możliwość zwiększania wartości brutto.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-247">The codes have various parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span>

<span data-ttu-id="dbd3f-248">Poniższe informacje są używane w programie Dayforce:</span><span class="sxs-lookup"><span data-stu-id="dbd3f-248">The following information is used in Dayforce:</span></span>

- <span data-ttu-id="dbd3f-249">Kod zarobków (wymagane)</span><span class="sxs-lookup"><span data-stu-id="dbd3f-249">Earning Code (required)</span></span>
- <span data-ttu-id="dbd3f-250">opis</span><span class="sxs-lookup"><span data-stu-id="dbd3f-250">Description</span></span>
- <span data-ttu-id="dbd3f-251">Jednostka miary</span><span class="sxs-lookup"><span data-stu-id="dbd3f-251">Unit of measure</span></span>
- <span data-ttu-id="dbd3f-252">Płatne</span><span class="sxs-lookup"><span data-stu-id="dbd3f-252">Productive</span></span>

### <a name="worker-data"></a><span data-ttu-id="dbd3f-253">Dane pracowników</span><span class="sxs-lookup"><span data-stu-id="dbd3f-253">Worker data</span></span>

<span data-ttu-id="dbd3f-254">Dokumenty o różnych typach posiadanych pracowników są ważne dla informatycznych systemów kadrowych i płacowych.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-254">Records for the various types of workers that you have are important to your human resources and payroll systems.</span></span> <span data-ttu-id="dbd3f-255">Wprowadzone informacje mogą służyć do monitorowania pracowników i danych osobowych.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-255">The information that you enter can be used to track workers and personal information.</span></span>

<span data-ttu-id="dbd3f-256">Można przechowywać następujące informacje o pracownikach:</span><span class="sxs-lookup"><span data-stu-id="dbd3f-256">You can maintain the following information for workers:</span></span>

- <span data-ttu-id="dbd3f-257">**Podstawowe** — Podstawowe informacje o pracowniku, takie jak dane kontaktowe, demograficzne, identyfikacyjne, informacje o rodzinie, stosunek do służby wojskowej, status emigranta oraz dane kontaktowe dla nagłych wypadków.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-257">**Basic** – Maintain basic information about a worker, such as contact information, demographic information, identification information, family information, military service status, expatriate information, and personal and emergency contacts.</span></span>
- <span data-ttu-id="dbd3f-258">**Zatrudnienie** — Informacje o zatrudnieniu pracownika, takie jak przynależność do firmy lub organizacji, przypisanie stanowiska, daty rozpoczęcia i zakończenia, prawo do zatrudnienia, warunki zatrudnienia, emerytura, urlop i informacje o przeniesieniu.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-258">**Employment** – Maintain information about a worker's employment, such as company or organization affiliation, position assignment, start and end dates, work eligibility, terms of employment, pension, vacation, and relocation information.</span></span>
- <span data-ttu-id="dbd3f-259">**Urlopy i nieobecności** — Informacje o nieobecności pracownika, takie jak kalendarze pracy, transakcje nieobecności i ustawienia nieobecności.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-259">**Leave and absence** – Maintain information about a worker's absences, such as working calendars, absence transactions, and absence setup.</span></span>
- <span data-ttu-id="dbd3f-260">**Wynagrodzenia i płace** — Informacje o planach wynagrodzeń i płacach pracownika, takie jak rejestracja w planie, nagrody, wydajność, prowizje, informacje podatkowe, odejście na emeryturę i potrącenia z wynagrodzenia.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-260">**Compensation and payroll** – Maintain information about a worker's compensation plans and payroll information, such as plan enrollment, awards, performance, commission, tax information, retirement, and salary deductions.</span></span>

<span data-ttu-id="dbd3f-261">Podczas wprowadzania danych pracownika należy wziąć pod uwagę następujące dane i konfiguracje używane w programie Dayforce.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-261">When you enter worker information, keep in mind the following data and configurations that are used in Dayforce.</span></span>

#### <a name="general-information"></a><span data-ttu-id="dbd3f-262">Informacje ogólne</span><span class="sxs-lookup"><span data-stu-id="dbd3f-262">General information</span></span>

- <span data-ttu-id="dbd3f-263">Numer pracownika (wymagane)</span><span class="sxs-lookup"><span data-stu-id="dbd3f-263">Personnel number (required)</span></span>
- <span data-ttu-id="dbd3f-264">Imię (wymagane)</span><span class="sxs-lookup"><span data-stu-id="dbd3f-264">First name (required)</span></span>
- <span data-ttu-id="dbd3f-265">Nazwisko (wymagane)</span><span class="sxs-lookup"><span data-stu-id="dbd3f-265">Last name (required)</span></span>
- <span data-ttu-id="dbd3f-266">Drugie imię</span><span class="sxs-lookup"><span data-stu-id="dbd3f-266">Middle name</span></span>
- <span data-ttu-id="dbd3f-267">Data stażu pracy</span><span class="sxs-lookup"><span data-stu-id="dbd3f-267">Seniority date</span></span>
- <span data-ttu-id="dbd3f-268">Znane jako</span><span class="sxs-lookup"><span data-stu-id="dbd3f-268">Known as</span></span>

#### <a name="personal-information"></a><span data-ttu-id="dbd3f-269">Informacje osobiste</span><span class="sxs-lookup"><span data-stu-id="dbd3f-269">Personal information</span></span>

- <span data-ttu-id="dbd3f-270">Stan cywilny (wymagane)</span><span class="sxs-lookup"><span data-stu-id="dbd3f-270">Marital status (required)</span></span>
- <span data-ttu-id="dbd3f-271">Data urodzenia (wymagane)</span><span class="sxs-lookup"><span data-stu-id="dbd3f-271">Birth date (required)</span></span>
- <span data-ttu-id="dbd3f-272">Płeć (wymagane)</span><span class="sxs-lookup"><span data-stu-id="dbd3f-272">Gender (required)</span></span>
- <span data-ttu-id="dbd3f-273">Osoba niepełnosprawna</span><span class="sxs-lookup"><span data-stu-id="dbd3f-273">Person with disabilities</span></span>
- <span data-ttu-id="dbd3f-274">Obywatelstwo (kraj/region) (tylko w przypadku Meksyku)</span><span class="sxs-lookup"><span data-stu-id="dbd3f-274">Nationality country region (only for Mexico)</span></span>

#### <a name="address-information"></a><span data-ttu-id="dbd3f-275">Informacje adresowe</span><span class="sxs-lookup"><span data-stu-id="dbd3f-275">Address information</span></span>

- <span data-ttu-id="dbd3f-276">Podstawowy (wymagane)</span><span class="sxs-lookup"><span data-stu-id="dbd3f-276">Primary (required)</span></span>
- <span data-ttu-id="dbd3f-277">Kraj/region (wymagane)</span><span class="sxs-lookup"><span data-stu-id="dbd3f-277">Country/region (required)</span></span>
- <span data-ttu-id="dbd3f-278">Kod pocztowy (wymagane)</span><span class="sxs-lookup"><span data-stu-id="dbd3f-278">Postal code (required)</span></span>
- <span data-ttu-id="dbd3f-279">Numer domu (wymagane) (jedynie w przypadku Meksyku)</span><span class="sxs-lookup"><span data-stu-id="dbd3f-279">Street Number (required) (Only for Mexico)</span></span>
- <span data-ttu-id="dbd3f-280">Dodatkowe określenie budynku (tylko w przypadku Meksyku)</span><span class="sxs-lookup"><span data-stu-id="dbd3f-280">Building Complement (Only for Mexico)</span></span>
- <span data-ttu-id="dbd3f-281">Miejscowość (wymagane)</span><span class="sxs-lookup"><span data-stu-id="dbd3f-281">City (required)</span></span>
- <span data-ttu-id="dbd3f-282">Województwo (wymagane)</span><span class="sxs-lookup"><span data-stu-id="dbd3f-282">State (required)</span></span>
- <span data-ttu-id="dbd3f-283">Powiat (wymagane)</span><span class="sxs-lookup"><span data-stu-id="dbd3f-283">County (required)</span></span>

#### <a name="contact-information"></a><span data-ttu-id="dbd3f-284">Informacje o kontakcie</span><span class="sxs-lookup"><span data-stu-id="dbd3f-284">Contact information</span></span> 

- <span data-ttu-id="dbd3f-285">Podstawowy (wymagane)</span><span class="sxs-lookup"><span data-stu-id="dbd3f-285">Primary (required)</span></span>
- <span data-ttu-id="dbd3f-286">Nazwa osoby kontaktowej (wymagane)</span><span class="sxs-lookup"><span data-stu-id="dbd3f-286">Contact number (required)</span></span>
- <span data-ttu-id="dbd3f-287">Wewnętrzny</span><span class="sxs-lookup"><span data-stu-id="dbd3f-287">Extension</span></span>

#### <a name="payroll-information-and-earning-codes"></a><span data-ttu-id="dbd3f-288">Informacje płacowe i kody zarobków</span><span class="sxs-lookup"><span data-stu-id="dbd3f-288">Payroll information and earning codes</span></span>

<span data-ttu-id="dbd3f-289">Pracownicy mogą mieć przypisane określone zarobki z określoną częstotliwością wypłat oraz mieć ustawioną preferowaną metodę płatności.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-289">Employees may be assigned specific earnings at a given frequency of payment and have a preferred payment method.</span></span> <span data-ttu-id="dbd3f-290">Następujące pola są używane w usłudze Dayforce w celu zagwarantowania, że te ustawienia i preferencje są wykorzystywane.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-290">The following fields are used in Dayforce to help guarantee that those preferences and settings are used.</span></span>

##### <a name="earning-codes"></a><span data-ttu-id="dbd3f-291">Kody zarobków</span><span class="sxs-lookup"><span data-stu-id="dbd3f-291">Earning codes</span></span>

- <span data-ttu-id="dbd3f-292">Stanowisko (wymagane)</span><span class="sxs-lookup"><span data-stu-id="dbd3f-292">Position (required)</span></span>
- <span data-ttu-id="dbd3f-293">Kod zarobków (wymagane)</span><span class="sxs-lookup"><span data-stu-id="dbd3f-293">Earning Code (required)</span></span>
- <span data-ttu-id="dbd3f-294">Częstotliwość (wymagane)</span><span class="sxs-lookup"><span data-stu-id="dbd3f-294">Frequency (required)</span></span>
- <span data-ttu-id="dbd3f-295">Kwota (wymagane)</span><span class="sxs-lookup"><span data-stu-id="dbd3f-295">Amount (required)</span></span>

##### <a name="payroll-information"></a><span data-ttu-id="dbd3f-296">Informacje listy płac</span><span class="sxs-lookup"><span data-stu-id="dbd3f-296">Payroll information</span></span>

- <span data-ttu-id="dbd3f-297">Metoda płatności</span><span class="sxs-lookup"><span data-stu-id="dbd3f-297">Payment Method</span></span>
- <span data-ttu-id="dbd3f-298">Region gospodarczy (wymagane)</span><span class="sxs-lookup"><span data-stu-id="dbd3f-298">Economic Region (required)</span></span>
- <span data-ttu-id="dbd3f-299">Identyfikator świadczeń pracownika etatowego</span><span class="sxs-lookup"><span data-stu-id="dbd3f-299">Employee Benefits ID</span></span>
- <span data-ttu-id="dbd3f-300">Numer dowodu osobistego (wymagane)</span><span class="sxs-lookup"><span data-stu-id="dbd3f-300">National ID Number (required)</span></span>
- <span data-ttu-id="dbd3f-301">Numer książeczki wojskowej</span><span class="sxs-lookup"><span data-stu-id="dbd3f-301">Military Service Number</span></span>
- <span data-ttu-id="dbd3f-302">Identyfikator zmiany (wymagane)</span><span class="sxs-lookup"><span data-stu-id="dbd3f-302">Shift ID (required)</span></span>
- <span data-ttu-id="dbd3f-303">Numer identyfikacji podatkowej (wymagane)</span><span class="sxs-lookup"><span data-stu-id="dbd3f-303">Tax Number (required)</span></span>
- <span data-ttu-id="dbd3f-304">Identyfikator związku (wymagane)</span><span class="sxs-lookup"><span data-stu-id="dbd3f-304">Union ID (required)</span></span>
- <span data-ttu-id="dbd3f-305">Identyfikator dnia roboczego (wymagane)</span><span class="sxs-lookup"><span data-stu-id="dbd3f-305">Work Day ID (required)</span></span>
- <span data-ttu-id="dbd3f-306">Numer pozwolenia na pracę</span><span class="sxs-lookup"><span data-stu-id="dbd3f-306">Work Permit Number</span></span>

> [!NOTE]
> <span data-ttu-id="dbd3f-307">W Meksyku obsługiwane metody płatności to **Gotówka**, **Czek** (fizyczny czek wystawiany przez firmę) i **Płatność elektroniczna**.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-307">For the payment method, Mexico supports **Cash**, **Check** (the company's physical check), and **Electronic Payment**.</span></span> <span data-ttu-id="dbd3f-308">Jeśli metoda płatności nie zostanie określona, domyślnie będzie używana metoda **Czek**.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-308">If np payment method is specified, **Check** is used by default.</span></span>

#### <a name="employment-details"></a><span data-ttu-id="dbd3f-309">Szczegóły zatrudnienia</span><span class="sxs-lookup"><span data-stu-id="dbd3f-309">Employment details</span></span>

<span data-ttu-id="dbd3f-310">Historia szczegółów zatrudnienia pełni rolę kluczowych informacji przy ustalaniu statusów zatrudnienia, zwolnienia i ponownego zatrudnienia pracownika etatowego w systemie Dayforce.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-310">Employment detail history is used as key information to derive an employee's hire, termination, and rehire statuses in Dayforce.</span></span> <span data-ttu-id="dbd3f-311">W rozwiązaniu Dayforce może istnieć tylko jeden aktywny rekord zatrudnienia na raz.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-311">Dayforce supports only one active employment record at a time.</span></span>

- <span data-ttu-id="dbd3f-312">Data rozpoczęcia zatrudnienia (wymagane)</span><span class="sxs-lookup"><span data-stu-id="dbd3f-312">Employment start date (required)</span></span>
- <span data-ttu-id="dbd3f-313">Data zakończenia zatrudnienia</span><span class="sxs-lookup"><span data-stu-id="dbd3f-313">Employment end date</span></span>
- <span data-ttu-id="dbd3f-314">Rozpoczęcie</span><span class="sxs-lookup"><span data-stu-id="dbd3f-314">Start date</span></span>
- <span data-ttu-id="dbd3f-315">Dopasowana data rozpoczęcia.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-315">Adjusted start date</span></span>
- <span data-ttu-id="dbd3f-316">Data zakończenia (wymagane po rozwiązaniu stosunku pracy)</span><span class="sxs-lookup"><span data-stu-id="dbd3f-316">Termination date (required upon termination)</span></span>
- <span data-ttu-id="dbd3f-317">Powód rozwiązania umowy (wymagane po rozwiązaniu stosunku pracy)</span><span class="sxs-lookup"><span data-stu-id="dbd3f-317">Termination reason (required upon termination)</span></span>

<span data-ttu-id="dbd3f-318">Kluczowe daty pracownika są obliczane na podstawie następujących informacji.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-318">An employee's key dates are derived by using the following information.</span></span>

| <span data-ttu-id="dbd3f-319">Talent</span><span class="sxs-lookup"><span data-stu-id="dbd3f-319">Talent</span></span>                | <span data-ttu-id="dbd3f-320">Dayforce</span><span class="sxs-lookup"><span data-stu-id="dbd3f-320">Dayforce</span></span>                                                                                             |
|-----------------------|------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="dbd3f-321">Ostatnia data zatrudnienia</span><span class="sxs-lookup"><span data-stu-id="dbd3f-321">Most recent hire date</span></span> | <span data-ttu-id="dbd3f-322">Rozpoczęcie pracy w bieżącym rekordzie historii niezakończonego zatrudnienia</span><span class="sxs-lookup"><span data-stu-id="dbd3f-322">Employment start of current non-terminated employment history record</span></span>                                 |
| <span data-ttu-id="dbd3f-323">Data zakończenia</span><span class="sxs-lookup"><span data-stu-id="dbd3f-323">Termination date</span></span>      | <span data-ttu-id="dbd3f-324">Data zakończenia zatrudnienia w bieżącym rekordzie historii niezakończonego zatrudnienia</span><span class="sxs-lookup"><span data-stu-id="dbd3f-324">Termination date of current non-terminated employment history record</span></span>                                 |
| <span data-ttu-id="dbd3f-325">Rozpoczęcie</span><span class="sxs-lookup"><span data-stu-id="dbd3f-325">Start date</span></span>            | <span data-ttu-id="dbd3f-326">Skorygowana data rozpoczęcia, data rozpoczęcia lub rozpoczęcie zatrudnienia w bieżącym rekordzie historii nieaktywnego zatrudnienia</span><span class="sxs-lookup"><span data-stu-id="dbd3f-326">Adjusted start date, start date, or employment start of current non-active employment history record</span></span> |
| <span data-ttu-id="dbd3f-327">Pierwotna data zatrudnienia</span><span class="sxs-lookup"><span data-stu-id="dbd3f-327">Original hire date</span></span>    | <span data-ttu-id="dbd3f-328">Rozpoczęcie zatrudnienia w najwcześniejszym rekordzie historii zatrudnienia</span><span class="sxs-lookup"><span data-stu-id="dbd3f-328">Employment start of earliest employment history record</span></span>                                               |

#### <a name="compensation"></a><span data-ttu-id="dbd3f-329">Wynagrodzenie</span><span class="sxs-lookup"><span data-stu-id="dbd3f-329">Compensation</span></span>

<span data-ttu-id="dbd3f-330">Plan stałych wynagrodzeń musi być skojarzony z podstawowym stanowiskiem każdego pracownika w okresie zatrudnienia.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-330">A fixed compensation plan must be associated with every employee's primary position throughout an employment period.</span></span> <span data-ttu-id="dbd3f-331">Okres ten rozpoczyna się w dniu zatrudnienia pracownika (lub rozpoczęcia zatrudnienia) i trwa do momentu zakończenia zatrudnienia.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-331">This period starts on the date that the employee was hired (or the employment start date) and continues until termination.</span></span>

- <span data-ttu-id="dbd3f-332">Data obowiązywania (wymagane)</span><span class="sxs-lookup"><span data-stu-id="dbd3f-332">Effective Date (required)</span></span>
- <span data-ttu-id="dbd3f-333">Data ważności</span><span class="sxs-lookup"><span data-stu-id="dbd3f-333">Expiration date</span></span>
- <span data-ttu-id="dbd3f-334">Stawka płacy (wymagane)</span><span class="sxs-lookup"><span data-stu-id="dbd3f-334">Pay Rate (required)</span></span>
- <span data-ttu-id="dbd3f-335">Konwersje stawek płacy (wymagane)</span><span class="sxs-lookup"><span data-stu-id="dbd3f-335">Pay Rate Conversions (required)</span></span>
- <span data-ttu-id="dbd3f-336">Równowartość roczna (wymagane)</span><span class="sxs-lookup"><span data-stu-id="dbd3f-336">Annual equivalent (required)</span></span>
- <span data-ttu-id="dbd3f-337">Równowartość godzinowa (wymagane)</span><span class="sxs-lookup"><span data-stu-id="dbd3f-337">Hourly equivalent (required)</span></span>

<span data-ttu-id="dbd3f-338">Jeśli pracownik rozliczany godzinowo zajmuje kilka stanowisk, stałe wynagrodzenie na podstawowym stanowisku jest importowane do systemu Dayforce jako podstawowa stawka/wynagrodzenie na poziomie pracownika.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-338">If an hourly employee has multiple positions, the fixed compensation of the primary position is imported into Dayforce as the employee-level base rate/salary.</span></span> <span data-ttu-id="dbd3f-339">Dla stanowisk dodatkowych stawka godzinowa jest zapisywana na odpowiednich stanowiskach w usłudze Dayforce.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-339">For non-primary positions, the hourly rate is saved to the corresponding position in Dayforce.</span></span>

<span data-ttu-id="dbd3f-340">Jeśli pracownik na stawce stałej zajmuje kilka stanowisk, skumulowana stawka godzinowa i roczne wynagrodzenie ze wszystkich aktywnych stanowisk są używane jako podstawowa stawka/wynagrodzenie na poziomie pracownika.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-340">If a salaried employee has multiple positions, the cumulative hour rate and annual salary across all active positions are derived and used as the employee-level base rate/salary.</span></span>

#### <a name="identification-numbers"></a><span data-ttu-id="dbd3f-341">Numery identyfikacyjne</span><span class="sxs-lookup"><span data-stu-id="dbd3f-341">Identification numbers</span></span>

##### <a name="social-security-identifier"></a><span data-ttu-id="dbd3f-342">Numer ubezpieczenia społecznego</span><span class="sxs-lookup"><span data-stu-id="dbd3f-342">Social Security identifier</span></span> 

<span data-ttu-id="dbd3f-343">Każdy pracownik musi mieć jeden identyfikator podstawowy.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-343">Every employee must have one primary identifier.</span></span> <span data-ttu-id="dbd3f-344">Identyfikator ten musi być typu **PESEL**.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-344">This identifier must be of **SSN** identification type.</span></span> <span data-ttu-id="dbd3f-345">W systemie Dayforce jest on automatycznie interpretowany jako numer ubezpieczenia społecznego wymagany w celu zatrudnienia.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-345">In Dayforce, it's automatically derived as the employee's Social Security identifier that is required for hire.</span></span>

- <span data-ttu-id="dbd3f-346">Podstawowy (wymagane)</span><span class="sxs-lookup"><span data-stu-id="dbd3f-346">Primary (required)</span></span>
- <span data-ttu-id="dbd3f-347">Typ identyfikacji = „PESEL”</span><span class="sxs-lookup"><span data-stu-id="dbd3f-347">Identification Type = "SSN"</span></span>
- <span data-ttu-id="dbd3f-348">Data wystawienia</span><span class="sxs-lookup"><span data-stu-id="dbd3f-348">Issued Date</span></span>
- <span data-ttu-id="dbd3f-349">Data ważności</span><span class="sxs-lookup"><span data-stu-id="dbd3f-349">Expiration Date</span></span>

<span data-ttu-id="dbd3f-350">Pracownicy mogą zadeklarować wiele numerów identyfikacyjnych typu **PESEL**.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-350">Employees can declare multiple identification numbers of the **SSN** identification type.</span></span> <span data-ttu-id="dbd3f-351">Jednak tylko rekord oznaczony jako **Podstawowy** jest integrowany z rozwiązaniem Dayforce, niezależnie od tego, czy jest on aktywny, czy wygasły.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-351">However, only the record that is marked as **Primary** is integrated into Dayforce, regardless of whether the number is active or expired.</span></span>

#### <a name="bank-accounts-and-disbursements"></a><span data-ttu-id="dbd3f-352">Konta bankowe i wypłaty</span><span class="sxs-lookup"><span data-stu-id="dbd3f-352">Bank accounts and disbursements</span></span>

<span data-ttu-id="dbd3f-353">Dla każdego pracownika, który wybrał opcję otrzymywania wynagrodzenia przelewami na rachunek bankowy, należy wprowadzić prawidłowe dane konta bankowego.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-353">Valid bank account information must be entered for any employee who chooses to be paid via bank account transfers.</span></span>

| <span data-ttu-id="dbd3f-354">Talent</span><span class="sxs-lookup"><span data-stu-id="dbd3f-354">Talent</span></span>                         | <span data-ttu-id="dbd3f-355">Dayforce</span><span class="sxs-lookup"><span data-stu-id="dbd3f-355">Dayforce</span></span>                                                                                                    |
|--------------------------------|-------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="dbd3f-356">Numer konta bankowego (wymagane)</span><span class="sxs-lookup"><span data-stu-id="dbd3f-356">Bank account number (required)</span></span> |                                                                                                             |
| <span data-ttu-id="dbd3f-357">Kod SWIFT (wymagane)</span><span class="sxs-lookup"><span data-stu-id="dbd3f-357">SWIFT code (required)</span></span>          | <span data-ttu-id="dbd3f-358">Pole **Identyfikator banku** używane w trakcie przetwarzania listy płac w Meksyku.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-358">**Bank ID** field used when processing payroll in Mexico.</span></span>                                                             |
| <span data-ttu-id="dbd3f-359">Numer oddziału (wymagane)</span><span class="sxs-lookup"><span data-stu-id="dbd3f-359">Branch number (required)</span></span>       |                                                                                                             |
| <span data-ttu-id="dbd3f-360">Typ konta bankowego (wymagane)</span><span class="sxs-lookup"><span data-stu-id="dbd3f-360">Bank account type (required)</span></span>   | <span data-ttu-id="dbd3f-361">Pole **Typ konta** używane w trakcie przetwarzania listy płac w Meksyku.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-361">**Account type** field used when processing payroll in Mexico.</span></span> <span data-ttu-id="dbd3f-362">Obsługiwane wartości **Czekowe** i **Lista płac**.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-362">Supported values include **Checking** and **Payroll**.</span></span> |

> [!NOTE]
> <span data-ttu-id="dbd3f-363">Pracownicy, którzy wybiorą otrzymywanie wynagrodzeń przelewami na rachunki bankowe, muszą podać łącze do konta pozostałości, które należy do firmy mającej podstawowy adres w Meksyku i jest skojarzone z prawidłowym kontem bankowym w meksykańskim banku.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-363">Employees who choose to be paid via bank account transfers must provide a link to a remainder account that is under a legal entity that has its primary address in Mexico and associated with a valid bank account from a Mexican bank.</span></span> <span data-ttu-id="dbd3f-364">Wszystkie inne konta pozostałości są ignorowane.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-364">All other non-remainder accounts are ignored.</span></span>

#### <a name="address-information"></a><span data-ttu-id="dbd3f-365">Informacje adresowe</span><span class="sxs-lookup"><span data-stu-id="dbd3f-365">Address information</span></span>

<span data-ttu-id="dbd3f-366">Każdy pracownik musi mieć jedną lokalizację podstawową.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-366">Every employee must have one primary location.</span></span> <span data-ttu-id="dbd3f-367">W systemie Dayforce ta lokalizacja jest używana do określenia głównego miejsca zamieszkania pracownika w celach podatkowych.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-367">In Dayforce, this location is used to determine the employee's primary residence for tax purposes.</span></span>

- <span data-ttu-id="dbd3f-368">Podstawowy (wymagane)</span><span class="sxs-lookup"><span data-stu-id="dbd3f-368">Primary (required)</span></span>
- <span data-ttu-id="dbd3f-369">Kraj/region (wymagane)</span><span class="sxs-lookup"><span data-stu-id="dbd3f-369">Country/region (required)</span></span>
- <span data-ttu-id="dbd3f-370">Kod pocztowy (wymagane)</span><span class="sxs-lookup"><span data-stu-id="dbd3f-370">Zip/postal code (required)</span></span>
- <span data-ttu-id="dbd3f-371">Ulica (wymagane)</span><span class="sxs-lookup"><span data-stu-id="dbd3f-371">Street (required)</span></span>
- <span data-ttu-id="dbd3f-372">Numer domu (wymagane)</span><span class="sxs-lookup"><span data-stu-id="dbd3f-372">Street Number (required)</span></span>
- <span data-ttu-id="dbd3f-373">Dodatkowe określenie budynku</span><span class="sxs-lookup"><span data-stu-id="dbd3f-373">Building Complement</span></span>
- <span data-ttu-id="dbd3f-374">Miejscowość (wymagane)</span><span class="sxs-lookup"><span data-stu-id="dbd3f-374">City (required)</span></span>
- <span data-ttu-id="dbd3f-375">Województwo (wymagane)</span><span class="sxs-lookup"><span data-stu-id="dbd3f-375">State (required)</span></span>
- <span data-ttu-id="dbd3f-376">Powiat (wymagane)</span><span class="sxs-lookup"><span data-stu-id="dbd3f-376">County (required)</span></span>

## <a name="configure-your-data-to-generate-payroll-in-united-states-and-canada"></a><span data-ttu-id="dbd3f-377">Konfigurowanie danych w celu generowania listy płac w Stanach Zjednoczonych i Kanadzie</span><span class="sxs-lookup"><span data-stu-id="dbd3f-377">Configure your data to generate payroll in United States and Canada</span></span>

<span data-ttu-id="dbd3f-378">Jeśli generujesz płace dla pracowników na terenie Stanów Zjednoczonych i Kanady, należy skonfigurować następujące elementy:</span><span class="sxs-lookup"><span data-stu-id="dbd3f-378">If you're generating pay for employees in the United States and Canada, the following elements must be configured:</span></span>

- <span data-ttu-id="dbd3f-379">Dla stanowisk muszą być określone działy.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-379">Departments are required on positions.</span></span>
- <span data-ttu-id="dbd3f-380">Centra kosztów muszą być ustawione jako wymiary finansowe i muszą być pierwszym elementem w ciągu domyślnych wymiarów finansowych.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-380">Cost centers must be set as financial dimensions and must be the first element in the default financial dimension string.</span></span>

> [!NOTE] 
> <span data-ttu-id="dbd3f-381">Można skonfigurować Talent tak, aby Stanowiska umożliwiały określenie działu.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-381">You can configure Talent to require that Positions specify a Department.</span></span> <span data-ttu-id="dbd3f-382">Aby to zrobić, przejdź do **stanowisk udostępnionych zasobów ludzkich > Stanowisk > wymagają działów stanowisk**.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-382">To do this, go to **Human Resources Shared Positions > Positions > Require departments on positions**.</span></span> <span data-ttu-id="dbd3f-383">Zaleca się, aby to ustawienie zostało wymuszone dla integracji.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-383">We recommend that this setting be enforced for the integration.</span></span>

### <a name="job-types"></a><span data-ttu-id="dbd3f-384">Typy funkcji</span><span class="sxs-lookup"><span data-stu-id="dbd3f-384">Job types</span></span>

<span data-ttu-id="dbd3f-385">Typy funkcji służą do grupowanie podobnych funkcji w kategorie.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-385">Job types are used to group similar jobs into categories.</span></span> <span data-ttu-id="dbd3f-386">Typy funkcji są wymagane w celu przetwarzania listy płac w Stanach Zjednoczonych i Kanadzie.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-386">Job types are required in order to process payroll in the United States and Canada.</span></span> <span data-ttu-id="dbd3f-387">Przykłady typów funkcji to zatrudnienie w pełnym i niepełnym wymiarze czasu albo wynagrodzenie za etat i za godziny.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-387">Examples of job types include full-time and part-time, or salary and hourly pay.</span></span> <span data-ttu-id="dbd3f-388">Typy funkcji są mapowane do systemu Dayforce jako typy płac, które wskazują, czy pracownik jest na stawce godzinowej, czy stałej pensji.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-388">Job types are mapped to Dayforce as pay types that indicate whether an employee is hourly or salaried.</span></span>

<span data-ttu-id="dbd3f-389">Następujące typy funkcji i opisy są wymagane.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-389">The following job types and descriptions are required.</span></span>

| <span data-ttu-id="dbd3f-390">Typ funkcji</span><span class="sxs-lookup"><span data-stu-id="dbd3f-390">Job type</span></span>   | <span data-ttu-id="dbd3f-391">opis</span><span class="sxs-lookup"><span data-stu-id="dbd3f-391">Description</span></span> |
|------------|-------------|
| <span data-ttu-id="dbd3f-392">Co godzinę</span><span class="sxs-lookup"><span data-stu-id="dbd3f-392">Hourly</span></span>     | <span data-ttu-id="dbd3f-393">Co godzinę</span><span class="sxs-lookup"><span data-stu-id="dbd3f-393">Hourly</span></span>      |
| <span data-ttu-id="dbd3f-394">Stała pensja</span><span class="sxs-lookup"><span data-stu-id="dbd3f-394">Salaried</span></span>   | <span data-ttu-id="dbd3f-395">Stała pensja</span><span class="sxs-lookup"><span data-stu-id="dbd3f-395">Salaried</span></span>    |

### <a name="position-types"></a><span data-ttu-id="dbd3f-396">Typy stanowisk</span><span class="sxs-lookup"><span data-stu-id="dbd3f-396">Position types</span></span> 

<span data-ttu-id="dbd3f-397">Typy stanowisk służą do opisywania, czy stanowisko jest w pełnym wymiarze czasu, niepełnym wymiarze czasu lub ma inną konfigurację.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-397">You use position types to describe whether the position is full-time, part-time, or something else.</span></span> <span data-ttu-id="dbd3f-398">Typy stanowisk są mapowane do systemu Dayforce jako klasy płac, które wskazują, czy pracownik jest zatrudniony na pełny etat, czy na część etatu.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-398">Position types are mapped to Dayforce as pay classes that indicate whether an employee is full-time or part-time.</span></span>

<span data-ttu-id="dbd3f-399">Następujące typy stanowisk i opisy są wymagane.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-399">The following position types and descriptions are required.</span></span>

| <span data-ttu-id="dbd3f-400">Typ stanowiska</span><span class="sxs-lookup"><span data-stu-id="dbd3f-400">Position type</span></span>   | <span data-ttu-id="dbd3f-401">opis</span><span class="sxs-lookup"><span data-stu-id="dbd3f-401">Description</span></span>        |
|-----------------|--------------------|
| <span data-ttu-id="dbd3f-402">Pełny etat</span><span class="sxs-lookup"><span data-stu-id="dbd3f-402">Full-time</span></span>       | <span data-ttu-id="dbd3f-403">Pracownik etatowy zatrudniony w pełnym wymiarze czasu</span><span class="sxs-lookup"><span data-stu-id="dbd3f-403">Full time employee</span></span> |
| <span data-ttu-id="dbd3f-404">Część etatu</span><span class="sxs-lookup"><span data-stu-id="dbd3f-404">Part-time</span></span>       | <span data-ttu-id="dbd3f-405">Pracownik etatowy zatrudniony w niepełnym wymiarze czasu</span><span class="sxs-lookup"><span data-stu-id="dbd3f-405">Part time employee</span></span> |

### <a name="reason-codes"></a><span data-ttu-id="dbd3f-406">Kody przyczyn</span><span class="sxs-lookup"><span data-stu-id="dbd3f-406">Reason codes</span></span>

<span data-ttu-id="dbd3f-407">Kody przyczyn informują o stanie pracownika.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-407">Reason codes provide information about the status of an employee.</span></span> <span data-ttu-id="dbd3f-408">Kody przyczyn są mapowane do systemu Dayforce jako przyczyny stanu, które wskazują powód zmiany stanowiska lub statusu zatrudnienia pracownika.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-408">Reason codes are mapped to Dayforce as status reasons that indicate the reason for changes to an employee's position or employment status.</span></span>

<span data-ttu-id="dbd3f-409">Następujące kody przyczyn i opisy są wymagane.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-409">The following reason codes and descriptions are required.</span></span>

| <span data-ttu-id="dbd3f-410">Kod przyczyny</span><span class="sxs-lookup"><span data-stu-id="dbd3f-410">Reason code</span></span>    | <span data-ttu-id="dbd3f-411">opis</span><span class="sxs-lookup"><span data-stu-id="dbd3f-411">Description</span></span>      | <span data-ttu-id="dbd3f-412">Odpowiednie scenariusze</span><span class="sxs-lookup"><span data-stu-id="dbd3f-412">Applicable scenarios</span></span> |
|----------------|------------------|----------------------|
| <span data-ttu-id="dbd3f-413">RESIGNATION</span><span class="sxs-lookup"><span data-stu-id="dbd3f-413">RESIGNATION</span></span>    | <span data-ttu-id="dbd3f-414">Rezygnacja</span><span class="sxs-lookup"><span data-stu-id="dbd3f-414">Resignation</span></span>      | <span data-ttu-id="dbd3f-415">Zwalnianie pracownika</span><span class="sxs-lookup"><span data-stu-id="dbd3f-415">Terminate worker</span></span>     |
| <span data-ttu-id="dbd3f-416">TERMINATION</span><span class="sxs-lookup"><span data-stu-id="dbd3f-416">TERMINATION</span></span>    | <span data-ttu-id="dbd3f-417">Przerwanie</span><span class="sxs-lookup"><span data-stu-id="dbd3f-417">Termination</span></span>      | <span data-ttu-id="dbd3f-418">Zwalnianie pracownika</span><span class="sxs-lookup"><span data-stu-id="dbd3f-418">Terminate worker</span></span>     |
| <span data-ttu-id="dbd3f-419">RETIREMENT</span><span class="sxs-lookup"><span data-stu-id="dbd3f-419">RETIREMENT</span></span>     | <span data-ttu-id="dbd3f-420">Emerytura</span><span class="sxs-lookup"><span data-stu-id="dbd3f-420">Retirement</span></span>       | <span data-ttu-id="dbd3f-421">Zwalnianie pracownika</span><span class="sxs-lookup"><span data-stu-id="dbd3f-421">Terminate worker</span></span>     |
| <span data-ttu-id="dbd3f-422">INNY</span><span class="sxs-lookup"><span data-stu-id="dbd3f-422">OTHER</span></span>          | <span data-ttu-id="dbd3f-423">Inne przyczyny</span><span class="sxs-lookup"><span data-stu-id="dbd3f-423">Other Reasons</span></span>    | <span data-ttu-id="dbd3f-424">Zwalnianie pracownika</span><span class="sxs-lookup"><span data-stu-id="dbd3f-424">Terminate worker</span></span>     |
| <span data-ttu-id="dbd3f-425">DEATH</span><span class="sxs-lookup"><span data-stu-id="dbd3f-425">DEATH</span></span>          | <span data-ttu-id="dbd3f-426">Śmierć</span><span class="sxs-lookup"><span data-stu-id="dbd3f-426">Death</span></span>            | <span data-ttu-id="dbd3f-427">Zwalnianie pracownika</span><span class="sxs-lookup"><span data-stu-id="dbd3f-427">Terminate worker</span></span>     |
| <span data-ttu-id="dbd3f-428">LEAVEOFABSENCE</span><span class="sxs-lookup"><span data-stu-id="dbd3f-428">LEAVEOFABSENCE</span></span> | <span data-ttu-id="dbd3f-429">Nieobecność</span><span class="sxs-lookup"><span data-stu-id="dbd3f-429">Leave of Absence</span></span> | <span data-ttu-id="dbd3f-430">Zwalnianie pracownika</span><span class="sxs-lookup"><span data-stu-id="dbd3f-430">Terminate worker</span></span>     |
| <span data-ttu-id="dbd3f-431">CONTRACTEND</span><span class="sxs-lookup"><span data-stu-id="dbd3f-431">CONTRACTEND</span></span>    | <span data-ttu-id="dbd3f-432">Zakończenie umowy</span><span class="sxs-lookup"><span data-stu-id="dbd3f-432">End of Contract</span></span>  | <span data-ttu-id="dbd3f-433">Zwalnianie pracownika</span><span class="sxs-lookup"><span data-stu-id="dbd3f-433">Terminate worker</span></span>     |
| <span data-ttu-id="dbd3f-434">SALARYCHANGE</span><span class="sxs-lookup"><span data-stu-id="dbd3f-434">SALARYCHANGE</span></span>   | <span data-ttu-id="dbd3f-435">Zmiana wynagrodzenia</span><span class="sxs-lookup"><span data-stu-id="dbd3f-435">Change of Salary</span></span> | <span data-ttu-id="dbd3f-436">Wynagrodzenie</span><span class="sxs-lookup"><span data-stu-id="dbd3f-436">Compensation</span></span>         |

### <a name="marital-status"></a><span data-ttu-id="dbd3f-437">Stan cywilny</span><span class="sxs-lookup"><span data-stu-id="dbd3f-437">Marital status</span></span>

<span data-ttu-id="dbd3f-438">Wartości stanu cywilnego są mapowane do systemu Dayforce i w razie potrzeby tłumaczone na akceptowane wartości podczas integracji.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-438">Marital status values are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="dbd3f-439">W poniższej tabeli przedstawiono mapowanie wartości stanu cywilnego do usługi Dayforce.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-439">The following table shows how marital status values are mapped to Dayforce.</span></span>

| <span data-ttu-id="dbd3f-440">Talent</span><span class="sxs-lookup"><span data-stu-id="dbd3f-440">Talent</span></span>                 | <span data-ttu-id="dbd3f-441">Dayforce</span><span class="sxs-lookup"><span data-stu-id="dbd3f-441">Dayforce</span></span>             |
|------------------------|----------------------|
| <span data-ttu-id="dbd3f-442">Żonaty/mężatka</span><span class="sxs-lookup"><span data-stu-id="dbd3f-442">Married</span></span>                | <span data-ttu-id="dbd3f-443">Żonaty/mężatka</span><span class="sxs-lookup"><span data-stu-id="dbd3f-443">Married</span></span>              |
| <span data-ttu-id="dbd3f-444">Jedno</span><span class="sxs-lookup"><span data-stu-id="dbd3f-444">Single</span></span>                 | <span data-ttu-id="dbd3f-445">Jedno</span><span class="sxs-lookup"><span data-stu-id="dbd3f-445">Single</span></span>               |
| <span data-ttu-id="dbd3f-446">Wdowiec/wdowa</span><span class="sxs-lookup"><span data-stu-id="dbd3f-446">Widowed</span></span>                | <span data-ttu-id="dbd3f-447">Wdowiec/wdowa</span><span class="sxs-lookup"><span data-stu-id="dbd3f-447">Widowed</span></span>              |
| <span data-ttu-id="dbd3f-448">Rozwiedziony/rozwiedziona</span><span class="sxs-lookup"><span data-stu-id="dbd3f-448">Divorced</span></span>               | <span data-ttu-id="dbd3f-449">Rozwiedziony/rozwiedziona</span><span class="sxs-lookup"><span data-stu-id="dbd3f-449">Divorced</span></span>             |
| <span data-ttu-id="dbd3f-450">Związek zarejestrowany</span><span class="sxs-lookup"><span data-stu-id="dbd3f-450">Registered Partnership</span></span> | <span data-ttu-id="dbd3f-451">Partnerstwo krajowe</span><span class="sxs-lookup"><span data-stu-id="dbd3f-451">Domestic Partnership</span></span> |
| <span data-ttu-id="dbd3f-452">None</span><span class="sxs-lookup"><span data-stu-id="dbd3f-452">None</span></span>                   | <span data-ttu-id="dbd3f-453">None</span><span class="sxs-lookup"><span data-stu-id="dbd3f-453">None</span></span>                 |
| <span data-ttu-id="dbd3f-454">Konkubinat</span><span class="sxs-lookup"><span data-stu-id="dbd3f-454">Cohabiting</span></span>             | <span data-ttu-id="dbd3f-455">Konkubinat</span><span class="sxs-lookup"><span data-stu-id="dbd3f-455">Cohabiting</span></span>           |

### <a name="gender"></a><span data-ttu-id="dbd3f-456">Rodzaj</span><span class="sxs-lookup"><span data-stu-id="dbd3f-456">Gender</span></span>

<span data-ttu-id="dbd3f-457">Określenia płci są mapowane do systemu Dayforce i w razie potrzeby tłumaczone na akceptowane wartości podczas integracji.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-457">Gender designations are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="dbd3f-458">W poniższej tabeli przedstawiono mapowanie określeń płci do usługi Dayforce.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-458">The following table shows how gender designations are mapped to Dayforce.</span></span>

| <span data-ttu-id="dbd3f-459">Talent</span><span class="sxs-lookup"><span data-stu-id="dbd3f-459">Talent</span></span>       | <span data-ttu-id="dbd3f-460">Dayforce</span><span class="sxs-lookup"><span data-stu-id="dbd3f-460">Dayforce</span></span>        |
|--------------|-----------------|
| <span data-ttu-id="dbd3f-461">Mężczyzna</span><span class="sxs-lookup"><span data-stu-id="dbd3f-461">Male</span></span>         | <span data-ttu-id="dbd3f-462">Mężczyzna</span><span class="sxs-lookup"><span data-stu-id="dbd3f-462">Male</span></span>            |
| <span data-ttu-id="dbd3f-463">Kobieta</span><span class="sxs-lookup"><span data-stu-id="dbd3f-463">Female</span></span>       | <span data-ttu-id="dbd3f-464">Kobieta</span><span class="sxs-lookup"><span data-stu-id="dbd3f-464">Female</span></span>          |
| <span data-ttu-id="dbd3f-465">Nieokreślone</span><span class="sxs-lookup"><span data-stu-id="dbd3f-465">Non-specific</span></span> | <span data-ttu-id="dbd3f-466">*Nieobsługiwane*</span><span class="sxs-lookup"><span data-stu-id="dbd3f-466">*Not supported*</span></span> |

### <a name="earning-codes"></a><span data-ttu-id="dbd3f-467">Kody zarobków</span><span class="sxs-lookup"><span data-stu-id="dbd3f-467">Earning codes</span></span>

<span data-ttu-id="dbd3f-468">Kody zarobków jednoznacznie identyfikują każdy rodzaj dochodów, które otrzymują pracownicy.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-468">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="dbd3f-469">Kody mają różne parametry związane z zarobkami, takie jak reguły księgowania, przepisy podatkowe, wymagania dotyczące raportowania i możliwość zwiększania wartości brutto.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-469">The codes cover several parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span> <span data-ttu-id="dbd3f-470">W razie ustawienia nieobsługiwanej częstotliwości domyślnie w obliczeniu będzie używana częstotliwość **Każda wypłata**.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-470">If an unsupported frequency is used, the **Every Pay** frequency is used by default for the calculation.</span></span>

#### <a name="supported-frequencies"></a><span data-ttu-id="dbd3f-471">Obsługiwane częstotliwości</span><span class="sxs-lookup"><span data-stu-id="dbd3f-471">Supported frequencies</span></span>

- <span data-ttu-id="dbd3f-472">Wszyscy</span><span class="sxs-lookup"><span data-stu-id="dbd3f-472">All</span></span>
- <span data-ttu-id="dbd3f-473">EVERYPAY</span><span class="sxs-lookup"><span data-stu-id="dbd3f-473">EVERYPAY</span></span>
- <span data-ttu-id="dbd3f-474">EACHPAYPERIOD</span><span class="sxs-lookup"><span data-stu-id="dbd3f-474">EACHPAYPERIOD</span></span>
- <span data-ttu-id="dbd3f-475">EVRYOTHRPAYODD</span><span class="sxs-lookup"><span data-stu-id="dbd3f-475">EVRYOTHRPAYODD</span></span>
- <span data-ttu-id="dbd3f-476">EVRYOTHRPAYEVN</span><span class="sxs-lookup"><span data-stu-id="dbd3f-476">EVRYOTHRPAYEVN</span></span>
- <span data-ttu-id="dbd3f-477">1OFMTH</span><span class="sxs-lookup"><span data-stu-id="dbd3f-477">1OFMTH</span></span>
- <span data-ttu-id="dbd3f-478">LASTOFMTH</span><span class="sxs-lookup"><span data-stu-id="dbd3f-478">LASTOFMTH</span></span>
- <span data-ttu-id="dbd3f-479">2OFMTH</span><span class="sxs-lookup"><span data-stu-id="dbd3f-479">2OFMTH</span></span>
- <span data-ttu-id="dbd3f-480">3OFMTH</span><span class="sxs-lookup"><span data-stu-id="dbd3f-480">3OFMTH</span></span>
- <span data-ttu-id="dbd3f-481">4OFMTH</span><span class="sxs-lookup"><span data-stu-id="dbd3f-481">4OFMTH</span></span>
- <span data-ttu-id="dbd3f-482">5OFMTH</span><span class="sxs-lookup"><span data-stu-id="dbd3f-482">5OFMTH</span></span>
- <span data-ttu-id="dbd3f-483">1N2OFMTH</span><span class="sxs-lookup"><span data-stu-id="dbd3f-483">1N2OFMTH</span></span>
- <span data-ttu-id="dbd3f-484">3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="dbd3f-484">3N4OFMTH</span></span>
- <span data-ttu-id="dbd3f-485">1N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="dbd3f-485">1N3OFMTH</span></span>
- <span data-ttu-id="dbd3f-486">1N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="dbd3f-486">1N4OFMTH</span></span>
- <span data-ttu-id="dbd3f-487">2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="dbd3f-487">2N3OFMTH</span></span>
- <span data-ttu-id="dbd3f-488">2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="dbd3f-488">2N4OFMTH</span></span>
- <span data-ttu-id="dbd3f-489">1N2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="dbd3f-489">1N2N3OFMTH</span></span>
- <span data-ttu-id="dbd3f-490">1N2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="dbd3f-490">1N2N4OFMTH</span></span>
- <span data-ttu-id="dbd3f-491">1N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="dbd3f-491">1N3N4OFMTH</span></span>
- <span data-ttu-id="dbd3f-492">2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="dbd3f-492">2N3N4OFMTH</span></span>
- <span data-ttu-id="dbd3f-493">1N2N3N4OFMTH – 1N2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="dbd3f-493">1N2N3N4OFMTH - 1N2N3N4OFMTH</span></span>
- <span data-ttu-id="dbd3f-494">2N3N4N5OFMth – 2N3N4N5OFMth</span><span class="sxs-lookup"><span data-stu-id="dbd3f-494">2N3N4N5OFMth - 2N3N4N5OFMth</span></span>
- <span data-ttu-id="dbd3f-495">1OFQTR – 1OFQTR</span><span class="sxs-lookup"><span data-stu-id="dbd3f-495">1OFQTR - 1OFQTR</span></span>
- <span data-ttu-id="dbd3f-496">LASTOFQTR – LASTOFQTR</span><span class="sxs-lookup"><span data-stu-id="dbd3f-496">LASTOFQTR – LASTOFQTR</span></span>
- <span data-ttu-id="dbd3f-497">LASTMTHOFQTR – LASTMTHOFQTR</span><span class="sxs-lookup"><span data-stu-id="dbd3f-497">LASTMTHOFQTR – LASTMTHOFQTR</span></span>
- <span data-ttu-id="dbd3f-498">1OFYEAR – 1OFYEAR</span><span class="sxs-lookup"><span data-stu-id="dbd3f-498">1OFYEAR - 1OFYEAR</span></span>
- <span data-ttu-id="dbd3f-499">LASTOFYEAR – LASTOFYEAR</span><span class="sxs-lookup"><span data-stu-id="dbd3f-499">LASTOFYEAR – LASTOFYEAR</span></span>
- <span data-ttu-id="dbd3f-500">NOVNDECOFYEAR – NOVNDECOFYEAR</span><span class="sxs-lookup"><span data-stu-id="dbd3f-500">NOVNDECOFYEAR - NOVNDECOFYEAR</span></span>

### <a name="addresses"></a><span data-ttu-id="dbd3f-501">Adresy</span><span class="sxs-lookup"><span data-stu-id="dbd3f-501">Addresses</span></span>

<span data-ttu-id="dbd3f-502">Identyfikacja określonych kodów kraju lub regionu, województwa i powiatu (gminy) wymaga określonych formatów, które potrafi rozpoznać system Dayforce oraz dostawcy wewnątrz krajów/regionów.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-502">The identification of specific country or region, state, and county (municipality) codes requires specific formats that Dayforce and in-country/in-region providers can recognize.</span></span> <span data-ttu-id="dbd3f-503">Co prawda format nazw miejscowości jest elastyczny, ale każda miejscowość musi być skojarzona z województwem.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-503">Although the format for cities is flexible, every city must be associated with a state.</span></span>

| <span data-ttu-id="dbd3f-504">Talent</span><span class="sxs-lookup"><span data-stu-id="dbd3f-504">Talent</span></span>          | <span data-ttu-id="dbd3f-505">Dayforce</span><span class="sxs-lookup"><span data-stu-id="dbd3f-505">Dayforce</span></span>              |
|-----------------|-----------------------|
| <span data-ttu-id="dbd3f-506">Kraj/region</span><span class="sxs-lookup"><span data-stu-id="dbd3f-506">Country/Region</span></span>  | <span data-ttu-id="dbd3f-507">Kod kraju</span><span class="sxs-lookup"><span data-stu-id="dbd3f-507">Country Code</span></span>          |
| <span data-ttu-id="dbd3f-508">Kod pocztowy</span><span class="sxs-lookup"><span data-stu-id="dbd3f-508">Zip/Postal Code</span></span> | <span data-ttu-id="dbd3f-509">Kod pocztowy</span><span class="sxs-lookup"><span data-stu-id="dbd3f-509">Postal Code</span></span>           |
| <span data-ttu-id="dbd3f-510">Stanowy</span><span class="sxs-lookup"><span data-stu-id="dbd3f-510">State</span></span>           | <span data-ttu-id="dbd3f-511">Kod województwa</span><span class="sxs-lookup"><span data-stu-id="dbd3f-511">State Code</span></span>            |
| <span data-ttu-id="dbd3f-512">Miejscowość</span><span class="sxs-lookup"><span data-stu-id="dbd3f-512">City</span></span>            | <span data-ttu-id="dbd3f-513">Miejscowość</span><span class="sxs-lookup"><span data-stu-id="dbd3f-513">City</span></span>                  |
| <span data-ttu-id="dbd3f-514">Powiat</span><span class="sxs-lookup"><span data-stu-id="dbd3f-514">County</span></span>          | <span data-ttu-id="dbd3f-515">Powiat (gmina)</span><span class="sxs-lookup"><span data-stu-id="dbd3f-515">County (Municipality)</span></span> |
| <span data-ttu-id="dbd3f-516">Ulica</span><span class="sxs-lookup"><span data-stu-id="dbd3f-516">Street</span></span>          | <span data-ttu-id="dbd3f-517">Wiersz adresu 1</span><span class="sxs-lookup"><span data-stu-id="dbd3f-517">Address Line 1</span></span>        |

### <a name="tax-regions"></a><span data-ttu-id="dbd3f-518">Regiony podatkowe</span><span class="sxs-lookup"><span data-stu-id="dbd3f-518">Tax regions</span></span>

<span data-ttu-id="dbd3f-519">Regiony podatkowe służą do określania odpowiedniej stawki podatkowej stosowanej podczas generowania listy płac.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-519">Tax regions are used to determine the appropriate tax that should be applied during payroll generation.</span></span> <span data-ttu-id="dbd3f-520">Regiony podatkowe są mapowane do systemu Dayforce jako adresy lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-520">Tax regions are mapped to Dayforce as location addresses.</span></span> <span data-ttu-id="dbd3f-521">Domyślny region podatkowy musi być skojarzony z aktywnym stanowiskiem pracownika.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-521">The default tax region must be associated with the worker's active position.</span></span> 

- <span data-ttu-id="dbd3f-522">Region podatkowy (wymagane)</span><span class="sxs-lookup"><span data-stu-id="dbd3f-522">Tax region (required)</span></span>
- <span data-ttu-id="dbd3f-523">Kraj/region (wymagane)</span><span class="sxs-lookup"><span data-stu-id="dbd3f-523">Country/Region (required)</span></span>
- <span data-ttu-id="dbd3f-524">Województwo (wymagane)</span><span class="sxs-lookup"><span data-stu-id="dbd3f-524">State (required)</span></span>
- <span data-ttu-id="dbd3f-525">Powiat</span><span class="sxs-lookup"><span data-stu-id="dbd3f-525">County</span></span> 
- <span data-ttu-id="dbd3f-526">Miejscowość (wymagane)</span><span class="sxs-lookup"><span data-stu-id="dbd3f-526">City (required)</span></span>

## <a name="configure-your-data-to-generate-payroll-in-mexico"></a><span data-ttu-id="dbd3f-527">Konfigurowanie danych w celu generowania listy płac w Meksyku</span><span class="sxs-lookup"><span data-stu-id="dbd3f-527">Configure your data to generate payroll in Mexico</span></span>

<span data-ttu-id="dbd3f-528">Jeśli generujesz płace dla pracowników na terenie Meksyku, należy skonfigurować następujące elementy:</span><span class="sxs-lookup"><span data-stu-id="dbd3f-528">If you're generating pay for employees in Mexico, the following elements must be configured:</span></span>

- <span data-ttu-id="dbd3f-529">Dla stanowisk muszą być określone działy.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-529">Departments are required on positions.</span></span>
- <span data-ttu-id="dbd3f-530">Centra kosztów muszą być ustawione jako wymiary finansowe i muszą być pierwszym elementem w ciągu domyślnych wymiarów finansowych.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-530">Cost centers must be set as financial dimensions and must be the first element in the Default Financial Dimension string.</span></span>

### <a name="job-types"></a><span data-ttu-id="dbd3f-531">Typy stanowisk</span><span class="sxs-lookup"><span data-stu-id="dbd3f-531">Job types</span></span>

<span data-ttu-id="dbd3f-532">Typy funkcji służą do grupowanie podobnych funkcji w kategorie.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-532">Job types are used to group similar jobs into categories.</span></span> <span data-ttu-id="dbd3f-533">Typy funkcji są wymagane w celu przetwarzania listy płac w Meksyku.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-533">Job types are required in order to process payroll in Mexico.</span></span> <span data-ttu-id="dbd3f-534">Przykłady typów funkcji to zatrudnienie w pełnym i niepełnym wymiarze czasu albo wynagrodzenie za etat i za godziny.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-534">Examples of job types include full-time and part-time, or salary and hourly pay.</span></span> <span data-ttu-id="dbd3f-535">Typy funkcji są mapowane do systemu Dayforce jako typy płac, które wskazują, czy pracownik jest na stawce godzinowej, czy stałej pensji.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-535">Job types are mapped to Dayforce as pay types that indicate whether an employee is hourly or salaried.</span></span>

<span data-ttu-id="dbd3f-536">Następujące typy funkcji i opisy są wymagane.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-536">The following job types and descriptions are required.</span></span>

| <span data-ttu-id="dbd3f-537">Typ funkcji</span><span class="sxs-lookup"><span data-stu-id="dbd3f-537">Job type</span></span>   | <span data-ttu-id="dbd3f-538">opis</span><span class="sxs-lookup"><span data-stu-id="dbd3f-538">Description</span></span> |
|------------|-------------|
| <span data-ttu-id="dbd3f-539">Co godzinę</span><span class="sxs-lookup"><span data-stu-id="dbd3f-539">Hourly</span></span>     | <span data-ttu-id="dbd3f-540">MX Co godzinę</span><span class="sxs-lookup"><span data-stu-id="dbd3f-540">MX Hourly</span></span>   |
| <span data-ttu-id="dbd3f-541">Stała pensja</span><span class="sxs-lookup"><span data-stu-id="dbd3f-541">Salaried</span></span>   | <span data-ttu-id="dbd3f-542">MX Stała pensja</span><span class="sxs-lookup"><span data-stu-id="dbd3f-542">MX Salaried</span></span> |

### <a name="position-types"></a><span data-ttu-id="dbd3f-543">Typy stanowisk</span><span class="sxs-lookup"><span data-stu-id="dbd3f-543">Position types</span></span> 

<span data-ttu-id="dbd3f-544">Typy stanowisk służą do opisywania, czy stanowisko jest w pełnym wymiarze czasu, niepełnym wymiarze czasu lub ma inną konfigurację.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-544">You use position types to describe whether the position is full-time, part-time, or something else.</span></span> <span data-ttu-id="dbd3f-545">Typy stanowisk są mapowane do systemu Dayforce jako klasy płac, które wskazują, czy pracownik jest zatrudniony na pełny etat, czy na część etatu.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-545">Position types are mapped to Dayforce as pay classes that indicate whether an employee is full-time or part-time.</span></span>

<span data-ttu-id="dbd3f-546">Następujące typy stanowisk i opisy są wymagane.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-546">The following position types and descriptions are required.</span></span>

| <span data-ttu-id="dbd3f-547">Typ stanowiska</span><span class="sxs-lookup"><span data-stu-id="dbd3f-547">Position type</span></span>   | <span data-ttu-id="dbd3f-548">opis</span><span class="sxs-lookup"><span data-stu-id="dbd3f-548">Description</span></span>        |
|-----------------|--------------------|
| <span data-ttu-id="dbd3f-549">Pełny etat</span><span class="sxs-lookup"><span data-stu-id="dbd3f-549">Full-time</span></span>       | <span data-ttu-id="dbd3f-550">Pracownik etatowy zatrudniony w pełnym wymiarze czasu</span><span class="sxs-lookup"><span data-stu-id="dbd3f-550">Full time employee</span></span> |
| <span data-ttu-id="dbd3f-551">Część etatu</span><span class="sxs-lookup"><span data-stu-id="dbd3f-551">Part-time</span></span>       | <span data-ttu-id="dbd3f-552">Pracownik etatowy zatrudniony w niepełnym wymiarze czasu</span><span class="sxs-lookup"><span data-stu-id="dbd3f-552">Part time employee</span></span> |

### <a name="reason-codes"></a><span data-ttu-id="dbd3f-553">Kody przyczyn</span><span class="sxs-lookup"><span data-stu-id="dbd3f-553">Reason codes</span></span>

<span data-ttu-id="dbd3f-554">Kody przyczyn informują o stanie pracownika.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-554">Reason codes provide information about the status of an employee.</span></span> <span data-ttu-id="dbd3f-555">Kody przyczyn są mapowane do systemu Dayforce jako przyczyny stanu, które wskazują powód zmiany stanowiska lub statusu zatrudnienia pracownika.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-555">Reason codes are mapped to Dayforce as status reasons that indicate the reason for changes to an employee's position or employment status.</span></span>

<span data-ttu-id="dbd3f-556">Następujące kody przyczyn i opisy są wymagane.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-556">The following reason codes and descriptions are required.</span></span>

| <span data-ttu-id="dbd3f-557">Kod przyczyny</span><span class="sxs-lookup"><span data-stu-id="dbd3f-557">Reason code</span></span>            | <span data-ttu-id="dbd3f-558">opis</span><span class="sxs-lookup"><span data-stu-id="dbd3f-558">Description</span></span>                    | <span data-ttu-id="dbd3f-559">Odpowiednie scenariusze</span><span class="sxs-lookup"><span data-stu-id="dbd3f-559">Applicable scenarios</span></span> |
|------------------------|--------------------------------|----------------------|
| <span data-ttu-id="dbd3f-560">DEPARTUREBEFOREPAYMENT</span><span class="sxs-lookup"><span data-stu-id="dbd3f-560">DEPARTUREBEFOREPAYMENT</span></span> | <span data-ttu-id="dbd3f-561">Odejście z pracy przed pierwszą wypłatą</span><span class="sxs-lookup"><span data-stu-id="dbd3f-561">Departure before first payroll</span></span> | <span data-ttu-id="dbd3f-562">Zwalnianie pracownika</span><span class="sxs-lookup"><span data-stu-id="dbd3f-562">Terminate worker</span></span>     |
| <span data-ttu-id="dbd3f-563">RESIGNATION</span><span class="sxs-lookup"><span data-stu-id="dbd3f-563">RESIGNATION</span></span>            | <span data-ttu-id="dbd3f-564">Rezygnacja</span><span class="sxs-lookup"><span data-stu-id="dbd3f-564">Resignation</span></span>                    | <span data-ttu-id="dbd3f-565">Zwalnianie pracownika</span><span class="sxs-lookup"><span data-stu-id="dbd3f-565">Terminate worker</span></span>     |
| <span data-ttu-id="dbd3f-566">PENSION</span><span class="sxs-lookup"><span data-stu-id="dbd3f-566">PENSION</span></span>                | <span data-ttu-id="dbd3f-567">Emerytura</span><span class="sxs-lookup"><span data-stu-id="dbd3f-567">Pension</span></span>                        | <span data-ttu-id="dbd3f-568">Zwalnianie pracownika</span><span class="sxs-lookup"><span data-stu-id="dbd3f-568">Terminate worker</span></span>     |
| <span data-ttu-id="dbd3f-569">TERMINATION</span><span class="sxs-lookup"><span data-stu-id="dbd3f-569">TERMINATION</span></span>            | <span data-ttu-id="dbd3f-570">Przerwanie</span><span class="sxs-lookup"><span data-stu-id="dbd3f-570">Termination</span></span>                    | <span data-ttu-id="dbd3f-571">Zwalnianie pracownika</span><span class="sxs-lookup"><span data-stu-id="dbd3f-571">Terminate worker</span></span>     |
| <span data-ttu-id="dbd3f-572">RETIREMENT</span><span class="sxs-lookup"><span data-stu-id="dbd3f-572">RETIREMENT</span></span>             | <span data-ttu-id="dbd3f-573">Emerytura</span><span class="sxs-lookup"><span data-stu-id="dbd3f-573">Retirement</span></span>                     | <span data-ttu-id="dbd3f-574">Zwalnianie pracownika</span><span class="sxs-lookup"><span data-stu-id="dbd3f-574">Terminate worker</span></span>     |
| <span data-ttu-id="dbd3f-575">ABSENTEE</span><span class="sxs-lookup"><span data-stu-id="dbd3f-575">ABSENTEE</span></span>               | <span data-ttu-id="dbd3f-576">Absencja</span><span class="sxs-lookup"><span data-stu-id="dbd3f-576">Absentee</span></span>                       | <span data-ttu-id="dbd3f-577">Zwalnianie pracownika</span><span class="sxs-lookup"><span data-stu-id="dbd3f-577">Terminate worker</span></span>     |
| <span data-ttu-id="dbd3f-578">INNY</span><span class="sxs-lookup"><span data-stu-id="dbd3f-578">OTHER</span></span>                  | <span data-ttu-id="dbd3f-579">Inne przyczyny</span><span class="sxs-lookup"><span data-stu-id="dbd3f-579">Other Reasons</span></span>                  | <span data-ttu-id="dbd3f-580">Zwalnianie pracownika</span><span class="sxs-lookup"><span data-stu-id="dbd3f-580">Terminate worker</span></span>     |
| <span data-ttu-id="dbd3f-581">CLOSURE</span><span class="sxs-lookup"><span data-stu-id="dbd3f-581">CLOSURE</span></span>                | <span data-ttu-id="dbd3f-582">Zaprzestanie działalności przez firmę</span><span class="sxs-lookup"><span data-stu-id="dbd3f-582">Business Closure</span></span>               | <span data-ttu-id="dbd3f-583">Zwalnianie pracownika</span><span class="sxs-lookup"><span data-stu-id="dbd3f-583">Terminate worker</span></span>     |
| <span data-ttu-id="dbd3f-584">DEATH</span><span class="sxs-lookup"><span data-stu-id="dbd3f-584">DEATH</span></span>                  | <span data-ttu-id="dbd3f-585">Śmierć</span><span class="sxs-lookup"><span data-stu-id="dbd3f-585">Death</span></span>                          | <span data-ttu-id="dbd3f-586">Zwalnianie pracownika</span><span class="sxs-lookup"><span data-stu-id="dbd3f-586">Terminate worker</span></span>     |
| <span data-ttu-id="dbd3f-587">LEAVEOFABSENCE</span><span class="sxs-lookup"><span data-stu-id="dbd3f-587">LEAVEOFABSENCE</span></span>         | <span data-ttu-id="dbd3f-588">Nieobecność</span><span class="sxs-lookup"><span data-stu-id="dbd3f-588">Leave of Absence</span></span>               | <span data-ttu-id="dbd3f-589">Zwalnianie pracownika</span><span class="sxs-lookup"><span data-stu-id="dbd3f-589">Terminate worker</span></span>     |
| <span data-ttu-id="dbd3f-590">CONTRACTEND</span><span class="sxs-lookup"><span data-stu-id="dbd3f-590">CONTRACTEND</span></span>            | <span data-ttu-id="dbd3f-591">Zakończenie umowy</span><span class="sxs-lookup"><span data-stu-id="dbd3f-591">End of Contract</span></span>                | <span data-ttu-id="dbd3f-592">Zwalnianie pracownika</span><span class="sxs-lookup"><span data-stu-id="dbd3f-592">Terminate worker</span></span>     |
| <span data-ttu-id="dbd3f-593">SALARYCHANGE</span><span class="sxs-lookup"><span data-stu-id="dbd3f-593">SALARYCHANGE</span></span>           | <span data-ttu-id="dbd3f-594">Zmiana wynagrodzenia</span><span class="sxs-lookup"><span data-stu-id="dbd3f-594">Change of Salary</span></span>               | <span data-ttu-id="dbd3f-595">Wynagrodzenie</span><span class="sxs-lookup"><span data-stu-id="dbd3f-595">Compensation</span></span>         |

### <a name="terms-of-employment"></a><span data-ttu-id="dbd3f-596">Warunki zatrudnienia</span><span class="sxs-lookup"><span data-stu-id="dbd3f-596">Terms of employment</span></span>

<span data-ttu-id="dbd3f-597">Warunki zatrudnienia służą do tworzenia kategorii warunków zatrudnienia.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-597">Terms of employment are used to create categories of employment terms.</span></span> <span data-ttu-id="dbd3f-598">Warunki są mapowane do systemu Dayforce jako wartości wskaźnika zatrudnienia.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-598">The terms are mapped to Dayforce as employment indicator values.</span></span>

<span data-ttu-id="dbd3f-599">Następujące warunki zatrudnienia i opisy są wymagane.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-599">The following terms of employment and descriptions are required.</span></span>

| <span data-ttu-id="dbd3f-600">Warunki zatrudnienia</span><span class="sxs-lookup"><span data-stu-id="dbd3f-600">Terms of employment</span></span>   | <span data-ttu-id="dbd3f-601">opis</span><span class="sxs-lookup"><span data-stu-id="dbd3f-601">Description</span></span> |
|-----------------------|-------------|
| <span data-ttu-id="dbd3f-602">Normalna</span><span class="sxs-lookup"><span data-stu-id="dbd3f-602">Regular</span></span>               | <span data-ttu-id="dbd3f-603">Normalna</span><span class="sxs-lookup"><span data-stu-id="dbd3f-603">Regular</span></span>     |
| <span data-ttu-id="dbd3f-604">Bezpośredni</span><span class="sxs-lookup"><span data-stu-id="dbd3f-604">Direct</span></span>                | <span data-ttu-id="dbd3f-605">Bezpośredni</span><span class="sxs-lookup"><span data-stu-id="dbd3f-605">Direct</span></span>      |
| <span data-ttu-id="dbd3f-606">Staż</span><span class="sxs-lookup"><span data-stu-id="dbd3f-606">Internship</span></span>            | <span data-ttu-id="dbd3f-607">Staż</span><span class="sxs-lookup"><span data-stu-id="dbd3f-607">Internship</span></span>  |
| <span data-ttu-id="dbd3f-608">Stałe</span><span class="sxs-lookup"><span data-stu-id="dbd3f-608">Permanent</span></span>             | <span data-ttu-id="dbd3f-609">Stałe</span><span class="sxs-lookup"><span data-stu-id="dbd3f-609">Permanent</span></span>   |

### <a name="marital-status"></a><span data-ttu-id="dbd3f-610">Stan cywilny</span><span class="sxs-lookup"><span data-stu-id="dbd3f-610">Marital status</span></span>

<span data-ttu-id="dbd3f-611">Wartości stanu cywilnego są mapowane do systemu Dayforce i w razie potrzeby tłumaczone na akceptowane wartości podczas integracji.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-611">Marital status values are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="dbd3f-612">W poniższej tabeli przedstawiono mapowanie wartości stanu cywilnego do usługi Dayforce.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-612">The following table shows how marital status values are mapped to Dayforce.</span></span>

| <span data-ttu-id="dbd3f-613">Talent</span><span class="sxs-lookup"><span data-stu-id="dbd3f-613">Talent</span></span>                 | <span data-ttu-id="dbd3f-614">Dayforce</span><span class="sxs-lookup"><span data-stu-id="dbd3f-614">Dayforce</span></span>                  |
|------------------------|---------------------------|
| <span data-ttu-id="dbd3f-615">Żonaty/mężatka</span><span class="sxs-lookup"><span data-stu-id="dbd3f-615">Married</span></span>                | <span data-ttu-id="dbd3f-616">Żonaty/mężatka</span><span class="sxs-lookup"><span data-stu-id="dbd3f-616">Married</span></span>                   |
| <span data-ttu-id="dbd3f-617">Jedno</span><span class="sxs-lookup"><span data-stu-id="dbd3f-617">Single</span></span>                 | <span data-ttu-id="dbd3f-618">Jedno</span><span class="sxs-lookup"><span data-stu-id="dbd3f-618">Single</span></span>                    |
| <span data-ttu-id="dbd3f-619">Wdowiec/wdowa</span><span class="sxs-lookup"><span data-stu-id="dbd3f-619">Widowed</span></span>                | <span data-ttu-id="dbd3f-620">Wdowiec/wdowa</span><span class="sxs-lookup"><span data-stu-id="dbd3f-620">Widowed</span></span>                   |
| <span data-ttu-id="dbd3f-621">Rozwiedziony/rozwiedziona</span><span class="sxs-lookup"><span data-stu-id="dbd3f-621">Divorced</span></span>               | <span data-ttu-id="dbd3f-622">Rozwiedziony/rozwiedziona</span><span class="sxs-lookup"><span data-stu-id="dbd3f-622">Divorced</span></span>                  |
| <span data-ttu-id="dbd3f-623">Związek zarejestrowany</span><span class="sxs-lookup"><span data-stu-id="dbd3f-623">Registered Partnership</span></span> | <span data-ttu-id="dbd3f-624">Partnerstwo krajowe</span><span class="sxs-lookup"><span data-stu-id="dbd3f-624">Domestic Partnership</span></span>      |
| <span data-ttu-id="dbd3f-625">None</span><span class="sxs-lookup"><span data-stu-id="dbd3f-625">None</span></span>                   | <span data-ttu-id="dbd3f-626">*Nieobsługiwane w Meksyku*</span><span class="sxs-lookup"><span data-stu-id="dbd3f-626">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="dbd3f-627">Konkubinat</span><span class="sxs-lookup"><span data-stu-id="dbd3f-627">Cohabiting</span></span>             | <span data-ttu-id="dbd3f-628">*Nieobsługiwane w Meksyku*</span><span class="sxs-lookup"><span data-stu-id="dbd3f-628">*Not supported by Mexico*</span></span> |

### <a name="gender"></a><span data-ttu-id="dbd3f-629">Rodzaj</span><span class="sxs-lookup"><span data-stu-id="dbd3f-629">Gender</span></span>

<span data-ttu-id="dbd3f-630">Określenia płci są mapowane do systemu Dayforce i w razie potrzeby tłumaczone na akceptowane wartości podczas integracji.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-630">Gender designations are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="dbd3f-631">W poniższej tabeli przedstawiono mapowanie określeń płci do usługi Dayforce.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-631">The following table shows how gender designations are mapped to Dayforce.</span></span>

| <span data-ttu-id="dbd3f-632">Talent</span><span class="sxs-lookup"><span data-stu-id="dbd3f-632">Talent</span></span>       | <span data-ttu-id="dbd3f-633">Dayforce</span><span class="sxs-lookup"><span data-stu-id="dbd3f-633">Dayforce</span></span>                  |
|--------------|---------------------------|
| <span data-ttu-id="dbd3f-634">Mężczyzna</span><span class="sxs-lookup"><span data-stu-id="dbd3f-634">Male</span></span>         | <span data-ttu-id="dbd3f-635">Mężczyzna</span><span class="sxs-lookup"><span data-stu-id="dbd3f-635">Male</span></span>                      |
| <span data-ttu-id="dbd3f-636">Kobieta</span><span class="sxs-lookup"><span data-stu-id="dbd3f-636">Female</span></span>       | <span data-ttu-id="dbd3f-637">Kobieta</span><span class="sxs-lookup"><span data-stu-id="dbd3f-637">Female</span></span>                    |
| <span data-ttu-id="dbd3f-638">Nieokreślone</span><span class="sxs-lookup"><span data-stu-id="dbd3f-638">Non-specific</span></span> | <span data-ttu-id="dbd3f-639">*Nieobsługiwane w Meksyku*</span><span class="sxs-lookup"><span data-stu-id="dbd3f-639">*Not supported by Mexico*</span></span> |

### <a name="payment-method"></a><span data-ttu-id="dbd3f-640">Metoda płatności</span><span class="sxs-lookup"><span data-stu-id="dbd3f-640">Payment method</span></span>

<span data-ttu-id="dbd3f-641">Funkcja metod płatności oferuje pracownikowi i firmie sposób opisania, jak pracownik będzie otrzymywał zapłatę.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-641">Payment methods give the employee and the company a way to describe how employees will be paid.</span></span> <span data-ttu-id="dbd3f-642">Metody płatności są mapowane do systemu Dayforce i w razie potrzeby tłumaczone na akceptowane wartości podczas integracji.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-642">Payment methods are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="dbd3f-643">W poniższej tabeli przedstawiono mapowanie metod płatności do usługi Dayforce.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-643">The following table shows how payment methods are mapped to Dayforce.</span></span>

| <span data-ttu-id="dbd3f-644">Talent</span><span class="sxs-lookup"><span data-stu-id="dbd3f-644">Talent</span></span>             | <span data-ttu-id="dbd3f-645">Dayforce</span><span class="sxs-lookup"><span data-stu-id="dbd3f-645">Dayforce</span></span>                  |
|--------------------|---------------------------|
| <span data-ttu-id="dbd3f-646">Kasa</span><span class="sxs-lookup"><span data-stu-id="dbd3f-646">Cash</span></span>               | <span data-ttu-id="dbd3f-647">Kasa</span><span class="sxs-lookup"><span data-stu-id="dbd3f-647">Cash</span></span>                      |
| <span data-ttu-id="dbd3f-648">Płatność elektroniczna</span><span class="sxs-lookup"><span data-stu-id="dbd3f-648">Electronic Payment</span></span> | <span data-ttu-id="dbd3f-649">Przenoszenie</span><span class="sxs-lookup"><span data-stu-id="dbd3f-649">Transfer</span></span>                  |
| <span data-ttu-id="dbd3f-650">Sprawdzanie</span><span class="sxs-lookup"><span data-stu-id="dbd3f-650">Check</span></span>              | <span data-ttu-id="dbd3f-651">Czek</span><span class="sxs-lookup"><span data-stu-id="dbd3f-651">Cheque</span></span>                    |
| <span data-ttu-id="dbd3f-652">Przekaz bankowy</span><span class="sxs-lookup"><span data-stu-id="dbd3f-652">Bank Draft</span></span>         | <span data-ttu-id="dbd3f-653">*Nieobsługiwane w Meksyku*</span><span class="sxs-lookup"><span data-stu-id="dbd3f-653">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="dbd3f-654">Inna</span><span class="sxs-lookup"><span data-stu-id="dbd3f-654">Other</span></span>              | <span data-ttu-id="dbd3f-655">*Nieobsługiwane w Meksyku*</span><span class="sxs-lookup"><span data-stu-id="dbd3f-655">*Not supported by Mexico*</span></span> |

### <a name="bank-account-type"></a><span data-ttu-id="dbd3f-656">Typ konta bankowego</span><span class="sxs-lookup"><span data-stu-id="dbd3f-656">Bank account type</span></span>

<span data-ttu-id="dbd3f-657">Typy kont bankowych są wykorzystywane w płatnościach elektronicznych dla pracowników.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-657">Bank account types are used for electronic payments to employees.</span></span> <span data-ttu-id="dbd3f-658">Typy kont bankowych są mapowane do systemu Dayforce jako informacje o koncie do przelewów.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-658">Bank account types are mapped to Dayforce as transfer account information.</span></span> <span data-ttu-id="dbd3f-659">Typy kont bankowych są w razie potrzeby tłumaczone na akceptowane wartości podczas integracji.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-659">The bank account types are translated, as appropriate, to the accepted values upon integration.</span></span>

| <span data-ttu-id="dbd3f-660">Talent</span><span class="sxs-lookup"><span data-stu-id="dbd3f-660">Talent</span></span>            | <span data-ttu-id="dbd3f-661">Dayforce</span><span class="sxs-lookup"><span data-stu-id="dbd3f-661">Dayforce</span></span>                  |
|-------------------|---------------------------|
| <span data-ttu-id="dbd3f-662">Konto czekowe</span><span class="sxs-lookup"><span data-stu-id="dbd3f-662">Checking Account</span></span>  | <span data-ttu-id="dbd3f-663">CheckingAccount</span><span class="sxs-lookup"><span data-stu-id="dbd3f-663">CheckingAccount</span></span>           |
| <span data-ttu-id="dbd3f-664">Konto listy płac</span><span class="sxs-lookup"><span data-stu-id="dbd3f-664">Payroll Account</span></span>   | <span data-ttu-id="dbd3f-665">PayrollAccount</span><span class="sxs-lookup"><span data-stu-id="dbd3f-665">PayrollAccount</span></span>            |
| <span data-ttu-id="dbd3f-666">Konto oszczędnościowe</span><span class="sxs-lookup"><span data-stu-id="dbd3f-666">Savings Account</span></span>   | <span data-ttu-id="dbd3f-667">*Nieobsługiwane w Meksyku*</span><span class="sxs-lookup"><span data-stu-id="dbd3f-667">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="dbd3f-668">Konto BankGirot</span><span class="sxs-lookup"><span data-stu-id="dbd3f-668">BankGirot account</span></span> | <span data-ttu-id="dbd3f-669">*Nieobsługiwane w Meksyku*</span><span class="sxs-lookup"><span data-stu-id="dbd3f-669">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="dbd3f-670">Konto PlusGirot</span><span class="sxs-lookup"><span data-stu-id="dbd3f-670">PlusGirot account</span></span> | <span data-ttu-id="dbd3f-671">*Nieobsługiwane w Meksyku*</span><span class="sxs-lookup"><span data-stu-id="dbd3f-671">*Not supported by Mexico*</span></span> |

### <a name="earning-codes"></a><span data-ttu-id="dbd3f-672">Kody zarobków</span><span class="sxs-lookup"><span data-stu-id="dbd3f-672">Earning codes</span></span>

<span data-ttu-id="dbd3f-673">Kody zarobków jednoznacznie identyfikują każdy rodzaj dochodów, które otrzymują pracownicy.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-673">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="dbd3f-674">Kody mają różne parametry związane z zarobkami, takie jak reguły księgowania, przepisy podatkowe, wymagania dotyczące raportowania i możliwość zwiększania wartości brutto.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-674">The codes cover several parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span> <span data-ttu-id="dbd3f-675">W razie ustawienia nieobsługiwanej częstotliwości domyślnie w obliczeniu będzie używana częstotliwość **Każda wypłata**.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-675">If an unsupported frequency is used, the **Every Pay** frequency is used by default for the calculation.</span></span>

#### <a name="supported-frequencies"></a><span data-ttu-id="dbd3f-676">Obsługiwane częstotliwości</span><span class="sxs-lookup"><span data-stu-id="dbd3f-676">Supported frequencies</span></span>

- <span data-ttu-id="dbd3f-677">Wszyscy</span><span class="sxs-lookup"><span data-stu-id="dbd3f-677">All</span></span>
- <span data-ttu-id="dbd3f-678">EVERYPAY</span><span class="sxs-lookup"><span data-stu-id="dbd3f-678">EVERYPAY</span></span>
- <span data-ttu-id="dbd3f-679">EACHPAYPERIOD</span><span class="sxs-lookup"><span data-stu-id="dbd3f-679">EACHPAYPERIOD</span></span>
- <span data-ttu-id="dbd3f-680">EVRYOTHRPAYODD</span><span class="sxs-lookup"><span data-stu-id="dbd3f-680">EVRYOTHRPAYODD</span></span>
- <span data-ttu-id="dbd3f-681">EVRYOTHRPAYEVN</span><span class="sxs-lookup"><span data-stu-id="dbd3f-681">EVRYOTHRPAYEVN</span></span>
- <span data-ttu-id="dbd3f-682">1OFMTH</span><span class="sxs-lookup"><span data-stu-id="dbd3f-682">1OFMTH</span></span>
- <span data-ttu-id="dbd3f-683">LASTOFMTH</span><span class="sxs-lookup"><span data-stu-id="dbd3f-683">LASTOFMTH</span></span>
- <span data-ttu-id="dbd3f-684">2OFMTH</span><span class="sxs-lookup"><span data-stu-id="dbd3f-684">2OFMTH</span></span>
- <span data-ttu-id="dbd3f-685">3OFMTH</span><span class="sxs-lookup"><span data-stu-id="dbd3f-685">3OFMTH</span></span>
- <span data-ttu-id="dbd3f-686">4OFMTH</span><span class="sxs-lookup"><span data-stu-id="dbd3f-686">4OFMTH</span></span>
- <span data-ttu-id="dbd3f-687">5OFMTH</span><span class="sxs-lookup"><span data-stu-id="dbd3f-687">5OFMTH</span></span>
- <span data-ttu-id="dbd3f-688">1N2OFMTH</span><span class="sxs-lookup"><span data-stu-id="dbd3f-688">1N2OFMTH</span></span>
- <span data-ttu-id="dbd3f-689">3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="dbd3f-689">3N4OFMTH</span></span>
- <span data-ttu-id="dbd3f-690">1N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="dbd3f-690">1N3OFMTH</span></span>
- <span data-ttu-id="dbd3f-691">1N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="dbd3f-691">1N4OFMTH</span></span>
- <span data-ttu-id="dbd3f-692">2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="dbd3f-692">2N3OFMTH</span></span>
- <span data-ttu-id="dbd3f-693">2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="dbd3f-693">2N4OFMTH</span></span>
- <span data-ttu-id="dbd3f-694">1N2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="dbd3f-694">1N2N3OFMTH</span></span>
- <span data-ttu-id="dbd3f-695">1N2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="dbd3f-695">1N2N4OFMTH</span></span>
- <span data-ttu-id="dbd3f-696">1N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="dbd3f-696">1N3N4OFMTH</span></span>
- <span data-ttu-id="dbd3f-697">2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="dbd3f-697">2N3N4OFMTH</span></span>
- <span data-ttu-id="dbd3f-698">1N2N3N4OFMTH – 1N2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="dbd3f-698">1N2N3N4OFMTH - 1N2N3N4OFMTH</span></span>
- <span data-ttu-id="dbd3f-699">2N3N4N5OFMth – 2N3N4N5OFMth</span><span class="sxs-lookup"><span data-stu-id="dbd3f-699">2N3N4N5OFMth - 2N3N4N5OFMth</span></span>
- <span data-ttu-id="dbd3f-700">1OFQTR – 1OFQTR</span><span class="sxs-lookup"><span data-stu-id="dbd3f-700">1OFQTR - 1OFQTR</span></span>
- <span data-ttu-id="dbd3f-701">LASTOFQTR – LASTOFQTR</span><span class="sxs-lookup"><span data-stu-id="dbd3f-701">LASTOFQTR – LASTOFQTR</span></span>
- <span data-ttu-id="dbd3f-702">LASTMTHOFQTR – LASTMTHOFQTR</span><span class="sxs-lookup"><span data-stu-id="dbd3f-702">LASTMTHOFQTR – LASTMTHOFQTR</span></span>
- <span data-ttu-id="dbd3f-703">1OFYEAR – 1OFYEAR</span><span class="sxs-lookup"><span data-stu-id="dbd3f-703">1OFYEAR - 1OFYEAR</span></span>
- <span data-ttu-id="dbd3f-704">LASTOFYEAR – LASTOFYEAR</span><span class="sxs-lookup"><span data-stu-id="dbd3f-704">LASTOFYEAR – LASTOFYEAR</span></span>
- <span data-ttu-id="dbd3f-705">NOVNDECOFYEAR – NOVNDECOFYEAR</span><span class="sxs-lookup"><span data-stu-id="dbd3f-705">NOVNDECOFYEAR - NOVNDECOFYEAR</span></span>

### <a name="addresses"></a><span data-ttu-id="dbd3f-706">Adresy</span><span class="sxs-lookup"><span data-stu-id="dbd3f-706">Addresses</span></span>

<span data-ttu-id="dbd3f-707">Identyfikacja określonych kodów kraju lub regionu, województwa i powiatu (gminy) wymaga określonych formatów, które potrafi rozpoznać system Dayforce oraz dostawcy wewnątrz krajów/regionów.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-707">The identification of specific country or region, state, and county (municipality) codes requires specific formats that Dayforce and in-country/in-region providers can recognize.</span></span> <span data-ttu-id="dbd3f-708">Co prawda format nazw miejscowości jest elastyczny, ale każda miejscowość musi być skojarzona z województwem.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-708">Although the format for cities is flexible, every city must be associated with a state.</span></span>

| <span data-ttu-id="dbd3f-709">Talent</span><span class="sxs-lookup"><span data-stu-id="dbd3f-709">Talent</span></span>              | <span data-ttu-id="dbd3f-710">Dayforce</span><span class="sxs-lookup"><span data-stu-id="dbd3f-710">Dayforce</span></span>              |
|---------------------|-----------------------|
| <span data-ttu-id="dbd3f-711">Kraj/region</span><span class="sxs-lookup"><span data-stu-id="dbd3f-711">Country/Region</span></span>      | <span data-ttu-id="dbd3f-712">Kod kraju</span><span class="sxs-lookup"><span data-stu-id="dbd3f-712">Country Code</span></span>          |
| <span data-ttu-id="dbd3f-713">Kod pocztowy</span><span class="sxs-lookup"><span data-stu-id="dbd3f-713">Zip/Postal Code</span></span>     | <span data-ttu-id="dbd3f-714">Kod pocztowy</span><span class="sxs-lookup"><span data-stu-id="dbd3f-714">Postal Code</span></span>           |
| <span data-ttu-id="dbd3f-715">Stanowy</span><span class="sxs-lookup"><span data-stu-id="dbd3f-715">State</span></span>               | <span data-ttu-id="dbd3f-716">Kod województwa</span><span class="sxs-lookup"><span data-stu-id="dbd3f-716">State Code</span></span>            |
| <span data-ttu-id="dbd3f-717">Miejscowość</span><span class="sxs-lookup"><span data-stu-id="dbd3f-717">City</span></span>                | <span data-ttu-id="dbd3f-718">Miejscowość</span><span class="sxs-lookup"><span data-stu-id="dbd3f-718">City</span></span>                  |
| <span data-ttu-id="dbd3f-719">Powiat</span><span class="sxs-lookup"><span data-stu-id="dbd3f-719">County</span></span>              | <span data-ttu-id="dbd3f-720">Powiat (gmina)</span><span class="sxs-lookup"><span data-stu-id="dbd3f-720">County (Municipality)</span></span> |
| <span data-ttu-id="dbd3f-721">Ulica</span><span class="sxs-lookup"><span data-stu-id="dbd3f-721">Street</span></span>              | <span data-ttu-id="dbd3f-722">Wiersz adresu 1</span><span class="sxs-lookup"><span data-stu-id="dbd3f-722">Address Line 1</span></span>        |
| <span data-ttu-id="dbd3f-723">Numer budynku</span><span class="sxs-lookup"><span data-stu-id="dbd3f-723">Street Number</span></span>       | <span data-ttu-id="dbd3f-724">Wiersz adresu 2</span><span class="sxs-lookup"><span data-stu-id="dbd3f-724">Address Line 2</span></span>        |
| <span data-ttu-id="dbd3f-725">Dodatkowe określenie budynku</span><span class="sxs-lookup"><span data-stu-id="dbd3f-725">Building Complement</span></span> | <span data-ttu-id="dbd3f-726">Wiersz adresu 5</span><span class="sxs-lookup"><span data-stu-id="dbd3f-726">Address Line 5</span></span>        |

### <a name="passport-number"></a><span data-ttu-id="dbd3f-727">Numer paszportu</span><span class="sxs-lookup"><span data-stu-id="dbd3f-727">Passport number</span></span>

<span data-ttu-id="dbd3f-728">Pracownicy mogą podać informacje z paszportów.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-728">Employees can declare passport information.</span></span> <span data-ttu-id="dbd3f-729">Te informacje mają typ identyfikacji **Paszport** i są integrowane z systemem Dayforce w ramach danych pracowników specyficznych dla Meksyku.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-729">This information is of the **Passport** identification type and is integrated into Dayforce as part of an employee's Mexico-specific information.</span></span>

- <span data-ttu-id="dbd3f-730">Typ identyfikacji = „Paszport”</span><span class="sxs-lookup"><span data-stu-id="dbd3f-730">Identification Type = "Passport"</span></span>
- <span data-ttu-id="dbd3f-731">Data wystawienia</span><span class="sxs-lookup"><span data-stu-id="dbd3f-731">Issued Date</span></span>
- <span data-ttu-id="dbd3f-732">Data ważności</span><span class="sxs-lookup"><span data-stu-id="dbd3f-732">Expiration Date</span></span>

<span data-ttu-id="dbd3f-733">Pracownicy mogą zadeklarować wiele numerów identyfikacyjnych typu **Paszport**.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-733">Employees can declare multiple identification numbers of the **Passport** identification type.</span></span> <span data-ttu-id="dbd3f-734">Jednak tylko obecnie aktywny wpis paszportu jest integrowany z usługą Dayforce.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-734">However, only the current active passport entry is integrated into Dayforce.</span></span> <span data-ttu-id="dbd3f-735">Jeśli wszystkie wpisy paszportów wygasły, z systemem Dayforce zostanie zintegrowany ostatnio wystawiony paszport.</span><span class="sxs-lookup"><span data-stu-id="dbd3f-735">If all passport entries are expired, the passport that was most recently issued is integrated into Dayforce.</span></span>
